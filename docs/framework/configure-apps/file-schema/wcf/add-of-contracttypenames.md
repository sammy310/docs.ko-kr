---
title: <add> / <contractTypeNames>
ms.date: 03/30/2017
ms.assetid: 03aff6be-5dfb-4a64-ada3-e36227cd43c7
ms.openlocfilehash: 856298cb0639cf19b941f326b5b9a25aa6663088
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59091319"
---
# <a name="add-of-contracttypenames"></a><span data-ttu-id="b1abd-102">\<추가 >의 \<contractTypeNames ></span><span class="sxs-lookup"><span data-stu-id="b1abd-102">\<add> of \<contractTypeNames></span></span>
<span data-ttu-id="b1abd-103">검색할 서비스의 계약 이름 및 서비스를 검색할 때 일반적으로 사용되는 기준을 지정하는 구성 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="b1abd-103">A configuration element that specifies the contract name of the services being searched for, and the criteria typically used when searching for a service.</span></span> <span data-ttu-id="b1abd-104">둘 이상의 계약 이름이 지정되면 모든 계약과 일치하는 서비스 엔드포인트만 응답합니다.</span><span class="sxs-lookup"><span data-stu-id="b1abd-104">If more than one contract name is specified, only service endpoints matching ALL contracts will reply.</span></span> <span data-ttu-id="b1abd-105">Windows Communication Foundation (WCF), 끝점 수 하나의 계약만 지원할 참고 합니다.</span><span class="sxs-lookup"><span data-stu-id="b1abd-105">Note that in Windows Communication Foundation (WCF), an endpoint can only support one contract.</span></span>  
  
 <span data-ttu-id="b1abd-106">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="b1abd-106">\<system.ServiceModel></span></span>  
<span data-ttu-id="b1abd-107">\<standardEndpoints></span><span class="sxs-lookup"><span data-stu-id="b1abd-107">\<standardEndpoints></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b1abd-108">구문</span><span class="sxs-lookup"><span data-stu-id="b1abd-108">Syntax</span></span>  
  
```xml  
<system.serviceModel>
  <standardEndpoints>
    <dynamicEndpoint>
      <standardEndpoint>
        <discoveryClientSettings discoveryEndpoint="String">
          <findCriteria duration="TimeSpan"
                        maxResults="Integer"
                        scopeMatchBy="Uri">
            <contractTypeNames>
              <add name="String" namespace="String" />
            <contractTypeNames>
            <extensions />
            <scopes>
              <add scope="URI"/>
            </scopes>
          </findCriteria>
        </discoveryClientSettings>
      <standardEndpoint>
    </dynamicEndpoint>
  </standardEndpoints>
</system.serviceModel>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="b1abd-109">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="b1abd-109">Attributes and Elements</span></span>  
 <span data-ttu-id="b1abd-110">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="b1abd-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="b1abd-111">특성</span><span class="sxs-lookup"><span data-stu-id="b1abd-111">Attributes</span></span>  
  
|<span data-ttu-id="b1abd-112">특성</span><span class="sxs-lookup"><span data-stu-id="b1abd-112">Attribute</span></span>|<span data-ttu-id="b1abd-113">설명</span><span class="sxs-lookup"><span data-stu-id="b1abd-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="b1abd-114">name</span><span class="sxs-lookup"><span data-stu-id="b1abd-114">name</span></span>|<span data-ttu-id="b1abd-115">계약 형식의 이름을 지정하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="b1abd-115">A string that specifies the name of the contract type.</span></span>|  
|<span data-ttu-id="b1abd-116">namespace</span><span class="sxs-lookup"><span data-stu-id="b1abd-116">namespace</span></span>|<span data-ttu-id="b1abd-117">계약 형식의 네임스페이스를 지정하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="b1abd-117">A string that specifies the namespace of the contract type.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="b1abd-118">자식 요소</span><span class="sxs-lookup"><span data-stu-id="b1abd-118">Child Elements</span></span>  
 <span data-ttu-id="b1abd-119">없음</span><span class="sxs-lookup"><span data-stu-id="b1abd-119">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="b1abd-120">부모 요소</span><span class="sxs-lookup"><span data-stu-id="b1abd-120">Parent Elements</span></span>  
  
|<span data-ttu-id="b1abd-121">요소</span><span class="sxs-lookup"><span data-stu-id="b1abd-121">Element</span></span>|<span data-ttu-id="b1abd-122">설명</span><span class="sxs-lookup"><span data-stu-id="b1abd-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="b1abd-123">\<contractTypeNames></span><span class="sxs-lookup"><span data-stu-id="b1abd-123">\<contractTypeNames></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/contracttypenames.md)|<span data-ttu-id="b1abd-124">계약 형식 이름의 컬렉션입니다.</span><span class="sxs-lookup"><span data-stu-id="b1abd-124">A collection of contract type names.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="b1abd-125">참고자료</span><span class="sxs-lookup"><span data-stu-id="b1abd-125">See also</span></span>

- <xref:System.ServiceModel.Discovery.FindCriteria>
- <xref:System.ServiceModel.Discovery.Configuration.FindCriteriaElement>
- <xref:System.ServiceModel.Discovery.Configuration.ContractTypeNameElement>
