---
description: '자세히 알아보기: <diagnostics> 활성화'
title: <diagnostics> 활성화
ms.date: 03/30/2017
ms.assetid: 1486e0eb-fe2a-46c3-b584-c924889477dd
ms.openlocfilehash: aa1529a478ac367ea89c8926571c6c6f2f57cf74
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99698364"
---
# <a name="diagnostics-for-activation"></a><span data-ttu-id="4047f-103">\<diagnostics> 활성화</span><span class="sxs-lookup"><span data-stu-id="4047f-103">\<diagnostics> for Activation</span></span>

<span data-ttu-id="4047f-104">WCF (Windows Communication Foundation) 수신기의 진단 기능을 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="4047f-104">Configures Windows Communication Foundation (WCF) listener's diagnostics functionalities.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel.activation>**](system-servicemodel-activation.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<diagnostics>**  
  
## <a name="syntax"></a><span data-ttu-id="4047f-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="4047f-105">Syntax</span></span>  
  
```xml  
<configuration>
  <system.serviceModel.activation>
    <diagnostics performanceCountersEnabled="Boolean" />
  </system.serviceModel.activation>
</configuration>
```  
  
## <a name="type"></a><span data-ttu-id="4047f-106">Type</span><span class="sxs-lookup"><span data-stu-id="4047f-106">Type</span></span>  

 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="4047f-107">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="4047f-107">Attributes and Elements</span></span>  

 <span data-ttu-id="4047f-108">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="4047f-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="4047f-109">특성</span><span class="sxs-lookup"><span data-stu-id="4047f-109">Attributes</span></span>  
  
|<span data-ttu-id="4047f-110">attribute</span><span class="sxs-lookup"><span data-stu-id="4047f-110">Attribute</span></span>|<span data-ttu-id="4047f-111">설명</span><span class="sxs-lookup"><span data-stu-id="4047f-111">Description</span></span>|  
|---------------|-----------------|  
|`performanceCountersEnabled`|<span data-ttu-id="4047f-112">진단 용도로 성능 카운터를 사용할지 여부를 나타내는 부울 값입니다.</span><span class="sxs-lookup"><span data-stu-id="4047f-112">A Boolean value that indicates whether performance counters are enabled for diagnostic purposes.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="4047f-113">자식 요소</span><span class="sxs-lookup"><span data-stu-id="4047f-113">Child Elements</span></span>  

 <span data-ttu-id="4047f-114">없음</span><span class="sxs-lookup"><span data-stu-id="4047f-114">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="4047f-115">부모 요소</span><span class="sxs-lookup"><span data-stu-id="4047f-115">Parent Elements</span></span>  
  
|<span data-ttu-id="4047f-116">요소</span><span class="sxs-lookup"><span data-stu-id="4047f-116">Element</span></span>|<span data-ttu-id="4047f-117">설명</span><span class="sxs-lookup"><span data-stu-id="4047f-117">Description</span></span>|  
|-------------|-----------------|  
|[\<system.serviceModel.activation>](system-servicemodel-activation.md)|<span data-ttu-id="4047f-118">수신기 프로세스 SMSvcHost.exe에 대한 구성 설정을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="4047f-118">Contains configuration settings for the listener process SMSvcHost.exe.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="4047f-119">참고 항목</span><span class="sxs-lookup"><span data-stu-id="4047f-119">See also</span></span>

- <xref:System.ServiceModel.Activation.Configuration.DiagnosticSection>
