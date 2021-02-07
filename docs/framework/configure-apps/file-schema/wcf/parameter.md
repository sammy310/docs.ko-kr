---
description: 다음에 대해 자세히 알아보세요. <parameter>
title: <parameter>
ms.date: 03/30/2017
ms.assetid: 0fb41e2d-64f7-44ab-993e-05892eac6d82
ms.openlocfilehash: fb04cfb5bf451cdb99c23ae41ea8fafeb13f0d11
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99683816"
---
# \<parameter>

<span data-ttu-id="470c9-102">선언된 형식이 제네릭 형식이면 제네릭 매개 변수를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="470c9-102">Specifies the generic parameter when a declared type is a generic type.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.runtime.serialization>**](system-runtime-serialization.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<dataContractSerializer>**](datacontractserializer.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<declaredTypes>**](declaredtypes.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<add>**](add-of-declaredtypes-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<knownType>**](knowntype.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<parameter>**  
  
## <a name="syntax"></a><span data-ttu-id="470c9-103">구문</span><span class="sxs-lookup"><span data-stu-id="470c9-103">Syntax</span></span>  
  
```xml  
<parameter index="Integer"
           type="String" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="470c9-104">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="470c9-104">Attributes and Elements</span></span>  

 <span data-ttu-id="470c9-105">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="470c9-105">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="470c9-106">특성</span><span class="sxs-lookup"><span data-stu-id="470c9-106">Attributes</span></span>  
  
|<span data-ttu-id="470c9-107">attribute</span><span class="sxs-lookup"><span data-stu-id="470c9-107">Attribute</span></span>|<span data-ttu-id="470c9-108">Description</span><span class="sxs-lookup"><span data-stu-id="470c9-108">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="470c9-109">인덱스</span><span class="sxs-lookup"><span data-stu-id="470c9-109">index</span></span>|<span data-ttu-id="470c9-110">선언된 형식이 제네릭 형식이면 알려진 형식을 반환하는 제네릭 매개 변수를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="470c9-110">When the declared type is a generic type, specifies the generic parameter that will return the known type.</span></span>|  
|<span data-ttu-id="470c9-111">형식</span><span class="sxs-lookup"><span data-stu-id="470c9-111">type</span></span>|<span data-ttu-id="470c9-112">serialization 및 deserialization에 사용되는 알려진 형식을 설명하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="470c9-112">A string that describes the known type used for serialization and deserialization.</span></span>|  
  
## <a name="index-attribute"></a><span data-ttu-id="470c9-113">index 특성</span><span class="sxs-lookup"><span data-stu-id="470c9-113">index Attribute</span></span>  
  
|<span data-ttu-id="470c9-114">값</span><span class="sxs-lookup"><span data-stu-id="470c9-114">Value</span></span>|<span data-ttu-id="470c9-115">설명</span><span class="sxs-lookup"><span data-stu-id="470c9-115">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="470c9-116">"0"</span><span class="sxs-lookup"><span data-stu-id="470c9-116">"0"</span></span>|<span data-ttu-id="470c9-117">제네릭 형식의 첫 번째 매개 변수입니다.</span><span class="sxs-lookup"><span data-stu-id="470c9-117">The first parameter in the generic type.</span></span> <span data-ttu-id="470c9-118">예를 들어, <xref:System.Collections.Generic.List%601>에는 하나의 매개 변수만 있습니다.</span><span class="sxs-lookup"><span data-stu-id="470c9-118">For example, a <xref:System.Collections.Generic.List%601> has only one parameter.</span></span> <span data-ttu-id="470c9-119">이 형식이 선언된 형식으로 사용되면 index가 "0"으로 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="470c9-119">If it is used as the declared type, the index would be set to "0".</span></span>|  
|<span data-ttu-id="470c9-120">"1"</span><span class="sxs-lookup"><span data-stu-id="470c9-120">"1"</span></span>|<span data-ttu-id="470c9-121">제네릭 형식의 두 번째 매개 변수입니다.</span><span class="sxs-lookup"><span data-stu-id="470c9-121">The second parameter in a generic type.</span></span> <span data-ttu-id="470c9-122">예를 들어, <xref:System.Collections.Generic.Dictionary%602>에는 두 개의 매개 변수가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="470c9-122">For example, a <xref:System.Collections.Generic.Dictionary%602> has two parameters.</span></span> <span data-ttu-id="470c9-123">이 알려진 형식이 두 번째 매개 변수에서 반환되면 index 특성을 "1"로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="470c9-123">If the known type is returned by the second parameter, set the index attribute to "1".</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="470c9-124">자식 요소</span><span class="sxs-lookup"><span data-stu-id="470c9-124">Child Elements</span></span>  

 <span data-ttu-id="470c9-125">없음</span><span class="sxs-lookup"><span data-stu-id="470c9-125">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="470c9-126">부모 요소</span><span class="sxs-lookup"><span data-stu-id="470c9-126">Parent Elements</span></span>  
  
|<span data-ttu-id="470c9-127">요소</span><span class="sxs-lookup"><span data-stu-id="470c9-127">Element</span></span>|<span data-ttu-id="470c9-128">설명</span><span class="sxs-lookup"><span data-stu-id="470c9-128">Description</span></span>|  
|-------------|-----------------|  
|[\<knownType>](knowntype.md)|<span data-ttu-id="470c9-129">선언된 형식의 필드 또는 속성에서 반환될 수 있는 알려진 형식을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="470c9-129">Specifies a known type that can be returned by a field or property of the declared type.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="470c9-130">설명</span><span class="sxs-lookup"><span data-stu-id="470c9-130">Remarks</span></span>  

 <span data-ttu-id="470c9-131">알려진 형식에 대 한 자세한 내용은 [데이터 계약 알려진 형식](../../../wcf/feature-details/data-contract-known-types.md) 및을 참조 하십시오 <xref:System.Runtime.Serialization.DataContractSerializer> .</span><span class="sxs-lookup"><span data-stu-id="470c9-131">For more information about known types, see [Data Contract Known Types](../../../wcf/feature-details/data-contract-known-types.md) and <xref:System.Runtime.Serialization.DataContractSerializer>.</span></span>  
  
 <span data-ttu-id="470c9-132">이 요소를 사용 하는 예제는를 참조 하십시오 [\<dataContractSerializer>](datacontractserializer-element.md) .</span><span class="sxs-lookup"><span data-stu-id="470c9-132">See the [\<dataContractSerializer>](datacontractserializer-element.md) for an example of using this element.</span></span>  
  
 <span data-ttu-id="470c9-133">이 구성 요소는 두 가지 특성을 동시에 가질 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="470c9-133">This configuration element cannot have both attributes at the same time.</span></span> <span data-ttu-id="470c9-134">두 가지 특성이 모두 설정되면 <xref:System.Configuration.ConfigurationErrorsException>이 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="470c9-134">If both attributes are set, a <xref:System.Configuration.ConfigurationErrorsException> occurs.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="470c9-135">참고 항목</span><span class="sxs-lookup"><span data-stu-id="470c9-135">See also</span></span>

- <xref:System.Runtime.Serialization.DataContractSerializer>
- [<span data-ttu-id="470c9-136">데이터 계약 알려진 형식</span><span class="sxs-lookup"><span data-stu-id="470c9-136">Data Contract Known Types</span></span>](../../../wcf/feature-details/data-contract-known-types.md)
- [\<dataContractSerializer>](datacontractserializer-element.md)
- [\<add>](add-of-declaredtypes-element.md)
