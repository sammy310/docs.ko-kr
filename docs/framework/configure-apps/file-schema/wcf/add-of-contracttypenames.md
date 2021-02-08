---
description: '다음에 대 한 자세한 정보:: <add><contractTypeNames>'
title: <contractTypeNames>의 <add>
ms.date: 03/30/2017
ms.assetid: 03aff6be-5dfb-4a64-ada3-e36227cd43c7
ms.openlocfilehash: 0708aa277b4250cb4134a98ddf7af661840981a8
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99803999"
---
# <a name="add-of-contracttypenames"></a><span data-ttu-id="0bce2-103">\<contractTypeNames>의 \<add></span><span class="sxs-lookup"><span data-stu-id="0bce2-103">\<add> of \<contractTypeNames></span></span>

<span data-ttu-id="0bce2-104">검색할 서비스의 계약 이름 및 서비스를 검색할 때 일반적으로 사용되는 기준을 지정하는 구성 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="0bce2-104">A configuration element that specifies the contract name of the services being searched for, and the criteria typically used when searching for a service.</span></span> <span data-ttu-id="0bce2-105">둘 이상의 계약 이름이 지정되면 모든 계약과 일치하는 서비스 엔드포인트만 응답합니다.</span><span class="sxs-lookup"><span data-stu-id="0bce2-105">If more than one contract name is specified, only service endpoints matching ALL contracts will reply.</span></span> <span data-ttu-id="0bce2-106">WCF (Windows Communication Foundation)에서 끝점은 하나의 계약만 지원할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0bce2-106">Note that in Windows Communication Foundation (WCF), an endpoint can only support one contract.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<standardEndpoints>**](standardendpoints.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<dynamicEndpoint>**](dynamicendpoint.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<standardEndpoint>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<discoveryClientSettings>**](discoveryclientsettings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<findCriteria>**](findcriteria.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<contractTypeNames>**](contracttypenames.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**  
  
## <a name="syntax"></a><span data-ttu-id="0bce2-107">구문</span><span class="sxs-lookup"><span data-stu-id="0bce2-107">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="0bce2-108">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="0bce2-108">Attributes and Elements</span></span>  

 <span data-ttu-id="0bce2-109">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="0bce2-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="0bce2-110">특성</span><span class="sxs-lookup"><span data-stu-id="0bce2-110">Attributes</span></span>  
  
|<span data-ttu-id="0bce2-111">attribute</span><span class="sxs-lookup"><span data-stu-id="0bce2-111">Attribute</span></span>|<span data-ttu-id="0bce2-112">설명</span><span class="sxs-lookup"><span data-stu-id="0bce2-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="0bce2-113">name</span><span class="sxs-lookup"><span data-stu-id="0bce2-113">name</span></span>|<span data-ttu-id="0bce2-114">계약 형식의 이름을 지정하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="0bce2-114">A string that specifies the name of the contract type.</span></span>|  
|<span data-ttu-id="0bce2-115">네임스페이스</span><span class="sxs-lookup"><span data-stu-id="0bce2-115">namespace</span></span>|<span data-ttu-id="0bce2-116">계약 형식의 네임스페이스를 지정하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="0bce2-116">A string that specifies the namespace of the contract type.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="0bce2-117">자식 요소</span><span class="sxs-lookup"><span data-stu-id="0bce2-117">Child Elements</span></span>  

 <span data-ttu-id="0bce2-118">없음</span><span class="sxs-lookup"><span data-stu-id="0bce2-118">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="0bce2-119">부모 요소</span><span class="sxs-lookup"><span data-stu-id="0bce2-119">Parent Elements</span></span>  
  
|<span data-ttu-id="0bce2-120">요소</span><span class="sxs-lookup"><span data-stu-id="0bce2-120">Element</span></span>|<span data-ttu-id="0bce2-121">설명</span><span class="sxs-lookup"><span data-stu-id="0bce2-121">Description</span></span>|  
|-------------|-----------------|  
|[\<contractTypeNames>](contracttypenames.md)|<span data-ttu-id="0bce2-122">계약 형식 이름의 컬렉션입니다.</span><span class="sxs-lookup"><span data-stu-id="0bce2-122">A collection of contract type names.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="0bce2-123">참고 항목</span><span class="sxs-lookup"><span data-stu-id="0bce2-123">See also</span></span>

- <xref:System.ServiceModel.Discovery.FindCriteria>
- <xref:System.ServiceModel.Discovery.Configuration.FindCriteriaElement>
- <xref:System.ServiceModel.Discovery.Configuration.ContractTypeNameElement>
