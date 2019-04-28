---
title: <routing>
ms.date: 03/30/2017
ms.assetid: a210c209-3940-4288-9a8e-39b1e62606bc
ms.openlocfilehash: cc7c1a64f9481a7ab41cf35241ade04bd690dae0
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61786388"
---
# <a name="routing"></a><span data-ttu-id="08e29-101">\<라우팅 ></span><span class="sxs-lookup"><span data-stu-id="08e29-101">\<routing></span></span>

<span data-ttu-id="08e29-102">Windows Communication Foundation (WCF)의 형식을 결정 하는 라우팅 필터 집합을 정의 하기 위한 구성 섹션을 나타냅니다 <xref:System.ServiceModel.Dispatcher.MessageFilter> 사용할 대상 끝점을 정의 하는 들어오는 메시지를 평가할 수 있을 뿐만 아니라 라우팅 테이블 필터가 일치할 때에 메시지를 보냅니다.</span><span class="sxs-lookup"><span data-stu-id="08e29-102">Represents a configuration section for defining a set of routing filters, which determine the type of Windows Communication Foundation (WCF) <xref:System.ServiceModel.Dispatcher.MessageFilter> to be used when evaluating incoming messages, as well as routing tables that define the target endpoints to send messages to when a filter matches.</span></span>

<span data-ttu-id="08e29-103">[**\<system.serviceModel>**](system-servicemodel.md) </span><span class="sxs-lookup"><span data-stu-id="08e29-103">[**\<system.serviceModel>**](system-servicemodel.md) </span></span>  
<span data-ttu-id="08e29-104">&nbsp;&nbsp;**\<routing>**</span><span class="sxs-lookup"><span data-stu-id="08e29-104">&nbsp;&nbsp;**\<routing>**</span></span>
  
## <a name="syntax"></a><span data-ttu-id="08e29-105">구문</span><span class="sxs-lookup"><span data-stu-id="08e29-105">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="08e29-106">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="08e29-106">Attributes and elements</span></span>

<span data-ttu-id="08e29-107">다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="08e29-107">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="08e29-108">특성</span><span class="sxs-lookup"><span data-stu-id="08e29-108">Attributes</span></span>

<span data-ttu-id="08e29-109">없음</span><span class="sxs-lookup"><span data-stu-id="08e29-109">None</span></span>

### <a name="child-elements"></a><span data-ttu-id="08e29-110">자식 요소</span><span class="sxs-lookup"><span data-stu-id="08e29-110">Child elements</span></span>

|     | <span data-ttu-id="08e29-111">설명</span><span class="sxs-lookup"><span data-stu-id="08e29-111">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="08e29-112">**\<filters>**</span><span class="sxs-lookup"><span data-stu-id="08e29-112">**\<filters>**</span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/filters-of-routing.md) | <span data-ttu-id="08e29-113">들어오는 메시지를 평가할 때 Windows Communication Foundation (WCF) messagefilter 형식을 사용할지를 결정 하는 라우팅 필터 집합을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="08e29-113">Contains a set of routing filters that determine the type of Windows Communication Foundation (WCF) MessageFilter will be used when evaluating incoming messages.</span></span> |
| [<span data-ttu-id="08e29-114">**\<filterTables>**</span><span class="sxs-lookup"><span data-stu-id="08e29-114">**\<filterTables>**</span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/filtertables.md) | <span data-ttu-id="08e29-115">필터가 일치할 때 사용할 엔드포인트를 지정하기 위한 라우팅 필터와 대상 엔드포인트 간의 매핑을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="08e29-115">Contains mappings between the routing filters and the target endpoints to specify which endpoint to use when the filter matches.</span></span> |

### <a name="parent-elements"></a><span data-ttu-id="08e29-116">부모 요소</span><span class="sxs-lookup"><span data-stu-id="08e29-116">Parent elements</span></span>

|     | <span data-ttu-id="08e29-117">설명</span><span class="sxs-lookup"><span data-stu-id="08e29-117">Description</span></span> |
| --- | ----------- |
| <span data-ttu-id="08e29-118">**\<system.ServiceModel>**</span><span class="sxs-lookup"><span data-stu-id="08e29-118">**\<system.ServiceModel>**</span></span> | <span data-ttu-id="08e29-119">모든 WCF 구성 요소의 루트 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="08e29-119">The root element of all WCF configuration elements.</span></span> |

## <a name="see-also"></a><span data-ttu-id="08e29-120">참고자료</span><span class="sxs-lookup"><span data-stu-id="08e29-120">See also</span></span>

- <xref:System.ServiceModel.Routing.Configuration.RoutingSection?displayProperty=nameWithType>
