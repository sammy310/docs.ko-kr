---
title: <applicationPool> 요소(웹 설정)
ms.date: 03/30/2017
helpviewer_keywords:
- applicationPool element
- <applicationPool> element
ms.assetid: 46d1baaa-e343-4639-b70d-2a43a9f62b2a
ms.openlocfilehash: 16207c3f3c711d06b71cafb2b67c5d29f3f14e39
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61698579"
---
# <a name="applicationpool-element-web-settings"></a><span data-ttu-id="d5702-102">\<응용 프로그램 풀 > 요소 (웹 설정)</span><span class="sxs-lookup"><span data-stu-id="d5702-102">\<applicationPool> Element (Web Settings)</span></span>
<span data-ttu-id="d5702-103">ASP.NET에서 ASP.NET 응용 프로그램 통합된 모드에서 실행 중인 경우 프로세스 전반 동작을 관리 하는 데 사용 되는 구성 설정을 지정 [!INCLUDE[iisver](../../../../../includes/iisver-md.md)] 이상 버전.</span><span class="sxs-lookup"><span data-stu-id="d5702-103">Specifies configuration settings that are used by ASP.NET to manage process-wide behavior when an ASP.NET application is running in Integrated mode on [!INCLUDE[iisver](../../../../../includes/iisver-md.md)] or a later version.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="d5702-104">ASP.NET 응용 프로그램에서 호스팅되는 경우 유일한 작업 지원이 요소 및 기능 [!INCLUDE[iisver](../../../../../includes/iisver-md.md)] 이상 버전.</span><span class="sxs-lookup"><span data-stu-id="d5702-104">This element and the feature it supports only work if your ASP.NET application is hosted on [!INCLUDE[iisver](../../../../../includes/iisver-md.md)] or later versions.</span></span>  
  
 <span data-ttu-id="d5702-105">\<configuration></span><span class="sxs-lookup"><span data-stu-id="d5702-105">\<configuration></span></span>  
<span data-ttu-id="d5702-106">\<system.web > 요소 (웹 설정)</span><span class="sxs-lookup"><span data-stu-id="d5702-106">\<system.web> Element (Web Settings)</span></span>  
<span data-ttu-id="d5702-107">\<응용 프로그램 풀 > 요소 (웹 설정)</span><span class="sxs-lookup"><span data-stu-id="d5702-107">\<applicationPool> Element (Web Settings)</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d5702-108">구문</span><span class="sxs-lookup"><span data-stu-id="d5702-108">Syntax</span></span>  
  
```xml  
<applicationPool   
    maxConcurrentRequestsPerCPU="5000"   
    maxConcurrentThreadsPerCPU="0"   
    requestQueueLimit="5000" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="d5702-109">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="d5702-109">Attributes and Elements</span></span>  
 <span data-ttu-id="d5702-110">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="d5702-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="d5702-111">특성</span><span class="sxs-lookup"><span data-stu-id="d5702-111">Attributes</span></span>  
  
|<span data-ttu-id="d5702-112">특성</span><span class="sxs-lookup"><span data-stu-id="d5702-112">Attribute</span></span>|<span data-ttu-id="d5702-113">설명</span><span class="sxs-lookup"><span data-stu-id="d5702-113">Description</span></span>|  
|---------------|-----------------|  
|`maxConcurrentRequestsPerCPU`|<span data-ttu-id="d5702-114">ASP.NET에서는 CPU 당 동시 요청 수를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="d5702-114">Specifies how many simultaneous requests ASP.NET allows per CPU.</span></span>|  
|`maxConcurrentThreadsPerCPU`|<span data-ttu-id="d5702-115">각 CPU에 대 한 응용 프로그램 풀에 대 한 동시 스레드를 실행할 수 있습니다를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="d5702-115">Specifies how many simultaneous threads can be running for an application pool for each CPU.</span></span> <span data-ttu-id="d5702-116">CPU 당 요청을 처리 하는 데 사용할 수 있는 관리 되는 스레드 수를 제한할 수 있기 때문에 ASP.NET 동시성을 제어 하는 대체 방법을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="d5702-116">This provides an alternative way to control ASP.NET concurrency, because you can limit the number of managed threads that can be used per CPU to serve requests.</span></span> <span data-ttu-id="d5702-117">기본적으로이 설정은 0 이며 ASP.NET CLR 스레드 풀도 만들 수 있는 스레드 수를 제한 하지만 CPU 당 만들 수 있는 스레드 수가 제한 되지 않습니다입니다.</span><span class="sxs-lookup"><span data-stu-id="d5702-117">By default this setting is 0, which means that ASP.NET does not limit the number of threads that can be created per CPU, although the CLR thread pool also limits the number of threads that can be created.</span></span>|  
|`requestQueueLimit`|<span data-ttu-id="d5702-118">단일 프로세스에서 ASP.NET에 대해 대기할 수 있는 요청의 최대 수를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="d5702-118">Specifies the maximum number of requests that can be queued for ASP.NET in a single process.</span></span> <span data-ttu-id="d5702-119">둘 이상의 ASP.NET 응용 프로그램을 단일 응용 프로그램 풀에서 실행 중인 응용 프로그램 풀의 모든 응용 프로그램에 대 한 요청의 누적 집합이이 설정은 하기 쉽습니다.</span><span class="sxs-lookup"><span data-stu-id="d5702-119">When two or more ASP.NET applications run in a single application pool, the cumulative set of requests being made to any application in the application pool is subject to this setting.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="d5702-120">자식 요소</span><span class="sxs-lookup"><span data-stu-id="d5702-120">Child Elements</span></span>  
 <span data-ttu-id="d5702-121">없음</span><span class="sxs-lookup"><span data-stu-id="d5702-121">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="d5702-122">부모 요소</span><span class="sxs-lookup"><span data-stu-id="d5702-122">Parent Elements</span></span>  
  
|<span data-ttu-id="d5702-123">요소</span><span class="sxs-lookup"><span data-stu-id="d5702-123">Element</span></span>|<span data-ttu-id="d5702-124">설명</span><span class="sxs-lookup"><span data-stu-id="d5702-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="d5702-125">\<system.web></span><span class="sxs-lookup"><span data-stu-id="d5702-125">\<system.web></span></span>](../../../../../docs/framework/configure-apps/file-schema/web/system-web-element-web-settings.md)|<span data-ttu-id="d5702-126">ASP.NET 응용 프로그램을 호스트와 상호 작용 하는 방법에 대 한 정보를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="d5702-126">Contains information about how ASP.NET interacts with a host application.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d5702-127">설명</span><span class="sxs-lookup"><span data-stu-id="d5702-127">Remarks</span></span>  
 <span data-ttu-id="d5702-128">실행할 때 [!INCLUDE[iisver](../../../../../includes/iisver-md.md)] 또는 통합된 모드의 이후 버전에서이 요소 조합을 사용 하 여 응용 프로그램은 IIS 응용 프로그램 풀에 호스팅되는 경우 ASP.NET 스레드 및 큐 요청을 관리 하는 방법을 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="d5702-128">When you run [!INCLUDE[iisver](../../../../../includes/iisver-md.md)] or a later version in Integrated mode, this element combination lets you configure how ASP.NET manages threads and queues requests when the application is hosted in an IIS application pool.</span></span> <span data-ttu-id="d5702-129">IIS 6을 실행 하거나 실행 하면 [!INCLUDE[iisver](../../../../../includes/iisver-md.md)] 클래식 모드에서 또는 ISAPI 모드에서 이러한 설정이 무시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d5702-129">If you run IIS 6 or you run [!INCLUDE[iisver](../../../../../includes/iisver-md.md)] in Classic mode or in ISAPI mode, these settings are ignored.</span></span>  
  
 <span data-ttu-id="d5702-130">`applicationPool` 설정은.NET Framework의 특정 버전에서 실행 되는 모든 응용 프로그램 풀에 적용 합니다.</span><span class="sxs-lookup"><span data-stu-id="d5702-130">The `applicationPool` settings apply to all application pools that run on a particular version of the .NET Framework.</span></span> <span data-ttu-id="d5702-131">설정을은 aspnet.config 파일에 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d5702-131">The settings are contained in an aspnet.config file.</span></span> <span data-ttu-id="d5702-132">버전 2.0 및.NET framework 4.0에 대 한이 파일의 버전이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d5702-132">There is a version of this file for versions 2.0 and 4.0 of the .NET Framework.</span></span> <span data-ttu-id="d5702-133">(버전 3.0 및 3.5는.NET Framework의 공유 aspnet.config 파일 버전 2.0 사용 하 여.)</span><span class="sxs-lookup"><span data-stu-id="d5702-133">(Versions 3.0 and 3.5 of the .NET Framework share the aspnet.config file with version 2.0.)</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="d5702-134">실행 하는 경우 [!INCLUDE[iisver](../../../../../includes/iisver-md.md)] 에서 [!INCLUDE[win7](../../../../../includes/win7-md.md)], 모든 응용 프로그램 풀에 대 한 별도 aspnet.config 파일을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d5702-134">If you run [!INCLUDE[iisver](../../../../../includes/iisver-md.md)] on [!INCLUDE[win7](../../../../../includes/win7-md.md)], you can configure a separate aspnet.config file for every application pool.</span></span> <span data-ttu-id="d5702-135">이렇게 하면 각 응용 프로그램 풀에 대 한 스레드의 성능을 조정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d5702-135">This lets you tailor the performance of the threads for each application pool.</span></span>  
  
 <span data-ttu-id="d5702-136">에 대 한는 `maxConcurrentRequestsPerCPU` 설정에서 기본 설정인 "5000"는 [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)] CPU 당 5000 개 이상의 요청이 실제로 없으면 ASP.NET에 의해 제어 되는 요청 된 제한 해제 효과적으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="d5702-136">For the `maxConcurrentRequestsPerCPU` setting, the default setting of "5000" in the [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)] effectively turns off request throttling that is controlled by ASP.NET, unless you actually have 5000 or more requests per CPU.</span></span> <span data-ttu-id="d5702-137">기본 설정은 자동으로 CPU 당 동시성을 관리 하도록 CLR 스레드 풀에 따라 대신 달라 집니다.</span><span class="sxs-lookup"><span data-stu-id="d5702-137">The default setting depends instead on the CLR thread-pool to automatically manage concurrency per CPU.</span></span> <span data-ttu-id="d5702-138">비동기 요청 처리를 광범위 하 게 사용 하는 또는 네트워크 I/O에서 차단 된 많은 장기 실행 요청이 응용 프로그램의 향상 된 기본 제한에서 이익을 [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)]합니다.</span><span class="sxs-lookup"><span data-stu-id="d5702-138">Applications that make extensive use of asynchronous request processing, or that have many long-running requests blocked on network I/O, will benefit from the increased default limit in the [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)].</span></span> <span data-ttu-id="d5702-139">설정 `maxConcurrentRequestsPerCPU` 를 0으로 설정 하면 관리 되는 스레드 사용 해제 ASP.NET 요청을 처리 합니다.</span><span class="sxs-lookup"><span data-stu-id="d5702-139">Setting `maxConcurrentRequestsPerCPU` to zero turns off the use of managed threads for processing ASP.NET requests.</span></span> <span data-ttu-id="d5702-140">응용 프로그램 IIS 응용 프로그램 풀에서 실행 되 면 IIS I/O 스레드 요청 유지 및 동시성 IIS 스레드 설정에 의해 제한 됩니다 따라서 합니다.</span><span class="sxs-lookup"><span data-stu-id="d5702-140">When an application runs in an IIS application pool, requests stay on the IIS I/O thread and therefore concurrency is throttled by IIS thread settings.</span></span>  
  
 <span data-ttu-id="d5702-141">`requestQueueLimit` 설정은 동일한 방식으로 작동 합니다 `requestQueueLimit` 특성을 [processModel](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/7w2sway1(v=vs.100)) ASP.NET 응용 프로그램에 대 한 Web.config 파일에 설정 된 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="d5702-141">The `requestQueueLimit` setting works the same way as the `requestQueueLimit` attribute of the [processModel](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/7w2sway1(v=vs.100)) element, which is set in the Web.config files for ASP.NET applications.</span></span> <span data-ttu-id="d5702-142">그러나 합니다 `requestQueueLimit` aspnet.config 파일의 설정 재정의 `requestQueueLimit` Web.config 파일에서 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="d5702-142">However, the `requestQueueLimit` setting in an aspnet.config file overrides the `requestQueueLimit` setting in a Web.config file.</span></span> <span data-ttu-id="d5702-143">즉, 두 특성 모두 설정 된 경우 (기본적으로 true 이면)는 `requestQueueLimit` aspnet.config 파일에서 설정이 우선 합니다.</span><span class="sxs-lookup"><span data-stu-id="d5702-143">In other words, if both attributes are set (by default, this is true), the `requestQueueLimit` setting in the aspnet.config file takes precedence.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d5702-144">예제</span><span class="sxs-lookup"><span data-stu-id="d5702-144">Example</span></span>  
 <span data-ttu-id="d5702-145">다음 예제에서는 다음과 같은 경우에서 aspnet.config 파일에서 ASP.NET 프로세스 전반 동작을 구성 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="d5702-145">The following example shows how to configure ASP.NET process-wide behavior in the aspnet.config file in the following circumstances:</span></span>  
  
- <span data-ttu-id="d5702-146">응용 프로그램에서 호스트 되는 [!INCLUDE[iisver](../../../../../includes/iisver-md.md)] 응용 프로그램 풀.</span><span class="sxs-lookup"><span data-stu-id="d5702-146">The application is hosted in an [!INCLUDE[iisver](../../../../../includes/iisver-md.md)] application pool.</span></span>  
  
- [!INCLUDE[iisver](../../../../../includes/iisver-md.md)] <span data-ttu-id="d5702-147">통합된 모드에서 실행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d5702-147">is running in Integrated mode.</span></span>  
  
- <span data-ttu-id="d5702-148">응용 프로그램을 사용 하는 [!INCLUDE[net_v35SP1_short](../../../../../includes/net-v35sp1-short-md.md)] 이상 버전.</span><span class="sxs-lookup"><span data-stu-id="d5702-148">The application is using the [!INCLUDE[net_v35SP1_short](../../../../../includes/net-v35sp1-short-md.md)] or a later version.</span></span>  
  
 <span data-ttu-id="d5702-149">예제에서 값은 기본값입니다.</span><span class="sxs-lookup"><span data-stu-id="d5702-149">The values in the example are the default values.</span></span>  
  
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
  
## <a name="element-information"></a><span data-ttu-id="d5702-150">요소 정보</span><span class="sxs-lookup"><span data-stu-id="d5702-150">Element Information</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="d5702-151">네임스페이스</span><span class="sxs-lookup"><span data-stu-id="d5702-151">Namespace</span></span>||  
|<span data-ttu-id="d5702-152">스키마 이름</span><span class="sxs-lookup"><span data-stu-id="d5702-152">Schema Name</span></span>||  
|<span data-ttu-id="d5702-153">유효성 검사 파일</span><span class="sxs-lookup"><span data-stu-id="d5702-153">Validation File</span></span>||  
|<span data-ttu-id="d5702-154">비워 둘 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d5702-154">Can be Empty</span></span>||  
  
## <a name="see-also"></a><span data-ttu-id="d5702-155">참고자료</span><span class="sxs-lookup"><span data-stu-id="d5702-155">See also</span></span>

- [<span data-ttu-id="d5702-156">\<system.web> 요소(웹 설정)</span><span class="sxs-lookup"><span data-stu-id="d5702-156">\<system.web> Element (Web Settings)</span></span>](../../../../../docs/framework/configure-apps/file-schema/web/system-web-element-web-settings.md)
