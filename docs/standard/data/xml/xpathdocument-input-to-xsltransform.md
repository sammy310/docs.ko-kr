---
title: XslTransform에 대한 XPathDocument 입력
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 7d1bbe8b-ed43-4e62-a5ba-d602d244f4ae
ms.openlocfilehash: 29bb345c2654baec8fbd2adce3788a4b4f2d582d
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95720869"
---
# <a name="xpathdocument-input-to-xsltransform"></a>XslTransform에 대한 XPathDocument 입력

<xref:System.Xml.XPath.XPathDocument>는 <xref:System.Xml.Xsl.XslTransform>을 사용하여 문서를 처리하기 위한 읽기 전용 캐시입니다. 이 캐시는 XML DOM(문서 개체 모델)과 구조상 유사하지만 <xref:System.Xml.XPath.XPathNavigator>의 XPath 최적화 함수를 사용하여 XSLT(Extensible Stylesheet Language for Transformations) 처리와 XPath(XML Path Language) 데이터 모델에 대해 최적화되었습니다.  
  
> [!NOTE]
> <xref:System.Xml.Xsl.XslTransform> 클래스는 .NET Framework 2.0에서 사용되지 않습니다. <xref:System.Xml.Xsl.XslCompiledTransform> 클래스를 사용하여 XSLT(Extensible Stylesheet Language for Transformations) 변환을 수행할 수 있습니다. 자세한 내용은 [XslCompiledTransform 클래스 사용](using-the-xslcompiledtransform-class.md) 및 [XslTransform 클래스에서 마이그레이션](migrating-from-the-xsltransform-class.md)을 참조하세요.  
  
 다음 코드 샘플에서는 변환에 대한 입력으로 <xref:System.Xml.XPath.XPathDocument>를 만듭니다.  
  
```vb  
Dim xslt as XslTransform = new XslTransform()  
Xslt.Load(someStylesheet)  
Dim doc as XPathDocument = New XPathDocument("books.xml")  
Dim fs as StringWriter = new StringWriter()  
Xslt.Transform(doc, Nothing, fs, Nothing);  
```  
  
```csharp  
XslTransform xslt = new XslTransform();  
Xslt.Load(someStylesheet);  
XPathDocument doc = XPathDocument("books.xml");  
StringWriter fs = new StringWriter();  
Xslt.Transform(doc, null, fs, null);  
```  
  
## <a name="see-also"></a>참조

- [XslTransform 클래스의 XSLT 프로세서 구현](xsltransform-class-implements-the-xslt-processor.md)
