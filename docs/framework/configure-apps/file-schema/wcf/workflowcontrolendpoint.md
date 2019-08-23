---
title: <workflowControlEndpoint>
ms.date: 03/30/2017
ms.assetid: 6c89e76c-643b-4b6a-9b25-628f753d7027
ms.openlocfilehash: 2c9774217b835acdb9ebf7374b964d838497fc9f
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/22/2019
ms.locfileid: "69915330"
---
# <a name="workflowcontrolendpoint"></a><span data-ttu-id="d8ddd-101">\<workflowControlEndpoint></span><span class="sxs-lookup"><span data-stu-id="d8ddd-101">\<workflowControlEndpoint></span></span>
<span data-ttu-id="d8ddd-102">이 구성 요소는 워크플로 인스턴스의 실행(만들기, 실행, 일시 중단, 종료 등)을 제어하기 위한 표준 엔드포인트를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="d8ddd-102">This configuration element defines a standard endpoint for controlling the execution of workflow instances (create, run, suspend, terminate, etc).</span></span>  
  
<span data-ttu-id="d8ddd-103">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="d8ddd-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="d8ddd-104">\<standardEndpoints></span><span class="sxs-lookup"><span data-stu-id="d8ddd-104">\<standardEndpoints></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d8ddd-105">구문</span><span class="sxs-lookup"><span data-stu-id="d8ddd-105">Syntax</span></span>  
  
```xml  
<system.serviceModel>
  <standardEndpoints>
    <workflowControlEndpoint>
      <standardEndpoint name="String" />
    </workflowControlEndpoint>
  </standardEndpoints>
</system.serviceModel>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="d8ddd-106">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="d8ddd-106">Attributes and Elements</span></span>  
 <span data-ttu-id="d8ddd-107">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="d8ddd-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="d8ddd-108">특성</span><span class="sxs-lookup"><span data-stu-id="d8ddd-108">Attributes</span></span>  
  
|<span data-ttu-id="d8ddd-109">특성</span><span class="sxs-lookup"><span data-stu-id="d8ddd-109">Attribute</span></span>|<span data-ttu-id="d8ddd-110">설명</span><span class="sxs-lookup"><span data-stu-id="d8ddd-110">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="d8ddd-111">name</span><span class="sxs-lookup"><span data-stu-id="d8ddd-111">name</span></span>|<span data-ttu-id="d8ddd-112">표준 엔드포인트의 구성 이름을 지정하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="d8ddd-112">A String that specifies the name of the configuration of the standard endpoint.</span></span> <span data-ttu-id="d8ddd-113">이 이름은 서비스 엔드포인트의 `endpointConfiguration` 특성에서 표준 엔드포인트를 해당 구성에 연결하기 위해 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="d8ddd-113">The name is used in the `endpointConfiguration` attribute of the service endpoint to link a standard endpoint to its configuration.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="d8ddd-114">자식 요소</span><span class="sxs-lookup"><span data-stu-id="d8ddd-114">Child Elements</span></span>  
 <span data-ttu-id="d8ddd-115">없음</span><span class="sxs-lookup"><span data-stu-id="d8ddd-115">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="d8ddd-116">부모 요소</span><span class="sxs-lookup"><span data-stu-id="d8ddd-116">Parent Elements</span></span>  
  
|<span data-ttu-id="d8ddd-117">요소</span><span class="sxs-lookup"><span data-stu-id="d8ddd-117">Element</span></span>|<span data-ttu-id="d8ddd-118">Description</span><span class="sxs-lookup"><span data-stu-id="d8ddd-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="d8ddd-119">\<standardEndpoints></span><span class="sxs-lookup"><span data-stu-id="d8ddd-119">\<standardEndpoints></span></span>](standardendpoints.md)|<span data-ttu-id="d8ddd-120">하나 이상의 속성(주소, 바인딩, 계약)이 고정된 미리 정의된 엔드포인트인 표준 엔드포인트의 컬렉션입니다.</span><span class="sxs-lookup"><span data-stu-id="d8ddd-120">A collection of standard endpoints that are pre-defined endpoints with one or more of their properties (address, binding, contract) fixed.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="d8ddd-121">참고자료</span><span class="sxs-lookup"><span data-stu-id="d8ddd-121">See also</span></span>

- <xref:System.ServiceModel.Activities.WorkflowControlEndpoint>
