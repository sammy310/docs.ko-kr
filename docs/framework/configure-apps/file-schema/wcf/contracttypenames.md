---
title: <contractTypeNames>
ms.date: 03/30/2017
ms.assetid: 5ec5efc6-87f8-4160-9be0-dcd2e01df3df
ms.openlocfilehash: 12f9d4eca02ae3b306646826667c4eafef51a95c
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/22/2019
ms.locfileid: "69919370"
---
# <a name="contracttypenames"></a><span data-ttu-id="aee72-101">\<contractTypeNames></span><span class="sxs-lookup"><span data-stu-id="aee72-101">\<contractTypeNames></span></span>
<span data-ttu-id="aee72-102">검색할 서비스의 계약 이름인 계약 형식 이름 목록 및 서비스를 검색할 때 일반적으로 사용되는 기준을 지정하는 구성 섹션입니다.</span><span class="sxs-lookup"><span data-stu-id="aee72-102">A configuration section that specifies a list of contract type names, which are the contract names of the services being searched for, and the criteria typically used when searching for a service.</span></span> <span data-ttu-id="aee72-103">둘 이상의 계약 이름이 지정되면 모든 계약과 일치하는 서비스 엔드포인트만 응답합니다.</span><span class="sxs-lookup"><span data-stu-id="aee72-103">If more than one contract name is specified, only service endpoints matching ALL contracts will reply.</span></span> <span data-ttu-id="aee72-104">WCF (Windows Communication Foundation)에서 끝점은 하나의 계약만 지원할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="aee72-104">Note that in Windows Communication Foundation (WCF), an endpoint can only support one contract.</span></span>  
  
 <span data-ttu-id="aee72-105">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="aee72-105">\<system.ServiceModel></span></span>  
<span data-ttu-id="aee72-106">\<standardEndpoints></span><span class="sxs-lookup"><span data-stu-id="aee72-106">\<standardEndpoints></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="aee72-107">구문</span><span class="sxs-lookup"><span data-stu-id="aee72-107">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="aee72-108">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="aee72-108">Attributes and Elements</span></span>  
 <span data-ttu-id="aee72-109">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="aee72-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="aee72-110">특성</span><span class="sxs-lookup"><span data-stu-id="aee72-110">Attributes</span></span>  
 <span data-ttu-id="aee72-111">없음</span><span class="sxs-lookup"><span data-stu-id="aee72-111">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="aee72-112">자식 요소</span><span class="sxs-lookup"><span data-stu-id="aee72-112">Child Elements</span></span>  
  
|<span data-ttu-id="aee72-113">요소</span><span class="sxs-lookup"><span data-stu-id="aee72-113">Element</span></span>|<span data-ttu-id="aee72-114">설명</span><span class="sxs-lookup"><span data-stu-id="aee72-114">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="aee72-115">\<add></span><span class="sxs-lookup"><span data-stu-id="aee72-115">\<add></span></span>](contracttypenames.md)|<span data-ttu-id="aee72-116">계약 형식 이름은 서비스를 검색할 때 일반적으로 사용되는 조건 집합을 나타나는 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="aee72-116">A contract type name is a property that refers to the set of criteria typically used when searching for a service.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="aee72-117">부모 요소</span><span class="sxs-lookup"><span data-stu-id="aee72-117">Parent Elements</span></span>  
  
|<span data-ttu-id="aee72-118">요소</span><span class="sxs-lookup"><span data-stu-id="aee72-118">Element</span></span>|<span data-ttu-id="aee72-119">Description</span><span class="sxs-lookup"><span data-stu-id="aee72-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="aee72-120">\<findCriteria></span><span class="sxs-lookup"><span data-stu-id="aee72-120">\<findCriteria></span></span>](findcriteria.md)|<span data-ttu-id="aee72-121">클라이언트 애플리케이션에서 검색 서비스를 찾기 위해 사용하는 조건 집합을 제공하는 구성 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="aee72-121">A configuration element that supplies a set of criteria used by a client application to search for a discovery service.</span></span> <span data-ttu-id="aee72-122">기준은 검색 조건 (찾으려는 서비스 지정)으로 그룹화 하 고 종료 조건 (검색이 마지막으로 수행 되는 시간)을 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="aee72-122">Criteria can be grouped into search criteria (specifying what services you’re looking for) and find termination criteria (how long the search should last).</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="aee72-123">참고자료</span><span class="sxs-lookup"><span data-stu-id="aee72-123">See also</span></span>

- <xref:System.ServiceModel.Discovery.FindCriteria>
- <xref:System.ServiceModel.Discovery.Configuration.FindCriteriaElement>
- <xref:System.ServiceModel.Discovery.Configuration.ContractTypeNameElementCollection>
