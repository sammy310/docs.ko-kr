---
title: <entries>
ms.date: 03/30/2017
ms.assetid: 202e430c-c1b9-4343-abe2-ac78c181a3b7
ms.openlocfilehash: ffe2538fa2c3cb680285cfaa68c975c0f9d4b1bd
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/06/2020
ms.locfileid: "70855281"
---
# \<entries>
<span data-ttu-id="885c5-101">필터가 일치할 때 메시지를 보내기 위한 라우팅 필터와 대상 엔드포인트 간의 매핑을 포함하는 라우팅 항목입니다.</span><span class="sxs-lookup"><span data-stu-id="885c5-101">A routing entry that contain mappings between the routing filters and the target endpoints to send messages to when the filter matches.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<routing>**](routing.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<filterTables>**](filtertables.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<filterTable>**](filtertable.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<entries>**  
  
## <a name="syntax"></a><span data-ttu-id="885c5-102">구문</span><span class="sxs-lookup"><span data-stu-id="885c5-102">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="885c5-103">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="885c5-103">Attributes and Elements</span></span>  
 <span data-ttu-id="885c5-104">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="885c5-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="885c5-105">특성</span><span class="sxs-lookup"><span data-stu-id="885c5-105">Attributes</span></span>  
 <span data-ttu-id="885c5-106">없음</span><span class="sxs-lookup"><span data-stu-id="885c5-106">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="885c5-107">자식 요소</span><span class="sxs-lookup"><span data-stu-id="885c5-107">Child Elements</span></span>  
  
|<span data-ttu-id="885c5-108">요소</span><span class="sxs-lookup"><span data-stu-id="885c5-108">Element</span></span>|<span data-ttu-id="885c5-109">Description</span><span class="sxs-lookup"><span data-stu-id="885c5-109">Description</span></span>|  
|-------------|-----------------|  
|[\<filters>](filters-of-routing.md)|<span data-ttu-id="885c5-110">이전에 정의된 클라이언트 엔드포인트에 필터를 매핑합니다.</span><span class="sxs-lookup"><span data-stu-id="885c5-110">Maps a filter to a client endpoint that was previously defined.</span></span> <span data-ttu-id="885c5-111">이 필터와 일치하는 메시지가 해당 대상으로 전송됩니다.</span><span class="sxs-lookup"><span data-stu-id="885c5-111">Messages matching this filter will be sent to this destination.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="885c5-112">부모 요소</span><span class="sxs-lookup"><span data-stu-id="885c5-112">Parent Elements</span></span>  
  
|<span data-ttu-id="885c5-113">요소</span><span class="sxs-lookup"><span data-stu-id="885c5-113">Element</span></span>|<span data-ttu-id="885c5-114">Description</span><span class="sxs-lookup"><span data-stu-id="885c5-114">Description</span></span>|  
|-------------|-----------------|  
|[\<routing>](routing.md)|<span data-ttu-id="885c5-115">라우팅 테이블을 포함하는 구성 섹션입니다.</span><span class="sxs-lookup"><span data-stu-id="885c5-115">A configuration section that contains a routing table.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="885c5-116">참고 항목</span><span class="sxs-lookup"><span data-stu-id="885c5-116">See also</span></span>

- <xref:System.ServiceModel.Routing.Configuration.RoutingSection?displayProperty=nameWithType>
- <xref:System.ServiceModel.Routing.Configuration.FilterTableEntryElement?displayProperty=nameWithType>
