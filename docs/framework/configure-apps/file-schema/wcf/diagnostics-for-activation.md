---
title: <diagnostics> 정품 인증
ms.date: 03/30/2017
ms.assetid: 1486e0eb-fe2a-46c3-b584-c924889477dd
ms.openlocfilehash: 30456963a7d74a93e39bb1fddc0910daae97f039
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59203810"
---
# <a name="diagnostics-for-activation"></a><span data-ttu-id="74b8a-102">\<진단 > 활성화</span><span class="sxs-lookup"><span data-stu-id="74b8a-102">\<diagnostics> for Activation</span></span>
<span data-ttu-id="74b8a-103">Windows Communication Foundation (WCF) 수신기의 진단 기능을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="74b8a-103">Configures Windows Communication Foundation (WCF) listener's diagnostics functionalities.</span></span>  
  
 <span data-ttu-id="74b8a-104">\<system.serviceModel.activation></span><span class="sxs-lookup"><span data-stu-id="74b8a-104">\<system.serviceModel.activation></span></span>  
<span data-ttu-id="74b8a-105">\<diagnostics></span><span class="sxs-lookup"><span data-stu-id="74b8a-105">\<diagnostics></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="74b8a-106">구문</span><span class="sxs-lookup"><span data-stu-id="74b8a-106">Syntax</span></span>  
  
```xml  
<configuration>
  <system.serviceModel.activation>
    <diagnostics performanceCountersEnabled="Boolean" />
  </system.serviceModel.activation>
</configuration>
```  
  
## <a name="type"></a><span data-ttu-id="74b8a-107">형식</span><span class="sxs-lookup"><span data-stu-id="74b8a-107">Type</span></span>  
 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="74b8a-108">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="74b8a-108">Attributes and Elements</span></span>  
 <span data-ttu-id="74b8a-109">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="74b8a-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="74b8a-110">특성</span><span class="sxs-lookup"><span data-stu-id="74b8a-110">Attributes</span></span>  
  
|<span data-ttu-id="74b8a-111">특성</span><span class="sxs-lookup"><span data-stu-id="74b8a-111">Attribute</span></span>|<span data-ttu-id="74b8a-112">설명</span><span class="sxs-lookup"><span data-stu-id="74b8a-112">Description</span></span>|  
|---------------|-----------------|  
|`performanceCountersEnabled`|<span data-ttu-id="74b8a-113">진단 용도로 성능 카운터를 사용할지 여부를 나타내는 부울 값입니다.</span><span class="sxs-lookup"><span data-stu-id="74b8a-113">A Boolean value that indicates whether performance counters are enabled for diagnostic purposes.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="74b8a-114">자식 요소</span><span class="sxs-lookup"><span data-stu-id="74b8a-114">Child Elements</span></span>  
 <span data-ttu-id="74b8a-115">없음</span><span class="sxs-lookup"><span data-stu-id="74b8a-115">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="74b8a-116">부모 요소</span><span class="sxs-lookup"><span data-stu-id="74b8a-116">Parent Elements</span></span>  
  
|<span data-ttu-id="74b8a-117">요소</span><span class="sxs-lookup"><span data-stu-id="74b8a-117">Element</span></span>|<span data-ttu-id="74b8a-118">설명</span><span class="sxs-lookup"><span data-stu-id="74b8a-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="74b8a-119">\<system.serviceModel.activation></span><span class="sxs-lookup"><span data-stu-id="74b8a-119">\<system.serviceModel.activation></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel-activation.md)|<span data-ttu-id="74b8a-120">수신기 프로세스 SMSvcHost.exe에 대한 구성 설정을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="74b8a-120">Contains configuration settings for the listener process SMSvcHost.exe.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="74b8a-121">참고자료</span><span class="sxs-lookup"><span data-stu-id="74b8a-121">See also</span></span>

- <xref:System.ServiceModel.Activation.Configuration.DiagnosticSection>
