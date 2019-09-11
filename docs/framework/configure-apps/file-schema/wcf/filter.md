---
title: <filter>
ms.date: 03/30/2017
ms.assetid: 3266700b-904b-44e4-93a7-e06a1a445100
ms.openlocfilehash: 6e78275aaeb202405e327302455d56fa431d7f27
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/10/2019
ms.locfileid: "70855253"
---
# <a name="filter"></a><span data-ttu-id="e8184-101">\<filter></span><span class="sxs-lookup"><span data-stu-id="e8184-101">\<filter></span></span>

<span data-ttu-id="e8184-102">들어오는 메시지를 평가할 때 사용할 WCF (Windows Communication Foundation 형식)<xref:System.ServiceModel.Dispatcher.MessageFilter> 와 필터에 필요한 지원 데이터 나 매개 변수를 결정 하는 라우팅 필터를 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="e8184-102">Defines a routing filter, which determines the type of Windows Communication Foundation (WCF)<xref:System.ServiceModel.Dispatcher.MessageFilter> to be used when evaluating incoming messages, as well any supporting data or parameters required by the filter.</span></span>

<span data-ttu-id="e8184-103">[ **\<system.serviceModel>** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="e8184-103">[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="e8184-104">&nbsp;&nbsp;[ **\<routing>** ](routing.md)</span><span class="sxs-lookup"><span data-stu-id="e8184-104">&nbsp;&nbsp;[**\<routing>**](routing.md)</span></span>\
<span data-ttu-id="e8184-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<필터 >** ](filters-of-routing.md)</span><span class="sxs-lookup"><span data-stu-id="e8184-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<filters>**](filters-of-routing.md)</span></span>\
<span data-ttu-id="e8184-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<필터 >**</span><span class="sxs-lookup"><span data-stu-id="e8184-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<filter>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e8184-107">구문</span><span class="sxs-lookup"><span data-stu-id="e8184-107">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e8184-108">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="e8184-108">Attributes and elements</span></span>

<span data-ttu-id="e8184-109">다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="e8184-109">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="e8184-110">특성</span><span class="sxs-lookup"><span data-stu-id="e8184-110">Attributes</span></span>

| <span data-ttu-id="e8184-111">특성</span><span class="sxs-lookup"><span data-stu-id="e8184-111">Attribute</span></span>  | <span data-ttu-id="e8184-112">Description</span><span class="sxs-lookup"><span data-stu-id="e8184-112">Description</span></span> |
| ---------- | ----------- |
| <span data-ttu-id="e8184-113">customType</span><span class="sxs-lookup"><span data-stu-id="e8184-113">customType</span></span> | <span data-ttu-id="e8184-114">필터로 사용할 사용자 지정 형식의 정규화된 형식 이름을 포함하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="e8184-114">A string containing the fully qualified type name of the custom type to be used as a filter.</span></span> <span data-ttu-id="e8184-115">가 `filterType` 로`custom`설정 된 경우이 특성은 만들 클래스의 정규화 된 형식 이름을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="e8184-115">If `filterType` is set to `custom`, this attribute contains the fully qualified type name of the class to create.</span></span>  <span data-ttu-id="e8184-116">`filterData`사용자 지정 형식 필터를 평가 하는 동안 사용할 값도 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e8184-116">`filterData` may also contain values to be used during evaluation of the custom type filter.</span></span> |
| <span data-ttu-id="e8184-117">filterData</span><span class="sxs-lookup"><span data-stu-id="e8184-117">filterData</span></span> | <span data-ttu-id="e8184-118">필터 데이터를 포함하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="e8184-118">A string containing the filter data.</span></span> <span data-ttu-id="e8184-119">이 특성을 지정하는 방법에 대한 자세한 내용은 <xref:System.ServiceModel.Routing.Configuration.FilterElement.FilterData%2A>를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="e8184-119">For more information on how to specify this attribute, see <xref:System.ServiceModel.Routing.Configuration.FilterElement.FilterData%2A>.</span></span> |
| <span data-ttu-id="e8184-120">filterType</span><span class="sxs-lookup"><span data-stu-id="e8184-120">filterType</span></span> | <span data-ttu-id="e8184-121">필터 형식을 포함하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="e8184-121">A string containing the filter type.</span></span> <span data-ttu-id="e8184-122">이 특성은 <xref:System.ServiceModel.Routing.Configuration.FilterType> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="e8184-122">This attribute is of <xref:System.ServiceModel.Routing.Configuration.FilterType> type.</span></span>  <span data-ttu-id="e8184-123">`filterData` 특성에서 이 형식이 어떻게 작동하는지에 대한 자세한 내용은 <xref:System.ServiceModel.Routing.Configuration.FilterElement.FilterData%2A>를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="e8184-123">For more information on how this works with the `filterData` attribute, see <xref:System.ServiceModel.Routing.Configuration.FilterElement.FilterData%2A>.</span></span> |
| <span data-ttu-id="e8184-124">name</span><span class="sxs-lookup"><span data-stu-id="e8184-124">name</span></span>       | <span data-ttu-id="e8184-125">이 필터 요소의 고유 이름을 포함하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="e8184-125">A string containing the unique name of this filter element.</span></span> |

### <a name="child-elements"></a><span data-ttu-id="e8184-126">자식 요소</span><span class="sxs-lookup"><span data-stu-id="e8184-126">Child elements</span></span>

<span data-ttu-id="e8184-127">없음</span><span class="sxs-lookup"><span data-stu-id="e8184-127">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="e8184-128">부모 요소</span><span class="sxs-lookup"><span data-stu-id="e8184-128">Parent elements</span></span>

| <span data-ttu-id="e8184-129">요소</span><span class="sxs-lookup"><span data-stu-id="e8184-129">Element</span></span> | <span data-ttu-id="e8184-130">Description</span><span class="sxs-lookup"><span data-stu-id="e8184-130">Description</span></span> |
| ------- | ----------- |
| [<span data-ttu-id="e8184-131">\<routing></span><span class="sxs-lookup"><span data-stu-id="e8184-131">\<routing></span></span>](routing.md) | <span data-ttu-id="e8184-132">들어오는 메시지를 평가할 때 사용할 WCF<xref:System.ServiceModel.Dispatcher.MessageFilter> (Windows Communication Foundation 유형을 결정 하는 라우팅 필터 집합을 정의 하는 구성 섹션입니다.</span><span class="sxs-lookup"><span data-stu-id="e8184-132">A configuration section for defining a set of routing filters, which determine the type of Windows Communication Foundation (WCF)<xref:System.ServiceModel.Dispatcher.MessageFilter> to be used when evaluating incoming messages.</span></span> |

## <a name="see-also"></a><span data-ttu-id="e8184-133">참고자료</span><span class="sxs-lookup"><span data-stu-id="e8184-133">See also</span></span>

- <xref:System.ServiceModel.Routing.Configuration.FilterElement?displayProperty=nameWithType>
- <xref:System.ServiceModel.Routing.Configuration.FilterElement.FilterData%2A?displayProperty=nameWithType>
- <xref:System.ServiceModel.Routing.Configuration.FilterType?displayProperty=nameWithType>
