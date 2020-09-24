---
title: <declaredTypes>
ms.date: 03/30/2017
helpviewer_keywords:
- dataContractSerializer element
- declaredTypes element
- DataContractSerializer
- KnownTypes
- <declaredTypes> element
ms.assetid: f35184e4-9d9e-4d37-8fb4-d5b58220eb3e
ms.openlocfilehash: 281d9d7d7e51a837de4f86f85472815956a20319
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/24/2020
ms.locfileid: "91153913"
---
# \<declaredTypes>

<span data-ttu-id="3595e-101">역직렬화할 때 <xref:System.Runtime.Serialization.DataContractSerializer>에서 사용하는 알려진 형식을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="3595e-101">Contains the known types that the <xref:System.Runtime.Serialization.DataContractSerializer> uses when deserializing.</span></span>  
  
 <span data-ttu-id="3595e-102">데이터 계약 및 알려진 형식에 대 한 자세한 내용은 [데이터 계약 알려진 형식](../../../wcf/feature-details/data-contract-known-types.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="3595e-102">For more information about data contracts and known types, see [Data Contract Known Types](../../../wcf/feature-details/data-contract-known-types.md).</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.runtime.serialization>**](system-runtime-serialization.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<dataContractSerializer>**](datacontractserializer.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<declaredTypes>**  
  
## <a name="syntax"></a><span data-ttu-id="3595e-103">구문</span><span class="sxs-lookup"><span data-stu-id="3595e-103">Syntax</span></span>  
  
```xml  
<configuration>
  <system.runtime.serialization>
    <dataContractSerializer>
      <declaredTypes>
        <add type="String ">
          <knownType type="String">
            <parameter index="Integer"/>
          </knownType>
        </add>
      </declaredTypes>
    <dataContractSerializer>
  </system.runtime.serialization>
</configuration>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="3595e-104">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="3595e-104">Attributes and Elements</span></span>  

 <span data-ttu-id="3595e-105">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="3595e-105">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="3595e-106">특성</span><span class="sxs-lookup"><span data-stu-id="3595e-106">Attributes</span></span>  

 <span data-ttu-id="3595e-107">없음</span><span class="sxs-lookup"><span data-stu-id="3595e-107">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="3595e-108">자식 요소</span><span class="sxs-lookup"><span data-stu-id="3595e-108">Child Elements</span></span>  
  
|<span data-ttu-id="3595e-109">요소</span><span class="sxs-lookup"><span data-stu-id="3595e-109">Element</span></span>|<span data-ttu-id="3595e-110">설명</span><span class="sxs-lookup"><span data-stu-id="3595e-110">Description</span></span>|  
|-------------|-----------------|  
|[\<add>](add-of-declaredtypes-element.md)|<span data-ttu-id="3595e-111">알려진 형식을 필요로 하는 형식을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="3595e-111">Adds types that require known types.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="3595e-112">부모 요소</span><span class="sxs-lookup"><span data-stu-id="3595e-112">Parent Elements</span></span>  
  
|<span data-ttu-id="3595e-113">요소</span><span class="sxs-lookup"><span data-stu-id="3595e-113">Element</span></span>|<span data-ttu-id="3595e-114">설명</span><span class="sxs-lookup"><span data-stu-id="3595e-114">Description</span></span>|  
|-------------|-----------------|  
|[\<dataContractSerializer>](datacontractserializer-of-system-runtime-serialization.md)|<span data-ttu-id="3595e-115"><xref:System.Runtime.Serialization.DataContractSerializer>에 대한 구성 데이터를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="3595e-115">Contains configuration data for the <xref:System.Runtime.Serialization.DataContractSerializer>.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3595e-116">설명</span><span class="sxs-lookup"><span data-stu-id="3595e-116">Remarks</span></span>  

 <span data-ttu-id="3595e-117">알려진 형식에 대 한 자세한 내용은 [데이터 계약 알려진 형식](../../../wcf/feature-details/data-contract-known-types.md) 및을 참조 하십시오 <xref:System.Runtime.Serialization.DataContractSerializer> .</span><span class="sxs-lookup"><span data-stu-id="3595e-117">For more information about known types, see [Data Contract Known Types](../../../wcf/feature-details/data-contract-known-types.md) and <xref:System.Runtime.Serialization.DataContractSerializer>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="3595e-118">예제</span><span class="sxs-lookup"><span data-stu-id="3595e-118">Example</span></span>  

 <span data-ttu-id="3595e-119">다음 XML 코드는 요소에 추가 된 선언 된 형식 및 알려진 형식을 보여 줍니다 `DataContractSerializer` .</span><span class="sxs-lookup"><span data-stu-id="3595e-119">The following XML code shows declared types and known types added to a `DataContractSerializer` element.</span></span> <span data-ttu-id="3595e-120">예제에서는 추가되는 세 가지 형식을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="3595e-120">The example shows three types being added.</span></span> <span data-ttu-id="3595e-121">첫 번째는 "Item"이라는 알려진 형식을 사용하는 "Orders"라는 사용자 지정 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="3595e-121">The first is a custom type named "Orders" that uses a known type named "Item".</span></span> <span data-ttu-id="3595e-122">두 번째 선언된 형식은 <xref:System.Collections.Generic.List%601>을 알려진 형식으로 사용하는 `Item`입니다.</span><span class="sxs-lookup"><span data-stu-id="3595e-122">The second declared type is a <xref:System.Collections.Generic.List%601> that uses `Item` as a known type.</span></span> <span data-ttu-id="3595e-123">마지막으로 세 번째 선언된 형식은 <xref:System.Collections.Generic.Dictionary%602>입니다.</span><span class="sxs-lookup"><span data-stu-id="3595e-123">Finally the third declared type is a <xref:System.Collections.Generic.Dictionary%602>.</span></span> <span data-ttu-id="3595e-124"><xref:System.Collections.Generic.Dictionary%602> 클래스 형식은 두 개의 형식 매개 변수가 있는 제네릭 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="3595e-124">The <xref:System.Collections.Generic.Dictionary%602> class type is a generic type, with two type parameters.</span></span> <span data-ttu-id="3595e-125">첫 번째는 키를 나타내고 두 번째는 값을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="3595e-125">The first represents the key and the second represents the value.</span></span> <span data-ttu-id="3595e-126">다음 예제에서는 알려진 형식 목록에 두 번째 형식(값)의 <xref:System.Collections.Generic.List%601>을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="3595e-126">The following example adds a <xref:System.Collections.Generic.List%601> of the second type (the value) to the list of known types.</span></span> <span data-ttu-id="3595e-127">`index` 특성을 사용하여 알려진 형식에 사용할 형식 매개 변수를 지정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3595e-127">You must use the `index` attribute to specify which type parameter to use in the known type.</span></span> <span data-ttu-id="3595e-128">이 경우 값 형식은 "1"로 설정된 index 특성으로 표시됩니다(컬렉션은 0부터 시작).</span><span class="sxs-lookup"><span data-stu-id="3595e-128">In this case, the value type is indicated by the index attribute set to "1" (the collection is zero-based).</span></span>  
  
```xml  
<configuration>
  <system.runtime.serialization>
    <dataContractSerializer>
      <declaredTypes>
        <add type="Examples.Types.Orders, SerializationTypes, Version = 2.0.0.0, Culture = neutral, PublicKeyToken=null">
          <knownType type="Examples.Types.Item, SerializationTypes, Version=2.0.0.0, Culture=neutral, PublicKey=null" />
        </add>
        <add type="System.Collections.Generic.List`1, SerializationTypes, Version = 2.0.0.0, Culture = neutral, PublicKeyToken=null">
          <knownType type="Examples.Types.Item, SerializationTypes, Version=2.0.0.0, Culture=neutral, PublicKey=null" />
        </add>
        <add type="System.Collections.Generic.Dictionary`2, SerializationTypes, Version = 2.0.0.0, Culture = neutral, PublicKeyToken=null">
          <knownType type="System.Collections.Generic.List`1, SerializationTypes, Version = 2.0.0.0, Culture = neutral, PublicKeyToken=null">
            <parameter index="1"/>
          </knownType>
        </add>
      </declaredTypes>
    <dataContractSerializer>
  </system.runtime.serialization>
</configuration>
```  
  
## <a name="see-also"></a><span data-ttu-id="3595e-129">참고 항목</span><span class="sxs-lookup"><span data-stu-id="3595e-129">See also</span></span>

- <xref:System.Runtime.Serialization.DataContractSerializer>
- [\<dataContractSerializer>](datacontractserializer-element.md)
- [<span data-ttu-id="3595e-130">데이터 계약 알려진 형식</span><span class="sxs-lookup"><span data-stu-id="3595e-130">Data Contract Known Types</span></span>](../../../wcf/feature-details/data-contract-known-types.md)
- [\<add>](add-of-declaredtypes-element.md)
