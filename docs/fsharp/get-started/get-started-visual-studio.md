---
title: Visual Studio F# 에서 시작 하기
description: Visual Studio에서를 F# 사용 하는 방법을 알아봅니다.
ms.date: 07/03/2018
ms.openlocfilehash: 80b4fc5b7631eace719832fe32003cad578ead27
ms.sourcegitcommit: 93762e1a0dae1b5f64d82eebb7b705a6d566d839
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/27/2019
ms.locfileid: "74552824"
---
# <a name="get-started-with-f-in-visual-studio"></a>Visual Studio F# 에서 시작 하기

F#그리고 visual Studio F# IDE에서 비주얼 도구가 지원 됩니다.

먼저를 [사용 하 여 F#Visual Studio를 설치 ](install-fsharp.md#install-f-with-visual-studio)했는지 확인 합니다.

## <a name="creating-a-console-application"></a>콘솔 응용 프로그램 만들기

Visual Studio의 가장 기본적인 프로젝트 중 하나는 콘솔 응용 프로그램입니다.  방법은 다음과 같습니다.  Visual Studio가 열리면 다음을 수행 합니다.

1. **파일** 메뉴에서 **새로 만들기**를 가리킨 다음 **프로젝트**를 선택 합니다.

2. 새 프로젝트 대화 상자의 **템플릿**아래에 **시각적 개체 F#** 가 표시 되어야 합니다.  F# 템플릿을 표시 하려면이를 선택 합니다.

3. **.Net Core 콘솔 앱** 또는 **콘솔 앱**을 선택 합니다.

4. 확인 단추 **를 선택 하 여** F# 프로젝트를 만듭니다.  이제 솔루션 탐색기에 F# 프로젝트가 표시 됩니다.

## <a name="writing-your-code"></a>코드 작성

먼저 코드를 작성 하 여 시작 해 보겠습니다.  `Program.fs` 파일이 열려 있는지 확인 하 고 해당 내용을 다음으로 바꿉니다.

[!code-fsharp[HelloSquare](~/samples/snippets/fsharp/getting-started/hello-square.fs)]

위의 코드 샘플에서는 `x` 라는 입력을 사용 하는 `square` 함수를 정의 하 고 그 자체로 곱합니다.  에서는 F# [형식 유추](../language-reference/type-inference.md)를 사용 하므로 `x` 형식을 지정할 필요가 없습니다.  컴파일러 F# 는 곱하기가 유효한 형식을 이해 하 고 `square` 호출 되는 방식에 따라 `x`에 형식을 할당 합니다.  `square`를 마우스로 가리키면 다음과 같이 표시 됩니다.

```fsharp
val square: x:int -> int
```

이를 함수의 형식 서명 이라고 합니다.  다음과 같이 읽을 수 있습니다. "Square는 x 라는 정수를 사용 하 고 정수를 생성 하는 함수입니다."  컴파일러는 현재 `int` 형식 `square`를 제공 했습니다 .이는 곱하기가 *모든* 형식에서 제네릭이 아니라 폐쇄형 형식 집합에 대해 제네릭 이기 때문입니다.  이 F# 시점에서 컴파일러 `int` 선택 되었지만 `float`와 같은 다른 입력 형식으로 `square`를 호출 하는 경우 형식 시그니처를 조정 합니다.

`EntryPoint` 특성으로 데코 레이트 된 다른 함수인 `main`를 정의 하 여 프로그램 실행을 시작 해야 F# 함을 컴파일러에 알립니다.  이 함수는 명령줄 인수를이 함수에 전달할 수 있는 다른 [C 스타일 프로그래밍 언어](https://en.wikipedia.org/wiki/Entry_point#C_and_C.2B.2B)와 동일한 규칙을 따르며 정수 코드가 반환 됩니다 (일반적으로 `0`).

이 함수에서는 `12`의 인수를 사용 하 여 `square` 함수를 호출 합니다.  그런 F# 다음 컴파일러는 `int -> int` 되는 `square` 형식 (즉, `int`를 사용 하 고 `int`를 생성 하는 함수)을 할당 합니다.  `printfn`에 대 한 호출은 형식 문자열을 사용 하는 서식 있는 인쇄 함수 이며, 형식 문자열에 지정 된 매개 변수에 해당 하는 매개 변수는 C 스타일 프로그래밍 언어와 비슷하며, 결과와 새 줄을 출력 합니다.

## <a name="running-your-code"></a>코드 실행

**Ctrl**+**F5**키를 눌러 코드를 실행 하 고 결과를 볼 수 있습니다.  이렇게 하면 프로그램을 디버깅 하지 않고 실행 하 고 결과를 볼 수 있습니다.  또는 Visual Studio에서 **디버그** 최상위 메뉴 항목을 선택 하 고 **디버깅 하지 않고 시작**을 선택할 수 있습니다.

이제 Visual Studio가 표시 된 콘솔 창에 다음과 같이 출력 됩니다.

```console
12 squared is 144!
```

지금까지  Visual Studio에서 첫 번째 F# 프로젝트를 만들고 함수를 작성 F# 하 여 해당 함수를 호출한 결과를 출력 하 고 프로젝트를 실행 하 여 일부 결과를 확인 했습니다.

## <a name="next-steps"></a>다음 단계

아직 없는 경우 F# 언어의 핵심 기능 중 일부를 포함 하는 [둘러보기 F# ](../tour.md)를 확인 하세요.  의 F#기능 중 일부에 대 한 개요를 제공 하 고 Visual Studio로 복사 하 여 실행할 수 있는 충분 한 코드 샘플을 제공 합니다.  F# 문서 [ F# 홈페이지](../index.yml)에서 설명서에 대해 자세히 알아볼 수도 있습니다.

## <a name="see-also"></a>참조

- [F# 둘러보기](../tour.md)
- [F#언어 참조](../language-reference/index.md)
- [형식 유추](../language-reference/type-inference.md)
- [기호 및 연산자 참조](../language-reference/symbol-and-operator-reference/index.md)
