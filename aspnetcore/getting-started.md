---
title: ASP.NET Core 入门 | Microsoft Docs
author: rick-anderson
description: 
keywords: ASP.NET Core,
ms.author: riande
manager: wpickett
ms.date: 10/14/2016
ms.topic: article
ms.assetid: 73543e9d-d9d5-47d6-9664-17a9beea6cd3
ms.technology: aspnet
ms.prod: asp.net-core
uid: getting-started
---
# ASP.NET Core 入门

翻译：[娄宇(Lyrics)](http://github.com/xbuilder)、[刘怡(AlexLEWIS)](http://github.com/alexinea)

1.  安装 [.NET Core](https://microsoft.com/net/core)

2.  创建一个新的 .NET Core 项目：

    ```terminal
    mkdir aspnetcoreapp
    cd aspnetcoreapp
    dotnet new web
    ```
    
    注意：
    - 在 macOS 和 Linux 上，打开终端窗口（terminal window）。在 Windows 上则打开命令提示符（command prompt）。
    - 上一版本的 .NET Core 需要一个 `t` 参数，即 `dotnet new -t web`。如果你在运行 `dotnet new web` 发生错误，请安装 [.NET Core](https://microsoft.com/net/core) 的最新版本。 `dotnet`（不带参数）会显示 .NET Core 的版本。

3.  还原包：

    ```terminal
    dotnet restore
    ```

4.  运行应用程序 (`dotnet run` 命令会在应用程序过期时构建它)：

    ```terminal
    dotnet run
    ```

5.  访问 `http://localhost:5000`：

## 下一步

更多入门指南可访问 [ASP.NET Core 指南](tutorials/index.md)

可以在 [ASP.NET Core 介绍](index.md) 和 [ASP.NET Core 基本原理](fundamentals/index.md) 了解 ASP.NET Core 的原理与架构。

ASP.NET Core 应用可使用 .NET Core 运行时或 .NET Framework 运行时。更多信息浏览 [在 .NET Core 与 .NET Framework 间选择](https://docs.microsoft.com/dotnet/articles/standard/choosing-core-framework-server).
