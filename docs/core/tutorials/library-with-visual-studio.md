---
title: Visual Studio를 사용하여 .NET 클래스 라이브러리 만들기
description: Visual Studio를 사용하여 .NET 클래스 라이브러리를 만드는 방법을 알아봅니다.
ms.date: 08/07/2020
dev_langs:
- csharp
- vb
ms.custom: vs-dotnet,contperfq1
ms.openlocfilehash: 3af08b5a92c61f29a3700a3417043170f41407bc
ms.sourcegitcommit: 5114e7847e0ff8ddb8c266802d47af78567949cf
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/19/2020
ms.locfileid: "94916152"
---
# <a name="tutorial-create-a-net-class-library-using-visual-studio"></a>자습서: Visual Studio를 사용하여 .NET 클래스 라이브러리 만들기

이 자습서에서는 단일 문자열 처리 메서드를 포함하는 간단한 클래스 라이브러리를 만듭니다.

*클래스 라이브러리* 는 애플리케이션에서 호출되는 형식 및 메서드를 정의합니다. 라이브러리가 .NET Standard 2.0을 대상으로 하는 경우 .NET Standard 2.0을 지원하는 .NET 구현(.NET Framework 포함)에서 호출될 수 있습니다. 라이브러리가 .NET 5를 대상으로 하는 경우 .NET 5를 대상으로 하는 모든 애플리케이션에서 호출될 수 있습니다. 이 자습서에서는 .NET 5를 대상으로 지정하는 방법을 보여 줍니다.

클래스 라이브러리를 만들 때 NuGet 패키지 또는 라이브러리를 사용하는 애플리케이션이 포함된 번들 구성 요소로 배포할 수 있습니다.

## <a name="prerequisites"></a>사전 요구 사항

- **.NET Core 플랫폼 간 개발** 워크로드가 설치된 [Visual Studio 2019 버전 16.8 이상](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019). 이 워크로드를 선택하면 .NET 5.0 SDK가 자동으로 설치됩니다. 이 자습서에서는 **새 프로젝트에 모든 .NET Core 템플릿 표시** 를 사용하도록 설정한 것으로 가정하며, 이 옵션은 [자습서: Visual Studio를 사용하여 .NET 콘솔 애플리케이션 만들기](with-visual-studio.md)에 설명되어 있습니다.

## <a name="create-a-solution"></a>솔루션 만들기

먼저 클래스 라이브러리 프로젝트를 배치할 빈 솔루션을 만듭니다. Visual Studio 솔루션은 하나 이상의 프로젝트에 대한 컨테이너로 작동합니다. 동일한 솔루션에 관련 프로젝트를 추가합니다.

빈 솔루션을 만들려면 다음을 수행합니다.

1. Visual Studio를 시작합니다.

2. 시작 창에서 **새 프로젝트 만들기** 를 선택합니다.

3. **새 프로젝트 만들기** 페이지의 검색 상자에 **solution** 을 입력합니다. **빈 솔루션** 템플릿을 선택한 후, **다음** 을 선택합니다.

   :::image type="content" source="media/library-with-visual-studio/blank-solution.png" alt-text="Visual Studio의 빈 솔루션 템플릿":::

4. **새 프로젝트 구성** 페이지에서 **프로젝트 이름** 상자에 **ClassLibraryProjects** 를 입력합니다. 그런 다음, **만들기** 를 선택합니다.

## <a name="create-a-class-library-project"></a>클래스 라이브러리 프로젝트 만들기

1. “StringLibrary”라는 새로운 .NET 클래스 라이브러리 프로젝트를 솔루션에 추가합니다.

   1. **솔루션 탐색기** 에서 솔루션을 마우스 오른쪽 단추로 클릭하고 **추가** > **새 프로젝트** 를 선택합니다.

   1. **새 프로젝트 추가** 페이지의 검색 상자에 **library** 를 입력합니다. 언어 목록에서 **C#** 또는 **Visual Basic** 을 선택한 다음, 플랫폼 목록에서 **모든 플랫폼** 을 선택합니다. **클래스 라이브러리** 템플릿을 선택한 후 **다음** 을 선택합니다.

   1. **새 프로젝트 구성** 페이지에서 **프로젝트 이름** 상자에 **StringLibrary** 를 입력한 후 **다음** 을 선택합니다.

   1. **추가 정보** 페이지에서 **.NET 5.0(현재)** 을 선택한 후 **만들기** 를 선택합니다.

1. 라이브러리에 올바른 버전의 .NET이 대상으로 지정되었는지 확인합니다. **솔루션 탐색기** 에서 라이브러리 프로젝트를 마우스 오른쪽 단추로 클릭한 다음, **속성** 을 선택합니다. **대상 프레임워크** 텍스트 상자에 프로젝트가 .NET 5.0을 대상으로 한다는 것이 표시됩니다.

1. Visual Basic을 사용하는 경우 **루트 네임스페이스** 텍스트 상자의 텍스트를 지웁니다.

   :::image type="content" source="./media/library-with-visual-studio/vb/library-project-properties.png" alt-text="클래스 라이브러리에 대한 프로젝트 속성":::

   각 프로젝트에 대해 Visual Basic에서는 프로젝트 이름에 해당하는 네임스페이스를 자동으로 만듭니다. 이 자습서에서는 코드 파일의 [`namespace`](../../visual-basic/language-reference/statements/namespace-statement.md) 키워드를 사용하여 최상위 네임스페이스를 정의합니다.

1. *Class1.cs* 또는 *Class1.vb* 코드 창에서 코드를 다음 코드로 바꾸고 파일을 저장합니다. 사용하려는 언어가 표시되지 않으면 페이지 맨 위에 있는 언어 선택기를 변경합니다.

   :::code language="csharp" source="./snippets/library-with-visual-studio/csharp/StringLibrary/Class1.cs":::
   :::code language="vb" source="./snippets/library-with-visual-studio/vb/StringLibrary/Class1.vb":::

   클래스 라이브러리 `UtilityLibraries.StringLibrary`에는 `StartsWithUpper`라는 메서드가 포함되어 있습니다. 이 메서드는 현재 문자열 인스턴스가 대문자로 시작하는지 여부를 나타내는 <xref:System.Boolean> 값을 반환합니다. 유니코드 표준은 대문자와 소문자를 구분합니다. <xref:System.Char.IsUpper(System.Char)?displayProperty=nameWithType> 메서드는 문자가 대문자인 경우 `true`를 반환합니다.

   `StartsWithUpper`은 <xref:System.String> 클래스의 멤버인 것처럼 호출할 수 있도록 [확장 메서드](../../csharp/programming-guide/classes-and-structs/extension-methods.md)로 구현됩니다.

1. 메뉴 모음에서 **빌드** > **솔루션 빌드** 를 선택하거나 <kbd>Ctrl</kbd>+<kbd>Shift</kbd>+<kbd>B</kbd>를 눌러 프로젝트가 오류 없이 컴파일되는지 확인합니다.

## <a name="add-a-console-app-to-the-solution"></a>솔루션에 콘솔 앱 추가

클래스 라이브러리를 사용하는 콘솔 애플리케이션을 추가합니다. 이 앱은 사용자에게 문자열을 입력하라는 메시지를 표시하고 문자열이 대문자로 시작하는지 여부를 보고합니다.

1. “ShowCase”라는 새 .NET 콘솔 애플리케이션을 솔루션에 추가합니다.

   1. **솔루션 탐색기** 에서 솔루션을 마우스 오른쪽 단추로 클릭하고 **추가** > **새 프로젝트** 를 선택합니다.

   1. **새 프로젝트 추가** 페이지의 검색 상자에 **console** 을 입력합니다. 언어 목록에서 **C#** 또는 **Visual Basic** 을 선택한 다음, 플랫폼 목록에서 **모든 플랫폼** 을 선택합니다.

   1. **콘솔 애플리케이션** 템플릿을 선택한 후 **다음** 을 선택합니다.

   1. **새 프로젝트 구성** 페이지에서 **프로젝트 이름** 상자에 **ShowCase** 를 입력합니다. 그리고 **다음** 을 선택합니다.

   1. **추가 정보** 페이지의 **대상 프레임워크** 상자에서 **.NET 5.0(현재)** 을 선택합니다. 그런 다음, **만들기** 를 선택합니다.

1. *Program.cs* 또는 *Program.vb* 파일의 코드 창에서 모든 코드를 다음 코드로 바꿉니다.

   :::code language="csharp" source="./snippets/library-with-visual-studio/csharp/ShowCase/Program.cs":::
   :::code language="vb" source="./snippets/library-with-visual-studio/vb/ShowCase/Program.vb":::

   코드는 `row` 변수를 사용하여 콘솔 창에 기록된 데이터 행 수를 유지합니다. 25보다 크거나 같으면 코드는 콘솔 창을 지우고 사용자에게 메시지를 표시합니다.

   프로그램에서 문자열을 입력하라는 메시지를 사용자에게 표시합니다. 문자열이 대문자로 시작하는지 여부를 나타냅니다. 사용자가 문자열을 입력하지 않고 <kbd>Enter</kbd> 키를 누르면 애플리케이션이 종료되고 콘솔 창이 닫힙니다.

## <a name="add-a-project-reference"></a>프로젝트 참조 추가

처음에는 새 콘솔 앱 프로젝트가 클래스 라이브러리에 액세스할 수 없습니다. 클래스 라이브러리의 메서드를 호출할 수 있도록 허용하려면 클래스 라이브러리 프로젝트에 대한 프로젝트 참조를 만듭니다.

1. **솔루션 탐색기** 에서 `ShowCase` 프로젝트의 **종속성** 노드를 마우스 오른쪽 단추로 클릭하고 **프로젝트 참조 추가** 를 선택합니다.

   :::image type="content" source="media/library-with-visual-studio/add-reference-context-menu.png" alt-text="Visual Studio의 참조 추가 상황에 맞는 메뉴":::

1. **참조 관리자** 대화 상자에서 **StringLibrary** 프로젝트를 선택하고 **확인** 을 선택합니다.

   :::image type="content" source="media/library-with-visual-studio/manage-project-references.png" alt-text="StringLibrary를 선택한 참조 관리자 대화 상자":::

## <a name="run-the-app"></a>앱 실행

1. **솔루션 탐색기** 에서 **ShowCase** 프로젝트를 마우스 오른쪽 단추로 클릭하고 상황에 맞는 메뉴에서 **시작 프로젝트로 설정** 을 선택합니다.

   :::image type="content" source="media/library-with-visual-studio/set-startup-project-context-menu.png" alt-text="Visual Studio 프로젝트 상황에 맞는 메뉴로 시작 프로젝트 설정":::

1. <kbd>Ctrl</kbd>+<kbd>F5</kbd>를 눌러 디버깅 없이 프로그램을 컴파일하고 실행합니다.

   :::image type="content" source="media/library-with-visual-studio/visual-studio-project-toolbar.png" alt-text="Visual Studio 프로젝트 도구 모음 디버그 단추 표시":::

1. 문자열을 입력하고 <kbd>Enter</kbd> 키를 눌러 프로그램을 사용해 본 다음 <kbd>Enter</kbd> 키를 눌러 끝냅니다.

   :::image type="content" source="media/library-with-visual-studio/run-showcase.png" alt-text="ShowCase가 실행되는 콘솔 창":::

## <a name="additional-resources"></a>추가 자료

* [.NET CLI를 사용하여 라이브러리 개발](libraries.md)

## <a name="next-steps"></a>다음 단계

이 자습서에서는 클래스 라이브러리를 만들었습니다. 다음 자습서에서는 클래스 라이브러리의 유닛 테스트를 실행하는 방법을 알아봅니다.

> [!div class="nextstepaction"]
> [Visual Studio를 사용하여 .NET 클래스 라이브러리 단위 테스트](testing-library-with-visual-studio.md)

또는 자동화된 유닛 테스트를 건너뛰고 NuGet 패키지를 만들어서 라이브러리를 공유하는 방법을 알아볼 수도 있습니다.

> [!div class="nextstepaction"]
> [Visual Studio를 사용하여 패키지 만들기 및 게시](/nuget/quickstart/create-and-publish-a-package-using-visual-studio)

또는 콘솔 앱을 게시하는 방법을 알아보세요. 이 자습서에서 만든 솔루션에서 콘솔 앱을 게시하는 경우 클래스 라이브러리는 *.dll* 파일로 함께 포함됩니다.

> [!div class="nextstepaction"]
> [Visual Studio를 사용하여 .NET 콘솔 애플리케이션 게시](publishing-with-visual-studio.md)
