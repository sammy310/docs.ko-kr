---
title: <add>of <declaredTypes> 요소
ms.date: 03/30/2017
helpviewer_keywords:
- data contracts
- dataContractSerializer element
- DataContractSerializer
- DataContractAttribute
ms.assetid: c3d37ae4-8f1c-463f-b195-658c5a7e90a1
ms.openlocfilehash: a001e8743b2c24f68b1b23cbccf3e5ac162c4e71
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/06/2019
ms.locfileid: "70400653"
---
# <a name="add-of-declaredtypes-element"></a><span data-ttu-id="b44ba-102">\<\<declaredTypes > 요소의 > 추가</span><span class="sxs-lookup"><span data-stu-id="b44ba-102">\<add> of \<declaredTypes> Element</span></span>
<span data-ttu-id="b44ba-103">deserialization을 수행하는 동안 <xref:System.Runtime.Serialization.DataContractSerializer>에서 사용하는 형식을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="b44ba-103">Adds a type used by the <xref:System.Runtime.Serialization.DataContractSerializer> during deserialization.</span></span> <span data-ttu-id="b44ba-104">선언된 각 형식에는 선언된 형식의 필드 또는 속성으로 반환되는 알려진 형식이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="b44ba-104">Each declared type includes the known types that will be returned as a field or property of the declared type.</span></span>  
  
<span data-ttu-id="b44ba-105">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="b44ba-105">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="b44ba-106">&nbsp;&nbsp;[ **\<>를 직렬화 합니다.** ](system-runtime-serialization.md)</span><span class="sxs-lookup"><span data-stu-id="b44ba-106">&nbsp;&nbsp;[**\<system.runtime.serialization>**](system-runtime-serialization.md)</span></span>\
<span data-ttu-id="b44ba-107">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<dataContractSerializer >** ](datacontractserializer.md)</span><span class="sxs-lookup"><span data-stu-id="b44ba-107">&nbsp;&nbsp;&nbsp;&nbsp;[**\<dataContractSerializer>**](datacontractserializer.md)</span></span>\
<span data-ttu-id="b44ba-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<declaredTypes >** ](declaredtypes.md)</span><span class="sxs-lookup"><span data-stu-id="b44ba-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<declaredTypes>**](declaredtypes.md)</span></span>\
<span data-ttu-id="b44ba-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<> 추가**</span><span class="sxs-lookup"><span data-stu-id="b44ba-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b44ba-110">구문</span><span class="sxs-lookup"><span data-stu-id="b44ba-110">Syntax</span></span>  
  
```xml  
<add type="String">
  <knownType type="String">
    <parameter index="Integer"
               type="String" />
  </knownType>
</add>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="b44ba-111">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="b44ba-111">Attributes and Elements</span></span>  
 <span data-ttu-id="b44ba-112">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="b44ba-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="b44ba-113">특성</span><span class="sxs-lookup"><span data-stu-id="b44ba-113">Attributes</span></span>  
  
|<span data-ttu-id="b44ba-114">특성</span><span class="sxs-lookup"><span data-stu-id="b44ba-114">Attribute</span></span>|<span data-ttu-id="b44ba-115">설명</span><span class="sxs-lookup"><span data-stu-id="b44ba-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="b44ba-116">type</span><span class="sxs-lookup"><span data-stu-id="b44ba-116">type</span></span>|<span data-ttu-id="b44ba-117">필수 문자열 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="b44ba-117">Required string attribute.</span></span><br /><br /> <span data-ttu-id="b44ba-118">형식 이름(네임스페이스 포함), 어셈블리 이름, 버전 번호, 문화권 및 공개 키 토큰을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="b44ba-118">Specifies the type name (including namespace), assembly name, version number, culture, and public key token.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="b44ba-119">자식 요소</span><span class="sxs-lookup"><span data-stu-id="b44ba-119">Child Elements</span></span>  
  
|<span data-ttu-id="b44ba-120">요소</span><span class="sxs-lookup"><span data-stu-id="b44ba-120">Element</span></span>|<span data-ttu-id="b44ba-121">Description</span><span class="sxs-lookup"><span data-stu-id="b44ba-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="b44ba-122">\<knownType></span><span class="sxs-lookup"><span data-stu-id="b44ba-122">\<knownType></span></span>](knowntype.md)|<span data-ttu-id="b44ba-123">추가 중인 선언된 형식에 대해 알려진 형식을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="b44ba-123">Specifies the known type for the declared type that is being added.</span></span> <span data-ttu-id="b44ba-124">선언된 형식이 제네릭 형식이면 매개 변수 요소를 `<knownType>` 요소에 추가하여 알려진 형식을 반환하는 데 사용되는 제네릭 매개 변수를 지정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b44ba-124">If the declared type is a generic type, then you must also add a parameter element to the `<knownType>` element to specify which generic parameter is used to return the known type.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="b44ba-125">부모 요소</span><span class="sxs-lookup"><span data-stu-id="b44ba-125">Parent Elements</span></span>  
  
|<span data-ttu-id="b44ba-126">요소</span><span class="sxs-lookup"><span data-stu-id="b44ba-126">Element</span></span>|<span data-ttu-id="b44ba-127">Description</span><span class="sxs-lookup"><span data-stu-id="b44ba-127">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="b44ba-128">\<declaredTypes></span><span class="sxs-lookup"><span data-stu-id="b44ba-128">\<declaredTypes></span></span>](declaredtypes.md)|<span data-ttu-id="b44ba-129"><xref:System.Runtime.Serialization.DataContractSerializer>에서 deserialization을 수행하는 동안 알려진 형식이 필요한 형식을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="b44ba-129">Contains the types that require known types during deserialization by the <xref:System.Runtime.Serialization.DataContractSerializer>.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b44ba-130">설명</span><span class="sxs-lookup"><span data-stu-id="b44ba-130">Remarks</span></span>  
 <span data-ttu-id="b44ba-131">알려진 형식에 대 한 자세한 내용은 [데이터 계약 알려진 형식](../../../wcf/feature-details/data-contract-known-types.md) 및 <xref:System.Runtime.Serialization.DataContractSerializer>을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="b44ba-131">For more information about known types, see [Data Contract Known Types](../../../wcf/feature-details/data-contract-known-types.md) and <xref:System.Runtime.Serialization.DataContractSerializer>.</span></span>  
  
 <span data-ttu-id="b44ba-132">이 요소를 사용 하는 예제는 [ \<dataContractSerializer >](datacontractserializer-element.md) 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="b44ba-132">See the [\<dataContractSerializer>](datacontractserializer-element.md) for an example of using this element.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="b44ba-133"><xref:System.Object> 형식을 `<declaredType>`으로 추가하면 <xref:System.Configuration.ConfigurationErrorsException>이 throw됩니다.</span><span class="sxs-lookup"><span data-stu-id="b44ba-133">If you add the <xref:System.Object> type as a `<declaredType>`, a <xref:System.Configuration.ConfigurationErrorsException> is thrown.</span></span> <span data-ttu-id="b44ba-134">이는 <xref:System.Object> 형식은 구성에서 선언된 형식으로 사용할 수 없기 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="b44ba-134">This is because the <xref:System.Object> type cannot be used as a declared type in configuration.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b44ba-135">예제</span><span class="sxs-lookup"><span data-stu-id="b44ba-135">Example</span></span>  
  
```xml  
<add type="MyCompany.Library.Shape,
           MyAssembly, Version=2.0.0.0, Culture=neutral,
           PublicKeyToken=XXXXXX, processorArchitecture=MSIL">
  <knownType type="MyCompany.Library.Circle,
                   MyAssembly, Version=2.0.0.0, Culture=neutral,
                   PublicKeyToken=XXXXXX,
                   processorArchitecture=MSIL" />
</add>
```  
  
## <a name="see-also"></a><span data-ttu-id="b44ba-136">참고자료</span><span class="sxs-lookup"><span data-stu-id="b44ba-136">See also</span></span>

- <xref:System.Runtime.Serialization.DataContractSerializer>
- [<span data-ttu-id="b44ba-137">데이터 계약 알려진 형식</span><span class="sxs-lookup"><span data-stu-id="b44ba-137">Data Contract Known Types</span></span>](../../../wcf/feature-details/data-contract-known-types.md)
- [<span data-ttu-id="b44ba-138">\<dataContractSerializer></span><span class="sxs-lookup"><span data-stu-id="b44ba-138">\<dataContractSerializer></span></span>](datacontractserializer-element.md)
- [<span data-ttu-id="b44ba-139">\<\<declaredTypes > > 추가</span><span class="sxs-lookup"><span data-stu-id="b44ba-139">\<add> of \<declaredTypes></span></span>](add-of-declaredtypes-element.md)
