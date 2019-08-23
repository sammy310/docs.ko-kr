---
title: <filter>
ms.date: 03/30/2017
ms.assetid: 3266700b-904b-44e4-93a7-e06a1a445100
ms.openlocfilehash: 68de255b9f11dc4377159d1cc3efa575633db316
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/22/2019
ms.locfileid: "69918890"
---
# <a name="filter"></a><span data-ttu-id="d209f-101">\<filter></span><span class="sxs-lookup"><span data-stu-id="d209f-101">\<filter></span></span>

<span data-ttu-id="d209f-102">들어오는 메시지를 평가할 때 사용할 WCF (Windows Communication Foundation 형식)<xref:System.ServiceModel.Dispatcher.MessageFilter> 와 필터에 필요한 지원 데이터 나 매개 변수를 결정 하는 라우팅 필터를 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="d209f-102">Defines a routing filter, which determines the type of Windows Communication Foundation (WCF)<xref:System.ServiceModel.Dispatcher.MessageFilter> to be used when evaluating incoming messages, as well any supporting data or parameters required by the filter.</span></span>

<span data-ttu-id="d209f-103">\<system.serviceModel> \<routing> \<filters> \<filter></span><span class="sxs-lookup"><span data-stu-id="d209f-103">\<system.serviceModel> \<routing> \<filters> \<filter></span></span>
  
## <a name="syntax"></a><span data-ttu-id="d209f-104">구문</span><span class="sxs-lookup"><span data-stu-id="d209f-104">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="d209f-105">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="d209f-105">Attributes and elements</span></span>

<span data-ttu-id="d209f-106">다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="d209f-106">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="d209f-107">특성</span><span class="sxs-lookup"><span data-stu-id="d209f-107">Attributes</span></span>

| <span data-ttu-id="d209f-108">특성</span><span class="sxs-lookup"><span data-stu-id="d209f-108">Attribute</span></span>  | <span data-ttu-id="d209f-109">Description</span><span class="sxs-lookup"><span data-stu-id="d209f-109">Description</span></span> |
| ---------- | ----------- |
| <span data-ttu-id="d209f-110">customType</span><span class="sxs-lookup"><span data-stu-id="d209f-110">customType</span></span> | <span data-ttu-id="d209f-111">필터로 사용할 사용자 지정 형식의 정규화된 형식 이름을 포함하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="d209f-111">A string containing the fully qualified type name of the custom type to be used as a filter.</span></span> <span data-ttu-id="d209f-112">가 `filterType` 로`custom`설정 된 경우이 특성은 만들 클래스의 정규화 된 형식 이름을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="d209f-112">If `filterType` is set to `custom`, this attribute contains the fully qualified type name of the class to create.</span></span>  <span data-ttu-id="d209f-113">`filterData`사용자 지정 형식 필터를 평가 하는 동안 사용할 값도 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d209f-113">`filterData` may also contain values to be used during evaluation of the custom type filter.</span></span> |
| <span data-ttu-id="d209f-114">filterData</span><span class="sxs-lookup"><span data-stu-id="d209f-114">filterData</span></span> | <span data-ttu-id="d209f-115">필터 데이터를 포함하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="d209f-115">A string containing the filter data.</span></span> <span data-ttu-id="d209f-116">이 특성을 지정하는 방법에 대한 자세한 내용은 <xref:System.ServiceModel.Routing.Configuration.FilterElement.FilterData%2A>를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d209f-116">For more information on how to specify this attribute, see <xref:System.ServiceModel.Routing.Configuration.FilterElement.FilterData%2A>.</span></span> |
| <span data-ttu-id="d209f-117">filterType</span><span class="sxs-lookup"><span data-stu-id="d209f-117">filterType</span></span> | <span data-ttu-id="d209f-118">필터 형식을 포함하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="d209f-118">A string containing the filter type.</span></span> <span data-ttu-id="d209f-119">이 특성은 <xref:System.ServiceModel.Routing.Configuration.FilterType> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="d209f-119">This attribute is of <xref:System.ServiceModel.Routing.Configuration.FilterType> type.</span></span>  <span data-ttu-id="d209f-120">`filterData` 특성에서 이 형식이 어떻게 작동하는지에 대한 자세한 내용은 <xref:System.ServiceModel.Routing.Configuration.FilterElement.FilterData%2A>를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d209f-120">For more information on how this works with the `filterData` attribute, see <xref:System.ServiceModel.Routing.Configuration.FilterElement.FilterData%2A>.</span></span> |
| <span data-ttu-id="d209f-121">name</span><span class="sxs-lookup"><span data-stu-id="d209f-121">name</span></span>       | <span data-ttu-id="d209f-122">이 필터 요소의 고유 이름을 포함하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="d209f-122">A string containing the unique name of this filter element.</span></span> |

### <a name="child-elements"></a><span data-ttu-id="d209f-123">자식 요소</span><span class="sxs-lookup"><span data-stu-id="d209f-123">Child elements</span></span>

<span data-ttu-id="d209f-124">없음</span><span class="sxs-lookup"><span data-stu-id="d209f-124">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="d209f-125">부모 요소</span><span class="sxs-lookup"><span data-stu-id="d209f-125">Parent elements</span></span>

| <span data-ttu-id="d209f-126">요소</span><span class="sxs-lookup"><span data-stu-id="d209f-126">Element</span></span> | <span data-ttu-id="d209f-127">Description</span><span class="sxs-lookup"><span data-stu-id="d209f-127">Description</span></span> |
| ------- | ----------- |
| [<span data-ttu-id="d209f-128">\<routing></span><span class="sxs-lookup"><span data-stu-id="d209f-128">\<routing></span></span>](routing.md) | <span data-ttu-id="d209f-129">들어오는 메시지를 평가할 때 사용할 WCF<xref:System.ServiceModel.Dispatcher.MessageFilter> (Windows Communication Foundation 유형을 결정 하는 라우팅 필터 집합을 정의 하는 구성 섹션입니다.</span><span class="sxs-lookup"><span data-stu-id="d209f-129">A configuration section for defining a set of routing filters, which determine the type of Windows Communication Foundation (WCF)<xref:System.ServiceModel.Dispatcher.MessageFilter> to be used when evaluating incoming messages.</span></span> |

## <a name="see-also"></a><span data-ttu-id="d209f-130">참고자료</span><span class="sxs-lookup"><span data-stu-id="d209f-130">See also</span></span>

- <xref:System.ServiceModel.Routing.Configuration.FilterElement?displayProperty=nameWithType>
- <xref:System.ServiceModel.Routing.Configuration.FilterElement.FilterData%2A?displayProperty=nameWithType>
- <xref:System.ServiceModel.Routing.Configuration.FilterType?displayProperty=nameWithType>
