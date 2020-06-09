---
title: 데이터 계약 Serializer에서 지원하는 형식
ms.date: 03/30/2017
helpviewer_keywords:
- serialization [WCF], supported types
ms.assetid: 7381b200-437a-4506-9556-d77bf1bc3f34
ms.openlocfilehash: 15c3cda8329682fcbaa36609647ec49de7eb3c37
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/09/2020
ms.locfileid: "84595104"
---
# <a name="types-supported-by-the-data-contract-serializer"></a>데이터 계약 Serializer에서 지원하는 형식

WCF (Windows Communication Foundation)는를 <xref:System.Runtime.Serialization.DataContractSerializer> 기본 serialization 엔진으로 사용 하 여 데이터를 xml로 변환 하 고 xml을 다시 데이터로 변환 합니다. <xref:System.Runtime.Serialization.DataContractSerializer> 는 *데이터 계약* 형식을 serialize하도록 디자인되었습니다. 그러나 암시적 데이터 계약이 있는 것으로 간주될 수 있는 여러 가지 다른 형식을 지원합니다. 다음은 serialize할 수 있는 형식의 전체 목록입니다.

- 매개 변수를 사용하지 않는 생성자가 있는 모든 공개 형식

- 데이터 계약 형식. 이러한 형식에는 <xref:System.Runtime.Serialization.DataContractAttribute> 특성이 적용되었습니다. 일반적으로 데이터 계약 형식으로 만들어야 하는 비즈니스 개체를 나타내는 새 사용자 지정 형식입니다. 자세한 내용은 [데이터 계약](using-data-contracts.md) 및 [직렬화 가능 형식](serializable-types.md)사용을 참조 하세요.

- 컬렉션 형식. 이 형식은 데이터 목록을 나타냅니다. 이러한 형식은 <xref:System.Collections.ArrayList> 및 <xref:System.Collections.Generic.Dictionary%602>등의 컬렉션 형식이거나 일반 배열 형식일 수 있습니다. <xref:System.Runtime.Serialization.CollectionDataContractAttribute> 특성은 이러한 형식의 serialization을 사용자 지정하는 데 사용할 수 있지만 반드시 필요하지는 않습니다. 자세한 내용은 [데이터 계약의 컬렉션 형식](collection-types-in-data-contracts.md)을 참조 하세요.

- 열거형 형식. 플래그 열거형을 비롯한 열거형은 serialize할 수 있습니다. 필요한 경우 열거형 형식을 <xref:System.Runtime.Serialization.DataContractAttribute> 특성으로 표시할 수 있으며, 이 경우 serialization에 참여하는 모든 멤버를 <xref:System.Runtime.Serialization.EnumMemberAttribute> 특성으로 표시해야 합니다. 표시하지 않은 멤버는 serialize되지 않습니다. 자세한 내용은 [데이터 계약의 열거형 형식](enumeration-types-in-data-contracts.md)을 참조 하세요.

- .NET Framework 기본 형식. .NET Framework에 기본 제공된 <xref:System.Byte>, <xref:System.SByte>, <xref:System.Int16>, <xref:System.Int32>, <xref:System.Int64>, <xref:System.UInt16>, <xref:System.UInt32>, <xref:System.UInt64>, <xref:System.Single>, <xref:System.Double>, <xref:System.Boolean>, <xref:System.Char>, <xref:System.Decimal>, <xref:System.Object>및 <xref:System.String>형식은 모두 serialize할 수 있으며 기본 형식으로 간주됩니다.

- 기타 기본 형식. 이러한 형식은 .NET Framework의 기본 형식은 아니지만 serialize된 XML 형식에서 기본 형식으로 처리됩니다. 이러한 형식은 <xref:System.DateTime>, <xref:System.DateTimeOffset>, <xref:System.TimeSpan>, <xref:System.Guid>, <xref:System.Uri>, <xref:System.Xml.XmlQualifiedName>및 <xref:System.Byte>의 배열입니다.

  > [!NOTE]
  > 다른 기본 형식과 달리 <xref:System.DateTimeOffset> 은 기본적으로 알려진 형식이 아닙니다. 자세한 내용은 [데이터 계약 알려진 형식](data-contract-known-types.md)을 참조 하세요.

- <xref:System.SerializableAttribute> 특성으로 표시된 형식입니다. .NET Framework 기본 클래스 라이브러리에 포함 된 많은 형식이이 범주에 속합니다. <xref:System.Runtime.Serialization.DataContractSerializer> 는 <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter>인터페이스 지원을 비롯하여 .NET Framework Remoting, <xref:System.Runtime.Serialization.Formatters.Soap.SoapFormatter>및 <xref:System.Runtime.Serialization.ISerializable> 에서 사용된 이 serialization 프로그래밍 모델을 완전히 지원합니다.

- 원시 XML 또는 ADO.NET 관계형 데이터를 나타내는 형식을 나타내는 형식입니다. <xref:System.Xml.XmlElement> 및 <xref:System.Xml.XmlNode> 형식의 배열은 XML을 직접 나타내는 방식으로 지원됩니다. 또한, 관련된 <xref:System.Xml.Serialization.IXmlSerializable> 특성, <xref:System.Xml.Serialization.XmlSchemaProviderAttribute> 및 <xref:System.Xml.Linq.XDocument> 형식을 비롯하여 <xref:System.Xml.Linq.XElement> 인터페이스를 구현하는 형식이 지원됩니다. ADO.NET <xref:System.Data.DataTable> 형식 및 <xref:System.Data.DataSet> 형식이 형식화 된 파생 클래스는 모두 <xref:System.Xml.Serialization.IXmlSerializable> 인터페이스를 구현 하므로이 범주에 맞습니다. 자세한 내용은 [데이터 계약의 XML 및 ADO.NET 형식](xml-and-ado-net-types-in-data-contracts.md)을 참조 하세요.

## <a name="limitations-of-using-certain-types-in-partial-trust-mode"></a>부분 신뢰 모드에서 특정 형식의 사용 제한

다음은 부분 신뢰 모드 시나리오에서 특정 형식을 사용할 때의 제한 사항을 나열한 것입니다.

- <xref:System.Runtime.Serialization.ISerializable> 를 사용하여 부분 신뢰 코드에서 <xref:System.Runtime.Serialization.DataContractSerializer> 을 구현하는 형식을 직렬화 또는 역직렬화하려면 <xref:System.Security.Permissions.SecurityPermissionAttribute.SerializationFormatter%2A> 및 <xref:System.Security.Permissions.SecurityPermissionAttribute.UnmanagedCode%2A> 권한이 필요합니다.

- [부분 신뢰](partial-trust.md) 모드에서 WCF 코드를 실행 하는 경우 필드 (및)의 serialization 및 deserialization은 `readonly` `public` `private` 지원 되지 않습니다. 이는 생성된 IL을 확인할 수 없어서 상승된 권한이 필요하기 때문입니다.

- <xref:System.Runtime.Serialization.DataContractSerializer> 및 <xref:System.Xml.Serialization.XmlSerializer> 는 모두 부분 신뢰 환경에서 지원됩니다. 그러나 <xref:System.Runtime.Serialization.DataContractSerializer> 의 사용은 다음 조건에 따라 결정됩니다.

  - serialize할 수 있는 모든 `[DataContract]` 형식은 public이어야 합니다.

  - `[DataMember]` 형식의 serialize할 수 있는 모든 `[DataContract]` 필드 또는 속성은 public이고 읽기/쓰기가 가능해야 합니다. `readonly`부분적으로 신뢰할 수 있는 응용 프로그램에서 WCF를 실행 하는 경우 필드의 serialization 및 deserialization은 지원 되지 않습니다.

  - `[Serializable]` / `ISerializable]` 프로그래밍 모델은 부분 신뢰 환경에서 지원 되지 않습니다.

  - 코드 또는 시스템 수준 구성(`Machine.config`)에서는 알려진 형식을 지정해야 합니다. 보안상의 이유로 애플리케이션 수준 구성에서는 알려진 형식을 지정할 수 없습니다.

- <xref:System.Runtime.Serialization.IObjectReference> 를 구현하는 형식은 <xref:System.Runtime.Serialization.IObjectReference.GetRealObject%2A> 메서드에서 보안 권한 `[SecurityPermission(SecurityAction.LinkDemand, Flags=SecurityPermissionFlag.SerializationFormatter)]`를 필요로 하기 때문에 부분 신뢰 환경에서 예외를 throw합니다.

## <a name="additional-notes-on-serialization"></a>Serialization에 대한 참고 사항

다음 규칙은 데이터 계약 Serializer에서 지원하는 형식에도 적용됩니다.

- 제네릭 형식은 데이터 계약 serializer에서 완전히 지원됩니다.

- Nullable 값 형식은 데이터 계약 serializer에서 완벽 하 게 지원 됩니다.

- 인터페이스 형식은 <xref:System.Object> 또는 컬렉션 형식(컬렉션 인터페이스의 경우)으로 처리됩니다.

- 구조체와 클래스 모두 지원됩니다.

- 는 <xref:System.Runtime.Serialization.DataContractSerializer> 및 ASP.NET 웹 서비스에서 사용 하는 프로그래밍 모델을 지원 하지 않습니다 <xref:System.Xml.Serialization.XmlSerializer> . 특히 <xref:System.Xml.Serialization.XmlElementAttribute> 및 <xref:System.Xml.Serialization.XmlAttributeAttribute>와 같은 특성을 지원하지 않습니다. 이 프로그래밍 모델에 대 한 지원을 사용 하도록 설정 하려면 WCF를 대신 사용 하도록 전환 해야 합니다 <xref:System.Xml.Serialization.XmlSerializer> <xref:System.Runtime.Serialization.DataContractSerializer> .

- <xref:System.DBNull> 형식은 특수한 방법으로 처리됩니다. singleton 형식이며, 역직렬화 시 역직렬 변환기가 singleton 제약 조건을 적용하고 singleton 인스턴스에 대한 모든 `DBNull` 참조를 가리킵니다. `DBNull` 은 serialize 가능한 형식이므로 <xref:System.Security.Permissions.SecurityPermissionAttribute.SerializationFormatter%2A> 권한이 필요합니다.

## <a name="see-also"></a>참고 항목

- [데이터 계약의 XML 및 ADO.NET 형식](xml-and-ado-net-types-in-data-contracts.md)
- [데이터 계약 사용](using-data-contracts.md)
- [직렬화 가능 형식](serializable-types.md)
- [데이터 계약의 컬렉션 형식](collection-types-in-data-contracts.md)
- [데이터 계약의 열거형 형식](enumeration-types-in-data-contracts.md)
