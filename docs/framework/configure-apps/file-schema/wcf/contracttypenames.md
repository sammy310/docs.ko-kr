---
title: <contractTypeNames>
ms.date: 03/30/2017
ms.assetid: 5ec5efc6-87f8-4160-9be0-dcd2e01df3df
ms.openlocfilehash: c67e5b9e82b96e27ce73512680bd4236b26ef4dd
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/10/2019
ms.locfileid: "70855443"
---
# <a name="contracttypenames"></a><span data-ttu-id="075d2-101">\<contractTypeNames></span><span class="sxs-lookup"><span data-stu-id="075d2-101">\<contractTypeNames></span></span>
<span data-ttu-id="075d2-102">검색할 서비스의 계약 이름인 계약 형식 이름 목록 및 서비스를 검색할 때 일반적으로 사용되는 기준을 지정하는 구성 섹션입니다.</span><span class="sxs-lookup"><span data-stu-id="075d2-102">A configuration section that specifies a list of contract type names, which are the contract names of the services being searched for, and the criteria typically used when searching for a service.</span></span> <span data-ttu-id="075d2-103">둘 이상의 계약 이름이 지정되면 모든 계약과 일치하는 서비스 엔드포인트만 응답합니다.</span><span class="sxs-lookup"><span data-stu-id="075d2-103">If more than one contract name is specified, only service endpoints matching ALL contracts will reply.</span></span> <span data-ttu-id="075d2-104">WCF (Windows Communication Foundation)에서 끝점은 하나의 계약만 지원할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="075d2-104">Note that in Windows Communication Foundation (WCF), an endpoint can only support one contract.</span></span>  
  
<span data-ttu-id="075d2-105">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="075d2-105">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="075d2-106">&nbsp;&nbsp;[ **\<System.servicemodel >** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="075d2-106">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="075d2-107">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<standardEndpoints >** ](standardendpoints.md)</span><span class="sxs-lookup"><span data-stu-id="075d2-107">&nbsp;&nbsp;&nbsp;&nbsp;[**\<standardEndpoints>**](standardendpoints.md)</span></span>\
<span data-ttu-id="075d2-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<dynamicEndpoint >** ](dynamicendpoint.md)</span><span class="sxs-lookup"><span data-stu-id="075d2-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<dynamicEndpoint>**](dynamicendpoint.md)</span></span>\
<span data-ttu-id="075d2-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<standardEndpoint >** </span><span class="sxs-lookup"><span data-stu-id="075d2-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<standardEndpoint>**</span></span>\
<span data-ttu-id="075d2-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<discoveryClientSettings >** ](discoveryclientsettings.md)</span><span class="sxs-lookup"><span data-stu-id="075d2-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<discoveryClientSettings>**](discoveryclientsettings.md)</span></span>\
<span data-ttu-id="075d2-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<findCriteria >** ](findcriteria.md)</span><span class="sxs-lookup"><span data-stu-id="075d2-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<findCriteria>**](findcriteria.md)</span></span>\
<span data-ttu-id="075d2-112">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<contractTypeNames >**</span><span class="sxs-lookup"><span data-stu-id="075d2-112">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<contractTypeNames>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="075d2-113">구문</span><span class="sxs-lookup"><span data-stu-id="075d2-113">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="075d2-114">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="075d2-114">Attributes and Elements</span></span>  
 <span data-ttu-id="075d2-115">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="075d2-115">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="075d2-116">특성</span><span class="sxs-lookup"><span data-stu-id="075d2-116">Attributes</span></span>  
 <span data-ttu-id="075d2-117">없음</span><span class="sxs-lookup"><span data-stu-id="075d2-117">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="075d2-118">자식 요소</span><span class="sxs-lookup"><span data-stu-id="075d2-118">Child Elements</span></span>  
  
|<span data-ttu-id="075d2-119">요소</span><span class="sxs-lookup"><span data-stu-id="075d2-119">Element</span></span>|<span data-ttu-id="075d2-120">설명</span><span class="sxs-lookup"><span data-stu-id="075d2-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="075d2-121">\<add></span><span class="sxs-lookup"><span data-stu-id="075d2-121">\<add></span></span>](contracttypenames.md)|<span data-ttu-id="075d2-122">계약 형식 이름은 서비스를 검색할 때 일반적으로 사용되는 조건 집합을 나타나는 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="075d2-122">A contract type name is a property that refers to the set of criteria typically used when searching for a service.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="075d2-123">부모 요소</span><span class="sxs-lookup"><span data-stu-id="075d2-123">Parent Elements</span></span>  
  
|<span data-ttu-id="075d2-124">요소</span><span class="sxs-lookup"><span data-stu-id="075d2-124">Element</span></span>|<span data-ttu-id="075d2-125">Description</span><span class="sxs-lookup"><span data-stu-id="075d2-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="075d2-126">\<findCriteria></span><span class="sxs-lookup"><span data-stu-id="075d2-126">\<findCriteria></span></span>](findcriteria.md)|<span data-ttu-id="075d2-127">클라이언트 애플리케이션에서 검색 서비스를 찾기 위해 사용하는 조건 집합을 제공하는 구성 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="075d2-127">A configuration element that supplies a set of criteria used by a client application to search for a discovery service.</span></span> <span data-ttu-id="075d2-128">기준은 검색 조건 (찾으려는 서비스 지정)으로 그룹화 하 고 종료 조건 (검색이 마지막으로 수행 되는 시간)을 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="075d2-128">Criteria can be grouped into search criteria (specifying what services you’re looking for) and find termination criteria (how long the search should last).</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="075d2-129">참고자료</span><span class="sxs-lookup"><span data-stu-id="075d2-129">See also</span></span>

- <xref:System.ServiceModel.Discovery.FindCriteria>
- <xref:System.ServiceModel.Discovery.Configuration.FindCriteriaElement>
- <xref:System.ServiceModel.Discovery.Configuration.ContractTypeNameElementCollection>
