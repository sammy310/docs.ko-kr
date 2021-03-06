---
title: .NET Core로 앱 포팅 소개
description: 이 장에서는 기존 ASP.NET apps를 .NET Core로 마이그레이션하기를 고려 하는 팀에 대 한 고려 사항 목록을 다룹니다.
author: ardalis
ms.date: 11/13/2020
ms.openlocfilehash: a346d1c693389cc4ca682b41a3b7fc094cfa5482
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/14/2021
ms.locfileid: "102401232"
---
# <a name="introduction-to-porting-apps-to-net-core"></a><span data-ttu-id="8ded3-103">.NET Core로 앱 포팅 소개</span><span class="sxs-lookup"><span data-stu-id="8ded3-103">Introduction to porting apps to .NET Core</span></span>

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

<span data-ttu-id="8ded3-104">.NET Core는 .NET Framework에서 혁신 단계로 진행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8ded3-104">.NET Core is a revolutionary step forward from .NET Framework.</span></span> <span data-ttu-id="8ded3-105">플랫폼 간 지원에서 개발자 만족도까지 보드 전체에서 생산성까지 .NET Framework에 비해 이점을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="8ded3-105">It offers a host of advantages over .NET Framework across the board from productivity to performance, from cross-platform support to developer satisfaction.</span></span> <span data-ttu-id="8ded3-106">ASP.NET Core는 [2020 Stack Overflow 개발자 설문 조사](https://insights.stackoverflow.com/survey/2020#technology-most-loved-dreaded-and-wanted-web-frameworks)에서 좋아했던 웹 프레임 워크에도 투표 했습니다.</span><span class="sxs-lookup"><span data-stu-id="8ded3-106">ASP.NET Core was even voted the most-loved web framework in the [2020 Stack Overflow developer survey](https://insights.stackoverflow.com/survey/2020#technology-most-loved-dreaded-and-wanted-web-frameworks).</span></span> <span data-ttu-id="8ded3-107">마이그레이션을 고려해 야 하는 강력한 이유가 분명히 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8ded3-107">Clearly there are strong reasons to consider migrating.</span></span>

<span data-ttu-id="8ded3-108">.Net [Core가 .net의 미래](https://devblogs.microsoft.com/dotnet/net-core-is-the-future-of-net/)임을 명심 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8ded3-108">It's important to keep in mind that [.NET Core is the Future of .NET](https://devblogs.microsoft.com/dotnet/net-core-is-the-future-of-net/).</span></span> <span data-ttu-id="8ded3-109">이 문서를 인용 하려면:</span><span class="sxs-lookup"><span data-stu-id="8ded3-109">To quote this article:</span></span>

> <span data-ttu-id="8ded3-110">새 앱은 .NET Core를 기반으로 빌드해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8ded3-110">New apps should be built on .NET Core.</span></span> <span data-ttu-id="8ded3-111">.NET Core는 .NET에 대 한 향후 투자를 발생 시킬 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8ded3-111">.NET Core is where future investments in .NET will happen.</span></span> <span data-ttu-id="8ded3-112">기존 앱은 지원 되는 .NET Framework에 유지 해도 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8ded3-112">Existing apps are safe to remain on .NET Framework which will be supported.</span></span> <span data-ttu-id="8ded3-113">.NET의 새로운 기능을 활용 하려는 기존 앱은 .NET Core로 이동 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="8ded3-113">Existing apps that want to take advantage of the new features in .NET should consider moving to .NET Core.</span></span> <span data-ttu-id="8ded3-114">앞으로 계획할 때 플랫폼에 훨씬 더 많은 기능을 제공 하 게 될 예정입니다.</span><span class="sxs-lookup"><span data-stu-id="8ded3-114">As we plan into the future, we will be bringing in even more capabilities to the platform.</span></span>

<span data-ttu-id="8ded3-115">그러나 앱을 ASP.NET Core로 업그레이드 하는 데는 몇 가지 노력이 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="8ded3-115">However, upgrading your app to ASP.NET Core will require some effort.</span></span> <span data-ttu-id="8ded3-116">이러한 작업은 비즈니스 가치 및 목표에 따라 균형을 맞춰야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8ded3-116">That effort should be balanced against business value and goals.</span></span> <span data-ttu-id="8ded3-117">.NET Framework 앱은 곧 Windows에 기본적으로 제공 되는 기능을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="8ded3-117">.NET Framework apps have a long life ahead of them, with support built into Windows for the foreseeable future.</span></span> <span data-ttu-id="8ded3-118">.NET Core로의 마이그레이션을 결정 하기 전에 고려해 야 할 몇 가지 질문은 무엇 인가요?</span><span class="sxs-lookup"><span data-stu-id="8ded3-118">What are some of the questions you should consider before deciding migration to .NET Core is appropriate?</span></span> <span data-ttu-id="8ded3-119">예상 이점은 무엇 인가요?</span><span class="sxs-lookup"><span data-stu-id="8ded3-119">What are the expected advantages?</span></span> <span data-ttu-id="8ded3-120">절충은 무엇 인가요?</span><span class="sxs-lookup"><span data-stu-id="8ded3-120">What are the tradeoffs?</span></span> <span data-ttu-id="8ded3-121">얼마나 많은 노력이 필요 한가요?</span><span class="sxs-lookup"><span data-stu-id="8ded3-121">How much effort is involved?</span></span> <span data-ttu-id="8ded3-122">이러한 명백한 질문은 단지 시작 이지만 팀에서 현재 및 내일 앱에 대 한 고객의 요구를 지 원하는 방법을 고려 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="8ded3-122">These obvious questions are just the beginning, but make for a great starting point as teams consider how to support their customers' needs with apps today and tomorrow.</span></span>

- <span data-ttu-id="8ded3-123">.NET Core로의 마이그레이션이 적절 합니까?</span><span class="sxs-lookup"><span data-stu-id="8ded3-123">Is migration to .NET Core appropriate?</span></span>
- <span data-ttu-id="8ded3-124">.NET Framework를 그대로 유지 하는 것이 적합 한가요?</span><span class="sxs-lookup"><span data-stu-id="8ded3-124">When does it make sense to remain on .NET Framework?</span></span>
- <span data-ttu-id="8ded3-125">앱이 ASP.NET Core 2.1를 스테핑 돌로 대상으로 지정 해야 하나요?</span><span class="sxs-lookup"><span data-stu-id="8ded3-125">Should apps target ASP.NET Core 2.1 as a stepping stone?</span></span>
- <span data-ttu-id="8ded3-126">팀에서 대상으로 적합 한 .NET Core 버전을 어떻게 선택 하나요?</span><span class="sxs-lookup"><span data-stu-id="8ded3-126">How should teams choose the right .NET Core version to target?</span></span>
- <span data-ttu-id="8ded3-127">대량 앱의 증분 마이그레이션에 권장 되는 전략은 무엇 인가요?</span><span class="sxs-lookup"><span data-stu-id="8ded3-127">What strategies are recommended for incremental migration of large apps?</span></span>
- <span data-ttu-id="8ded3-128">.NET Core로 이식할 때 고려해 야 할 배포 전략은 무엇 인가요?</span><span class="sxs-lookup"><span data-stu-id="8ded3-128">What deployment strategies should be considered when porting to .NET Core?</span></span>
- <span data-ttu-id="8ded3-129">추가 리소스는 어디에서 찾을 수 있나요?</span><span class="sxs-lookup"><span data-stu-id="8ded3-129">Where can we find additional resources?</span></span>

<span data-ttu-id="8ded3-130">이 소개 장에서는 이후 챕터에서 보다 구체적인 기술 고려 사항으로 이동 하기 전에 이러한 모든 질문과 대답을 다룹니다.</span><span class="sxs-lookup"><span data-stu-id="8ded3-130">This introductory chapter addresses all of these questions and more before moving on to more specific and technical considerations in future chapters.</span></span>

## <a name="references"></a><span data-ttu-id="8ded3-131">참조</span><span class="sxs-lookup"><span data-stu-id="8ded3-131">References</span></span>

- [<span data-ttu-id="8ded3-132">2020 Stack Overflow 개발자 설문 조사 가장 좋아했던 웹 프레임 워크</span><span class="sxs-lookup"><span data-stu-id="8ded3-132">2020 Stack Overflow developer survey most loved web frameworks</span></span>](https://insights.stackoverflow.com/survey/2020#technology-most-loved-dreaded-and-wanted-web-frameworks)
- [<span data-ttu-id="8ded3-133">.Net Core는 .NET의 미래입니다.</span><span class="sxs-lookup"><span data-stu-id="8ded3-133">.NET Core is the Future of .NET</span></span>](https://devblogs.microsoft.com/dotnet/net-core-is-the-future-of-net/)

>[!div class="step-by-step"]
><span data-ttu-id="8ded3-134">[이전](index.md)
>[다음](migration-considerations.md)</span><span class="sxs-lookup"><span data-stu-id="8ded3-134">[Previous](index.md)
[Next](migration-considerations.md)</span></span>
