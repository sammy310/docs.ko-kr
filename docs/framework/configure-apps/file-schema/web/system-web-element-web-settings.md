---
title: <system.web> 요소(웹 설정)
ms.date: 03/30/2017
helpviewer_keywords:
- Web.config configuration file [ASP.NET]
- system.Web element
- <system.Web> element
- ASP.NET configuration system
- configuration files [ASP.NET]
ms.assetid: 24c4cf4f-ad32-42b2-b040-8e4549e2855e
ms.openlocfilehash: b37b05bdf90630251cbfcf86751243a3a8b77663
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79152843"
---
# <a name="systemweb-element-web-settings"></a><span data-ttu-id="8e361-102">\<system.web> 요소(웹 설정)</span><span class="sxs-lookup"><span data-stu-id="8e361-102">\<system.web> Element (Web Settings)</span></span>
<span data-ttu-id="8e361-103">ASP.NET 호스팅 계층이 프로세스 전체 동작을 관리하는 방법에 대한 정보를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="8e361-103">Contains information about how the ASP.NET hosting layer manages process-wide behavior.</span></span>  
  
[<span data-ttu-id="8e361-104">**\<구성>**</span><span class="sxs-lookup"><span data-stu-id="8e361-104">**\<configuration>**</span></span>](../configuration-element.md)  
<span data-ttu-id="8e361-105">&nbsp;&nbsp;**\<system.web>**</span><span class="sxs-lookup"><span data-stu-id="8e361-105">&nbsp;&nbsp;**\<system.web>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8e361-106">구문</span><span class="sxs-lookup"><span data-stu-id="8e361-106">Syntax</span></span>  
  
```xml  
<system.web>  
</system.web>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="8e361-107">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="8e361-107">Attributes and Elements</span></span>  

<span data-ttu-id="8e361-108">다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="8e361-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="8e361-109">특성</span><span class="sxs-lookup"><span data-stu-id="8e361-109">Attributes</span></span>  

<span data-ttu-id="8e361-110">없음</span><span class="sxs-lookup"><span data-stu-id="8e361-110">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="8e361-111">자식 요소</span><span class="sxs-lookup"><span data-stu-id="8e361-111">Child Elements</span></span>  
  
|<span data-ttu-id="8e361-112">요소</span><span class="sxs-lookup"><span data-stu-id="8e361-112">Element</span></span>|<span data-ttu-id="8e361-113">Description</span><span class="sxs-lookup"><span data-stu-id="8e361-113">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="8e361-114">\<애플리케이션풀></span><span class="sxs-lookup"><span data-stu-id="8e361-114">\<applicationPool></span></span>](applicationpool-element-web-settings.md)|<span data-ttu-id="8e361-115">aspnet.config 파일에서 IIS 응용 프로그램 풀에 대한 구성 설정을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="8e361-115">Specifies configuration settings for IIS application pools in an aspnet.config file.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="8e361-116">부모 요소</span><span class="sxs-lookup"><span data-stu-id="8e361-116">Parent Elements</span></span>  
  
|<span data-ttu-id="8e361-117">요소</span><span class="sxs-lookup"><span data-stu-id="8e361-117">Element</span></span>|<span data-ttu-id="8e361-118">Description</span><span class="sxs-lookup"><span data-stu-id="8e361-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="8e361-119">\<구성></span><span class="sxs-lookup"><span data-stu-id="8e361-119">\<configuration></span></span>](../configuration-element.md)|<span data-ttu-id="8e361-120">공통 언어 런타임 및 .NET Framework 응용 프로그램에서 사용하는 모든 구성 파일의 루트 요소를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="8e361-120">Specifies the root element in every configuration file that is used by the common language runtime and .NET Framework applications.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8e361-121">설명</span><span class="sxs-lookup"><span data-stu-id="8e361-121">Remarks</span></span>  

<span data-ttu-id="8e361-122">`system.web` .NET Framework `applicationPool` 3.5 SP1을 사용하여 요소와 자식 요소가 .NET 프레임워크에 추가되었습니다.</span><span class="sxs-lookup"><span data-stu-id="8e361-122">The `system.web` element and its child `applicationPool` element were added to the .NET Framework as of .NET Framework 3.5 SP1.</span></span> <span data-ttu-id="8e361-123">통합 모드에서 IIS 7.0 이상 버전을 실행하는 경우 이 요소 조합을 사용하면 ASP.NET 스레드를 관리하는 방법과 iIS 응용 프로그램 풀에서 호스팅될 때 요청을 큐에 대기하는 방법을 구성할 수 ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="8e361-123">When you run IIS 7.0 or later versions in Integrated mode, this element combination lets you configure how ASP.NET manages threads and how it queues requests when ASP.NET is hosted in an IIS application pool.</span></span> <span data-ttu-id="8e361-124">클래식 또는 ISAPI 모드에서 IIS 7.0 이상 버전을 실행하면 이러한 설정은 무시됩니다.</span><span class="sxs-lookup"><span data-stu-id="8e361-124">If you run IIS 7.0 or later versions in Classic or ISAPI mode, these settings are ignored.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8e361-125">예제</span><span class="sxs-lookup"><span data-stu-id="8e361-125">Example</span></span>  

<span data-ttu-id="8e361-126">다음 예제에서는 iis 응용 프로그램 풀에서 ASP.NET 호스트될 때 aspnet.config 파일에서 프로세스 ASP.NET 동작을 구성하는 방법을 보여 주며, 이 예제에서는</span><span class="sxs-lookup"><span data-stu-id="8e361-126">The following example shows how to configure ASP.NET process-wide behavior in the aspnet.config file when ASP.NET is hosted in an IIS application pool.</span></span> <span data-ttu-id="8e361-127">이 예제에서는 IIS가 통합 모드에서 실행중이며 응용 프로그램이 .NET Framework 3.5 SP1 또는 이후 버전을 사용하고 있다고 가정합니다.</span><span class="sxs-lookup"><span data-stu-id="8e361-127">The example assumes that IIS is running in Integrated mode and that the application is using the .NET Framework 3.5 SP1 or a later version.</span></span> <span data-ttu-id="8e361-128">이 동작은 .NET Framework 3.5 SP1 보다 이전의 .NET Framework 버전에서는 발생하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8e361-128">This behavior does not occur in versions of the .NET Framework earlier than the .NET Framework 3.5 SP1.</span></span> <span data-ttu-id="8e361-129">예제의 값은 기본값입니다.</span><span class="sxs-lookup"><span data-stu-id="8e361-129">The values in the example are the default values.</span></span>  
  
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
  
## <a name="element-information"></a><span data-ttu-id="8e361-130">요소 정보</span><span class="sxs-lookup"><span data-stu-id="8e361-130">Element Information</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="8e361-131">네임스페이스</span><span class="sxs-lookup"><span data-stu-id="8e361-131">Namespace</span></span>||  
|<span data-ttu-id="8e361-132">Schema Name</span><span class="sxs-lookup"><span data-stu-id="8e361-132">Schema Name</span></span>||  
|<span data-ttu-id="8e361-133">유효성 검사 파일</span><span class="sxs-lookup"><span data-stu-id="8e361-133">Validation File</span></span>||  
|<span data-ttu-id="8e361-134">비어 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8e361-134">Can be Empty</span></span>||  
  
## <a name="see-also"></a><span data-ttu-id="8e361-135">참고 항목</span><span class="sxs-lookup"><span data-stu-id="8e361-135">See also</span></span>

- [<span data-ttu-id="8e361-136">\<응용 프로그램풀> 요소(웹 설정)</span><span class="sxs-lookup"><span data-stu-id="8e361-136">\<applicationPool> Element (Web Settings)</span></span>](applicationpool-element-web-settings.md)
