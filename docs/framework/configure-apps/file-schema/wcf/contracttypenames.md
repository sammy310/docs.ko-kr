---
title: <contractTypeNames>
ms.date: 03/30/2017
ms.assetid: 5ec5efc6-87f8-4160-9be0-dcd2e01df3df
ms.openlocfilehash: b1cec9272a1de029ab72ea4d5f36c74630e5b93a
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59089499"
---
# <a name="contracttypenames"></a><span data-ttu-id="4925c-101">\<contractTypeNames></span><span class="sxs-lookup"><span data-stu-id="4925c-101">\<contractTypeNames></span></span>
<span data-ttu-id="4925c-102">검색할 서비스의 계약 이름인 계약 형식 이름 목록 및 서비스를 검색할 때 일반적으로 사용되는 기준을 지정하는 구성 섹션입니다.</span><span class="sxs-lookup"><span data-stu-id="4925c-102">A configuration section that specifies a list of contract type names, which are the contract names of the services being searched for, and the criteria typically used when searching for a service.</span></span> <span data-ttu-id="4925c-103">둘 이상의 계약 이름이 지정되면 모든 계약과 일치하는 서비스 엔드포인트만 응답합니다.</span><span class="sxs-lookup"><span data-stu-id="4925c-103">If more than one contract name is specified, only service endpoints matching ALL contracts will reply.</span></span> <span data-ttu-id="4925c-104">Windows Communication Foundation (WCF), 끝점 수 하나의 계약만 지원할 참고 합니다.</span><span class="sxs-lookup"><span data-stu-id="4925c-104">Note that in Windows Communication Foundation (WCF), an endpoint can only support one contract.</span></span>  
  
 <span data-ttu-id="4925c-105">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="4925c-105">\<system.ServiceModel></span></span>  
<span data-ttu-id="4925c-106">\<standardEndpoints></span><span class="sxs-lookup"><span data-stu-id="4925c-106">\<standardEndpoints></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4925c-107">구문</span><span class="sxs-lookup"><span data-stu-id="4925c-107">Syntax</span></span>  
  
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
              <add name="String"
                   namespace="String" />
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="4925c-108">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="4925c-108">Attributes and Elements</span></span>  
 <span data-ttu-id="4925c-109">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="4925c-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="4925c-110">특성</span><span class="sxs-lookup"><span data-stu-id="4925c-110">Attributes</span></span>  
 <span data-ttu-id="4925c-111">없음</span><span class="sxs-lookup"><span data-stu-id="4925c-111">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="4925c-112">자식 요소</span><span class="sxs-lookup"><span data-stu-id="4925c-112">Child Elements</span></span>  
  
|<span data-ttu-id="4925c-113">요소</span><span class="sxs-lookup"><span data-stu-id="4925c-113">Element</span></span>|<span data-ttu-id="4925c-114">설명</span><span class="sxs-lookup"><span data-stu-id="4925c-114">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="4925c-115">\<add></span><span class="sxs-lookup"><span data-stu-id="4925c-115">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/contracttypenames.md)|<span data-ttu-id="4925c-116">계약 형식 이름은 서비스를 검색할 때 일반적으로 사용되는 조건 집합을 나타나는 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="4925c-116">A contract type name is a property that refers to the set of criteria typically used when searching for a service.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="4925c-117">부모 요소</span><span class="sxs-lookup"><span data-stu-id="4925c-117">Parent Elements</span></span>  
  
|<span data-ttu-id="4925c-118">요소</span><span class="sxs-lookup"><span data-stu-id="4925c-118">Element</span></span>|<span data-ttu-id="4925c-119">설명</span><span class="sxs-lookup"><span data-stu-id="4925c-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="4925c-120">\<findCriteria></span><span class="sxs-lookup"><span data-stu-id="4925c-120">\<findCriteria></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/findcriteria.md)|<span data-ttu-id="4925c-121">클라이언트 응용 프로그램에서 검색 서비스를 찾기 위해 사용하는 조건 집합을 제공하는 구성 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="4925c-121">A configuration element that supplies a set of criteria used by a client application to search for a discovery service.</span></span> <span data-ttu-id="4925c-122">조건 (찾으려는 서비스 지정) 하는 검색 조건으로 그룹화 할 수 있습니다 및 찾기 종료 조건 (검색 지속 기간).</span><span class="sxs-lookup"><span data-stu-id="4925c-122">Criteria can be grouped into search criteria (specifying what services you’re looking for) and find termination criteria (how long the search should last).</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="4925c-123">참고자료</span><span class="sxs-lookup"><span data-stu-id="4925c-123">See also</span></span>

- <xref:System.ServiceModel.Discovery.FindCriteria>
- <xref:System.ServiceModel.Discovery.Configuration.FindCriteriaElement>
- <xref:System.ServiceModel.Discovery.Configuration.ContractTypeNameElementCollection>
