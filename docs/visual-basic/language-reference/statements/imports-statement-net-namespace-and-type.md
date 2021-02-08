---
description: '자세한 정보: Imports 문 (.NET 네임 스페이스 및 형식)'
title: Imports 문-.NET 네임 스페이스 및 형식
ms.date: 07/20/2015
f1_keywords:
- vb.Imports
- imports
helpviewer_keywords:
- declared element names [Visual Basic], qualification
- imports [Visual Basic]
- Imports statement [Visual Basic]
- aliases [Visual Basic], Imports statement
- container elements [Visual Basic]
- namespaces [Visual Basic], importing
- Imports statement [Visual Basic], syntax
- import aliases [Visual Basic]
- aliases [Visual Basic], import
- declared elements [Visual Basic], container elements
ms.assetid: 7062f8aa-d890-4232-9eed-92836e13fb6e
ms.openlocfilehash: 28b7608e250fdba9c39f0209154d5a3d8f725eea
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99768976"
---
# <a name="imports-statement-net-namespace-and-type"></a>Imports 문(.NET 네임스페이스 및 형식)

네임 스페이스 한정자 없이 형식 이름을 참조할 수 있습니다.

## <a name="syntax"></a>Syntax

```vb
Imports [ aliasname = ] namespace
' -or-
Imports [ aliasname = ] namespace.element
```

## <a name="parts"></a>부분

|용어|정의|
|---|---|
|`aliasname`|선택 사항입니다. 코드에서 전체 한정 문자열 대신 참조할 수 있는 *가져오기 별칭* 또는 이름입니다 `namespace` . [Declared Element Names](../../programming-guide/language-features/declared-elements/declared-element-names.md)을 참조하세요.|
|`namespace`|필수 사항입니다. 가져오는 네임 스페이스의 정규화 된 이름입니다. 는 임의의 수준에 중첩 된 네임 스페이스의 문자열일 수 있습니다.|
|`element`|선택 사항입니다. 네임 스페이스에 선언 된 프로그래밍 요소의 이름입니다. 모든 컨테이너 요소일 수 있습니다.|

## <a name="remarks"></a>설명

`Imports`문을 사용 하면 지정 된 네임 스페이스에 포함 된 형식을 직접 참조할 수 있습니다.

단일 네임 스페이스 이름 또는 중첩 된 네임 스페이스의 문자열을 제공할 수 있습니다. 다음 예제와 같이 중첩 된 각 네임 스페이스는 다음 상위 수준 네임 스페이스와 마침표 ()로 구분 됩니다 `.` .

```vb
Imports System.Collections.Generic
```

각 소스 파일에는 개수에 관계 없이 문을 포함할 수 있습니다 `Imports` . 이는 문과 같은 모든 옵션 선언을 따라야 하며, `Option Strict` 또는 문과 같은 프로그래밍 요소 선언 앞에와 야 합니다 `Module` `Class` .

는 `Imports` 파일 수준 에서만 사용할 수 있습니다. 즉, 가져오기에 대 한 선언 컨텍스트는 소스 파일 이어야 하며 네임 스페이스, 클래스, 구조체, 모듈, 인터페이스, 프로시저 또는 블록이 될 수 없습니다.

`Imports`문은 다른 프로젝트 및 어셈블리의 요소를 프로젝트에서 사용할 수 있도록 합니다. 가져오기는 참조 설정 대신 사용 됩니다. 프로젝트에 이미 사용할 수 있는 이름을 한정할 필요성이 제거 됩니다. 자세한 내용은 [선언 된 요소에](../../programming-guide/language-features/declared-elements/references-to-declared-elements.md)대 한 참조에서 "포함 하는 요소 가져오기"를 참조 하세요.

> [!NOTE]
> `Imports` [참조 페이지, 프로젝트 디자이너 (Visual Basic)](/visualstudio/ide/reference/references-page-project-designer-visual-basic)를 사용 하 여 암시적 문을 정의할 수 있습니다. 자세한 내용은 [방법: 가져온 네임 스페이스 추가 또는 제거 (Visual Basic)](/visualstudio/ide/how-to-add-or-remove-imported-namespaces-visual-basic)를 참조 하세요.

## <a name="import-aliases"></a>Import 별칭

*가져오기 별칭* 은 네임 스페이스 또는 형식에 대 한 별칭을 정의 합니다. 가져오기 별칭은 하나 이상의 네임 스페이스에 선언 된 것과 동일한 이름의 항목을 사용 해야 하는 경우에 유용 합니다. 자세한 내용 및 예제는 [선언 된 요소에](../../programming-guide/language-features/declared-elements/references-to-declared-elements.md)대 한 참조의 "요소 이름 한정"을 참조 하세요.

와 동일한 이름을 사용 하 여 모듈 수준에서 멤버를 선언 하면 안 됩니다 `aliasname` . 이 경우 Visual Basic 컴파일러는 `aliasname` 선언 된 멤버에만를 사용 하며 더 이상 가져오기 별칭으로 인식 하지 않습니다.

가져오기 별칭을 선언 하는 데 사용 되는 구문은 XML 네임 스페이스 접두사를 가져오는 데 사용 되는 구문과 유사 하지만 결과는 다릅니다. Xml 네임 스페이스 접두사는 xml 리터럴 또는 XML 축 속성 에서만 정규화 된 요소 또는 특성 이름에 대 한 접두사로 사용할 수 있는 반면, 코드에서는 가져오기 별칭을 식으로 사용할 수 있습니다.

### <a name="element-names"></a>요소 이름

를 제공 하는 경우 `element` 다른 요소를 포함할 수 있는 프로그래밍 요소인 *컨테이너 요소* 를 나타내야 합니다. 컨테이너 요소에는 클래스, 구조체, 모듈, 인터페이스 및 열거형이 포함 됩니다.

문에서 사용할 수 있는 요소의 범위는 `Imports` 지정 여부에 따라 달라 집니다 `element` . 만 지정 하는 경우 `namespace` 해당 네임 스페이스의 고유 하 게 명명 된 멤버와 해당 네임 스페이스 내에 있는 컨테이너 요소의 멤버를 한정자 없이 사용할 수 있습니다. 및를 둘 다 지정 하는 경우 `namespace` `element` 해당 요소의 멤버만 한정 없이 사용할 수 있습니다.

## <a name="example"></a>예제

다음 예제에서는 클래스를 사용 하 여 *C: \\* 디렉터리의 모든 폴더를 반환 합니다 <xref:System.IO.DirectoryInfo> .

코드에는 `Imports` 파일 맨 위에 문이 없습니다. 따라서, <xref:System.IO.DirectoryInfo> <xref:System.Text.StringBuilder> 및 <xref:Microsoft.VisualBasic.ControlChars.CrLf> 참조는 모두 네임 스페이스를 사용 하 여 정규화 됩니다.

[!code-vb[VbVbalrStatements#152](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class12.vb#152)]

## <a name="example"></a>예제

다음 예제에서는 `Imports` 참조 된 네임 스페이스에 대 한 문을 포함 합니다. 따라서 네임 스페이스를 사용 하 여 형식을 정규화 할 필요가 없습니다.

[!code-vb[VbVbalrStatements#153](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class12.vb#153)]

[!code-vb[VbVbalrStatements#154](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class12.vb#154)]
  
## <a name="example"></a>예제

다음 예제에는 `Imports` 참조 된 네임 스페이스에 대 한 별칭을 만드는 문이 포함 되어 있습니다. 형식은 별칭으로 한정 됩니다.

[!code-vb[VbVbalrStatements#155](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class12.vb#155)]

[!code-vb[VbVbalrStatements#156](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class12.vb#156)]

## <a name="example"></a>예제

다음 예에는 `Imports` 참조 된 형식에 대 한 별칭을 만드는 문이 포함 되어 있습니다. 별칭은 형식을 지정 하는 데 사용 됩니다.

[!code-vb[VbVbalrStatements#157](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class12.vb#157)]

[!code-vb[VbVbalrStatements#158](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class12.vb#158)]
  
## <a name="see-also"></a>참고 항목

- [Namespace 문](namespace-statement.md)
- [Visual Basic의 네임스페이스](../../programming-guide/program-structure/namespaces.md)
- [참조 및 Imports 문](../../programming-guide/program-structure/references-and-the-imports-statement.md)
- [Imports 문(XML 네임스페이스)](imports-statement-xml-namespace.md)
- [References to Declared Elements](../../programming-guide/language-features/declared-elements/references-to-declared-elements.md)
