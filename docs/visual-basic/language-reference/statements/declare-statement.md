---
title: Declare 문
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
ms.openlocfilehash: 9895709076634ce156ba9d1009f79ba7ddd2ba56
ms.sourcegitcommit: 62285ec11fa8e8424bab00511a90760c60e63c95
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/20/2020
ms.locfileid: "81646378"
---
# <a name="declare-statement"></a>Declare 문

외부 파일에 구현된 프로시저에 대한 참조를 선언합니다.

## <a name="syntax"></a>구문

```vb
[ <attributelist> ] [ accessmodifier ] [ Shadows ] [ Overloads ] _
Declare [ charsetmodifier ] [ Sub ] name Lib "libname" _
[ Alias "aliasname" ] [ ([ parameterlist ]) ]
' -or-
[ <attributelist> ] [ accessmodifier ] [ Shadows ] [ Overloads ] _
Declare [ charsetmodifier ] [ Function ] name Lib "libname" _
[ Alias "aliasname" ] [ ([ parameterlist ]) ] [ As returntype ]
```

## <a name="parts"></a>부분

|용어|정의|
|---|---|
|`attributelist`|(선택 사항) [속성 목록을](../../../visual-basic/language-reference/statements/attribute-list.md)참조하십시오.|
|`accessmodifier`|(선택 사항) 다음 중 하나일 수 있습니다.<br /><br /> -   [공용](../../../visual-basic/language-reference/modifiers/public.md)<br />-   [보호](../../../visual-basic/language-reference/modifiers/protected.md)<br />-   [친구](../../../visual-basic/language-reference/modifiers/friend.md)<br />-   [개인](../../../visual-basic/language-reference/modifiers/private.md)<br />- [보호된 친구](../../language-reference/modifiers/protected-friend.md)<br />- [개인 보호](../../language-reference/modifiers/private-protected.md)<br /><br /> [Access levels in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)을 참조하세요.|
|`Shadows`|(선택 사항) [그림자 를](../../../visual-basic/language-reference/modifiers/shadows.md)참조하십시오.|
|`charsetmodifier`|(선택 사항) 문자 집합 및 파일 검색 정보를 지정합니다. 다음 중 하나일 수 있습니다.<br /><br /> -   [안시(기본값)](../../../visual-basic/language-reference/modifiers/ansi.md)<br />-   [유니코드](../../../visual-basic/language-reference/modifiers/unicode.md)<br />-   [자동](../../../visual-basic/language-reference/modifiers/auto.md)|
|`Sub`|선택 사항이지만 `Sub` `Function` 나타나야 합니다. 외부 프로시저가 값을 반환하지 않음을 나타냅니다.|
|`Function`|선택 사항이지만 `Sub` `Function` 나타나야 합니다. 외부 프로시저가 값을 반환했음을 나타냅니다.|
|`name`|필수 사항입니다. 이 외부 참조의 이름입니다. 자세한 내용은 [선언된 요소 이름을](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md)참조하십시오.|
|`Lib`|필수 사항입니다. 외부 프로시저가 포함된 외부 파일(DLL 또는 코드 리소스)을 식별하는 `Lib` 절을 소개합니다.|
|`libname`|필수 사항입니다. 선언된 프로시저가 포함된 파일의 이름입니다.|
|`Alias`|(선택 사항) 선언되는 프로시저가 에 지정된 이름으로 파일 내에서 `name`식별될 수 없음을 나타냅니다. 에서 ID를 `aliasname`지정합니다.|
|`aliasname`|키워드를 `Alias` 사용하는 경우 필요합니다. 다음 두 가지 방법 중 하나로 프로시저를 식별하는 문자열:<br /><br /> 파일 내의 프로시저의 진입점 이름(따옴표(`""`) 내에서<br /><br /> 또는<br /><br /> 숫자 부호`#`() 다음에 해당 파일 내에서 프로시저의 진입점의 서수 수를 지정하는 정수|
|`parameterlist`|프로시저가 매개 변수를 취하는 경우 필요합니다. [매개 변수 목록](../../../visual-basic/language-reference/statements/parameter-list.md)을 참조하십시오.|
|`returntype`|지정되어 `Function` 있고 `Option Strict` 있는 `On`경우 필수입니다. 프로시저에서 반환되는 값의 데이터 형식입니다.|

## <a name="remarks"></a>설명

경우에 따라 프로젝트 외부의 파일(예: DLL 또는 코드 리소스)에 정의된 프로시저를 호출해야 합니다. 이렇게 하면 Visual Basic 컴파일러는 프로시저가 있는 위치, 식별 되는 방법, 호출 시퀀스 및 반환 형식 및 사용 하는 문자열 문자 집합 등 프로시저를 올바르게 호출 하는 데 필요한 정보에 액세스할 수 없습니다. 문은 `Declare` 외부 프로시저에 대한 참조를 만들고 이 필요한 정보를 제공합니다.

`Declare`는 모듈 수준에서만 사용할 수 있습니다. 즉, 외부 참조에 대한 *선언 컨텍스트는* 클래스, 구조 또는 모듈이어야 하며 소스 파일, 네임스페이스, 인터페이스, 프로시저 또는 블록일 수 없습니다. 자세한 내용은 [선언 컨텍스트 및 기본 액세스 수준](../../../visual-basic/language-reference/statements/declaration-contexts-and-default-access-levels.md)을 참조하세요.

외부 참조는 기본적으로 [공용](../../../visual-basic/language-reference/modifiers/public.md) 액세스로 설정됩니다. 액세스 수정자를 통해 액세스 수준을 조정할 수 있습니다.

## <a name="rules"></a>규칙

- **특성.** 외부 참조에 특성을 적용할 수 있습니다. 적용하는 모든 특성은 외부 파일이 아닌 프로젝트에만 영향을 미칩니다.

- **한정자.** 외부 프로시저는 암시적으로 [공유됩니다.](../../../visual-basic/language-reference/modifiers/shared.md) 외부 참조를 `Shared` 선언할 때는 키워드를 사용할 수 없으며 공유 상태를 변경할 수 없습니다.

  외부 프로시저는 재정의에 참여하거나 인터페이스 멤버를 구현하거나 이벤트를 처리할 수 없습니다. 따라서 `Declare` 명령문에서 `Overrides`" `Overridable` `NotOverridable` `MustOverride` `Implements`의 키워드를 `Handles` 사용할 수 없습니다.

- **외부 프로시저 이름입니다.** 이 외부 참조에 외부 파일()에서 `name``aliasname`프로시저의 진입점 이름과 동일한 이름(in)을 지정할 필요는 없습니다. 절을 `Alias` 사용하여 진입점 이름을 지정할 수 있습니다. 이 기능은 외부 프로시저가 Visual Basic 예약 수정자 또는 변수, 프로시저 또는 동일한 범위의 다른 프로그래밍 요소와 이름이 같은 경우에 유용할 수 있습니다.

  > [!NOTE]
  > 대부분의 DLL의 진입점 이름은 대/소문자를 구분합니다.

- **외부 프로시저 번호입니다.** 또는 절을 `Alias` 사용하여 외부 파일의 내보내기 테이블 내에서 진입점의 서수 수를 지정할 수 있습니다. 이렇게 하려면 숫자 `aliasname` 기호()로`#`시작합니다. 이 기능은 Visual Basic에서 외부 프로시저 이름의 문자를 허용하지 않거나 외부 파일이 이름 없이 프로시저를 내보내는 경우에 유용할 수 있습니다.

## <a name="data-type-rules"></a>데이터 형식 규칙

- **매개 변수 데이터 유형입니다.** is는 `Option Strict` 에서 각 매개 변수의 데이터 형식을 지정해야 `parameterlist` `On` 모든 데이터 형식 또는 열거형, 구조체, 클래스 또는 인터페이스의 이름일 수 있습니다. 에서 `parameterlist`절을 `As` 사용하여 각 매개 변수에 전달할 인수의 데이터 형식을 지정합니다.

  > [!NOTE]
  > .NET Framework에 대해 외부 프로시저가 작성되지 않은 경우 데이터 형식이 해당하는지 주의해야 합니다. 예를 들어 `Integer` 매개 변수(Visual Basic 6.0의 16비트)를 사용하여 Visual Basic 6.0 프로시저에 대한 `Short` 외부 `Declare` 참조를 선언하는 경우 Visual Basic의 16비트 정수 유형이기 때문에 문에서와 같이 해당 인수를 식별해야 합니다. 마찬가지로 `Long` Visual Basic 6.0에서 데이터 너비가 `Date` 다르고 다르게 구현됩니다.

- **데이터 형식을 반환합니다.** 외부 프로시저가 `Function` `Option Strict` a이고 `On`있는 경우 호출 코드에 반환되는 값의 데이터 형식을 지정해야 합니다. 모든 데이터 형식 또는 열거형, 구조체, 클래스 또는 인터페이스의 이름일 수 있습니다.

  > [!NOTE]
  > Visual Basic 컴파일러는 데이터 형식이 외부 프로시저의 데이터 형식과 호환되는지 확인하지 않습니다. 불일치가 있는 경우 공통 언어 런타임은 <xref:System.Runtime.InteropServices.MarshalDirectiveException> 런타임에 예외를 생성합니다.

- **기본 데이터 유형입니다.** 에서 `Option Strict` `Off` 매개 변수의 `parameterlist`데이터 형식을 지정하지 않은 경우 Visual Basic 컴파일러는 해당 인수를 [개체 데이터 유형으로](../../../visual-basic/language-reference/data-types/object-data-type.md)변환합니다. 마찬가지로 지정하지 `returntype`않으면 컴파일러는 반환 데이터 형식을 으로 `Object`합니다.

  > [!NOTE]
  > 다른 플랫폼에서 작성되었을 수 있는 외부 프로시저를 처리하기 때문에 데이터 형식에 대해 가정하거나 기본값으로 허용하는 것은 위험합니다. 모든 매개 변수의 데이터 형식과 반환 값(있는 경우)을 지정하는 것이 훨씬 안전합니다. 이렇게 하면 코드의 가독성이 향상됩니다.

## <a name="behavior"></a>동작

- **범위.** 외부 참조는 클래스, 구조 또는 모듈 전체에서 범위에 있습니다.

- **수명.** 외부 참조는 선언된 클래스, 구조또는 모듈과 수명이 동일합니다.

- **외부 프로시저를 호출합니다.** 값을 반환하는 경우 식에서 사용하거나 `Sub` 값을 반환하지 않는 경우 호출 [문에](../../../visual-basic/language-reference/statements/call-statement.md) 지정하여 외부 프로시저를 호출하는 `Function` 것과 동일한 방식으로 외부 프로시저를 호출합니다.

  문에서 지정한 대로 외부 `parameterlist` 프로시저에 `Declare` 인수를 전달합니다. 매개 변수가 원래 외부 파일에서 선언된 방법을 고려하지 마십시오. 마찬가지로 반환 값이 있는 경우 `returntype` `Declare` 명령문에 지정된 대로 정확하게 사용합니다.

- **문자 집합입니다.** Visual Basic이 `charsetmodifier` 외부 프로시저를 호출할 때 문자열을 마샬링하는 방법을 지정할 수 있습니다. `Ansi` 수정자는 Visual Basic을 지시하여 모든 문자열을 ANSI 값으로 `Unicode` 마샬링하고, 수정자는 모든 문자열을 유니코드 값으로 마샬링하도록 지시합니다. `Auto` 수정자는 외부 참조를 `name`기반으로 하거나 `aliasname` 지정된 경우 .NET Framework 규칙에 따라 Visual Basic을 마샬링하도록 지시합니다. 기본값은 `Ansi`입니다.

  `charsetmodifier`또한 Visual Basic이 외부 파일 내에서 외부 프로시저를 조회하는 방법을 지정합니다. `Ansi`그리고 `Unicode` 둘 다 검색 하는 동안 이름을 수정 하지 않고 그것을 조회 하는 Visual Basic 을 직접. `Auto`Visual Basic을 지시하여 런타임 플랫폼의 기본 문자 집합을 결정하고 다음과 같이 외부 프로시저 이름을 수정할 수 있습니다.

  - Windows 95, Windows 98 또는 Windows 밀레니엄 에디션과 같은 ANSI 플랫폼에서 먼저 이름 수정 없이 외부 프로시저를 찾습니다. 실패하면 외부 프로시저 이름 끝에 "A"를 더한 다음 다시 찾습니다.

  - Windows NT, Windows 2000 또는 Windows XP와 같은 유니코드 플랫폼에서 먼저 이름 수정 없이 외부 프로시저를 찾습니다. 실패하면 외부 프로시저 이름 끝에 "W"를 더한 다음 다시 찾습니다.

- **메커니즘.** Visual Basic은 .NET Framework 플랫폼 호출(PInvoke) 메커니즘을 사용하여 외부 프로시저를 해결하고 액세스합니다. *platform invoke* 명령문과 `Declare` <xref:System.Runtime.InteropServices.DllImportAttribute> 클래스 는 모두 이 메커니즘을 자동으로 사용하며 PInvoke에 대한 지식이 필요하지 않습니다. 자세한 내용은 [연습: Windows Api 호출](../../../visual-basic/programming-guide/com-interop/walkthrough-calling-windows-apis.md)합니다.

> [!IMPORTANT]
> 외부 프로시저가 공통 언어 런타임(CLR) 외부에서 실행되는 경우 *관리되지 않는 코드입니다.* 이러한 프로시저를 호출할 때(예: Windows API 함수 또는 COM 메서드) 응용 프로그램을 보안 위험에 노출시킬 수 있습니다. 자세한 내용은 [관리되지 않는 코드에 대한 보안 코딩 지침을](https://docs.microsoft.com/previous-versions/dotnet/framework/security/secure-coding-guidelines-for-unmanaged-code)참조하십시오.

## <a name="example"></a>예제

다음 예제는 현재 사용자 이름을 `Function` 반환 하는 프로시저에 대 한 외부 참조를 선언 합니다. 그런 다음 프로시저의 일부로 외부 프로시저를 `GetUserNameA` 호출합니다. `getUser`

[!code-vb[VbVbalrStatements#15](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#15)]

## <a name="example"></a>예제

는 <xref:System.Runtime.InteropServices.DllImportAttribute> 관리되지 않는 코드에서 함수를 사용하는 다른 방법을 제공합니다. 다음 예제는 문을 사용 하지 않고 `Declare` 가져온된 함수를 선언 합니다.

[!code-vb[VbVbalrStatements#16](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#16)]

[!code-vb[VbVbalrStatements#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#1)]

## <a name="see-also"></a>참고 항목

- <xref:Microsoft.VisualBasic.ErrObject.LastDllError%2A>
- [Imports 문(.NET 네임스페이스 및 형식)](../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md)
- [주소운영자](../../../visual-basic/language-reference/operators/addressof-operator.md)
- [Function 문](../../../visual-basic/language-reference/statements/function-statement.md)
- [Sub 문](../../../visual-basic/language-reference/statements/sub-statement.md)
- [매개 변수 목록](../../../visual-basic/language-reference/statements/parameter-list.md)
- [Call 문](../../../visual-basic/language-reference/statements/call-statement.md)
- [연습: Windows API 호출](../../../visual-basic/programming-guide/com-interop/walkthrough-calling-windows-apis.md)
