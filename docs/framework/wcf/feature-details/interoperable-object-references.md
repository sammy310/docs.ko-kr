---
title: 상호 운용 가능한 개체 참조
ms.date: 04/15/2019
ms.assetid: cb8da4c8-08ca-4220-a16b-e04c8f527f1b
ms.openlocfilehash: 0927f217a1666f8f27ca9c3e68f80a96b9c0f2b1
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79184701"
---
# <a name="interoperable-object-references"></a>상호 운용 가능한 개체 참조
기본적으로 개체를 값별로 <xref:System.Runtime.Serialization.DataContractSerializer> 직렬화합니다. 속성을 <xref:System.Runtime.Serialization.DataContractAttribute.IsReference%2A> 사용하여 개체를 직렬화할 때 데이터 계약 serializer에 개체 참조를 보존하도록 지시할 수 있습니다.  
  
## <a name="generated-xml"></a>생성된 XML  
 예를 들어 다음과 같은 개체를 살펴보세요.  
  
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
  
 <xref:System.Runtime.Serialization.DataContractSerializer.PreserveObjectReferences%2A>를 `false`(기본값)로 설정하면 다음 XML이 생성됩니다.  
  
```xml  
<X>  
   <A>contents of someInstance</A>  
   <B>contents of someInstance</B>  
</X>  
```  
  
 <xref:System.Runtime.Serialization.DataContractSerializer.PreserveObjectReferences%2A>를 `true`로 설정하면 다음 XML이 생성됩니다.  
  
```xml  
<X>  
   <A id="1">contents of someInstance</A>  
   <B ref="1"></B>  
</X>  
```  
  
 그러나 <xref:System.Runtime.Serialization.XsdDataContractExporter> `id` `preserveObjectReferences` 속성이 로 설정된 `ref` 경우에도 해당 스키마의 및 특성을 설명하지 `true`않습니다.  
  
## <a name="using-isreference"></a>IsReference 사용  
 이를 설명하는 스키마에 따라 유효한 개체 참조 정보를 생성하려면 형식에 특성을 <xref:System.Runtime.Serialization.DataContractAttribute> 적용하고 <xref:System.Runtime.Serialization.DataContractAttribute.IsReference%2A> 플래그를 `true`로 설정합니다. 다음 예제에서는 다음 `X` 예제에서 클래스를 `IsReference`추가 하 여 클래스를 수정 합니다.  
  
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

 생성되는 XML은 다음과 같습니다.  

```xml
<X>  
    <A id="1">
        <Value>contents of A</Value>  
    </A>
    <B ref="1"></B>  
</X>
```  
  
 `IsReference`를 사용하면 메시지 라운드트립이 준수됩니다. 스키마에서 형식이 생성될 때 해당 형식의 XML 출력이 원래 가정된 스키마와 반드시 호환되는 것은 아닙니다. 즉, `id` 및 `ref` 특성이 serialize되었더라도 원래 스키마 때문에 이러한 특성 또는 모든 특성이 XML에서 발생하지 않았을 수 있습니다. 데이터 `IsReference` 멤버에 적용하면 멤버는 라운드 트립시 *참조 가능한* 것으로 계속 인식됩니다.  
  
## <a name="see-also"></a>참고 항목

- <xref:System.Runtime.Serialization.DataContractAttribute>
- <xref:System.Runtime.Serialization.CollectionDataContractAttribute>
- <xref:System.Runtime.Serialization.DataContractAttribute.IsReference?displayProperty=nameWithType>
- <xref:System.Runtime.Serialization.CollectionDataContractAttribute.IsReference?displayProperty=nameWithType>
