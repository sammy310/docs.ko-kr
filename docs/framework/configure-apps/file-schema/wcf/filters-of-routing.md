---
title: <routing>의 <filters>
ms.date: 03/30/2017
ms.assetid: 7993cf90-9afd-4c3c-9608-184d5da1105c
ms.openlocfilehash: c9bc3a2c379e14d8cf687676a3ec40702d150e1e
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/06/2020
ms.locfileid: "70855242"
---
# <a name="filters-of-routing"></a><span data-ttu-id="34ad6-102">\<routing>의 \<filters></span><span class="sxs-lookup"><span data-stu-id="34ad6-102">\<filters> of \<routing></span></span>

<span data-ttu-id="34ad6-103"><xref:System.ServiceModel.Dispatcher.MessageFilter>들어오는 메시지를 평가할 때 사용할 WCF (Windows Communication Foundation 형식)를 결정 하는 라우팅 필터 집합을 정의 하기 위한 구성 섹션을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="34ad6-103">Represents a configuration section for defining a set of routing filters, which determine the type of Windows Communication Foundation (WCF) <xref:System.ServiceModel.Dispatcher.MessageFilter> to be used when evaluating incoming messages.</span></span>

[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;[**\<routing>**](routing.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<filters>**  
  
## <a name="syntax"></a><span data-ttu-id="34ad6-104">구문</span><span class="sxs-lookup"><span data-stu-id="34ad6-104">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="34ad6-105">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="34ad6-105">Attributes and elements</span></span>

<span data-ttu-id="34ad6-106">다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="34ad6-106">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="34ad6-107">특성</span><span class="sxs-lookup"><span data-stu-id="34ad6-107">Attributes</span></span>

<span data-ttu-id="34ad6-108">None</span><span class="sxs-lookup"><span data-stu-id="34ad6-108">None</span></span>

### <a name="child-elements"></a><span data-ttu-id="34ad6-109">자식 요소</span><span class="sxs-lookup"><span data-stu-id="34ad6-109">Child elements</span></span>

|     | <span data-ttu-id="34ad6-110">Description</span><span class="sxs-lookup"><span data-stu-id="34ad6-110">Description</span></span> |
| --- | ----------- |
| [**\<filter>**](filter.md) | <span data-ttu-id="34ad6-111">들어오는 메시지를 평가할 때 사용할 WCF (Windows Communication Foundation 형식)를 결정 하는 라우팅 필터를 포함 <xref:System.ServiceModel.Dispatcher.MessageFilter> 합니다.</span><span class="sxs-lookup"><span data-stu-id="34ad6-111">Contains a routing filter that determines the type of Windows Communication Foundation (WCF)<xref:System.ServiceModel.Dispatcher.MessageFilter> will be used when evaluating incoming messages.</span></span> |

### <a name="parent-elements"></a><span data-ttu-id="34ad6-112">부모 요소</span><span class="sxs-lookup"><span data-stu-id="34ad6-112">Parent elements</span></span>

|     | <span data-ttu-id="34ad6-113">Description</span><span class="sxs-lookup"><span data-stu-id="34ad6-113">Description</span></span> |
| --- | ----------- |
| [**\<routing>**](routing.md) | <span data-ttu-id="34ad6-114"><xref:System.ServiceModel.Dispatcher.MessageFilter>들어오는 메시지를 평가할 때 사용할 WCF (Windows Communication Foundation 유형)와 필터가 일치할 때 메시지를 보낼 대상 끝점을 정의 하는 라우팅 테이블을 결정 하는 라우팅 필터 집합을 정의 하기 위한 구성 섹션을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="34ad6-114">Represents a configuration section for defining a set of routing filters, which determine the type of Windows Communication Foundation (WCF)<xref:System.ServiceModel.Dispatcher.MessageFilter> to be used when evaluating incoming messages, as well as routing tables that define the target endpoints to send messages to when a filter matches.</span></span> |

## <a name="see-also"></a><span data-ttu-id="34ad6-115">참고 항목</span><span class="sxs-lookup"><span data-stu-id="34ad6-115">See also</span></span>

- <xref:System.ServiceModel.Routing.Configuration.FilterElement?displayProperty=nameWithType>
