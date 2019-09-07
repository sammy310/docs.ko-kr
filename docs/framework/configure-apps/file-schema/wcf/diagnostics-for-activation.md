---
title: <diagnostics>활성화
ms.date: 03/30/2017
ms.assetid: 1486e0eb-fe2a-46c3-b584-c924889477dd
ms.openlocfilehash: 33b2cd4c5ae1b4076892a61aa7e2b927efa1ddc1
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/06/2019
ms.locfileid: "70400404"
---
# <a name="diagnostics-for-activation"></a><span data-ttu-id="3d08c-102">\<정품 인증을 위한 진단 ></span><span class="sxs-lookup"><span data-stu-id="3d08c-102">\<diagnostics> for Activation</span></span>
<span data-ttu-id="3d08c-103">WCF (Windows Communication Foundation) 수신기의 진단 기능을 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="3d08c-103">Configures Windows Communication Foundation (WCF) listener's diagnostics functionalities.</span></span>  
  
<span data-ttu-id="3d08c-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="3d08c-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="3d08c-105">&nbsp;&nbsp;[ **\<System.servicemodel >** ](system-servicemodel-activation.md)</span><span class="sxs-lookup"><span data-stu-id="3d08c-105">&nbsp;&nbsp;[**\<system.serviceModel.activation>**](system-servicemodel-activation.md)</span></span>\
<span data-ttu-id="3d08c-106">&nbsp;&nbsp;&nbsp;&nbsp; **\<진단 >**</span><span class="sxs-lookup"><span data-stu-id="3d08c-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<diagnostics>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3d08c-107">구문</span><span class="sxs-lookup"><span data-stu-id="3d08c-107">Syntax</span></span>  
  
```xml  
<configuration>
  <system.serviceModel.activation>
    <diagnostics performanceCountersEnabled="Boolean" />
  </system.serviceModel.activation>
</configuration>
```  
  
## <a name="type"></a><span data-ttu-id="3d08c-108">형식</span><span class="sxs-lookup"><span data-stu-id="3d08c-108">Type</span></span>  
 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="3d08c-109">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="3d08c-109">Attributes and Elements</span></span>  
 <span data-ttu-id="3d08c-110">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="3d08c-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="3d08c-111">특성</span><span class="sxs-lookup"><span data-stu-id="3d08c-111">Attributes</span></span>  
  
|<span data-ttu-id="3d08c-112">특성</span><span class="sxs-lookup"><span data-stu-id="3d08c-112">Attribute</span></span>|<span data-ttu-id="3d08c-113">설명</span><span class="sxs-lookup"><span data-stu-id="3d08c-113">Description</span></span>|  
|---------------|-----------------|  
|`performanceCountersEnabled`|<span data-ttu-id="3d08c-114">진단 용도로 성능 카운터를 사용할지 여부를 나타내는 부울 값입니다.</span><span class="sxs-lookup"><span data-stu-id="3d08c-114">A Boolean value that indicates whether performance counters are enabled for diagnostic purposes.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="3d08c-115">자식 요소</span><span class="sxs-lookup"><span data-stu-id="3d08c-115">Child Elements</span></span>  
 <span data-ttu-id="3d08c-116">없음</span><span class="sxs-lookup"><span data-stu-id="3d08c-116">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="3d08c-117">부모 요소</span><span class="sxs-lookup"><span data-stu-id="3d08c-117">Parent Elements</span></span>  
  
|<span data-ttu-id="3d08c-118">요소</span><span class="sxs-lookup"><span data-stu-id="3d08c-118">Element</span></span>|<span data-ttu-id="3d08c-119">설명</span><span class="sxs-lookup"><span data-stu-id="3d08c-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="3d08c-120">\<system.serviceModel.activation></span><span class="sxs-lookup"><span data-stu-id="3d08c-120">\<system.serviceModel.activation></span></span>](system-servicemodel-activation.md)|<span data-ttu-id="3d08c-121">수신기 프로세스 SMSvcHost.exe에 대한 구성 설정을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="3d08c-121">Contains configuration settings for the listener process SMSvcHost.exe.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="3d08c-122">참고자료</span><span class="sxs-lookup"><span data-stu-id="3d08c-122">See also</span></span>

- <xref:System.ServiceModel.Activation.Configuration.DiagnosticSection>
