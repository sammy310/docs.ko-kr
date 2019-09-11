---
title: <contractTypeNames>의 <add>
ms.date: 03/30/2017
ms.assetid: 03aff6be-5dfb-4a64-ada3-e36227cd43c7
ms.openlocfilehash: 696752470aa39c2bcc66a1337f84119031742ae9
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/10/2019
ms.locfileid: "70850538"
---
# <a name="add-of-contracttypenames"></a><span data-ttu-id="e53f2-102">\<\<contractTypeNames > > 추가</span><span class="sxs-lookup"><span data-stu-id="e53f2-102">\<add> of \<contractTypeNames></span></span>
<span data-ttu-id="e53f2-103">검색할 서비스의 계약 이름 및 서비스를 검색할 때 일반적으로 사용되는 기준을 지정하는 구성 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="e53f2-103">A configuration element that specifies the contract name of the services being searched for, and the criteria typically used when searching for a service.</span></span> <span data-ttu-id="e53f2-104">둘 이상의 계약 이름이 지정되면 모든 계약과 일치하는 서비스 엔드포인트만 응답합니다.</span><span class="sxs-lookup"><span data-stu-id="e53f2-104">If more than one contract name is specified, only service endpoints matching ALL contracts will reply.</span></span> <span data-ttu-id="e53f2-105">WCF (Windows Communication Foundation)에서 끝점은 하나의 계약만 지원할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e53f2-105">Note that in Windows Communication Foundation (WCF), an endpoint can only support one contract.</span></span>  
  
<span data-ttu-id="e53f2-106">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="e53f2-106">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="e53f2-107">&nbsp;&nbsp;[ **\<System.servicemodel >** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="e53f2-107">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="e53f2-108">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<standardEndpoints >** ](standardendpoints.md)</span><span class="sxs-lookup"><span data-stu-id="e53f2-108">&nbsp;&nbsp;&nbsp;&nbsp;[**\<standardEndpoints>**](standardendpoints.md)</span></span>\
<span data-ttu-id="e53f2-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<dynamicEndpoint >** ](dynamicendpoint.md)</span><span class="sxs-lookup"><span data-stu-id="e53f2-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<dynamicEndpoint>**](dynamicendpoint.md)</span></span>\
<span data-ttu-id="e53f2-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<standardEndpoint >** </span><span class="sxs-lookup"><span data-stu-id="e53f2-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<standardEndpoint>**</span></span>\
<span data-ttu-id="e53f2-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<discoveryClientSettings >** ](discoveryclientsettings.md)</span><span class="sxs-lookup"><span data-stu-id="e53f2-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<discoveryClientSettings>**](discoveryclientsettings.md)</span></span>\
<span data-ttu-id="e53f2-112">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<findCriteria >** ](findcriteria.md)</span><span class="sxs-lookup"><span data-stu-id="e53f2-112">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<findCriteria>**](findcriteria.md)</span></span>\
<span data-ttu-id="e53f2-113">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<contractTypeNames >** ](contracttypenames.md)</span><span class="sxs-lookup"><span data-stu-id="e53f2-113">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<contractTypeNames>**](contracttypenames.md)</span></span>\
<span data-ttu-id="e53f2-114">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<> 추가**</span><span class="sxs-lookup"><span data-stu-id="e53f2-114">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e53f2-115">구문</span><span class="sxs-lookup"><span data-stu-id="e53f2-115">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e53f2-116">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="e53f2-116">Attributes and Elements</span></span>  
 <span data-ttu-id="e53f2-117">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="e53f2-117">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e53f2-118">특성</span><span class="sxs-lookup"><span data-stu-id="e53f2-118">Attributes</span></span>  
  
|<span data-ttu-id="e53f2-119">특성</span><span class="sxs-lookup"><span data-stu-id="e53f2-119">Attribute</span></span>|<span data-ttu-id="e53f2-120">설명</span><span class="sxs-lookup"><span data-stu-id="e53f2-120">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="e53f2-121">name</span><span class="sxs-lookup"><span data-stu-id="e53f2-121">name</span></span>|<span data-ttu-id="e53f2-122">계약 형식의 이름을 지정하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="e53f2-122">A string that specifies the name of the contract type.</span></span>|  
|<span data-ttu-id="e53f2-123">namespace</span><span class="sxs-lookup"><span data-stu-id="e53f2-123">namespace</span></span>|<span data-ttu-id="e53f2-124">계약 형식의 네임스페이스를 지정하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="e53f2-124">A string that specifies the namespace of the contract type.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="e53f2-125">자식 요소</span><span class="sxs-lookup"><span data-stu-id="e53f2-125">Child Elements</span></span>  
 <span data-ttu-id="e53f2-126">없음</span><span class="sxs-lookup"><span data-stu-id="e53f2-126">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="e53f2-127">부모 요소</span><span class="sxs-lookup"><span data-stu-id="e53f2-127">Parent Elements</span></span>  
  
|<span data-ttu-id="e53f2-128">요소</span><span class="sxs-lookup"><span data-stu-id="e53f2-128">Element</span></span>|<span data-ttu-id="e53f2-129">설명</span><span class="sxs-lookup"><span data-stu-id="e53f2-129">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="e53f2-130">\<contractTypeNames></span><span class="sxs-lookup"><span data-stu-id="e53f2-130">\<contractTypeNames></span></span>](contracttypenames.md)|<span data-ttu-id="e53f2-131">계약 형식 이름의 컬렉션입니다.</span><span class="sxs-lookup"><span data-stu-id="e53f2-131">A collection of contract type names.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="e53f2-132">참고자료</span><span class="sxs-lookup"><span data-stu-id="e53f2-132">See also</span></span>

- <xref:System.ServiceModel.Discovery.FindCriteria>
- <xref:System.ServiceModel.Discovery.Configuration.FindCriteriaElement>
- <xref:System.ServiceModel.Discovery.Configuration.ContractTypeNameElement>
