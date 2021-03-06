---
title: ASP.NET Core에 대 한 대량 솔루션 마이그레이션
description: ASP.NET Core로 large ASP.NET MVC 앱을 마이그레이션하는 방법에 대해 살펴봅니다.
author: ardalis
ms.date: 11/13/2020
ms.openlocfilehash: d3ebd71213e074ce80dc83fc3230c4e365275ad3
ms.sourcegitcommit: 42d436ebc2a7ee02fc1848c7742bc7d80e13fc2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/04/2021
ms.locfileid: "102401729"
---
# <a name="migrate-large-solutions-to-aspnet-core"></a><span data-ttu-id="7ad33-103">ASP.NET Core에 대 한 대량 솔루션 마이그레이션</span><span class="sxs-lookup"><span data-stu-id="7ad33-103">Migrate large solutions to ASP.NET Core</span></span>

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

<span data-ttu-id="7ad33-104">.NET Framework에서 .NET Core로 규모가 많은 솔루션을 마이그레이션하려면 몇 가지 계획이 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="7ad33-104">Migrating large solutions from .NET Framework to .NET Core requires some planning.</span></span> <span data-ttu-id="7ad33-105">종속성은 해당 종속성을 기반으로 하는 프로젝트 보다 먼저 마이그레이션하거나 업데이트 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7ad33-105">Dependencies must be migrated or updated before the projects that depend on them.</span></span> <span data-ttu-id="7ad33-106">종속성을 식별 하 고 .NET Core로 마이그레이션하는 데 도움을 줄 수 있는 도구를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="7ad33-106">There are tools that can identify dependencies and offer help with migrating to .NET Core.</span></span> <span data-ttu-id="7ad33-107">앱, 해당 범위 및 현재 사용 패턴에 따라 마이그레이션할 때 다양 한 전략을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7ad33-107">Depending on the app, its scope, and current usage patterns, different strategies may be employed when migrating.</span></span> <span data-ttu-id="7ad33-108">모든 작업을 한 번에 또는 현재 시스템과 함께 병렬로 마이그레이션 하나요?</span><span class="sxs-lookup"><span data-stu-id="7ad33-108">Do you migrate it all at once, or over time, side-by-side with the current system?</span></span> <span data-ttu-id="7ad33-109">현재 시스템을 새 시스템으로 래핑하고 해당 기능을 증분 방식으로 바꾸시겠습니까?</span><span class="sxs-lookup"><span data-stu-id="7ad33-109">Do you wrap the current system in the new one, and incrementally replace its functionality?</span></span>

<span data-ttu-id="7ad33-110">이 장에서는 대량 솔루션에 대 한 마이그레이션 계획을 만드는 방법, 마이그레이션에 도움이 되는 도구를 사용 하는 방법 및 마이그레이션 자체를 고려 하는 몇 가지 전략에 대해 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="7ad33-110">In this chapter, you'll learn how create a migration plan for a large solution, how to use tools to help with the migration, and some strategies to consider for the migration itself.</span></span>

## <a name="references"></a><span data-ttu-id="7ad33-111">참조</span><span class="sxs-lookup"><span data-stu-id="7ad33-111">References</span></span>

- [<span data-ttu-id="7ad33-112">큰 MVC 및 Web API 앱을 .NET Core로 마이그레이션하는 데 중요 한 항목은 무엇 인가요?</span><span class="sxs-lookup"><span data-stu-id="7ad33-112">What topics are important to migrating large MVC and Web API apps to .NET Core?</span></span>](https://twitter.com/ardalis/status/1313669040859217921)
- [<span data-ttu-id="7ad33-113">.NET Framework에서 .NET Core로 이식</span><span class="sxs-lookup"><span data-stu-id="7ad33-113">Porting from .NET Framework to .NET Core</span></span>](../../core/porting/index.md)

>[!div class="step-by-step"]
><span data-ttu-id="7ad33-114">[이전](testing-differences.md)
>[다음](identify-migration-sequence.md)</span><span class="sxs-lookup"><span data-stu-id="7ad33-114">[Previous](testing-differences.md)
[Next](identify-migration-sequence.md)</span></span>
