---
title: 시작 F# Visual Studio에서
description: 사용 하는 방법을 알아봅니다 F# Visual Studio를 사용 하 여 합니다.
ms.date: 07/03/2018
ms.openlocfilehash: 020e5d32b3aa5d5a2195c19d70d8fe684fbd56ef
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/09/2019
ms.locfileid: "59331912"
---
# <a name="get-started-with-f-in-visual-studio"></a>시작 F# Visual Studio에서

F#시각적 개체 및 F# 도구는 Visual Studio IDE에서 지원 됩니다.

시작 하려면 했는지 [Visual Studio와 함께 설치 F# ](install-fsharp.md#install-f-with-visual-studio)합니다.

## <a name="creating-a-console-application"></a>콘솔 응용 프로그램 만들기

Visual Studio에서 가장 기본적인 프로젝트 중 하나에 콘솔 응용 프로그램입니다.  방법은 다음과 같습니다.  Visual Studio가 열리면:

1. 에 **파일** 메뉴에서 **새로 만들기**를 선택한 후 **프로젝트**합니다.

2. 새 프로젝트에서 대화 상자에서 아래 **템플릿을**, 표시 되어야 **시각적 F#** .  이 옵션을 표시 하려면 선택는 F# 템플릿.

3. 선택 **.NET Core 콘솔 앱** 하거나 **콘솔 앱**합니다.

3. 선택 된 **네** 만들기 단추를 F# 프로젝트!  이제는 F# 솔루션 탐색기에서 프로젝트입니다.

## <a name="writing-your-code"></a>코드 작성

보겠습니다 먼저 일부 코드를 작성 하 여 시작 하세요.  했는지를 `Program.fs` 파일 열려 있는 경우 및 다음 해당 콘텐츠를 다음으로 바꿉니다.

[!code-fsharp[HelloSquare](../../../samples/snippets/fsharp/getting-started/hello-square.fs)]

이전 코드 샘플에서는 함수 `square` 명명 된 입력을 가져와서는 정의한 `x` 을 단독으로 곱합니다.  때문에 F# 사용 하 여 [Typeinference](../language-reference/type-inference.md), 형식의 `x` 지정할 필요가 없습니다.  F# 컴파일러 곱하기 유효 형식에 대 한 이해 및 형식을 할당 합니다 `x` 하는 방법에 따라 `square` 라고 합니다.  위로 가져가면 `square`, 다음과 같이 표시 됩니다.

```
val square: x:int -> int
```

이 함수 형식 시그니처 라고 합니다.  다음과 같이 읽을 수 있습니다. "정사각형은 명명 된 정수를 사용 하는 함수 x는 정수를 생성 하 고".  컴파일러 했습니다 보면 `square` 를 `int` 형식 곱하기에서 제네릭 없기 때문에 이것이-지금은 *모든* 형식 이지만 대신 제네릭 형식의 폐쇄형 집합입니다.  F# 선택 하는 컴파일러 `int` 지금은 지점 하지만 조정 됩니다 형식 시그니처 호출 하는 경우 `square` 다른 입력 형식에 같은 `float`합니다.

다른 함수를 `main`, 정의 된으로 데코 레이트 된는 `EntryPoint` 하기가 특성은 F# 컴파일러는 프로그램 실행을 시작 해야 합니다.  다른 동일한 규칙을 따릅니다 [C 스타일 프로그래밍 언어](https://en.wikipedia.org/wiki/Entry_point#C_and_C.2B.2B), 여기서이 함수에 명령줄 인수를 전달할 수 있습니다 및 정수 코드가 반환 됩니다 (일반적으로 `0`).

이 함수를 호출 하는 것은 `square` 의 인수를 사용 하 여 함수 `12`합니다.  F# 컴파일러에는 다음 형식의 할당 `square` 되도록 `int -> int` (사용 하는 함수,는 `int` 생성 및는 `int`).  에 대 한 호출 `printfn` 은 형식 문자열에 지정 된 해당 하는 매개 변수를 C 스타일 프로그래밍 언어와 유사한 형식 문자열을 사용 하는 서식이 지정 된 인쇄 기능 및 다음 결과 새 줄을 출력 합니다.

## <a name="running-your-code"></a>코드 실행

코드를 실행 하 고 키를 눌러 결과 볼 수 있습니다 **Ctrl**+**F5**합니다.  이 디버깅 하지 않고 프로그램을 실행 하 고 결과 볼 수 있습니다.  선택할 수 있습니다 합니다 **디버깅할** 최상위 메뉴 항목 Visual Studio에서 선택한 **디버깅 하지 않고 시작**합니다.

이제 Visual Studio를 나타나게 하는 콘솔 창에 출력 한 다음을 표시 됩니다.

```
12 squared is 144!
```

지금까지  첫 번째 만든 F# 작성 된 Visual Studio에서 프로젝트를 F# 함수는 함수 및 일부 결과를 보려면 프로젝트를 실행 하는 호출의 결과 인쇄 합니다.

## <a name="next-steps"></a>다음 단계

않았다면, 체크 아웃 합니다 [둘러보기 F# ](../tour.md)의 핵심 기능 중 일부를 포함 합니다 F# 언어.  기능 중 몇 가지를 간략하게 제공 합니다 F#, Visual Studio로 복사 하 고 실행할 수 있는 충분 한 코드 샘플을 제공 합니다.  도 유용한 외부 리소스 사용할 수 있습니다에 표시 된 [ F# 가이드](../index.md)합니다.

## <a name="see-also"></a>참고자료

- [F# 둘러보기](../tour.md)
- [F#언어 참조](../language-reference/index.md)
- [형식 유추](../language-reference/type-inference.md)
- [기호 및 연산자 참조](../language-reference/symbol-and-operator-reference/index.md)
