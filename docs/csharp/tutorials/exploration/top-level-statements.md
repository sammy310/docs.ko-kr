---
title: 최상위 문 - C# 자습서
description: 이 자습서에서는 아이디어를 탐색하는 동안 최상위 문을 사용하여 개념을 실험하고 증명하는 방법을 보여 줍니다.
ms.date: 10/28/2020
ms.openlocfilehash: 210fbd83bf4677061cab303089d0b27f1a4a7d01
ms.sourcegitcommit: 7588b1f16b7608bc6833c05f91ae670c22ef56f8
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/02/2020
ms.locfileid: "93189369"
---
# <a name="tutorial-explore-ideas-using-top-level-statements-to-build-code-as-you-learn"></a>자습서: 배우는 동안 최상위 문을 사용하여 코드를 빌드하는 아이디어 탐색

이 자습서에서 학습할 방법은 다음과 같습니다.

> [!div class="checklist"]
>
> - 최상위 문 사용을 제어하는 규칙을 알아봅니다.
> - 최상위 문을 사용하여 알고리즘을 탐색합니다.
> - 탐색을 재사용 가능한 구성 요소로 리팩터링합니다.

## <a name="prerequisites"></a>사전 요구 사항

C# 9 컴파일러를 포함하는 .NET 5를 실행하도록 머신을 설정해야 합니다. C# 9 컴파일러는 [Visual Studio 2019 버전 16.9 미리 보기 1](https://visualstudio.microsoft.com/vs/preview/) 또는 [.NET 5.0 SDK](https://dot.net/get-dotnet5)부터 사용할 수 있습니다.

이 자습서에서는 Visual Studio 또는 .NET Core CLI를 포함하여 C# 및 .NET에 익숙하다고 가정합니다.

## <a name="start-exploring"></a>다양한 콘텐츠 살펴보기

최상위 문을 사용하면 프로그램의 진입점을 클래스의 정적 메서드에 배치하여 필요한 추가 공식 절차를 방지할 수 있습니다. 새 콘솔 애플리케이션의 일반적인 시작점은 다음 코드와 같습니다.

```csharp
using System;

namespace Application
{
    class Program
    {
        static void Main(string[] args)
        {
            Console.WriteLine("Hello World!");
        }
    }
}
```

위 코드는 `dotnet new console` 명령을 실행하고 새 콘솔 애플리케이션을 만든 결과입니다. 11줄의 코드에 단 한 줄의 실행 코드가 포함됩니다. 새 최상위 문 기능을 사용하여 해당 프로그램을 단순화할 수 있습니다. 이렇게 하면 해당 프로그램에서 두 개 줄을 제외한 모든 줄을 제거할 수 있습니다.

```csharp
using System;

Console.WriteLine("Hello World!");
```

이 작업은 새로운 아이디어 탐색을 시작하는 데 필요한 작업을 간소화합니다. 스크립팅 시나리오에서 또는 탐색하는 데 최상위 문을 사용할 수 있습니다. 적용되는 기본 사항을 확인한 후 코드의 리팩터링을 시작하고 빌드한 재사용 가능 구성 요소의 메서드, 클래스 또는 기타 어셈블리를 만들 수 있습니다. 최상위 문은 빠른 실험 및 초보자 자습서를 가능하게 합니다. 또한 실험에서 전체 프로그램까지 원활한 경로를 제공합니다.

최상위 문은 파일에 표시된 순서대로 실행됩니다. 최상위 문은 애플리케이션의 한 소스 파일에만 사용할 수 있습니다. 둘 이상의 파일에서 사용하는 경우 컴파일러에서 오류를 생성합니다.

## <a name="build-a-magic-net-answer-machine"></a>매직 .NET 응답 머신 빌드

이 자습서에서는 임의 응답을 사용하여 “예” 또는 “아니요” 질문에 대답하는 콘솔 애플리케이션을 빌드해 보겠습니다. 기능을 단계별로 빌드합니다. 일반적인 프로그램의 구조에 필요한 공식 절차가 아닌 작업에 집중할 수 있습니다. 그런 다음, 기능에 만족하면 필요한 경우 애플리케이션을 리팩터링할 수 있습니다.

좋은 시작점은 질문을 다시 콘솔에 쓰는 것입니다. 먼저 다음 코드를 작성할 수 있습니다.

```csharp
using System;

Console.WriteLine(args);
```

`args` 변수를 선언하지 않습니다. 최상위 문이 포함된 단일 소스 파일의 경우 컴파일러는 명령줄 인수를 의미하는 `args`를 인식합니다. 인수 형식은 모든 C# 프로그램과 같이 `string[]`입니다.

다음 `dotnet run` 명령을 실행하여 코드를 테스트할 수 있습니다.

```dotnetcli
dotnet run -- Should I use top level statements in all my programs?
```

명령줄에 있는 `--` 뒤의 인수는 프로그램에 전달됩니다. 콘솔에 인쇄된 항목인 `args` 변수 형식을 확인할 수 있습니다.

```console
System.String[]
```

콘솔에 질문을 쓰려면 인수를 열거하고 공백으로 구분해야 합니다. `WriteLine` 호출을 다음 코드로 바꿉니다.

:::code language="csharp" source="snippets/top-level-statements/Program.cs" ID="EchoInput":::

이제 프로그램을 실행하면 질문을 인수 문자열로 올바르게 표시합니다.

## <a name="respond-with-a-random-answer"></a>임의 응답으로 응답

질문을 에코한 후에는 임의 응답을 생성하는 코드를 추가할 수 있습니다. 먼저 가능한 응답의 배열을 추가합니다.

:::code language="csharp" source="snippets/top-level-statements/Program.cs" ID="Answers":::

이 배열에는 긍정 응답 12개, 커밋이 아닌 응답 6개, 부정 응답 6개가 있습니다. 다음으로, 다음 코드를 추가하여 배열에서 임의 응답을 생성하고 표시합니다.

:::code language="csharp" source="snippets/top-level-statements/Program.cs" ID="GenerateAnswer":::

애플리케이션을 다시 실행하여 결과를 볼 수 있습니다. 다음 출력과 같은 정보가 표시됩니다.

```dotnetcli
dotnet run -- Should I use top level statements in all my programs?

Should I use top level statements in all my programs?
Better not tell you now.
```

이 코드는 질문에 응답하지만 기능을 하나 더 추가하겠습니다. 질문 앱에서 응답에 관한 생각을 시뮬레이트하려고 합니다. 이렇게 하려면 약간의 ASCII 애니메이션을 추가하고 작동 중에 일시 중지합니다.  질문을 에코하는 줄 뒤에 다음 코드를 추가합니다.

:::code language="csharp" source="snippets/top-level-statements/UtilitiesPassOne.cs" ID="AnimationFirstPass":::

또한 소스 파일의 맨 위에 `using` 문을 추가해야 합니다.

```csharp
using System.Threading.Tasks;
```

`using` 문은 파일의 다른 문 앞에 있어야 합니다. 그렇지 않으면 컴파일러 오류가 발생합니다. 프로그램을 다시 실행하여 애니메이션을 확인할 수 있습니다. 이를 통해 더 나은 환경을 제공할 수 있습니다. 원하는 대로 지연 길이를 실험합니다.

앞의 코드는 공백으로 구분된 회전하는 선 세트를 만듭니다. `await` 키워드를 추가하면 컴파일러가 프로그램 진입점을 `async` 한정자가 있는 메서드로 생성하고 <xref:System.Threading.Tasks.Task?displayProperty=nameWithType>를 반환하도록 지시합니다. 이 프로그램은 값을 반환하지 않으므로 프로그램 진입점이 `Task`를 반환합니다. 프로그램이 정수 값을 반환하는 경우 최상위 문의 끝에 return 문을 추가합니다. return 문은 반환할 정수 값을 지정합니다. 최상위 문에 `await` 식이 포함된 경우 반환 형식은 <xref:System.Threading.Tasks.Task%601?displayProperty=nameWithType>이 됩니다.

## <a name="refactoring-for-the-future"></a>미래를 위한 리팩터링

프로그램은 다음 코드와 같이 표시됩니다.

```csharp
using System;
using System.Threading.Tasks;

Console.WriteLine();
foreach(var s in args)
{
    Console.Write(s);
    Console.Write(' ');
}
Console.WriteLine();

for (int i = 0; i < 20; i++)
{
    Console.Write("| -");
    await Task.Delay(50);
    Console.Write("\b\b\b");
    Console.Write("/ \\");
    await Task.Delay(50);
    Console.Write("\b\b\b");
    Console.Write("- |");
    await Task.Delay(50);
    Console.Write("\b\b\b");
    Console.Write("\\ /");
    await Task.Delay(50);
    Console.Write("\b\b\b");
}
Console.WriteLine();

string[] answers =
{
    "It is certain.",       "Reply hazy, try again.",     "Don’t count on it.",
    "It is decidedly so.",  "Ask again later.",           "My reply is no.",
    "Without a doubt.",     "Better not tell you now.",   "My sources say no.",
    "Yes – definitely.",    "Cannot predict now.",        "Outlook not so good.",
    "You may rely on it.",  "Concentrate and ask again.", "Very doubtful.",
    "As I see it, yes.",
    "Most likely.",
    "Outlook good.",
    "Yes.",
    "Signs point to yes.",
};

var index = new Random().Next(answers.Length - 1);
Console.WriteLine(answers[index]);
```

앞의 코드는 적절합니다. 예상대로 작동합니다. 하지만 재사용할 수 없습니다. 이제 애플리케이션이 작동하고 있으므로 재사용 가능한 부분을 가져오겠습니다.

한 후보는 대기 중인 애니메이션을 표시하는 코드입니다. 해당 코드 조각은 메서드가 될 수 있습니다.

먼저 파일에서 로컬 함수를 만들 수 있습니다. 현재 애니메이션을 다음 코드로 바꿉니다.

```csharp
await ShowConsoleAnimation();

static async Task ShowConsoleAnimation()
{
    for (int i = 0; i < 20; i++)
    {
        Console.Write("| -");
        await Task.Delay(50);
        Console.Write("\b\b\b");
        Console.Write("/ \\");
        await Task.Delay(50);
        Console.Write("\b\b\b");
        Console.Write("- |");
        await Task.Delay(50);
        Console.Write("\b\b\b");
        Console.Write("\\ /");
        await Task.Delay(50);
        Console.Write("\b\b\b");
    }
    Console.WriteLine();
}
```

앞의 코드는 main 메서드 내에 로컬 함수를 만듭니다. 그래도 재사용할 수 없습니다. 따라서 해당 코드를 클래스로 추출합니다. *utilities.cs* 라는 새 파일을 만들고 다음 코드를 추가합니다.

:::code language="csharp" source="snippets/top-level-statements/UtilitiesPassOne.cs" ID="SnippetUtilities":::

최상위 문은 한 파일에만 있을 수 있으며, 해당 파일은 네임스페이스나 형식을 포함할 수 없습니다.

마지막으로, 애니메이션 코드를 정리하여 일부 중복을 제거할 수 있습니다.

:::code language="csharp" source="snippets/top-level-statements/Utiliities.cs" ID="Animation":::

이제 전체 애플리케이션이 있으며 나중에 사용할 수 있도록 재사용 가능한 부분을 리팩터링했습니다.

## <a name="summary"></a>요약

최상위 문을 사용하면 새 알고리즘을 탐색하는 데 사용할 간단한 프로그램을 더 쉽게 만들 수 있습니다. 코드의 다른 조각을 시도하여 알고리즘을 실험할 수 있습니다. 작동 기능을 알아본 후에는 코드를 더 쉽게 유지 관리할 수 있도록 리팩터링할 수 있습니다.

최상위 문은 콘솔 애플리케이션을 기반으로 하는 프로그램을 단순화합니다. 여기에는 Azure Functions, GitHub Actions, 기타 작은 유틸리티가 포함됩니다.
