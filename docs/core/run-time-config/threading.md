---
title: 스레딩 구성 설정
description: .NET Core 앱의 스레딩을 구성하는 런타임 설정에 대해 알아봅니다.
ms.date: 11/27/2019
ms.topic: reference
ms.openlocfilehash: 6a920dbc301830e3f4c95bf637ff3de6d4f464ff
ms.sourcegitcommit: 32a575bf4adccc901f00e264f92b759ced633379
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/04/2019
ms.locfileid: "74998830"
---
# <a name="run-time-configuration-options-for-threading"></a><span data-ttu-id="c6af8-103">스레딩을 위한 런타임 구성 옵션</span><span class="sxs-lookup"><span data-stu-id="c6af8-103">Run-time configuration options for threading</span></span>

## <a name="cpu-groups"></a><span data-ttu-id="c6af8-104">CPU 그룹</span><span class="sxs-lookup"><span data-stu-id="c6af8-104">CPU groups</span></span>

- <span data-ttu-id="c6af8-105">스레드가 여러 CPU 그룹에 자동으로 분산되는지 여부를 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="c6af8-105">Configures whether threads are automatically distributed across CPU groups.</span></span>
- <span data-ttu-id="c6af8-106">기본값: 사용 안 함(`0`).</span><span class="sxs-lookup"><span data-stu-id="c6af8-106">Default: Disabled (`0`).</span></span>

| | <span data-ttu-id="c6af8-107">설정 이름</span><span class="sxs-lookup"><span data-stu-id="c6af8-107">Setting name</span></span> | <span data-ttu-id="c6af8-108">값</span><span class="sxs-lookup"><span data-stu-id="c6af8-108">Values</span></span> |
| - | - | - |
| <span data-ttu-id="c6af8-109">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="c6af8-109">**runtimeconfig.json**</span></span> | <span data-ttu-id="c6af8-110">해당 사항 없음</span><span class="sxs-lookup"><span data-stu-id="c6af8-110">N/A</span></span> | <span data-ttu-id="c6af8-111">해당 사항 없음</span><span class="sxs-lookup"><span data-stu-id="c6af8-111">N/A</span></span> |
| <span data-ttu-id="c6af8-112">**환경 변수**</span><span class="sxs-lookup"><span data-stu-id="c6af8-112">**Environment variable**</span></span> | `COMPlus_Thread_UseAllCpuGroups` | <span data-ttu-id="c6af8-113">`0` - 사용 안 함</span><span class="sxs-lookup"><span data-stu-id="c6af8-113">`0` - disabled</span></span><br/><span data-ttu-id="c6af8-114">`1` - 사용</span><span class="sxs-lookup"><span data-stu-id="c6af8-114">`1` - enabled</span></span> |

## <a name="minimum-threads"></a><span data-ttu-id="c6af8-115">최소 스레드</span><span class="sxs-lookup"><span data-stu-id="c6af8-115">Minimum threads</span></span>

- <span data-ttu-id="c6af8-116">작업자 스레드 풀의 최소 스레드 개수를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="c6af8-116">Specifies the minimum number of threads for the worker threadpool.</span></span>
- <span data-ttu-id="c6af8-117"><xref:System.Threading.ThreadPool.SetMinThreads%2A?displayProperty=nameWithType> 메서드에 대응됩니다.</span><span class="sxs-lookup"><span data-stu-id="c6af8-117">Corresponds to the <xref:System.Threading.ThreadPool.SetMinThreads%2A?displayProperty=nameWithType> method.</span></span>

| | <span data-ttu-id="c6af8-118">설정 이름</span><span class="sxs-lookup"><span data-stu-id="c6af8-118">Setting name</span></span> | <span data-ttu-id="c6af8-119">값</span><span class="sxs-lookup"><span data-stu-id="c6af8-119">Values</span></span> |
| - | - | - |
| <span data-ttu-id="c6af8-120">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="c6af8-120">**runtimeconfig.json**</span></span> | `System.Threading.ThreadPool.MinThreads` | <span data-ttu-id="c6af8-121">최소 스레드 개수를 나타내는 정수</span><span class="sxs-lookup"><span data-stu-id="c6af8-121">An integer that represents the minimum number of threads</span></span> |
| <span data-ttu-id="c6af8-122">**환경 변수**</span><span class="sxs-lookup"><span data-stu-id="c6af8-122">**Environment variable**</span></span> | <span data-ttu-id="c6af8-123">해당 사항 없음</span><span class="sxs-lookup"><span data-stu-id="c6af8-123">N/A</span></span> | <span data-ttu-id="c6af8-124">해당 사항 없음</span><span class="sxs-lookup"><span data-stu-id="c6af8-124">N/A</span></span> |

## <a name="maximum-threads"></a><span data-ttu-id="c6af8-125">최대 스레드</span><span class="sxs-lookup"><span data-stu-id="c6af8-125">Maximum threads</span></span>

- <span data-ttu-id="c6af8-126">작업자 스레드 풀의 최대 스레드 개수를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="c6af8-126">Specifies the maximum number of threads for the worker threadpool.</span></span>
- <span data-ttu-id="c6af8-127"><xref:System.Threading.ThreadPool.SetMaxThreads%2A?displayProperty=nameWithType> 메서드에 대응됩니다.</span><span class="sxs-lookup"><span data-stu-id="c6af8-127">Corresponds to the <xref:System.Threading.ThreadPool.SetMaxThreads%2A?displayProperty=nameWithType> method.</span></span>

| | <span data-ttu-id="c6af8-128">설정 이름</span><span class="sxs-lookup"><span data-stu-id="c6af8-128">Setting name</span></span> | <span data-ttu-id="c6af8-129">값</span><span class="sxs-lookup"><span data-stu-id="c6af8-129">Values</span></span> |
| - | - | - |
| <span data-ttu-id="c6af8-130">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="c6af8-130">**runtimeconfig.json**</span></span> | `System.Threading.ThreadPool.MaxThreads` | <span data-ttu-id="c6af8-131">최대 스레드 개수를 나타내는 정수</span><span class="sxs-lookup"><span data-stu-id="c6af8-131">An integer that represents the maximum number of threads</span></span> |
| <span data-ttu-id="c6af8-132">**환경 변수**</span><span class="sxs-lookup"><span data-stu-id="c6af8-132">**Environment variable**</span></span> | <span data-ttu-id="c6af8-133">해당 사항 없음</span><span class="sxs-lookup"><span data-stu-id="c6af8-133">N/A</span></span> | <span data-ttu-id="c6af8-134">해당 사항 없음</span><span class="sxs-lookup"><span data-stu-id="c6af8-134">N/A</span></span> |
