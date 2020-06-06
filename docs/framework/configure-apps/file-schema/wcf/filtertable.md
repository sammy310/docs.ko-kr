---
title: <filterTable>
ms.date: 03/30/2017
ms.assetid: e9f05441-3ad1-49b9-a267-71724aa094b4
ms.openlocfilehash: 918a365004efea82f4ef4c8868f6821d4bb6da18
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/06/2020
ms.locfileid: "70855184"
---
# \<filterTable>
<span data-ttu-id="6412e-101">메시지를 평가할 필터 목록 및 필터가 true로 평가될 경우 메시지를 라우팅할 클라이언트 엔드포인트를 포함하는 라우팅 테이블을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="6412e-101">Represents a routing table that contains a list of filters to evaluate messages against and the client endpoint to route messages to if the filter evaluates to true.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<routing>**](routing.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<filterTables>**](filtertables.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<filterTable>**  
  
## <a name="syntax"></a><span data-ttu-id="6412e-102">구문</span><span class="sxs-lookup"><span data-stu-id="6412e-102">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="6412e-103">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="6412e-103">Attributes and Elements</span></span>  
 <span data-ttu-id="6412e-104">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="6412e-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="6412e-105">특성</span><span class="sxs-lookup"><span data-stu-id="6412e-105">Attributes</span></span>  
  
|<span data-ttu-id="6412e-106">요소</span><span class="sxs-lookup"><span data-stu-id="6412e-106">Element</span></span>|<span data-ttu-id="6412e-107">Description</span><span class="sxs-lookup"><span data-stu-id="6412e-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="6412e-108">name</span><span class="sxs-lookup"><span data-stu-id="6412e-108">name</span></span>|<span data-ttu-id="6412e-109">이 구성 요소의 고유 이름을 포함하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="6412e-109">A string that contains the unique name of this configuration element.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="6412e-110">자식 요소</span><span class="sxs-lookup"><span data-stu-id="6412e-110">Child Elements</span></span>  
  
|<span data-ttu-id="6412e-111">요소</span><span class="sxs-lookup"><span data-stu-id="6412e-111">Element</span></span>|<span data-ttu-id="6412e-112">Description</span><span class="sxs-lookup"><span data-stu-id="6412e-112">Description</span></span>|  
|-------------|-----------------|  
|[\<filters>](filters-of-routing.md)|<span data-ttu-id="6412e-113">필터가 일치할 때 메시지를 보내기 위한 라우팅 필터와 대상 엔드포인트 간의 매핑입니다.</span><span class="sxs-lookup"><span data-stu-id="6412e-113">Mappings between the routing filters and the target endpoints to send messages to when the filter matches.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="6412e-114">부모 요소</span><span class="sxs-lookup"><span data-stu-id="6412e-114">Parent Elements</span></span>  
  
|<span data-ttu-id="6412e-115">요소</span><span class="sxs-lookup"><span data-stu-id="6412e-115">Element</span></span>|<span data-ttu-id="6412e-116">Description</span><span class="sxs-lookup"><span data-stu-id="6412e-116">Description</span></span>|  
|-------------|-----------------|  
|[\<routing>](routing.md)|<span data-ttu-id="6412e-117">라우팅 테이블을 포함하는 구성 섹션입니다.</span><span class="sxs-lookup"><span data-stu-id="6412e-117">A configuration section that contains routing tables.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="6412e-118">참고 항목</span><span class="sxs-lookup"><span data-stu-id="6412e-118">See also</span></span>

- <xref:System.ServiceModel.Routing.Configuration.RoutingSection?displayProperty=nameWithType>
