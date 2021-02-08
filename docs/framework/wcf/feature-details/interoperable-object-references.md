---
description: '자세히 알아보기: 상호 운용 가능한 개체 참조'
title: 상호 운용 가능한 개체 참조
ms.date: 04/15/2019
ms.assetid: cb8da4c8-08ca-4220-a16b-e04c8f527f1b
ms.openlocfilehash: 27c801fb3954c7ea3f821a6588a2229502702989
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99802686"
---
# <a name="interoperable-object-references"></a><span data-ttu-id="1d0c8-103">상호 운용 가능한 개체 참조</span><span class="sxs-lookup"><span data-stu-id="1d0c8-103">Interoperable object references</span></span>

<span data-ttu-id="1d0c8-104">기본적으로는 <xref:System.Runtime.Serialization.DataContractSerializer> 개체를 값으로 serialize 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d0c8-104">By default, <xref:System.Runtime.Serialization.DataContractSerializer> serializes objects by value.</span></span> <span data-ttu-id="1d0c8-105">속성을 사용 하 여 <xref:System.Runtime.Serialization.DataContractAttribute.IsReference%2A> 개체를 serialize 할 때 개체 참조를 유지 하도록 데이터 계약 serializer에 지시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1d0c8-105">You can use the <xref:System.Runtime.Serialization.DataContractAttribute.IsReference%2A> property to instruct the data contract serializer to preserve object references when serializing objects.</span></span>  
  
## <a name="generated-xml"></a><span data-ttu-id="1d0c8-106">생성된 XML</span><span class="sxs-lookup"><span data-stu-id="1d0c8-106">Generated XML</span></span>  

 <span data-ttu-id="1d0c8-107">예를 들어 다음과 같은 개체를 살펴보세요.</span><span class="sxs-lookup"><span data-stu-id="1d0c8-107">As an example, consider the following object:</span></span>  
  
```csharp  
[DataContract]  
public class X  
{  
    SomeClass someInstance = new SomeClass();  
    [DataMember]  
    public SomeClass A = someInstance;  
    [DataMember]  
    public SomeClass B = someInstance;  
}  
  
public class SomeClass
{  
}  
```  
  
 <span data-ttu-id="1d0c8-108"><xref:System.Runtime.Serialization.DataContractSerializer.PreserveObjectReferences%2A>를 `false`(기본값)로 설정하면 다음 XML이 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="1d0c8-108">With <xref:System.Runtime.Serialization.DataContractSerializer.PreserveObjectReferences%2A> set to `false` (the default), the following XML is generated:</span></span>  
  
```xml  
<X>  
   <A>contents of someInstance</A>  
   <B>contents of someInstance</B>  
</X>  
```  
  
 <span data-ttu-id="1d0c8-109"><xref:System.Runtime.Serialization.DataContractSerializer.PreserveObjectReferences%2A>를 `true`로 설정하면 다음 XML이 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="1d0c8-109">With <xref:System.Runtime.Serialization.DataContractSerializer.PreserveObjectReferences%2A> set to `true`, the following XML is generated:</span></span>  
  
```xml  
<X>  
   <A id="1">contents of someInstance</A>  
   <B ref="1"></B>  
</X>  
```  
  
 <span data-ttu-id="1d0c8-110">그러나는 <xref:System.Runtime.Serialization.XsdDataContractExporter> `id` `ref` 속성이로 설정 된 경우에도 해당 스키마의 및 특성을 설명 하지 않습니다 `preserveObjectReferences` `true` .</span><span class="sxs-lookup"><span data-stu-id="1d0c8-110">However, <xref:System.Runtime.Serialization.XsdDataContractExporter> doesn't describe the `id` and `ref` attributes in its schema, even when the `preserveObjectReferences` property is set to `true`.</span></span>  
  
## <a name="using-isreference"></a><span data-ttu-id="1d0c8-111">IsReference 사용</span><span class="sxs-lookup"><span data-stu-id="1d0c8-111">Using IsReference</span></span>  

 <span data-ttu-id="1d0c8-112">이를 설명 하는 스키마에 따라 유효한 개체 참조 정보를 생성 하려면 <xref:System.Runtime.Serialization.DataContractAttribute> 형식에 특성을 적용 하 고 플래그를로 설정 <xref:System.Runtime.Serialization.DataContractAttribute.IsReference%2A> `true` 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d0c8-112">To generate object reference information that's valid according to the schema that describes it, apply the <xref:System.Runtime.Serialization.DataContractAttribute> attribute to a type, and set the <xref:System.Runtime.Serialization.DataContractAttribute.IsReference%2A> flag to `true`.</span></span> <span data-ttu-id="1d0c8-113">다음 예에서는를 `X` 추가 하 여 이전 예제의 클래스를 수정 합니다 `IsReference` .</span><span class="sxs-lookup"><span data-stu-id="1d0c8-113">The following example modifies class `X` in the previous example by adding `IsReference`:</span></span>  
  
```csharp
[DataContract(IsReference=true)]
public class X
{  
     SomeClass someInstance = new SomeClass();
     [DataMember]
     public SomeClass A = someInstance;
     [DataMember]
     public SomeClass B = someInstance;
}
  
public class SomeClass
{
}  
````

 <span data-ttu-id="1d0c8-114">생성되는 XML은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="1d0c8-114">The generated XML is as follows:</span></span>  

```xml
<X>  
    <A id="1">
        <Value>contents of A</Value>  
    </A>
    <B ref="1"></B>  
</X>
```  
  
 <span data-ttu-id="1d0c8-115">`IsReference`를 사용하면 메시지 라운드트립이 준수됩니다.</span><span class="sxs-lookup"><span data-stu-id="1d0c8-115">Using `IsReference` ensures compliance on message round-tripping.</span></span> <span data-ttu-id="1d0c8-116">이를 사용 하지 않으면 스키마에서 형식이 생성 될 때 해당 형식에 대 한 XML 출력이 원래 가정 된 스키마와 호환 되지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1d0c8-116">Without it, when a type is generated from schema, the XML output for that type isn't necessarily compatible with the schema originally assumed.</span></span> <span data-ttu-id="1d0c8-117">즉, `id` 및 `ref` 특성이 serialize되었더라도 원래 스키마 때문에 이러한 특성 또는 모든 특성이 XML에서 발생하지 않았을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1d0c8-117">In other words, although the `id` and `ref` attributes were serialized, the original schema could have barred these attributes (or all attributes) from occurring in the XML.</span></span> <span data-ttu-id="1d0c8-118">를 `IsReference` 데이터 멤버에 적용 하는 경우에는 라운드트립할 때 멤버가 *참조 가능한* 로 계속 인식 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1d0c8-118">With `IsReference` applied to a data member, the member continues to be recognized as *referenceable* when round-tripped.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1d0c8-119">참고 항목</span><span class="sxs-lookup"><span data-stu-id="1d0c8-119">See also</span></span>

- <xref:System.Runtime.Serialization.DataContractAttribute>
- <xref:System.Runtime.Serialization.CollectionDataContractAttribute>
- <xref:System.Runtime.Serialization.DataContractAttribute.IsReference?displayProperty=nameWithType>
- <xref:System.Runtime.Serialization.CollectionDataContractAttribute.IsReference?displayProperty=nameWithType>
