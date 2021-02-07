---
description: '자세한 정보: <system.web> 요소 (웹 설정)'
title: <system.web> 요소(웹 설정)
ms.date: 03/30/2017
helpviewer_keywords:
- Web.config configuration file [ASP.NET]
- system.Web element
- <system.Web> element
- ASP.NET configuration system
- configuration files [ASP.NET]
ms.assetid: 24c4cf4f-ad32-42b2-b040-8e4549e2855e
ms.openlocfilehash: 2adcd3eba1eb6d67bcb4dc82243cd70d31d64fe9
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99681905"
---
# <a name="systemweb-element-web-settings"></a><span data-ttu-id="3884d-103">\<system.web> 요소(웹 설정)</span><span class="sxs-lookup"><span data-stu-id="3884d-103">\<system.web> Element (Web Settings)</span></span>

<span data-ttu-id="3884d-104">ASP.NET 호스팅 계층이 프로세스 전체 동작을 관리 하는 방법에 대 한 정보를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="3884d-104">Contains information about how the ASP.NET hosting layer manages process-wide behavior.</span></span>  
  
[**\<configuration>**](../configuration-element.md)  
&nbsp;&nbsp;**\<system.web>**  
  
## <a name="syntax"></a><span data-ttu-id="3884d-105">구문</span><span class="sxs-lookup"><span data-stu-id="3884d-105">Syntax</span></span>  
  
```xml  
<system.web>  
</system.web>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="3884d-106">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="3884d-106">Attributes and Elements</span></span>  

<span data-ttu-id="3884d-107">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="3884d-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="3884d-108">특성</span><span class="sxs-lookup"><span data-stu-id="3884d-108">Attributes</span></span>  

<span data-ttu-id="3884d-109">없음</span><span class="sxs-lookup"><span data-stu-id="3884d-109">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="3884d-110">자식 요소</span><span class="sxs-lookup"><span data-stu-id="3884d-110">Child Elements</span></span>  
  
|<span data-ttu-id="3884d-111">요소</span><span class="sxs-lookup"><span data-stu-id="3884d-111">Element</span></span>|<span data-ttu-id="3884d-112">설명</span><span class="sxs-lookup"><span data-stu-id="3884d-112">Description</span></span>|  
|-------------|-----------------|  
|[\<applicationPool>](applicationpool-element-web-settings.md)|<span data-ttu-id="3884d-113">aspnet.config 파일의 IIS 응용 프로그램 풀에 대 한 구성 설정을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="3884d-113">Specifies configuration settings for IIS application pools in an aspnet.config file.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="3884d-114">부모 요소</span><span class="sxs-lookup"><span data-stu-id="3884d-114">Parent Elements</span></span>  
  
|<span data-ttu-id="3884d-115">요소</span><span class="sxs-lookup"><span data-stu-id="3884d-115">Element</span></span>|<span data-ttu-id="3884d-116">설명</span><span class="sxs-lookup"><span data-stu-id="3884d-116">Description</span></span>|  
|-------------|-----------------|  
|[\<configuration>](../configuration-element.md)|<span data-ttu-id="3884d-117">공용 언어 런타임 및 .NET Framework 응용 프로그램에서 사용 하는 모든 구성 파일의 루트 요소를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="3884d-117">Specifies the root element in every configuration file that is used by the common language runtime and .NET Framework applications.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3884d-118">설명</span><span class="sxs-lookup"><span data-stu-id="3884d-118">Remarks</span></span>  

<span data-ttu-id="3884d-119">`system.web`요소와 해당 자식 `applicationPool` 요소가 .NET Framework 3.5 s p 1의 .NET Framework에 추가 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="3884d-119">The `system.web` element and its child `applicationPool` element were added to the .NET Framework as of .NET Framework 3.5 SP1.</span></span> <span data-ttu-id="3884d-120">통합 모드에서 IIS 7.0 이상 버전을 실행 하는 경우이 요소 조합을 사용 하면 ASP.NET에서 스레드를 관리 하는 방법 및 ASP.NET가 IIS 응용 프로그램 풀에서 호스팅되는 경우 요청을 큐에 대기 하는 방법을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3884d-120">When you run IIS 7.0 or later versions in Integrated mode, this element combination lets you configure how ASP.NET manages threads and how it queues requests when ASP.NET is hosted in an IIS application pool.</span></span> <span data-ttu-id="3884d-121">클래식 또는 ISAPI 모드에서 IIS 7.0 이상 버전을 실행 하는 경우 이러한 설정은 무시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3884d-121">If you run IIS 7.0 or later versions in Classic or ISAPI mode, these settings are ignored.</span></span>  
  
## <a name="example"></a><span data-ttu-id="3884d-122">예제</span><span class="sxs-lookup"><span data-stu-id="3884d-122">Example</span></span>  

<span data-ttu-id="3884d-123">다음 예제에서는 ASP.NET가 IIS 응용 프로그램 풀에서 호스팅될 때 aspnet.config 파일에서 ASP.NET 프로세스 전체 동작을 구성 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="3884d-123">The following example shows how to configure ASP.NET process-wide behavior in the aspnet.config file when ASP.NET is hosted in an IIS application pool.</span></span> <span data-ttu-id="3884d-124">이 예제에서는 IIS가 통합 모드로 실행 중이 고 응용 프로그램에서 .NET Framework 3.5 SP1 이상 버전을 사용 하 고 있다고 가정 합니다.</span><span class="sxs-lookup"><span data-stu-id="3884d-124">The example assumes that IIS is running in Integrated mode and that the application is using the .NET Framework 3.5 SP1 or a later version.</span></span> <span data-ttu-id="3884d-125">이 동작은 .NET Framework 3.5 s p 1 이전의 .NET Framework 버전에서 발생 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="3884d-125">This behavior does not occur in versions of the .NET Framework earlier than the .NET Framework 3.5 SP1.</span></span> <span data-ttu-id="3884d-126">이 예제의 값은 기본값입니다.</span><span class="sxs-lookup"><span data-stu-id="3884d-126">The values in the example are the default values.</span></span>  
  
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
  
## <a name="element-information"></a><span data-ttu-id="3884d-127">요소 정보</span><span class="sxs-lookup"><span data-stu-id="3884d-127">Element Information</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="3884d-128">네임스페이스</span><span class="sxs-lookup"><span data-stu-id="3884d-128">Namespace</span></span>||  
|<span data-ttu-id="3884d-129">Schema Name</span><span class="sxs-lookup"><span data-stu-id="3884d-129">Schema Name</span></span>||  
|<span data-ttu-id="3884d-130">유효성 검사 파일</span><span class="sxs-lookup"><span data-stu-id="3884d-130">Validation File</span></span>||  
|<span data-ttu-id="3884d-131">비워 둘 수 있음</span><span class="sxs-lookup"><span data-stu-id="3884d-131">Can be Empty</span></span>||  
  
## <a name="see-also"></a><span data-ttu-id="3884d-132">참고 항목</span><span class="sxs-lookup"><span data-stu-id="3884d-132">See also</span></span>

- [<span data-ttu-id="3884d-133">\<applicationPool> 요소 (웹 설정)</span><span class="sxs-lookup"><span data-stu-id="3884d-133">\<applicationPool> Element (Web Settings)</span></span>](applicationpool-element-web-settings.md)
