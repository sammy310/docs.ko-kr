---
title: Declare 문 (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.Declare
- vb.Lib
- vb.Any
helpviewer_keywords:
- Lib keyword [Visual Basic]
- declaring procedures [Visual Basic], Declare statement
- functions [Visual Basic], function procedures
- declarations [Visual Basic], procedures
- procedures [Visual Basic], declaration
- procedures [Visual Basic], external
- Alias keyword [Visual Basic]
- external references [Visual Basic], Visual Basic
- DLLs, declaring procedures
- Declare statement [Visual Basic]
- declarations [Visual Basic], external
- Visual Basic code, Function procedures
- As keyword [Visual Basic], in Declare statement
- resources [Visual Basic], declaring
- Public keyword [Visual Basic], Declare statement
- platform invoke, Visual Basic external references
- Sub procedures [Visual Basic], declarations
- APIs, declaring API functions
- Visual Basic code, Sub procedures
- Function procedures [Visual Basic], declaring
ms.assetid: d3f21fb0-b804-4c99-97ed-583b23894cf1
ms.openlocfilehash: 6ff20af1ef439e27cffaf306c7917dbc98a419ce
ms.sourcegitcommit: d6e27023aeaffc4b5a3cb4b88685018d6284ada4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/09/2019
ms.locfileid: "67662916"
---
# <a name="declare-statement"></a>Declare 문

외부 파일에 구현 된 프로시저에 대 한 참조를 선언 합니다.

## <a name="syntax"></a>구문

```
[ <attributelist> ] [ accessmodifier ] [ Shadows ] [ Overloads ] _
Declare [ charsetmodifier ] [ Sub ] name Lib "libname" _
[ Alias "aliasname" ] [ ([ parameterlist ]) ]
' -or-
[ <attributelist> ] [ accessmodifier ] [ Shadows ] [ Overloads ] _
Declare [ charsetmodifier ] [ Function ] name Lib "libname" _
[ Alias "aliasname" ] [ ([ parameterlist ]) ] [ As returntype ]
```

## <a name="parts"></a>요소

|용어|정의|
|---|---|
|`attributelist`|선택 사항입니다. 참조 [특성 목록](../../../visual-basic/language-reference/statements/attribute-list.md)합니다.|
|`accessmodifier`|선택 사항입니다. 다음 중 하나일 수 있습니다.<br /><br /> -   [Public](../../../visual-basic/language-reference/modifiers/public.md)<br />-   [보호](../../../visual-basic/language-reference/modifiers/protected.md)<br />-   [friend](../../../visual-basic/language-reference/modifiers/friend.md)<br />-   [개인](../../../visual-basic/language-reference/modifiers/private.md)<br />- [Protected Friend](../../language-reference/modifiers/protected-friend.md)<br />- [Private Protected](../../language-reference/modifiers/private-protected.md)<br /><br /> [Access levels in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)을 참조하세요.|
|`Shadows`|선택 사항입니다. 참조 [그림자](../../../visual-basic/language-reference/modifiers/shadows.md)합니다.|
|`charsetmodifier`|선택 사항입니다. 문자 집합과 파일 지정 정보를 검색 합니다. 다음 중 하나일 수 있습니다.<br /><br /> -   [Ansi](../../../visual-basic/language-reference/modifiers/ansi.md) (기본값)<br />-   [Unicode](../../../visual-basic/language-reference/modifiers/unicode.md)<br />-   [Auto](../../../visual-basic/language-reference/modifiers/auto.md)|
|`Sub`|선택 사항 이지만 하나 `Sub` 또는 `Function` 나타나야 합니다. 외부 프로시저가 값을 반환 하지 않음을 나타냅니다.|
|`Function`|선택 사항 이지만 하나 `Sub` 또는 `Function` 나타나야 합니다. 외부 프로시저가 값을 반환 함을 나타냅니다.|
|`name`|필수 요소. 이 외부 참조의 이름입니다. 자세한 내용은 [선언 요소 이름](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md)합니다.|
|`Lib`|필수 요소. 소개는 `Lib` 절 외부 프로시저를 포함 하는 외부 파일 (DLL 또는 코드 리소스)을 식별 합니다.|
|`libname`|필수 요소. 선언 된 프로시저를 포함 하는 파일의 이름입니다.|
|`Alias`|선택 사항입니다. 에 지정 된 이름으로 선언 되는 프로시저 파일 내에서 식별할 수 없음을 나타냅니다 `name`합니다. 해당 id를 지정할 `aliasname`합니다.|
|`aliasname`|사용 하는 경우 필요 합니다 `Alias` 키워드입니다. 두 가지 방법 중 하나에서 프로시저를 식별 하는 문자열:<br /><br /> 따옴표 안에 해당 파일 내에서 프로시저 진입점 (`""`)<br /><br /> 또는<br /><br /> 숫자 기호 (`#`) 뒤에 해당 파일 내에서 프로시저의 진입점의 서 수를 지정 하는 정수|
|`parameterlist`|프로시저 매개 변수를 사용 하는 경우 필요 합니다. 참조 [매개 변수 목록](../../../visual-basic/language-reference/statements/parameter-list.md)합니다.|
|`returntype`|필요한 경우 `Function` 지정 하 고 `Option Strict` 는 `On`합니다. 프로시저에서 반환 된 값의 데이터 형식입니다.|

## <a name="remarks"></a>설명

경우에 따라 프로젝트 외부 (예: DLL 또는 코드 리소스) 파일에 정의 된 프로시저를 호출 해야 합니다. 이렇게 하면 Visual Basic 컴파일러 액세스 절차를 올바르게 호출 하는 데 필요한 정보를 프로시저 위치한, 등 식별 방법, 호출 시퀀스 및 반환 형식으로 사용 하는 문자열 문자 집합 없습니다. `Declare` 문 외부 프로시저에 대 한 참조를 만들고이 필요한 정보를 제공 합니다.

`Declare`는 모듈 수준에서만 사용할 수 있습니다. 즉, 합니다 *선언 컨텍스트* 외부 참조를 클래스, 구조체 또는 모듈 이어야 하며 원본 파일, 네임 스페이스, 인터페이스, 프로시저 또는 블록 수 없습니다. 자세한 내용은 [선언 컨텍스트 및 기본 액세스 수준](../../../visual-basic/language-reference/statements/declaration-contexts-and-default-access-levels.md)을 참조하세요.

외부 참조는 기본적으로 [공용](../../../visual-basic/language-reference/modifiers/public.md) 액세스 합니다. 액세스 한정자를 사용 하 여 해당 액세스 수준을 조정할 수 있습니다.

## <a name="rules"></a>규칙

- **특성입니다.** 외부 참조 특성을 적용할 수 있습니다. 적용 되는 특성은 외부 파일을 프로젝트에만 효과가 있습니다.

- **한정자입니다.** 외부 프로시저는 암시적으로 [공유](../../../visual-basic/language-reference/modifiers/shared.md)합니다. 사용할 수 없습니다는 `Shared` 공유 상태를 변경할 수 없습니다 외부 참조를 선언 하는 경우에 키워드입니다.

  외부 프로시저를 재정의에 참여 하 고 인터페이스 멤버를 구현 하 하거나 이벤트를 처리할 수 없습니다. 그에 따라 사용할 수 없습니다는 `Overrides`, `Overridable`, `NotOverridable`, `MustOverride`를 `Implements`, 또는 `Handles` 키워드는 `Declare` 문.

- **외부 프로시저 이름입니다.** 동일한 이름을이 외부 참조를 지정할 필요가 없습니다 (에서 `name`) 외부 파일 내에서 프로시저의 진입점 이름으로 (`aliasname`). 사용할 수는 `Alias` 절 진입점 이름을 지정 합니다. 이 외부 프로시저가 같은 범위에 대 한 Visual Basic의 예약 된 한정자 또는 변수, 프로시저 또는 다른 프로그래밍 요소 이름이 같은 경우에 유용할 수 있습니다.

  > [!NOTE]
  > 대부분의 Dll에 진입점 이름은 대/소문자를 구분 하지 않습니다.

- **외부 프로시저 번호입니다.** 사용할 수 있습니다는 `Alias` 절을 외부 파일의 내보내기 테이블 내에서 진입점의 서 수를 지정 합니다. 먼저이를 위해서는 `aliasname` 숫자 기호를 사용 하 여 (`#`). 이 기능은 Visual basic의 경우 외부 프로시저 이름이 있는 모든 문자를 허용 되지 않는 경우 또는 외부 파일 이름 없이 프로시저를 내보내는 경우에 유용할 수 있습니다.

## <a name="data-type-rules"></a>데이터 형식 규칙

- **매개 변수 데이터 형식입니다.** 하는 경우 `Option Strict` 됩니다 `On`에서 각 매개 변수의 데이터 형식을 지정 해야 `parameterlist`합니다. 이 열거형, 구조체, 클래스 또는 인터페이스의 이름 또는 데이터 형식일 수 있습니다. 내 `parameterlist`를 사용 하면는 `As` 각 매개 변수에 전달할 인수의 데이터 형식을 지정 하는 절.

  > [!NOTE]
  > .NET Framework에 대 한 외부 프로시저가 쓰지, 하는 경우 주의 해야 합니다는 데이터 형식이 일치 하는 합니다. 예를 들어, Visual Basic 6.0 프로시저에 대 한 외부 참조를 선언 하는 경우는 `Integer` 매개 변수 (Visual Basic 6.0에서 16 비트)으로 해당 인수를 식별 해야 합니다 `Short` 에 `Declare` 문 이므로 16- Visual Basic의 비트 정수 형식입니다. 마찬가지로 `Long` Visual Basic 6.0에는 다른 데이터 너비 및 `Date` 다르게 구현 됩니다.

- **데이터 형식을 반환 합니다.** 외부 프로시저가 `Function` 하 고 `Option Strict` 는 `On`, 호출 코드에 반환 되는 값의 데이터 형식을 지정 해야 합니다. 이 열거형, 구조체, 클래스 또는 인터페이스의 이름 또는 데이터 형식일 수 있습니다.

  > [!NOTE]
  > Visual Basic 컴파일러는 데이터 형식에는 외부 프로시저와 호환 되는지 확인 하지 않습니다. 불일치가 있는 경우 공용 언어 런타임에서 생성 된 <xref:System.Runtime.InteropServices.MarshalDirectiveException> 런타임 시 예외입니다.

- **기본 데이터 형식입니다.** 경우 `Option Strict` 는 `Off` 매개 변수의 데이터 형식을 지정 하지 않으면 및 `parameterlist`, Visual Basic 컴파일러에서 해당 인수를 변환 합니다 [Object Data Type](../../../visual-basic/language-reference/data-types/object-data-type.md). 마찬가지로, 지정 하지 않는 경우 `returntype`, 컴파일러는 되도록 반환 데이터 형식이 `Object`합니다.

  > [!NOTE]
  > 다른 플랫폼에서 작성 된 외부 프로시저를 처리 하는 때문에 데이터 형식에 대 한 가정을 또는 기본값을 지정할 수 있도록 위험 합니다. 것이 있는 경우 모든 매개 변수 및 반환 값의 데이터 형식을 지정 하려면 훨씬 안전 합니다. 또한 코드의 가독성이 향상 됩니다.

## <a name="behavior"></a>동작

- **범위입니다.** 외부 참조는 해당 클래스, 구조체 또는 모듈 전체 범위의 합니다.

- **수명입니다.** 외부 참조에는 클래스, 구조체 또는 모듈 선언 되는 동일한 수명 주기

- **외부 프로시저를 호출 합니다.** 외부 프로시저를 호출 하면 동일한 방식으로 호출을 `Function` 하거나 `Sub` 프로시저-값을 반환 하는 경우에 식에서 사용 하거나에서 지정 하 여를 [Call 문을](../../../visual-basic/language-reference/statements/call-statement.md) 값을 반환 하지 않는 경우.

  에 지정 된 대로 정확 하 게 외부 프로시저에 인수를 전달할 `parameterlist` 에 `Declare` 문입니다. 고려 하지 않은 계정 매개 변수를 외부 파일의 원래 선언 된 방법입니다. 마찬가지로, 반환 값의 경우 사용 하 여 지정 된 대로 정확 하 게 `returntype` 에 `Declare` 문입니다.

- **문자 집합입니다.** 지정할 수 있습니다 `charsetmodifier` 문자열 외부 프로시저를 호출할 때 Visual Basic 해야 하는 방법을 마샬링합니다. 합니다 `Ansi` 한정자 지시 Visual Basic에서 모든 문자열을 ANSI 값으로 마샬링 및 `Unicode` 한정자를 모든 문자열을 유니코드 값으로 마샬링하 지시 합니다. `Auto` 한정자는 Visual Basic.NET 프레임 워크에 따라 문자열 마샬링을 외부 참조를 기반으로 규칙 보냅니다 `name`, 또는 `aliasname` 지정 합니다. 기본값은 `Ansi`입니다.

  `charsetmodifier` 또한 Visual Basic 외부 파일 내에서 외부 프로시저를 조회 하는 방법을 지정 합니다. `Ansi` 및 `Unicode` 모두 직접 Visual Basic로 검색 하는 동안 이름을 수정 하지 않고 조회 합니다. `Auto` Visual Basic 런타임 플랫폼의 기본 문자 집합을 확인 하 고 다음과 같이 외부 프로시저 이름을 수정 하도록 지시 합니다.

  - Windows 95, Windows 98 또는 Windows Millennium Edition 등의 ANSI 플랫폼에서 먼저 이름 수정 하지 않을 외부 프로시저를 찾습니다. 실패할 경우 외부 프로시저 이름의 끝에 "A"를 추가 하 고 다시 조회 합니다.

  - Windows NT, Windows 2000 또는 Windows XP와 같은 유니코드 플랫폼에서 먼저 이름 수정 하지 않을 외부 프로시저를 찾습니다. 실패 하는 경우 추가 "W" 끝에는 외부 프로시저의 이름을 지정 하 고 다시 조회 합니다.

- **Mechanism.** .NET Framework를 사용 하는 Visual Basic *플랫폼 호출* (PInvoke)를 해결 하 고 외부 프로시저에 액세스 하는 메커니즘입니다. 합니다 `Declare` 문 및 <xref:System.Runtime.InteropServices.DllImportAttribute> 클래스에는 모두 자동으로이 메커니즘을 사용 하며 모든 지식이 PInvoke 필요가 없습니다. 자세한 내용은 [연습: Windows Api 호출](../../../visual-basic/programming-guide/com-interop/walkthrough-calling-windows-apis.md)합니다.

> [!IMPORTANT]
> 외부 프로시저를 CLR (공용 언어 런타임) 외부를 실행 하는 경우 *비관리 코드*합니다. 이러한 프로시저를 예를 들어 Windows API 함수 또는 COM 메서드를 호출 하는 경우 보안 위험에 응용 프로그램을 노출할 수 있습니다. 자세한 내용은 [보안 코딩 지침 비관리 코드에 대 한](../../../framework/security/secure-coding-guidelines-for-unmanaged-code.md)합니다.

## <a name="example"></a>예제

다음 예제에서는 선언에 대 한 외부 참조는 `Function` 현재 사용자 이름을 반환 하는 프로시저입니다. 그런 다음 외부 프로시저를 호출 `GetUserNameA` 의 일부로 `getUser` 프로시저입니다.

[!code-vb[VbVbalrStatements#15](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#15)]

## <a name="example"></a>예제

<xref:System.Runtime.InteropServices.DllImportAttribute> 비관리 코드에서 함수를 사용 하는 대체 방법을 제공 합니다. 다음 예제에서는 가져온된 함수를 사용 하지 않고 선언 된 `Declare` 문입니다.

[!code-vb[VbVbalrStatements#16](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#16)]

[!code-vb[VbVbalrStatements#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#1)]

## <a name="see-also"></a>참고자료

- <xref:Microsoft.VisualBasic.ErrObject.LastDllError%2A>
- [Imports 문(.NET 네임스페이스 및 형식)](../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md)
- [AddressOf 연산자](../../../visual-basic/language-reference/operators/addressof-operator.md)
- [Function 문](../../../visual-basic/language-reference/statements/function-statement.md)
- [Sub 문](../../../visual-basic/language-reference/statements/sub-statement.md)
- [매개 변수 목록](../../../visual-basic/language-reference/statements/parameter-list.md)
- [Call 문](../../../visual-basic/language-reference/statements/call-statement.md)
- [연습: Windows API 호출](../../../visual-basic/programming-guide/com-interop/walkthrough-calling-windows-apis.md)
