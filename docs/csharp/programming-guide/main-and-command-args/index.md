---
title: Main()과 명령줄 인수 - C# 프로그래밍 가이드
ms.date: 08/02/2017
f1_keywords:
- CS5001
- main_CSharpKeyword
- Main
helpviewer_keywords:
- Main method [C#]
- C# language, command-line arguments
- arguments [C#], command-line
- command line [C#], arguments
- command-line arguments [C#], Main method
ms.assetid: 73a17231-cf96-44ea-aa8a-54807c6fb1f4
ms.openlocfilehash: 190216b01ea416aedbca270a6d7a5acbf0c2e797
ms.sourcegitcommit: 5988e9a29cedb8757320817deda3c08c6f44a6aa
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/28/2020
ms.locfileid: "82200121"
---
# <a name="main-and-command-line-arguments-c-programming-guide"></a>Main()과 명령줄 인수(C# 프로그래밍 가이드)

`Main` 메서드는 C# 애플리케이션의 진입점입니다. (라이브러리와 서비스에는 `Main` 메서드가 진입점으로 필요하지 않습니다.) 애플리케이션이 시작될 때 `Main` 메서드는 호출되는 첫 번째 메서드입니다.

 C# 프로그램에는 하나의 진입점만 있을 수 있습니다. `Main` 메서드가 있는 클래스가 둘 이상 있는 경우 **/main** 컴파일러 옵션으로 프로그램을 컴파일하여 진입점으로 사용할 `Main` 메서드를 지정해야 합니다. 자세한 내용은 [-main(C# 컴파일러 옵션)](../../language-reference/compiler-options/main-compiler-option.md)을 참조하세요.

[!code-csharp[csProgGuideMain#17](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideMain/CS/Class1.cs#17)]

## <a name="overview"></a>개요

- `Main` 메서드는 실행 가능한 프로그램의 진입점으로, 프로그램의 제어가 시작되고 끝나는 위치합니다.
- `Main`은 클래스 또는 구조체 내부에 선언됩니다 `Main`은 [static](../../language-reference/keywords/static.md)이어야 하며 [public](../../language-reference/keywords/public.md)일 필요가 없습니다. (앞의 예제에서는 기본 액세스 한정자인 [private](../../language-reference/keywords/private.md)으로 지정됩니다.) `Main`을 포함하는 클래스 또는 구조체는 정적일 필요가 없습니다.
- `Main`은 `void` 또는 `int`를 반환 형식으로 가질 수 있으며 C# 7.1 부터는 `Task` 또는 `Task<int>` 반환 형식을 가질 수 있습니다.
- `Main`에서 `Task` 또는 `Task<int>`을 반환하는 경우에만 `Main` 선언에 [`async`](../../language-reference/keywords/async.md) 한정자가 포함될 수 있습니다. 이는 구체적으로 `async void Main` 메서드를 제외합니다.
- `Main` 메서드는 명령줄 인수를 포함하는 `string[]` 매개 변수 사용 여부에 관계 없이 선언될 수 있습니다. Visual Studio를 사용하여 Windows 애플리케이션을 만드는 경우 매개 변수를 수동으로 추가하거나 <xref:System.Environment.GetCommandLineArgs> 메서드를 사용하여 [명령줄 인수](command-line-arguments.md)를 가져올 수 있습니다. 매개 변수는 0부터 시작하는 명령줄 인수로 읽힙니다. C 및 C++와 달리, 프로그램의 이름이 `args` 배열의 첫 번째 명령줄 인수로 처리되지 않지만, <xref:System.Environment.GetCommandLineArgs> 메서드의 첫 번째 요소입니다.

다음은 유효한 `Main` 시그니처 목록입니다.

```csharp
public static void Main() { }
public static int Main() { }
public static void Main(string[] args) { }
public static int Main(string[] args) { }
public static async Task Main() { }
public static async Task<int> Main() { }
public static async Task Main(string[] args) { }
public static async Task<int> Main(string[] args) { }
```

앞의 예에서는 모두 `public` 액세스 한정자를 사용합니다. 일반적으로 그렇게 하지만 필수는 아닙니다.

`async` 및 `Task`, `Task<int>` 반환 형식을 추가하면 콘솔 애플리케이션을 시작해야 하고 비동기 작업을 `Main`에서 `await`해야 하는 경우에 프로그램 코드가 간소화됩니다.

## <a name="c-language-specification"></a>C# 언어 사양

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a>참조

- [csc.exe를 사용한 명령줄 빌드](../../language-reference/compiler-options/command-line-building-with-csc-exe.md)
- [C# 프로그래밍 가이드](../index.md)
- [메서드](../classes-and-structs/methods.md)
- [C# 프로그램 내부](../inside-a-program/index.md)
