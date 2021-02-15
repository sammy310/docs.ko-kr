---
description: '자세한 정보: Serialization'
title: Serialization
ms.date: 10/22/2008
ms.assetid: bebb27ac-9712-4196-9931-de19fc04dbac
ms.openlocfilehash: a12163c01da2f9eed19de05b0434c02d05ca99b1
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99713301"
---
# <a name="serialization"></a>Serialization

serialization은 개체를 쉽게 유지하고 전송할 수 있는 형식으로 변환하는 프로세스입니다. 예를 들어 개체를 직렬화하고 HTTP를 사용하여 인터넷을 통해 전송하고 대상 머신에서 역직렬화할 수 있습니다.

 .NET Framework에서는 다양한 serialization 시나리오에 최적화된 세 가지 기본 serialization 기술을 제공합니다. 다음 표에서는 이러한 기술 및 해당 기술과 관련된 기본 Framework 형식을 보여 줍니다.

|**기술 이름**|**기본 형식**|**시나리오**|
|-------------------------|--------------------|-------------------|
|**데이터 계약 Serialization**|<xref:System.Runtime.Serialization.DataContractAttribute> <br /> <xref:System.Runtime.Serialization.DataMemberAttribute> <br /> <xref:System.Runtime.Serialization.DataContractSerializer> <br /> <xref:System.Runtime.Serialization.NetDataContractSerializer> <br /> <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> <br /> <xref:System.Runtime.Serialization.ISerializable>|일반 지속성<br />웹 서비스<br />JSON|
|**XML Serialization**|<xref:System.Xml.Serialization.XmlSerializer>|XML 모양에 대한 모든 권한이 있는 XML 형식|
|**런타임 Serialization(이진 및 SOAP)**|<xref:System.SerializableAttribute> <br /> <xref:System.Runtime.Serialization.ISerializable> <br /> <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter> <br /> <xref:System.Runtime.Serialization.Formatters.Soap.SoapFormatter>|.NET Remoting|

 ✔️ 새로운 형식을 디자인할 때는 serialization을 고려해야 합니다.

## <a name="choosing-the-right-serialization-technology-to-support"></a>지원할 올바른 Serialization 기술 선택

 ✔️ 형식의 인스턴스가 웹 서비스에서 유지되거나 사용되어야 하는 경우 데이터 계약 serialization을 지원하는 것이 좋습니다.

 ✔️ 형식이 직렬화될 때 생성되는 XML 형식을 더 구체적으로 제어해야 하는 경우 데이터 계약 serialization 대신 또는 데이터 계약 serialization과 함께 XML serialization을 지원하는 것이 좋습니다.

 이러한 지원은 XML 특성을 생성하는 등의 목적으로 데이터 계약 serialization에서 지원하지 않는 XML 구문을 사용해야 하는 일부 상호 운용성 시나리오에 필요할 수 있습니다.

 ✔️ 형식의 인스턴스에서 .NET Remoting 경계 간에 이동해야 하는 경우 런타임 serialization을 지원하는 것이 좋습니다.

 ❌ 일반적인 지속성 이유만으로는 런타임 serialization 또는 XML serialization을 지원하면 안 됩니다. 대신 데이터 계약 serialization을 사용하세요.

## <a name="supporting-data-contract-serialization"></a>데이터 계약 Serialization 지원

 형식은 형식에 <xref:System.Runtime.Serialization.DataContractAttribute>를 적용하고 형식의 멤버(필드 및 속성)에 <xref:System.Runtime.Serialization.DataMemberAttribute>를 적용하여 데이터 계약 serialization을 지원할 수 있습니다.

 ✔️ 부분 신뢰에서 사용할 수 있는 형식의 경우 형식의 데이터 멤버를 퍼블릭으로 표시하는 것이 좋습니다.

 완전 신뢰에서는 데이터 계약 직렬 변환기가 퍼블릭이 아닌 형식 및 멤버를 직렬화하고 역직렬화할 수 있지만 부분 신뢰에서는 퍼블릭 멤버만 직렬화하고 역직렬화할 수 있습니다.

 ✔️ <xref:System.Runtime.Serialization.DataMemberAttribute>가 있는 모든 속성에서 getter 및 setter를 구현하세요. 직렬화 가능한 형식으로 간주되도록 하려면 데이터 계약 직렬 변환기에 getter와 setter가 모두 필요합니다. .NET Framework 3.5 SP1에서는 일부 컬렉션 속성이 가져오기 전용일 수 있습니다. 부분 신뢰에서 사용하지 않을 형식의 경우에는 두 속성 접근자 중 하나 또는 둘 다 public이 아닐 수 있습니다.

 ✔️ 역직렬화된 인스턴스의 초기화에는 serialization 콜백을 사용하는 것이 좋습니다.

 개체가 역직렬화될 때는 생성자가 호출되지 않습니다. 규칙에 대한 예외가 있습니다. <xref:System.Runtime.Serialization.CollectionDataContractAttribute>로 표시된 컬렉션의 생성자는 deserialization 중에 호출됩니다. 따라서 정상적인 생성이 수행되는 동안 실행되는 논리는 모두 serialization 콜백 중 하나로 구현되어야 합니다.

 `OnDeserializedAttribute`는 가장 일반적으로 사용되는 콜백 특성입니다. 패밀리의 다른 특성으로는 <xref:System.Runtime.Serialization.OnDeserializingAttribute>, <xref:System.Runtime.Serialization.OnSerializingAttribute> 및 <xref:System.Runtime.Serialization.OnSerializedAttribute>가 있습니다. 이 특성은 deserialization하기 전, serialization하기 전 및 마지막으로 serialization한 후에 각각 실행되는 콜백을 표시하는 데 사용할 수 있습니다.

 ✔️ <xref:System.Runtime.Serialization.KnownTypeAttribute>를 사용하여 복합 개체 그래프를 역직렬화할 때 사용되어야 하는 구체적 형식을 나타내는 것이 좋습니다.

 ✔️ 직렬화 가능한 형식을 만들거나 변경할 때 이전 버전과의 호환성 및 이후 버전과의 호환성을 고려하세요.

 이후 버전의 형식에 대한 직렬화된 스트림을 현재 버전의 형식으로 역직렬화할 수 있고, 그 반대로 역직렬화할 수도 있습니다.

 데이터 계약 특성에 명시적 매개 변수를 사용하여 계약을 유지할 목적으로 특별히 주의하는 경우를 제외하면 프라이빗 멤버이거나 내부 멤버인 경우를 포함하여 데이터 멤버는 이후 버전의 형식에서 해당 멤버의 이름, 형식 또는 순서를 변경할 수 없습니다.

 직렬화 가능한 형식을 변경할 때 serialization의 호환성을 테스트하세요. 이 경우에는 새 버전을 이전 버전으로 역직렬화하거나 이전 버전을 새 버전으로 역직렬화하십시오.

 ✔️ 서로 다른 버전의 형식 간에 라운드트립이 가능하도록 <xref:System.Runtime.Serialization.IExtensibleDataObject>를 구현하는 것이 좋습니다.

 이 인터페이스를 사용하면 serializer에서 라운드트립하는 동안 데이터가 손실되지 않습니다. <xref:System.Runtime.Serialization.IExtensibleDataObject.ExtensionData%2A?displayProperty=nameWithType> 속성은 현재 버전에 알려지지 않은 형식의 이후 버전에서 데이터를 저장하는 데 사용되므로 해당 데이터 멤버에 저장할 수 없습니다. 이후에 현재 버전을 이후 버전으로 직렬화하고 역직렬화하면 직렬화된 스트림에서 추가 데이터를 사용할 수 있습니다.

## <a name="supporting-xml-serialization"></a>XML Serialization 지원

 데이터 계약 serialization은 .NET Framework의 기본 serialization 기술이지만 데이터 계약 serialization에서 지원하지 않는 serialization 시나리오가 있습니다. 예를 들어 serializer에서 생성하거나 사용하는 XML의 모양을 완전히 제어할 수 있는 권한이 없습니다. 이러한 세부적인 제어가 필요한 경우 XML Serialization을 사용해야 하며 이 serialization 기술을 지원하도록 형식을 디자인해야 합니다.

 ❌ 생성된 XML의 모양을 제어해야 하는 확실한 이유가 있지 않으면 XML Serialization에 맞게 형식을 디자인하면 안 됩니다. 이 serialization 기술은 앞의 섹션에서 설명한 데이터 계약 Serialization으로 대체되었습니다.

 ✔️ XML Serialization 특성을 적용하는 방법보다 직렬화된 XML의 모양을 더 구체적으로 제어하려면 <xref:System.Xml.Serialization.IXmlSerializable> 인터페이스를 구현하는 것이 좋습니다. 인터페이스의 두 메서드인 <xref:System.Xml.Serialization.IXmlSerializable.ReadXml%2A> 및 <xref:System.Xml.Serialization.IXmlSerializable.WriteXml%2A>을 사용하면 직렬화된 XML 스트림을 완전히 제어할 수 있습니다. `XmlSchemaProviderAttribute`를 적용하여 형식에 대해 생성되는 XML 스키마를 제어할 수도 있습니다.

## <a name="supporting-runtime-serialization"></a>런타임 Serialization 지원

 런타임 serialization은 .NET Remoting에서 사용되는 기술입니다. .NET Remoting을 사용하여 형식을 전송하려는 경우 런타임 Serialization을 지원하는지 확인해야 합니다.

 런타임 Serialization에 대한 기본 지원은 <xref:System.SerializableAttribute>를 적용하여 제공할 수 있으며, 고급 시나리오에는 간단한 런타임 직렬화 가능 패턴(<xref:System.Runtime.Serialization.ISerializable>을 구현하고 serialization 생성자 제공)의 구현이 포함됩니다.

 ✔️ .NET Remoting에서 형식을 사용하려는 경우 런타임 Serialization을 지원하는 것이 좋습니다. 예를 들어 <xref:System.AddIn?displayProperty=nameWithType> 네임스페이스는 .NET Remoting을 사용하므로 `System.AddIn` 추가 기능 간에 교환되는 모든 형식은 런타임 Serialization을 지원해야 합니다.

 ✔️ serialization 프로세스를 완전하게 제어하려면 런타임 직렬화 가능 패턴을 구현하는 것이 좋습니다. 데이터가 직렬화 또는 역직렬화될 때 데이터를 변환하려는 경우를 예로 들 수 있습니다.

 이 패턴은 아주 단순합니다. <xref:System.Runtime.Serialization.ISerializable> 인터페이스를 구현하고, 개체가 역직렬화될 때 사용되는 특별한 생성자를 제공하기만 하면 됩니다.

 ✔️ serialization 생성자를 보호되도록 설정하고 여기 샘플에 표시된 대로 정확하게 형식화하고 이름을 지정한 두 개의 매개 변수를 제공하세요.

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

 ✔️ <xref:System.Runtime.Serialization.ISerializable> 멤버를 명시적으로 구현하세요.

 ✔️ <xref:System.Runtime.Serialization.ISerializable.GetObjectData%2A?displayProperty=nameWithType> 구현에 링크 요청을 적용하세요. 그러면 완전히 신뢰할 수 있는 코어 및 런타임 직렬 변환기만 멤버에 액세스할 수 있습니다.

 *Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*

 *Pearson Education, Inc의 동의로 재인쇄. 출처: [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) 작성자: Krzysztof Cwalina 및 Brad Abrams, 출판 정보: Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*

## <a name="see-also"></a>참고 항목

- [프레임워크 디자인 지침](index.md)
- [사용 지침](usage-guidelines.md)
