---
title: <knownType>
ms.date: 03/30/2017
ms.assetid: ee2b7be3-7148-4a3a-b861-48e7330615e5
ms.openlocfilehash: a0794314cfcb87df00d66b6832356fb130787eba
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/22/2019
ms.locfileid: "69928862"
---
# <a name="knowntype"></a><span data-ttu-id="60e22-101">\<knownType></span><span class="sxs-lookup"><span data-stu-id="60e22-101">\<knownType></span></span>
<span data-ttu-id="60e22-102">deserialization을 수행하는 동안 <xref:System.Runtime.Serialization.DataContractSerializer>에서 사용하는 형식을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="60e22-102">Specifies a type to be used by <xref:System.Runtime.Serialization.DataContractSerializer> during deserialization.</span></span> <span data-ttu-id="60e22-103">요소는 "선언된 형식"의 필드 또는 속성에서 반환하는 "알려진 형식"을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="60e22-103">The element specifies a "known type" that is returned by a field or property of a "declared type."</span></span> <span data-ttu-id="60e22-104">자세한 내용은 [데이터 계약 알려진 형식을](../../../wcf/feature-details/data-contract-known-types.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="60e22-104">For more information, see [Data Contract Known Types](../../../wcf/feature-details/data-contract-known-types.md).</span></span>  
  
 <span data-ttu-id="60e22-105">\<system.runtime.serialization></span><span class="sxs-lookup"><span data-stu-id="60e22-105">\<system.runtime.serialization></span></span>  
<span data-ttu-id="60e22-106">\<dataContractSerializer></span><span class="sxs-lookup"><span data-stu-id="60e22-106">\<dataContractSerializer></span></span>  
<span data-ttu-id="60e22-107">\<declaredTypes > 요소</span><span class="sxs-lookup"><span data-stu-id="60e22-107">\<declaredTypes> Element</span></span>  
<span data-ttu-id="60e22-108">\<\<declaredTypes > > 추가</span><span class="sxs-lookup"><span data-stu-id="60e22-108">\<add> of \<declaredTypes></span></span>  
<span data-ttu-id="60e22-109">\<knownType > 요소</span><span class="sxs-lookup"><span data-stu-id="60e22-109">\<knownType> Element</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="60e22-110">구문</span><span class="sxs-lookup"><span data-stu-id="60e22-110">Syntax</span></span>  
  
```xml  
<knownType type="String">
  <parameter index="Integer"
             type="String" />
</knownType>
```  
  
## <a name="type"></a><span data-ttu-id="60e22-111">형식</span><span class="sxs-lookup"><span data-stu-id="60e22-111">Type</span></span>  
 `string`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="60e22-112">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="60e22-112">Attributes and Elements</span></span>  
 <span data-ttu-id="60e22-113">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="60e22-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="60e22-114">특성</span><span class="sxs-lookup"><span data-stu-id="60e22-114">Attributes</span></span>  
  
|<span data-ttu-id="60e22-115">특성</span><span class="sxs-lookup"><span data-stu-id="60e22-115">Attribute</span></span>|<span data-ttu-id="60e22-116">Description</span><span class="sxs-lookup"><span data-stu-id="60e22-116">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="60e22-117">type</span><span class="sxs-lookup"><span data-stu-id="60e22-117">type</span></span>|<span data-ttu-id="60e22-118">형식(네임스페이스 포함), 어셈블리 이름, 버전, 문화권 및 공개 키 토큰을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="60e22-118">Specifies the type (including namespace), assembly name, version, culture, and public key token.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="60e22-119">자식 요소</span><span class="sxs-lookup"><span data-stu-id="60e22-119">Child Elements</span></span>  
  
|<span data-ttu-id="60e22-120">요소</span><span class="sxs-lookup"><span data-stu-id="60e22-120">Element</span></span>|<span data-ttu-id="60e22-121">Description</span><span class="sxs-lookup"><span data-stu-id="60e22-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="60e22-122">\<parameter></span><span class="sxs-lookup"><span data-stu-id="60e22-122">\<parameter></span></span>](parameter.md)|<span data-ttu-id="60e22-123">선언된 형식이 제네릭 형식이면 매개 변수 인덱스를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="60e22-123">Specifies a parameter index when the declared type is a generic type.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="60e22-124">부모 요소</span><span class="sxs-lookup"><span data-stu-id="60e22-124">Parent Elements</span></span>  
  
|<span data-ttu-id="60e22-125">요소</span><span class="sxs-lookup"><span data-stu-id="60e22-125">Element</span></span>|<span data-ttu-id="60e22-126">설명</span><span class="sxs-lookup"><span data-stu-id="60e22-126">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="60e22-127">\<add></span><span class="sxs-lookup"><span data-stu-id="60e22-127">\<add></span></span>](add-of-declaredtypes-element.md)|<span data-ttu-id="60e22-128">선언된 형식을 선언된 형식의 컬렉션에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="60e22-128">Adds a declared type to the collection of declared types.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="60e22-129">설명</span><span class="sxs-lookup"><span data-stu-id="60e22-129">Remarks</span></span>  
 <span data-ttu-id="60e22-130">알려진 형식에 대 한 자세한 내용은 [데이터 계약 알려진 형식](../../../wcf/feature-details/data-contract-known-types.md) 및 <xref:System.Runtime.Serialization.DataContractSerializer>을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="60e22-130">For more information about known types, see [Data Contract Known Types](../../../wcf/feature-details/data-contract-known-types.md) and <xref:System.Runtime.Serialization.DataContractSerializer>.</span></span>  
  
 <span data-ttu-id="60e22-131">이 요소를 사용 하는 예제는 [ \<dataContractSerializer >](datacontractserializer-element.md) 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="60e22-131">See the [\<dataContractSerializer>](datacontractserializer-element.md) for an example of using this element.</span></span>  
  
## <a name="example"></a><span data-ttu-id="60e22-132">예제</span><span class="sxs-lookup"><span data-stu-id="60e22-132">Example</span></span>  
  
```xml  
<add type="MyCompany.Library.Shape,
           MyAssembly, Version=2.0.0.0, Culture=neutral,
           PublicKeyToken=XXXXXX, processorArchitecture=MSIL">
  <knownType type="MyCompany.Library.Circle,
                   MyAssembly, Version=2.0.0.0, Culture=neutral,
                   PublicKeyToken=XXXXXX,
                   processorArchitecture=MSIL"/>
</add>
```  
  
## <a name="see-also"></a><span data-ttu-id="60e22-133">참고자료</span><span class="sxs-lookup"><span data-stu-id="60e22-133">See also</span></span>

- <xref:System.Runtime.Serialization.DataContractSerializer>
- [<span data-ttu-id="60e22-134">데이터 계약 알려진 형식</span><span class="sxs-lookup"><span data-stu-id="60e22-134">Data Contract Known Types</span></span>](../../../wcf/feature-details/data-contract-known-types.md)
- [<span data-ttu-id="60e22-135">\<dataContractSerializer></span><span class="sxs-lookup"><span data-stu-id="60e22-135">\<dataContractSerializer></span></span>](datacontractserializer-element.md)
- [<span data-ttu-id="60e22-136">\<add></span><span class="sxs-lookup"><span data-stu-id="60e22-136">\<add></span></span>](add-of-declaredtypes-element.md)
