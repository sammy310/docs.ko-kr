---
description: 다음에 대해 자세히 알아보세요. <routing>
title: <routing>
ms.date: 03/30/2017
ms.assetid: a210c209-3940-4288-9a8e-39b1e62606bc
ms.openlocfilehash: 62222b527a14310b66015d4fdc4503e6cff25c8a
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99683348"
---
# \<routing>

<span data-ttu-id="64768-102"><xref:System.ServiceModel.Dispatcher.MessageFilter>들어오는 메시지를 평가할 때 사용할 WCF (Windows Communication Foundation 유형)와 필터가 일치할 때 메시지를 보낼 대상 끝점을 정의 하는 라우팅 테이블을 결정 하는 라우팅 필터 집합을 정의 하기 위한 구성 섹션을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="64768-102">Represents a configuration section for defining a set of routing filters, which determine the type of Windows Communication Foundation (WCF) <xref:System.ServiceModel.Dispatcher.MessageFilter> to be used when evaluating incoming messages, as well as routing tables that define the target endpoints to send messages to when a filter matches.</span></span>

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<routing>**
  
## <a name="syntax"></a><span data-ttu-id="64768-103">구문</span><span class="sxs-lookup"><span data-stu-id="64768-103">Syntax</span></span>  
  
```xml  
<system.serviceModel>
  <routing>
    <filters>
      <filter customType="String"
              filterData="String"
              filterType="Action/Address/AddressPrefix/And/Custom/Endpoint/MatchAll/XPath"
              name="String" />
    </filters>
    <routingTables>
      <table name="String">
        <entries>
          <add endpoint="String"
               filterName="String"
               priority="Integer" />
        </entries>
      </table>
    </routingTables>
  </routing>
</system.serviceModel>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="64768-104">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="64768-104">Attributes and elements</span></span>

<span data-ttu-id="64768-105">다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="64768-105">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="64768-106">특성</span><span class="sxs-lookup"><span data-stu-id="64768-106">Attributes</span></span>

<span data-ttu-id="64768-107">None</span><span class="sxs-lookup"><span data-stu-id="64768-107">None</span></span>

### <a name="child-elements"></a><span data-ttu-id="64768-108">자식 요소</span><span class="sxs-lookup"><span data-stu-id="64768-108">Child elements</span></span>

|     | <span data-ttu-id="64768-109">설명</span><span class="sxs-lookup"><span data-stu-id="64768-109">Description</span></span> |
| --- | ----------- |
| [**\<filters>**](filters-of-routing.md) | <span data-ttu-id="64768-110">들어오는 메시지를 평가할 때 사용 되는 Windows Communication Foundation (WCF) MessageFilter 유형을 결정 하는 라우팅 필터 집합을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="64768-110">Contains a set of routing filters that determine the type of Windows Communication Foundation (WCF) MessageFilter will be used when evaluating incoming messages.</span></span> |
| [**\<filterTables>**](filtertables.md) | <span data-ttu-id="64768-111">필터가 일치할 때 사용할 엔드포인트를 지정하기 위한 라우팅 필터와 대상 엔드포인트 간의 매핑을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="64768-111">Contains mappings between the routing filters and the target endpoints to specify which endpoint to use when the filter matches.</span></span> |

### <a name="parent-elements"></a><span data-ttu-id="64768-112">부모 요소</span><span class="sxs-lookup"><span data-stu-id="64768-112">Parent elements</span></span>

|     | <span data-ttu-id="64768-113">설명</span><span class="sxs-lookup"><span data-stu-id="64768-113">Description</span></span> |
| --- | ----------- |
| **\<system.ServiceModel>** | <span data-ttu-id="64768-114">모든 WCF 구성 요소의 루트 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="64768-114">The root element of all WCF configuration elements.</span></span> |

## <a name="see-also"></a><span data-ttu-id="64768-115">참고 항목</span><span class="sxs-lookup"><span data-stu-id="64768-115">See also</span></span>

- <xref:System.ServiceModel.Routing.Configuration.RoutingSection?displayProperty=nameWithType>
