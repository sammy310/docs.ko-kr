---
title: 스레딩 구성 설정
description: .NET Core 앱의 스레딩을 구성하는 런타임 설정에 대해 알아봅니다.
ms.date: 11/27/2019
ms.topic: reference
ms.openlocfilehash: 1c7c16993a07ef95223481791153b75ab2f61533
ms.sourcegitcommit: c76c8b2c39ed2f0eee422b61a2ab4c05ca7771fa
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/21/2020
ms.locfileid: "83761930"
---
# <a name="run-time-configuration-options-for-threading"></a><span data-ttu-id="b71f6-103">스레딩을 위한 런타임 구성 옵션</span><span class="sxs-lookup"><span data-stu-id="b71f6-103">Run-time configuration options for threading</span></span>

## <a name="cpu-groups"></a><span data-ttu-id="b71f6-104">CPU 그룹</span><span class="sxs-lookup"><span data-stu-id="b71f6-104">CPU groups</span></span>

- <span data-ttu-id="b71f6-105">스레드가 여러 CPU 그룹에 자동으로 분산되는지 여부를 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="b71f6-105">Configures whether threads are automatically distributed across CPU groups.</span></span>
- <span data-ttu-id="b71f6-106">이 설정을 생략하면 스레드가 CPU 그룹 간에 분산되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b71f6-106">If you omit this setting, threads are not distributed across CPU groups.</span></span> <span data-ttu-id="b71f6-107">이는 값을 `0`으로 설정하는 것과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="b71f6-107">This is equivalent to setting the value to `0`.</span></span>

| | <span data-ttu-id="b71f6-108">설정 이름</span><span class="sxs-lookup"><span data-stu-id="b71f6-108">Setting name</span></span> | <span data-ttu-id="b71f6-109">값</span><span class="sxs-lookup"><span data-stu-id="b71f6-109">Values</span></span> |
| - | - | - |
| <span data-ttu-id="b71f6-110">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="b71f6-110">**runtimeconfig.json**</span></span> | <span data-ttu-id="b71f6-111">N/A</span><span class="sxs-lookup"><span data-stu-id="b71f6-111">N/A</span></span> | <span data-ttu-id="b71f6-112">N/A</span><span class="sxs-lookup"><span data-stu-id="b71f6-112">N/A</span></span> |
| <span data-ttu-id="b71f6-113">**환경 변수**</span><span class="sxs-lookup"><span data-stu-id="b71f6-113">**Environment variable**</span></span> | `COMPlus_Thread_UseAllCpuGroups` | <span data-ttu-id="b71f6-114">`0` - 사용 안 함</span><span class="sxs-lookup"><span data-stu-id="b71f6-114">`0` - disabled</span></span><br/><span data-ttu-id="b71f6-115">`1` - 사용</span><span class="sxs-lookup"><span data-stu-id="b71f6-115">`1` - enabled</span></span> |

## <a name="minimum-threads"></a><span data-ttu-id="b71f6-116">최소 스레드</span><span class="sxs-lookup"><span data-stu-id="b71f6-116">Minimum threads</span></span>

- <span data-ttu-id="b71f6-117">작업자 스레드 풀의 최소 스레드 개수를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="b71f6-117">Specifies the minimum number of threads for the worker thread pool.</span></span>
- <span data-ttu-id="b71f6-118"><xref:System.Threading.ThreadPool.SetMinThreads%2A?displayProperty=nameWithType> 메서드에 대응됩니다.</span><span class="sxs-lookup"><span data-stu-id="b71f6-118">Corresponds to the <xref:System.Threading.ThreadPool.SetMinThreads%2A?displayProperty=nameWithType> method.</span></span>

| | <span data-ttu-id="b71f6-119">설정 이름</span><span class="sxs-lookup"><span data-stu-id="b71f6-119">Setting name</span></span> | <span data-ttu-id="b71f6-120">값</span><span class="sxs-lookup"><span data-stu-id="b71f6-120">Values</span></span> |
| - | - | - |
| <span data-ttu-id="b71f6-121">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="b71f6-121">**runtimeconfig.json**</span></span> | `System.Threading.ThreadPool.MinThreads` | <span data-ttu-id="b71f6-122">최소 스레드 개수를 나타내는 정수</span><span class="sxs-lookup"><span data-stu-id="b71f6-122">An integer that represents the minimum number of threads</span></span> |
| <span data-ttu-id="b71f6-123">**MSBuild 속성**</span><span class="sxs-lookup"><span data-stu-id="b71f6-123">**MSBuild property**</span></span> | `ThreadPoolMinThreads` | <span data-ttu-id="b71f6-124">최소 스레드 개수를 나타내는 정수</span><span class="sxs-lookup"><span data-stu-id="b71f6-124">An integer that represents the minimum number of threads</span></span> |
| <span data-ttu-id="b71f6-125">**환경 변수**</span><span class="sxs-lookup"><span data-stu-id="b71f6-125">**Environment variable**</span></span> | <span data-ttu-id="b71f6-126">N/A</span><span class="sxs-lookup"><span data-stu-id="b71f6-126">N/A</span></span> | <span data-ttu-id="b71f6-127">N/A</span><span class="sxs-lookup"><span data-stu-id="b71f6-127">N/A</span></span> |

### <a name="examples"></a><span data-ttu-id="b71f6-128">예</span><span class="sxs-lookup"><span data-stu-id="b71f6-128">Examples</span></span>

<span data-ttu-id="b71f6-129">*runtimeconfig.json* 파일:</span><span class="sxs-lookup"><span data-stu-id="b71f6-129">*runtimeconfig.json* file:</span></span>

```json
{
   "runtimeOptions": {
      "configProperties": {
         "System.Threading.ThreadPool.MinThreads": 4
      }
   }
}
```

<span data-ttu-id="b71f6-130">프로젝트 파일:</span><span class="sxs-lookup"><span data-stu-id="b71f6-130">Project file:</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">

  <PropertyGroup>
    <ThreadPoolMinThreads>4</ThreadPoolMinThreads>
  </PropertyGroup>

</Project>
```

## <a name="maximum-threads"></a><span data-ttu-id="b71f6-131">최대 스레드</span><span class="sxs-lookup"><span data-stu-id="b71f6-131">Maximum threads</span></span>

- <span data-ttu-id="b71f6-132">작업자 스레드 풀의 최대 스레드 개수를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="b71f6-132">Specifies the maximum number of threads for the worker thread pool.</span></span>
- <span data-ttu-id="b71f6-133"><xref:System.Threading.ThreadPool.SetMaxThreads%2A?displayProperty=nameWithType> 메서드에 대응됩니다.</span><span class="sxs-lookup"><span data-stu-id="b71f6-133">Corresponds to the <xref:System.Threading.ThreadPool.SetMaxThreads%2A?displayProperty=nameWithType> method.</span></span>

| | <span data-ttu-id="b71f6-134">설정 이름</span><span class="sxs-lookup"><span data-stu-id="b71f6-134">Setting name</span></span> | <span data-ttu-id="b71f6-135">값</span><span class="sxs-lookup"><span data-stu-id="b71f6-135">Values</span></span> |
| - | - | - |
| <span data-ttu-id="b71f6-136">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="b71f6-136">**runtimeconfig.json**</span></span> | `System.Threading.ThreadPool.MaxThreads` | <span data-ttu-id="b71f6-137">최대 스레드 개수를 나타내는 정수</span><span class="sxs-lookup"><span data-stu-id="b71f6-137">An integer that represents the maximum number of threads</span></span> |
| <span data-ttu-id="b71f6-138">**MSBuild 속성**</span><span class="sxs-lookup"><span data-stu-id="b71f6-138">**MSBuild property**</span></span> | `ThreadPoolMaxThreads` | <span data-ttu-id="b71f6-139">최대 스레드 개수를 나타내는 정수</span><span class="sxs-lookup"><span data-stu-id="b71f6-139">An integer that represents the maximum number of threads</span></span> |
| <span data-ttu-id="b71f6-140">**환경 변수**</span><span class="sxs-lookup"><span data-stu-id="b71f6-140">**Environment variable**</span></span> | <span data-ttu-id="b71f6-141">N/A</span><span class="sxs-lookup"><span data-stu-id="b71f6-141">N/A</span></span> | <span data-ttu-id="b71f6-142">N/A</span><span class="sxs-lookup"><span data-stu-id="b71f6-142">N/A</span></span> |

### <a name="examples"></a><span data-ttu-id="b71f6-143">예</span><span class="sxs-lookup"><span data-stu-id="b71f6-143">Examples</span></span>

<span data-ttu-id="b71f6-144">*runtimeconfig.json* 파일:</span><span class="sxs-lookup"><span data-stu-id="b71f6-144">*runtimeconfig.json* file:</span></span>

```json
{
   "runtimeOptions": {
      "configProperties": {
         "System.Threading.ThreadPool.MaxThreads": 20
      }
   }
}
```

<span data-ttu-id="b71f6-145">프로젝트 파일:</span><span class="sxs-lookup"><span data-stu-id="b71f6-145">Project file:</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">

  <PropertyGroup>
    <ThreadPoolMaxThreads>20</ThreadPoolMaxThreads>
  </PropertyGroup>

</Project>
```
