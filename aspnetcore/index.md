---
title: ASP.NET Core 介绍 | Microsoft Docs
author: rick-anderson
description: 
keywords: ASP.NET Core,
ms.author: riande
manager: wpickett
ms.date: 10/14/2016
ms.topic: article
ms.assetid: 1c501638-114a-4cd3-ad39-0a5790b4e764
ms.technology: aspnet
ms.prod: asp.net-core
uid: index
---
# ASP.NET Core 介绍

编写：[Daniel Roth](https://github.com/danroth27)、[Rick Anderson](https://twitter.com/RickAndMSFT)、[Shaun Luttin](https://twitter.com/dicshaunary)

翻译：[江振宇(Kerry Jiang)](http://github.com/kerryjiang)、[刘怡(AlexLEWIS)](http://github.com/alexinea)（修订）

ASP.NET Core 是对 ASP.NET 的一次意义重大的重新设计。本文介绍了 ASP.NET Core 中的一些新概念，并解释了它们如何帮助你开发现代的 Web 应用程序。

## 什么是 ASP.NET Core？

ASP.NET Core 是一个新的开源和跨平台的框架，用于构建如 Web 应用、物联网（IoT）应用和移动后端应用等连接到互联网的基于云的现代应用程序。ASP.NET Core 应用可运行于 [.NET Core](https://www.microsoft.com/net/core/platform) 和完整的 .NET Framework 之上。 构建它的目的是为那些部署在云端或者内部运行（on-premises）的应用提供一个优化的开发框架。它由最小开销的模块化的组件构成，因此在构建你的解决方案的同时可以保持灵活性。你可以在 Windows、Mac 和 Linux 上跨平台的开发和运行你的 ASP.NET Core 应用。 ASP.NET Core 开源在 [GitHub](https://github.com/aspnet/home) 上。

## 为什么构建 ASP.NET Core？

ASP.NET 的首个预览版作为 .NET Framework 的一部分发布于15年前。自那以后数百万的开发者用它开发和运行着众多非常棒的 Web 应用，而且在这么多年之间我们也为它增加和改进了很多的功能。

ASP.NET Core 有一些架构上的改变，这些改变会使它成为一个更为精简并且模块化的框架。ASP.NET Core 不再基于 *System.Web.dll*。当前它基于一系列颗粒化的，并且良好构建的 [NuGet](http://www.nuget.org/) 包。这一特点能够让你通过仅仅包含需要的 NuGet 包的方法来优化你的应用。一个更小的应用程序接口通过“按需使用（pay-for-what-you-use）”的模型获得的好处包括更可靠的安全性、简化服务、改进性能和减少成本。

通过 ASP.NET Core，你可以获得的改进：

* 一个用于构建 web UI 和 web APIs 的统一的方式

* 集成[现代的客户端侧开发框架](client-side/index.md)和开发流程

* 一个适用于云的,基于环境的[配置系统](fundamentals/configuration.md)

* 内置的[依赖注入](fundamentals/dependency-injection.md)

* 新型的轻量级的、模块化 HTTP 请求管道

* 运行于 IIS 或者自宿主（self-host）于你自己的进程的能力

* 基于支持真正的 side-by-side 应用程序版本化的 [.NET Core](https://microsoft.com/net/core) 构建

* 完全以 [NuGet](https://nuget.org) 包的形式发布

* 新的用于简化现代 web 开发的工具

* 可以在 Windows 、Mac 和 Linux 上构建和运行跨平台的 ASP.NET 应用

* 开源并重视社区

## 使用 ASP.NET Core MVC 构建 web UI 和 web APIs

* 你可以使用 Model-View-Controller（MVC）模式创建优秀的并且可测试的 web 应用程序。查看 [MVC](mvc/index.md) 和[测试](testing/index.md).

* 你可以构建支持多种格式并且完全支持内容协商的 HTTP 服务。查看[格式化响应数据](mvc/models/formatting.md)

* [Razor](http://www.asp.net/web-pages/overview/getting-started/introducing-razor-syntax-c) 提供了一种高效的语言用于创建 [Views](mvc/views/index.md)

* [Tag Helpers](mvc/views/tag-helpers/intro.md) 启用服务器端的代码参与到 Razor 文件的创建和 HTML 元素渲染

* 你可以使用自定义或者内置的 formatters （JSON， XML）来构建完全支持内容协商的 HTTP 服务

* [模型绑定](mvc/models/model-binding.md) 自动的映射 HTTP 请求中的数据到动作（Action）方法参数

* [模型验证](mvc/models/validation.md) 自动的执行客户端和服务器端验证

## 客户端侧开发

ASP.NET Core 在设计时已考虑到和各种客户端框架的无缝集成，包括 [AngularJS](client-side/angular.md)、[KnockoutJS](client-side/knockout.md) 以及 [Bootstrap](client-side/bootstrap.md)。查看 [客户端侧开发](client-side/index.md)获取更多信息。

## 下一步

入门指南，查看 [ASP.NET Core 指南](tutorials/index.md)

进一步 介绍ASP.NET Core 的原理与架构，查看 [ASP.NET Core 基本原理](fundamentals/index.md)。

ASP.NET Core 应用可使用 .NET Core 运行时或 .NET Framework 运行时。更多信息浏览 [在 .NET Core 与 .NET Framework 间选择](https://docs.microsoft.com/dotnet/articles/standard/choosing-core-framework-server)。

