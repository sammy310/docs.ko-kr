---
description: '다음에 대 한 자세한 정보: <add> <declaredTypes> 요소'
title: <add> of <declaredTypes> 요소
ms.date: 03/30/2017
helpviewer_keywords:
- data contracts
- dataContractSerializer element
- DataContractSerializer
- DataContractAttribute
ms.assetid: c3d37ae4-8f1c-463f-b195-658c5a7e90a1
ms.openlocfilehash: 8e2be6e553ee5dc5c96bcae81d1c1c6bf609afed
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99803986"
---
# <a name="add-of-declaredtypes-element"></a><span data-ttu-id="d3f12-103">\<add> of \<declaredTypes> 요소</span><span class="sxs-lookup"><span data-stu-id="d3f12-103">\<add> of \<declaredTypes> Element</span></span>

<span data-ttu-id="d3f12-104">deserialization을 수행하는 동안 <xref:System.Runtime.Serialization.DataContractSerializer>에서 사용하는 형식을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="d3f12-104">Adds a type used by the <xref:System.Runtime.Serialization.DataContractSerializer> during deserialization.</span></span> <span data-ttu-id="d3f12-105">선언된 각 형식에는 선언된 형식의 필드 또는 속성으로 반환되는 알려진 형식이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="d3f12-105">Each declared type includes the known types that will be returned as a field or property of the declared type.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.runtime.serialization>**](system-runtime-serialization.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<dataContractSerializer>**](datacontractserializer.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<declaredTypes>**](declaredtypes.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**  
  
## <a name="syntax"></a><span data-ttu-id="d3f12-106">구문</span><span class="sxs-lookup"><span data-stu-id="d3f12-106">Syntax</span></span>  
  
```xml  
<add type="String">
  <knownType type="String">
    <parameter index="Integer"
               type="String" />
  </knownType>
</add>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="d3f12-107">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="d3f12-107">Attributes and Elements</span></span>  

 <span data-ttu-id="d3f12-108">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="d3f12-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="d3f12-109">특성</span><span class="sxs-lookup"><span data-stu-id="d3f12-109">Attributes</span></span>  
  
|<span data-ttu-id="d3f12-110">attribute</span><span class="sxs-lookup"><span data-stu-id="d3f12-110">Attribute</span></span>|<span data-ttu-id="d3f12-111">Description</span><span class="sxs-lookup"><span data-stu-id="d3f12-111">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="d3f12-112">type</span><span class="sxs-lookup"><span data-stu-id="d3f12-112">type</span></span>|<span data-ttu-id="d3f12-113">필수 문자열 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="d3f12-113">Required string attribute.</span></span><br /><br /> <span data-ttu-id="d3f12-114">형식 이름(네임스페이스 포함), 어셈블리 이름, 버전 번호, 문화권 및 공개 키 토큰을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="d3f12-114">Specifies the type name (including namespace), assembly name, version number, culture, and public key token.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="d3f12-115">자식 요소</span><span class="sxs-lookup"><span data-stu-id="d3f12-115">Child Elements</span></span>  
  
|<span data-ttu-id="d3f12-116">요소</span><span class="sxs-lookup"><span data-stu-id="d3f12-116">Element</span></span>|<span data-ttu-id="d3f12-117">설명</span><span class="sxs-lookup"><span data-stu-id="d3f12-117">Description</span></span>|  
|-------------|-----------------|  
|[\<knownType>](knowntype.md)|<span data-ttu-id="d3f12-118">추가 중인 선언된 형식에 대해 알려진 형식을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="d3f12-118">Specifies the known type for the declared type that is being added.</span></span> <span data-ttu-id="d3f12-119">선언된 형식이 제네릭 형식이면 매개 변수 요소를 `<knownType>` 요소에 추가하여 알려진 형식을 반환하는 데 사용되는 제네릭 매개 변수를 지정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d3f12-119">If the declared type is a generic type, then you must also add a parameter element to the `<knownType>` element to specify which generic parameter is used to return the known type.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="d3f12-120">부모 요소</span><span class="sxs-lookup"><span data-stu-id="d3f12-120">Parent Elements</span></span>  
  
|<span data-ttu-id="d3f12-121">요소</span><span class="sxs-lookup"><span data-stu-id="d3f12-121">Element</span></span>|<span data-ttu-id="d3f12-122">설명</span><span class="sxs-lookup"><span data-stu-id="d3f12-122">Description</span></span>|  
|-------------|-----------------|  
|[\<declaredTypes>](declaredtypes.md)|<span data-ttu-id="d3f12-123"><xref:System.Runtime.Serialization.DataContractSerializer>에서 deserialization을 수행하는 동안 알려진 형식이 필요한 형식을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="d3f12-123">Contains the types that require known types during deserialization by the <xref:System.Runtime.Serialization.DataContractSerializer>.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d3f12-124">설명</span><span class="sxs-lookup"><span data-stu-id="d3f12-124">Remarks</span></span>  

 <span data-ttu-id="d3f12-125">알려진 형식에 대 한 자세한 내용은 [데이터 계약 알려진 형식](../../../wcf/feature-details/data-contract-known-types.md) 및을 참조 하십시오 <xref:System.Runtime.Serialization.DataContractSerializer> .</span><span class="sxs-lookup"><span data-stu-id="d3f12-125">For more information about known types, see [Data Contract Known Types](../../../wcf/feature-details/data-contract-known-types.md) and <xref:System.Runtime.Serialization.DataContractSerializer>.</span></span>  
  
 <span data-ttu-id="d3f12-126">이 요소를 사용 하는 예제는를 참조 하십시오 [\<dataContractSerializer>](datacontractserializer-element.md) .</span><span class="sxs-lookup"><span data-stu-id="d3f12-126">See the [\<dataContractSerializer>](datacontractserializer-element.md) for an example of using this element.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="d3f12-127"><xref:System.Object> 형식을 `<declaredType>`으로 추가하면 <xref:System.Configuration.ConfigurationErrorsException>이 throw됩니다.</span><span class="sxs-lookup"><span data-stu-id="d3f12-127">If you add the <xref:System.Object> type as a `<declaredType>`, a <xref:System.Configuration.ConfigurationErrorsException> is thrown.</span></span> <span data-ttu-id="d3f12-128">이는 <xref:System.Object> 형식은 구성에서 선언된 형식으로 사용할 수 없기 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="d3f12-128">This is because the <xref:System.Object> type cannot be used as a declared type in configuration.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d3f12-129">예제</span><span class="sxs-lookup"><span data-stu-id="d3f12-129">Example</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="d3f12-130">참고 항목</span><span class="sxs-lookup"><span data-stu-id="d3f12-130">See also</span></span>

- <xref:System.Runtime.Serialization.DataContractSerializer>
- [<span data-ttu-id="d3f12-131">데이터 계약 알려진 형식</span><span class="sxs-lookup"><span data-stu-id="d3f12-131">Data Contract Known Types</span></span>](../../../wcf/feature-details/data-contract-known-types.md)
- [\<dataContractSerializer>](datacontractserializer-element.md)
- [<span data-ttu-id="d3f12-132">\<declaredTypes>의 \<add></span><span class="sxs-lookup"><span data-stu-id="d3f12-132">\<add> of \<declaredTypes></span></span>](add-of-declaredtypes-element.md)
