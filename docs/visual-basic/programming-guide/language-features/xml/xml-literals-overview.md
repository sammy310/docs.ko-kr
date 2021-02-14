---
description: '자세한 정보: XML 리터럴 개요 (Visual Basic)'
title: XML 리터럴 개요
ms.date: 07/20/2015
helpviewer_keywords:
- XML literals [Visual Basic], about XML literals
- declaring XML literals [Visual Basic]
- LINQ to XML [Visual Basic], XML literals
- literals [Visual Basic], XML
ms.assetid: 37987c15-4ab8-471b-bd45-399816bfb57f
ms.openlocfilehash: 5544c0238b117ed5b9b2f9cdab312127736e97d7
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/14/2021
ms.locfileid: "100423851"
---
# <a name="xml-literals-overview-visual-basic"></a>XML 리터럴 개요(Visual Basic)

*Xml 리터럴을* 사용 하면 xml을 Visual Basic 코드에 직접 통합할 수 있습니다. XML 리터럴 구문은 [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] 개체를 나타내며 xml 1.0 구문과 유사 합니다. 이렇게 하면 코드의 구조가 최종 XML과 동일 하기 때문에 XML 요소와 문서를 프로그래밍 방식으로 쉽게 만들 수 있습니다.  
  
 Visual Basic XML 리터럴을 개체로 컴파일합니다 [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] . [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] XML을 만들고 조작 하는 간단한 개체 모델을 제공 하며,이 모델은 LINQ (Language-Integrated Query)와 잘 통합 됩니다. 자세한 내용은 <xref:System.Xml.Linq.XElement>를 참조하세요.  
  
 Visual Basic 식을 XML 리터럴에 포함할 수 있습니다. 런타임에 응용 프로그램은 [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] 포함 된 식의 값을 통합 하 여 각 리터럴에 대 한 개체를 만듭니다. 이렇게 하면 XML 리터럴 내에서 동적 콘텐츠를 지정할 수 있습니다. 자세한 내용은 [XML의 포함 식](embedded-expressions-in-xml.md)을 참조 하세요.  
  
 Xml 리터럴 구문과 XML 1.0 구문 간의 차이점에 대 한 자세한 내용은 [Xml 리터럴 및 xml 1.0 사양](xml-literals-and-the-xml-1-0-specification.md)을 참조 하십시오.  
  
## <a name="simple-literals"></a>단순 리터럴  

 [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)]올바른 XML을 입력 하거나 붙여넣어 Visual Basic 코드에서 개체를 만들 수 있습니다. XML 요소 리터럴은 개체를 반환 <xref:System.Xml.Linq.XElement> 합니다. 자세한 내용은 [Xml 요소 리터럴](../../../language-reference/xml-literals/xml-element-literal.md) 및 xml [리터럴 및 xml 1.0 사양](xml-literals-and-the-xml-1-0-specification.md)을 참조 하세요. 다음 예제에서는 여러 자식 요소가 있는 XML 요소를 만듭니다.  
  
 [!code-vb[VbXMLSamples#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples2.vb#5)]  
  
 다음 예제와 같이를 사용 하 여 XML 리터럴을 시작 하 여 XML 문서를 만들 수 있습니다 `<?xml version="1.0"?>` . XML 문서 리터럴은 개체를 반환 <xref:System.Xml.Linq.XDocument> 합니다. 자세한 내용은 [XML 문서 리터럴](../../../language-reference/xml-literals/xml-document-literal.md)을 참조 하세요.  
  
 [!code-vb[VbXMLSamples#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples2.vb#6)]  
  
> [!NOTE]
> Visual Basic의 XML 리터럴 구문은 XML 1.0 사양의 구문과 동일 하지 않습니다. 자세한 내용은 [Xml 리터럴 및 xml 1.0 사양](xml-literals-and-the-xml-1-0-specification.md)을 참조 하세요.  
  
## <a name="line-continuation"></a>줄 연속  

 XML 리터럴은 줄 연속 문자 (공백-밑줄-enter 시퀀스)를 사용 하지 않고 여러 줄에 걸쳐 있을 수 있습니다. 이렇게 하면 코드에서 XML 리터럴을 XML 문서와 쉽게 비교할 수 있습니다.  
  
 컴파일러는 줄 연속 문자를 XML 리터럴의 일부로 처리 합니다. 따라서 개체에 속하는 경우에만 공백 밑줄 입력 시퀀스를 사용 해야 합니다 [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] .  
  
 그러나 포함 된 식에 여러 줄 식이 있는 경우에는 줄 연속 문자가 필요 합니다. 자세한 내용은 [XML의 포함 식](embedded-expressions-in-xml.md)을 참조 하세요.  
  
## <a name="embedding-queries-in-xml-literals"></a>XML 리터럴에 쿼리 포함  

 포함 된 식에 쿼리를 사용할 수 있습니다. 이렇게 하면 쿼리에서 반환 된 요소가 XML 요소에 추가 됩니다. 이렇게 하면 사용자 쿼리의 결과와 같은 동적 콘텐츠를 XML 리터럴에 추가할 수 있습니다.  
  
 예를 들어 다음 코드에서는 포함 된 쿼리를 사용 하 여 배열의 멤버에서 XML 요소를 만든 `phoneNumbers2` 다음 해당 요소를의 자식으로 추가 합니다 `contact2` .  
  
 [!code-vb[VbXMLSamples#7](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples2.vb#7)]  
  
## <a name="how-the-compiler-creates-objects-from-xml-literals"></a>컴파일러가 XML 리터럴에서 개체를 만드는 방법  

 Visual Basic 컴파일러는 XML 리터럴을 해당 생성자에 대 한 호출로 변환 [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] 하 여 개체를 빌드합니다 [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] . 예를 들어 Visual Basic 컴파일러는 다음 코드 예제를 XML 버전 명령의 생성자에 대 한 호출로 변환 <xref:System.Xml.Linq.XProcessingInstruction> 하 <xref:System.Xml.Linq.XElement> 고, 및 요소에 대 한 생성자를 호출 하 `<contact>` 고, `<name>` `<phone>` <xref:System.Xml.Linq.XAttribute> 특성에 대 한 생성자를 `type` 호출 합니다. 구체적으로 다음 샘플의 특성을 지정 하는 경우 Visual Basic 컴파일러는 생성자를 <xref:System.Xml.Linq.XAttribute.%23ctor%28System.Xml.Linq.XName%2CSystem.Object%29> 두 번 호출 합니다. 첫 번째는 매개 변수의 값 `type` `name` 및 `home` 매개 변수에 대 한 값을 전달 합니다 `value` . 두 번째는 매개 변수의 값도 전달 `type` `name` 하지만 `work` `value` 매개 변수의 값은 전달 하지 않습니다.  
  
 [!code-vb[VbXMLSamples#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples2.vb#6)]  
  
## <a name="see-also"></a>추가 정보

- <xref:System.Xml.Linq.XElement>
- [Visual Basic에서 XML 만들기](creating-xml.md)
- [XML의 포함 식](embedded-expressions-in-xml.md)
- [XML 문서 리터럴](../../../language-reference/xml-literals/xml-document-literal.md)
- [XML 요소 리터럴](../../../language-reference/xml-literals/xml-element-literal.md)
- [XML 리터럴](../../../language-reference/xml-literals/index.md)
