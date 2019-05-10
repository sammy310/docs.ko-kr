---
title: Visual Studio에서 F# 시작
description: Visual Studio에서 F#을 사용하는 방법을 알아봅니다.
ms.date: 07/03/2018
ms.openlocfilehash: 9b02a5d295f982b1911dab567213fa9a2b6c4304
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/28/2019
ms.locfileid: "64754870"
---
# <a name="get-started-with-f-in-visual-studio"></a>Visual Studio에서 F# 시작

F#과 Visual F# 도구가 Visual Studio IDE에서 지원됩니다.

시작하기 위해서는 [F#이 설치된 Visual Studio](install-fsharp.md#install-f-with-visual-studio)가 있어야 합니다.

## <a name="creating-a-console-application"></a>콘솔 응용 프로그램 만들기

Visual Studio에서 가장 기본적인 프로젝트 중 하나가 콘솔 응용 프로그램입니다.  방법은 다음과 같습니다.  Visual Studio를 열고

1. **파일** 메뉴에서 **새로 만들기**를 선택한 후 **프로젝트**를 선택합니다.

2. 새 프로젝트에서 대화 상자의 **템플릿**에서 **Visual F#** 을 확인합니다.  F# 템플릿을 표시하려면 이 옵션을 선택합니다.

3. **.NET Core 콘솔 앱**이나 **콘솔 앱**을 선택합니다.

4. F# 프로젝트를 만들기 위해 **확인** 버튼을 클릭힙니다.  이제 솔루션 탐색기에서 F# 프로젝트를 확인할 수 있습니다.

## <a name="writing-your-code"></a>코드 작성

먼저 코드 작성으로 시작하세요.  `Program.fs` 파일을 열고 다음 내용으로 변경합니다.

[!code-fsharp[HelloSquare](../../../samples/snippets/fsharp/getting-started/hello-square.fs)]

이 코드 샘플에서는 입력으로 `x`를 가져와 자신과 곱셈하도록 정의된 `square`함수가 정의되어 있습니다.  F#에서는 [Typeinference](../language-reference/type-inference.md)를 사용하기 때문에 `x`의 형식을 지정할 필요가 없습니다.  F# 컴파일러는 곱셈에서 유효한 형식을 이해하고 `square`가 호출되는 방식에 따라 `x`의 형식을 할당합니다.  `square` 위로 마우스를 가져가면 다음과 같이 표시됩니다.

```fsharp
val square: x:int -> int
```

이것을 함수 형식 시그니처라고 합니다.  다음과 같이 "square는 정수 x를 사용하고 정수를 생성하는 함수"라고 읽을 수 있습니다.  컴파일러가 `square`를 `int`형식으로 지정한 것에 주목하십시오. 곱셈은 *모든* 형식에서 제네릭이 아니라, 폐쇄형 집합 형식에서 제네릭이기 때문입니다.  F# 컴파일러에서 지금은 `int`를 선택하지만, `float` 같은 다른 입력 형식으로 `square`를 호출 하는 경우는 형식 시그니처가 조정됩니다.

그 밖에 `main` 함수가 정의되고 F# 컴파일러에게 프로그램 수행이 시작되는 곳이라는 것을 알려주는 `EntryPoint`속성이 데코레이트되었습니다.  함수에 명령줄 인수를 전달하고 정수 코드(일반적으로 `0`)를 반환하는 [C 스타일 프로그래밍 언어](https://en.wikipedia.org/wiki/Entry_point#C_and_C.2B.2B)와 동일한 규칙을 따릅니다.

이 함수에서는 인수로 `12`를 사용하여 `square` 함수를 호출합니다.  F# 컴파일러에는 `square`의 형식을 `int -> int`가 되도록 할당합니다(이것이 `int`를 가지고 `int`를 생성하는 함수입니다).  `printfn` 호출은 서식이 지정된 출력 기능으로, C 스타일 프로그래밍 언어와 유사한 형식 문자열을 사용하고, 형식 문자열의 서식이 지정된 매개 변수와 결과를 새로운 라인에 출력합니다.

## <a name="running-your-code"></a>코드 실행

코드를 실행 하 고 키를 눌러 결과 볼 수 있습니다 **Ctrl**+**F5**합니다.  이 디버깅 하지 않고 프로그램을 실행 하 고 결과 볼 수 있습니다.  선택할 수 있습니다 합니다 **디버깅할** 최상위 메뉴 항목 Visual Studio에서 선택한 **디버깅 하지 않고 시작**합니다.

이제 Visual Studio를 나타나게 하는 콘솔 창에 출력 한 다음을 표시 됩니다.

```
12 squared is 144!
```

지금까지  첫 번째 만든 F# 작성 된 Visual Studio에서 프로젝트를 F# 함수는 함수 및 일부 결과를 보려면 프로젝트를 실행 하는 호출의 결과 인쇄 합니다.

## <a name="next-steps"></a>다음 단계

아직 확인하지 않았다면 F# 언어의 핵심 기능 중 일부를 다루는 [F# 둘러보기](../tour.md)를 확인해보세요.  기능 중 몇 가지를 간략하게 제공 합니다 F#, Visual Studio로 복사 하 고 실행할 수 있는 충분 한 코드 샘플을 제공 합니다.  [F# 가이드](../index.md)에서 소개된 훌륭한 외부 리소스도 있습니다.

## <a name="see-also"></a>참고자료

- [F# 둘러보기](../tour.md)
- [F# 언어 참조](../language-reference/index.md)
- [형식 유추](../language-reference/type-inference.md)
- [기호 및 연산자 참조](../language-reference/symbol-and-operator-reference/index.md)
