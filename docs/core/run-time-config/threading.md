---
title: 스레딩 구성 설정
description: .NET Core 앱의 스레딩을 구성하는 런타임 설정에 대해 알아봅니다.
ms.date: 11/27/2019
ms.topic: reference
ms.openlocfilehash: 68b8e93ca6ec3f708a7a627307655ada1955500a
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/14/2020
ms.locfileid: "76789857"
---
# <a name="run-time-configuration-options-for-threading"></a><span data-ttu-id="3825c-103">스레딩을 위한 런타임 구성 옵션</span><span class="sxs-lookup"><span data-stu-id="3825c-103">Run-time configuration options for threading</span></span>

## <a name="cpu-groups"></a><span data-ttu-id="3825c-104">CPU 그룹</span><span class="sxs-lookup"><span data-stu-id="3825c-104">CPU groups</span></span>

- <span data-ttu-id="3825c-105">스레드가 여러 CPU 그룹에 자동으로 분산되는지 여부를 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="3825c-105">Configures whether threads are automatically distributed across CPU groups.</span></span>
- <span data-ttu-id="3825c-106">기본값: 사용 안 함(`0`).</span><span class="sxs-lookup"><span data-stu-id="3825c-106">Default: Disabled (`0`).</span></span>

| | <span data-ttu-id="3825c-107">설정 이름</span><span class="sxs-lookup"><span data-stu-id="3825c-107">Setting name</span></span> | <span data-ttu-id="3825c-108">값</span><span class="sxs-lookup"><span data-stu-id="3825c-108">Values</span></span> |
| - | - | - |
| <span data-ttu-id="3825c-109">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="3825c-109">**runtimeconfig.json**</span></span> | <span data-ttu-id="3825c-110">N/A</span><span class="sxs-lookup"><span data-stu-id="3825c-110">N/A</span></span> | <span data-ttu-id="3825c-111">N/A</span><span class="sxs-lookup"><span data-stu-id="3825c-111">N/A</span></span> |
| <span data-ttu-id="3825c-112">**환경 변수**</span><span class="sxs-lookup"><span data-stu-id="3825c-112">**Environment variable**</span></span> | `COMPlus_Thread_UseAllCpuGroups` | <span data-ttu-id="3825c-113">`0` - 사용 안 함</span><span class="sxs-lookup"><span data-stu-id="3825c-113">`0` - disabled</span></span><br/><span data-ttu-id="3825c-114">`1` - 사용</span><span class="sxs-lookup"><span data-stu-id="3825c-114">`1` - enabled</span></span> |

## <a name="minimum-threads"></a><span data-ttu-id="3825c-115">최소 스레드</span><span class="sxs-lookup"><span data-stu-id="3825c-115">Minimum threads</span></span>

- <span data-ttu-id="3825c-116">작업자 스레드 풀의 최소 스레드 개수를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="3825c-116">Specifies the minimum number of threads for the worker thread pool.</span></span>
- <span data-ttu-id="3825c-117"><xref:System.Threading.ThreadPool.SetMinThreads%2A?displayProperty=nameWithType> 메서드에 대응됩니다.</span><span class="sxs-lookup"><span data-stu-id="3825c-117">Corresponds to the <xref:System.Threading.ThreadPool.SetMinThreads%2A?displayProperty=nameWithType> method.</span></span>

| | <span data-ttu-id="3825c-118">설정 이름</span><span class="sxs-lookup"><span data-stu-id="3825c-118">Setting name</span></span> | <span data-ttu-id="3825c-119">값</span><span class="sxs-lookup"><span data-stu-id="3825c-119">Values</span></span> |
| - | - | - |
| <span data-ttu-id="3825c-120">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="3825c-120">**runtimeconfig.json**</span></span> | `System.Threading.ThreadPool.MinThreads` | <span data-ttu-id="3825c-121">최소 스레드 개수를 나타내는 정수</span><span class="sxs-lookup"><span data-stu-id="3825c-121">An integer that represents the minimum number of threads</span></span> |
| <span data-ttu-id="3825c-122">**MSBuild 속성**</span><span class="sxs-lookup"><span data-stu-id="3825c-122">**MSBuild property**</span></span> | `ThreadPoolMinThreads` | <span data-ttu-id="3825c-123">최소 스레드 개수를 나타내는 정수</span><span class="sxs-lookup"><span data-stu-id="3825c-123">An integer that represents the minimum number of threads</span></span> |
| <span data-ttu-id="3825c-124">**환경 변수**</span><span class="sxs-lookup"><span data-stu-id="3825c-124">**Environment variable**</span></span> | <span data-ttu-id="3825c-125">N/A</span><span class="sxs-lookup"><span data-stu-id="3825c-125">N/A</span></span> | <span data-ttu-id="3825c-126">N/A</span><span class="sxs-lookup"><span data-stu-id="3825c-126">N/A</span></span> |

### <a name="examples"></a><span data-ttu-id="3825c-127">예</span><span class="sxs-lookup"><span data-stu-id="3825c-127">Examples</span></span>

<span data-ttu-id="3825c-128">*runtimeconfig.json* 파일:</span><span class="sxs-lookup"><span data-stu-id="3825c-128">*runtimeconfig.json* file:</span></span>

```json
{
   "runtimeOptions": {
      "configProperties": {
         "System.Threading.ThreadPool.MinThreads": 4
      }
   }
}
```

<span data-ttu-id="3825c-129">프로젝트 파일:</span><span class="sxs-lookup"><span data-stu-id="3825c-129">Project file:</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">

  <PropertyGroup>
    <ThreadPoolMinThreads>4</ThreadPoolMinThreads>
  </PropertyGroup>

</Project>
```

## <a name="maximum-threads"></a><span data-ttu-id="3825c-130">최대 스레드</span><span class="sxs-lookup"><span data-stu-id="3825c-130">Maximum threads</span></span>

- <span data-ttu-id="3825c-131">작업자 스레드 풀의 최대 스레드 개수를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="3825c-131">Specifies the maximum number of threads for the worker thread pool.</span></span>
- <span data-ttu-id="3825c-132"><xref:System.Threading.ThreadPool.SetMaxThreads%2A?displayProperty=nameWithType> 메서드에 대응됩니다.</span><span class="sxs-lookup"><span data-stu-id="3825c-132">Corresponds to the <xref:System.Threading.ThreadPool.SetMaxThreads%2A?displayProperty=nameWithType> method.</span></span>

| | <span data-ttu-id="3825c-133">설정 이름</span><span class="sxs-lookup"><span data-stu-id="3825c-133">Setting name</span></span> | <span data-ttu-id="3825c-134">값</span><span class="sxs-lookup"><span data-stu-id="3825c-134">Values</span></span> |
| - | - | - |
| <span data-ttu-id="3825c-135">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="3825c-135">**runtimeconfig.json**</span></span> | `System.Threading.ThreadPool.MaxThreads` | <span data-ttu-id="3825c-136">최대 스레드 개수를 나타내는 정수</span><span class="sxs-lookup"><span data-stu-id="3825c-136">An integer that represents the maximum number of threads</span></span> |
| <span data-ttu-id="3825c-137">**MSBuild 속성**</span><span class="sxs-lookup"><span data-stu-id="3825c-137">**MSBuild property**</span></span> | `ThreadPoolMaxThreads` | <span data-ttu-id="3825c-138">최대 스레드 개수를 나타내는 정수</span><span class="sxs-lookup"><span data-stu-id="3825c-138">An integer that represents the maximum number of threads</span></span> |
| <span data-ttu-id="3825c-139">**환경 변수**</span><span class="sxs-lookup"><span data-stu-id="3825c-139">**Environment variable**</span></span> | <span data-ttu-id="3825c-140">N/A</span><span class="sxs-lookup"><span data-stu-id="3825c-140">N/A</span></span> | <span data-ttu-id="3825c-141">N/A</span><span class="sxs-lookup"><span data-stu-id="3825c-141">N/A</span></span> |

### <a name="examples"></a><span data-ttu-id="3825c-142">예</span><span class="sxs-lookup"><span data-stu-id="3825c-142">Examples</span></span>

<span data-ttu-id="3825c-143">*runtimeconfig.json* 파일:</span><span class="sxs-lookup"><span data-stu-id="3825c-143">*runtimeconfig.json* file:</span></span>

```json
{
   "runtimeOptions": {
      "configProperties": {
         "System.Threading.ThreadPool.MaxThreads": 20
      }
   }
}
```

<span data-ttu-id="3825c-144">프로젝트 파일:</span><span class="sxs-lookup"><span data-stu-id="3825c-144">Project file:</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">

  <PropertyGroup>
    <ThreadPoolMaxThreads>20</ThreadPoolMaxThreads>
  </PropertyGroup>

</Project>
```
