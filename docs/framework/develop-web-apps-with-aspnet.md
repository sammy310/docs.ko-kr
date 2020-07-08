---
title: ASP.NET을 사용하여 웹 애플리케이션 개발
description: ASP.NET Core를 사용하여 웹앱을 개발합니다. ASP.NET Core는 웹 UI 및 웹 API를 빌드하기 위해 효율성과 모듈성이 강화된 통합형 플랫폼 간 프레임워크인 ASP.NET 4.x를 재설계한 것입니다.
ms.date: 09/25/2018
helpviewer_keywords:
- ASP.NET
- .NET Framework, ASP.NET
- dynamic Web applications [ASP.NET]
ms.assetid: b7861df0-690a-4a58-bd12-f9d0123e40df
ms.openlocfilehash: 82f6b9421abbfd9f547cac1c7e08c63de2b2cf48
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.contentlocale: ko-KR
ms.lasthandoff: 07/01/2020
ms.locfileid: "85619379"
---
# <a name="developing-web-apps-with-aspnet"></a><span data-ttu-id="f0cf1-103">ASP.NET을 사용하여 웹앱 개발</span><span class="sxs-lookup"><span data-stu-id="f0cf1-103">Developing Web apps with ASP.NET</span></span>

<span data-ttu-id="f0cf1-104">ASP.NET은 웹 응용 프로그램을 만들기 위한 .NET Framework 기술입니다.</span><span class="sxs-lookup"><span data-stu-id="f0cf1-104">ASP.NET is a .NET Framework technology for creating web apps.</span></span> <span data-ttu-id="f0cf1-105">ASP.NET에 대한 자세한 내용은 다음을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f0cf1-105">For more information on ASP.NET, see:</span></span>

- [<span data-ttu-id="f0cf1-106">ASP.NET 설명서</span><span class="sxs-lookup"><span data-stu-id="f0cf1-106">ASP.NET documentation</span></span>](/aspnet/overview)
- [<span data-ttu-id="f0cf1-107">ASP.NET MVC</span><span class="sxs-lookup"><span data-stu-id="f0cf1-107">ASP.NET MVC</span></span>](https://dotnet.microsoft.com/apps/aspnet/mvc)
- [<span data-ttu-id="f0cf1-108">ASP.NET 웹 페이지 2</span><span class="sxs-lookup"><span data-stu-id="f0cf1-108">ASP.NET Web Pages</span></span>](https://dotnet.microsoft.com/apps/aspnet/web-apps)
- [<span data-ttu-id="f0cf1-109">ASP.NET Web API</span><span class="sxs-lookup"><span data-stu-id="f0cf1-109">ASP.NET Web API</span></span>](https://dotnet.microsoft.com/apps/aspnet/apis)  
- [<span data-ttu-id="f0cf1-110">Azure에서 ASP.NET Framework 웹앱 만들기</span><span class="sxs-lookup"><span data-stu-id="f0cf1-110">Create an ASP.NET Framework web app in Azure</span></span>](/azure/app-service/app-service-web-get-started-dotnet-framework)

## <a name="developing-web-apps-with-aspnet-core"></a><span data-ttu-id="f0cf1-111">ASP.NET Core를 사용하여 웹앱 개발</span><span class="sxs-lookup"><span data-stu-id="f0cf1-111">Developing Web apps with ASP.NET Core</span></span>

<span data-ttu-id="f0cf1-112">ASP.NET Core는 ASP.NET 4.x를 새롭게 디자인한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="f0cf1-112">ASP.NET Core is a redesign of ASP.NET 4.x.</span></span> <span data-ttu-id="f0cf1-113">ASP.NET Core가 ASP.NET을 통해 제공하는 몇 가지 이점은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="f0cf1-113">Some of the benefits ASP.NET Core provides over ASP.NET:</span></span>

- <span data-ttu-id="f0cf1-114">플랫폼 간에 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f0cf1-114">Cross platform.</span></span>
- <span data-ttu-id="f0cf1-115">더 간결하고 더 모듈식인 도구입니다.</span><span class="sxs-lookup"><span data-stu-id="f0cf1-115">Leaner and more modular.</span></span>
- <span data-ttu-id="f0cf1-116">웹 UI 및 웹 API를 동일한 과정으로 빌드합니다.</span><span class="sxs-lookup"><span data-stu-id="f0cf1-116">A unified story for building web UI and web APIs.</span></span>

<span data-ttu-id="f0cf1-117">추가 이점 목록을 보려면 [ASP.NET Core를 사용하는 이유는 무엇인가요?](/aspnet/core/introduction-to-aspnet-core#why-choose-aspnet-core)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f0cf1-117">See [Why use ASP.NET Core?](/aspnet/core/introduction-to-aspnet-core#why-choose-aspnet-core) for an expanded list of benefits.</span></span>

<span data-ttu-id="f0cf1-118">ASP.NET Core(/aspnet/core)에 대한 자세한 내용은 다음을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f0cf1-118">For more information on ASP.NET Core](/aspnet/core), see:</span></span>

- [<span data-ttu-id="f0cf1-119">Razor 페이지 시작</span><span class="sxs-lookup"><span data-stu-id="f0cf1-119">Get started with Razor Pages</span></span>](/aspnet/core/tutorials/razor-pages/razor-pages-start)
- [<span data-ttu-id="f0cf1-120">Web API 만들기</span><span class="sxs-lookup"><span data-stu-id="f0cf1-120">Create a Web API</span></span>](/aspnet/core/tutorials/first-web-api)
- [<span data-ttu-id="f0cf1-121">Azure에서 ASP.NET Core 웹앱 만들기</span><span class="sxs-lookup"><span data-stu-id="f0cf1-121">Create an ASP.NET Core web app in Azure</span></span>](/azure/app-service/app-service-web-get-started-dotnet)
  
## <a name="see-also"></a><span data-ttu-id="f0cf1-122">참조</span><span class="sxs-lookup"><span data-stu-id="f0cf1-122">See also</span></span>

- [<span data-ttu-id="f0cf1-123">개발 가이드</span><span class="sxs-lookup"><span data-stu-id="f0cf1-123">Development Guide</span></span>](development-guide.md)
