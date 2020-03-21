---
title: <applicationPool> 요소(웹 설정)
ms.date: 03/30/2017
helpviewer_keywords:
- applicationPool element
- <applicationPool> element
ms.assetid: 46d1baaa-e343-4639-b70d-2a43a9f62b2a
ms.openlocfilehash: 6feaa801610fa0ffbbf47575f25aff29fa46a66c
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79152856"
---
# <a name="applicationpool-element-web-settings"></a><span data-ttu-id="e8eea-102">\<applicationPool> 요소(웹 설정)</span><span class="sxs-lookup"><span data-stu-id="e8eea-102">\<applicationPool> Element (Web Settings)</span></span>
<span data-ttu-id="e8eea-103">ASP.NET 응용 프로그램이 IIS 7.0 또는 이후 버전의 통합 모드에서 실행중인 경우 ASP.NET 프로세스 전체 동작을 관리하는 데 사용되는 구성 설정을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="e8eea-103">Specifies configuration settings that are used by ASP.NET to manage process-wide behavior when an ASP.NET application is running in Integrated mode on IIS 7.0 or a later version.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="e8eea-104">이 요소와 지원되는 기능은 ASP.NET 응용 프로그램이 IIS 7.0 이상 버전에서 호스팅되는 경우에만 작동합니다.</span><span class="sxs-lookup"><span data-stu-id="e8eea-104">This element and the feature it supports only work if your ASP.NET application is hosted on IIS 7.0 or later versions.</span></span>  
  
[<span data-ttu-id="e8eea-105">**\<구성>**</span><span class="sxs-lookup"><span data-stu-id="e8eea-105">**\<configuration>**</span></span>](../configuration-element.md)  
<span data-ttu-id="e8eea-106">&nbsp;&nbsp;[**\<system.web>**](system-web-element-web-settings.md)</span><span class="sxs-lookup"><span data-stu-id="e8eea-106">&nbsp;&nbsp;[**\<system.web>**](system-web-element-web-settings.md)</span></span>  
<span data-ttu-id="e8eea-107">&nbsp;&nbsp;&nbsp;&nbsp;**\<애플리케이션풀>**</span><span class="sxs-lookup"><span data-stu-id="e8eea-107">&nbsp;&nbsp;&nbsp;&nbsp;**\<applicationPool>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e8eea-108">구문</span><span class="sxs-lookup"><span data-stu-id="e8eea-108">Syntax</span></span>  
  
```xml  
<applicationPool
    maxConcurrentRequestsPerCPU="5000"
    maxConcurrentThreadsPerCPU="0"
    requestQueueLimit="5000" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e8eea-109">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="e8eea-109">Attributes and Elements</span></span>  

<span data-ttu-id="e8eea-110">다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="e8eea-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e8eea-111">특성</span><span class="sxs-lookup"><span data-stu-id="e8eea-111">Attributes</span></span>  
  
|<span data-ttu-id="e8eea-112">attribute</span><span class="sxs-lookup"><span data-stu-id="e8eea-112">Attribute</span></span>|<span data-ttu-id="e8eea-113">Description</span><span class="sxs-lookup"><span data-stu-id="e8eea-113">Description</span></span>|  
|---------------|-----------------|  
|`maxConcurrentRequestsPerCPU`|<span data-ttu-id="e8eea-114">CPU당 허용할 ASP.NET 동시 요청 수를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="e8eea-114">Specifies how many simultaneous requests ASP.NET allows per CPU.</span></span>|  
|`maxConcurrentThreadsPerCPU`|<span data-ttu-id="e8eea-115">각 CPU에 대한 응용 프로그램 풀에 대해 실행할 수 있는 동시 스레드 수를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="e8eea-115">Specifies how many simultaneous threads can be running for an application pool for each CPU.</span></span> <span data-ttu-id="e8eea-116">이렇게 하면 CPU당 요청을 제공하는 데 사용할 수 있는 관리되는 스레드 수를 제한할 수 있으므로 ASP.NET 동시성을 제어하는 다른 방법이 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="e8eea-116">This provides an alternative way to control ASP.NET concurrency, because you can limit the number of managed threads that can be used per CPU to serve requests.</span></span> <span data-ttu-id="e8eea-117">기본적으로 이 설정은 0이므로 clR 스레드 풀은 만들 수 있는 스레드 수도 제한되지만 ASP.NET CPU당 만들 수 있는 스레드 수를 제한하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e8eea-117">By default this setting is 0, which means that ASP.NET does not limit the number of threads that can be created per CPU, although the CLR thread pool also limits the number of threads that can be created.</span></span>|  
|`requestQueueLimit`|<span data-ttu-id="e8eea-118">단일 프로세스에서 ASP.NET 동안 큐에 대기할 수 있는 최대 요청 수를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="e8eea-118">Specifies the maximum number of requests that can be queued for ASP.NET in a single process.</span></span> <span data-ttu-id="e8eea-119">둘 이상의 ASP.NET 응용 프로그램이 단일 응용 프로그램 풀에서 실행되는 경우 응용 프로그램 풀의 모든 응용 프로그램에 대해 발생하는 누적 요청 집합이 이 설정의 적용을 받습니다.</span><span class="sxs-lookup"><span data-stu-id="e8eea-119">When two or more ASP.NET applications run in a single application pool, the cumulative set of requests being made to any application in the application pool is subject to this setting.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="e8eea-120">자식 요소</span><span class="sxs-lookup"><span data-stu-id="e8eea-120">Child Elements</span></span>  
 <span data-ttu-id="e8eea-121">없음</span><span class="sxs-lookup"><span data-stu-id="e8eea-121">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="e8eea-122">부모 요소</span><span class="sxs-lookup"><span data-stu-id="e8eea-122">Parent Elements</span></span>  
  
|<span data-ttu-id="e8eea-123">요소</span><span class="sxs-lookup"><span data-stu-id="e8eea-123">Element</span></span>|<span data-ttu-id="e8eea-124">Description</span><span class="sxs-lookup"><span data-stu-id="e8eea-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="e8eea-125">\<system.web></span><span class="sxs-lookup"><span data-stu-id="e8eea-125">\<system.web></span></span>](system-web-element-web-settings.md)|<span data-ttu-id="e8eea-126">ASP.NET 호스트 응용 프로그램과 상호 작용하는 방법에 대한 정보를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="e8eea-126">Contains information about how ASP.NET interacts with a host application.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e8eea-127">설명</span><span class="sxs-lookup"><span data-stu-id="e8eea-127">Remarks</span></span>  

<span data-ttu-id="e8eea-128">통합 모드에서 IIS 7.0 또는 이후 버전을 실행하는 경우 이 요소 조합을 사용하면 응용 프로그램이 IIS 응용 프로그램 풀에서 호스팅될 때 ASP.NET 스레드 및 큐 요청을 관리하는 방법을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e8eea-128">When you run IIS 7.0 or a later version in Integrated mode, this element combination lets you configure how ASP.NET manages threads and queues requests when the application is hosted in an IIS application pool.</span></span> <span data-ttu-id="e8eea-129">IIS 6을 실행하거나 클래식 모드 또는 ISAPI 모드에서 IIS 7.0을 실행하면 이러한 설정이 무시됩니다.</span><span class="sxs-lookup"><span data-stu-id="e8eea-129">If you run IIS 6 or you run IIS 7.0 in Classic mode or in ISAPI mode, these settings are ignored.</span></span>  
  
<span data-ttu-id="e8eea-130">이 `applicationPool` 설정은 .NET Framework의 특정 버전에서 실행되는 모든 응용 프로그램 풀에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="e8eea-130">The `applicationPool` settings apply to all application pools that run on a particular version of the .NET Framework.</span></span> <span data-ttu-id="e8eea-131">설정은 aspnet.config 파일에 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e8eea-131">The settings are contained in an aspnet.config file.</span></span> <span data-ttu-id="e8eea-132">.NET Framework의 버전 2.0 및 4.0에 대해 이 파일버전이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e8eea-132">There is a version of this file for versions 2.0 and 4.0 of the .NET Framework.</span></span> <span data-ttu-id="e8eea-133">(.NET 프레임워크의 버전 3.0 및 3.5는 버전 2.0과 aspnet.config 파일을 공유합니다.)</span><span class="sxs-lookup"><span data-stu-id="e8eea-133">(Versions 3.0 and 3.5 of the .NET Framework share the aspnet.config file with version 2.0.)</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="e8eea-134">Windows 7에서 IIS 7.0을 실행하는 경우 모든 응용 프로그램 풀에 대해 별도의 aspnet.config 파일을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e8eea-134">If you run IIS 7.0 on Windows 7, you can configure a separate aspnet.config file for every application pool.</span></span> <span data-ttu-id="e8eea-135">이렇게 하면 각 응용 프로그램 풀에 대한 스레드의 성능을 조정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e8eea-135">This lets you tailor the performance of the threads for each application pool.</span></span>  
  
<span data-ttu-id="e8eea-136">설정의 `maxConcurrentRequestsPerCPU` 경우 .NET Framework 4의 기본 설정인 "5000"은 실제로 CPU당 5,000개 이상의 요청이 있는 경우가 아니면 ASP.NET 의해 제어되는 요청 제한을 효과적으로 해제합니다.</span><span class="sxs-lookup"><span data-stu-id="e8eea-136">For the `maxConcurrentRequestsPerCPU` setting, the default setting of "5000" in the .NET Framework 4 effectively turns off request throttling that is controlled by ASP.NET, unless you actually have 5000 or more requests per CPU.</span></span> <span data-ttu-id="e8eea-137">기본 설정은 CPU당 동시성을 자동으로 관리하기 위해 CLR 스레드 풀에 따라 달라집니다.</span><span class="sxs-lookup"><span data-stu-id="e8eea-137">The default setting depends instead on the CLR thread-pool to automatically manage concurrency per CPU.</span></span> <span data-ttu-id="e8eea-138">비동기 요청 처리를 광범위하게 사용하거나 네트워크 I/O에서 장기 실행 요청이 많이 차단된 응용 프로그램은 .NET Framework 4에서 증가된 기본 제한의 이점을 누릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e8eea-138">Applications that make extensive use of asynchronous request processing, or that have many long-running requests blocked on network I/O, will benefit from the increased default limit in the .NET Framework 4.</span></span> <span data-ttu-id="e8eea-139">0으로 설정하면 `maxConcurrentRequestsPerCPU` ASP.NET 요청을 처리하기 위해 관리되는 스레드의 사용이 해제됩니다.</span><span class="sxs-lookup"><span data-stu-id="e8eea-139">Setting `maxConcurrentRequestsPerCPU` to zero turns off the use of managed threads for processing ASP.NET requests.</span></span> <span data-ttu-id="e8eea-140">응용 프로그램이 IIS 응용 프로그램 풀에서 실행되면 요청이 IIS I/O 스레드에 유지되므로 IIS 스레드 설정에 의해 동시화가 제한됩니다.</span><span class="sxs-lookup"><span data-stu-id="e8eea-140">When an application runs in an IIS application pool, requests stay on the IIS I/O thread and therefore concurrency is throttled by IIS thread settings.</span></span>  
  
<span data-ttu-id="e8eea-141">`requestQueueLimit`설정은 ASP.NET 응용 프로그램의 web.config 파일에 설정된 [processModel](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/7w2sway1(v=vs.100)) 요소의 `requestQueueLimit`특성과 동일한 방식으로 작동합니다.</span><span class="sxs-lookup"><span data-stu-id="e8eea-141">The `requestQueueLimit` setting works the same way as the `requestQueueLimit` attribute of the [processModel](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/7w2sway1(v=vs.100)) element, which is set in the Web.config files for ASP.NET applications.</span></span> <span data-ttu-id="e8eea-142">그러나 aspnet.config 파일의 `requestQueueLimit` 설정은 `requestQueueLimit` Web.config 파일의 설정을 재정의합니다.</span><span class="sxs-lookup"><span data-stu-id="e8eea-142">However, the `requestQueueLimit` setting in an aspnet.config file overrides the `requestQueueLimit` setting in a Web.config file.</span></span> <span data-ttu-id="e8eea-143">즉, 두 특성이 모두 설정된 경우(기본적으로 true) `requestQueueLimit` aspnet.config 파일의 설정이 우선합니다.</span><span class="sxs-lookup"><span data-stu-id="e8eea-143">In other words, if both attributes are set (by default, this is true), the `requestQueueLimit` setting in the aspnet.config file takes precedence.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e8eea-144">예제</span><span class="sxs-lookup"><span data-stu-id="e8eea-144">Example</span></span>  

<span data-ttu-id="e8eea-145">다음 예제에서는 다음과 같은 상황에서 aspnet.config 파일에서 프로세스 전체의 동작을 구성하는 ASP.NET 방법을 보여 주며 다음과 같은 경우를 보여 주며 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e8eea-145">The following example shows how to configure ASP.NET process-wide behavior in the aspnet.config file in the following circumstances:</span></span>  
  
- <span data-ttu-id="e8eea-146">응용 프로그램은 IIS 7.0 응용 프로그램 풀에서 호스팅됩니다.</span><span class="sxs-lookup"><span data-stu-id="e8eea-146">The application is hosted in an IIS 7.0 application pool.</span></span>  
  
- <span data-ttu-id="e8eea-147">IIS 7.0이 통합 모드에서 실행되고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e8eea-147">IIS 7.0 is running in Integrated mode.</span></span>  
  
- <span data-ttu-id="e8eea-148">응용 프로그램이 .NET Framework 3.5 SP1 또는 이후 버전을 사용하고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e8eea-148">The application is using the .NET Framework 3.5 SP1 or a later version.</span></span>  
  
<span data-ttu-id="e8eea-149">예제의 값은 기본값입니다.</span><span class="sxs-lookup"><span data-stu-id="e8eea-149">The values in the example are the default values.</span></span>  
  
```xml  
<configuration>  
  <system.web>  
    <applicationPool
        maxConcurrentRequestsPerCPU="5000"  
        maxConcurrentThreadsPerCPU="0"
        requestQueueLimit="5000" />  
  </system.web>  
</configuration>  
```  
  
## <a name="element-information"></a><span data-ttu-id="e8eea-150">요소 정보</span><span class="sxs-lookup"><span data-stu-id="e8eea-150">Element Information</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="e8eea-151">네임스페이스</span><span class="sxs-lookup"><span data-stu-id="e8eea-151">Namespace</span></span>||  
|<span data-ttu-id="e8eea-152">Schema Name</span><span class="sxs-lookup"><span data-stu-id="e8eea-152">Schema Name</span></span>||  
|<span data-ttu-id="e8eea-153">유효성 검사 파일</span><span class="sxs-lookup"><span data-stu-id="e8eea-153">Validation File</span></span>||  
|<span data-ttu-id="e8eea-154">비어 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e8eea-154">Can be Empty</span></span>||  
  
## <a name="see-also"></a><span data-ttu-id="e8eea-155">참고 항목</span><span class="sxs-lookup"><span data-stu-id="e8eea-155">See also</span></span>

- [<span data-ttu-id="e8eea-156">\<system.web> 요소(웹 설정)</span><span class="sxs-lookup"><span data-stu-id="e8eea-156">\<system.web> Element (Web Settings)</span></span>](system-web-element-web-settings.md)
