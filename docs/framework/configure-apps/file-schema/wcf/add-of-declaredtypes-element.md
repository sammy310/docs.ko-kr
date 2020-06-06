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
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/06/2020
ms.locfileid: "70400653"
---
# <a name="add-of-declaredtypes-element"></a><span data-ttu-id="7530d-102">\<add>of \<declaredTypes> 요소</span><span class="sxs-lookup"><span data-stu-id="7530d-102">\<add> of \<declaredTypes> Element</span></span>
<span data-ttu-id="7530d-103">deserialization을 수행하는 동안 <xref:System.Runtime.Serialization.DataContractSerializer>에서 사용하는 형식을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="7530d-103">Adds a type used by the <xref:System.Runtime.Serialization.DataContractSerializer> during deserialization.</span></span> <span data-ttu-id="7530d-104">선언된 각 형식에는 선언된 형식의 필드 또는 속성으로 반환되는 알려진 형식이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="7530d-104">Each declared type includes the known types that will be returned as a field or property of the declared type.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.runtime.serialization>**](system-runtime-serialization.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<dataContractSerializer>**](datacontractserializer.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<declaredTypes>**](declaredtypes.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**  
  
## <a name="syntax"></a><span data-ttu-id="7530d-105">구문</span><span class="sxs-lookup"><span data-stu-id="7530d-105">Syntax</span></span>  
  
```xml  
<add type="String">
  <knownType type="String">
    <parameter index="Integer"
               type="String" />
  </knownType>
</add>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="7530d-106">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="7530d-106">Attributes and Elements</span></span>  
 <span data-ttu-id="7530d-107">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="7530d-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="7530d-108">특성</span><span class="sxs-lookup"><span data-stu-id="7530d-108">Attributes</span></span>  
  
|<span data-ttu-id="7530d-109">attribute</span><span class="sxs-lookup"><span data-stu-id="7530d-109">Attribute</span></span>|<span data-ttu-id="7530d-110">Description</span><span class="sxs-lookup"><span data-stu-id="7530d-110">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="7530d-111">type</span><span class="sxs-lookup"><span data-stu-id="7530d-111">type</span></span>|<span data-ttu-id="7530d-112">필수 문자열 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="7530d-112">Required string attribute.</span></span><br /><br /> <span data-ttu-id="7530d-113">형식 이름(네임스페이스 포함), 어셈블리 이름, 버전 번호, 문화권 및 공개 키 토큰을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="7530d-113">Specifies the type name (including namespace), assembly name, version number, culture, and public key token.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="7530d-114">자식 요소</span><span class="sxs-lookup"><span data-stu-id="7530d-114">Child Elements</span></span>  
  
|<span data-ttu-id="7530d-115">요소</span><span class="sxs-lookup"><span data-stu-id="7530d-115">Element</span></span>|<span data-ttu-id="7530d-116">Description</span><span class="sxs-lookup"><span data-stu-id="7530d-116">Description</span></span>|  
|-------------|-----------------|  
|[\<knownType>](knowntype.md)|<span data-ttu-id="7530d-117">추가 중인 선언된 형식에 대해 알려진 형식을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="7530d-117">Specifies the known type for the declared type that is being added.</span></span> <span data-ttu-id="7530d-118">선언된 형식이 제네릭 형식이면 매개 변수 요소를 `<knownType>` 요소에 추가하여 알려진 형식을 반환하는 데 사용되는 제네릭 매개 변수를 지정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7530d-118">If the declared type is a generic type, then you must also add a parameter element to the `<knownType>` element to specify which generic parameter is used to return the known type.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="7530d-119">부모 요소</span><span class="sxs-lookup"><span data-stu-id="7530d-119">Parent Elements</span></span>  
  
|<span data-ttu-id="7530d-120">요소</span><span class="sxs-lookup"><span data-stu-id="7530d-120">Element</span></span>|<span data-ttu-id="7530d-121">Description</span><span class="sxs-lookup"><span data-stu-id="7530d-121">Description</span></span>|  
|-------------|-----------------|  
|[\<declaredTypes>](declaredtypes.md)|<span data-ttu-id="7530d-122"><xref:System.Runtime.Serialization.DataContractSerializer>에서 deserialization을 수행하는 동안 알려진 형식이 필요한 형식을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="7530d-122">Contains the types that require known types during deserialization by the <xref:System.Runtime.Serialization.DataContractSerializer>.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7530d-123">설명</span><span class="sxs-lookup"><span data-stu-id="7530d-123">Remarks</span></span>  
 <span data-ttu-id="7530d-124">알려진 형식에 대 한 자세한 내용은 [데이터 계약 알려진 형식](../../../wcf/feature-details/data-contract-known-types.md) 및을 참조 하십시오 <xref:System.Runtime.Serialization.DataContractSerializer> .</span><span class="sxs-lookup"><span data-stu-id="7530d-124">For more information about known types, see [Data Contract Known Types](../../../wcf/feature-details/data-contract-known-types.md) and <xref:System.Runtime.Serialization.DataContractSerializer>.</span></span>  
  
 <span data-ttu-id="7530d-125">이 요소를 사용 하는 예제는를 참조 하십시오 [\<dataContractSerializer>](datacontractserializer-element.md) .</span><span class="sxs-lookup"><span data-stu-id="7530d-125">See the [\<dataContractSerializer>](datacontractserializer-element.md) for an example of using this element.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="7530d-126"><xref:System.Object> 형식을 `<declaredType>`으로 추가하면 <xref:System.Configuration.ConfigurationErrorsException>이 throw됩니다.</span><span class="sxs-lookup"><span data-stu-id="7530d-126">If you add the <xref:System.Object> type as a `<declaredType>`, a <xref:System.Configuration.ConfigurationErrorsException> is thrown.</span></span> <span data-ttu-id="7530d-127">이는 <xref:System.Object> 형식은 구성에서 선언된 형식으로 사용할 수 없기 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="7530d-127">This is because the <xref:System.Object> type cannot be used as a declared type in configuration.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7530d-128">예제</span><span class="sxs-lookup"><span data-stu-id="7530d-128">Example</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="7530d-129">참고 항목</span><span class="sxs-lookup"><span data-stu-id="7530d-129">See also</span></span>

- <xref:System.Runtime.Serialization.DataContractSerializer>
- [<span data-ttu-id="7530d-130">데이터 계약 알려진 형식</span><span class="sxs-lookup"><span data-stu-id="7530d-130">Data Contract Known Types</span></span>](../../../wcf/feature-details/data-contract-known-types.md)
- [\<dataContractSerializer>](datacontractserializer-element.md)
- [<span data-ttu-id="7530d-131">\<add>으로\<declaredTypes></span><span class="sxs-lookup"><span data-stu-id="7530d-131">\<add> of \<declaredTypes></span></span>](add-of-declaredtypes-element.md)
