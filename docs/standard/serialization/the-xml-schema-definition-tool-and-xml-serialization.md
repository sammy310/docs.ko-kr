---
title: XML 스키마 정의 도구 및 XML Serialization
description: XML 스키마 정의 도구는 XSD 스키마에 대한 C# 또는 Visual Basic 클래스 파일을 생성하거나 라이브러리 또는 실행 파일에서 XML 스키마를 생성합니다.
ms.date: 03/30/2017
helpviewer_keywords:
- Xsd.exe
- XML serialization, XML Schema Definition tool
- XML Schema Definition tool
- serialization, XML Schema Definition tool
ms.assetid: 3c03f855-f931-47ff-bbc6-50c0367a16e4
ms.openlocfilehash: c88770403d4c2abfb5ce99f44ea1bec1f8337545
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/06/2020
ms.locfileid: "84279778"
---
# <a name="the-xml-schema-definition-tool-and-xml-serialization"></a>XML 스키마 정의 도구 및 XML Serialization

XML 스키마 정의 도구([XML Schema Definition Tool(Xsd.exe)](xml-schema-definition-tool-xsd-exe.md))는 Windows&reg; SDK(소프트웨어 개발 키트)의 일부로 .NET Framework 도구와 함께 설치됩니다. 이 도구는 주로 다음 두 가지 목적으로 디자인되었습니다.  
  
- 특정 XSD(XML 스키마 정의 언어) 스키마를 따르는 C# 또는 Visual Basic 클래스 파일을 생성합니다. 이 도구는 XML 스키마를 인수로 받아서 <xref:System.Xml.Serialization.XmlSerializer>로 serialize될 때 스키마를 따르는 여러 클래스가 포함된 파일을 출력합니다. 도구를 사용하여 특정 스키마를 따르는 클래스를 생성하는 방법에 대한 자세한 내용은 [방법: XML 스키마 정의 도구를 사용하여 클래스 및 XML 스키마 문서 생성](xml-schema-def-tool-gen.md)을 참조하세요.  
  
- .dll 파일 또는 .exe 파일에서 XML 스키마 문서를 생성합니다. 만들었거나 특성으로 수정한 파일 집합의 스키마를 보려면 DLL 또는 EXE를 도구에 인수로 전달하여 XML 스키마를 생성합니다. 도구를 사용하여 클래스 집합에서 XML 스키마 문서를 생성하는 방법에 대한 자세한 내용은 [방법: XML 스키마 정의 도구를 사용하여 클래스 및 XML 스키마 문서 생성](xml-schema-def-tool-gen.md)을 참조하세요.  
  
도구 사용에 대한 자세한 내용은 [XML 스키마 정의 도구(Xsd.exe)](xml-schema-definition-tool-xsd-exe.md)를 참조하세요.  
  
## <a name="see-also"></a>참조

- <xref:System.Data.DataSet>
- [XML serialization 소개](introducing-xml-serialization.md)
- [XML 스키마 정의 도구(Xsd.exe)](xml-schema-definition-tool-xsd-exe.md)
- <xref:System.Xml.Serialization.XmlSerializer>
- [방법: 개체 직렬화](how-to-serialize-an-object.md)
- [방법: 개체 역직렬화](how-to-deserialize-an-object.md)
- [방법: XML 스키마 정의 도구를 사용하여 클래스 및 XML 스키마 문서 생성](xml-schema-def-tool-gen.md)
- [XML 스키마의 바인딩 지원](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/sh1e66zd(v=vs.100))
