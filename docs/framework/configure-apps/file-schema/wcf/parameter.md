---
title: <parameter>
ms.date: 03/30/2017
ms.assetid: 0fb41e2d-64f7-44ab-993e-05892eac6d82
ms.openlocfilehash: 2ef674dc8601bc9afaf6b547265988bb8a99f943
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/24/2020
ms.locfileid: "91170170"
---
# \<parameter>

<span data-ttu-id="a4ba4-101">선언된 형식이 제네릭 형식이면 제네릭 매개 변수를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="a4ba4-101">Specifies the generic parameter when a declared type is a generic type.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.runtime.serialization>**](system-runtime-serialization.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<dataContractSerializer>**](datacontractserializer.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<declaredTypes>**](declaredtypes.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<add>**](add-of-declaredtypes-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<knownType>**](knowntype.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<parameter>**  
  
## <a name="syntax"></a><span data-ttu-id="a4ba4-102">구문</span><span class="sxs-lookup"><span data-stu-id="a4ba4-102">Syntax</span></span>  
  
```xml  
<parameter index="Integer"
           type="String" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="a4ba4-103">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="a4ba4-103">Attributes and Elements</span></span>  

 <span data-ttu-id="a4ba4-104">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="a4ba4-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="a4ba4-105">특성</span><span class="sxs-lookup"><span data-stu-id="a4ba4-105">Attributes</span></span>  
  
|<span data-ttu-id="a4ba4-106">attribute</span><span class="sxs-lookup"><span data-stu-id="a4ba4-106">Attribute</span></span>|<span data-ttu-id="a4ba4-107">Description</span><span class="sxs-lookup"><span data-stu-id="a4ba4-107">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="a4ba4-108">인덱스</span><span class="sxs-lookup"><span data-stu-id="a4ba4-108">index</span></span>|<span data-ttu-id="a4ba4-109">선언된 형식이 제네릭 형식이면 알려진 형식을 반환하는 제네릭 매개 변수를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="a4ba4-109">When the declared type is a generic type, specifies the generic parameter that will return the known type.</span></span>|  
|<span data-ttu-id="a4ba4-110">형식</span><span class="sxs-lookup"><span data-stu-id="a4ba4-110">type</span></span>|<span data-ttu-id="a4ba4-111">serialization 및 deserialization에 사용되는 알려진 형식을 설명하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="a4ba4-111">A string that describes the known type used for serialization and deserialization.</span></span>|  
  
## <a name="index-attribute"></a><span data-ttu-id="a4ba4-112">index 특성</span><span class="sxs-lookup"><span data-stu-id="a4ba4-112">index Attribute</span></span>  
  
|<span data-ttu-id="a4ba4-113">Value</span><span class="sxs-lookup"><span data-stu-id="a4ba4-113">Value</span></span>|<span data-ttu-id="a4ba4-114">설명</span><span class="sxs-lookup"><span data-stu-id="a4ba4-114">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="a4ba4-115">"0"</span><span class="sxs-lookup"><span data-stu-id="a4ba4-115">"0"</span></span>|<span data-ttu-id="a4ba4-116">제네릭 형식의 첫 번째 매개 변수입니다.</span><span class="sxs-lookup"><span data-stu-id="a4ba4-116">The first parameter in the generic type.</span></span> <span data-ttu-id="a4ba4-117">예를 들어, <xref:System.Collections.Generic.List%601>에는 하나의 매개 변수만 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a4ba4-117">For example, a <xref:System.Collections.Generic.List%601> has only one parameter.</span></span> <span data-ttu-id="a4ba4-118">이 형식이 선언된 형식으로 사용되면 index가 "0"으로 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="a4ba4-118">If it is used as the declared type, the index would be set to "0".</span></span>|  
|<span data-ttu-id="a4ba4-119">"1"</span><span class="sxs-lookup"><span data-stu-id="a4ba4-119">"1"</span></span>|<span data-ttu-id="a4ba4-120">제네릭 형식의 두 번째 매개 변수입니다.</span><span class="sxs-lookup"><span data-stu-id="a4ba4-120">The second parameter in a generic type.</span></span> <span data-ttu-id="a4ba4-121">예를 들어, <xref:System.Collections.Generic.Dictionary%602>에는 두 개의 매개 변수가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a4ba4-121">For example, a <xref:System.Collections.Generic.Dictionary%602> has two parameters.</span></span> <span data-ttu-id="a4ba4-122">이 알려진 형식이 두 번째 매개 변수에서 반환되면 index 특성을 "1"로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="a4ba4-122">If the known type is returned by the second parameter, set the index attribute to "1".</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="a4ba4-123">자식 요소</span><span class="sxs-lookup"><span data-stu-id="a4ba4-123">Child Elements</span></span>  

 <span data-ttu-id="a4ba4-124">없음</span><span class="sxs-lookup"><span data-stu-id="a4ba4-124">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="a4ba4-125">부모 요소</span><span class="sxs-lookup"><span data-stu-id="a4ba4-125">Parent Elements</span></span>  
  
|<span data-ttu-id="a4ba4-126">요소</span><span class="sxs-lookup"><span data-stu-id="a4ba4-126">Element</span></span>|<span data-ttu-id="a4ba4-127">설명</span><span class="sxs-lookup"><span data-stu-id="a4ba4-127">Description</span></span>|  
|-------------|-----------------|  
|[\<knownType>](knowntype.md)|<span data-ttu-id="a4ba4-128">선언된 형식의 필드 또는 속성에서 반환될 수 있는 알려진 형식을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="a4ba4-128">Specifies a known type that can be returned by a field or property of the declared type.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a4ba4-129">설명</span><span class="sxs-lookup"><span data-stu-id="a4ba4-129">Remarks</span></span>  

 <span data-ttu-id="a4ba4-130">알려진 형식에 대 한 자세한 내용은 [데이터 계약 알려진 형식](../../../wcf/feature-details/data-contract-known-types.md) 및을 참조 하십시오 <xref:System.Runtime.Serialization.DataContractSerializer> .</span><span class="sxs-lookup"><span data-stu-id="a4ba4-130">For more information about known types, see [Data Contract Known Types](../../../wcf/feature-details/data-contract-known-types.md) and <xref:System.Runtime.Serialization.DataContractSerializer>.</span></span>  
  
 <span data-ttu-id="a4ba4-131">이 요소를 사용 하는 예제는를 참조 하십시오 [\<dataContractSerializer>](datacontractserializer-element.md) .</span><span class="sxs-lookup"><span data-stu-id="a4ba4-131">See the [\<dataContractSerializer>](datacontractserializer-element.md) for an example of using this element.</span></span>  
  
 <span data-ttu-id="a4ba4-132">이 구성 요소는 두 가지 특성을 동시에 가질 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a4ba4-132">This configuration element cannot have both attributes at the same time.</span></span> <span data-ttu-id="a4ba4-133">두 가지 특성이 모두 설정되면 <xref:System.Configuration.ConfigurationErrorsException>이 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="a4ba4-133">If both attributes are set, a <xref:System.Configuration.ConfigurationErrorsException> occurs.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a4ba4-134">참고 항목</span><span class="sxs-lookup"><span data-stu-id="a4ba4-134">See also</span></span>

- <xref:System.Runtime.Serialization.DataContractSerializer>
- [<span data-ttu-id="a4ba4-135">데이터 계약 알려진 형식</span><span class="sxs-lookup"><span data-stu-id="a4ba4-135">Data Contract Known Types</span></span>](../../../wcf/feature-details/data-contract-known-types.md)
- [\<dataContractSerializer>](datacontractserializer-element.md)
- [\<add>](add-of-declaredtypes-element.md)
