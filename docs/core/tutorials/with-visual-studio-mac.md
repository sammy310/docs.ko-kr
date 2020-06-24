---
title: Mac용 Visual Studio를 사용하여 .NET Core 콘솔 애플리케이션 만들기
description: Mac용 Visual Studio를 사용하여 .NET Core 콘솔 애플리케이션을 만드는 방법을 알아봅니다.
ms.date: 06/02/2020
ms.openlocfilehash: 57f16e510270b7256b285493b1f978101fc11804
ms.sourcegitcommit: f6350c2c542e6edd52d7e9d6667b96d85d810e67
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/11/2020
ms.locfileid: "84717525"
---
# <a name="tutorial-create-a-net-core-console-application-using-visual-studio-for-mac"></a>자습서: Mac용 Visual Studio를 사용하여 .NET Core 콘솔 애플리케이션 만들기

이 자습서에서는 Mac용 Visual Studio를 사용하여 .NET Core 콘솔 애플리케이션을 만들고 실행하는 방법을 보여 줍니다.

> [!NOTE]
> 사용자 의견은 매우 중요합니다. Mac용 Visual Studio의 개발 팀에 다음 두 가지 방법으로 의견을 제공할 수 있습니다.
>
> * Mac용 Visual Studio의 메뉴에서 **도움말** > **문제 보고**를 선택하거나 시작 화면에서 **문제 보고**를 선택하면 버그 보고서를 작성하기 위한 창이 열립니다. [Developer Community](https://developercommunity.visualstudio.com/spaces/8/index.html)(개발자 커뮤니티) 포털에서 의견을 추적할 수 있습니다.
> * 제안하려면 메뉴에서 **도움말** > **제안하기**를 선택하거나 시작 화면에서 **제안하기**를 선택합니다. 그러면 [Mac용 Visual Studio Developer Community 웹 페이지](https://developercommunity.visualstudio.com/content/idea/post.html?space=41)로 이동됩니다.

## <a name="prerequisites"></a>사전 요구 사항

* [Mac용 Visual Studio 버전 8.6 이상](https://visualstudio.microsoft.com/vs/mac/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link). .NET Core 설치 옵션을 선택합니다. Xamarin의 설치는 .NET Core 개발에서 선택 사항입니다. 자세한 내용은 다음 자료를 참조하세요.

  * [자습서: Mac용 Visual Studio](/visualstudio/mac/installation)를 설치합니다.
  * [지원되는 macOS 버전](../install/dependencies.md?pivots=os-macos).
  * [Mac용 Visual Studio에서 지원되는 .NET Core 버전](/visualstudio/mac/net-core-support).

## <a name="create-the-app"></a>앱 만들기

"HelloWorld"라는 .NET Core 콘솔 앱 프로젝트를 만듭니다.

1. Mac용 Visual Studio를 시작합니다.

1. 시작 창에서 **새로 만들기**를 선택합니다.

   :::image type="content" source="media/with-visual-studio-mac/visual-studio-mac-new-project.png" alt-text="Mac용 Visual Studio 시작 화면의 새로 만들기 버튼":::

1. **새 프로젝트** 대화 상자에서 **웹 및 콘솔** 노드 아래에서 **앱**을 선택합니다. **콘솔 애플리케이션** 템플릿을 선택하고 **다음**을 선택합니다.

   :::image type="content" source="media/with-visual-studio-mac/visual-studio-mac-new-dialog.png" alt-text="새 프로젝트 템플릿 목록":::

1. **새 콘솔 애플리케이션 구성** 대화 상자의 **대상 프레임워크** 드롭다운에서 **.NET Core 3.1**을 선택하고 **다음**을 선택합니다.

   :::image type="content" source="media/with-visual-studio-mac/target-framework.png" alt-text="대상 프레임워크 선택":::

1. **프로젝트 이름**으로 "HelloWorld"를 입력하고 **만들기**를 선택합니다.

   :::image type="content" source="media/with-visual-studio-mac/visual-studio-mac-new-options.png" alt-text="새 콘솔 애플리케이션 대화 상자 구성":::

템플릿은 간단한 "Hello World" 애플리케이션을 만듭니다. <xref:System.Console.WriteLine(System.String)?displayProperty=nameWithType> 메서드를 호출하여 "Hello World!"를 터미널 창에서 표시합니다.

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

`Main`은 애플리케이션 진입점으로, 애플리케이션을 시작할 때 런타임에 의해 자동으로 호출되는 메서드입니다. 애플리케이션이 시작될 때 제공되는 모든 명령줄 인수는 `args` 배열에서 사용할 수 있습니다.

## <a name="run-the-app"></a>앱 실행

1. <kbd>⌥</kbd><kbd>⌘</kbd><kbd>↵</kbd> (<kbd>option</kbd>+<kbd>command</kbd>+<kbd>enter</kbd>)를 눌러 디버그 없이 앱을 실행합니다.

   :::image type="content" source="media/with-visual-studio-mac/visual-studio-mac-output.png" alt-text="Hello World!가 표시된 터미널":::

1. **터미널** 창을 닫습니다.

## <a name="enhance-the-app"></a>앱 향상

사용자에게 이름을 입력하라는 메시지를 표시한 다음 사용자 이름을 날짜 및 시간과 함께 표시하도록 애플리케이션을 개선합니다.

1. *Program.cs*에서 `Console.WriteLine`을 호출하는 줄인 `Main` 메서드의 내용을 다음 코드로 바꿉니다.

   :::code language="csharp" source="./snippets/with-visual-studio/csharp/Program.cs" id="1":::

   이 코드는 "What is your name?"을 콘솔 창에 표시하고 사용자가 문자열을 입력한 후 <kbd>Enter</kbd> 키를 누를 때까지 기다립니다. 이 문자열을 `name`이라는 변수에 저장합니다. 또한 현재 현지 시간을 포함하는 <xref:System.DateTime.Now?displayProperty=nameWithType> 속성 값을 검색한 후 `date`라는 변수에 할당합니다. 마지막으로 콘솔 창에 이러한 값을 표시합니다.

   `\n`은 줄 바꿈 문자를 나타냅니다.

   문자열 앞의 달러 기호(`$`)를 사용하면 변수 이름과 같은 식을 문자열의 중괄호 안에 넣을 수 있습니다. 식 값은 식 대신 문자열에 삽입됩니다. 이 구문을 [보간된 문자열](../../csharp/language-reference/tokens/interpolated.md)이라고 합니다.

1. <kbd>⌥</kbd><kbd>⌘</kbd><kbd>↵</kbd> (<kbd>option</kbd>+<kbd>command</kbd>+<kbd>enter</kbd>)를 눌러 앱을 실행합니다.

1. 이름을 입력하고 <kbd>Enter</kbd>를 눌러 프롬프트에 응답합니다.

   :::image type="content" source="media/with-visual-studio-mac/hello-world-update.png" alt-text="수정된 프로그램 출력이 표시된 터미널":::

1. 터미널을 닫습니다.

## <a name="next-steps"></a>다음 단계

이 자습서에서는 .NET Core 콘솔 애플리케이션을 만들었습니다. 다음 자습서에서는 앱을 디버그합니다.

> [!div class="nextstepaction"]
> [Visual Studio에서 .NET Core 콘솔 애플리케이션 디버그](debugging-with-visual-studio-mac.md)
