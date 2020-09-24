---
title: <knownType>
ms.date: 03/30/2017
ms.assetid: ee2b7be3-7148-4a3a-b861-48e7330615e5
ms.openlocfilehash: 6bb6a419d863172951d82a67de044cb8cfc30f49
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/24/2020
ms.locfileid: "91183795"
---
# \<knownType>

<span data-ttu-id="4e655-101">deserialization을 수행하는 동안 <xref:System.Runtime.Serialization.DataContractSerializer>에서 사용하는 형식을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="4e655-101">Specifies a type to be used by <xref:System.Runtime.Serialization.DataContractSerializer> during deserialization.</span></span> <span data-ttu-id="4e655-102">요소는 "선언된 형식"의 필드 또는 속성에서 반환하는 "알려진 형식"을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="4e655-102">The element specifies a "known type" that is returned by a field or property of a "declared type."</span></span> <span data-ttu-id="4e655-103">자세한 내용은 [데이터 계약 알려진 형식을](../../../wcf/feature-details/data-contract-known-types.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="4e655-103">For more information, see [Data Contract Known Types](../../../wcf/feature-details/data-contract-known-types.md).</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.runtime.serialization>**](system-runtime-serialization.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<dataContractSerializer>**](datacontractserializer.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<declaredTypes>**](declaredtypes.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<add>**](add-of-declaredtypes-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<knownType>**  
  
## <a name="syntax"></a><span data-ttu-id="4e655-104">구문</span><span class="sxs-lookup"><span data-stu-id="4e655-104">Syntax</span></span>  
  
```xml  
<knownType type="String">
  <parameter index="Integer"
             type="String" />
</knownType>
```  
  
## <a name="type"></a><span data-ttu-id="4e655-105">형식</span><span class="sxs-lookup"><span data-stu-id="4e655-105">Type</span></span>  

 `string`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="4e655-106">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="4e655-106">Attributes and Elements</span></span>  

 <span data-ttu-id="4e655-107">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="4e655-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="4e655-108">특성</span><span class="sxs-lookup"><span data-stu-id="4e655-108">Attributes</span></span>  
  
|<span data-ttu-id="4e655-109">attribute</span><span class="sxs-lookup"><span data-stu-id="4e655-109">Attribute</span></span>|<span data-ttu-id="4e655-110">Description</span><span class="sxs-lookup"><span data-stu-id="4e655-110">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="4e655-111">type</span><span class="sxs-lookup"><span data-stu-id="4e655-111">type</span></span>|<span data-ttu-id="4e655-112">형식(네임스페이스 포함), 어셈블리 이름, 버전, 문화권 및 공개 키 토큰을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="4e655-112">Specifies the type (including namespace), assembly name, version, culture, and public key token.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="4e655-113">자식 요소</span><span class="sxs-lookup"><span data-stu-id="4e655-113">Child Elements</span></span>  
  
|<span data-ttu-id="4e655-114">요소</span><span class="sxs-lookup"><span data-stu-id="4e655-114">Element</span></span>|<span data-ttu-id="4e655-115">설명</span><span class="sxs-lookup"><span data-stu-id="4e655-115">Description</span></span>|  
|-------------|-----------------|  
|[\<parameter>](parameter.md)|<span data-ttu-id="4e655-116">선언된 형식이 제네릭 형식이면 매개 변수 인덱스를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="4e655-116">Specifies a parameter index when the declared type is a generic type.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="4e655-117">부모 요소</span><span class="sxs-lookup"><span data-stu-id="4e655-117">Parent Elements</span></span>  
  
|<span data-ttu-id="4e655-118">요소</span><span class="sxs-lookup"><span data-stu-id="4e655-118">Element</span></span>|<span data-ttu-id="4e655-119">설명</span><span class="sxs-lookup"><span data-stu-id="4e655-119">Description</span></span>|  
|-------------|-----------------|  
|[\<add>](add-of-declaredtypes-element.md)|<span data-ttu-id="4e655-120">선언된 형식을 선언된 형식의 컬렉션에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="4e655-120">Adds a declared type to the collection of declared types.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4e655-121">설명</span><span class="sxs-lookup"><span data-stu-id="4e655-121">Remarks</span></span>  

 <span data-ttu-id="4e655-122">알려진 형식에 대 한 자세한 내용은 [데이터 계약 알려진 형식](../../../wcf/feature-details/data-contract-known-types.md) 및을 참조 하십시오 <xref:System.Runtime.Serialization.DataContractSerializer> .</span><span class="sxs-lookup"><span data-stu-id="4e655-122">For more information about known types, see [Data Contract Known Types](../../../wcf/feature-details/data-contract-known-types.md) and <xref:System.Runtime.Serialization.DataContractSerializer>.</span></span>  
  
 <span data-ttu-id="4e655-123">이 요소를 사용 하는 예제는를 참조 하십시오 [\<dataContractSerializer>](datacontractserializer-element.md) .</span><span class="sxs-lookup"><span data-stu-id="4e655-123">See the [\<dataContractSerializer>](datacontractserializer-element.md) for an example of using this element.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4e655-124">예제</span><span class="sxs-lookup"><span data-stu-id="4e655-124">Example</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="4e655-125">참고 항목</span><span class="sxs-lookup"><span data-stu-id="4e655-125">See also</span></span>

- <xref:System.Runtime.Serialization.DataContractSerializer>
- [<span data-ttu-id="4e655-126">데이터 계약 알려진 형식</span><span class="sxs-lookup"><span data-stu-id="4e655-126">Data Contract Known Types</span></span>](../../../wcf/feature-details/data-contract-known-types.md)
- [\<dataContractSerializer>](datacontractserializer-element.md)
- [\<add>](add-of-declaredtypes-element.md)
