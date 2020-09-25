---
title: <filterTable>
ms.date: 03/30/2017
ms.assetid: e9f05441-3ad1-49b9-a267-71724aa094b4
ms.openlocfilehash: fb36feedc5fb2cbdf3827cbe44242c7ac6ab8a9b
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/24/2020
ms.locfileid: "91185693"
---
# \<filterTable>

<span data-ttu-id="6f0f0-101">메시지를 평가할 필터 목록 및 필터가 true로 평가될 경우 메시지를 라우팅할 클라이언트 엔드포인트를 포함하는 라우팅 테이블을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="6f0f0-101">Represents a routing table that contains a list of filters to evaluate messages against and the client endpoint to route messages to if the filter evaluates to true.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<routing>**](routing.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<filterTables>**](filtertables.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<filterTable>**  
  
## <a name="syntax"></a><span data-ttu-id="6f0f0-102">구문</span><span class="sxs-lookup"><span data-stu-id="6f0f0-102">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="6f0f0-103">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="6f0f0-103">Attributes and Elements</span></span>  

 <span data-ttu-id="6f0f0-104">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="6f0f0-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="6f0f0-105">특성</span><span class="sxs-lookup"><span data-stu-id="6f0f0-105">Attributes</span></span>  
  
|<span data-ttu-id="6f0f0-106">요소</span><span class="sxs-lookup"><span data-stu-id="6f0f0-106">Element</span></span>|<span data-ttu-id="6f0f0-107">Description</span><span class="sxs-lookup"><span data-stu-id="6f0f0-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="6f0f0-108">name</span><span class="sxs-lookup"><span data-stu-id="6f0f0-108">name</span></span>|<span data-ttu-id="6f0f0-109">이 구성 요소의 고유 이름을 포함하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="6f0f0-109">A string that contains the unique name of this configuration element.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="6f0f0-110">자식 요소</span><span class="sxs-lookup"><span data-stu-id="6f0f0-110">Child Elements</span></span>  
  
|<span data-ttu-id="6f0f0-111">요소</span><span class="sxs-lookup"><span data-stu-id="6f0f0-111">Element</span></span>|<span data-ttu-id="6f0f0-112">설명</span><span class="sxs-lookup"><span data-stu-id="6f0f0-112">Description</span></span>|  
|-------------|-----------------|  
|[\<filters>](filters-of-routing.md)|<span data-ttu-id="6f0f0-113">필터가 일치할 때 메시지를 보내기 위한 라우팅 필터와 대상 엔드포인트 간의 매핑입니다.</span><span class="sxs-lookup"><span data-stu-id="6f0f0-113">Mappings between the routing filters and the target endpoints to send messages to when the filter matches.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="6f0f0-114">부모 요소</span><span class="sxs-lookup"><span data-stu-id="6f0f0-114">Parent Elements</span></span>  
  
|<span data-ttu-id="6f0f0-115">요소</span><span class="sxs-lookup"><span data-stu-id="6f0f0-115">Element</span></span>|<span data-ttu-id="6f0f0-116">설명</span><span class="sxs-lookup"><span data-stu-id="6f0f0-116">Description</span></span>|  
|-------------|-----------------|  
|[\<routing>](routing.md)|<span data-ttu-id="6f0f0-117">라우팅 테이블을 포함하는 구성 섹션입니다.</span><span class="sxs-lookup"><span data-stu-id="6f0f0-117">A configuration section that contains routing tables.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="6f0f0-118">참고 항목</span><span class="sxs-lookup"><span data-stu-id="6f0f0-118">See also</span></span>

- <xref:System.ServiceModel.Routing.Configuration.RoutingSection?displayProperty=nameWithType>
