---
title: <entries>
ms.date: 03/30/2017
ms.assetid: 202e430c-c1b9-4343-abe2-ac78c181a3b7
ms.openlocfilehash: ffe2538fa2c3cb680285cfaa68c975c0f9d4b1bd
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/10/2019
ms.locfileid: "70855281"
---
# <a name="entries"></a><span data-ttu-id="afa4a-101">\<entries></span><span class="sxs-lookup"><span data-stu-id="afa4a-101">\<entries></span></span>
<span data-ttu-id="afa4a-102">필터가 일치할 때 메시지를 보내기 위한 라우팅 필터와 대상 엔드포인트 간의 매핑을 포함하는 라우팅 항목입니다.</span><span class="sxs-lookup"><span data-stu-id="afa4a-102">A routing entry that contain mappings between the routing filters and the target endpoints to send messages to when the filter matches.</span></span>  
  
<span data-ttu-id="afa4a-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="afa4a-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="afa4a-104">&nbsp;&nbsp;[ **\<System.servicemodel >** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="afa4a-104">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="afa4a-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<라우팅 >** ](routing.md)</span><span class="sxs-lookup"><span data-stu-id="afa4a-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<routing>**](routing.md)</span></span>\
<span data-ttu-id="afa4a-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<filterTables >** ](filtertables.md)</span><span class="sxs-lookup"><span data-stu-id="afa4a-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<filterTables>**](filtertables.md)</span></span>\
<span data-ttu-id="afa4a-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<filterTable >** ](filtertable.md)</span><span class="sxs-lookup"><span data-stu-id="afa4a-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<filterTable>**](filtertable.md)</span></span>\
<span data-ttu-id="afa4a-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<항목 >**</span><span class="sxs-lookup"><span data-stu-id="afa4a-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<entries>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="afa4a-109">구문</span><span class="sxs-lookup"><span data-stu-id="afa4a-109">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="afa4a-110">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="afa4a-110">Attributes and Elements</span></span>  
 <span data-ttu-id="afa4a-111">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="afa4a-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="afa4a-112">특성</span><span class="sxs-lookup"><span data-stu-id="afa4a-112">Attributes</span></span>  
 <span data-ttu-id="afa4a-113">없음</span><span class="sxs-lookup"><span data-stu-id="afa4a-113">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="afa4a-114">자식 요소</span><span class="sxs-lookup"><span data-stu-id="afa4a-114">Child Elements</span></span>  
  
|<span data-ttu-id="afa4a-115">요소</span><span class="sxs-lookup"><span data-stu-id="afa4a-115">Element</span></span>|<span data-ttu-id="afa4a-116">설명</span><span class="sxs-lookup"><span data-stu-id="afa4a-116">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="afa4a-117">\<필터></span><span class="sxs-lookup"><span data-stu-id="afa4a-117">\<filters></span></span>](filters-of-routing.md)|<span data-ttu-id="afa4a-118">이전에 정의된 클라이언트 엔드포인트에 필터를 매핑합니다.</span><span class="sxs-lookup"><span data-stu-id="afa4a-118">Maps a filter to a client endpoint that was previously defined.</span></span> <span data-ttu-id="afa4a-119">이 필터와 일치하는 메시지가 해당 대상으로 전송됩니다.</span><span class="sxs-lookup"><span data-stu-id="afa4a-119">Messages matching this filter will be sent to this destination.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="afa4a-120">부모 요소</span><span class="sxs-lookup"><span data-stu-id="afa4a-120">Parent Elements</span></span>  
  
|<span data-ttu-id="afa4a-121">요소</span><span class="sxs-lookup"><span data-stu-id="afa4a-121">Element</span></span>|<span data-ttu-id="afa4a-122">Description</span><span class="sxs-lookup"><span data-stu-id="afa4a-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="afa4a-123">\<routing></span><span class="sxs-lookup"><span data-stu-id="afa4a-123">\<routing></span></span>](routing.md)|<span data-ttu-id="afa4a-124">라우팅 테이블을 포함하는 구성 섹션입니다.</span><span class="sxs-lookup"><span data-stu-id="afa4a-124">A configuration section that contains a routing table.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="afa4a-125">참고자료</span><span class="sxs-lookup"><span data-stu-id="afa4a-125">See also</span></span>

- <xref:System.ServiceModel.Routing.Configuration.RoutingSection?displayProperty=nameWithType>
- <xref:System.ServiceModel.Routing.Configuration.FilterTableEntryElement?displayProperty=nameWithType>
