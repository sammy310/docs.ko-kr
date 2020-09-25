---
title: <appDomainResourceMonitoring> 요소
ms.date: 03/30/2017
helpviewer_keywords:
- appDomainResourceMonitoring element
- <appDomainResourceMonitoring> element
ms.assetid: 02119ab6-1e91-448e-97ad-e7b2e5c4bbbd
ms.openlocfilehash: 9ecf2e382b5d483377df871835793219b3f74760
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/24/2020
ms.locfileid: "91170274"
---
# <a name="appdomainresourcemonitoring-element"></a><span data-ttu-id="776d9-102">\<appDomainResourceMonitoring> 요소</span><span class="sxs-lookup"><span data-stu-id="776d9-102">\<appDomainResourceMonitoring> Element</span></span>

<span data-ttu-id="776d9-103">프로세스의 수명 동안 프로세스의 모든 애플리케이션 도메인에서 통계를 수집하도록 런타임에 명령합니다.</span><span class="sxs-lookup"><span data-stu-id="776d9-103">Instructs the runtime to collect statistics on all application domains in the process for the life of the process.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<appDomainResourceMonitoring>**  
  
## <a name="syntax"></a><span data-ttu-id="776d9-104">구문</span><span class="sxs-lookup"><span data-stu-id="776d9-104">Syntax</span></span>  
  
```xml  
<appDomainResourceMonitoring
   enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="776d9-105">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="776d9-105">Attributes and Elements</span></span>  

 <span data-ttu-id="776d9-106">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="776d9-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="776d9-107">특성</span><span class="sxs-lookup"><span data-stu-id="776d9-107">Attributes</span></span>  
  
|<span data-ttu-id="776d9-108">attribute</span><span class="sxs-lookup"><span data-stu-id="776d9-108">Attribute</span></span>|<span data-ttu-id="776d9-109">설명</span><span class="sxs-lookup"><span data-stu-id="776d9-109">Description</span></span>|  
|---------------|-----------------|  
|`enabled`|<span data-ttu-id="776d9-110">필수 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="776d9-110">Required attribute.</span></span><br /><br /> <span data-ttu-id="776d9-111">런타임이 응용 프로그램 도메인 리소스 모니터링에 대 한 통계를 수집 하는지 여부를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="776d9-111">Specifies whether the runtime collects statistics for application domain resource monitoring.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="776d9-112">enabled 특성</span><span class="sxs-lookup"><span data-stu-id="776d9-112">enabled Attribute</span></span>  
  
|<span data-ttu-id="776d9-113">Value</span><span class="sxs-lookup"><span data-stu-id="776d9-113">Value</span></span>|<span data-ttu-id="776d9-114">설명</span><span class="sxs-lookup"><span data-stu-id="776d9-114">Description</span></span>|  
|-----------|-----------------|  
|`true`|<span data-ttu-id="776d9-115">응용 프로그램 도메인 리소스 모니터링에 대 한 통계가 수집 됩니다.</span><span class="sxs-lookup"><span data-stu-id="776d9-115">Statistics for application domain resource monitoring are collected.</span></span>|  
|`false`|<span data-ttu-id="776d9-116">응용 프로그램 도메인 리소스 모니터링에 대 한 통계는 수집 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="776d9-116">Statistics for application domain resource monitoring are not collected.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="776d9-117">자식 요소</span><span class="sxs-lookup"><span data-stu-id="776d9-117">Child Elements</span></span>  

 <span data-ttu-id="776d9-118">없음</span><span class="sxs-lookup"><span data-stu-id="776d9-118">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="776d9-119">부모 요소</span><span class="sxs-lookup"><span data-stu-id="776d9-119">Parent Elements</span></span>  
  
|<span data-ttu-id="776d9-120">요소</span><span class="sxs-lookup"><span data-stu-id="776d9-120">Element</span></span>|<span data-ttu-id="776d9-121">설명</span><span class="sxs-lookup"><span data-stu-id="776d9-121">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="776d9-122">공용 언어 런타임 및 .NET Framework 애플리케이션에서 사용하는 모든 구성 파일의 루트 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="776d9-122">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="776d9-123">어셈블리 바인딩 및 가비지 컬렉션에 대한 정보를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="776d9-123">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="776d9-124">설명</span><span class="sxs-lookup"><span data-stu-id="776d9-124">Remarks</span></span>  

 <span data-ttu-id="776d9-125">응용 프로그램 도메인 리소스 모니터링은 관리 되는 응용 프로그램 도메인 클래스, 호스팅 [ICLRAppDomainResourceMonitor](../../../unmanaged-api/hosting/iclrappdomainresourcemonitor-interface.md) 인터페이스 및 ETW (Windows 용 이벤트 추적)를 통해 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="776d9-125">Application domain resource monitoring is available through the managed application domain class, the hosting [ICLRAppDomainResourceMonitor](../../../unmanaged-api/hosting/iclrappdomainresourcemonitor-interface.md) interface, and event tracing for Windows (ETW).</span></span> <span data-ttu-id="776d9-126">모니터링을 사용 하는 경우 프로세스의 수명 동안 모든 응용 프로그램 도메인에 대 한 통계가 수집 됩니다.</span><span class="sxs-lookup"><span data-stu-id="776d9-126">When monitoring is enabled, statistics are collected for all application domains in the process for the life of the process.</span></span>  
  
 <span data-ttu-id="776d9-127">관리 코드에서 모니터링을 사용 하도록 설정 하려면 <xref:System.AppDomain.MonitoringIsEnabled%2A> 속성을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="776d9-127">To enable monitoring from managed code, use the <xref:System.AppDomain.MonitoringIsEnabled%2A> property.</span></span>  
  
 <span data-ttu-id="776d9-128">이 구성 요소는 .NET Framework 4 이상 에서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="776d9-128">This configuration element is available only in the .NET Framework 4 and later.</span></span>  
  
## <a name="example"></a><span data-ttu-id="776d9-129">예제</span><span class="sxs-lookup"><span data-stu-id="776d9-129">Example</span></span>  

 <span data-ttu-id="776d9-130">다음 예제에서는 응용 프로그램 도메인 리소스 모니터링을 사용 하도록 설정 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="776d9-130">The following example shows how to enable application domain resource monitoring.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <appDomainResourceMonitoring enabled="true"/>  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="776d9-131">참고 항목</span><span class="sxs-lookup"><span data-stu-id="776d9-131">See also</span></span>

- <xref:System.AppDomain.MonitoringIsEnabled%2A?displayProperty=nameWithType>
- [<span data-ttu-id="776d9-132">런타임 설정 스키마</span><span class="sxs-lookup"><span data-stu-id="776d9-132">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="776d9-133">구성 파일 스키마</span><span class="sxs-lookup"><span data-stu-id="776d9-133">Configuration File Schema</span></span>](../index.md)
