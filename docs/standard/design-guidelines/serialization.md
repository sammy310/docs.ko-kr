---
title: Serialization
ms.date: 10/22/2008
ms.assetid: bebb27ac-9712-4196-9931-de19fc04dbac
ms.openlocfilehash: 58ed937df5b60daf9fcbcb7610d6026c5e9805fc
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95730931"
---
# <a name="serialization"></a>Serialization

Serialization은 개체를 쉽게 유지 하거나 전송할 수 있는 형식으로 변환 하는 프로세스입니다. 예를 들어 개체를 serialize 하 고, HTTP를 사용 하 여 인터넷을 통해 전송 하 고, 대상 컴퓨터에서 deserialize 할 수 있습니다.

 .NET Framework는 다양 한 serialization 시나리오에 최적화 된 세 가지 주요 serialization 기술을 제공 합니다. 다음 표에서는 이러한 기술 및 해당 기술과 관련된 기본 Framework 형식을 보여 줍니다.

|**기술 이름**|**기본 형식**|**시나리오**|
|-------------------------|--------------------|-------------------|
|**데이터 계약 Serialization**|<xref:System.Runtime.Serialization.DataContractAttribute> <br /> <xref:System.Runtime.Serialization.DataMemberAttribute> <br /> <xref:System.Runtime.Serialization.DataContractSerializer> <br /> <xref:System.Runtime.Serialization.NetDataContractSerializer> <br /> <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> <br /> <xref:System.Runtime.Serialization.ISerializable>|일반 지속성<br />웹 서비스<br />JSON|
|**XML Serialization**|<xref:System.Xml.Serialization.XmlSerializer>|XML 모양에 대 한 모든 권한이 있는 XML 형식|
|**런타임 Serialization (이진 및 SOAP)**|<xref:System.SerializableAttribute> <br /> <xref:System.Runtime.Serialization.ISerializable> <br /> <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter> <br /> <xref:System.Runtime.Serialization.Formatters.Soap.SoapFormatter>|.NET Remoting|

 ✔️는 새 형식을 디자인할 때 serialization에 대해 생각해 야 합니다.

## <a name="choosing-the-right-serialization-technology-to-support"></a>지원할 올바른 Serialization 기술 선택

 형식의 인스턴스가 웹 서비스에서 유지 되거나 사용 되어야 하는 경우 데이터 계약 Serialization을 지 원하는 것이 좋습니다 ✔️.

 형식이 serialize 될 때 생성 되는 XML 형식을 보다 세부적으로 제어 해야 하는 경우 데이터 계약 Serialization 대신 또는 데이터 계약 Serialization과 함께 XML Serialization을 지 원하는 것이 좋습니다. ✔️

 이는 XML 특성을 생성 하는 등의 데이터 계약 Serialization에서 지원 하지 않는 XML 구문을 사용 해야 하는 일부 상호 운용성 시나리오에서 필요할 수 있습니다.

 형식의 인스턴스가 .NET Remoting 경계 간에 이동 해야 하는 경우 런타임 Serialization을 지 원하는 것이 좋습니다. ✔️

 ❌ 일반적인 지 속성 이유에 대해서만 런타임 Serialization 또는 XML Serialization을 지원 하지 않습니다. 대신 데이터 계약 Serialization을 사용 하는 것이 좋습니다.

## <a name="supporting-data-contract-serialization"></a>데이터 계약 Serialization 지원

 형식은 형식에를 적용 하 <xref:System.Runtime.Serialization.DataContractAttribute> 고 <xref:System.Runtime.Serialization.DataMemberAttribute> 형식의 멤버 (필드 및 속성)에를 적용 하 여 데이터 계약 Serialization을 지원할 수 있습니다.

 형식을 부분 신뢰에서 사용할 수 있는 경우 형식의 데이터 멤버를 public으로 표시 하는 것이 좋습니다. ✔️

 완전 신뢰에서 데이터 계약 serializer는 public이 아닌 형식과 멤버를 serialize 및 deserialize 할 수 있지만 부분 신뢰에서는 public 멤버만 serialize 및 deserialize 할 수 있습니다.

 가 있는 모든 속성에 getter 및 setter를 구현 ✔️ <xref:System.Runtime.Serialization.DataMemberAttribute> 합니다. 데이터 계약 serializer에는 형식에 대해 getter와 setter를 모두 사용할 수 있어야 serializable로 간주할 수 있습니다. .NET Framework 3.5 s p 1에서는 일부 컬렉션 속성이 가져오기 전용 일 수 있습니다. 형식을 부분 신뢰에서 사용 하지 않는 경우 속성 접근자 중 하나 또는 둘 다가 public이 될 수 있습니다.

 deserialize 된 인스턴스를 초기화 하는 데 serialization 콜백을 사용 하는 것이 좋습니다 ✔️.

 개체가 역직렬화될 때는 생성자가 호출되지 않습니다. 규칙에 대 한 예외가 있습니다. Deserialization 중에로 표시 된 컬렉션의 생성자 <xref:System.Runtime.Serialization.CollectionDataContractAttribute> 가 호출 됩니다. 따라서 일반 생성 중에 실행 되는 모든 논리는 serialization 콜백 중 하나로 구현 되어야 합니다.

 `OnDeserializedAttribute` 가장 일반적으로 사용 되는 콜백 특성입니다. 패밀리의 다른 특성으로는 <xref:System.Runtime.Serialization.OnDeserializingAttribute>, <xref:System.Runtime.Serialization.OnSerializingAttribute> 및 <xref:System.Runtime.Serialization.OnSerializedAttribute>가 있습니다. 이 특성은 deserialization하기 전, serialization하기 전 및 마지막으로 serialization한 후에 각각 실행되는 콜백을 표시하는 데 사용할 수 있습니다.

 ✔️ <xref:System.Runtime.Serialization.KnownTypeAttribute> 복잡 한 개체 그래프를 deserialize 할 때 사용 해야 하는 구체적인 형식을 나타내는 데 사용 하는 것이 좋습니다.

 serialize 할 수 있는 형식을 만들거나 변경 하는 경우에는 이전 버전과 이후 버전과의 호환성을 고려 ✔️.

 이후 버전의 형식에 대한 직렬화된 스트림을 현재 버전의 형식으로 역직렬화할 수 있고, 그 반대로 역직렬화할 수도 있습니다.

 데이터 계약 특성에 대 한 명시적 매개 변수를 사용 하 여 계약을 유지 해야 하는 경우를 제외 하 고는 개인 및 내부용으로 데이터 멤버의 이름, 형식 또는 순서를 변경할 수 없습니다.

 직렬화 가능 형식을 변경할 때 serialization의 호환성을 테스트 합니다. 이 경우에는 새 버전을 이전 버전으로 역직렬화하거나 이전 버전을 새 버전으로 역직렬화하십시오.

 <xref:System.Runtime.Serialization.IExtensibleDataObject>다른 버전의 형식 간에 라운드트립이 가능 하도록 구현 하는 것이 좋습니다 ✔️.

 이 인터페이스를 사용하면 serializer에서 라운드트립하는 동안 데이터가 손실되지 않습니다. <xref:System.Runtime.Serialization.IExtensibleDataObject.ExtensionData%2A?displayProperty=nameWithType>속성은 현재 버전에 알려지지 않은 형식의 이후 버전의 데이터를 저장 하는 데 사용 되므로 해당 데이터 멤버에 저장할 수 없습니다. 이후 버전으로 현재 버전을 직렬화 하 고 역직렬화 하는 경우에는 serialize 된 스트림에서 추가 데이터를 사용할 수 있습니다.

## <a name="supporting-xml-serialization"></a>XML Serialization 지원

 데이터 계약 Serialization은 .NET Framework의 기본 serialization 기술 이지만 데이터 계약 Serialization에서 지원 하지 않는 serialization 시나리오가 있습니다. 예를 들어 serializer에서 생성하거나 사용하는 XML의 모양을 완전히 제어할 수 있는 권한이 없습니다. 이러한 세밀 한 제어가 필요한 경우 XML Serialization을 사용 해야 하며이 serialization 기술을 지원 하도록 형식을 디자인 해야 합니다.

 ❌ 생성 된 XML의 모양을 제어 하는 매우 강력한 이유가 없다면 XML 직렬화를 위해 특별히 형식을 디자인 하지 마십시오. 이 serialization 기술은 앞의 섹션에서 설명한 데이터 계약 Serialization으로 대체되었습니다.

 <xref:System.Xml.Serialization.IXmlSerializable>Xml Serialization 특성을 적용 하 여 제공 되는 것 보다 serialize 된 XML의 셰이프를 더 많이 제어 하려는 경우 인터페이스를 구현 하는 것이 좋습니다. ✔️ 인터페이스의 두 메서드인 <xref:System.Xml.Serialization.IXmlSerializable.ReadXml%2A> 및 <xref:System.Xml.Serialization.IXmlSerializable.WriteXml%2A>을 사용하면 직렬화된 XML 스트림을 완전히 제어할 수 있습니다. 를 적용 하 여 형식에 대해 생성 되는 XML 스키마를 제어할 수도 있습니다 `XmlSchemaProviderAttribute` .

## <a name="supporting-runtime-serialization"></a>런타임 Serialization 지원

 런타임 Serialization은 .NET Remoting에 사용 되는 기술입니다. .NET Remoting을 사용 하 여 형식을 전송할 것으로 생각 되는 경우 런타임 Serialization을 지원 하는지 확인 해야 합니다.

 를 적용 하 여 런타임 Serialization에 대 한 기본 지원을 제공할 수 <xref:System.SerializableAttribute> 있으며, 더 많은 고급 시나리오에는 간단한 런타임 직렬화 가능 패턴 (구현 <xref:System.Runtime.Serialization.ISerializable> 및 Serialization 생성자 제공)을 구현 하는 작업이 포함 됩니다.

 .NET Remoting과 함께 사용 되는 형식의 경우 런타임 Serialization을 지 원하는 것을 고려 ✔️. 예를 들어 <xref:System.AddIn?displayProperty=nameWithType> 네임 스페이스는 .Net Remoting을 사용 하므로 추가 기능 간에 교환 되는 모든 형식은 `System.AddIn` 런타임 Serialization을 지원 해야 합니다.

 serialization 프로세스를 완전 하 게 제어 하려면 런타임 Serializable 패턴을 구현 하는 것이 좋습니다. ✔️ 데이터가 직렬화 또는 역직렬화될 때 데이터를 변환하려는 경우를 예로 들 수 있습니다.

 이 패턴은 아주 단순합니다. <xref:System.Runtime.Serialization.ISerializable> 인터페이스를 구현하고, 개체가 역직렬화될 때 사용되는 특별한 생성자를 제공하기만 하면 됩니다.

 ✔️ serialization 생성자를 보호 하 고 여기에 샘플에 표시 된 것 처럼 형식화 되 고 이름이 지정 된 두 개의 매개 변수를 제공 합니다.

```csharp
[Serializable]
public class Person : ISerializable
{
    protected Person(SerializationInfo info, StreamingContext context)
    {
        // ...
    }
}
```

 <xref:System.Runtime.Serialization.ISerializable>멤버를 명시적으로 구현 ✔️ 합니다.

 구현에 링크 요청을 적용 ✔️ <xref:System.Runtime.Serialization.ISerializable.GetObjectData%2A?displayProperty=nameWithType> 합니다. 이렇게 하면 완전히 신뢰할 수 있는 코어 및 런타임 Serializer만 멤버에 액세스할 수 있습니다.

 *2005, 2009 Microsoft Corporation © 부분입니다. All rights reserved.*

 *Pearson Education, Inc의 동의로 재인쇄. 출처: [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) 작성자: Krzysztof Cwalina 및 Brad Abrams, 출판 정보: Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*

## <a name="see-also"></a>참조

- [프레임 워크 디자인 지침](index.md)
- [사용 지침](usage-guidelines.md)
