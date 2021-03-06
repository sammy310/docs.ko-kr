---
title: ASP.NET MVC 및 ASP.NET Core에서 정적 파일을 제공 합니다.
description: IIS의 ASP.NET MVC와 비교 하 여 ASP.NET Core에서 정적 파일을 제공 하기 위한 지원을 구성 하는 데 관련 된 사항은 무엇입니까?
author: ardalis
ms.date: 11/13/2020
ms.openlocfilehash: 02f84a6985835502c24db8cc68db24c8de086b18
ms.sourcegitcommit: 42d436ebc2a7ee02fc1848c7742bc7d80e13fc2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/04/2021
ms.locfileid: "102401700"
---
# <a name="serve-static-files-in-aspnet-mvc-and-aspnet-core"></a><span data-ttu-id="2b63d-103">ASP.NET MVC 및 ASP.NET Core에서 정적 파일을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="2b63d-103">Serve static files in ASP.NET MVC and ASP.NET Core</span></span>

<span data-ttu-id="2b63d-104">대부분의 웹 앱은 클라이언트에 있는 그대로 전송 되어야 하는 서버측 논리와 정적 파일의 조합을 포함 하 고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2b63d-104">Most web apps involve a combination of server-side logic and static files that must be sent to the client as-is.</span></span> <span data-ttu-id="2b63d-105">ASP.NET MVC에서 정적 파일을 처리 하는 ASP.NET Core 처리 하는 방법은 무엇입니까?</span><span class="sxs-lookup"><span data-stu-id="2b63d-105">How should your migration from ASP.NET MVC to ASP.NET Core handle serving static files?</span></span>

## <a name="host-static-files-in-aspnet-mvc"></a><span data-ttu-id="2b63d-106">ASP.NET MVC에서 정적 파일 호스트</span><span class="sxs-lookup"><span data-stu-id="2b63d-106">Host static files in ASP.NET MVC</span></span>

<span data-ttu-id="2b63d-107">IIS에서 호스트 되는 ASP.NET MVC 앱은 일반적으로 앱에서 직접 정적 파일을 호스팅합니다.</span><span class="sxs-lookup"><span data-stu-id="2b63d-107">ASP.NET MVC apps, hosted by IIS, typically host static files directly from the app.</span></span> <span data-ttu-id="2b63d-108">ASP.NET MVC는 서버에서 전용으로 유지 해야 하는 파일을 사용 하 여 정적 파일을 나란히 배치할 수 있도록 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="2b63d-108">ASP.NET MVC supports placing static files side by side with files that should be kept private on the server.</span></span> <span data-ttu-id="2b63d-109">IIS 및 ASP.NET는 특정 파일 또는 파일 확장명이 ASP.NET 앱이 호스트 되는 폴더에서 제공 되는 것을 명시적으로 제한 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2b63d-109">IIS and ASP.NET require explicitly restricting certain files or file extensions from being served from the folder in which an ASP.NET app is hosted.</span></span>

<span data-ttu-id="2b63d-110">많은 정적 파일의 경우 CDN (content delivery network)을 사용 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="2b63d-110">For many static files, using a content delivery network (CDN) is a good practice.</span></span> <span data-ttu-id="2b63d-111">[정적 콘텐츠 호스팅을](/azure/architecture/patterns/static-content-hosting) 사용 하면 앱 서버에서 로드와 대역폭을 줄이는 동시에 성능을 향상 시킬 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2b63d-111">[Static content hosting](/azure/architecture/patterns/static-content-hosting) allows better performance while reducing load and bandwidth from app servers.</span></span>

## <a name="host-static-files-in-aspnet-core"></a><span data-ttu-id="2b63d-112">ASP.NET Core에서 정적 파일 호스트</span><span class="sxs-lookup"><span data-stu-id="2b63d-112">Host static files in ASP.NET Core</span></span>

<span data-ttu-id="2b63d-113">이는 놀라운 것일 수 있지만 ASP.NET Core는 정적 파일에 대 한 기본 제공 지원을 제공 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="2b63d-113">It may be surprising, but ASP.NET Core doesn't have built-in support for static files.</span></span> <span data-ttu-id="2b63d-114">IIS에서 사용 하는 ASP.NET의 일부로 항상 존재 하는이 기능은 ASP.NET Core 또는 Kestrel 웹 서버에 내장 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="2b63d-114">This feature that has always existed as just a part of ASP.NET, enabled by IIS, isn't intrinsic to ASP.NET Core or its Kestrel web server.</span></span> <span data-ttu-id="2b63d-115">ASP.NET Core 앱에서 정적 파일을 제공 하려면 [정적 파일 미들웨어](/aspnet/core/fundamentals/static-files)를 구성 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2b63d-115">To serve static files from an ASP.NET Core app, you must configure [static files middleware](/aspnet/core/fundamentals/static-files).</span></span>

<span data-ttu-id="2b63d-116">정적 파일 미들웨어가 구성 된 상태에서 ASP.NET Core 앱은 특정 폴더 (일반적으로 */wwwroot*)에 있는 모든 파일을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="2b63d-116">With static files middleware configured, an ASP.NET Core app will serve all files located in a certain folder (typically */wwwroot*).</span></span> <span data-ttu-id="2b63d-117">응용 프로그램 또는 프로젝트 폴더의 다른 파일은 실수로 서버에 의해 노출 될 위험이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2b63d-117">No other files in the app or project folder are at risk of being accidentally exposed by the server.</span></span> <span data-ttu-id="2b63d-118">IIS의 경우와 마찬가지로 파일 이름 또는 확장명을 기반으로 하는 특별 한 제한 사항은 구성 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2b63d-118">No special restrictions based on file names or extensions need to be configured, as is the case with IIS.</span></span> <span data-ttu-id="2b63d-119">대신 개발자가 파일을 *wwwroot* 폴더에 배치할 때 파일을 공개적으로 노출 하도록 명시적으로 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="2b63d-119">Instead, developers explicitly choose to expose files publicly when they place them in the *wwwroot* folder.</span></span> <span data-ttu-id="2b63d-120">기본적으로이 폴더의 외부에 있는 파일은 공유 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="2b63d-120">By default, files outside of this folder aren't shared.</span></span>

<span data-ttu-id="2b63d-121">정적 파일에 대 한 지원은 미들웨어를 사용 하기 때문에 다른 미들웨어는 동일한 요청 파이프라인의 일부로 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2b63d-121">Because support for static files uses middleware, any other middleware can be applied as part of the same request pipeline.</span></span> <span data-ttu-id="2b63d-122">미들웨어의 예로는 인증, 캐싱 및 압축이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2b63d-122">Examples of middleware include authentication, caching, and compression.</span></span>

<span data-ttu-id="2b63d-123">물론 ASP.NET MVC 앱에서 사용 되는 것과 동일한 모든 이유로 CDNs는 ASP.NET Core 앱에 적합 합니다.</span><span class="sxs-lookup"><span data-stu-id="2b63d-123">Of course, CDNs remain a good choice for ASP.NET Core apps for all the same reasons they're used in ASP.NET MVC apps.</span></span> <span data-ttu-id="2b63d-124">.NET Core로의 마이그레이션을 준비 하는 과정에서 앱이 CDN을 사용 하 여 실현할 수 있는 이점이 있으면 .NET Core로 마이그레이션하기 전에 CDN으로 정적 파일을 이동 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="2b63d-124">As part of preparing to migrate to .NET Core, if there are benefits your app could realize from using a CDN, it would be good to move static files to a CDN before migrating to .NET Core.</span></span> <span data-ttu-id="2b63d-125">이렇게 하면 정적 자산의 전체 마이그레이션 작업 범위가 줄어듭니다.</span><span class="sxs-lookup"><span data-stu-id="2b63d-125">Doing so reduces the migration effort's overall scope for static assets.</span></span>

## <a name="references"></a><span data-ttu-id="2b63d-126">참조</span><span class="sxs-lookup"><span data-stu-id="2b63d-126">References</span></span>

- [<span data-ttu-id="2b63d-127">정적 콘텐츠 호스팅</span><span class="sxs-lookup"><span data-stu-id="2b63d-127">Static content hosting</span></span>](/azure/architecture/patterns/static-content-hosting)
- [<span data-ttu-id="2b63d-128">ASP.NET Core의 정적 파일</span><span class="sxs-lookup"><span data-stu-id="2b63d-128">Static files in ASP.NET Core</span></span>](/aspnet/core/fundamentals/static-files)

>[!div class="step-by-step"]
><span data-ttu-id="2b63d-129">[이전](hosting-differences.md)
>[다음](dependency-injection-differences.md)</span><span class="sxs-lookup"><span data-stu-id="2b63d-129">[Previous](hosting-differences.md)
[Next](dependency-injection-differences.md)</span></span>
