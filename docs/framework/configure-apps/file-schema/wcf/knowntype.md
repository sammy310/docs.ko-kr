---
description: 다음에 대해 자세히 알아보세요. <knownType>
title: <knownType>
ms.date: 03/30/2017
ms.assetid: ee2b7be3-7148-4a3a-b861-48e7330615e5
ms.openlocfilehash: 205f799c81263be3dd08aae9efefb975b06a0cc7
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99725508"
---
# \<knownType>

<span data-ttu-id="83a60-102">deserialization을 수행하는 동안 <xref:System.Runtime.Serialization.DataContractSerializer>에서 사용하는 형식을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="83a60-102">Specifies a type to be used by <xref:System.Runtime.Serialization.DataContractSerializer> during deserialization.</span></span> <span data-ttu-id="83a60-103">요소는 "선언된 형식"의 필드 또는 속성에서 반환하는 "알려진 형식"을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="83a60-103">The element specifies a "known type" that is returned by a field or property of a "declared type."</span></span> <span data-ttu-id="83a60-104">자세한 내용은 [데이터 계약 알려진 형식을](../../../wcf/feature-details/data-contract-known-types.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="83a60-104">For more information, see [Data Contract Known Types](../../../wcf/feature-details/data-contract-known-types.md).</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.runtime.serialization>**](system-runtime-serialization.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<dataContractSerializer>**](datacontractserializer.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<declaredTypes>**](declaredtypes.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<add>**](add-of-declaredtypes-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<knownType>**  
  
## <a name="syntax"></a><span data-ttu-id="83a60-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="83a60-105">Syntax</span></span>  
  
```xml  
<knownType type="String">
  <parameter index="Integer"
             type="String" />
</knownType>
```  
  
## <a name="type"></a><span data-ttu-id="83a60-106">Type</span><span class="sxs-lookup"><span data-stu-id="83a60-106">Type</span></span>  

 `string`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="83a60-107">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="83a60-107">Attributes and Elements</span></span>  

 <span data-ttu-id="83a60-108">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="83a60-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="83a60-109">특성</span><span class="sxs-lookup"><span data-stu-id="83a60-109">Attributes</span></span>  
  
|<span data-ttu-id="83a60-110">attribute</span><span class="sxs-lookup"><span data-stu-id="83a60-110">Attribute</span></span>|<span data-ttu-id="83a60-111">Description</span><span class="sxs-lookup"><span data-stu-id="83a60-111">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="83a60-112">type</span><span class="sxs-lookup"><span data-stu-id="83a60-112">type</span></span>|<span data-ttu-id="83a60-113">형식(네임스페이스 포함), 어셈블리 이름, 버전, 문화권 및 공개 키 토큰을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="83a60-113">Specifies the type (including namespace), assembly name, version, culture, and public key token.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="83a60-114">자식 요소</span><span class="sxs-lookup"><span data-stu-id="83a60-114">Child Elements</span></span>  
  
|<span data-ttu-id="83a60-115">요소</span><span class="sxs-lookup"><span data-stu-id="83a60-115">Element</span></span>|<span data-ttu-id="83a60-116">설명</span><span class="sxs-lookup"><span data-stu-id="83a60-116">Description</span></span>|  
|-------------|-----------------|  
|[\<parameter>](parameter.md)|<span data-ttu-id="83a60-117">선언된 형식이 제네릭 형식이면 매개 변수 인덱스를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="83a60-117">Specifies a parameter index when the declared type is a generic type.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="83a60-118">부모 요소</span><span class="sxs-lookup"><span data-stu-id="83a60-118">Parent Elements</span></span>  
  
|<span data-ttu-id="83a60-119">요소</span><span class="sxs-lookup"><span data-stu-id="83a60-119">Element</span></span>|<span data-ttu-id="83a60-120">설명</span><span class="sxs-lookup"><span data-stu-id="83a60-120">Description</span></span>|  
|-------------|-----------------|  
|[\<add>](add-of-declaredtypes-element.md)|<span data-ttu-id="83a60-121">선언된 형식을 선언된 형식의 컬렉션에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="83a60-121">Adds a declared type to the collection of declared types.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="83a60-122">설명</span><span class="sxs-lookup"><span data-stu-id="83a60-122">Remarks</span></span>  

 <span data-ttu-id="83a60-123">알려진 형식에 대 한 자세한 내용은 [데이터 계약 알려진 형식](../../../wcf/feature-details/data-contract-known-types.md) 및을 참조 하십시오 <xref:System.Runtime.Serialization.DataContractSerializer> .</span><span class="sxs-lookup"><span data-stu-id="83a60-123">For more information about known types, see [Data Contract Known Types](../../../wcf/feature-details/data-contract-known-types.md) and <xref:System.Runtime.Serialization.DataContractSerializer>.</span></span>  
  
 <span data-ttu-id="83a60-124">이 요소를 사용 하는 예제는를 참조 하십시오 [\<dataContractSerializer>](datacontractserializer-element.md) .</span><span class="sxs-lookup"><span data-stu-id="83a60-124">See the [\<dataContractSerializer>](datacontractserializer-element.md) for an example of using this element.</span></span>  
  
## <a name="example"></a><span data-ttu-id="83a60-125">예제</span><span class="sxs-lookup"><span data-stu-id="83a60-125">Example</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="83a60-126">참고 항목</span><span class="sxs-lookup"><span data-stu-id="83a60-126">See also</span></span>

- <xref:System.Runtime.Serialization.DataContractSerializer>
- [<span data-ttu-id="83a60-127">데이터 계약 알려진 형식</span><span class="sxs-lookup"><span data-stu-id="83a60-127">Data Contract Known Types</span></span>](../../../wcf/feature-details/data-contract-known-types.md)
- [\<dataContractSerializer>](datacontractserializer-element.md)
- [\<add>](add-of-declaredtypes-element.md)
