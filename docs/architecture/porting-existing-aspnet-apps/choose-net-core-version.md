---
title: 적절한 .NET Core 버전 선택
description: 어떤 버전의 .NET Core를 대상으로 결정 해야 하나요?
author: ardalis
ms.date: 11/13/2020
ms.openlocfilehash: 401eead986ee8b67ed15be609d0b5d228773312d
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/14/2021
ms.locfileid: "102401269"
---
# <a name="choose-the-right-net-core-version"></a><span data-ttu-id="93bd4-103">적절한 .NET Core 버전 선택</span><span class="sxs-lookup"><span data-stu-id="93bd4-103">Choose the right .NET Core version</span></span>

<span data-ttu-id="93bd4-104">대상으로 하는 .NET Core 버전을 선택할 때 대부분의 조직에서 가장 큰 고려 사항은 지원 수명 주기입니다.</span><span class="sxs-lookup"><span data-stu-id="93bd4-104">The largest consideration for most organizations when choosing a version of .NET Core to target is the support lifecycle.</span></span> <span data-ttu-id="93bd4-105">LTS (장기 지원) 릴리스는 자주 제공 되지 않지만 현재 (LTS) 릴리스 보다 더 긴 지원 창이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="93bd4-105">Long Term Support (LTS) releases ship less frequently but have a longer support window than Current (non-LTS) releases.</span></span> <span data-ttu-id="93bd4-106">현재 LTS 릴리스는 1 년 마다 배송 되도록 예약 됩니다.</span><span class="sxs-lookup"><span data-stu-id="93bd4-106">Currently, LTS releases are scheduled to ship every other year.</span></span> <span data-ttu-id="93bd4-107">고객은 대상으로 지정할 릴리스를 선택할 수 있으며, 동일한 컴퓨터에 .NET Core의 다른 릴리스를 함께 설치할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="93bd4-107">Customers can choose which releases to target, and can install different releases of .NET Core side by side on the same machine.</span></span> <span data-ttu-id="93bd4-108">LTS 릴리스는 수명 주기 내내 중요 하 고 호환 되는 픽스만 받습니다.</span><span class="sxs-lookup"><span data-stu-id="93bd4-108">LTS releases will receive only critical and compatible fixes throughout their lifecycle.</span></span> <span data-ttu-id="93bd4-109">현재 릴리스는 이와 동일한 픽스를 수신 하며 호환 되는 혁신 및 기능을 사용 하 여 업데이트 됩니다.</span><span class="sxs-lookup"><span data-stu-id="93bd4-109">Current releases will receive these same fixes and will also be updated with compatible innovations and features.</span></span> <span data-ttu-id="93bd4-110">LTS 릴리스는 초기 릴리스 후 3 년 동안 지원 됩니다.</span><span class="sxs-lookup"><span data-stu-id="93bd4-110">LTS releases are supported for three years after their initial release.</span></span> <span data-ttu-id="93bd4-111">현재 릴리스는 이어지는 현재 또는 LTS 릴리스 후 3개월 동안 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="93bd4-111">Current releases are supported for three months after a subsequent Current or LTS release.</span></span>

<span data-ttu-id="93bd4-112">현재는 이전 버전의 .NET Core로 이동 하지 않았기 때문에 큰 .NET Framework 앱을 현재 .NET Core로 마이그레이션하기를 원하는 대부분의 고객이 안정적인 대상을 찾고 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="93bd4-112">Most customers looking to migrate a large .NET Framework app to .NET Core today are probably looking for a stable destination, given that they haven't already made the move to an earlier version of .NET Core.</span></span> <span data-ttu-id="93bd4-113">이 경우 마이그레이션의 대상으로 가장 적합 한 .NET Core 버전은 현재 LTS 버전인 .NET Core 3.1입니다.</span><span class="sxs-lookup"><span data-stu-id="93bd4-113">In this case, the best .NET Core version to target for the migration is .NET Core 3.1, which is the current LTS version.</span></span> <span data-ttu-id="93bd4-114">.NET Core 3.1에 대 한 지원은 12 월 2022에 종료 됩니다.</span><span class="sxs-lookup"><span data-stu-id="93bd4-114">Support for .NET Core 3.1 ends in December 2022.</span></span> <span data-ttu-id="93bd4-115">계획 된 다음 LTS 릴리스는 .NET 6.0 년 11 월 2021에 제공 될 예정입니다.</span><span class="sxs-lookup"><span data-stu-id="93bd4-115">The next planned LTS release will be .NET 6.0, slated to ship in November 2021.</span></span>

<span data-ttu-id="93bd4-116">.NET Core 3.1에서 .NET 5.0 (다음 버전)로 업데이트 하는 경우 .NET Framework에서 .NET Core로 이식 하는 것 보다 훨씬 더 많은 노력이 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="93bd4-116">Updating from .NET Core 3.1 to .NET 5.0 (the next version) requires much less effort than porting from .NET Framework to .NET Core.</span></span> <span data-ttu-id="93bd4-117">따라서 대부분의 고객에 대 한 권장 사항은 먼저 .NET Core 3.1로 업그레이드 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="93bd4-117">For this reason, the recommendation for most customers is to upgrade to .NET Core 3.1 first.</span></span> <span data-ttu-id="93bd4-118">그런 다음 나중에 업그레이드 하기 전에 다음 업데이트가 최신 릴리스 (.NET 5.0)로 되어야 하는지 아니면 다음 LTS 릴리스 (.NET 6.0)를 기다려야 하는지 결정 합니다.</span><span class="sxs-lookup"><span data-stu-id="93bd4-118">Then decide whether the next update should be to the latest current release (.NET 5.0) or to wait for the next LTS release (.NET 6.0) before upgrading further.</span></span>

<span data-ttu-id="93bd4-119">이 책에서는 .NET Framework 앱이 .NET Core 3.1로 업그레이드 된다고 가정 합니다.</span><span class="sxs-lookup"><span data-stu-id="93bd4-119">This book assumes .NET Framework apps will be upgraded to .NET Core 3.1.</span></span>

## <a name="references"></a><span data-ttu-id="93bd4-120">참조</span><span class="sxs-lookup"><span data-stu-id="93bd4-120">References</span></span>

[<span data-ttu-id="93bd4-121">.NET Core 및 .NET 5 지원 정책</span><span class="sxs-lookup"><span data-stu-id="93bd4-121">.NET Core and .NET 5 Support Policy</span></span>](https://dotnet.microsoft.com/platform/support/policy/dotnet-core)

>[!div class="step-by-step"]
><span data-ttu-id="93bd4-122">[이전](migrate-aspnet-core-2-1.md)
>[다음](incremental-migration-strategies.md)</span><span class="sxs-lookup"><span data-stu-id="93bd4-122">[Previous](migrate-aspnet-core-2-1.md)
[Next](incremental-migration-strategies.md)</span></span>
