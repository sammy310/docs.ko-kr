---
title: ASP.NET MVC와 ASP.NET Core의 아키텍처 차이점
description: ASP.NET와 ASP.NET Core 간의 아키텍처 차이를 검토 합니다.
author: ardalis
ms.date: 11/13/2020
ms.openlocfilehash: 96477f2393482380eee9891e9b2dbbb6445e15bd
ms.sourcegitcommit: 42d436ebc2a7ee02fc1848c7742bc7d80e13fc2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/04/2021
ms.locfileid: "102401820"
---
# <a name="architectural-differences-between-aspnet-mvc-and-aspnet-core"></a><span data-ttu-id="c952b-103">ASP.NET MVC와 ASP.NET Core의 아키텍처 차이점</span><span class="sxs-lookup"><span data-stu-id="c952b-103">Architectural differences between ASP.NET MVC and ASP.NET Core</span></span>

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

<span data-ttu-id="c952b-104">.NET Framework와 ASP.NET Core ASP.NET MVC 간에는 많은 아키텍처 차이가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c952b-104">There are many architectural differences between ASP.NET MVC on .NET Framework and ASP.NET Core.</span></span> <span data-ttu-id="c952b-105">팀에서 ASP.NET MVC 앱을 ASP.NET Core로 이식 하는 데 관련 된 작업을 평가할 때 이러한 차이를 광범위 하 게 이해 하는 것이 중요 합니다.</span><span class="sxs-lookup"><span data-stu-id="c952b-105">It's important to have a broad understanding of these differences as teams evaluate the work involved in porting their ASP.NET MVC apps to ASP.NET Core.</span></span> <span data-ttu-id="c952b-106">이 장에서는 ASP.NET Core ASP.NET MVC와 크게 다른 방법에 대해 살펴봅니다.</span><span class="sxs-lookup"><span data-stu-id="c952b-106">This chapter looks at each of the ways in which ASP.NET Core differs substantially from ASP.NET MVC.</span></span>

## <a name="breaking-changes"></a><span data-ttu-id="c952b-107">주요 변경 내용</span><span class="sxs-lookup"><span data-stu-id="c952b-107">Breaking changes</span></span>

<span data-ttu-id="c952b-108">.NET Core는 .NET Framework의 플랫폼 간 재작성입니다.</span><span class="sxs-lookup"><span data-stu-id="c952b-108">.NET Core is a cross-platform rewrite of .NET Framework.</span></span> <span data-ttu-id="c952b-109">[두 프레임 워크 사이에는 몇 가지 주요 변경 사항이](../../core/compatibility/fx-core.md)있습니다.</span><span class="sxs-lookup"><span data-stu-id="c952b-109">There are many [breaking changes between the two frameworks](../../core/compatibility/fx-core.md).</span></span> <span data-ttu-id="c952b-110">다음 섹션에서는 ASP.NET MVC와 ASP.NET Core 앱이 설계 및 개발 되는 방식 간의 구체적인 차이점을 식별 합니다.</span><span class="sxs-lookup"><span data-stu-id="c952b-110">The following sections identify specific differences between how ASP.NET MVC and ASP.NET Core apps are designed and developed.</span></span> <span data-ttu-id="c952b-111">또한 설명서를 검토 하 여 변경 해야 할 수 있는 사용 중인 프레임 워크 라이브러리를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="c952b-111">Take care to also examine the documentation to determine which framework libraries you're using that may need to change.</span></span> <span data-ttu-id="c952b-112">대부분의 경우 .NET Framework와 .NET Core 사이에서 남은 간격을 채우도록 대체 NuGet 패키지가 존재 합니다.</span><span class="sxs-lookup"><span data-stu-id="c952b-112">In many cases, a replacement NuGet package exists to fill in any gaps left between .NET Framework and .NET Core.</span></span> <span data-ttu-id="c952b-113">드문 경우 지만 타사 솔루션을 찾거나 새로운 사용자 지정 코드를 구현 하 여 비 호환성 문제를 해결 해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c952b-113">In rare cases, you may need to find a third-party solution or implement new custom code to address incompatibilities.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="c952b-114">[이전](additional-migration-resources.md)
>[다음](app-startup-differences.md)</span><span class="sxs-lookup"><span data-stu-id="c952b-114">[Previous](additional-migration-resources.md)
[Next](app-startup-differences.md)</span></span>
