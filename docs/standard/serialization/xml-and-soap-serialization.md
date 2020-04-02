---
title: XML 및 SOAP Serialization
ms.date: 03/30/2017
helpviewer_keywords:
- SOAP, XML serialization
- XML serialization, SOAP
- serialization, SOAP
- serialization, about serialization
- XML serialization
- serialization
ms.assetid: 832ac524-21bc-419a-a27b-ca8bfc45840f
ms.openlocfilehash: dcb2ed1703473be582a12f430d2e051d8a420230
ms.sourcegitcommit: 961ec21c22d2f1d55c9cc8a7edf2ade1d1fd92e3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/02/2020
ms.locfileid: "80588369"
---
# <a name="xml-and-soap-serialization"></a>XML 및 비누 일련화

XML 직렬화는 개체의 공용 필드 및 속성과 메서드의 매개 변수 및 반환 값을 특정 XML 스키마 정의 언어(XSD) 문서를 준수하는 XML 스트림으로 변환(직렬화)합니다. XML serialization을 사용하면 스토리지이나 전송을 위해 직렬 형식(이 경우 XML)으로 변환되는 public 속성 및 필드가 있는 강력한 형식의 클래스가 만들어집니다.

XML은 공개 표준이기 때문에 XML 스트림은 플랫폼에 관계없이 필요에 따라 모든 애플리케이션에서 처리될 수 있습니다. 예를 들어 ASP.NET을 사용하여 만들어진 XML Web services는 <xref:System.Xml.Serialization.XmlSerializer> 클래스를 사용하여 데이터를 인터넷이나 인트라넷을 통해 XML Web services 애플리케이션 간에 전달하는 XML 스트림을 만듭니다. 이와 반대로 deserialization에서는 이러한 XML 스트림을 받아서 개체를 다시 만듭니다.

XML serialization은 SOAP 사양과 일치하는 XML 스트림으로 개체를 serialize하는 데 사용할 수도 있습니다. SOAP는 특히 XML을 사용하여 프로시저 호출을 전송하기 위해 디자인된 XML 기반 프로토콜입니다.

개체를 직렬화하거나 역직렬화하려면 <xref:System.Xml.Serialization.XmlSerializer> 클래스를 사용합니다. 클래스가 serialize되도록 하려면 XML 스키마 정의 도구를 사용합니다.

## <a name="see-also"></a>참고 항목

- [이진 Serialization](binary-serialization.md)
- [ASP.NET 및 XML 웹 서비스 클라이언트를 사용하여 만든 XML 웹 서비스](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/7bkzywba(v=vs.100))
