---
description: '다음에 대 한 자세한 정보: <appDomainResourceMonitoring> 요소'
title: <appDomainResourceMonitoring> 요소
ms.date: 03/30/2017
helpviewer_keywords:
- appDomainResourceMonitoring element
- <appDomainResourceMonitoring> element
ms.assetid: 02119ab6-1e91-448e-97ad-e7b2e5c4bbbd
ms.openlocfilehash: aee85386e6d0af2ca4fd30c0ad8fe69bae240315
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99719294"
---
# <a name="appdomainresourcemonitoring-element"></a><span data-ttu-id="875db-103">\<appDomainResourceMonitoring> 요소</span><span class="sxs-lookup"><span data-stu-id="875db-103">\<appDomainResourceMonitoring> Element</span></span>

<span data-ttu-id="875db-104">프로세스의 수명 동안 프로세스의 모든 애플리케이션 도메인에서 통계를 수집하도록 런타임에 명령합니다.</span><span class="sxs-lookup"><span data-stu-id="875db-104">Instructs the runtime to collect statistics on all application domains in the process for the life of the process.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<appDomainResourceMonitoring>**  
  
## <a name="syntax"></a><span data-ttu-id="875db-105">구문</span><span class="sxs-lookup"><span data-stu-id="875db-105">Syntax</span></span>  
  
```xml  
<appDomainResourceMonitoring
   enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="875db-106">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="875db-106">Attributes and Elements</span></span>  

 <span data-ttu-id="875db-107">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="875db-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="875db-108">특성</span><span class="sxs-lookup"><span data-stu-id="875db-108">Attributes</span></span>  
  
|<span data-ttu-id="875db-109">attribute</span><span class="sxs-lookup"><span data-stu-id="875db-109">Attribute</span></span>|<span data-ttu-id="875db-110">설명</span><span class="sxs-lookup"><span data-stu-id="875db-110">Description</span></span>|  
|---------------|-----------------|  
|`enabled`|<span data-ttu-id="875db-111">필수 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="875db-111">Required attribute.</span></span><br /><br /> <span data-ttu-id="875db-112">런타임이 응용 프로그램 도메인 리소스 모니터링에 대 한 통계를 수집 하는지 여부를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="875db-112">Specifies whether the runtime collects statistics for application domain resource monitoring.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="875db-113">enabled 특성</span><span class="sxs-lookup"><span data-stu-id="875db-113">enabled Attribute</span></span>  
  
|<span data-ttu-id="875db-114">값</span><span class="sxs-lookup"><span data-stu-id="875db-114">Value</span></span>|<span data-ttu-id="875db-115">설명</span><span class="sxs-lookup"><span data-stu-id="875db-115">Description</span></span>|  
|-----------|-----------------|  
|`true`|<span data-ttu-id="875db-116">응용 프로그램 도메인 리소스 모니터링에 대 한 통계가 수집 됩니다.</span><span class="sxs-lookup"><span data-stu-id="875db-116">Statistics for application domain resource monitoring are collected.</span></span>|  
|`false`|<span data-ttu-id="875db-117">응용 프로그램 도메인 리소스 모니터링에 대 한 통계는 수집 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="875db-117">Statistics for application domain resource monitoring are not collected.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="875db-118">자식 요소</span><span class="sxs-lookup"><span data-stu-id="875db-118">Child Elements</span></span>  

 <span data-ttu-id="875db-119">없음</span><span class="sxs-lookup"><span data-stu-id="875db-119">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="875db-120">부모 요소</span><span class="sxs-lookup"><span data-stu-id="875db-120">Parent Elements</span></span>  
  
|<span data-ttu-id="875db-121">요소</span><span class="sxs-lookup"><span data-stu-id="875db-121">Element</span></span>|<span data-ttu-id="875db-122">설명</span><span class="sxs-lookup"><span data-stu-id="875db-122">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="875db-123">공용 언어 런타임 및 .NET Framework 애플리케이션에서 사용하는 모든 구성 파일의 루트 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="875db-123">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="875db-124">어셈블리 바인딩 및 가비지 컬렉션에 대한 정보를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="875db-124">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="875db-125">설명</span><span class="sxs-lookup"><span data-stu-id="875db-125">Remarks</span></span>  

 <span data-ttu-id="875db-126">응용 프로그램 도메인 리소스 모니터링은 관리 되는 응용 프로그램 도메인 클래스, 호스팅 [ICLRAppDomainResourceMonitor](../../../unmanaged-api/hosting/iclrappdomainresourcemonitor-interface.md) 인터페이스 및 ETW (Windows 용 이벤트 추적)를 통해 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="875db-126">Application domain resource monitoring is available through the managed application domain class, the hosting [ICLRAppDomainResourceMonitor](../../../unmanaged-api/hosting/iclrappdomainresourcemonitor-interface.md) interface, and event tracing for Windows (ETW).</span></span> <span data-ttu-id="875db-127">모니터링을 사용 하는 경우 프로세스의 수명 동안 모든 응용 프로그램 도메인에 대 한 통계가 수집 됩니다.</span><span class="sxs-lookup"><span data-stu-id="875db-127">When monitoring is enabled, statistics are collected for all application domains in the process for the life of the process.</span></span>  
  
 <span data-ttu-id="875db-128">관리 코드에서 모니터링을 사용 하도록 설정 하려면 <xref:System.AppDomain.MonitoringIsEnabled%2A> 속성을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="875db-128">To enable monitoring from managed code, use the <xref:System.AppDomain.MonitoringIsEnabled%2A> property.</span></span>  
  
 <span data-ttu-id="875db-129">이 구성 요소는 .NET Framework 4 이상 에서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="875db-129">This configuration element is available only in the .NET Framework 4 and later.</span></span>  
  
## <a name="example"></a><span data-ttu-id="875db-130">예제</span><span class="sxs-lookup"><span data-stu-id="875db-130">Example</span></span>  

 <span data-ttu-id="875db-131">다음 예제에서는 응용 프로그램 도메인 리소스 모니터링을 사용 하도록 설정 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="875db-131">The following example shows how to enable application domain resource monitoring.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <appDomainResourceMonitoring enabled="true"/>  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="875db-132">참고 항목</span><span class="sxs-lookup"><span data-stu-id="875db-132">See also</span></span>

- <xref:System.AppDomain.MonitoringIsEnabled%2A?displayProperty=nameWithType>
- [<span data-ttu-id="875db-133">런타임 설정 스키마</span><span class="sxs-lookup"><span data-stu-id="875db-133">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="875db-134">구성 파일 스키마</span><span class="sxs-lookup"><span data-stu-id="875db-134">Configuration File Schema</span></span>](../index.md)
