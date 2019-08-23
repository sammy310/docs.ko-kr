---
title: <routing>
ms.date: 03/30/2017
ms.assetid: a210c209-3940-4288-9a8e-39b1e62606bc
ms.openlocfilehash: 3c7e9cb1284ab55c8dd199d9fb47a223698814f0
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/22/2019
ms.locfileid: "69934133"
---
# <a name="routing"></a><span data-ttu-id="1e0b2-101">\<라우팅 ></span><span class="sxs-lookup"><span data-stu-id="1e0b2-101">\<routing></span></span>

<span data-ttu-id="1e0b2-102">들어오는 메시지를 평가할 때 사용 되는 WCF <xref:System.ServiceModel.Dispatcher.MessageFilter> (Windows Communication Foundation 형식 및 대상 끝점을 정의 하는 라우팅 테이블을 결정 하는 라우팅 필터 집합을 정의 하기 위한 구성 섹션을 나타냅니다. 필터가 일치 하는 경우에 메시지를 보냅니다.</span><span class="sxs-lookup"><span data-stu-id="1e0b2-102">Represents a configuration section for defining a set of routing filters, which determine the type of Windows Communication Foundation (WCF) <xref:System.ServiceModel.Dispatcher.MessageFilter> to be used when evaluating incoming messages, as well as routing tables that define the target endpoints to send messages to when a filter matches.</span></span>

<span data-ttu-id="1e0b2-103">[ **\<system.serviceModel>** ](system-servicemodel.md) </span><span class="sxs-lookup"><span data-stu-id="1e0b2-103">[**\<system.serviceModel>**](system-servicemodel.md) </span></span>  
<span data-ttu-id="1e0b2-104">&nbsp;&nbsp; **\<routing>**</span><span class="sxs-lookup"><span data-stu-id="1e0b2-104">&nbsp;&nbsp;**\<routing>**</span></span>
  
## <a name="syntax"></a><span data-ttu-id="1e0b2-105">구문</span><span class="sxs-lookup"><span data-stu-id="1e0b2-105">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="1e0b2-106">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="1e0b2-106">Attributes and elements</span></span>

<span data-ttu-id="1e0b2-107">다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="1e0b2-107">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="1e0b2-108">특성</span><span class="sxs-lookup"><span data-stu-id="1e0b2-108">Attributes</span></span>

<span data-ttu-id="1e0b2-109">없음</span><span class="sxs-lookup"><span data-stu-id="1e0b2-109">None</span></span>

### <a name="child-elements"></a><span data-ttu-id="1e0b2-110">자식 요소</span><span class="sxs-lookup"><span data-stu-id="1e0b2-110">Child elements</span></span>

|     | <span data-ttu-id="1e0b2-111">Description</span><span class="sxs-lookup"><span data-stu-id="1e0b2-111">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="1e0b2-112"> **\<filters>** </span><span class="sxs-lookup"><span data-stu-id="1e0b2-112">**\<filters>**</span></span>](filters-of-routing.md) | <span data-ttu-id="1e0b2-113">들어오는 메시지를 평가할 때 사용 되는 Windows Communication Foundation (WCF) MessageFilter 유형을 결정 하는 라우팅 필터 집합을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="1e0b2-113">Contains a set of routing filters that determine the type of Windows Communication Foundation (WCF) MessageFilter will be used when evaluating incoming messages.</span></span> |
| [<span data-ttu-id="1e0b2-114"> **\<filterTables>** </span><span class="sxs-lookup"><span data-stu-id="1e0b2-114">**\<filterTables>**</span></span>](filtertables.md) | <span data-ttu-id="1e0b2-115">필터가 일치할 때 사용할 엔드포인트를 지정하기 위한 라우팅 필터와 대상 엔드포인트 간의 매핑을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="1e0b2-115">Contains mappings between the routing filters and the target endpoints to specify which endpoint to use when the filter matches.</span></span> |

### <a name="parent-elements"></a><span data-ttu-id="1e0b2-116">부모 요소</span><span class="sxs-lookup"><span data-stu-id="1e0b2-116">Parent elements</span></span>

|     | <span data-ttu-id="1e0b2-117">설명</span><span class="sxs-lookup"><span data-stu-id="1e0b2-117">Description</span></span> |
| --- | ----------- |
| <span data-ttu-id="1e0b2-118">**\<system.ServiceModel>**</span><span class="sxs-lookup"><span data-stu-id="1e0b2-118">**\<system.ServiceModel>**</span></span> | <span data-ttu-id="1e0b2-119">모든 WCF 구성 요소의 루트 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="1e0b2-119">The root element of all WCF configuration elements.</span></span> |

## <a name="see-also"></a><span data-ttu-id="1e0b2-120">참고자료</span><span class="sxs-lookup"><span data-stu-id="1e0b2-120">See also</span></span>

- <xref:System.ServiceModel.Routing.Configuration.RoutingSection?displayProperty=nameWithType>
