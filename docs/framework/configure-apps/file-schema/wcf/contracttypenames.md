---
description: 다음에 대해 자세히 알아보세요. <contractTypeNames>
title: <contractTypeNames>
ms.date: 03/30/2017
ms.assetid: 5ec5efc6-87f8-4160-9be0-dcd2e01df3df
ms.openlocfilehash: 7521b16c097a8df75819654525c0663124a1ebd0
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99754448"
---
# \<contractTypeNames>

<span data-ttu-id="fd218-102">검색할 서비스의 계약 이름인 계약 형식 이름 목록 및 서비스를 검색할 때 일반적으로 사용되는 기준을 지정하는 구성 섹션입니다.</span><span class="sxs-lookup"><span data-stu-id="fd218-102">A configuration section that specifies a list of contract type names, which are the contract names of the services being searched for, and the criteria typically used when searching for a service.</span></span> <span data-ttu-id="fd218-103">둘 이상의 계약 이름이 지정되면 모든 계약과 일치하는 서비스 엔드포인트만 응답합니다.</span><span class="sxs-lookup"><span data-stu-id="fd218-103">If more than one contract name is specified, only service endpoints matching ALL contracts will reply.</span></span> <span data-ttu-id="fd218-104">WCF (Windows Communication Foundation)에서 끝점은 하나의 계약만 지원할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fd218-104">Note that in Windows Communication Foundation (WCF), an endpoint can only support one contract.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<standardEndpoints>**](standardendpoints.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<dynamicEndpoint>**](dynamicendpoint.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<standardEndpoint>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<discoveryClientSettings>**](discoveryclientsettings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<findCriteria>**](findcriteria.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<contractTypeNames>**  
  
## <a name="syntax"></a><span data-ttu-id="fd218-105">구문</span><span class="sxs-lookup"><span data-stu-id="fd218-105">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="fd218-106">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="fd218-106">Attributes and Elements</span></span>  

 <span data-ttu-id="fd218-107">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="fd218-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="fd218-108">특성</span><span class="sxs-lookup"><span data-stu-id="fd218-108">Attributes</span></span>  

 <span data-ttu-id="fd218-109">없음</span><span class="sxs-lookup"><span data-stu-id="fd218-109">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="fd218-110">자식 요소</span><span class="sxs-lookup"><span data-stu-id="fd218-110">Child Elements</span></span>  
  
|<span data-ttu-id="fd218-111">요소</span><span class="sxs-lookup"><span data-stu-id="fd218-111">Element</span></span>|<span data-ttu-id="fd218-112">설명</span><span class="sxs-lookup"><span data-stu-id="fd218-112">Description</span></span>|  
|-------------|-----------------|  
|[\<add>](contracttypenames.md)|<span data-ttu-id="fd218-113">계약 형식 이름은 서비스를 검색할 때 일반적으로 사용되는 조건 집합을 나타나는 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="fd218-113">A contract type name is a property that refers to the set of criteria typically used when searching for a service.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="fd218-114">부모 요소</span><span class="sxs-lookup"><span data-stu-id="fd218-114">Parent Elements</span></span>  
  
|<span data-ttu-id="fd218-115">요소</span><span class="sxs-lookup"><span data-stu-id="fd218-115">Element</span></span>|<span data-ttu-id="fd218-116">설명</span><span class="sxs-lookup"><span data-stu-id="fd218-116">Description</span></span>|  
|-------------|-----------------|  
|[\<findCriteria>](findcriteria.md)|<span data-ttu-id="fd218-117">클라이언트 애플리케이션에서 검색 서비스를 찾기 위해 사용하는 조건 집합을 제공하는 구성 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="fd218-117">A configuration element that supplies a set of criteria used by a client application to search for a discovery service.</span></span> <span data-ttu-id="fd218-118">기준을 검색 조건(찾으려는 서비스 지정) 및 찾기 종료 조건(검색 지속 기간)으로 그룹화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fd218-118">Criteria can be grouped into search criteria (specifying what services you’re looking for) and find termination criteria (how long the search should last).</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="fd218-119">참고 항목</span><span class="sxs-lookup"><span data-stu-id="fd218-119">See also</span></span>

- <xref:System.ServiceModel.Discovery.FindCriteria>
- <xref:System.ServiceModel.Discovery.Configuration.FindCriteriaElement>
- <xref:System.ServiceModel.Discovery.Configuration.ContractTypeNameElementCollection>
