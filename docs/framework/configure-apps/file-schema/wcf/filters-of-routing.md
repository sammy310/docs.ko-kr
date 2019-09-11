---
title: <routing>의 <filters>
ms.date: 03/30/2017
ms.assetid: 7993cf90-9afd-4c3c-9608-184d5da1105c
ms.openlocfilehash: c9bc3a2c379e14d8cf687676a3ec40702d150e1e
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/10/2019
ms.locfileid: "70855242"
---
# <a name="filters-of-routing"></a><span data-ttu-id="246dc-102">\<라우팅 > > \<를 필터링 합니다.</span><span class="sxs-lookup"><span data-stu-id="246dc-102">\<filters> of \<routing></span></span>

<span data-ttu-id="246dc-103">들어오는 메시지를 평가할 때 사용할 WCF (Windows Communication Foundation 형식) <xref:System.ServiceModel.Dispatcher.MessageFilter> 를 결정 하는 라우팅 필터 집합을 정의 하기 위한 구성 섹션을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="246dc-103">Represents a configuration section for defining a set of routing filters, which determine the type of Windows Communication Foundation (WCF) <xref:System.ServiceModel.Dispatcher.MessageFilter> to be used when evaluating incoming messages.</span></span>

<span data-ttu-id="246dc-104">[ **\<system.serviceModel>** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="246dc-104">[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="246dc-105">&nbsp;&nbsp;[ **\<routing>** ](routing.md)</span><span class="sxs-lookup"><span data-stu-id="246dc-105">&nbsp;&nbsp;[**\<routing>**](routing.md)</span></span>\
<span data-ttu-id="246dc-106">&nbsp;&nbsp;&nbsp;&nbsp; **\<filters>**</span><span class="sxs-lookup"><span data-stu-id="246dc-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<filters>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="246dc-107">구문</span><span class="sxs-lookup"><span data-stu-id="246dc-107">Syntax</span></span>  
  
```xml  
<system.serviceModel>
  <routing>
    <filters>
      <filter customType="String"
              filterData="String"
              filterType="Action/Address/AddressPrefix/And/Custom/Endpoint/MatchAll/XPath"
              name="String" />
    </filters>
  </routing>
</system.serviceModel>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="246dc-108">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="246dc-108">Attributes and elements</span></span>

<span data-ttu-id="246dc-109">다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="246dc-109">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="246dc-110">특성</span><span class="sxs-lookup"><span data-stu-id="246dc-110">Attributes</span></span>

<span data-ttu-id="246dc-111">없음</span><span class="sxs-lookup"><span data-stu-id="246dc-111">None</span></span>

### <a name="child-elements"></a><span data-ttu-id="246dc-112">자식 요소</span><span class="sxs-lookup"><span data-stu-id="246dc-112">Child elements</span></span>

|     | <span data-ttu-id="246dc-113">Description</span><span class="sxs-lookup"><span data-stu-id="246dc-113">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="246dc-114"> **\<filter>** </span><span class="sxs-lookup"><span data-stu-id="246dc-114">**\<filter>**</span></span>](filter.md) | <span data-ttu-id="246dc-115">들어오는 메시지를 평가할 때 사용할 WCF (Windows Communication Foundation 형식)<xref:System.ServiceModel.Dispatcher.MessageFilter> 를 결정 하는 라우팅 필터를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="246dc-115">Contains a routing filter that determines the type of Windows Communication Foundation (WCF)<xref:System.ServiceModel.Dispatcher.MessageFilter> will be used when evaluating incoming messages.</span></span> |

### <a name="parent-elements"></a><span data-ttu-id="246dc-116">부모 요소</span><span class="sxs-lookup"><span data-stu-id="246dc-116">Parent elements</span></span>

|     | <span data-ttu-id="246dc-117">설명</span><span class="sxs-lookup"><span data-stu-id="246dc-117">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="246dc-118"> **\<routing>** </span><span class="sxs-lookup"><span data-stu-id="246dc-118">**\<routing>**</span></span>](routing.md) | <span data-ttu-id="246dc-119">들어오는 메시지를 평가할 때 사용 되는 WCF<xref:System.ServiceModel.Dispatcher.MessageFilter> (Windows Communication Foundation 형식 및 대상 끝점을 정의 하는 라우팅 테이블을 결정 하는 라우팅 필터 집합을 정의 하기 위한 구성 섹션을 나타냅니다. 필터가 일치 하는 경우에 메시지를 보냅니다.</span><span class="sxs-lookup"><span data-stu-id="246dc-119">Represents a configuration section for defining a set of routing filters, which determine the type of Windows Communication Foundation (WCF)<xref:System.ServiceModel.Dispatcher.MessageFilter> to be used when evaluating incoming messages, as well as routing tables that define the target endpoints to send messages to when a filter matches.</span></span> |

## <a name="see-also"></a><span data-ttu-id="246dc-120">참고자료</span><span class="sxs-lookup"><span data-stu-id="246dc-120">See also</span></span>

- <xref:System.ServiceModel.Routing.Configuration.FilterElement?displayProperty=nameWithType>
