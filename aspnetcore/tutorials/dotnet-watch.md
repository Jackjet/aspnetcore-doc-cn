---
title: 使用 dotnet watch 开发 ASP.NET Core 应用程序 | Microsoft Docs
author: rick-anderson
description: Shows how to use dotnet watch.
keywords: ASP.NET Core, using dotnet watch
ms.author: riande
manager: wpickett
ms.date: 03/09/2017
ms.topic: article
ms.assetid: 563ffb3f-d369-4aa5-bf0a-7300b4e7832c
ms.technology: aspnet
ms.prod: asp.net-core
uid: tutorials/dotnet-watch
---
# 使用 dotnet watch 开发 ASP.NET Core 应用程序


编写：[Rick Anderson](https://twitter.com/RickAndMSFT) 和 [Victor Hurdugaci](https://twitter.com/victorhurdugaci)

翻译：[谢炀（Kiler）](https://github.com/kiler398/aspnetcore)、[刘怡(AlexLEWIS)](http://github.com/alexinea)

`dotnet watch` 是一个在源文件发生变动的情况下使用 `dotnet` 命令的工具。 例如，当一个文件变化时，会触发编译、测试或发布操作。

在本教程中，我们使用一个已存在的带两个端点的 Web API：一个返回两数之和，一个返回两数之积。其中 product 方法故意包含一个错误，作为本教程的一部分我们会修复它。 

下载[示例](https://github.com/aspnet/Docs/tree/master/aspnetcore/tutorials/dotnet-watch/sample)。 它包含两个项目，`WebApp`（一个新的 Web 应用程序）和 `WebAppTests`（Web 应用程序配套的单元测试项目）。

在命令控制台程序中导航到 WebApp 所在的文件夹，然后运行以下命令：

- `dotnet restore`
- `dotnet run`

在 console 中输出的信息如下（表明该应用程序正在运行并等待请求）：

```console
$ dotnet run
Hosting environment: Production
Content root path: C:/Docs/aspnetcore/tutorials/dotnet-watch/sample/WebApp
Now listening on: http://localhost:5000
Application started. Press Ctrl+C to shut down.
```

在 Web 浏览器中，导航到 `http://localhost:5000/api/math/sum?a=4&b=5` 页面你会看到结果 `9` 。

如果你访问乘法接口 `http://localhost:5000/api/math/product?a=4&b=5`，你期望得到结果 `20`，但是实际上还是返回了 `9`。我们后面会修复它。

## 项目中添加 `dotnet watch`

- 在 *.csproj* 文件中添加 `Microsoft.DotNet.Watcher.Tools`：
 ```xml
 <ItemGroup>
   <DotNetCliToolReference Include="Microsoft.DotNet.Watcher.Tools" Version="1.0.0" />
 </ItemGroup> 
 ```

- 运行 `dotnet restore`.

## 使用 `dotnet watch` 运行 `dotnet` 命令

任何 `dotnet` 命令都可以以 `dotnet watch` 这样的方式运行，例如：

| 命令 | 带 watch 的命令 |
| ---- | ----- |
| dotnet run | dotnet watch run |
| dotnet run -f net451 | dotnet watch run -f net451 |
| dotnet run -f net451 -- --arg1 | dotnet watch run -f net451 -- --arg1 |
| dotnet test | dotnet watch test |

在 `WebApp` 文件夹中运行 `dotnet watch run`。控制台的输出信息表明 `watch` 开始生效。

## 在 `dotnet watch` 模式中修改

确认 `dotnet watch` 模式运行中。

修复 `MathController` 的 `Product` 方法，这样它就返回两数之积而非两数之和。

```csharp
public static int Product(int a, int b)
{
  return a * b;
} 
```

保存文件。控制台会输出消息以表明 `dotnet watch` 检测到文件的变化并重启应用程序。

验证 `http://localhost:5000/api/math/product?a=4&b=5` 返回正确结果。

## 使用 `dotnet watch` 运行单元测试

- 把 `MathController` 的 `Product` 方法重新变为两数之和，然后保存文件。
- 在命令行窗口中，导航到 `WebAppTests` 文件夹。
- 运行 `dotnet restore`
- 运行 `dotnet watch test`。 你会看到输出信息显示测试失败，同时监视器等待着文件变更：

 ```console
 Total tests: 2. Passed: 1. Failed: 1. Skipped: 0.
 Test Run Failed.
  ```
- 修正 `Product` 方法的代码，让它返回两数之积，然后保存文件。

`dotnet watch` 检测到文件变更后重新运行测试。控制台输出显示测试通过。

## GitHub 中的 dotnet-watch

dotnet-watch 是 GitHub [DotNetTools 仓库](https://github.com/aspnet/DotNetTools/tree/dev/src/Microsoft.DotNet.Watcher.Tools)的一部分。

[dotnet-watch ReadMe 文件](https://github.com/aspnet/DotNetTools/blob/dev/src/Microsoft.DotNet.Watcher.Tools/README.md)的 [MSBuild 节](https://github.com/aspnet/DotNetTools/blob/dev/src/Microsoft.DotNet.Watcher.Tools/README.md#msbuild)解释了 dotnet-watch 是如何从被监视的 MSBuild 项目文件中获得配置的。[dotnet-watch ReadMe 文件](https://github.com/aspnet/DotNetTools/blob/dev/src/Microsoft.DotNet.Watcher.Tools/README.md) 所包含的 dotnet-watch 信息并不涵盖本教程。
