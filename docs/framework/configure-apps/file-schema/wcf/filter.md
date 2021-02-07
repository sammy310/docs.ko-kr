---
description: 다음에 대해 자세히 알아보세요. <filter>
title: <filter>
ms.date: 03/30/2017
ms.assetid: 3266700b-904b-44e4-93a7-e06a1a445100
ms.openlocfilehash: 993d2265ac3a714475e8cbe9e8a2c3f93c46bde2
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99664680"
---
# \<filter>

<span data-ttu-id="eb2af-102">들어오는 메시지를 평가할 때 사용할 WCF (Windows Communication Foundation 형식)와 필터에 <xref:System.ServiceModel.Dispatcher.MessageFilter> 필요한 지원 데이터 나 매개 변수를 결정 하는 라우팅 필터를 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="eb2af-102">Defines a routing filter, which determines the type of Windows Communication Foundation (WCF)<xref:System.ServiceModel.Dispatcher.MessageFilter> to be used when evaluating incoming messages, as well any supporting data or parameters required by the filter.</span></span>

[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;[**\<routing>**](routing.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<filters>**](filters-of-routing.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<filter>**  
  
## <a name="syntax"></a><span data-ttu-id="eb2af-103">구문</span><span class="sxs-lookup"><span data-stu-id="eb2af-103">Syntax</span></span>  
  
```xml  
<routing>
  <filters>
    <filter customType="String"
            filterData="String"
            filterType="Action/Address/AddressPrefix/And/Custom/Endpoint/MatchAll/XPath"
            name="String" />
  </filters>
</routing>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="eb2af-104">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="eb2af-104">Attributes and elements</span></span>

<span data-ttu-id="eb2af-105">다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="eb2af-105">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="eb2af-106">특성</span><span class="sxs-lookup"><span data-stu-id="eb2af-106">Attributes</span></span>

| <span data-ttu-id="eb2af-107">attribute</span><span class="sxs-lookup"><span data-stu-id="eb2af-107">Attribute</span></span>  | <span data-ttu-id="eb2af-108">설명</span><span class="sxs-lookup"><span data-stu-id="eb2af-108">Description</span></span> |
| ---------- | ----------- |
| <span data-ttu-id="eb2af-109">customType</span><span class="sxs-lookup"><span data-stu-id="eb2af-109">customType</span></span> | <span data-ttu-id="eb2af-110">필터로 사용할 사용자 지정 형식의 정규화된 형식 이름을 포함하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="eb2af-110">A string containing the fully qualified type name of the custom type to be used as a filter.</span></span> <span data-ttu-id="eb2af-111">`filterType`가로 설정 된 경우 `custom` 이 특성은 만들 클래스의 정규화 된 형식 이름을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="eb2af-111">If `filterType` is set to `custom`, this attribute contains the fully qualified type name of the class to create.</span></span>  <span data-ttu-id="eb2af-112">`filterData` 사용자 지정 형식 필터를 평가 하는 동안 사용할 값도 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eb2af-112">`filterData` may also contain values to be used during evaluation of the custom type filter.</span></span> |
| <span data-ttu-id="eb2af-113">filterData</span><span class="sxs-lookup"><span data-stu-id="eb2af-113">filterData</span></span> | <span data-ttu-id="eb2af-114">필터 데이터를 포함하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="eb2af-114">A string containing the filter data.</span></span> <span data-ttu-id="eb2af-115">이 특성을 지정하는 방법에 대한 자세한 내용은 <xref:System.ServiceModel.Routing.Configuration.FilterElement.FilterData%2A>를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="eb2af-115">For more information on how to specify this attribute, see <xref:System.ServiceModel.Routing.Configuration.FilterElement.FilterData%2A>.</span></span> |
| <span data-ttu-id="eb2af-116">filterType</span><span class="sxs-lookup"><span data-stu-id="eb2af-116">filterType</span></span> | <span data-ttu-id="eb2af-117">필터 형식을 포함하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="eb2af-117">A string containing the filter type.</span></span> <span data-ttu-id="eb2af-118">이 특성은 <xref:System.ServiceModel.Routing.Configuration.FilterType> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="eb2af-118">This attribute is of <xref:System.ServiceModel.Routing.Configuration.FilterType> type.</span></span>  <span data-ttu-id="eb2af-119">`filterData` 특성에서 이 형식이 어떻게 작동하는지에 대한 자세한 내용은 <xref:System.ServiceModel.Routing.Configuration.FilterElement.FilterData%2A>를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="eb2af-119">For more information on how this works with the `filterData` attribute, see <xref:System.ServiceModel.Routing.Configuration.FilterElement.FilterData%2A>.</span></span> |
| <span data-ttu-id="eb2af-120">name</span><span class="sxs-lookup"><span data-stu-id="eb2af-120">name</span></span>       | <span data-ttu-id="eb2af-121">이 필터 요소의 고유 이름을 포함하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="eb2af-121">A string containing the unique name of this filter element.</span></span> |

### <a name="child-elements"></a><span data-ttu-id="eb2af-122">자식 요소</span><span class="sxs-lookup"><span data-stu-id="eb2af-122">Child elements</span></span>

<span data-ttu-id="eb2af-123">없음</span><span class="sxs-lookup"><span data-stu-id="eb2af-123">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="eb2af-124">부모 요소</span><span class="sxs-lookup"><span data-stu-id="eb2af-124">Parent elements</span></span>

| <span data-ttu-id="eb2af-125">요소</span><span class="sxs-lookup"><span data-stu-id="eb2af-125">Element</span></span> | <span data-ttu-id="eb2af-126">설명</span><span class="sxs-lookup"><span data-stu-id="eb2af-126">Description</span></span> |
| ------- | ----------- |
| [\<routing>](routing.md) | <span data-ttu-id="eb2af-127"><xref:System.ServiceModel.Dispatcher.MessageFilter>들어오는 메시지를 평가할 때 사용할 WCF (Windows Communication Foundation 유형을 결정 하는 라우팅 필터 집합을 정의 하는 구성 섹션입니다.</span><span class="sxs-lookup"><span data-stu-id="eb2af-127">A configuration section for defining a set of routing filters, which determine the type of Windows Communication Foundation (WCF)<xref:System.ServiceModel.Dispatcher.MessageFilter> to be used when evaluating incoming messages.</span></span> |

## <a name="see-also"></a><span data-ttu-id="eb2af-128">참고 항목</span><span class="sxs-lookup"><span data-stu-id="eb2af-128">See also</span></span>

- <xref:System.ServiceModel.Routing.Configuration.FilterElement?displayProperty=nameWithType>
- <xref:System.ServiceModel.Routing.Configuration.FilterElement.FilterData%2A?displayProperty=nameWithType>
- <xref:System.ServiceModel.Routing.Configuration.FilterType?displayProperty=nameWithType>
