---
title: 명령줄 인수 - C# 프로그래밍 가이드
description: 명령줄 인수에 대해 알아봅니다. 콘솔 애플리케이션에서 명령줄 인수를 사용하는 예제를 살펴봅니다.
ms.date: 03/11/2021
helpviewer_keywords:
- command-line arguments [C#]
ms.assetid: 0e597e0d-ea7a-41ba-a38a-0198122f3c26
ms.openlocfilehash: f495efb3bc2c76a98f74c173d5b777ebe383edcb
ms.sourcegitcommit: e3cf8227573e13b8e1f4e3dc007404881cdafe47
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/11/2021
ms.locfileid: "103190413"
---
# <a name="command-line-arguments-c-programming-guide"></a>명령줄 인수(C# 프로그래밍 가이드)

다음 방법 중 하나로 메서드를 정의하여 인수를 `Main` 메서드에 보낼 수 있습니다.

| `Main` 메서드 코드                 | `Main` 서명                             |
|------------------------------------|----------------------------------------------|
| 반환 값 없음, `await` 사용 없음 | `static void Main(string[] args)`            |
| 반환 값, `await` 사용 없음    | `static int Main(string[] args)`             |
| 반환 값 없음, `await` 사용      | `static async Task Main(string[] args)`      |
| 반환 값, `await` 사용         | `static async Task<int> Main(string[] args)` |

인수가 사용되지 않는 경우 약간 더 간단한 코드를 위해 메서드 서명에서 `args`를 생략할 수 있습니다.

| `Main` 메서드 코드                 | `Main` 서명                |
|------------------------------------|---------------------------------|
| 반환 값 없음, `await` 사용 없음 | `static void Main()`            |
| 반환 값, `await` 사용 없음    | `static int Main()`             |
| 반환 값 없음, `await` 사용      | `static async Task Main()`      |
| 반환 값, `await` 사용         | `static async Task<int> Main()` |

> [!NOTE]
> Windows Forms 애플리케이션의 `Main` 메서드에서 명령줄 인수를 사용하도록 설정하려면 *program.cs* 에서 `Main`의 시그니처를 수동으로 수정해야 합니다. Windows Forms 디자이너에서 생성된 코드는 입력 매개 변수 없이 `Main`을 만듭니다. <xref:System.Environment.CommandLine%2A?displayProperty=nameWithType> 또는 <xref:System.Environment.GetCommandLineArgs%2A?displayProperty=nameWithType>를 사용하여 콘솔 또는 Windows 애플리케이션의 임의 지점에서 명령줄 인수에 액세스할 수 있습니다.

`Main` 메서드의 매개 변수는 명령줄 인수를 나타내는 <xref:System.String> 배열입니다. 일반적으로 다음과 같이 `Length` 속성을 테스트하여 인수가 있는지 확인합니다.

[!code-csharp[csProgGuideMain#4](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideMain/CS/Class3.cs#4)]

> [!TIP]
> `args` 배열은 null일 수 없습니다. 따라서 null 검사 없이 `Length` 속성에 액세스하는 것이 안전합니다.

<xref:System.Convert> 클래스 또는 `Parse` 메서드를 사용하여 문자열 인수를 숫자 형식으로 변환할 수도 있습니다. 예를 들어 다음 문은 <xref:System.Int64.Parse%2A> 메서드를 사용하여 `string`을 `long` 숫자로 변환합니다.

```csharp
long num = Int64.Parse(args[0]);
```

`Int64`의 별칭을 지정하는 C# 형식 `long`을 사용할 수도 있습니다.

```csharp
long num = long.Parse(args[0]);
```

`Convert` 클래스 메서드 `ToInt64`를 사용하여 같은 작업을 수행할 수도 있습니다.

```csharp
long num = Convert.ToInt64(s);
```

자세한 내용은 <xref:System.Int64.Parse%2A> 및 <xref:System.Convert>를 참조하세요.

## <a name="example"></a>예제

다음 예제에서는 콘솔 애플리케이션에서 명령줄 인수를 사용하는 방법을 보여 줍니다. 애플리케이션은 런타임에 하나의 인수를 사용하고, 인수를 정수로 변환하고, 숫자의 계승을 계산합니다. 인수가 제공되지 않으면 애플리케이션에서는 프로그램의 올바른 사용법을 설명하는 메시지를 표시합니다.

명령 프롬프트에서 애플리케이션을 컴파일 및 실행하려면 다음 단계를 수행합니다.

1. 다음 코드를 텍스트 편집기에 붙여넣고 이름 *Factorial.cs* 를 사용하여 파일을 텍스트 파일로 저장합니다.

     [!code-csharp[csProgGuideMain#16](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideMain/CS/Class1.cs#16)]

2. **시작** 화면이나 **시작** 메뉴에서 Visual Studio **개발자 명령 프롬프트** 창을 열고 방금 만든 파일이 포함된 폴더로 이동합니다.

3. 다음 명령을 입력하여 애플리케이션을 컴파일합니다.
  
     `csc Factorial.cs`  
  
     애플리케이션에 컴파일 오류가 없으면 *Factorial.exe* 라는 실행 파일이 만들어집니다.
  
4. 다음 명령을 입력하여 3의 계승을 계산합니다.
  
     `Factorial 3`  
  
5. 이 명령은 다음 출력을 생성합니다. `The factorial of 3 is 6.`

> [!NOTE]
> Visual Studio에서 애플리케이션을 실행할 경우 [프로젝트 디자이너, 디버그 페이지](/visualstudio/ide/reference/debug-page-project-designer)에서 명령줄 인수를 지정할 수 있습니다.

## <a name="see-also"></a>참조

- <xref:System.Environment?displayProperty=nameWithType>
- [C# 프로그래밍 가이드](../index.md)
- [Main()과 명령줄 인수](index.md)
- [명령줄 인수를 표시하는 방법](how-to-display-command-line-arguments.md)
- [Main() 반환 값](main-return-values.md)
- [클래스](../classes-and-structs/classes.md)
