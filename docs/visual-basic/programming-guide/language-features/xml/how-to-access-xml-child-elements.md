---
title: '방법: XML 자식 요소 액세스'
ms.date: 07/20/2015
helpviewer_keywords:
- XML axis [Visual Basic], child
- child axis property [Visual Basic]
- XML child axis property [Visual Basic]
- XML [Visual Basic], accessing
ms.assetid: 6689eb36-c471-469f-a82d-099ab8197b25
ms.openlocfilehash: af5ea809cb0777b16230f20e133764dd5f1f86d9
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/22/2019
ms.locfileid: "74332334"
---
# <a name="how-to-access-xml-child-elements-visual-basic"></a>방법: XML 자식 요소 액세스(Visual Basic)
이 예제에서는 자식 축 속성을 사용 하 여 XML 요소에 지정 된 이름의 모든 XML 자식 요소에 액세스 하는 방법을 보여 줍니다. 특히 <xref:System.Xml.Linq.XElement.Value%2A> 속성을 사용 하 여 `name` 자식 축 속성이 반환 하는 컬렉션의 첫 번째 요소 값을 가져옵니다. `name` 자식 축 속성은 `contact` 개체의 `phone` 이라는 모든 자식 요소를 가져옵니다. 또한이 예제에서는 `phone` 자식 축 속성을 사용 하 여 `contact` 개체에 포함 된 `phone` 라는 모든 자식 요소에 액세스 합니다.  
  
## <a name="example"></a>예제  
 [!code-vb[VbXMLSamples#10](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples4.vb#10)]  
  
## <a name="compiling-the-code"></a>코드 컴파일  
 이 예제에는 다음 사항이 필요합니다.  
  
- <xref:System.Xml.Linq> 네임스페이스에 대한 참조  
  
## <a name="see-also"></a>참고 항목

- <xref:System.Xml.Linq.XContainer.Elements%2A?displayProperty=nameWithType>
- [XML Child 축 속성](../../../../visual-basic/language-reference/xml-axis/xml-child-axis-property.md)
- [XML 값 속성](../../../../visual-basic/language-reference/xml-axis/xml-value-property.md)
- [Visual Basic에서 XML에 액세스](../../../../visual-basic/programming-guide/language-features/xml/accessing-xml.md)
- [XML](../../../../visual-basic/programming-guide/language-features/xml/index.md)
