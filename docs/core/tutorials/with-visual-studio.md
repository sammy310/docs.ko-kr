---
title: Visual Studio를 사용하여 .NET 콘솔 애플리케이션 만들기
description: Visual Studio를 사용하여 C# 또는 Visual Basic으로 .NET 콘솔 애플리케이션을 만드는 방법을 알아봅니다.
ms.date: 06/08/2020
dev_langs:
- csharp
- vb
ms.custom: vs-dotnet
ms.openlocfilehash: 3986ef4083b964799be33d2876570ac4cf2082b8
ms.sourcegitcommit: 1d3af230ec30d8d061be7a887f6ba38a530c4ece
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/09/2021
ms.locfileid: "102511855"
---
# <a name="tutorial-create-a-net-console-application-using-visual-studio"></a>자습서: Visual Studio를 사용하여 .NET 콘솔 애플리케이션 만들기

이 자습서에서는 Visual Studio 2019에서 .NET 콘솔 애플리케이션을 만들고 실행하는 방법을 보여 줍니다.

## <a name="prerequisites"></a>사전 요구 사항

- **.NET Core 플랫폼 간 개발** 워크로드가 설치된 [Visual Studio 2019 버전 16.8 이상](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019). 이 워크로드를 선택하면 .NET 5.0 SDK가 자동으로 설치됩니다.

  자세한 내용은 [Visual Studio로 .NET SDK 설치](../install/windows.md#install-with-visual-studio)를 참조하세요.

## <a name="create-the-app"></a>앱 만들기

“HelloWorld”라는 .NET 콘솔 앱 프로젝트를 만듭니다.

1. Visual Studio 2019를 시작합니다.

1. **도구** > **옵션** > **환경** > **미리 보기 기능** 을 선택하고 **새 프로젝트에 모든 .NET Core 템플릿 표시(다시 시작해야 함)** 를 선택합니다.

   :::image type="content" source="media/with-visual-studio/dotnet-options.png" alt-text="모든 .NET 템플릿 표시 옵션":::

1. Visual Studio를 닫았다가 다시 엽니다.

1. 시작 페이지에서 **새 프로젝트 만들기** 를 선택합니다.

   :::image type="content" source="./media/with-visual-studio/start-window.png" alt-text="Visual Studio 시작 페이지에서 새 프로젝트 만들기 단추 선택":::

1. **새 프로젝트 만들기** 페이지의 검색 상자에 **console** 을 입력합니다. 다음으로 언어 목록에서 **C#** 또는 **Visual Basic** 을 선택한 다음 플랫폼 목록에서 **모든 플랫폼** 을 선택합니다. **콘솔 애플리케이션** 템플릿을 선택한 후 **다음** 을 선택합니다.

   :::image type="content" source="./media/with-visual-studio/create-new-project.png" alt-text="필터가 선택된 새 프로젝트 만들기 창":::

   > [!TIP]
   > .NET 템플릿이 표시되지 않으면 필요한 워크로드가 없을 수 있습니다. **원하는 항목을 찾을 수 없나요?** 메시지에서 **추가 도구 및 기능 설치** 링크를 선택합니다. Visual Studio 설치 관리자가 열립니다. **.NET Core 플랫폼 간 개발** 워크로드가 설치되어 있어야 합니다.

1. **새 프로젝트 구성** 대화 상자에서 **프로젝트 이름** 상자에 **HelloWorld** 를 입력합니다. 그리고 **다음** 을 선택합니다.

   :::image type="content" source="./media/with-visual-studio/configure-new-project.png" alt-text="프로젝트 이름, 위치 및 솔루션 이름 필드를 사용하여 새 프로젝트 창을 구성합니다.":::

1. **추가 정보** 대화 상자에서 **.NET 5.0(현재)** 을 선택한 후 **만들기** 를 선택합니다.

   :::image type="content" source="media/with-visual-studio/additional-info.png" alt-text="추가 정보 대화 상자":::

템플릿은 간단한 "Hello World" 애플리케이션을 만듭니다. <xref:System.Console.WriteLine(System.String)?displayProperty=nameWithType> 메서드를 호출하여 "Hello World!"를 콘솔 창에 표시합니다.

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

```vb
Imports System

Module Program
    Sub Main(args As String())
        Console.WriteLine("Hello World!")
    End Sub
End Module
```

`Main`은 애플리케이션 진입점으로, 애플리케이션을 시작할 때 런타임에 의해 자동으로 호출되는 메서드입니다. 애플리케이션이 시작될 때 제공되는 모든 명령줄 인수는 *args* 배열에서 사용할 수 있습니다.

사용하려는 언어가 표시되지 않으면 페이지 맨 위에 있는 언어 선택기를 변경합니다.

## <a name="run-the-app"></a>앱 실행

1. <kbd>Ctrl</kbd>+<kbd>F5</kbd>를 눌러 디버깅 없이 프로그램을 실행합니다.

   콘솔 창이 열리고 "Hello World!"라는 텍스트가 화면에 출력되었습니다.

   :::image type="content" source="./media/with-visual-studio/hello-world-console.png" alt-text="“Hello World 계속하려면 아무 키나 누르세요.”를 표시하는 콘솔 창":::

1. 콘솔 창을 닫으려면 아무 키나 누릅니다.

## <a name="enhance-the-app"></a>앱 향상

사용자에게 이름을 입력하라는 메시지를 표시한 다음 사용자 이름을 날짜 및 시간과 함께 표시하도록 애플리케이션을 개선합니다.

1. *Program.cs* 또는 *Program.vb* 에서 다음 코드로 `Console.WriteLine`를 호출하는 줄인 `Main` 메서드의 내용을 바꿉니다.

   :::code language="csharp" source="./snippets/with-visual-studio/csharp/Program.cs" id="MainMethod":::
   :::code language="vb" source="./snippets/with-visual-studio/vb/Program.vb" id="MainMethod":::

   해당 코드는 콘솔 창에 프롬프트를 표시하고 사용자가 문자열을 입력한 후 <kbd>Enter</kbd> 키를 누를 때까지 기다립니다. 이 문자열을 `name`이라는 변수에 저장합니다. 또한 현재 현지 시간을 포함하는 <xref:System.DateTime.Now?displayProperty=nameWithType> 속성 값을 검색한 후 `date`라는 변수(Visual Basic에서는 `currentDate`)에 할당합니다. 또한 콘솔 창에 해당 값을 표시합니다. 마지막으로 콘솔 창에 프롬프트를 표시하고 <xref:System.Console.ReadKey(System.Boolean)?displayProperty=nameWithType> 메서드를 호출하여 사용자 입력을 기다립니다.

   <xref:System.Environment.NewLine>은 줄 바꿈을 나타내는 플랫폼과 언어에 독립적인 방법입니다. 대안은 C#의 `\n` 및 Visual Basic의 `vbCrLf`입니다.

   문자열 앞의 달러 기호(`$`)를 사용하면 변수 이름과 같은 식을 문자열의 중괄호 안에 넣을 수 있습니다. 식 값은 식 대신 문자열에 삽입됩니다. 이 구문을 [보간된 문자열](../../csharp/language-reference/tokens/interpolated.md)이라고 합니다.

1. <kbd>Ctrl</kbd>+<kbd>F5</kbd>를 눌러 디버깅 없이 프로그램을 실행합니다.

1. 이름을 입력하고 <kbd>Enter</kbd> 키를 눌러 프롬프트에 응답합니다.

   :::image type="content" source="./media/with-visual-studio/hello-world-update.png" alt-text="수정된 프로그램 출력이 표시된 콘솔 창":::

1. 콘솔 창을 닫으려면 아무 키나 누릅니다.

## <a name="additional-resources"></a>추가 리소스

- [현재 릴리스 및 장기 지원 릴리스](../releases-and-support.md#net-core-and-net-5-version-lifecycles)

## <a name="next-steps"></a>다음 단계

이 자습서에서는 .NET 콘솔 애플리케이션을 만들었습니다. 다음 자습서에서는 앱을 디버그합니다.

> [!div class="nextstepaction"]
> [Visual Studio를 사용하여 .NET 콘솔 애플리케이션 디버그](debugging-with-visual-studio.md)
