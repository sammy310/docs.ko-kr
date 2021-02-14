---
description: '자세한 정보: 방법: XML 하위 요소 액세스 (Visual Basic)'
title: '방법: XML 하위 요소에 액세스'
ms.date: 07/20/2015
helpviewer_keywords:
- XML descendent axis property [Visual Basic]
- XML axis [Visual Basic], descendent
- descendent axis property [Visual Basic]
- XML [Visual Basic], accessing
ms.assetid: aabfa258-4112-4e7e-bab9-403f96072ef7
ms.openlocfilehash: d8f3176a91c2f637f49d2754513f3253399ee8ed
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/14/2021
ms.locfileid: "100433176"
---
# <a name="how-to-access-xml-descendant-elements-visual-basic"></a>방법: XML 하위 요소 액세스(Visual Basic)

이 예제에서는 하위 항목 축 속성을 사용 하 여 지정 된 이름의 xml 요소에 포함 된 모든 XML 요소에 액세스 하는 방법을 보여 줍니다. 특히, 속성을 사용 하 여 `Value` `name` 하위 항목 축 속성이 반환 하는 컬렉션의 첫 번째 요소 값을 가져옵니다. `name`하위 축 속성은 개체에 포함 된 이라는 모든 요소 `name` 를 가져옵니다 `contacts` . 또한이 예제에서는 `phone` 하위 항목 축 속성을 사용 하 여 `phone` 개체에 포함 된 이라는 모든 하위 요소에 액세스 합니다 `contacts` .  
  
## <a name="example"></a>예  

 [!code-vb[VbXMLSamples#31](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples13.vb#31)]  
  
## <a name="compile-the-code"></a>코드 컴파일  

 이 예제에는 다음 사항이 필요합니다.  
  
- <xref:System.Xml.Linq> 네임스페이스에 대한 참조  
  
## <a name="see-also"></a>추가 정보

- <xref:System.Xml.Linq.XContainer.Descendants%2A?displayProperty=nameWithType>
- [XML Descendant Axis Property](../../../language-reference/xml-axis/xml-descendant-axis-property.md)
- [XML 값 속성](../../../language-reference/xml-axis/xml-value-property.md)
- [Visual Basic에서 XML에 액세스](accessing-xml.md)
- [XML](index.md)
