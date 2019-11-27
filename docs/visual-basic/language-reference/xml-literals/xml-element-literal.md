---
title: XML 요소 리터럴
ms.date: 07/20/2015
f1_keywords:
- vb.XmlLiteralElement
helpviewer_keywords:
- XML element literal [Visual Basic]
- element literal [Visual Basic]
- XML literals [Visual Basic], element
ms.assetid: 95039642-7893-48b7-b23f-45a6c55d8f67
ms.openlocfilehash: d6d900ca6868cfffe6b0e5b349321a79c5716c46
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/22/2019
ms.locfileid: "74347022"
---
# <a name="xml-element-literal-visual-basic"></a>XML 요소 리터럴(Visual Basic)

<xref:System.Xml.Linq.XElement> 개체를 나타내는 리터럴입니다.

## <a name="syntax"></a>구문

```xml
<name [ attributeList ] />
-or-
<name [ attributeList ] > [ elementContents ] </[ name ]>
```

## <a name="parts"></a>요소

- `<`

  필수입니다. 시작 요소 태그를 엽니다.

- `name`

  필수입니다. 요소 이름입니다. 형식은 다음 중 하나입니다.

  - `[ePrefix:]eName`폼의 요소 이름에 대 한 리터럴 텍스트입니다. 여기에서 다음을 수행 합니다.

    |파트|설명|
    |---|---|
    |`ePrefix`|(선택 사항) 요소에 대 한 XML 네임 스페이스 접두사입니다. 는 파일이 나 프로젝트 수준에서 `Imports` 문으로 정의 된 전역 XML 네임 스페이스 또는이 요소 또는 부모 요소에 정의 된 로컬 XML 네임 스페이스 여야 합니다.|
    |`eName`|필수입니다. 요소 이름입니다. 형식은 다음 중 하나입니다.<br /><br /> -리터럴 텍스트 [선언 된 XML 요소 및 특성의 이름](../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md)을 참조 하세요.<br />-`<%= eNameExp %>`폼의 포함 식입니다. `eNameExp` 형식은 `String` 이거나 <xref:System.Xml.Linq.XName>으로 암시적으로 변환할 수 있는 형식 이어야 합니다.|

  - `<%= nameExp %>`폼의 포함 된 식입니다. `nameExp` 형식은 `String` 이거나 <xref:System.Xml.Linq.XName>으로 암시적으로 변환할 수 있는 형식 이어야 합니다. 요소의 닫는 태그에는 포함 식이 허용 되지 않습니다.

- `attributeList`

  (선택 사항) 리터럴에 선언 된 특성의 목록입니다.

  `attribute [ attribute ... ]`

  각 `attribute`에는 다음 구문 중 하나가 있습니다.

  - `[aPrefix:]aName=aValue`형식의 특성 할당:

    |파트|설명|
    |---|---|
    |`aPrefix`|(선택 사항) 특성에 대 한 XML 네임 스페이스 접두사입니다. 는이 요소 또는 부모 요소에 정의 된 `Imports` 문 또는 로컬 XML 네임 스페이스를 사용 하 여 정의 된 전역 XML 네임 스페이스 여야 합니다.|
    |`aName`|필수입니다. 특성의 이름입니다. 형식은 다음 중 하나입니다.<br /><br /> -리터럴 텍스트 [선언 된 XML 요소 및 특성의 이름](../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md)을 참조 하세요.<br />-`<%= aNameExp %>`폼의 포함 식입니다. `aNameExp` 형식은 `String` 이거나 <xref:System.Xml.Linq.XName>으로 암시적으로 변환할 수 있는 형식 이어야 합니다.|
    |`aValue`|(선택 사항) 특성의 값입니다. 형식은 다음 중 하나입니다.<br /><br /> -따옴표로 묶인 리터럴 텍스트입니다.<br />-`<%= aValueExp %>`폼의 포함 식입니다. 모든 형식을 사용할 수 있습니다.|

  - `<%= aExp %>`폼의 포함 된 식입니다.

- `/>`

  (선택 사항) 요소가 콘텐츠가 없는 빈 요소 임을 나타냅니다.

- `>`

  필수입니다. 시작 또는 빈 요소 태그를 끝냅니다.

- `elementContents`

  (선택 사항) 요소의 콘텐츠입니다.

  `content [ content ... ]`

  각 `content` 다음 중 하나일 수 있습니다.

  - 리터럴 텍스트입니다. 리터럴 텍스트가 있는 경우 `elementContents`의 모든 공백은 중요 합니다.

  - `<%= contentExp %>`폼의 포함 된 식입니다.

  - XML 요소 리터럴입니다.

  - XML 주석 리터럴입니다. [XML 주석 리터럴](../../../visual-basic/language-reference/xml-literals/xml-comment-literal.md)을 참조 하세요.

  - XML 처리 명령 리터럴입니다. [XML 처리 명령 리터럴](../../../visual-basic/language-reference/xml-literals/xml-processing-instruction-literal.md)을 참조 하세요.

  - XML CDATA 리터럴입니다. [XML CDATA 리터럴](../../../visual-basic/language-reference/xml-literals/xml-cdata-literal.md)을 참조 하세요.

- `</[name]>`

  (선택 사항) 요소의 닫는 태그를 나타냅니다. 선택적인 `name` 매개 변수는 포함 된 식의 결과일 때 허용 되지 않습니다.

## <a name="return-value"></a>반환 값

<xref:System.Xml.Linq.XElement> 개체입니다.

## <a name="remarks"></a>주의

XML 요소 리터럴 구문을 사용 하 여 코드에 <xref:System.Xml.Linq.XElement> 개체를 만들 수 있습니다.

> [!NOTE]
> XML 리터럴은 줄 연속 문자를 사용 하지 않고 여러 줄에 걸쳐 있을 수 있습니다. 이 기능을 사용 하면 XML 문서에서 콘텐츠를 복사 하 여 Visual Basic 프로그램에 직접 붙여넣을 수 있습니다.

`<%= exp %>` 형식의 포함 식을 사용 하면 XML 요소 리터럴에 동적 정보를 추가할 수 있습니다. 자세한 내용은 [XML의 포함 식](../../../visual-basic/programming-guide/language-features/xml/embedded-expressions-in-xml.md)을 참조 하세요.

Visual Basic 컴파일러는 XML 요소 리터럴을 <xref:System.Xml.Linq.XElement.%23ctor%2A> 생성자에 대 한 호출로 변환 하 고 필요한 경우 <xref:System.Xml.Linq.XAttribute.%23ctor%2A> 생성자를 호출 합니다.

## <a name="xml-namespaces"></a>XML 네임스페이스

XML 네임 스페이스 접두사는 동일한 네임 스페이스의 요소를 사용 하 여 코드에서 여러 번 XML 리터럴을 만들어야 하는 경우에 유용 합니다. `xmlns:xmlPrefix="xmlNamespace"` 특성 구문을 사용 하 여 정의 하는 `Imports` 문 또는 로컬 접두사를 사용 하 여 정의 하는 전역 XML 네임 스페이스 접두사를 사용할 수 있습니다. 자세한 내용은 [Imports 문 (XML 네임 스페이스)](../../../visual-basic/language-reference/statements/imports-statement-xml-namespace.md)을 참조 하세요.

XML 네임 스페이스에 대 한 범위 지정 규칙에 따라 지역 접두사는 전역 접두사 보다 우선적으로 적용 됩니다. 그러나 XML 리터럴이 XML 네임 스페이스를 정의 하는 경우 해당 네임 스페이스는 포함 된 식에 표시 되는 식에 사용할 수 없습니다. 포함 된 식은 전역 XML 네임 스페이스에만 액세스할 수 있습니다.

Visual Basic 컴파일러는 XML 리터럴에 사용 되는 각 전역 XML 네임 스페이스를 생성 된 코드에서 하나의 로컬 네임 스페이스 정의로 변환 합니다. 사용 되지 않는 전역 XML 네임 스페이스는 생성 된 코드에 표시 되지 않습니다.

## <a name="example"></a>예제

다음 예제에서는 두 개의 중첩 된 빈 요소가 있는 간단한 XML 요소를 만드는 방법을 보여 줍니다.

[!code-vb[VbXMLSamples#20](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples9.vb#20)]

이 예제에서는 다음 텍스트를 표시 합니다. 리터럴은 빈 요소의 구조를 유지 합니다.

```xml
<outer>
  <inner1></inner1>
  <inner2 />
</outer>
```

## <a name="example"></a>예제

다음 예제에서는 포함 식을 사용 하 여 요소의 이름을로 하 고 특성을 만드는 방법을 보여 줍니다.

[!code-vb[VbXMLSamples#21](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples9.vb#21)]

이 코드의 텍스트는 다음과 같습니다.

```xml
<book isbn="1234" author="My Author" year="1999" title="My Book" />
```

## <a name="example"></a>예제

다음 예제에서는 `ns`를 XML 네임스페이스 접두사로 선언한 다음 그런 다음 네임 스페이스의 접두사를 사용 하 여 XML 리터럴을 만들고 요소의 최종 형식을 표시 합니다.

[!code-vb[VbXMLSamples#22](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples10.vb#22)]

이 코드의 텍스트는 다음과 같습니다.

```xml
<ns:outer xmlns:ns="http://SomeNamespace">
  <ns:middle xmlns:ns="http://NewNamespace">
    <ns:inner1 />
    <inner2 xmlns="http://SomeNamespace" />
  </ns:middle>
</ns:outer>
```

컴파일러가 전역 XML 네임 스페이스의 접두사를 XML 네임 스페이스에 대 한 접두사 정의로 변환 했습니다. \<ns: 중간 > 요소는 \<ns: inner1 > 요소에 대 한 XML 네임 스페이스 접두사를 다시 정의 합니다. 그러나 \<ns: inner2 > 요소는 `Imports` 문에 의해 정의 된 네임 스페이스를 사용 합니다.

## <a name="see-also"></a>참고 항목

- <xref:System.Xml.Linq.XElement>
- [선언된 XML 요소 및 특성의 이름](../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md)
- [XML 주석 리터럴](../../../visual-basic/language-reference/xml-literals/xml-comment-literal.md)
- [XML CDATA 리터럴](../../../visual-basic/language-reference/xml-literals/xml-cdata-literal.md)
- [XML 리터럴](../../../visual-basic/language-reference/xml-literals/index.md)
- [Visual Basic에서 XML 만들기](../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)
- [XML의 포함 식](../../../visual-basic/programming-guide/language-features/xml/embedded-expressions-in-xml.md)
- [Imports 문(XML 네임스페이스)](../../../visual-basic/language-reference/statements/imports-statement-xml-namespace.md)
