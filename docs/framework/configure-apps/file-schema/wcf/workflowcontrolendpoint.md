---
description: 다음에 대해 자세히 알아보세요. <workflowControlEndpoint>
title: <workflowControlEndpoint>
ms.date: 03/30/2017
ms.assetid: 6c89e76c-643b-4b6a-9b25-628f753d7027
ms.openlocfilehash: 5205edf159bd947531231e69fd23f6cdf9c77d2d
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99682347"
---
# \<workflowControlEndpoint>

<span data-ttu-id="19f2b-102">이 구성 요소는 워크플로 인스턴스의 실행(만들기, 실행, 일시 중단, 종료 등)을 제어하기 위한 표준 엔드포인트를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="19f2b-102">This configuration element defines a standard endpoint for controlling the execution of workflow instances (create, run, suspend, terminate, etc).</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<standardEndpoints>**](standardendpoints.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<workflowControlEndpoint>**  
  
## <a name="syntax"></a><span data-ttu-id="19f2b-103">구문</span><span class="sxs-lookup"><span data-stu-id="19f2b-103">Syntax</span></span>  
  
```xml  
<system.serviceModel>
  <standardEndpoints>
    <workflowControlEndpoint>
      <standardEndpoint name="String" />
    </workflowControlEndpoint>
  </standardEndpoints>
</system.serviceModel>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="19f2b-104">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="19f2b-104">Attributes and Elements</span></span>  

 <span data-ttu-id="19f2b-105">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="19f2b-105">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="19f2b-106">특성</span><span class="sxs-lookup"><span data-stu-id="19f2b-106">Attributes</span></span>  
  
|<span data-ttu-id="19f2b-107">attribute</span><span class="sxs-lookup"><span data-stu-id="19f2b-107">Attribute</span></span>|<span data-ttu-id="19f2b-108">설명</span><span class="sxs-lookup"><span data-stu-id="19f2b-108">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="19f2b-109">name</span><span class="sxs-lookup"><span data-stu-id="19f2b-109">name</span></span>|<span data-ttu-id="19f2b-110">표준 엔드포인트의 구성 이름을 지정하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="19f2b-110">A String that specifies the name of the configuration of the standard endpoint.</span></span> <span data-ttu-id="19f2b-111">이 이름은 서비스 엔드포인트의 `endpointConfiguration` 특성에서 표준 엔드포인트를 해당 구성에 연결하기 위해 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="19f2b-111">The name is used in the `endpointConfiguration` attribute of the service endpoint to link a standard endpoint to its configuration.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="19f2b-112">자식 요소</span><span class="sxs-lookup"><span data-stu-id="19f2b-112">Child Elements</span></span>  

 <span data-ttu-id="19f2b-113">없음</span><span class="sxs-lookup"><span data-stu-id="19f2b-113">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="19f2b-114">부모 요소</span><span class="sxs-lookup"><span data-stu-id="19f2b-114">Parent Elements</span></span>  
  
|<span data-ttu-id="19f2b-115">요소</span><span class="sxs-lookup"><span data-stu-id="19f2b-115">Element</span></span>|<span data-ttu-id="19f2b-116">설명</span><span class="sxs-lookup"><span data-stu-id="19f2b-116">Description</span></span>|  
|-------------|-----------------|  
|[\<standardEndpoints>](standardendpoints.md)|<span data-ttu-id="19f2b-117">하나 이상의 속성(주소, 바인딩, 계약)이 고정된 미리 정의된 엔드포인트인 표준 엔드포인트의 컬렉션입니다.</span><span class="sxs-lookup"><span data-stu-id="19f2b-117">A collection of standard endpoints that are pre-defined endpoints with one or more of their properties (address, binding, contract) fixed.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="19f2b-118">참고 항목</span><span class="sxs-lookup"><span data-stu-id="19f2b-118">See also</span></span>

- <xref:System.ServiceModel.Activities.WorkflowControlEndpoint>
