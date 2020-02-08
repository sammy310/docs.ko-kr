---
title: 스레딩 구성 설정
description: .NET Core 앱의 스레딩을 구성하는 런타임 설정에 대해 알아봅니다.
ms.date: 11/27/2019
ms.topic: reference
ms.openlocfilehash: 68b8e93ca6ec3f708a7a627307655ada1955500a
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/28/2020
ms.locfileid: "76789857"
---
# <a name="run-time-configuration-options-for-threading"></a><span data-ttu-id="f54f0-103">스레딩을 위한 런타임 구성 옵션</span><span class="sxs-lookup"><span data-stu-id="f54f0-103">Run-time configuration options for threading</span></span>

## <a name="cpu-groups"></a><span data-ttu-id="f54f0-104">CPU 그룹</span><span class="sxs-lookup"><span data-stu-id="f54f0-104">CPU groups</span></span>

- <span data-ttu-id="f54f0-105">스레드가 여러 CPU 그룹에 자동으로 분산되는지 여부를 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="f54f0-105">Configures whether threads are automatically distributed across CPU groups.</span></span>
- <span data-ttu-id="f54f0-106">기본값: 사용 안 함(`0`).</span><span class="sxs-lookup"><span data-stu-id="f54f0-106">Default: Disabled (`0`).</span></span>

| | <span data-ttu-id="f54f0-107">설정 이름</span><span class="sxs-lookup"><span data-stu-id="f54f0-107">Setting name</span></span> | <span data-ttu-id="f54f0-108">값</span><span class="sxs-lookup"><span data-stu-id="f54f0-108">Values</span></span> |
| - | - | - |
| <span data-ttu-id="f54f0-109">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="f54f0-109">**runtimeconfig.json**</span></span> | <span data-ttu-id="f54f0-110">N/A</span><span class="sxs-lookup"><span data-stu-id="f54f0-110">N/A</span></span> | <span data-ttu-id="f54f0-111">N/A</span><span class="sxs-lookup"><span data-stu-id="f54f0-111">N/A</span></span> |
| <span data-ttu-id="f54f0-112">**환경 변수**</span><span class="sxs-lookup"><span data-stu-id="f54f0-112">**Environment variable**</span></span> | `COMPlus_Thread_UseAllCpuGroups` | <span data-ttu-id="f54f0-113">`0` - 사용 안 함</span><span class="sxs-lookup"><span data-stu-id="f54f0-113">`0` - disabled</span></span><br/><span data-ttu-id="f54f0-114">`1` - 사용</span><span class="sxs-lookup"><span data-stu-id="f54f0-114">`1` - enabled</span></span> |

## <a name="minimum-threads"></a><span data-ttu-id="f54f0-115">최소 스레드</span><span class="sxs-lookup"><span data-stu-id="f54f0-115">Minimum threads</span></span>

- <span data-ttu-id="f54f0-116">작업자 스레드 풀의 최소 스레드 개수를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="f54f0-116">Specifies the minimum number of threads for the worker thread pool.</span></span>
- <span data-ttu-id="f54f0-117"><xref:System.Threading.ThreadPool.SetMinThreads%2A?displayProperty=nameWithType> 메서드에 대응됩니다.</span><span class="sxs-lookup"><span data-stu-id="f54f0-117">Corresponds to the <xref:System.Threading.ThreadPool.SetMinThreads%2A?displayProperty=nameWithType> method.</span></span>

| | <span data-ttu-id="f54f0-118">설정 이름</span><span class="sxs-lookup"><span data-stu-id="f54f0-118">Setting name</span></span> | <span data-ttu-id="f54f0-119">값</span><span class="sxs-lookup"><span data-stu-id="f54f0-119">Values</span></span> |
| - | - | - |
| <span data-ttu-id="f54f0-120">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="f54f0-120">**runtimeconfig.json**</span></span> | `System.Threading.ThreadPool.MinThreads` | <span data-ttu-id="f54f0-121">최소 스레드 개수를 나타내는 정수</span><span class="sxs-lookup"><span data-stu-id="f54f0-121">An integer that represents the minimum number of threads</span></span> |
| <span data-ttu-id="f54f0-122">**MSBuild 속성**</span><span class="sxs-lookup"><span data-stu-id="f54f0-122">**MSBuild property**</span></span> | `ThreadPoolMinThreads` | <span data-ttu-id="f54f0-123">최소 스레드 개수를 나타내는 정수</span><span class="sxs-lookup"><span data-stu-id="f54f0-123">An integer that represents the minimum number of threads</span></span> |
| <span data-ttu-id="f54f0-124">**환경 변수**</span><span class="sxs-lookup"><span data-stu-id="f54f0-124">**Environment variable**</span></span> | <span data-ttu-id="f54f0-125">N/A</span><span class="sxs-lookup"><span data-stu-id="f54f0-125">N/A</span></span> | <span data-ttu-id="f54f0-126">N/A</span><span class="sxs-lookup"><span data-stu-id="f54f0-126">N/A</span></span> |

### <a name="examples"></a><span data-ttu-id="f54f0-127">예</span><span class="sxs-lookup"><span data-stu-id="f54f0-127">Examples</span></span>

<span data-ttu-id="f54f0-128">*runtimeconfig.json* 파일:</span><span class="sxs-lookup"><span data-stu-id="f54f0-128">*runtimeconfig.json* file:</span></span>

```json
{
   "runtimeOptions": {
      "configProperties": {
         "System.Threading.ThreadPool.MinThreads": 4
      }
   }
}
```

<span data-ttu-id="f54f0-129">프로젝트 파일:</span><span class="sxs-lookup"><span data-stu-id="f54f0-129">Project file:</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">

  <PropertyGroup>
    <ThreadPoolMinThreads>4</ThreadPoolMinThreads>
  </PropertyGroup>

</Project>
```

## <a name="maximum-threads"></a><span data-ttu-id="f54f0-130">최대 스레드</span><span class="sxs-lookup"><span data-stu-id="f54f0-130">Maximum threads</span></span>

- <span data-ttu-id="f54f0-131">작업자 스레드 풀의 최대 스레드 개수를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="f54f0-131">Specifies the maximum number of threads for the worker thread pool.</span></span>
- <span data-ttu-id="f54f0-132"><xref:System.Threading.ThreadPool.SetMaxThreads%2A?displayProperty=nameWithType> 메서드에 대응됩니다.</span><span class="sxs-lookup"><span data-stu-id="f54f0-132">Corresponds to the <xref:System.Threading.ThreadPool.SetMaxThreads%2A?displayProperty=nameWithType> method.</span></span>

| | <span data-ttu-id="f54f0-133">설정 이름</span><span class="sxs-lookup"><span data-stu-id="f54f0-133">Setting name</span></span> | <span data-ttu-id="f54f0-134">값</span><span class="sxs-lookup"><span data-stu-id="f54f0-134">Values</span></span> |
| - | - | - |
| <span data-ttu-id="f54f0-135">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="f54f0-135">**runtimeconfig.json**</span></span> | `System.Threading.ThreadPool.MaxThreads` | <span data-ttu-id="f54f0-136">최대 스레드 개수를 나타내는 정수</span><span class="sxs-lookup"><span data-stu-id="f54f0-136">An integer that represents the maximum number of threads</span></span> |
| <span data-ttu-id="f54f0-137">**MSBuild 속성**</span><span class="sxs-lookup"><span data-stu-id="f54f0-137">**MSBuild property**</span></span> | `ThreadPoolMaxThreads` | <span data-ttu-id="f54f0-138">최대 스레드 개수를 나타내는 정수</span><span class="sxs-lookup"><span data-stu-id="f54f0-138">An integer that represents the maximum number of threads</span></span> |
| <span data-ttu-id="f54f0-139">**환경 변수**</span><span class="sxs-lookup"><span data-stu-id="f54f0-139">**Environment variable**</span></span> | <span data-ttu-id="f54f0-140">N/A</span><span class="sxs-lookup"><span data-stu-id="f54f0-140">N/A</span></span> | <span data-ttu-id="f54f0-141">N/A</span><span class="sxs-lookup"><span data-stu-id="f54f0-141">N/A</span></span> |

### <a name="examples"></a><span data-ttu-id="f54f0-142">예</span><span class="sxs-lookup"><span data-stu-id="f54f0-142">Examples</span></span>

<span data-ttu-id="f54f0-143">*runtimeconfig.json* 파일:</span><span class="sxs-lookup"><span data-stu-id="f54f0-143">*runtimeconfig.json* file:</span></span>

```json
{
   "runtimeOptions": {
      "configProperties": {
         "System.Threading.ThreadPool.MaxThreads": 20
      }
   }
}
```

<span data-ttu-id="f54f0-144">프로젝트 파일:</span><span class="sxs-lookup"><span data-stu-id="f54f0-144">Project file:</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">

  <PropertyGroup>
    <ThreadPoolMaxThreads>20</ThreadPoolMaxThreads>
  </PropertyGroup>

</Project>
```
