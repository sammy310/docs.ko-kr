---
title: <diagnostics>활성화
ms.date: 03/30/2017
ms.assetid: 1486e0eb-fe2a-46c3-b584-c924889477dd
ms.openlocfilehash: 33b2cd4c5ae1b4076892a61aa7e2b927efa1ddc1
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/06/2020
ms.locfileid: "70400404"
---
# <a name="diagnostics-for-activation"></a><span data-ttu-id="16f16-102">\<diagnostics>활성화</span><span class="sxs-lookup"><span data-stu-id="16f16-102">\<diagnostics> for Activation</span></span>
<span data-ttu-id="16f16-103">WCF (Windows Communication Foundation) 수신기의 진단 기능을 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="16f16-103">Configures Windows Communication Foundation (WCF) listener's diagnostics functionalities.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel.activation>**](system-servicemodel-activation.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<diagnostics>**  
  
## <a name="syntax"></a><span data-ttu-id="16f16-104">구문</span><span class="sxs-lookup"><span data-stu-id="16f16-104">Syntax</span></span>  
  
```xml  
<configuration>
  <system.serviceModel.activation>
    <diagnostics performanceCountersEnabled="Boolean" />
  </system.serviceModel.activation>
</configuration>
```  
  
## <a name="type"></a><span data-ttu-id="16f16-105">Type</span><span class="sxs-lookup"><span data-stu-id="16f16-105">Type</span></span>  
 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="16f16-106">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="16f16-106">Attributes and Elements</span></span>  
 <span data-ttu-id="16f16-107">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="16f16-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="16f16-108">특성</span><span class="sxs-lookup"><span data-stu-id="16f16-108">Attributes</span></span>  
  
|<span data-ttu-id="16f16-109">attribute</span><span class="sxs-lookup"><span data-stu-id="16f16-109">Attribute</span></span>|<span data-ttu-id="16f16-110">Description</span><span class="sxs-lookup"><span data-stu-id="16f16-110">Description</span></span>|  
|---------------|-----------------|  
|`performanceCountersEnabled`|<span data-ttu-id="16f16-111">진단 용도로 성능 카운터를 사용할지 여부를 나타내는 부울 값입니다.</span><span class="sxs-lookup"><span data-stu-id="16f16-111">A Boolean value that indicates whether performance counters are enabled for diagnostic purposes.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="16f16-112">자식 요소</span><span class="sxs-lookup"><span data-stu-id="16f16-112">Child Elements</span></span>  
 <span data-ttu-id="16f16-113">없음</span><span class="sxs-lookup"><span data-stu-id="16f16-113">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="16f16-114">부모 요소</span><span class="sxs-lookup"><span data-stu-id="16f16-114">Parent Elements</span></span>  
  
|<span data-ttu-id="16f16-115">요소</span><span class="sxs-lookup"><span data-stu-id="16f16-115">Element</span></span>|<span data-ttu-id="16f16-116">Description</span><span class="sxs-lookup"><span data-stu-id="16f16-116">Description</span></span>|  
|-------------|-----------------|  
|[\<system.serviceModel.activation>](system-servicemodel-activation.md)|<span data-ttu-id="16f16-117">수신기 프로세스 SMSvcHost.exe에 대한 구성 설정을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="16f16-117">Contains configuration settings for the listener process SMSvcHost.exe.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="16f16-118">참고 항목</span><span class="sxs-lookup"><span data-stu-id="16f16-118">See also</span></span>

- <xref:System.ServiceModel.Activation.Configuration.DiagnosticSection>
