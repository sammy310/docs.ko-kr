---
title: 스레딩 구성 설정
description: .NET Core 앱의 스레딩을 구성하는 런타임 설정에 대해 알아봅니다.
ms.date: 11/27/2019
ms.topic: reference
ms.openlocfilehash: ed7688d4d8f7178440fe59afc6e2f5e0a11b2a5c
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/24/2020
ms.locfileid: "76733425"
---
# <a name="run-time-configuration-options-for-threading"></a><span data-ttu-id="9b8e9-103">스레딩을 위한 런타임 구성 옵션</span><span class="sxs-lookup"><span data-stu-id="9b8e9-103">Run-time configuration options for threading</span></span>

## <a name="cpu-groups"></a><span data-ttu-id="9b8e9-104">CPU 그룹</span><span class="sxs-lookup"><span data-stu-id="9b8e9-104">CPU groups</span></span>

- <span data-ttu-id="9b8e9-105">스레드가 여러 CPU 그룹에 자동으로 분산되는지 여부를 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="9b8e9-105">Configures whether threads are automatically distributed across CPU groups.</span></span>
- <span data-ttu-id="9b8e9-106">기본값: 사용 안 함(`0`).</span><span class="sxs-lookup"><span data-stu-id="9b8e9-106">Default: Disabled (`0`).</span></span>

| | <span data-ttu-id="9b8e9-107">설정 이름</span><span class="sxs-lookup"><span data-stu-id="9b8e9-107">Setting name</span></span> | <span data-ttu-id="9b8e9-108">값</span><span class="sxs-lookup"><span data-stu-id="9b8e9-108">Values</span></span> |
| - | - | - |
| <span data-ttu-id="9b8e9-109">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="9b8e9-109">**runtimeconfig.json**</span></span> | <span data-ttu-id="9b8e9-110">N/A</span><span class="sxs-lookup"><span data-stu-id="9b8e9-110">N/A</span></span> | <span data-ttu-id="9b8e9-111">N/A</span><span class="sxs-lookup"><span data-stu-id="9b8e9-111">N/A</span></span> |
| <span data-ttu-id="9b8e9-112">**환경 변수**</span><span class="sxs-lookup"><span data-stu-id="9b8e9-112">**Environment variable**</span></span> | `COMPlus_Thread_UseAllCpuGroups` | <span data-ttu-id="9b8e9-113">`0` - 사용 안 함</span><span class="sxs-lookup"><span data-stu-id="9b8e9-113">`0` - disabled</span></span><br/><span data-ttu-id="9b8e9-114">`1` - 사용</span><span class="sxs-lookup"><span data-stu-id="9b8e9-114">`1` - enabled</span></span> |

## <a name="minimum-threads"></a><span data-ttu-id="9b8e9-115">최소 스레드</span><span class="sxs-lookup"><span data-stu-id="9b8e9-115">Minimum threads</span></span>

- <span data-ttu-id="9b8e9-116">작업자 스레드 풀의 최소 스레드 개수를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="9b8e9-116">Specifies the minimum number of threads for the worker threadpool.</span></span>
- <span data-ttu-id="9b8e9-117"><xref:System.Threading.ThreadPool.SetMinThreads%2A?displayProperty=nameWithType> 메서드에 대응됩니다.</span><span class="sxs-lookup"><span data-stu-id="9b8e9-117">Corresponds to the <xref:System.Threading.ThreadPool.SetMinThreads%2A?displayProperty=nameWithType> method.</span></span>

| | <span data-ttu-id="9b8e9-118">설정 이름</span><span class="sxs-lookup"><span data-stu-id="9b8e9-118">Setting name</span></span> | <span data-ttu-id="9b8e9-119">값</span><span class="sxs-lookup"><span data-stu-id="9b8e9-119">Values</span></span> |
| - | - | - |
| <span data-ttu-id="9b8e9-120">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="9b8e9-120">**runtimeconfig.json**</span></span> | `System.Threading.ThreadPool.MinThreads` | <span data-ttu-id="9b8e9-121">최소 스레드 개수를 나타내는 정수</span><span class="sxs-lookup"><span data-stu-id="9b8e9-121">An integer that represents the minimum number of threads</span></span> |
| <span data-ttu-id="9b8e9-122">**MSBuild 속성**</span><span class="sxs-lookup"><span data-stu-id="9b8e9-122">**MSBuild property**</span></span> | `ThreadPoolMinThreads` | <span data-ttu-id="9b8e9-123">최소 스레드 개수를 나타내는 정수</span><span class="sxs-lookup"><span data-stu-id="9b8e9-123">An integer that represents the minimum number of threads</span></span> |
| <span data-ttu-id="9b8e9-124">**환경 변수**</span><span class="sxs-lookup"><span data-stu-id="9b8e9-124">**Environment variable**</span></span> | <span data-ttu-id="9b8e9-125">N/A</span><span class="sxs-lookup"><span data-stu-id="9b8e9-125">N/A</span></span> | <span data-ttu-id="9b8e9-126">N/A</span><span class="sxs-lookup"><span data-stu-id="9b8e9-126">N/A</span></span> |

### <a name="examples"></a><span data-ttu-id="9b8e9-127">예</span><span class="sxs-lookup"><span data-stu-id="9b8e9-127">Examples</span></span>

<span data-ttu-id="9b8e9-128">*runtimeconfig.json* 파일:</span><span class="sxs-lookup"><span data-stu-id="9b8e9-128">*runtimeconfig.json* file:</span></span>

```json
{
   "runtimeOptions": {
      "configProperties": {
         "System.Threading.ThreadPool.MinThreads": 4
      }
   }
}
```

<span data-ttu-id="9b8e9-129">프로젝트 파일:</span><span class="sxs-lookup"><span data-stu-id="9b8e9-129">Project file:</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">

  <PropertyGroup>
    <ThreadPoolMinThreads>4</ThreadPoolMinThreads>
  </PropertyGroup>

</Project>
```

## <a name="maximum-threads"></a><span data-ttu-id="9b8e9-130">최대 스레드</span><span class="sxs-lookup"><span data-stu-id="9b8e9-130">Maximum threads</span></span>

- <span data-ttu-id="9b8e9-131">작업자 스레드 풀의 최대 스레드 개수를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="9b8e9-131">Specifies the maximum number of threads for the worker threadpool.</span></span>
- <span data-ttu-id="9b8e9-132"><xref:System.Threading.ThreadPool.SetMaxThreads%2A?displayProperty=nameWithType> 메서드에 대응됩니다.</span><span class="sxs-lookup"><span data-stu-id="9b8e9-132">Corresponds to the <xref:System.Threading.ThreadPool.SetMaxThreads%2A?displayProperty=nameWithType> method.</span></span>

| | <span data-ttu-id="9b8e9-133">설정 이름</span><span class="sxs-lookup"><span data-stu-id="9b8e9-133">Setting name</span></span> | <span data-ttu-id="9b8e9-134">값</span><span class="sxs-lookup"><span data-stu-id="9b8e9-134">Values</span></span> |
| - | - | - |
| <span data-ttu-id="9b8e9-135">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="9b8e9-135">**runtimeconfig.json**</span></span> | `System.Threading.ThreadPool.MaxThreads` | <span data-ttu-id="9b8e9-136">최대 스레드 개수를 나타내는 정수</span><span class="sxs-lookup"><span data-stu-id="9b8e9-136">An integer that represents the maximum number of threads</span></span> |
| <span data-ttu-id="9b8e9-137">**MSBuild 속성**</span><span class="sxs-lookup"><span data-stu-id="9b8e9-137">**MSBuild property**</span></span> | `ThreadPoolMaxThreads` | <span data-ttu-id="9b8e9-138">최대 스레드 개수를 나타내는 정수</span><span class="sxs-lookup"><span data-stu-id="9b8e9-138">An integer that represents the maximum number of threads</span></span> |
| <span data-ttu-id="9b8e9-139">**환경 변수**</span><span class="sxs-lookup"><span data-stu-id="9b8e9-139">**Environment variable**</span></span> | <span data-ttu-id="9b8e9-140">N/A</span><span class="sxs-lookup"><span data-stu-id="9b8e9-140">N/A</span></span> | <span data-ttu-id="9b8e9-141">N/A</span><span class="sxs-lookup"><span data-stu-id="9b8e9-141">N/A</span></span> |

### <a name="examples"></a><span data-ttu-id="9b8e9-142">예</span><span class="sxs-lookup"><span data-stu-id="9b8e9-142">Examples</span></span>

<span data-ttu-id="9b8e9-143">*runtimeconfig.json* 파일:</span><span class="sxs-lookup"><span data-stu-id="9b8e9-143">*runtimeconfig.json* file:</span></span>

```json
{
   "runtimeOptions": {
      "configProperties": {
         "System.Threading.ThreadPool.MaxThreads": 20
      }
   }
}
```

<span data-ttu-id="9b8e9-144">프로젝트 파일:</span><span class="sxs-lookup"><span data-stu-id="9b8e9-144">Project file:</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">

  <PropertyGroup>
    <ThreadPoolMaxThreads>20</ThreadPoolMaxThreads>
  </PropertyGroup>

</Project>
```
