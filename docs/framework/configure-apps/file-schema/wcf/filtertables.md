---
description: 다음에 대해 자세히 알아보세요. <filterTables>
title: <filterTables>
ms.date: 03/30/2017
ms.assetid: 41f1ac35-f559-473a-b2c3-8cc83a6a3831
ms.openlocfilehash: 932d0e162c3fdeba8b166d3adaaa73cc3b5293a9
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99664589"
---
# \<filterTables>

<span data-ttu-id="67f6a-102">필터가 일치할 때 메시지를 보내기 위한 라우팅 필터와 대상 엔드포인트 간의 매핑을 포함하는 라우팅 테이블을 정의하기 위한 구성 섹션을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="67f6a-102">Represents a configuration section for defining routing tables that contain mappings between the routing filters and the target endpoints to send messages to when the filter matches.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<routing>**](routing.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<filterTables>**  
  
## <a name="syntax"></a><span data-ttu-id="67f6a-103">구문</span><span class="sxs-lookup"><span data-stu-id="67f6a-103">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="67f6a-104">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="67f6a-104">Attributes and Elements</span></span>  

 <span data-ttu-id="67f6a-105">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="67f6a-105">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="67f6a-106">특성</span><span class="sxs-lookup"><span data-stu-id="67f6a-106">Attributes</span></span>  

 <span data-ttu-id="67f6a-107">없음</span><span class="sxs-lookup"><span data-stu-id="67f6a-107">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="67f6a-108">자식 요소</span><span class="sxs-lookup"><span data-stu-id="67f6a-108">Child Elements</span></span>  
  
|<span data-ttu-id="67f6a-109">요소</span><span class="sxs-lookup"><span data-stu-id="67f6a-109">Element</span></span>|<span data-ttu-id="67f6a-110">설명</span><span class="sxs-lookup"><span data-stu-id="67f6a-110">Description</span></span>|  
|-------------|-----------------|  
|[\<filters>](filters-of-routing.md)|<span data-ttu-id="67f6a-111">필터가 일치할 때 메시지를 보내기 위한 라우팅 필터와 대상 엔드포인트 간의 매핑을 포함하는 라우팅 테이블입니다.</span><span class="sxs-lookup"><span data-stu-id="67f6a-111">A routing table that contain mappings between the routing filters and the target endpoints to send messages to when the filter matches.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="67f6a-112">부모 요소</span><span class="sxs-lookup"><span data-stu-id="67f6a-112">Parent Elements</span></span>  
  
|<span data-ttu-id="67f6a-113">요소</span><span class="sxs-lookup"><span data-stu-id="67f6a-113">Element</span></span>|<span data-ttu-id="67f6a-114">설명</span><span class="sxs-lookup"><span data-stu-id="67f6a-114">Description</span></span>|  
|-------------|-----------------|  
|[\<routing>](routing.md)|<span data-ttu-id="67f6a-115">라우팅 필터와 라우팅 테이블을 포함하는 구성 섹션입니다.</span><span class="sxs-lookup"><span data-stu-id="67f6a-115">A configuration section that contains routing filters and routing tables.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="67f6a-116">참고 항목</span><span class="sxs-lookup"><span data-stu-id="67f6a-116">See also</span></span>

- <xref:System.ServiceModel.Routing.Configuration.RoutingSection?displayProperty=nameWithType>
- <xref:System.ServiceModel.Routing.Configuration.FilterTableCollection?displayProperty=nameWithType>
