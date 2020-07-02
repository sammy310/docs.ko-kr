---
ms.openlocfilehash: fdec6671cbf2dae0d72dfaec07f162058b38cf9d
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/01/2020
ms.locfileid: "85620511"
---
### <a name="xmltextreader-dtd-entity-expansion-is-limited-to-10000000-characters"></a>XmlTextReader DTD 엔터티 확장은 10,000,000자로 제한됨

#### <a name="details"></a>설명

이제 DTD 엔터티 확장은 10,000,000자로 제한됩니다. DTD 엔터티 확장 없이 또는 제한된 DTD 엔터티 확장으로 XML 파일을 로드해도 영향을 받지 않습니다. 이제 파일에 10,000,000자를 초과하는 문자로 확장되는 DTD 엔터티가 있으면 로드하지 못하고 예외를 throw합니다.

#### <a name="suggestion"></a>제안 해결 방법

DTD 엔터티 확장의 제한이 10,000,000보다 너무 작으면, 값은 <xref:System.Xml.XmlReaderSettings.MaxCharactersFromEntities> 속성으로 재정의됩니다. 올바른 <xref:System.Xml.XmlReaderSettings.MaxCharactersFromEntities?displayProperty=fullName> 값을 가진 <xref:System.Xml.XmlReaderSettings?displayProperty=fullName>은 <xref:System.Xml.XmlReaderSettings?displayProperty=fullName>(즉, <xref:System.Xml.XmlReader.Create(System.String,System.Xml.XmlReaderSettings)>)을 취하도록 <code>XmlReader.Create</code>에 전달될 수 있습니다.

| 이름    | 값       |
|:--------|:------------|
| Scope   |Microsoft Edge|
|버전|4.5|
|형식|런타임

#### <a name="affected-apis"></a>영향을 받는 API

-<xref:System.Xml.XmlTextReader?displayProperty=nameWithType></li><li><xref:System.Xml.XmlTextReader.%23ctor></li><li><xref:System.Xml.XmlTextReader.%23ctor(System.IO.Stream)></li><li><xref:System.Xml.XmlTextReader.%23ctor(System.IO.Stream,System.Xml.XmlNameTable)></li><li><xref:System.Xml.XmlTextReader.%23ctor(System.IO.Stream,System.Xml.XmlNodeType,System.Xml.XmlParserContext)></li><li><xref:System.Xml.XmlTextReader.%23ctor(System.IO.TextReader)></li><li><xref:System.Xml.XmlTextReader.%23ctor(System.IO.TextReader,System.Xml.XmlNameTable)></li><li><xref:System.Xml.XmlTextReader.%23ctor(System.String)></li><li><xref:System.Xml.XmlTextReader.%23ctor(System.String,System.IO.Stream)></li><li><xref:System.Xml.XmlTextReader.%23ctor(System.String,System.IO.Stream,System.Xml.XmlNameTable)></li><li><xref:System.Xml.XmlTextReader.%23ctor(System.String,System.IO.TextReader)></li><li><xref:System.Xml.XmlTextReader.%23ctor(System.String,System.IO.TextReader,System.Xml.XmlNameTable)></li><li><xref:System.Xml.XmlTextReader.%23ctor(System.String,System.Xml.XmlNameTable)></li><li><xref:System.Xml.XmlTextReader.%23ctor(System.String,System.Xml.XmlNodeType,System.Xml.XmlParserContext)></li><li><xref:System.Xml.XmlTextReader.%23ctor(System.Xml.XmlNameTable)></li></ul>|
