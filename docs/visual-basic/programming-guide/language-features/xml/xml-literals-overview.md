---
title: XML 리터럴 개요(Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- XML literals [Visual Basic], about XML literals
- declaring XML literals [Visual Basic]
- LINQ to XML [Visual Basic], XML literals
- literals [Visual Basic], XML
ms.assetid: 37987c15-4ab8-471b-bd45-399816bfb57f
ms.openlocfilehash: a7b70669131ae35135088418e4b33b3ae289d322
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "58839888"
---
# <a name="xml-literals-overview-visual-basic"></a>XML 리터럴 개요(Visual Basic)
*XML 리터럴* Visual Basic 코드에 직접 XML을 통합할 수 있습니다. XML 리터럴 구문을 나타내는 [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] 개체 되며 XML 1.0 구문과 비슷합니다. 이렇게 하면 쉽게 코드에 동일한 최종 XML 구조 때문에 XML 요소와 문서를 프로그래밍 방식으로 만들 수 있습니다.  
  
 Visual Basic XML 리터럴을 컴파일합니다 [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] 개체입니다. [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] 만들고 XML을 조작 하기 위한 간단한 개체 모델 및이 모델 통합도 제공 [!INCLUDE[vbteclinqext](~/includes/vbteclinqext-md.md)]합니다. 자세한 내용은 <xref:System.Xml.Linq.XElement>을 참조하세요.  
  
 Xml 리터럴에 Visual Basic 식을 포함할 수 있습니다. 런타임 시 응용 프로그램 만들기를 [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] 각 리터럴, 포함된 된 식의 값을 통합에 대 한 개체입니다. 이렇게 하면 XML 리터럴 내에서 동적 콘텐츠를 지정할 수 있습니다. 자세한 내용은 [XML의 포함 식](../../../../visual-basic/programming-guide/language-features/xml/embedded-expressions-in-xml.md)합니다.  
  
 XML 리터럴 구문 및 XML 1.0 구문 간의 차이점에 대 한 자세한 내용은 참조 하세요. [XML 리터럴 및 XML 1.0 사양에](../../../../visual-basic/programming-guide/language-features/xml/xml-literals-and-the-xml-1-0-specification.md)입니다.  
  
## <a name="simple-literals"></a>간단한 리터럴  
 만들 수는 [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] 입력 하거나 유효한 XML에 붙여 넣어 Visual Basic 코드의 개체입니다. XML 요소 리터럴의 반환을 <xref:System.Xml.Linq.XElement> 개체입니다. 자세한 내용은 [XML 요소 리터럴](../../../../visual-basic/language-reference/xml-literals/xml-element-literal.md) 하 고 [XML 리터럴 및 XML 1.0 사양에](../../../../visual-basic/programming-guide/language-features/xml/xml-literals-and-the-xml-1-0-specification.md)입니다. 다음 예제에서는 몇 가지 자식 요소가 있는 XML 요소를 만듭니다.  
  
 [!code-vb[VbXMLSamples#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples2.vb#5)]  
  
 XML 리터럴을 사용 하 여 시작 하 여 XML 문서를 만들 수 있습니다 `<?xml version="1.0"?>`다음 예제에서와 같이 합니다. XML 문서 리터럴의 반환을 <xref:System.Xml.Linq.XDocument> 개체입니다. 자세한 내용은 [XML 문서 리터럴](../../../../visual-basic/language-reference/xml-literals/xml-document-literal.md)합니다.  
  
 [!code-vb[VbXMLSamples#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples2.vb#6)]  
  
> [!NOTE]
>  Visual Basic의 XML 리터럴 구문을 구문에 XML 1.0 사양과 일치 하지 않습니다. 자세한 내용은 [XML 리터럴 및 XML 1.0 사양에](../../../../visual-basic/programming-guide/language-features/xml/xml-literals-and-the-xml-1-0-specification.md)입니다.  
  
## <a name="line-continuation"></a>줄 연속 문자  
 줄 연속 문자 (공백 밑줄 enter 순서)를 사용 하지 않고 XML 리터럴의 여러 줄으로 나누어 입력할 수 있습니다. 이 XML 문서를 사용 하 여 코드에서 XML 리터럴의 비교할 쉽게 있습니다.  
  
 컴파일러는 XML 리터럴을의 일부로 줄 연속 문자를 처리 합니다. 따라서에 속해 있을 때만 공간 밑줄 입력 시퀀스 사용 해야 하는 [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] 개체입니다.  
  
 그러나 여러 줄의 식이 포함된 된 식에 있는 경우 줄 연속 문자가 필요지 않습니다. 자세한 내용은 [XML의 포함 식](../../../../visual-basic/programming-guide/language-features/xml/embedded-expressions-in-xml.md)합니다.  
  
## <a name="embedding-queries-in-xml-literals"></a>XML 리터럴의 포함 쿼리  
 포함된 식에서 쿼리를 사용할 수 있습니다. 이렇게 하면 쿼리에서 반환 하는 요소는 XML 요소에 추가 됩니다. 이렇게 하면 XML 리터럴을에 사용자의 쿼리 결과 같은 동적 콘텐츠를 추가할 수 있습니다.  
  
 예를 들어, 다음 코드를 사용 하 여 포함 된 쿼리를의 멤버에서 XML 요소를 만드는 합니다 `phoneNumbers2` 배열을 추가한 다음 요소 자식으로 `contact2`입니다.  
  
 [!code-vb[VbXMLSamples#7](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples2.vb#7)]  
  
## <a name="how-the-compiler-creates-objects-from-xml-literals"></a>컴파일러가는 XML 리터럴에서 개체를 만드는 방법  
 Visual Basic 컴파일러는 XML 리터럴을 해당 호출으로 변환 [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] 구축 하는 생성자를 [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] 개체입니다. 예를 들어, Visual Basic 컴파일러는 변환 다음 코드 예제에 대 한 호출을 <xref:System.Xml.Linq.XProcessingInstruction> XML 버전 명령에 대 한 생성자를 호출 합니다 <xref:System.Xml.Linq.XElement> 생성자에 대 한는 `<contact>`, `<name>`, 및 `<phone>` 요소 및에 대 한 호출을 <xref:System.Xml.Linq.XAttribute> 에 대 한 생성자는 `type` 특성입니다. 특히, 다음 예제의 특성 지정, Visual Basic 컴파일러를 호출 합니다 <xref:System.Xml.Linq.XAttribute.%23ctor%28System.Xml.Linq.XName%2CSystem.Object%29> 생성자를 두 번입니다. 첫 번째 값을 전달 `type` 에 대 한 합니다 `name` 매개 변수와 값 `home` 에 대 한는 `value` 매개 변수입니다. 두 번째는 값을 전달할 수도 `type` 에 대 한 합니다 `name` 매개 변수 이지만 값 `work` 에 대 한는 `value` 매개 변수입니다.  
  
 [!code-vb[VbXMLSamples#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples2.vb#6)]  
  
## <a name="see-also"></a>참고자료

- <xref:System.Xml.Linq.XElement>
- [Visual Basic에서 XML 만들기](../../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)
- [XML의 포함 식](../../../../visual-basic/programming-guide/language-features/xml/embedded-expressions-in-xml.md)
- [XML 문서 리터럴](../../../../visual-basic/language-reference/xml-literals/xml-document-literal.md)
- [XML 요소 리터럴](../../../../visual-basic/language-reference/xml-literals/xml-element-literal.md)
- [XML 리터럴](../../../../visual-basic/language-reference/xml-literals/index.md)
