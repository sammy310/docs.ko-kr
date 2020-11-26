---
title: Visual Studio Code를 사용하여 .NET 콘솔 애플리케이션 만들기
description: Visual Studio Code와 .NET CLI를 사용하여 .NET 콘솔 애플리케이션을 만드는 방법을 알아봅니다.
ms.date: 11/17/2020
ms.openlocfilehash: dbbdf88b0c84089249eb7e446c25eddc11543c1a
ms.sourcegitcommit: 5114e7847e0ff8ddb8c266802d47af78567949cf
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/19/2020
ms.locfileid: "94915871"
---
# <a name="tutorial-create-a-net-console-application-using-visual-studio-code"></a>자습서: Visual Studio Code를 사용하여 .NET 콘솔 애플리케이션 만들기

이 자습서에서는 Visual Studio Code와 .NET CLI를 사용하여 .NET 콘솔 애플리케이션을 만들고 실행하는 방법을 보여 줍니다. 프로젝트 만들기, 컴파일, 실행과 같은 프로젝트 작업은 .NET CLI를 사용하여 수행합니다. 원할 경우, 다른 코드 편집기를 사용하여 이 자습서를 따르고 터미널에서 명령을 실행할 수 있습니다.

## <a name="prerequisites"></a>사전 요구 사항

1. [C# 확장](https://marketplace.visualstudio.com/items?itemName=ms-dotnettools.csharp)이 설치된 [Visual Studio Code](https://code.visualstudio.com/). Visual Studio Code에 확장을 설치하는 방법에 대한 자세한 내용은 [VS Code 확장 Marketplace](https://code.visualstudio.com/docs/editor/extension-gallery)를 참조하세요.
2. [.NET 5.0 SDK 이상](https://dotnet.microsoft.com/download)

## <a name="create-the-app"></a>앱 만들기

“HelloWorld”라는 .NET 콘솔 앱 프로젝트를 만듭니다.

1. Visual Studio Code를 시작합니다.

1. 주 메뉴에서 **파일** > **폴더 열기**(macOS에서는 **파일** > **열기...** )를 선택합니다.

1. **폴더 열기** 대화 상자에서 *HelloWorld* 폴더를 만들고 **폴더 선택**(macOS에서는 **열기**)을 클릭합니다.

   기본적으로 폴더 이름은 프로젝트 이름 및 네임스페이스 이름이 됩니다. 프로젝트 네임스페이스가 `HelloWorld`라고 가정하는 코드를 자습서의 뒷부분에 추가합니다.

1. 주 메뉴에서 **보기** > **터미널** 을 선택하여 Visual Studio Code에서 **터미널** 을 엽니다.

   *HelloWorld* 폴더에서 명령 프롬프트와 함께 **터미널** 이 열립니다.

1. **터미널** 에서 다음 명령을 입력합니다.

   ```dotnetcli
   dotnet new console
   ```

템플릿은 간단한 "Hello World" 애플리케이션을 만듭니다. <xref:System.Console.WriteLine(System.String)?displayProperty=nameWithType> 메서드를 호출하여 콘솔 창에 “:::no-loc text="Hello World!":::”를 표시합니다.

템플릿 코드는 <xref:System.String> 배열을 인수로 사용하는 단일 메서드 `Main`으로 `Program` 클래스를 정의합니다.

```csharp
using System;

namespace HelloWorld
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

`Main`은 애플리케이션 진입점으로, 애플리케이션을 시작할 때 런타임에 의해 자동으로 호출되는 메서드입니다. 애플리케이션이 시작될 때 제공되는 모든 명령줄 인수는 *args* 배열에서 사용할 수 있습니다.

## <a name="run-the-app"></a>앱 실행

**터미널** 에서 다음 명령을 실행합니다.

```dotnetcli
dotnet run
```

프로그램이 "Hello World!"를 표시하고 종료됩니다.

![dotnet run 명령](media/with-visual-studio-code/dotnet-run-command.png)

## <a name="enhance-the-app"></a>앱 향상

사용자에게 이름을 입력하라는 메시지를 표시한 다음 사용자 이름을 날짜 및 시간과 함께 표시하도록 애플리케이션을 개선합니다.

1. *Program.cs* 를 클릭하여 엽니다.

   Visual Studio Code에서 C# 파일을 처음 열면 [OmniSharp](https://www.omnisharp.net/)에서 편집기가 로드됩니다.

   ![Program.cs 파일 열기](media/with-visual-studio-code/open-program-cs.png)

1. Visual Studio Code가 앱을 빌드하고 디버그하기 위해 누락된 자산을 추가하라는 메시지를 표시하면 **예** 를 선택합니다.

   ![누락된 자산에 대한 프롬프트](media/with-visual-studio-code/missing-assets.png)

1. *Program.cs* 에서 `Console.WriteLine`을 호출하는 줄인 `Main` 메서드의 내용을 다음 코드로 바꿉니다.

   :::code language="csharp" source="./snippets/with-visual-studio/csharp/Program.cs" id="MainMethod":::

   해당 코드는 콘솔 창에 프롬프트를 표시하고 사용자가 문자열을 입력한 후 <kbd>Enter</kbd> 키를 누를 때까지 기다립니다. 이 문자열을 `name`이라는 변수에 저장합니다. 또한 현재 현지 시간을 포함하는 <xref:System.DateTime.Now?displayProperty=nameWithType> 속성 값을 검색한 후 `date`라는 변수에 할당합니다. 또한 콘솔 창에 해당 값을 표시합니다. 마지막으로 콘솔 창에 프롬프트를 표시하고 <xref:System.Console.ReadKey(System.Boolean)?displayProperty=nameWithType> 메서드를 호출하여 사용자 입력을 기다립니다.

   `\n`은 줄 바꿈 문자를 나타냅니다.

   문자열 앞의 달러 기호(`$`)를 사용하면 변수 이름과 같은 식을 문자열의 중괄호 안에 넣을 수 있습니다. 식 값은 식 대신 문자열에 삽입됩니다. 이 구문을 [보간된 문자열](../../csharp/language-reference/tokens/interpolated.md)이라고 합니다.

1. 변경 내용을 저장합니다.

   > [!IMPORTANT]
   > Visual Studio Code에서는 변경 내용을 명시적으로 저장해야 합니다. Visual Studio와 달리 애플리케이션을 빌드 및 실행할 때 파일 변경 내용이 자동으로 저장되지 않습니다.

1. 프로그램을 다시 실행합니다.

   ```dotnetcli
   dotnet run
   ```

1. 이름을 입력하고 <kbd>Enter</kbd> 키를 눌러 프롬프트에 응답합니다.

   :::image type="content" source="media/debugging-with-visual-studio-code/run-modified-program.png" alt-text="수정된 프로그램 출력이 표시된 터미널 창":::

1. 아무 키나 눌러 프로그램을 종료합니다.

## <a name="additional-resources"></a>추가 자료

- [Visual Studio Code 설치](https://code.visualstudio.com/docs/setup/setup-overview)

## <a name="next-steps"></a>다음 단계

이 자습서에서는 .NET 콘솔 애플리케이션을 만들었습니다. 다음 자습서에서는 앱을 디버그합니다.

> [!div class="nextstepaction"]
> [Visual Studio Code를 사용하여 .NET 콘솔 애플리케이션 디버그](debugging-with-visual-studio-code.md)
