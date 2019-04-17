---
title: Visual Studio에서 F# 시작
description: Visual Studio에서 F#을 사용하는 방법을 알아봅니다.
ms.date: 07/03/2018
ms.openlocfilehash: 020e5d32b3aa5d5a2195c19d70d8fe684fbd56ef
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/09/2019
ms.locfileid: "59331912"
---
# <a name="get-started-with-f-in-visual-studio"></a>Visual Studio에서 F# 시작

F#과 Visual F# 도구가 Visual Studio IDE에서 지원됩니다.

시작하기 위해서는 [F#이 설치된 Visual Studio](install-fsharp.md#install-f-with-visual-studio)가 있어야 합니다.

## <a name="creating-a-console-application"></a>콘솔 응용 프로그램 만들기

Visual Studio에서 가장 기본적인 프로젝트 중 하나가 콘솔 응용 프로그램입니다.  방법은 다음과 같습니다.  Visual Studio를 열고

1. **파일** 메뉴에서 **새로 만들기**를 선택한 후 **프로젝트**를 선택합니다.

2. 새 프로젝트에서 대화 상자의 **템플릿**에서 **Visual F#**을 확인합니다. F# 템플릿을 표시하려면 이 옵션을 선택합니다.

3. **.NET Core 콘솔 앱**이나 **콘솔 앱**을 선택합니다.

3. F# 프로젝트를 만들기 위해 **확인** 버튼을 클릭힙니다.  이제 솔루션 탐색기에서 F# 프로젝트를 확인할 수 있습니다.

## <a name="writing-your-code"></a>코드 작성

먼저 코드 작성으로 시작하세요.  `Program.fs` 파일을 열고 다음 내용으로 변경합니다.

[!code-fsharp[HelloSquare](../../../samples/snippets/fsharp/getting-started/hello-square.fs)]

이 코드 샘플에서는 입력으로 `x`를 가져와 같은 값으로 곱셈하도록 정의된 `square`함수가 정의되어 있습니다.  F#에서는 [형식 추정](../language-reference/type-inference.md)을 사용하기 때문에 `x`의 형식을 지정할 필요가 없습니다.  F# 컴파일러는 곱셈이 유효한 형식을 이해하고 `square`가 호출되는 방식에 따라 `x`에 형식을 할당합니다.  `square` 위로 마우스를 가져가면 다음과 같이 표시됩니다.

```
val square: x:int -> int
```

이것을 함수 형식 시그니처라고 합니다. 다음과 같이 "square는 정수 x를 사용하고 정수를 생성하는 함수"라고 읽을 수 있습니다. 컴파일러가 `square`를 `int`형식으로 지정한 것에 주목합니다. 곱셈은 *모든* 형식에서 제네릭이 아니라, 폐쇄형 집합 형식에서 제네릭이기 때문입니다. F# 컴파일러에서 지금은 `int`를 선택하지만, `float` 같은 다른 입력 형식으로 `square`를 호출하는 경우 형식 시그니처가 조정됩니다.

그 밖에 `main` 함수가 정의되고 F# 컴파일러에게 프로그램 수행이 시작되는 곳이라는 것을 알려주는 `EntryPoint`속성이 데코레이트되었습니다.  함수에 명령줄 인수를 전달하고 정수 코드를 반환(일반적으로 `0`)하는 [C 스타일 프로그래밍 언어](https://en.wikipedia.org/wiki/Entry_point#C_and_C.2B.2B)와 동일한 규칙을 따릅니다.

이 함수에서는 인수로 `12`를 사용하여 `square` 함수를 호출합니다.  F# 컴파일러에는 `square`의 형식을 `int -> int`가 되도록 할당합니다(즉, `int`로 `int`를 생성하는 함수).  `printfn` 호출은 서식이 지정된 출력기능으로, C 스타일 프로그래밍 언어와 유사한 형식 문자열(형식 문자열의 서식이 지정된 매개 변수)을 사용하고 결과와 새로운 라인을 출력합니다.

## <a name="running-your-code"></a>코드 실행

**Ctrl**+**F5** 단축키를 사용하여 코드를 실행하고 그 결과 볼 수 있습니다. 이렇게 하면 디버깅 하지 않고 프로그램을 실행하고 결과 볼 수 있습니다. 또는 Visual Studio의 최상단 메뉴에서 **디버깅**과 **디버깅 하지 않고 시작**항목을 선택할 수도 있습니다.

이제 Visual Studio의 콘솔 창에서 다음 내용이 표시되는 것을 볼 수 있습니다.

```
12 squared is 144!
```

축하합니다. 지금까지 Visual Studio에서 프로젝트 첫 번째 F# 프로젝트를 만들고, 함수를 호출하면 그 결과를 출력하는 F# 함수를 작성하고, 결과를 확인하기 위해 실행해 보았습니다.

## <a name="next-steps"></a>다음 단계

아직 F# 언어의 핵심 기능을 확인하지 않았다면 [F# 둘러보기](../tour.md)에서 확인하십시오. 여기에는 F#의 몇 가지 기능에 대한 개요를 제공하고 Visual Studio로 복사하여 실행할 수 있는 충분한 코드 샘플을 제공합니다. [F# 가이드](../index.md)에 소개된 훌륭한 외부 리소스도 있습니다.

## <a name="see-also"></a>참고자료

- [F# 둘러보기](../tour.md)
- [F#언어 참조](../language-reference/index.md)
- [형식 유추](../language-reference/type-inference.md)
- [기호 및 연산자 참조](../language-reference/symbol-and-operator-reference/index.md)
