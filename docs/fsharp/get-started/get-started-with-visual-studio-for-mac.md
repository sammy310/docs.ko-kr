---
title: Mac 용 Visual Studio에서 F# 시작
description: Mac 용 Visual Studio에서 F#을 사용하는 방법을 알아봅니다.
ms.date: 07/03/2018
ms.openlocfilehash: a6997f139d7e6c5fdf77878442db0b0b75b3d727
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/09/2019
ms.locfileid: "59331873"
---
# <a name="get-started-with-f-in-visual-studio-for-mac"></a>Mac 용 Visual Studio에서 F# 시작

F#과 F# Visual 도구가 Mac IDE용 Visual Studio에서 지원됩니다. [Mac용 Visual Studio의 설치](install-fsharp.md#install-f-with-visual-studio-for-mac)를 확인합니다.

## <a name="creating-a-console-application"></a>콘솔 응용 프로그램 만들기

Mac 용 Visual Studio에서 가장 기본적인 프로젝트 중 하나는 콘솔 응용 프로그램입니다.  방법은 다음과 같습니다.  Mac 용 Visual Studio를 열고

1. **파일** 메뉴에서 **새 솔루션**을 선택합니다.

2. 새 프로젝트 대화 상자에서 콘솔 응용 프로그램에 대 한 2 개의 다른 템플릿이 있습니다.  다른 하나는.NET Framework를 대상으로 하는.NET-> 합니다.  .NET Core는 다른 템플릿에->.NET Core를 대상으로 하는 앱입니다.  이 문서의 목적을 위해 템플릿 작동 해야 합니다.

3. 필요에 따라 콘솔 앱을 C#에서 F#으로 변경합니다.  다음으로 진행하기 위해 **다음**버튼을 선택합니다.  

4. 프로젝트 이름을 지정하고 앱에서 사용할 옵션을 선택합니다.  화면 측면의 미리 보기 창에는 선택한 옵션을 기반으로 생성될 디렉터리 구조가 표시됩니다.  

5. **만들기**를 클릭합니다.  이제는 솔루션 탐색기에서 F# 프로젝트를 볼 수 있습니다.

## <a name="writing-your-code"></a>코드 작성

먼저 코드 작성으로 시작하세요.  `Program.fs` 파일을 열고 다음 내용으로 변경합니다.

[!code-fsharp[HelloSquare](../../../samples/snippets/fsharp/getting-started/hello-square.fs)]

이 코드 샘플에서는 입력으로 `x`를 가져와 자신과 곱셈하도록 정의된 `square`함수가 정의되어 있습니다.  F#에서는 [Typeinference](../language-reference/type-inference.md)를 사용하기 때문에 `x`의 형식을 지정할 필요가 없습니다.  F# 컴파일러는 곱셈에서 유효한 형식을 이해하고 `square`가 호출되는 방식에 따라 `x`의 형식을 할당합니다.  `square` 위로 마우스를 가져가면 다음과 같이 표시됩니다.

```
val square: x:int -> int
```

이 함수 형식 시그니처 라고 합니다.  다음과 같이 읽을 수 있습니다. "정사각형은 명명 된 정수를 사용 하는 함수 x는 정수를 생성 하 고".  컴파일러 했습니다 보면 `square` 를 `int` 형식 곱하기에서 제네릭 없기 때문에 이것이-지금은 *모든* 형식 이지만 대신 제네릭 형식의 폐쇄형 집합입니다.  F# 선택 하는 컴파일러 `int` 지금은 지점 하지만 조정 됩니다 형식 시그니처 호출 하는 경우 `square` 다른 입력 형식에 같은 `float`합니다.

그 밖에 `main` 함수가 정의되고 F# 컴파일러에게 프로그램 수행이 시작되는 곳이라는 것을 알려주는 `EntryPoint`속성이 데코레이트되었습니다.  함수에 명령줄 인수를 전달하고 정수 코드(일반적으로 `0`)를 반환하는 [C 스타일 프로그래밍 언어](https://en.wikipedia.org/wiki/Entry_point#C_and_C.2B.2B)와 동일한 규칙을 따릅니다.

이 함수에서는 인수로 `12`를 사용하여 `square` 함수를 호출합니다.  F# 컴파일러에는 `square`의 형식을 `int -> int`가 되도록 할당합니다(이것이 `int`를 가지고 `int`를 생성하는 함수입니다).  `printfn` 호출은 서식이 지정된 출력 기능으로, C 스타일 프로그래밍 언어와 유사한 형식 문자열을 사용하고, 형식 문자열의 서식이 지정된 매개 변수와 결과를 새로운 라인에 출력합니다.

## <a name="running-your-code"></a>코드 실행

최상단 메뉴에서 **실행**과 **디버깅하지 않고 시작**을 순서대로 클릭하여 코드를 실행하고 그 결과를 확인할 수 있습니다.  이렇게 하면 디버깅을 하지 않고 프로그램을 실행하여 그 결과 볼 수 있습니다.

이제 Mac 용 Visual Studio의 콘솔 창에서 다음 내용이 표시되는 것을 볼 수 있습니다.

```
12 squared is 144!
```

지금까지  첫 번째 만든 F# 작성 하는 Mac 용 Visual Studio에서 프로젝트를 F# 함수, 함수 및 일부 결과를 보려면 프로젝트를 실행 하는 호출의 결과 인쇄 합니다.

## <a name="using-f-interactive"></a>사용 하 여 F# 대화형

시각적 개체의 가장 유용한 기능 중 F# Mac에 Visual Studio에서 도구를 F# 대화형 창입니다.  해당 코드를 호출 하 고 결과 대화형으로 볼 수 있는 프로세스에 코드를 보내야 할 수 있습니다.

사용을 시작 하려면 강조 표시 된 `square` 함수 코드에 정의 합니다.  다음으로, 클릭 **편집** 최상위 메뉴에서.  다음 선택 **선택 항목에 보내기 F# 대화형**합니다.  이 코드를 실행 합니다 F# 대화형 창입니다.  선택 영역을 마우스 오른쪽 단추로 클릭 하 고 선택할 수 있습니다 또는 **선택 항목에 보내기 F# 대화형**합니다.  표시 되어야 합니다 F# 대화형 창에서 다음을 사용 하 여 표시 합니다.

```
>

val square : x:int -> int

>
```

이 대 한 동일한 함수 시그니처를 보여 줍니다는 `square` 함수 위로 가져갈 때 앞서 보았던는 함수입니다.  때문에 `square` 에 정의 된 F# 대화형 프로세스를 호출할 수 있습니다 다른 값을 사용 하 여:

```
> square 12;;
val it : int = 144
>square 13;;
val it : int = 169
```

이 함수를 실행, 새 이름으로 결과 바인딩합니다 `it`, 형식 및 값 표시 `it`합니다.  각 줄을 종료 해야 참고 `;;`합니다.  이 방법을 F# 대화형 함수 호출 완료 되 면 알고 있습니다.  새 함수를 정의할 수도 있습니다 F# Interactive:

```
> let isOdd x = x % 2 <> 0;;

val isOdd : x:int -> bool

> isOdd 12;;
val it : bool = false
```

위의 새 함수를 정의 `isOdd`를 사용 하는 `int` 홀수 인지를 확인!  서로 다른 입력을 사용 하 여 반환 값을 확인 하려면이 함수를 호출할 수 있습니다.  함수 호출 내에서 함수를 호출할 수 있습니다.

```
> isOdd (square 15);;
val it : bool = true
```

사용할 수도 있습니다는 [파이프 정방향 연산자](../language-reference/symbol-and-operator-reference/index.md) 두 함수에 값을 파이프라인에:

```
> 15 |> square |> isOdd;;
val it : bool = true
```

나중에 자습서 정방향 파이프 연산자 등을 설명 합니다.

이 사용 하 여 수행할 수 있는 작업에 대해 간략히만 F# 대화형입니다.  자세한 내용은 체크 아웃 [를 사용한 대화형 프로그래밍 F# ](../tutorials/fsharp-interactive/index.md)합니다.

## <a name="next-steps"></a>다음 단계

않았다면, 체크 아웃 합니다 [둘러보기 F# ](../tour.md)의 핵심 기능 중 일부를 포함 합니다 F# 언어.  기능 중 몇 가지를 간략하게 제공 합니다 F#, Mac 및 실행에 대 한 Visual Studio에 복사할 수 있는 충분 한 코드 샘플을 제공 합니다.  도 유용한 외부 리소스 사용할 수 있습니다에 표시 된 [ F# 가이드](../index.md)합니다.

## <a name="see-also"></a>참고자료

- [Visual F#](../index.md)
- [F# 둘러보기](../tour.md)
- [F#언어 참조](../language-reference/index.md)
- [형식 유추](../language-reference/type-inference.md)
- [기호 및 연산자 참조](../language-reference/symbol-and-operator-reference/index.md)
