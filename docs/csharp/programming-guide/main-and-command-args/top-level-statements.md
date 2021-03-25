---
title: 최상위 문 - C# 프로그래밍 가이드
description: C# 9 이상의 최상위 문에 대해 알아봅니다.
ms.date: 03/08/2021
helpviewer_keywords:
- C# language, top-level statements
- C# language, Main method
ms.openlocfilehash: 69ff5fd606f5e12f55bd3e6dfc15fc7e64d8352b
ms.sourcegitcommit: e3cf8227573e13b8e1f4e3dc007404881cdafe47
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/11/2021
ms.locfileid: "103190451"
---
# <a name="top-level-statements-c-programming-guide"></a>최상위 문(C# 프로그래밍 가이드)

C# 9부터 콘솔 애플리케이션 프로젝트에 `Main` 메서드를 명시적으로 포함할 필요가 없습니다. 대신 *최상위 문* 기능을 사용하여 작성해야 하는 코드를 최소화할 수 있습니다. 이 경우 컴파일러는 애플리케이션에 대한 클래스 및 `Main` 메서드 진입점을 생성합니다.

다음은 C# 9의 완전한 C# 프로그램인 *Program.cs* 파일입니다.

:::code language="csharp" source="snippets/top-level-statements-1/Program.cs":::

최상위 문을 사용하면 Azure Functions 및 GitHub Actions와 같은 소규모 유틸리티에 대한 간단한 프로그램을 작성할 수 있습니다. 또한 새로운 C# 프로그래머가 코드를 학습하고 작성하는 작업을 더 쉽게 수행할 수 있습니다.

다음 섹션에서는 최상위 문으로 수행할 수 있는 작업과 수행할 수 없는 작업에 대한 규칙을 설명합니다.

## <a name="only-one-top-level-file"></a>하나의 최상위 파일만

애플리케이션에는 진입점이 하나만 있어야 하므로 프로젝트에는 최상위 문이 있는 파일이 하나만 있을 수 있습니다. 프로젝트의 두 개 이상의 파일에 최상위 문을 넣으면 다음과 같은 컴파일러 오류가 발생합니다.

> CS8802 하나의 컴파일 단위만 최상위 문을 포함할 수 있습니다.

프로젝트에는 최상위 문이 없는 추가 소스 코드 파일이 얼마든지 있을 수 있습니다.

## <a name="no-other-entry-points"></a>다른 진입점 없음

`Main` 메서드를 명시적으로 작성할 수 있지만 진입점으로 작동할 수는 없습니다. 컴파일러에서 다음과 같은 경고가 발생합니다.

> CS7022 프로그램의 진입점은 전역 코드이며 'Main()' 진입점은 무시됩니다.

최상위 문이 있는 프로젝트에서는 프로젝트에 하나 이상의 `Main` 메서드가 있는 경우에도 [-main](../../language-reference/compiler-options/main-compiler-option.md) 컴파일러 옵션을 사용하여 진입점을 선택할 수 없습니다.

## <a name="using-directives"></a>`using` 지시문

using 지시문을 포함하는 경우 다음 예제와 같이 파일에서 먼저 제공되어야 합니다.

:::code language="csharp" source="snippets/top-level-statements-1/Program.cs":::

## <a name="global-namespace"></a>전역 네임스페이스

최상위 문은 전역 네임스페이스에서 암시적으로 사용할 수 있습니다.

## <a name="namespaces-and-type-definitions"></a>네임스페이스 및 형식 정의

최상위 문이 있는 파일에는 네임스페이스 및 형식 정의도 포함될 수 있지만 최상위 문 뒤에 와야 합니다. 예를 들면 다음과 같습니다.

:::code language="csharp" source="snippets/top-level-statements-2/Program.cs":::

## `args`

최상위 문은 `args` 변수를 참조하여 입력된 명령줄 인수에 액세스할 수 있습니다. `args` 변수는 null이 아니지만 명령줄 인수가 제공되지 않은 경우 `Length`는 0입니다. 예를 들면 다음과 같습니다.

:::code language="csharp" source="snippets/top-level-statements-3/Program.cs":::

## `await`

`await`를 사용하여 비동기 메서드를 호출할 수 있습니다. 예를 들면 다음과 같습니다.

:::code language="csharp" source="snippets/top-level-statements-4/Program.cs":::

## <a name="exit-code-for-the-process"></a>프로세스의 종료 코드

애플리케이션 종료될 때 `int` 값을 반환하려면 `int`를 반환하는 `Main` 메서드에서와 같이 `return` 문을 사용합니다. 예를 들면 다음과 같습니다.

:::code language="csharp" source="snippets/top-level-statements-5/Program.cs":::

## <a name="implicit-entry-point-method"></a>암시적 진입점 메서드

컴파일러는 최상위 문이 있는 프로젝트의 프로그램 진입점 역할을 하는 메서드를 생성합니다. 이 메서드의 이름은 실제로 `Main`이 아니라 코드에서 직접 참조할 수 없는 구현 세부 정보입니다. 메서드의 서명은 최상위 문에 `await` 키워드 또는 `return` 문이 포함되어 있는지 여부에 따라 달라집니다. 다음 표에서는 편의를 위해 표에 있는 메서드 이름 `Main`을 사용하여 메서드 서명이 어떻게 표시되는지 보여줍니다.

| 최상위 코드에는 다음이 포함됩니다.| 암시적 `Main` 서명                    |
|------------------------|----------------------------------------------|
| `await` 및 `return`   | `static async Task<int> Main(string[] args)` |
| `await`                | `static async Task Main(string[] args)`      |
| `return`               | `static int Main(string[] args)`             |
| `await` 또는 `return` 없음 | `static void Main(string[] args)`            |

## <a name="c-language-specification"></a>C# 언어 사양

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]
[최상위 문](~/_csharplang/proposals/csharp-9.0/top-level-statements.md)

## <a name="see-also"></a>참고 항목

- [C# 프로그래밍 가이드](../index.md)
- [메서드](../classes-and-structs/methods.md)
- [C# 프로그램 내부](../inside-a-program/index.md)
