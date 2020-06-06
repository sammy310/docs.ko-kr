---
title: <filter>
ms.date: 03/30/2017
ms.assetid: 3266700b-904b-44e4-93a7-e06a1a445100
ms.openlocfilehash: 6e78275aaeb202405e327302455d56fa431d7f27
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/06/2020
ms.locfileid: "70855253"
---
# \<filter>

<span data-ttu-id="6b86f-101">들어오는 메시지를 평가할 때 사용할 WCF (Windows Communication Foundation 형식)와 필터에 <xref:System.ServiceModel.Dispatcher.MessageFilter> 필요한 지원 데이터 나 매개 변수를 결정 하는 라우팅 필터를 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="6b86f-101">Defines a routing filter, which determines the type of Windows Communication Foundation (WCF)<xref:System.ServiceModel.Dispatcher.MessageFilter> to be used when evaluating incoming messages, as well any supporting data or parameters required by the filter.</span></span>

[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;[**\<routing>**](routing.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<filters>**](filters-of-routing.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<filter>**  
  
## <a name="syntax"></a><span data-ttu-id="6b86f-102">구문</span><span class="sxs-lookup"><span data-stu-id="6b86f-102">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="6b86f-103">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="6b86f-103">Attributes and elements</span></span>

<span data-ttu-id="6b86f-104">다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="6b86f-104">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="6b86f-105">특성</span><span class="sxs-lookup"><span data-stu-id="6b86f-105">Attributes</span></span>

| <span data-ttu-id="6b86f-106">attribute</span><span class="sxs-lookup"><span data-stu-id="6b86f-106">Attribute</span></span>  | <span data-ttu-id="6b86f-107">Description</span><span class="sxs-lookup"><span data-stu-id="6b86f-107">Description</span></span> |
| ---------- | ----------- |
| <span data-ttu-id="6b86f-108">customType</span><span class="sxs-lookup"><span data-stu-id="6b86f-108">customType</span></span> | <span data-ttu-id="6b86f-109">필터로 사용할 사용자 지정 형식의 정규화된 형식 이름을 포함하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="6b86f-109">A string containing the fully qualified type name of the custom type to be used as a filter.</span></span> <span data-ttu-id="6b86f-110">`filterType`가로 설정 된 경우 `custom` 이 특성은 만들 클래스의 정규화 된 형식 이름을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="6b86f-110">If `filterType` is set to `custom`, this attribute contains the fully qualified type name of the class to create.</span></span>  <span data-ttu-id="6b86f-111">`filterData`사용자 지정 형식 필터를 평가 하는 동안 사용할 값도 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6b86f-111">`filterData` may also contain values to be used during evaluation of the custom type filter.</span></span> |
| <span data-ttu-id="6b86f-112">filterData</span><span class="sxs-lookup"><span data-stu-id="6b86f-112">filterData</span></span> | <span data-ttu-id="6b86f-113">필터 데이터를 포함하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="6b86f-113">A string containing the filter data.</span></span> <span data-ttu-id="6b86f-114">이 특성을 지정하는 방법에 대한 자세한 내용은 <xref:System.ServiceModel.Routing.Configuration.FilterElement.FilterData%2A>를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="6b86f-114">For more information on how to specify this attribute, see <xref:System.ServiceModel.Routing.Configuration.FilterElement.FilterData%2A>.</span></span> |
| <span data-ttu-id="6b86f-115">filterType</span><span class="sxs-lookup"><span data-stu-id="6b86f-115">filterType</span></span> | <span data-ttu-id="6b86f-116">필터 형식을 포함하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="6b86f-116">A string containing the filter type.</span></span> <span data-ttu-id="6b86f-117">이 특성은 <xref:System.ServiceModel.Routing.Configuration.FilterType> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="6b86f-117">This attribute is of <xref:System.ServiceModel.Routing.Configuration.FilterType> type.</span></span>  <span data-ttu-id="6b86f-118">`filterData` 특성에서 이 형식이 어떻게 작동하는지에 대한 자세한 내용은 <xref:System.ServiceModel.Routing.Configuration.FilterElement.FilterData%2A>를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="6b86f-118">For more information on how this works with the `filterData` attribute, see <xref:System.ServiceModel.Routing.Configuration.FilterElement.FilterData%2A>.</span></span> |
| <span data-ttu-id="6b86f-119">name</span><span class="sxs-lookup"><span data-stu-id="6b86f-119">name</span></span>       | <span data-ttu-id="6b86f-120">이 필터 요소의 고유 이름을 포함하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="6b86f-120">A string containing the unique name of this filter element.</span></span> |

### <a name="child-elements"></a><span data-ttu-id="6b86f-121">자식 요소</span><span class="sxs-lookup"><span data-stu-id="6b86f-121">Child elements</span></span>

<span data-ttu-id="6b86f-122">없음</span><span class="sxs-lookup"><span data-stu-id="6b86f-122">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="6b86f-123">부모 요소</span><span class="sxs-lookup"><span data-stu-id="6b86f-123">Parent elements</span></span>

| <span data-ttu-id="6b86f-124">요소</span><span class="sxs-lookup"><span data-stu-id="6b86f-124">Element</span></span> | <span data-ttu-id="6b86f-125">Description</span><span class="sxs-lookup"><span data-stu-id="6b86f-125">Description</span></span> |
| ------- | ----------- |
| [\<routing>](routing.md) | <span data-ttu-id="6b86f-126"><xref:System.ServiceModel.Dispatcher.MessageFilter>들어오는 메시지를 평가할 때 사용할 WCF (Windows Communication Foundation 유형을 결정 하는 라우팅 필터 집합을 정의 하는 구성 섹션입니다.</span><span class="sxs-lookup"><span data-stu-id="6b86f-126">A configuration section for defining a set of routing filters, which determine the type of Windows Communication Foundation (WCF)<xref:System.ServiceModel.Dispatcher.MessageFilter> to be used when evaluating incoming messages.</span></span> |

## <a name="see-also"></a><span data-ttu-id="6b86f-127">참고 항목</span><span class="sxs-lookup"><span data-stu-id="6b86f-127">See also</span></span>

- <xref:System.ServiceModel.Routing.Configuration.FilterElement?displayProperty=nameWithType>
- <xref:System.ServiceModel.Routing.Configuration.FilterElement.FilterData%2A?displayProperty=nameWithType>
- <xref:System.ServiceModel.Routing.Configuration.FilterType?displayProperty=nameWithType>
