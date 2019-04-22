---
title: XML 문서 리터럴(Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.XmlLiteralDocument
helpviewer_keywords:
- XML document literal [Visual Basic]
- XML literals [Visual Basic], document
- XML documents [Visual Basic], creating
- document literal [Visual Basic]
ms.assetid: f7bbee56-0911-41de-b907-96f20450137b
ms.openlocfilehash: f58c1365e145166dfe122d455854d44526300a1e
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "58814629"
---
# <a name="xml-document-literal-visual-basic"></a>XML 문서 리터럴(Visual Basic)
리터럴 나타내는 <xref:System.Xml.Linq.XDocument> 개체입니다.  
  
## <a name="syntax"></a>구문  
  
```xml  
<?xml version="1.0" [encoding="encoding"] [standalone="standalone"] ?>  
[ piCommentList ]  
rootElement  
[ piCommentList ]  
```  
  
## <a name="parts"></a>요소  
  
|용어|정의|  
|---|---|  
|`encoding`|선택 사항입니다. 리터럴 텍스트 문서의 인코딩을 선언 사용 됩니다.|  
|`standalone`|선택 사항입니다. 리터럴 텍스트입니다. "Yes" 여야 합니다 또는 "no"입니다.|  
|`piCommentList`|선택 사항입니다. XML 처리 명령 및 XML 주석 목록입니다. 다음 형식을 갖습니다.<br /><br /> `piComment [` `piComment` `... ]`<br /><br /> 각 `piComment` 다음 중 하나일 수 있습니다.<br /><br /> -   [XML 처리 명령 리터럴](../../../visual-basic/language-reference/xml-literals/xml-processing-instruction-literal.md)합니다.<br />-   [XML 주석 리터럴](../../../visual-basic/language-reference/xml-literals/xml-comment-literal.md)합니다.|  
|`rootElement`|필수 요소. 문서의 루트 요소입니다. 형식에는 다음 중 하나입니다.<br /><br /> <ul><li>[XML 요소 리터럴](../../../visual-basic/language-reference/xml-literals/xml-element-literal.md)합니다.</li><li>포함 식 형식의 `<%=` `elementExp` `%>`합니다. `elementExp` 다음 중 하나를 반환 합니다.<br /><br /> <ul><li><xref:System.Xml.Linq.XElement> 개체입니다.</li><li>하나를 포함 하는 컬렉션 <xref:System.Xml.Linq.XElement> 개체와 임의 개수의 <xref:System.Xml.Linq.XProcessingInstruction> 고 <xref:System.Xml.Linq.XComment> 개체입니다.</li></ul></li></ul><br /> 자세한 내용은 [XML의 포함 식](../../../visual-basic/programming-guide/language-features/xml/embedded-expressions-in-xml.md)합니다.|  
  
## <a name="return-value"></a>반환 값  
 <xref:System.Xml.Linq.XDocument> 개체입니다.  
  
## <a name="remarks"></a>설명  
 XML 문서 리터럴에 리터럴의 시작 XML 선언에 의해 식별 됩니다. 각 XML 문서 리터럴에 루트 XML 요소가 하나만 있어야, 있지만 원하는 수의 XML 처리 명령과 XML 주석에 있습니다.  
  
 XML 문서 리터럴에 XML 요소에 나타날 수 없습니다.  
  
> [!NOTE]
>  XML 리터럴을 줄 연속 문자를 사용 하지 않고 여러 줄을 확장할 수 있습니다. 이 옵션을 사용 하면 XML 문서에서 콘텐츠를 복사 하 고 Visual Basic 프로그램에 직접 붙여넣을 수 있습니다.  
  
 리터럴 XML 문서에 대 한 호출으로 변환 하는 Visual Basic 컴파일러는 <xref:System.Xml.Linq.XDocument.%23ctor%2A> 고 <xref:System.Xml.Linq.XDeclaration.%23ctor%2A> 생성자입니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는 XML 선언, 처리 명령, 주석 및 다른 요소를 포함 하는 요소에는 XML 문서를 만듭니다.  
  
 [!code-vb[VbXMLSamples#30](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples13.vb#30)]  
  
## <a name="see-also"></a>참고자료

- <xref:System.Xml.Linq.XElement>
- <xref:System.Xml.Linq.XProcessingInstruction>
- <xref:System.Xml.Linq.XComment>
- <xref:System.Xml.Linq.XDocument>
- [XML 처리 명령 리터럴](../../../visual-basic/language-reference/xml-literals/xml-processing-instruction-literal.md)
- [XML 주석 리터럴](../../../visual-basic/language-reference/xml-literals/xml-comment-literal.md)
- [XML 요소 리터럴](../../../visual-basic/language-reference/xml-literals/xml-element-literal.md)
- [XML 리터럴](../../../visual-basic/language-reference/xml-literals/index.md)
- [Visual Basic에서 XML 만들기](../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)
- [XML의 포함 식](../../../visual-basic/programming-guide/language-features/xml/embedded-expressions-in-xml.md)
