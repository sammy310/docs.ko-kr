---
title: Imports 문-XML 네임 스페이스 (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.ImportsXmlns
helpviewer_keywords:
- XML namespace [Visual Basic], importing
- imports [Visual Basic]
- Imports statement [Visual Basic]
- namespaces [Visual Basic], importing
ms.assetid: 1f4d50a6-08c7-4c2e-8206-ccae35fcd1b4
ms.openlocfilehash: 0fca0caecfd69580510a539317856209108e5a32
ms.sourcegitcommit: 1f12db2d852d05bed8c53845f0b5a57a762979c8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2019
ms.locfileid: "72581761"
---
# <a name="imports-statement-xml-namespace"></a>Imports 문(XML 네임스페이스)

Xml 리터럴 및 XML 축 속성에 사용할 XML 네임 스페이스 접두사를 가져옵니다.

## <a name="syntax"></a>구문

```vb
Imports <xmlns:xmlNamespacePrefix = "xmlNamespaceName">
```

## <a name="parts"></a>요소

`xmlNamespacePrefix`  
(선택 사항) XML 요소와 특성이 `xmlNamespaceName`를 참조할 수 있는 문자열입니다. @No__t_0 제공 되지 않으면 가져온 XML 네임 스페이스가 기본 XML 네임 스페이스입니다. 유효한 XML 식별자 여야 합니다. 자세한 내용은 [선언 된 XML 요소 및 특성의 이름](../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md)을 참조 하세요.

`xmlNamespaceName`  
필수 요소. 가져올 XML 네임 스페이스를 식별 하는 문자열입니다.

## <a name="remarks"></a>주의

@No__t_0 문을 사용 하 여 XML 리터럴 및 XML 축 속성에 사용할 수 있는 전역 XML 네임 스페이스를 정의 하거나 `GetXmlNamespace` 연산자에 전달 되는 매개 변수로 사용할 수 있습니다. @No__t_0 문을 사용 하 여 코드에서 형식 이름을 사용 하는 데 사용할 수 있는 별칭을 가져오는 방법에 대 한 자세한 내용은 [Imports 문 (.Net 네임 스페이스 및 형식)](../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md)을 참조 하세요. @No__t_2 문을 사용 하 여 XML 네임 스페이스를 선언 하는 구문은 XML에서 사용 되는 구문과 동일 합니다. 따라서 XML 파일에서 네임 스페이스 선언을 복사 하 여 `Imports` 문에서 사용할 수 있습니다.

XML 네임 스페이스 접두사는 동일한 네임 스페이스에 있는 XML 요소를 반복 해 서 만들려는 경우에 유용 합니다. @No__t_0 문으로 선언 된 XML 네임 스페이스 접두사는 파일의 모든 코드에서 사용할 수 있다는 점에서 전역적입니다. Xml 요소 리터럴을 만들 때와 XML 축 속성에 액세스할 때이를 사용할 수 있습니다. 자세한 내용은 [Xml 요소 리터럴](../../../visual-basic/language-reference/xml-literals/xml-element-literal.md) 및 [xml 축 속성](../../../visual-basic/language-reference/xml-axis/index.md)을 참조 하세요.

네임 스페이스 접두사 없이 전역 XML 네임 스페이스를 정의 하는 경우 (예: `Imports <xmlns="http://SomeNameSpace>"`) 해당 네임 스페이스는 기본 XML 네임 스페이스로 간주 됩니다. 기본 XML 네임 스페이스는 네임 스페이스를 명시적으로 지정 하지 않는 모든 XML 요소 리터럴 또는 XML 특성 축 속성에 사용 됩니다. 기본 네임 스페이스는 지정 된 네임 스페이스가 빈 네임 스페이스 (즉, `xmlns=""`) 인 경우에도 사용 됩니다. 기본 XML 네임 스페이스는 xml 리터럴의 XML 특성이 나 네임 스페이스를 포함 하지 않는 XML 특성 축 속성에는 적용 되지 않습니다.

*로컬 xml 네임 스페이스*라고 하는 xml 리터럴에 정의 된 xml 네임 스페이스는 `Imports` 문에서 전역으로 정의 된 xml 네임 스페이스 보다 우선적으로 적용 됩니다. @No__t_0 문으로 정의 된 XML 네임 스페이스는 Visual Basic 프로젝트에 대해 가져온 XML 네임 스페이스 보다 우선적으로 적용 됩니다. Xml 리터럴이 XML 네임 스페이스를 정의 하는 경우 해당 로컬 네임 스페이스는 포함 식에 적용 되지 않습니다.

전역 XML 네임 스페이스는 .NET Framework 네임 스페이스와 동일한 범위 지정 및 정의 규칙을 따릅니다. 따라서 `Imports` 문을 포함 하 여 .NET Framework 네임 스페이스를 가져올 수 있는 위치에 전역 XML 네임 스페이스를 정의할 수 있습니다. 여기에는 코드 파일과 프로젝트 수준 가져온 네임 스페이스가 모두 포함 됩니다. 프로젝트 수준에서 가져온 네임 스페이스에 대 한 자세한 내용은 [참조 페이지, 프로젝트 디자이너 (Visual Basic)](/visualstudio/ide/reference/references-page-project-designer-visual-basic)를 참조 하세요.

각 소스 파일에는 개수에 관계 없이 `Imports` 문이 모두 포함 될 수 있습니다. 이는 `Option Strict` 문과 같은 옵션 선언을 따라야 하며 `Module` 또는 `Class` 문과 같은 프로그래밍 요소 선언 앞에와 야 합니다.

## <a name="example"></a>예제

다음 예에서는 `ns` 접두사를 사용 하 여 식별 되는 기본 XML 네임 스페이스와 XML 네임 스페이스를 가져옵니다. 그런 다음 두 네임 스페이스를 모두 사용 하는 XML 리터럴을 만듭니다.

[!code-vb[VbXMLSamples#45](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/Module1.vb#45)]

이 코드의 텍스트는 다음과 같습니다.

```xml
<ns:outer xmlns="http://DefaultNamespace"
          xmlns:ns="http://NewNamespace">
  <ns:innerElement></ns:innerElement>
  <siblingElement></siblingElement>
  <innerElement />
</ns:outer>
```

## <a name="example"></a>예제

다음 예에서는 `ns` XML 네임 스페이스 접두사를 가져옵니다. 그런 다음 네임 스페이스 접두사를 사용 하 고 요소의 최종 형식을 표시 하는 XML 리터럴을 만듭니다.

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

컴파일러는 XML 네임 스페이스 접두사를 전역 접두사에서 로컬 접두사 정의로 변환 했습니다.

## <a name="example"></a>예제

다음 예에서는 `ns` XML 네임 스페이스 접두사를 가져옵니다. 네임스페이스의 접두사를 사용하여 XML 리터럴을 만들고 정규화된 이름 `ns:name`을 가진 첫 번째 자식 노드에 액세스합니다.

[!code-vb[VbXMLSamples#19](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples8.vb#19)]

이 코드의 텍스트는 다음과 같습니다.

`Patrick Hines`

## <a name="see-also"></a>참조

- [XML 요소 리터럴](../../../visual-basic/language-reference/xml-literals/xml-element-literal.md)
- [XML 축 속성](../../../visual-basic/language-reference/xml-axis/index.md)
- [선언된 XML 요소 및 특성의 이름](../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md)
- [GetXmlNamespace 연산자](../../../visual-basic/language-reference/operators/getxmlnamespace-operator.md)
