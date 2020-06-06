---
title: <filterTables>
ms.date: 03/30/2017
ms.assetid: 41f1ac35-f559-473a-b2c3-8cc83a6a3831
ms.openlocfilehash: c68479737cefe542a10a404a8b31a4820a430ffb
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/06/2020
ms.locfileid: "70855205"
---
# \<filterTables>
<span data-ttu-id="cc5e8-101">필터가 일치할 때 메시지를 보내기 위한 라우팅 필터와 대상 엔드포인트 간의 매핑을 포함하는 라우팅 테이블을 정의하기 위한 구성 섹션을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="cc5e8-101">Represents a configuration section for defining routing tables that contain mappings between the routing filters and the target endpoints to send messages to when the filter matches.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<routing>**](routing.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<filterTables>**  
  
## <a name="syntax"></a><span data-ttu-id="cc5e8-102">구문</span><span class="sxs-lookup"><span data-stu-id="cc5e8-102">Syntax</span></span>  
  
```xml  
<routing>
  <filterTables>
    <filterTable name="String">
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="cc5e8-103">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="cc5e8-103">Attributes and Elements</span></span>  
 <span data-ttu-id="cc5e8-104">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="cc5e8-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="cc5e8-105">특성</span><span class="sxs-lookup"><span data-stu-id="cc5e8-105">Attributes</span></span>  
 <span data-ttu-id="cc5e8-106">없음</span><span class="sxs-lookup"><span data-stu-id="cc5e8-106">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="cc5e8-107">자식 요소</span><span class="sxs-lookup"><span data-stu-id="cc5e8-107">Child Elements</span></span>  
  
|<span data-ttu-id="cc5e8-108">요소</span><span class="sxs-lookup"><span data-stu-id="cc5e8-108">Element</span></span>|<span data-ttu-id="cc5e8-109">Description</span><span class="sxs-lookup"><span data-stu-id="cc5e8-109">Description</span></span>|  
|-------------|-----------------|  
|[\<filters>](filters-of-routing.md)|<span data-ttu-id="cc5e8-110">필터가 일치할 때 메시지를 보내기 위한 라우팅 필터와 대상 엔드포인트 간의 매핑을 포함하는 라우팅 테이블입니다.</span><span class="sxs-lookup"><span data-stu-id="cc5e8-110">A routing table that contain mappings between the routing filters and the target endpoints to send messages to when the filter matches.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="cc5e8-111">부모 요소</span><span class="sxs-lookup"><span data-stu-id="cc5e8-111">Parent Elements</span></span>  
  
|<span data-ttu-id="cc5e8-112">요소</span><span class="sxs-lookup"><span data-stu-id="cc5e8-112">Element</span></span>|<span data-ttu-id="cc5e8-113">Description</span><span class="sxs-lookup"><span data-stu-id="cc5e8-113">Description</span></span>|  
|-------------|-----------------|  
|[\<routing>](routing.md)|<span data-ttu-id="cc5e8-114">라우팅 필터와 라우팅 테이블을 포함하는 구성 섹션입니다.</span><span class="sxs-lookup"><span data-stu-id="cc5e8-114">A configuration section that contains routing filters and routing tables.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="cc5e8-115">참고 항목</span><span class="sxs-lookup"><span data-stu-id="cc5e8-115">See also</span></span>

- <xref:System.ServiceModel.Routing.Configuration.RoutingSection?displayProperty=nameWithType>
- <xref:System.ServiceModel.Routing.Configuration.FilterTableCollection?displayProperty=nameWithType>
