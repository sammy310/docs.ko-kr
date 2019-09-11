---
title: <filterTable>
ms.date: 03/30/2017
ms.assetid: e9f05441-3ad1-49b9-a267-71724aa094b4
ms.openlocfilehash: 918a365004efea82f4ef4c8868f6821d4bb6da18
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/10/2019
ms.locfileid: "70855184"
---
# <a name="filtertable"></a><span data-ttu-id="26d6d-101">\<filterTable></span><span class="sxs-lookup"><span data-stu-id="26d6d-101">\<filterTable></span></span>
<span data-ttu-id="26d6d-102">메시지를 평가할 필터 목록과 필터가 true로 평가 될 경우 메시지를 라우팅할 클라이언트 끝점을 포함 하는 라우팅 테이블을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="26d6d-102">Represents a routing table that contains a list of filters to evaluate messages against and the client endpoint to route messages to if the filter evaluates to true.</span></span>  
  
<span data-ttu-id="26d6d-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="26d6d-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="26d6d-104">&nbsp;&nbsp;[ **\<System.servicemodel >** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="26d6d-104">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="26d6d-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<라우팅 >** ](routing.md)</span><span class="sxs-lookup"><span data-stu-id="26d6d-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<routing>**](routing.md)</span></span>\
<span data-ttu-id="26d6d-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<filterTables >** ](filtertables.md)</span><span class="sxs-lookup"><span data-stu-id="26d6d-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<filterTables>**](filtertables.md)</span></span>\
<span data-ttu-id="26d6d-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<filterTable >**</span><span class="sxs-lookup"><span data-stu-id="26d6d-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<filterTable>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="26d6d-108">구문</span><span class="sxs-lookup"><span data-stu-id="26d6d-108">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="26d6d-109">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="26d6d-109">Attributes and Elements</span></span>  
 <span data-ttu-id="26d6d-110">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="26d6d-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="26d6d-111">특성</span><span class="sxs-lookup"><span data-stu-id="26d6d-111">Attributes</span></span>  
  
|<span data-ttu-id="26d6d-112">요소</span><span class="sxs-lookup"><span data-stu-id="26d6d-112">Element</span></span>|<span data-ttu-id="26d6d-113">Description</span><span class="sxs-lookup"><span data-stu-id="26d6d-113">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="26d6d-114">name</span><span class="sxs-lookup"><span data-stu-id="26d6d-114">name</span></span>|<span data-ttu-id="26d6d-115">이 구성 요소의 고유 이름을 포함하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="26d6d-115">A string that contains the unique name of this configuration element.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="26d6d-116">자식 요소</span><span class="sxs-lookup"><span data-stu-id="26d6d-116">Child Elements</span></span>  
  
|<span data-ttu-id="26d6d-117">요소</span><span class="sxs-lookup"><span data-stu-id="26d6d-117">Element</span></span>|<span data-ttu-id="26d6d-118">설명</span><span class="sxs-lookup"><span data-stu-id="26d6d-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="26d6d-119">\<필터></span><span class="sxs-lookup"><span data-stu-id="26d6d-119">\<filters></span></span>](filters-of-routing.md)|<span data-ttu-id="26d6d-120">필터가 일치할 때 메시지를 보내기 위한 라우팅 필터와 대상 엔드포인트 간의 매핑입니다.</span><span class="sxs-lookup"><span data-stu-id="26d6d-120">Mappings between the routing filters and the target endpoints to send messages to when the filter matches.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="26d6d-121">부모 요소</span><span class="sxs-lookup"><span data-stu-id="26d6d-121">Parent Elements</span></span>  
  
|<span data-ttu-id="26d6d-122">요소</span><span class="sxs-lookup"><span data-stu-id="26d6d-122">Element</span></span>|<span data-ttu-id="26d6d-123">설명</span><span class="sxs-lookup"><span data-stu-id="26d6d-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="26d6d-124">\<routing></span><span class="sxs-lookup"><span data-stu-id="26d6d-124">\<routing></span></span>](routing.md)|<span data-ttu-id="26d6d-125">라우팅 테이블을 포함하는 구성 섹션입니다.</span><span class="sxs-lookup"><span data-stu-id="26d6d-125">A configuration section that contains routing tables.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="26d6d-126">참고자료</span><span class="sxs-lookup"><span data-stu-id="26d6d-126">See also</span></span>

- <xref:System.ServiceModel.Routing.Configuration.RoutingSection?displayProperty=nameWithType>
