---
description: 다음에 대해 자세히 알아보세요. <filterTable>
title: <filterTable>
ms.date: 03/30/2017
ms.assetid: e9f05441-3ad1-49b9-a267-71724aa094b4
ms.openlocfilehash: 2051bb0e778e5676f39d91b7d7ba415fd7e523af
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99782041"
---
# \<filterTable>

<span data-ttu-id="36888-102">메시지를 평가할 필터 목록 및 필터가 true로 평가될 경우 메시지를 라우팅할 클라이언트 엔드포인트를 포함하는 라우팅 테이블을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="36888-102">Represents a routing table that contains a list of filters to evaluate messages against and the client endpoint to route messages to if the filter evaluates to true.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<routing>**](routing.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<filterTables>**](filtertables.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<filterTable>**  
  
## <a name="syntax"></a><span data-ttu-id="36888-103">구문</span><span class="sxs-lookup"><span data-stu-id="36888-103">Syntax</span></span>  
  
```xml  
<routing>
  <filterTables>
     name="String">
      <entries>
        <add backupList="String"
             endpointName="String"
             filterName="String"
             priority="Integer" />
      </entries>
    </filterTable>
  </filterTables>
</routing>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="36888-104">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="36888-104">Attributes and Elements</span></span>  

 <span data-ttu-id="36888-105">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="36888-105">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="36888-106">특성</span><span class="sxs-lookup"><span data-stu-id="36888-106">Attributes</span></span>  
  
|<span data-ttu-id="36888-107">요소</span><span class="sxs-lookup"><span data-stu-id="36888-107">Element</span></span>|<span data-ttu-id="36888-108">설명</span><span class="sxs-lookup"><span data-stu-id="36888-108">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="36888-109">name</span><span class="sxs-lookup"><span data-stu-id="36888-109">name</span></span>|<span data-ttu-id="36888-110">이 구성 요소의 고유 이름을 포함하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="36888-110">A string that contains the unique name of this configuration element.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="36888-111">자식 요소</span><span class="sxs-lookup"><span data-stu-id="36888-111">Child Elements</span></span>  
  
|<span data-ttu-id="36888-112">요소</span><span class="sxs-lookup"><span data-stu-id="36888-112">Element</span></span>|<span data-ttu-id="36888-113">설명</span><span class="sxs-lookup"><span data-stu-id="36888-113">Description</span></span>|  
|-------------|-----------------|  
|[\<filters>](filters-of-routing.md)|<span data-ttu-id="36888-114">필터가 일치할 때 메시지를 보내기 위한 라우팅 필터와 대상 엔드포인트 간의 매핑입니다.</span><span class="sxs-lookup"><span data-stu-id="36888-114">Mappings between the routing filters and the target endpoints to send messages to when the filter matches.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="36888-115">부모 요소</span><span class="sxs-lookup"><span data-stu-id="36888-115">Parent Elements</span></span>  
  
|<span data-ttu-id="36888-116">요소</span><span class="sxs-lookup"><span data-stu-id="36888-116">Element</span></span>|<span data-ttu-id="36888-117">설명</span><span class="sxs-lookup"><span data-stu-id="36888-117">Description</span></span>|  
|-------------|-----------------|  
|[\<routing>](routing.md)|<span data-ttu-id="36888-118">라우팅 테이블을 포함하는 구성 섹션입니다.</span><span class="sxs-lookup"><span data-stu-id="36888-118">A configuration section that contains routing tables.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="36888-119">참고 항목</span><span class="sxs-lookup"><span data-stu-id="36888-119">See also</span></span>

- <xref:System.ServiceModel.Routing.Configuration.RoutingSection?displayProperty=nameWithType>
