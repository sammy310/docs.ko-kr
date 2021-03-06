---
title: ASP.NET MVC 및 ASP.NET Core에서 Razor 사용 비교
description: ASP.NET MVC와 ASP.NET Core에서 Razor는 어떻게 다릅니까?
author: ardalis
ms.date: 11/13/2020
ms.openlocfilehash: a9f7fa2e6b8c0c6bf61c743cf8c956b1ad09713c
ms.sourcegitcommit: 42d436ebc2a7ee02fc1848c7742bc7d80e13fc2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/04/2021
ms.locfileid: "102401718"
---
# <a name="compare-razor-usage-in-aspnet-mvc-and-aspnet-core"></a><span data-ttu-id="d2608-103">ASP.NET MVC 및 ASP.NET Core에서 Razor 사용 비교</span><span class="sxs-lookup"><span data-stu-id="d2608-103">Compare Razor usage in ASP.NET MVC and ASP.NET Core</span></span>

<span data-ttu-id="d2608-104">ASP.NET MVC와 ASP.NET Core 간에 Razor의 기본 구문이 크게 변경 되지 않았습니다.</span><span class="sxs-lookup"><span data-stu-id="d2608-104">The basic syntax of Razor hasn't changed substantially between ASP.NET MVC and ASP.NET Core.</span></span> <span data-ttu-id="d2608-105">그러나 마이그레이션할 때 고려해 야 하는 [태그 도우미](/aspnet/core/mvc/views/tag-helpers/intro) 및 Razor Pages의 소개와 같은 몇 가지 차이점이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d2608-105">However, there are certain differences, such as the introduction of [Tag Helpers](/aspnet/core/mvc/views/tag-helpers/intro) and Razor Pages, that should be considered when migrating.</span></span> <span data-ttu-id="d2608-106">앱이 사용자 지정 Razor 기능을 과도 하 게 사용 하는 경우 [ASP.NET Core에 대 한 Razor 구문 참조](/aspnet/core/razor-pages) 를 참조 하 여 ASP.NET Core로 마이그레이션할 때 필요한 변경 내용을 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="d2608-106">If your app makes heavy use of custom Razor functionality, refer to the [Razor syntax reference for ASP.NET Core](/aspnet/core/razor-pages) to see what changes may be required when you migrate to ASP.NET Core.</span></span>

## <a name="tag-helpers"></a><span data-ttu-id="d2608-107">태그 도우미</span><span class="sxs-lookup"><span data-stu-id="d2608-107">Tag Helpers</span></span>

<span data-ttu-id="d2608-108">태그 도우미를 사용하면 서버 쪽 코드를 Razor 파일에서 HTML 요소를 만들고 렌더링하는 데 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d2608-108">Tag Helpers enable server-side code to participate in creating and rendering HTML elements in Razor files.</span></span> <span data-ttu-id="d2608-109">HTML 도우미에 비해 많은 이점을 제공 하므로 가능 하면 HTML 도우미 대신 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d2608-109">They offer many advantages over HTML Helpers and should be used in place of HTML Helpers wherever possible.</span></span> <span data-ttu-id="d2608-110">Html에 친숙 한 개발 환경을 제공 합니다. 표준 HTML 처럼 보이지만 HTML 편집을 위해 디자인 된 대부분의 도구에서 무시 되기 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="d2608-110">They provide an HTML-friendly development experience, since they look like standard HTML and are ignored by most tooling designed to edit HTML.</span></span> <span data-ttu-id="d2608-111">_Visual Studio_ 내에는 태그 도우미를 사용 하 여 HTML 및 Razor 태그를 만들기 위한 다양 한 IntelliSense 지원이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d2608-111">Within _Visual Studio_, there's rich IntelliSense support for creating HTML and Razor markup with Tag Helpers.</span></span> <span data-ttu-id="d2608-112">태그 도우미는 Razor 파일의 선언 태그에서 단순 하거나 복잡 한 동작을 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d2608-112">Tag Helpers can provide simple or complex behavior from declarative markup in Razor files.</span></span>

## <a name="razor-pages"></a><span data-ttu-id="d2608-113">Razor 페이지</span><span class="sxs-lookup"><span data-stu-id="d2608-113">Razor Pages</span></span>

<span data-ttu-id="d2608-114">Razor Pages는 페이지 및 양식 기반 앱에 대 한 컨트롤러, 작업 및 보기에 대 한 대안을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="d2608-114">Razor Pages offer an alternative to controllers, actions, and views for page- and form-based apps.</span></span> <span data-ttu-id="d2608-115">[이 장 앞부분의 ASP.NET MVC와 Razor Pages 되었습니다](./comparing-razor-pages-aspnet-mvc.md).</span><span class="sxs-lookup"><span data-stu-id="d2608-115">[Razor Pages were compared to ASP.NET MVC earlier in this chapter](./comparing-razor-pages-aspnet-mvc.md).</span></span>

## <a name="references"></a><span data-ttu-id="d2608-116">참조</span><span class="sxs-lookup"><span data-stu-id="d2608-116">References</span></span>

- [<span data-ttu-id="d2608-117">ASP.NET MVC에서 ASP.NET Core MVC: 컨트롤러 및 뷰로 마이그레이션</span><span class="sxs-lookup"><span data-stu-id="d2608-117">Migrate from ASP.NET MVC to ASP.NET Core MVC: Controllers and Views</span></span>](/aspnet/core/migration/mvc#migrate-controllers-and-views)
- [<span data-ttu-id="d2608-118">ASP.NET Core의 태그 도우미</span><span class="sxs-lookup"><span data-stu-id="d2608-118">Tag Helpers in ASP.NET Core</span></span>](/aspnet/core/mvc/views/tag-helpers/intro)
- [<span data-ttu-id="d2608-119">ASP.NET Core의 Razor 페이지 소개</span><span class="sxs-lookup"><span data-stu-id="d2608-119">Introduction to Razor Pages in ASP.NET Core</span></span>](/aspnet/core/razor-pages)
- [<span data-ttu-id="d2608-120">ASP.NET Core에 대한 Razor 구문 참조</span><span class="sxs-lookup"><span data-stu-id="d2608-120">Razor syntax reference for ASP.NET Core</span></span>](/aspnet/core/razor-pages)

>[!div class="step-by-step"]
><span data-ttu-id="d2608-121">[이전](controller-differences.md)
>[다음](signalr-differences.md)</span><span class="sxs-lookup"><span data-stu-id="d2608-121">[Previous](controller-differences.md)
[Next](signalr-differences.md)</span></span>
