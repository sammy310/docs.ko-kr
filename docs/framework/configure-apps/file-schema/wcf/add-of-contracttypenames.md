---
title: <contractTypeNames>의 <add>
ms.date: 03/30/2017
ms.assetid: 03aff6be-5dfb-4a64-ada3-e36227cd43c7
ms.openlocfilehash: 696752470aa39c2bcc66a1337f84119031742ae9
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/06/2020
ms.locfileid: "70850538"
---
# <a name="add-of-contracttypenames"></a><span data-ttu-id="7b924-102">\<contractTypeNames>의 \<add></span><span class="sxs-lookup"><span data-stu-id="7b924-102">\<add> of \<contractTypeNames></span></span>
<span data-ttu-id="7b924-103">검색할 서비스의 계약 이름 및 서비스를 검색할 때 일반적으로 사용되는 기준을 지정하는 구성 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="7b924-103">A configuration element that specifies the contract name of the services being searched for, and the criteria typically used when searching for a service.</span></span> <span data-ttu-id="7b924-104">둘 이상의 계약 이름이 지정되면 모든 계약과 일치하는 서비스 엔드포인트만 응답합니다.</span><span class="sxs-lookup"><span data-stu-id="7b924-104">If more than one contract name is specified, only service endpoints matching ALL contracts will reply.</span></span> <span data-ttu-id="7b924-105">WCF (Windows Communication Foundation)에서 끝점은 하나의 계약만 지원할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7b924-105">Note that in Windows Communication Foundation (WCF), an endpoint can only support one contract.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<standardEndpoints>**](standardendpoints.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<dynamicEndpoint>**](dynamicendpoint.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<standardEndpoint>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<discoveryClientSettings>**](discoveryclientsettings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<findCriteria>**](findcriteria.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<contractTypeNames>**](contracttypenames.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**  
  
## <a name="syntax"></a><span data-ttu-id="7b924-106">구문</span><span class="sxs-lookup"><span data-stu-id="7b924-106">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="7b924-107">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="7b924-107">Attributes and Elements</span></span>  
 <span data-ttu-id="7b924-108">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="7b924-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="7b924-109">특성</span><span class="sxs-lookup"><span data-stu-id="7b924-109">Attributes</span></span>  
  
|<span data-ttu-id="7b924-110">attribute</span><span class="sxs-lookup"><span data-stu-id="7b924-110">Attribute</span></span>|<span data-ttu-id="7b924-111">Description</span><span class="sxs-lookup"><span data-stu-id="7b924-111">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="7b924-112">name</span><span class="sxs-lookup"><span data-stu-id="7b924-112">name</span></span>|<span data-ttu-id="7b924-113">계약 형식의 이름을 지정하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="7b924-113">A string that specifies the name of the contract type.</span></span>|  
|<span data-ttu-id="7b924-114">namespace</span><span class="sxs-lookup"><span data-stu-id="7b924-114">namespace</span></span>|<span data-ttu-id="7b924-115">계약 형식의 네임스페이스를 지정하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="7b924-115">A string that specifies the namespace of the contract type.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="7b924-116">자식 요소</span><span class="sxs-lookup"><span data-stu-id="7b924-116">Child Elements</span></span>  
 <span data-ttu-id="7b924-117">None</span><span class="sxs-lookup"><span data-stu-id="7b924-117">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="7b924-118">부모 요소</span><span class="sxs-lookup"><span data-stu-id="7b924-118">Parent Elements</span></span>  
  
|<span data-ttu-id="7b924-119">요소</span><span class="sxs-lookup"><span data-stu-id="7b924-119">Element</span></span>|<span data-ttu-id="7b924-120">Description</span><span class="sxs-lookup"><span data-stu-id="7b924-120">Description</span></span>|  
|-------------|-----------------|  
|[\<contractTypeNames>](contracttypenames.md)|<span data-ttu-id="7b924-121">계약 형식 이름의 컬렉션입니다.</span><span class="sxs-lookup"><span data-stu-id="7b924-121">A collection of contract type names.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="7b924-122">참고 항목</span><span class="sxs-lookup"><span data-stu-id="7b924-122">See also</span></span>

- <xref:System.ServiceModel.Discovery.FindCriteria>
- <xref:System.ServiceModel.Discovery.Configuration.FindCriteriaElement>
- <xref:System.ServiceModel.Discovery.Configuration.ContractTypeNameElement>
