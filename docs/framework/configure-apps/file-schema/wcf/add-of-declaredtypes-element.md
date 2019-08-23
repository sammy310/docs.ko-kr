---
title: <add>of <declaredTypes> 요소
ms.date: 03/30/2017
helpviewer_keywords:
- data contracts
- dataContractSerializer element
- DataContractSerializer
- DataContractAttribute
ms.assetid: c3d37ae4-8f1c-463f-b195-658c5a7e90a1
ms.openlocfilehash: 1ea008dcc72d555b00e9648ace95bb9522ffc2c8
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/22/2019
ms.locfileid: "69920180"
---
# <a name="add-of-declaredtypes-element"></a><span data-ttu-id="32e06-102">\<\<declaredTypes > 요소의 > 추가</span><span class="sxs-lookup"><span data-stu-id="32e06-102">\<add> of \<declaredTypes> Element</span></span>
<span data-ttu-id="32e06-103">deserialization을 수행하는 동안 <xref:System.Runtime.Serialization.DataContractSerializer>에서 사용하는 형식을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="32e06-103">Adds a type used by the <xref:System.Runtime.Serialization.DataContractSerializer> during deserialization.</span></span> <span data-ttu-id="32e06-104">선언된 각 형식에는 선언된 형식의 필드 또는 속성으로 반환되는 알려진 형식이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="32e06-104">Each declared type includes the known types that will be returned as a field or property of the declared type.</span></span>  
  
 <span data-ttu-id="32e06-105">system.runtime.serialization</span><span class="sxs-lookup"><span data-stu-id="32e06-105">system.runtime.serialization</span></span>  
<span data-ttu-id="32e06-106">\<dataContractSerializer></span><span class="sxs-lookup"><span data-stu-id="32e06-106">\<dataContractSerializer></span></span>  
<span data-ttu-id="32e06-107">\<declaredTypes></span><span class="sxs-lookup"><span data-stu-id="32e06-107">\<declaredTypes></span></span>  
<span data-ttu-id="32e06-108">\<\<declaredTypes > > 추가</span><span class="sxs-lookup"><span data-stu-id="32e06-108">\<add> of \<declaredTypes></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="32e06-109">구문</span><span class="sxs-lookup"><span data-stu-id="32e06-109">Syntax</span></span>  
  
```xml  
<add type="String">
  <knownType type="String">
    <parameter index="Integer"
               type="String" />
  </knownType>
</add>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="32e06-110">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="32e06-110">Attributes and Elements</span></span>  
 <span data-ttu-id="32e06-111">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="32e06-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="32e06-112">특성</span><span class="sxs-lookup"><span data-stu-id="32e06-112">Attributes</span></span>  
  
|<span data-ttu-id="32e06-113">특성</span><span class="sxs-lookup"><span data-stu-id="32e06-113">Attribute</span></span>|<span data-ttu-id="32e06-114">Description</span><span class="sxs-lookup"><span data-stu-id="32e06-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="32e06-115">type</span><span class="sxs-lookup"><span data-stu-id="32e06-115">type</span></span>|<span data-ttu-id="32e06-116">필수 문자열 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="32e06-116">Required string attribute.</span></span><br /><br /> <span data-ttu-id="32e06-117">형식 이름(네임스페이스 포함), 어셈블리 이름, 버전 번호, 문화권 및 공개 키 토큰을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="32e06-117">Specifies the type name (including namespace), assembly name, version number, culture, and public key token.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="32e06-118">자식 요소</span><span class="sxs-lookup"><span data-stu-id="32e06-118">Child Elements</span></span>  
  
|<span data-ttu-id="32e06-119">요소</span><span class="sxs-lookup"><span data-stu-id="32e06-119">Element</span></span>|<span data-ttu-id="32e06-120">설명</span><span class="sxs-lookup"><span data-stu-id="32e06-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="32e06-121">\<knownType></span><span class="sxs-lookup"><span data-stu-id="32e06-121">\<knownType></span></span>](knowntype.md)|<span data-ttu-id="32e06-122">추가 중인 선언된 형식에 대해 알려진 형식을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="32e06-122">Specifies the known type for the declared type that is being added.</span></span> <span data-ttu-id="32e06-123">선언된 형식이 제네릭 형식이면 매개 변수 요소를 `<knownType>` 요소에 추가하여 알려진 형식을 반환하는 데 사용되는 제네릭 매개 변수를 지정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="32e06-123">If the declared type is a generic type, then you must also add a parameter element to the `<knownType>` element to specify which generic parameter is used to return the known type.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="32e06-124">부모 요소</span><span class="sxs-lookup"><span data-stu-id="32e06-124">Parent Elements</span></span>  
  
|<span data-ttu-id="32e06-125">요소</span><span class="sxs-lookup"><span data-stu-id="32e06-125">Element</span></span>|<span data-ttu-id="32e06-126">설명</span><span class="sxs-lookup"><span data-stu-id="32e06-126">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="32e06-127">\<declaredTypes></span><span class="sxs-lookup"><span data-stu-id="32e06-127">\<declaredTypes></span></span>](declaredtypes.md)|<span data-ttu-id="32e06-128"><xref:System.Runtime.Serialization.DataContractSerializer>에서 deserialization을 수행하는 동안 알려진 형식이 필요한 형식을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="32e06-128">Contains the types that require known types during deserialization by the <xref:System.Runtime.Serialization.DataContractSerializer>.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="32e06-129">설명</span><span class="sxs-lookup"><span data-stu-id="32e06-129">Remarks</span></span>  
 <span data-ttu-id="32e06-130">알려진 형식에 대 한 자세한 내용은 [데이터 계약 알려진 형식](../../../wcf/feature-details/data-contract-known-types.md) 및 <xref:System.Runtime.Serialization.DataContractSerializer>을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="32e06-130">For more information about known types, see [Data Contract Known Types](../../../wcf/feature-details/data-contract-known-types.md) and <xref:System.Runtime.Serialization.DataContractSerializer>.</span></span>  
  
 <span data-ttu-id="32e06-131">이 요소를 사용 하는 예제는 [ \<dataContractSerializer >](datacontractserializer-element.md) 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="32e06-131">See the [\<dataContractSerializer>](datacontractserializer-element.md) for an example of using this element.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="32e06-132"><xref:System.Object> 형식을 `<declaredType>`으로 추가하면 <xref:System.Configuration.ConfigurationErrorsException>이 throw됩니다.</span><span class="sxs-lookup"><span data-stu-id="32e06-132">If you add the <xref:System.Object> type as a `<declaredType>`, a <xref:System.Configuration.ConfigurationErrorsException> is thrown.</span></span> <span data-ttu-id="32e06-133">이는 <xref:System.Object> 형식은 구성에서 선언된 형식으로 사용할 수 없기 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="32e06-133">This is because the <xref:System.Object> type cannot be used as a declared type in configuration.</span></span>  
  
## <a name="example"></a><span data-ttu-id="32e06-134">예제</span><span class="sxs-lookup"><span data-stu-id="32e06-134">Example</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="32e06-135">참고자료</span><span class="sxs-lookup"><span data-stu-id="32e06-135">See also</span></span>

- <xref:System.Runtime.Serialization.DataContractSerializer>
- [<span data-ttu-id="32e06-136">데이터 계약 알려진 형식</span><span class="sxs-lookup"><span data-stu-id="32e06-136">Data Contract Known Types</span></span>](../../../wcf/feature-details/data-contract-known-types.md)
- [<span data-ttu-id="32e06-137">\<dataContractSerializer></span><span class="sxs-lookup"><span data-stu-id="32e06-137">\<dataContractSerializer></span></span>](datacontractserializer-element.md)
- [<span data-ttu-id="32e06-138">\<\<declaredTypes > > 추가</span><span class="sxs-lookup"><span data-stu-id="32e06-138">\<add> of \<declaredTypes></span></span>](add-of-declaredtypes-element.md)
