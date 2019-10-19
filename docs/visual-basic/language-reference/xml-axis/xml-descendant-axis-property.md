---
title: XML 하위 항목 축 속성(Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.XmlPropertyDescendantsAxis
helpviewer_keywords:
- Visual Basic code, accessing XML
- XML descendant axis property [Visual Basic]
- descendant axis property [Visual Basic]
- XML axis [Visual Basic], descendant
- XML [Visual Basic], accessing
ms.assetid: a178f85b-5d54-438f-8479-40b62af6fe76
ms.openlocfilehash: e2c3e01808d3eeb18f6753a5fc79b8627e7f323b
ms.sourcegitcommit: 1f12db2d852d05bed8c53845f0b5a57a762979c8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2019
ms.locfileid: "72582226"
---
# <a name="xml-descendant-axis-property-visual-basic"></a>XML 하위 항목 축 속성(Visual Basic)

@No__t_0 개체, <xref:System.Xml.Linq.XDocument> 개체, <xref:System.Xml.Linq.XElement> 개체 컬렉션 또는 <xref:System.Xml.Linq.XDocument> 개체 컬렉션의 하위 항목에 대 한 액세스를 제공 합니다.

## <a name="syntax"></a>구문

```vb
object...<descendant>
```

## <a name="parts"></a>요소

`object` 필수입니다. <xref:System.Xml.Linq.XElement> 개체, <xref:System.Xml.Linq.XDocument> 개체, <xref:System.Xml.Linq.XElement> 개체의 컬렉션 또는 <xref:System.Xml.Linq.XDocument> 개체의 컬렉션입니다.

`...<` 필수입니다. 하위 축 속성의 시작을 나타냅니다.

`descendant` 필수입니다. [@No__t_0 형식으로 액세스할 하위 노드의 이름입니다.

|파트|설명|
|----------|-----------------|
|`prefix`|(선택 사항) 하위 노드에 대 한 XML 네임 스페이스 접두사입니다. 는 `Imports` 문을 사용 하 여 정의 된 전역 XML 네임 스페이스 여야 합니다.|
|`name`|필수 요소. 하위 노드의 로컬 이름입니다. [선언 된 XML 요소 및 특성의 이름](../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md)을 참조 하세요.|

`>` 필수입니다. 하위 축 속성의 끝을 나타냅니다.

## <a name="return-value"></a>반환 값

<xref:System.Xml.Linq.XElement> 개체의 컬렉션입니다.

## <a name="remarks"></a>주의

XML 하위 항목 축 속성을 사용 하 여 <xref:System.Xml.Linq.XElement> 또는 <xref:System.Xml.Linq.XDocument> 개체 또는 <xref:System.Xml.Linq.XElement> 또는 <xref:System.Xml.Linq.XDocument> 개체의 컬렉션에서 이름별로 하위 노드에 액세스할 수 있습니다. XML `Value` 속성을 사용 하 여 반환 된 컬렉션에서 첫 번째 하위 노드의 값에 액세스할 수 있습니다. 자세한 내용은 [XML Value 속성](../../../visual-basic/language-reference/xml-axis/xml-value-property.md)을 참조 하세요.

Visual Basic 컴파일러는 하위 항목 축 속성을 <xref:System.Xml.Linq.XContainer.Descendants%2A> 메서드에 대 한 호출로 변환 합니다.

## <a name="xml-namespaces"></a>XML 네임스페이스

하위 축 속성의 이름은 `Imports` 문으로 전역적으로 선언 된 XML 네임 스페이스만 사용할 수 있습니다. XML 요소 리터럴 내에서 로컬로 선언 된 XML 네임 스페이스를 사용할 수 없습니다. 자세한 내용은 [Imports 문 (XML 네임 스페이스)](../../../visual-basic/language-reference/statements/imports-statement-xml-namespace.md)을 참조 하세요.

## <a name="example"></a>예제

다음 예에서는 `name` 이라는 첫 번째 하위 노드의 값 및 `contacts` 개체에서 `phone` 이라는 모든 하위 노드의 값에 액세스 하는 방법을 보여 줍니다.

[!code-vb[VbXMLSamples#25](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples11.vb#25)]

이 코드의 텍스트는 다음과 같습니다.

`Name: Patrick Hines`

`Home Phone = 206-555-0144`

## <a name="example"></a>예제

다음 예제에서는 `ns`를 XML 네임스페이스 접두사로 선언한 다음 그런 다음 네임 스페이스의 접두사를 사용 하 여 XML 리터럴을 만들고 `ns:name` 정규화 된 이름을 사용 하 여 첫 번째 자식 노드의 값에 액세스 합니다.

[!code-vb[VbXMLSamples#26](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples12.vb#26)]

이 코드의 텍스트는 다음과 같습니다.

`Name: Patrick Hines`

## <a name="see-also"></a>참조

- <xref:System.Xml.Linq.XElement>
- [XML 축 속성](../../../visual-basic/language-reference/xml-axis/index.md)
- [XML 리터럴](../../../visual-basic/language-reference/xml-literals/index.md)
- [Visual Basic에서 XML 만들기](../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)
- [선언된 XML 요소 및 특성의 이름](../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md)
