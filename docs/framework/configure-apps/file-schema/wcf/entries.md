---
description: 다음에 대해 자세히 알아보세요. <entries>
title: <entries>
ms.date: 03/30/2017
ms.assetid: 202e430c-c1b9-4343-abe2-ac78c181a3b7
ms.openlocfilehash: e5aefce4328c341b6d132765c8e726910241aae1
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99782106"
---
# \<entries>

<span data-ttu-id="baf94-102">필터가 일치할 때 메시지를 보내기 위한 라우팅 필터와 대상 엔드포인트 간의 매핑을 포함하는 라우팅 항목입니다.</span><span class="sxs-lookup"><span data-stu-id="baf94-102">A routing entry that contain mappings between the routing filters and the target endpoints to send messages to when the filter matches.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<routing>**](routing.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<filterTables>**](filtertables.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<filterTable>**](filtertable.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<entries>**  
  
## <a name="syntax"></a><span data-ttu-id="baf94-103">구문</span><span class="sxs-lookup"><span data-stu-id="baf94-103">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="baf94-104">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="baf94-104">Attributes and Elements</span></span>  

 <span data-ttu-id="baf94-105">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="baf94-105">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="baf94-106">특성</span><span class="sxs-lookup"><span data-stu-id="baf94-106">Attributes</span></span>  

 <span data-ttu-id="baf94-107">없음</span><span class="sxs-lookup"><span data-stu-id="baf94-107">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="baf94-108">자식 요소</span><span class="sxs-lookup"><span data-stu-id="baf94-108">Child Elements</span></span>  
  
|<span data-ttu-id="baf94-109">요소</span><span class="sxs-lookup"><span data-stu-id="baf94-109">Element</span></span>|<span data-ttu-id="baf94-110">설명</span><span class="sxs-lookup"><span data-stu-id="baf94-110">Description</span></span>|  
|-------------|-----------------|  
|[\<filters>](filters-of-routing.md)|<span data-ttu-id="baf94-111">이전에 정의된 클라이언트 엔드포인트에 필터를 매핑합니다.</span><span class="sxs-lookup"><span data-stu-id="baf94-111">Maps a filter to a client endpoint that was previously defined.</span></span> <span data-ttu-id="baf94-112">이 필터와 일치하는 메시지가 해당 대상으로 전송됩니다.</span><span class="sxs-lookup"><span data-stu-id="baf94-112">Messages matching this filter will be sent to this destination.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="baf94-113">부모 요소</span><span class="sxs-lookup"><span data-stu-id="baf94-113">Parent Elements</span></span>  
  
|<span data-ttu-id="baf94-114">요소</span><span class="sxs-lookup"><span data-stu-id="baf94-114">Element</span></span>|<span data-ttu-id="baf94-115">설명</span><span class="sxs-lookup"><span data-stu-id="baf94-115">Description</span></span>|  
|-------------|-----------------|  
|[\<routing>](routing.md)|<span data-ttu-id="baf94-116">라우팅 테이블을 포함하는 구성 섹션입니다.</span><span class="sxs-lookup"><span data-stu-id="baf94-116">A configuration section that contains a routing table.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="baf94-117">참고 항목</span><span class="sxs-lookup"><span data-stu-id="baf94-117">See also</span></span>

- <xref:System.ServiceModel.Routing.Configuration.RoutingSection?displayProperty=nameWithType>
- <xref:System.ServiceModel.Routing.Configuration.FilterTableEntryElement?displayProperty=nameWithType>
