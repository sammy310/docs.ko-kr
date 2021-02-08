---
description: '자세한 정보: Dim 문 (Visual Basic)'
title: Dim 문
ms.date: 05/12/2018
f1_keywords:
- vb.Dim
- Dim
helpviewer_keywords:
- Public keyword [Visual Basic], in Dim statement
- Dim statement [Visual Basic]
- fixed-length strings [Visual Basic], declaring
- variables [Visual Basic], declaring
- WithEvents keyword [Visual Basic], Dim statement
- dynamic arrays [Visual Basic], Dim statement
- variables [Visual Basic], initializing
- '{} braces'
- fields [Visual Basic], as member variables
- declarations [Visual Basic], dynamic arrays
- member variables [Visual Basic]
- default values [Visual Basic]
- data types [Visual Basic], assigning
- braces {}
- As keyword [Visual Basic], in Dim statement
- arrays [Visual Basic], declaring
- New keyword [Visual Basic], Dim statement
- To keyword [Visual Basic], in Dim statement
- storage [Visual Basic], allocating
- local variables [Visual Basic]
- declaration statements [Visual Basic]
- Dim statement [Visual Basic], syntax
- variables [Visual Basic], member and local
ms.assetid: fae3eca1-f0b2-4400-994b-7aa58a848448
ms.openlocfilehash: b950ae95af01be4e064ac9177300f144e0cc08b7
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99795198"
---
# <a name="dim-statement-visual-basic"></a>Dim 문 (Visual Basic)

하나 이상의 변수에 대 한 저장소 공간을 선언 하 고 할당 합니다.

## <a name="syntax"></a>Syntax

```vb
[ <attributelist> ] [ accessmodifier ] [[ Shared ] [ Shadows ] | [ Static ]] [ ReadOnly ]
Dim [ WithEvents ] variablelist
```

## <a name="parts"></a>부분

- `attributelist`

  선택 사항입니다. [특성 목록](attribute-list.md)을 참조 하십시오.

- `accessmodifier`

  선택 사항입니다. 다음 중 하나일 수 있습니다.

  - [공용](../modifiers/public.md)

  - [보호됨](../modifiers/protected.md)

  - [Friend](../modifiers/friend.md)

  - [개인](../modifiers/private.md)

  - [Protected Friend](../modifiers/protected-friend.md)

  - [비공개 보호](../modifiers/private-protected.md)

  [Access levels in Visual Basic](../../programming-guide/language-features/declared-elements/access-levels.md)을 참조하세요.

- `Shared`

  선택 사항입니다. [공유](../modifiers/shared.md)를 참조 하세요.

- `Shadows`

  선택 사항입니다. [그림자](../modifiers/shadows.md)를 참조 하세요.

- `Static`

  선택 사항입니다. [Static](../modifiers/static.md)을 참조 하세요.

- `ReadOnly`

  선택 사항입니다. [ReadOnly](../modifiers/readonly.md)를 참조 하세요.

- `WithEvents`

  선택 사항입니다. 이러한 개체 변수가 이벤트를 발생 시킬 수 있는 클래스의 인스턴스를 참조 하도록 지정 합니다. [WithEvents](../modifiers/withevents.md)를 참조 하세요.

- `variablelist`

  필수 사항입니다. 이 문에서 선언 되는 변수의 목록입니다.

  `variable [ , variable ... ]`

  각 `variable`에는 다음과 같은 구문과 요소가 있습니다.

  `variablename [ ( [ boundslist ] ) ] [ As [ New ] datatype [ With`{`[ .propertyname = propinitializer [ , ... ] ] } ] ] [ = initializer ]`

  |파트|설명|
  |---|---|
  |`variablename`|필수 사항입니다. 변수의 이름입니다. [Declared Element Names](../../programming-guide/language-features/declared-elements/declared-element-names.md)을 참조하세요.|
  |`boundslist`|선택 사항입니다. 배열 변수의 각 차원에 대 한 범위 목록입니다.|
  |`New`|선택 사항입니다. 문이 실행 될 때 클래스의 새 인스턴스를 만듭니다 `Dim` .|
  |`datatype`|선택 사항입니다. 변수의 데이터 형식입니다.|
  |`With`|선택 사항입니다. 개체 이니셜라이저 목록을 소개 합니다.|
  |`propertyname`|선택 사항입니다. 인스턴스를 만드는 클래스의 속성 이름입니다.|
  |`propinitializer`|= 이후에 필요 `propertyname` 합니다. 평가 되 고 속성 이름에 할당 되는 식입니다.|
  |`initializer`|`New`가 지정 되지 않은 경우 선택 사항입니다. 식이 생성 될 때 계산 되어 변수에 할당 되는 식입니다.|

## <a name="remarks"></a>설명

Visual Basic 컴파일러는 문을 사용 하 여 변수의 `Dim` 데이터 형식 및 변수에 액세스할 수 있는 코드와 같은 기타 정보를 확인 합니다. 다음 예에서는 변수를 선언 하 여 값을 저장 합니다 `Integer` .

```vb
Dim numberOfStudents As Integer
```

모든 데이터 형식 또는 열거형, 구조체, 클래스 또는 인터페이스의 이름을 지정할 수 있습니다.

```vb
Dim finished As Boolean
Dim monitorBox As System.Windows.Forms.Form
```

참조 형식의 경우 키워드를 사용 하 여 `New` 데이터 형식으로 지정 된 클래스 또는 구조체의 새 인스턴스를 만듭니다. 를 사용 하 `New` 는 경우 이니셜라이저 식을 사용 하지 않습니다. 대신, 필요한 경우 변수를 만들 클래스의 생성자에 인수를 제공 합니다.

```vb
Dim bottomLabel As New System.Windows.Forms.Label
```

프로시저, 블록, 클래스, 구조체 또는 모듈에서 변수를 선언할 수 있습니다. 소스 파일, 네임 스페이스 또는 인터페이스에서는 변수를 선언할 수 없습니다. 자세한 내용은 [선언 컨텍스트 및 기본 액세스 수준](declaration-contexts-and-default-access-levels.md)을 참조하세요.

프로시저 외부에서 모듈 수준에 선언 된 변수는 *멤버 변수* 또는 *필드* 입니다. 멤버 변수는 클래스, 구조체 또는 모듈 전체의 범위에 있습니다. 프로시저 수준에서 선언 된 변수는 *지역 변수* 입니다. 지역 변수는 해당 프로시저 또는 블록 내 에서만 범위 내에 있습니다.

프로시저 외부에서 변수를 선언 하는 데 사용 되는 액세스 한정자는 `Public` ,, `Protected` `Friend` , `Protected Friend` 및 `Private` 입니다. 자세한 내용은 [Visual Basic의 액세스 수준](../../programming-guide/language-features/declared-elements/access-levels.md)을 참조 하세요.

,,,,,,,, `Dim` `Public` `Protected` `Friend` `Protected Friend` `Private` `Shared` `Shadows` `Static` `ReadOnly` 또는 `WithEvents` 한정자를 지정 하는 경우 키워드는 선택 사항이 며 일반적으로 생략 됩니다.

```vb
Public maximumAllowed As Double
Protected Friend currentUserName As String
Private salary As Decimal
Static runningTotal As Integer
```

`Option Explicit`가 on (기본값) 이면 컴파일러에서 사용 하는 모든 변수에 대 한 선언이 필요 합니다. 자세한 내용은 [Option Explicit 문](option-explicit-statement.md)을 참조 하세요.

## <a name="specifying-an-initial-value"></a>초기 값 지정

변수를 만들 때 변수에 값을 할당할 수 있습니다. 값 형식의 경우 *이니셜라이저* 를 사용 하 여 변수에 할당 되는 식을 제공 합니다. 식은 컴파일 시간에 계산 될 수 있는 상수로 계산 되어야 합니다.

```vb
Dim quantity As Integer = 10
Dim message As String = "Just started"
```

이니셜라이저가 지정 되 고 절에 데이터 형식이 지정 되지 않은 경우 `As` *형식 유추* 를 사용 하 여 이니셜라이저의 데이터 형식을 유추 합니다. 다음 예제에서 `num1` 및 `num2` 는 모두 정수로 강력 하 게 형식화 됩니다. 두 번째 선언에서 형식 유추는 값 3에서 형식을 유추 합니다.

```vb
' Use explicit typing.
Dim num1 As Integer = 3

' Use local type inference.
Dim num2 = 3
```

형식 유추는 프로시저 수준에서 적용 됩니다. 클래스, 구조체, 모듈 또는 인터페이스의 프로시저 외부에는 적용 되지 않습니다. 형식 유추에 대 한 자세한 내용은 [Option 유추 문](option-infer-statement.md) 및 [지역 형식 유추](../../programming-guide/language-features/variables/local-type-inference.md)를 참조 하세요.

데이터 형식 또는 이니셜라이저가 지정 되지 않은 경우 발생 하는 상황에 대 한 자세한 내용은이 항목의 뒷부분에 나오는 [기본 데이터 형식 및 값](dim-statement.md#default) 을 참조 하십시오.

*개체 이니셜라이저* 를 사용 하 여 명명 된 형식과 익명 형식의 인스턴스를 선언할 수 있습니다. 다음 코드에서는 클래스의 인스턴스를 만들고 `Student` 개체 이니셜라이저를 사용 하 여 속성을 초기화 합니다.

```vb
Dim student1 As New Student With {.First = "Michael",
                                  .Last = "Tucker"}
```

개체 이니셜라이저에 대 한 자세한 내용은 [방법: 개체 이니셜라이저를 사용 하 여 개체 선언](../../programming-guide/language-features/objects-and-classes/how-to-declare-an-object-by-using-an-object-initializer.md), [개체 이니셜라이저: 명명 된 형식과 익명 형식](../../programming-guide/language-features/objects-and-classes/object-initializers-named-and-anonymous-types.md)및 [익명 형식](../../programming-guide/language-features/objects-and-classes/anonymous-types.md)을 참조 하세요.

## <a name="declaring-multiple-variables"></a>여러 변수 선언

하나의 선언문에서 여러 변수를 선언 하 고 각각에 대 한 변수 이름을 지정 하 고 괄호를 사용 하 여 각 배열 이름을 지정할 수 있습니다. 여러 변수는 쉼표로 구분됩니다.

```vb
Dim lastTime, nextTime, allTimes() As Date
```

절이 한 개 이상 있는 변수를 선언 하 `As` 는 경우 해당 변수 그룹에 대 한 이니셜라이저를 제공할 수 없습니다.

`As`선언 하는 각 변수에 대해 별도의 절을 사용 하 여 서로 다른 변수에 대해 서로 다른 데이터 형식을 지정할 수 있습니다. 각 변수는 해당 부분 뒤에 오는 첫 번째 절에 지정 된 데이터 형식을 사용 합니다 `As` `variablename` .

```vb
Dim a, b, c As Single, x, y As Double, i As Integer
' a, b, and c are all Single; x and y are both Double
```

## <a name="arrays"></a>배열

여러 값이 포함 될 수 있는 *배열을* 포함 하는 변수를 선언할 수 있습니다. 변수가 배열을 포함 하도록 지정 하려면 괄호를 사용 하 여 바로 뒤에를 추가 합니다 `variablename` . 배열에 대한 자세한 내용은 [배열](../../programming-guide/language-features/arrays/index.md)을 참조하세요.

배열의 각 차원에 대 한 하 한과 상한을 지정할 수 있습니다. 이렇게 하려면 괄호 안에를 포함 `boundslist` 합니다. 각 차원에 대해는 `boundslist` 상한을 지정 하 고 선택적으로 하한값을 지정 합니다. 지정 여부에 관계 없이 하한값은 항상 0입니다. 각 인덱스는 0부터 상한 값까지 달라질 수 있습니다.

다음 두 문은 동일 합니다. 각 문은 21 개 요소의 배열을 선언 `Integer` 합니다. 배열에 액세스할 때 인덱스는 0부터 20까지 달라질 수 있습니다.

```vb
Dim totals(20) As Integer
Dim totals(0 To 20) As Integer
```

다음 문은 형식의 2 차원 배열을 선언 합니다 `Double` . 배열에는 각각 6 개의 행 (5 + 1)이 있습니다 (5 + 1). 상한은 차원의 길이가 아니라 인덱스에 사용할 수 있는 가장 높은 값을 나타냅니다. 차원의 길이는 상한에 1을 더한 값입니다.

```vb
Dim matrix2(3, 5) As Double
```

배열은 1 ~ 32 차원을 포함할 수 있습니다.

배열 선언에서 모든 범위를 비워 둘 수 있습니다. 이렇게 하면 배열에 지정 된 차원 수가 있지만 초기화 되지 않습니다. `Nothing`하나 이상의 요소를 초기화할 때까지 값은입니다. `Dim`문은 모든 차원에 대해 범위를 지정 하거나 차원 없이 범위를 지정 해야 합니다.

```vb
' Declare an array with blank array bounds.
Dim messages() As String
' Initialize the array.
ReDim messages(4)
```

배열에 둘 이상의 차원이 있는 경우 괄호 사이에 쉼표를 포함 하 여 차원 수를 나타내야 합니다.

```vb
Dim oneDimension(), twoDimensions(,), threeDimensions(,,) As Byte
```

배열의 차원 중 하나를-1로 선언 하 여 *길이가 0 인 배열을* 선언할 수 있습니다. 길이가 0 인 배열을 포함 하는 변수에는 값이 없습니다 `Nothing` . 특정 공용 언어 런타임 함수에는 길이가 0 인 배열이 필요 합니다. 이러한 배열에 액세스 하려고 하면 런타임 예외가 발생 합니다. 자세한 내용은 [배열](../../programming-guide/language-features/arrays/index.md)을 참조하세요.

배열 리터럴을 사용 하 여 배열 값을 초기화할 수 있습니다. 이렇게 하려면 초기화 값을 중괄호 ()로 묶습니다 `{}` .

```vb
Dim longArray() As Long = {0, 1, 2, 3}
```

다차원 배열의 경우 각 개별 차원에 대 한 초기화는 외부 차원에서 중괄호로 묶입니다. 요소는 행 중심 순서로 지정 됩니다.

```vb
Dim twoDimensions(,) As Integer = {{0, 1, 2}, {10, 11, 12}}
```

배열 리터럴에 대 한 자세한 내용은 [배열](../../programming-guide/language-features/arrays/index.md)을 참조 하세요.

## <a name="default-data-types-and-values"></a><a name="default"></a> 기본 데이터 형식 및 값

다음 테이블에는 `Dim` 문에서 데이터 형식과 이니셜라이저를 지정하는 다양한 조합의 결과에 대한 설명이 나와 있습니다.

|데이터 형식 지정 여부|이니셜라이저 지정 여부|예제|결과|
|---|---|---|---|
|아니요|아니요|`Dim qty`|[Option Strict](option-strict-statement.md) 가 off로 설정 된 경우 (기본값) 변수는로 설정 됩니다 `Nothing` .<br /><br /> `Option Strict`가 on이면 컴파일 시간 오류가 발생합니다.|
|아니요|예|`Dim qty = 5`|[유추 옵션](option-infer-statement.md) (기본값)이 설정 된 경우 변수는 이니셜라이저의 데이터 형식을 사용 합니다. [지역 형식 유추](../../programming-guide/language-features/variables/local-type-inference.md)를 참조 하세요.<br /><br /> `Option Infer`가 off이고 `Option Strict`고 off이면 변수가 `Object`의 데이터 형식을 사용합니다.<br /><br /> `Option Infer`가 off이고 `Option Strict`는 on이면 컴파일 시간 오류가 발생합니다.|
|예|아니요|`Dim qty As Integer`|변수는 데이터 형식의 기본값으로 초기화됩니다. 이 단원의 뒷부분에 나오는 표를 참조 하세요.|
|예|예|`Dim qty  As Integer = 5`|이니셜라이저의 데이터 형식을 지정한 데이터 형식으로 변환할 수 없으면 컴파일 시간 오류가 발생합니다.|

데이터 형식을 지정 하지만 이니셜라이저를 지정 하지 않는 경우 Visual Basic는 변수를 해당 데이터 형식에 대 한 기본값으로 초기화 합니다. 다음 표에서는 기본 초기화 값을 보여 줍니다.

|데이터 형식|기본값|
|---|---|
|모든 숫자 형식 ( `Byte` 및 포함 `SByte` )|0|
|`Char`|이진 0|
|모든 참조 형식 ( `Object` , `String` 및 모든 배열 포함)|`Nothing`|
|`Boolean`|`False`|
|`Date`|1 년 1 월 1 일 오전 12:00 (01/01/0001 12:00:00 AM)|

구조체의 각 요소는 개별 변수인 것 처럼 초기화 됩니다. 배열의 길이를 선언 하지만 요소를 초기화 하지 않는 경우 각 요소는 개별 변수인 것 처럼 초기화 됩니다.

## <a name="static-local-variable-lifetime"></a>정적 지역 변수 수명

`Static`지역 변수는 변수가 선언 된 프로시저 보다 수명이 깁니다. 변수의 수명 범위는 프로시저가 선언 되는 위치 및이의 여부에 따라 달라 집니다 `Shared` .

|프로시저 선언|변수가 초기화 됨|변수가 기존에 중지 됨|
|---|---|---|
|모듈에서|프로시저가 처음 호출 될 때|프로그램 실행이 중지 되는 경우|
|클래스 또는 구조체에서 프로시저는 `Shared`|프로시저가 특정 인스턴스나 클래스 또는 구조체 자체에서 처음 호출 될 때|프로그램 실행이 중지 되는 경우|
|클래스 또는 구조체에서 프로시저는 그렇지 않습니다. `Shared`|프로시저가 특정 인스턴스에서 처음으로 호출 될 때|GC (가비지 수집)를 위해 인스턴스를 해제 하는 경우|

## <a name="attributes-and-modifiers"></a>특성 및 한정자

지역 변수가 아니라 멤버 변수에만 특성을 적용할 수 있습니다. 특성은 어셈블리의 메타 데이터에 정보를 제공 하며,이는 로컬 변수와 같은 임시 저장소에는 의미가 없습니다.

모듈 수준에서 한정자를 사용 하 여 `Static` 멤버 변수를 선언할 수 없습니다. 프로시저 수준에서 `Shared` ,, `Shadows` `ReadOnly` , `WithEvents` 또는 액세스 한정자를 사용 하 여 지역 변수를 선언할 수 없습니다.

를 제공 하 여 변수에 액세스할 수 있는 코드를 지정할 수 있습니다 `accessmodifier` . 클래스 및 모듈 멤버 변수 (프로시저 외부)는 기본적으로 private access로, 구조체 멤버 변수의 기본값은 공용 액세스입니다. 액세스 한정자를 사용 하 여 액세스 수준을 조정할 수 있습니다. 프로시저 내에서 지역 변수에 액세스 한정자를 사용할 수 없습니다.

`WithEvents`프로시저 내의 지역 변수가 아니라 멤버 변수에만 지정할 수 있습니다. 을 지정 하는 경우 `WithEvents` 변수의 데이터 형식은가 아닌 특정 클래스 형식 이어야 합니다 `Object` . 를 사용 하 여 배열을 선언할 수 없습니다 `WithEvents` . 이벤트에 대 한 자세한 내용은 [이벤트](../../programming-guide/language-features/events/index.md)를 참조 하세요.

> [!NOTE]
> 클래스, 구조체 또는 모듈 외부의 코드는 멤버 변수의 이름을 해당 클래스, 구조체 또는 모듈의 이름으로 한 정해야 합니다. 프로시저 또는 블록 외부의 코드는 해당 프로시저나 블록 내의 지역 변수를 참조할 수 없습니다.

## <a name="releasing-managed-resources"></a>관리 되는 리소스 해제

.NET Framework 가비지 수집기는 파트에서 추가 코딩 없이 관리 되는 리소스를 삭제 합니다. 그러나 가비지 수집기를 대기 하지 않고 관리 되는 리소스를 강제로 삭제할 수 있습니다.

클래스에서 특히 중요 하 고 부족 한 리소스 (예: 데이터베이스 연결 또는 파일 핸들)를 사용 하는 경우 더 이상 사용 하지 않는 클래스 인스턴스를 정리할 다음 가비지 수집이 끝날 때까지 기다리지 않으려고 할 수 있습니다. 클래스는 인터페이스를 구현 <xref:System.IDisposable> 하 여 가비지 수집 전에 리소스를 해제 하는 방법을 제공할 수 있습니다. 해당 인터페이스를 구현 하는 클래스는 `Dispose` 중요 한 리소스를 즉시 해제 하기 위해 호출할 수 있는 메서드를 노출 합니다.

`Using`문은 리소스를 확보 하 고, 문 집합을 실행 한 다음 리소스를 삭제 하는 프로세스를 자동화 합니다. 그러나 리소스는 인터페이스를 구현 해야 합니다 <xref:System.IDisposable> . 자세한 내용은 [Using 문](using-statement.md)을 참조 하세요.

## <a name="example"></a>예제

다음 예에서는 `Dim` 문을 여러 옵션과 함께 사용 하 여 변수를 선언 합니다.

[!code-vb[VbVbalrStatements#141](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class11.vb#141)]

## <a name="example"></a>예제

다음 예에서는 1에서 30 사이의 소수를 나열 합니다. 지역 변수의 범위는 코드 설명에 설명 되어 있습니다.

[!code-vb[VbVbalrStatements#142](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class11.vb#142)]

## <a name="example"></a>예제

다음 예제에서는 `speedValue` 변수가 클래스 수준에서 선언 됩니다. `Private`키워드는 변수를 선언 하는 데 사용 됩니다. 이 변수는 클래스의 모든 프로시저에서 액세스할 수 있습니다 `Car` .

[!code-vb[VbVbalrStatements#144](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class11.vb#144)]

[!code-vb[VbVbalrStatements#145](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class11.vb#145)]

## <a name="see-also"></a>참고 항목

- [Const 문](const-statement.md)
- [ReDim 문](redim-statement.md)
- [Option Explicit 문](option-explicit-statement.md)
- [Option Infer 문](option-infer-statement.md)
- [Option Strict 문](option-strict-statement.md)
- [프로젝트 디자이너, 컴파일 페이지(Visual Basic)](/visualstudio/ide/reference/compile-page-project-designer-visual-basic)
- [변수 선언](../../programming-guide/language-features/variables/variable-declaration.md)
- [배열](../../programming-guide/language-features/arrays/index.md)
- [개체 이니셜라이저: 명명된 형식 및 무명 형식](../../programming-guide/language-features/objects-and-classes/object-initializers-named-and-anonymous-types.md)
- [익명 형식](../../programming-guide/language-features/objects-and-classes/anonymous-types.md)
- [개체 이니셜라이저: 명명된 형식 및 무명 형식](../../programming-guide/language-features/objects-and-classes/object-initializers-named-and-anonymous-types.md)
- [방법: 개체 이니셜라이저를 사용하여 개체 선언](../../programming-guide/language-features/objects-and-classes/how-to-declare-an-object-by-using-an-object-initializer.md)
- [지역 형식 유추](../../programming-guide/language-features/variables/local-type-inference.md)
