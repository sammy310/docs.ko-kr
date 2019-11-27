---
title: '방법: XML 리터럴에 식 포함'
ms.date: 07/20/2015
helpviewer_keywords:
- embedded expressions [Visual Basic]
- XML literals [Visual Basic], embedded expressions
ms.assetid: 75016fad-0141-42de-8564-5051be29487e
ms.openlocfilehash: 2e8dd10b334b0271e3c9de11ed155c9d5d7aae48
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/22/2019
ms.locfileid: "74332934"
---
# <a name="how-to-embed-expressions-in-xml-literals-visual-basic"></a>방법: XML 리터럴에 식 포함(Visual Basic)
XML 리터럴을 포함 된 식과 결합 하 여 런타임에 생성 된 내용이 포함 된 XML 문서, 조각 또는 요소를 만들 수 있습니다. 다음 예제에서는 포함 식을 사용 하 여 런타임에 요소 내용, 특성 및 요소 이름을 채우는 방법을 보여 줍니다.  
  
 포함 된 식에 대 한 구문은 ASP.NET에서 사용 하는 것과 동일한 구문인 `%>``exp` `<%=` 됩니다. 자세한 내용은 [XML의 포함 식](../../../../visual-basic/programming-guide/language-features/xml/embedded-expressions-in-xml.md)을 참조 하세요.  
  
 [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] Api를 사용 하 여 [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] 개체를 만들 수도 있습니다. 자세한 내용은 <xref:System.Xml.Linq.XElement>을 참조하세요.  
  
## <a name="procedures"></a>절차  
  
#### <a name="to-insert-text-as-element-content"></a>텍스트를 요소 콘텐츠로 삽입 하려면  
  
- 다음 예제에서는 여는 이름과 닫는 name 요소 사이에 `contactName` 변수에 포함 된 텍스트를 삽입 하는 방법을 보여 줍니다.  
  
     [!code-vb[VbXMLSamples#39](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples14.vb#39)]  
  
     이 예제는 다음과 같은 출력을 생성합니다.  
  
    ```xml  
    <contact>  
      <name>Patrick Hines</name>  
    </contact>  
    ```  
  
#### <a name="to-insert-text-as-an-attribute-value"></a>텍스트를 특성 값으로 삽입 하려면  
  
- 다음 예에서는 `phoneType` 변수에 포함 된 텍스트를 `type` 특성 값으로 삽입 하는 방법을 보여 줍니다.  
  
     [!code-vb[VbXMLSamples#40](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples14.vb#40)]  
  
     이 예제는 다음과 같은 출력을 생성합니다.  
  
    ```xml  
    <contact>  
      <phone type="home">206-555-0144</phone>  
    </contact>  
    ```  
  
#### <a name="to-insert-text-for-an-element-name"></a>요소 이름에 텍스트를 삽입 하려면  
  
- 다음 예제에서는 `elementName` 변수에 포함 된 텍스트를 요소의 이름으로 삽입 하는 방법을 보여 줍니다.  
  
     이 기술을 사용 하 여 요소를 만들 때는 \</> 태그를 사용 하 여 요소를 닫아야 합니다.  
  
     [!code-vb[VbXMLSamples#41](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples14.vb#41)]  
  
     이 예제는 다음과 같은 출력을 생성합니다.  
  
    ```xml  
    <contact>  
      <name>Patrick Hines</name>  
    </contact>  
    ```  
  
## <a name="see-also"></a>참고자료

- [방법: XML 리터럴 만들기](../../../../visual-basic/programming-guide/language-features/xml/how-to-create-xml-literals.md)
- [XML의 포함 식](../../../../visual-basic/programming-guide/language-features/xml/embedded-expressions-in-xml.md)
- [Visual Basic에서 XML 만들기](../../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)
- [XML](../../../../visual-basic/programming-guide/language-features/xml/index.md)
