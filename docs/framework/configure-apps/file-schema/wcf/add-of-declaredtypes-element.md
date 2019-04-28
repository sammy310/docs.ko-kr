---
title: <add> <declaredTypes> 요소
ms.date: 03/30/2017
helpviewer_keywords:
- data contracts
- dataContractSerializer element
- DataContractSerializer
- DataContractAttribute
ms.assetid: c3d37ae4-8f1c-463f-b195-658c5a7e90a1
ms.openlocfilehash: 9b280a63e85beac3231bc1a414430239bea4a1f8
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61701114"
---
# <a name="add-of-declaredtypes-element"></a><span data-ttu-id="238c4-102">\<추가 >의 \<declaredTypes > 요소</span><span class="sxs-lookup"><span data-stu-id="238c4-102">\<add> of \<declaredTypes> Element</span></span>
<span data-ttu-id="238c4-103">deserialization을 수행하는 동안 <xref:System.Runtime.Serialization.DataContractSerializer>에서 사용하는 형식을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="238c4-103">Adds a type used by the <xref:System.Runtime.Serialization.DataContractSerializer> during deserialization.</span></span> <span data-ttu-id="238c4-104">선언된 각 형식에는 선언된 형식의 필드 또는 속성으로 반환되는 알려진 형식이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="238c4-104">Each declared type includes the known types that will be returned as a field or property of the declared type.</span></span>  
  
 <span data-ttu-id="238c4-105">system.runtime.serialization</span><span class="sxs-lookup"><span data-stu-id="238c4-105">system.runtime.serialization</span></span>  
<span data-ttu-id="238c4-106">\<dataContractSerializer></span><span class="sxs-lookup"><span data-stu-id="238c4-106">\<dataContractSerializer></span></span>  
<span data-ttu-id="238c4-107">\<declaredTypes></span><span class="sxs-lookup"><span data-stu-id="238c4-107">\<declaredTypes></span></span>  
<span data-ttu-id="238c4-108">\<추가 >의 \<declaredTypes ></span><span class="sxs-lookup"><span data-stu-id="238c4-108">\<add> of \<declaredTypes></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="238c4-109">구문</span><span class="sxs-lookup"><span data-stu-id="238c4-109">Syntax</span></span>  
  
```xml  
<add type="String">
  <knownType type="String">
    <parameter index="Integer"
               type="String" />
  </knownType>
</add>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="238c4-110">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="238c4-110">Attributes and Elements</span></span>  
 <span data-ttu-id="238c4-111">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="238c4-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="238c4-112">특성</span><span class="sxs-lookup"><span data-stu-id="238c4-112">Attributes</span></span>  
  
|<span data-ttu-id="238c4-113">특성</span><span class="sxs-lookup"><span data-stu-id="238c4-113">Attribute</span></span>|<span data-ttu-id="238c4-114">설명</span><span class="sxs-lookup"><span data-stu-id="238c4-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="238c4-115">type</span><span class="sxs-lookup"><span data-stu-id="238c4-115">type</span></span>|<span data-ttu-id="238c4-116">필수 문자열 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="238c4-116">Required string attribute.</span></span><br /><br /> <span data-ttu-id="238c4-117">형식 이름(네임스페이스 포함), 어셈블리 이름, 버전 번호, 문화권 및 공개 키 토큰을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="238c4-117">Specifies the type name (including namespace), assembly name, version number, culture, and public key token.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="238c4-118">자식 요소</span><span class="sxs-lookup"><span data-stu-id="238c4-118">Child Elements</span></span>  
  
|<span data-ttu-id="238c4-119">요소</span><span class="sxs-lookup"><span data-stu-id="238c4-119">Element</span></span>|<span data-ttu-id="238c4-120">설명</span><span class="sxs-lookup"><span data-stu-id="238c4-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="238c4-121">\<knownType></span><span class="sxs-lookup"><span data-stu-id="238c4-121">\<knownType></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/knowntype.md)|<span data-ttu-id="238c4-122">추가 중인 선언된 형식에 대해 알려진 형식을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="238c4-122">Specifies the known type for the declared type that is being added.</span></span> <span data-ttu-id="238c4-123">선언된 형식이 제네릭 형식이면 매개 변수 요소를 `<knownType>` 요소에 추가하여 알려진 형식을 반환하는 데 사용되는 제네릭 매개 변수를 지정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="238c4-123">If the declared type is a generic type, then you must also add a parameter element to the `<knownType>` element to specify which generic parameter is used to return the known type.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="238c4-124">부모 요소</span><span class="sxs-lookup"><span data-stu-id="238c4-124">Parent Elements</span></span>  
  
|<span data-ttu-id="238c4-125">요소</span><span class="sxs-lookup"><span data-stu-id="238c4-125">Element</span></span>|<span data-ttu-id="238c4-126">설명</span><span class="sxs-lookup"><span data-stu-id="238c4-126">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="238c4-127">\<declaredTypes></span><span class="sxs-lookup"><span data-stu-id="238c4-127">\<declaredTypes></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/declaredtypes.md)|<span data-ttu-id="238c4-128"><xref:System.Runtime.Serialization.DataContractSerializer>에서 deserialization을 수행하는 동안 알려진 형식이 필요한 형식을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="238c4-128">Contains the types that require known types during deserialization by the <xref:System.Runtime.Serialization.DataContractSerializer>.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="238c4-129">설명</span><span class="sxs-lookup"><span data-stu-id="238c4-129">Remarks</span></span>  
 <span data-ttu-id="238c4-130">알려진된 형식에 대 한 자세한 내용은 참조 하세요. [데이터 계약 알려진 형식을](../../../../../docs/framework/wcf/feature-details/data-contract-known-types.md) 고 <xref:System.Runtime.Serialization.DataContractSerializer>입니다.</span><span class="sxs-lookup"><span data-stu-id="238c4-130">For more information about known types, see [Data Contract Known Types](../../../../../docs/framework/wcf/feature-details/data-contract-known-types.md) and <xref:System.Runtime.Serialization.DataContractSerializer>.</span></span>  
  
 <span data-ttu-id="238c4-131">참조 된 [ \<dataContractSerializer >](../../../../../docs/framework/configure-apps/file-schema/wcf/datacontractserializer-element.md) 이 요소를 사용 하는 예입니다.</span><span class="sxs-lookup"><span data-stu-id="238c4-131">See the [\<dataContractSerializer>](../../../../../docs/framework/configure-apps/file-schema/wcf/datacontractserializer-element.md) for an example of using this element.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="238c4-132"><xref:System.Object> 형식을 `<declaredType>`으로 추가하면 <xref:System.Configuration.ConfigurationErrorsException>이 throw됩니다.</span><span class="sxs-lookup"><span data-stu-id="238c4-132">If you add the <xref:System.Object> type as a `<declaredType>`, a <xref:System.Configuration.ConfigurationErrorsException> is thrown.</span></span> <span data-ttu-id="238c4-133">이는 <xref:System.Object> 형식은 구성에서 선언된 형식으로 사용할 수 없기 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="238c4-133">This is because the <xref:System.Object> type cannot be used as a declared type in configuration.</span></span>  
  
## <a name="example"></a><span data-ttu-id="238c4-134">예제</span><span class="sxs-lookup"><span data-stu-id="238c4-134">Example</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="238c4-135">참고자료</span><span class="sxs-lookup"><span data-stu-id="238c4-135">See also</span></span>

- <xref:System.Runtime.Serialization.DataContractSerializer>
- [<span data-ttu-id="238c4-136">데이터 계약 알려진 형식</span><span class="sxs-lookup"><span data-stu-id="238c4-136">Data Contract Known Types</span></span>](../../../../../docs/framework/wcf/feature-details/data-contract-known-types.md)
- [<span data-ttu-id="238c4-137">\<dataContractSerializer></span><span class="sxs-lookup"><span data-stu-id="238c4-137">\<dataContractSerializer></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/datacontractserializer-element.md)
- [<span data-ttu-id="238c4-138">\<추가 >의 \<declaredTypes ></span><span class="sxs-lookup"><span data-stu-id="238c4-138">\<add> of \<declaredTypes></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-declaredtypes-element.md)
