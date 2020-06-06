---
title: <workflowControlEndpoint>
ms.date: 03/30/2017
ms.assetid: 6c89e76c-643b-4b6a-9b25-628f753d7027
ms.openlocfilehash: 670c1573fe4378a18c19d0a58fe58241745725bd
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/06/2020
ms.locfileid: "70854790"
---
# \<workflowControlEndpoint>
<span data-ttu-id="1d706-101">이 구성 요소는 워크플로 인스턴스의 실행(만들기, 실행, 일시 중단, 종료 등)을 제어하기 위한 표준 엔드포인트를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="1d706-101">This configuration element defines a standard endpoint for controlling the execution of workflow instances (create, run, suspend, terminate, etc).</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<standardEndpoints>**](standardendpoints.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<workflowControlEndpoint>**  
  
## <a name="syntax"></a><span data-ttu-id="1d706-102">구문</span><span class="sxs-lookup"><span data-stu-id="1d706-102">Syntax</span></span>  
  
```xml  
<system.serviceModel>
  <standardEndpoints>
    <workflowControlEndpoint>
      <standardEndpoint name="String" />
    </workflowControlEndpoint>
  </standardEndpoints>
</system.serviceModel>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="1d706-103">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="1d706-103">Attributes and Elements</span></span>  
 <span data-ttu-id="1d706-104">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="1d706-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="1d706-105">특성</span><span class="sxs-lookup"><span data-stu-id="1d706-105">Attributes</span></span>  
  
|<span data-ttu-id="1d706-106">attribute</span><span class="sxs-lookup"><span data-stu-id="1d706-106">Attribute</span></span>|<span data-ttu-id="1d706-107">Description</span><span class="sxs-lookup"><span data-stu-id="1d706-107">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="1d706-108">name</span><span class="sxs-lookup"><span data-stu-id="1d706-108">name</span></span>|<span data-ttu-id="1d706-109">표준 엔드포인트의 구성 이름을 지정하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="1d706-109">A String that specifies the name of the configuration of the standard endpoint.</span></span> <span data-ttu-id="1d706-110">이 이름은 서비스 엔드포인트의 `endpointConfiguration` 특성에서 표준 엔드포인트를 해당 구성에 연결하기 위해 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="1d706-110">The name is used in the `endpointConfiguration` attribute of the service endpoint to link a standard endpoint to its configuration.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="1d706-111">자식 요소</span><span class="sxs-lookup"><span data-stu-id="1d706-111">Child Elements</span></span>  
 <span data-ttu-id="1d706-112">없음</span><span class="sxs-lookup"><span data-stu-id="1d706-112">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="1d706-113">부모 요소</span><span class="sxs-lookup"><span data-stu-id="1d706-113">Parent Elements</span></span>  
  
|<span data-ttu-id="1d706-114">요소</span><span class="sxs-lookup"><span data-stu-id="1d706-114">Element</span></span>|<span data-ttu-id="1d706-115">Description</span><span class="sxs-lookup"><span data-stu-id="1d706-115">Description</span></span>|  
|-------------|-----------------|  
|[\<standardEndpoints>](standardendpoints.md)|<span data-ttu-id="1d706-116">하나 이상의 속성(주소, 바인딩, 계약)이 고정된 미리 정의된 엔드포인트인 표준 엔드포인트의 컬렉션입니다.</span><span class="sxs-lookup"><span data-stu-id="1d706-116">A collection of standard endpoints that are pre-defined endpoints with one or more of their properties (address, binding, contract) fixed.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="1d706-117">참고 항목</span><span class="sxs-lookup"><span data-stu-id="1d706-117">See also</span></span>

- <xref:System.ServiceModel.Activities.WorkflowControlEndpoint>
