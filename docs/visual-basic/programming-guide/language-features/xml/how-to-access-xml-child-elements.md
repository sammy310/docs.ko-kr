---
description: '자세한 정보: 방법: XML 자식 요소 액세스 (Visual Basic)'
title: '방법: XML 자식 요소에 액세스'
ms.date: 07/20/2015
helpviewer_keywords:
- XML axis [Visual Basic], child
- child axis property [Visual Basic]
- XML child axis property [Visual Basic]
- XML [Visual Basic], accessing
ms.assetid: 6689eb36-c471-469f-a82d-099ab8197b25
ms.openlocfilehash: fad4d45853006762bc319b0ff8f9143ef13058da
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/14/2021
ms.locfileid: "100433241"
---
# <a name="how-to-access-xml-child-elements-visual-basic"></a>방법: XML 자식 요소 액세스(Visual Basic)

이 예제에서는 자식 축 속성을 사용 하 여 XML 요소에 지정 된 이름의 모든 XML 자식 요소에 액세스 하는 방법을 보여 줍니다. 특히, 속성을 사용 하 여 <xref:System.Xml.Linq.XElement.Value%2A> `name` 자식 축 속성이 반환 하는 컬렉션의 첫 번째 요소 값을 가져옵니다. `name`자식 축 속성은 개체의 이라는 모든 자식 요소를 가져옵니다 `phone` `contact` . 또한이 예제에서는 자식 축 속성을 사용 하 여 `phone` 개체에 포함 된 이라는 모든 자식 요소에 액세스 `phone` `contact` 합니다.  
  
## <a name="example"></a>예  

 [!code-vb[VbXMLSamples#10](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples4.vb#10)]  
  
## <a name="compile-the-code"></a>코드 컴파일  

 이 예제에는 다음 사항이 필요합니다.  
  
- <xref:System.Xml.Linq> 네임스페이스에 대한 참조  
  
## <a name="see-also"></a>추가 정보

- <xref:System.Xml.Linq.XContainer.Elements%2A?displayProperty=nameWithType>
- [XML Child Axis Property](../../../language-reference/xml-axis/xml-child-axis-property.md)
- [XML 값 속성](../../../language-reference/xml-axis/xml-value-property.md)
- [Visual Basic에서 XML에 액세스](accessing-xml.md)
- [XML](index.md)
