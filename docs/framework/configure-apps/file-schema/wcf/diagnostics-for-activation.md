---
title: <diagnostics> 활성화
ms.date: 03/30/2017
ms.assetid: 1486e0eb-fe2a-46c3-b584-c924889477dd
ms.openlocfilehash: c16f32357d40b9b69d52c525ce8a395a3de8fdb1
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/24/2020
ms.locfileid: "91192323"
---
# <a name="diagnostics-for-activation"></a><span data-ttu-id="c0ff7-102">\<diagnostics> 활성화</span><span class="sxs-lookup"><span data-stu-id="c0ff7-102">\<diagnostics> for Activation</span></span>

<span data-ttu-id="c0ff7-103">WCF (Windows Communication Foundation) 수신기의 진단 기능을 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="c0ff7-103">Configures Windows Communication Foundation (WCF) listener's diagnostics functionalities.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel.activation>**](system-servicemodel-activation.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<diagnostics>**  
  
## <a name="syntax"></a><span data-ttu-id="c0ff7-104">구문</span><span class="sxs-lookup"><span data-stu-id="c0ff7-104">Syntax</span></span>  
  
```xml  
<configuration>
  <system.serviceModel.activation>
    <diagnostics performanceCountersEnabled="Boolean" />
  </system.serviceModel.activation>
</configuration>
```  
  
## <a name="type"></a><span data-ttu-id="c0ff7-105">형식</span><span class="sxs-lookup"><span data-stu-id="c0ff7-105">Type</span></span>  

 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="c0ff7-106">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="c0ff7-106">Attributes and Elements</span></span>  

 <span data-ttu-id="c0ff7-107">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="c0ff7-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="c0ff7-108">특성</span><span class="sxs-lookup"><span data-stu-id="c0ff7-108">Attributes</span></span>  
  
|<span data-ttu-id="c0ff7-109">attribute</span><span class="sxs-lookup"><span data-stu-id="c0ff7-109">Attribute</span></span>|<span data-ttu-id="c0ff7-110">설명</span><span class="sxs-lookup"><span data-stu-id="c0ff7-110">Description</span></span>|  
|---------------|-----------------|  
|`performanceCountersEnabled`|<span data-ttu-id="c0ff7-111">진단 용도로 성능 카운터를 사용할지 여부를 나타내는 부울 값입니다.</span><span class="sxs-lookup"><span data-stu-id="c0ff7-111">A Boolean value that indicates whether performance counters are enabled for diagnostic purposes.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="c0ff7-112">자식 요소</span><span class="sxs-lookup"><span data-stu-id="c0ff7-112">Child Elements</span></span>  

 <span data-ttu-id="c0ff7-113">없음</span><span class="sxs-lookup"><span data-stu-id="c0ff7-113">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="c0ff7-114">부모 요소</span><span class="sxs-lookup"><span data-stu-id="c0ff7-114">Parent Elements</span></span>  
  
|<span data-ttu-id="c0ff7-115">요소</span><span class="sxs-lookup"><span data-stu-id="c0ff7-115">Element</span></span>|<span data-ttu-id="c0ff7-116">설명</span><span class="sxs-lookup"><span data-stu-id="c0ff7-116">Description</span></span>|  
|-------------|-----------------|  
|[\<system.serviceModel.activation>](system-servicemodel-activation.md)|<span data-ttu-id="c0ff7-117">수신기 프로세스 SMSvcHost.exe에 대한 구성 설정을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="c0ff7-117">Contains configuration settings for the listener process SMSvcHost.exe.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="c0ff7-118">참고 항목</span><span class="sxs-lookup"><span data-stu-id="c0ff7-118">See also</span></span>

- <xref:System.ServiceModel.Activation.Configuration.DiagnosticSection>
