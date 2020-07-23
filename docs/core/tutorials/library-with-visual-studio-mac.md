---
title: Mac용 Visual Studio를 사용하여 .NET Standard 클래스 라이브러리 만들기
description: Mac용 Visual Studio를 사용하여 .NET Standard 클래스 라이브러리를 만드는 방법을 알아봅니다.
ms.date: 06/08/2020
ms.openlocfilehash: 8e1e4ca3bc1b12d889b847d80318f3d6cd1bbe46
ms.sourcegitcommit: 3492dafceb5d4183b6b0d2f3bdf4a1abc4d5ed8c
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/16/2020
ms.locfileid: "86416003"
---
# <a name="tutorial-create-a-net-standard-library-using-visual-studio-for-mac"></a>자습서: Mac용 Visual Studio를 사용하여 .NET Standard 라이브러리 만들기

이 자습서에서는 단일 문자열 처리 메서드를 포함하는 클래스 라이브러리를 만듭니다. <xref:System.String> 클래스의 멤버인 것처럼 호출할 수 있도록 [확장 메서드](../../csharp/programming-guide/classes-and-structs/extension-methods.md)로 구현합니다.

*클래스 라이브러리*는 애플리케이션에서 호출되는 형식 및 메서드를 정의합니다. .NET Standard 2.1을 대상으로 하는 클래스 라이브러리는 .NET Standard 버전 2.1이 지원되는 모든 .NET 구현을 대상으로 하는 애플리케이션에서 사용할 수 있습니다. 클래스 라이브러리를 마칠 때 타사 구성 요소 또는 하나 이상의 애플리케이션이 포함된 번들 구성 요소로 배포할 수 있습니다.

> [!NOTE]
> 사용자 의견은 매우 중요합니다. Mac용 Visual Studio의 개발 팀에 다음 두 가지 방법으로 의견을 제공할 수 있습니다.
>
> - Mac용 Visual Studio의 메뉴에서 **도움말** > **문제 보고**를 선택하거나 시작 화면에서 **문제 보고**를 선택하면 버그 보고서를 작성하기 위한 창이 열립니다. [Developer Community](https://developercommunity.visualstudio.com/spaces/41/index.html)(개발자 커뮤니티) 포털에서 의견을 추적할 수 있습니다.
> - 제안하려면 메뉴에서 **도움말** > **제안하기**를 선택하거나 시작 화면에서 **제안하기**를 선택합니다. 그러면 [Mac용 Visual Studio Developer Community 웹 페이지](https://developercommunity.visualstudio.com/content/idea/post.html?space=41)로 이동됩니다.

## <a name="prerequisites"></a>사전 요구 사항

* [Mac용 Visual Studio 버전 8.6 이상을 설치](https://visualstudio.microsoft.com/vs/mac/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link)합니다. .NET Core 설치 옵션을 선택합니다. Xamarin의 설치는 .NET Core 개발에서 선택 사항입니다. 자세한 내용은 다음 자료를 참조하세요.

  * [자습서: Mac용 Visual Studio](/visualstudio/mac/installation)를 설치합니다.
  * [지원되는 macOS 버전](../install/dependencies.md?pivots=os-macos).
  * [Mac용 Visual Studio에서 지원되는 .NET Core 버전](/visualstudio/mac/net-core-support).

## <a name="create-a-solution-with-a-class-library-project"></a>클래스 라이브러리 프로젝트로 솔루션 만들기

Visual Studio 솔루션은 하나 이상의 프로젝트에 대한 컨테이너로 작동합니다. 솔루션과 솔루션의 클래스 라이브러리 프로젝트를 만듭니다. 나중에 동일한 솔루션에 관련 프로젝트를 추가합니다.

1. Mac용 Visual Studio를 시작합니다.

1. 시작 창에서 **새 프로젝트**를 선택합니다.

1. **다중 플랫폼** 노드의 **새 프로젝트** 대화 상자에서 **라이브러리**를 선택한 다음 **.NET Standard 라이브러리** 템플릿을 선택하고 **다음**을 선택합니다.

   :::image type="content" source="media/library-with-visual-studio-mac/visual-studio-mac-new-project.png" alt-text="새 프로젝트 대화 상자":::

1. **새 .NET Standard 라이브러리 구성** 대화 상자에서 ".NET Standard 2.1"을 선택하고 **다음**을 선택합니다.

   :::image type="content" source="media/library-with-visual-studio-mac/choose-net-std-21.png" alt-text=".NET Standard 2.1 선택":::

1. 프로젝트 이름을 "StringLibrary", 솔루션 이름을 "ClassLibraryProjects"로 지정합니다. **솔루션 디렉터리 내에 프로젝트 디렉터리를 만드세요**를 선택한 상태로 둡니다. **만들기**를 선택합니다.

   :::image type="content" source="media/library-with-visual-studio-mac/visual-studio-mac-new-project-options.png" alt-text="Mac용 Visual Studio 새 프로젝트 대화 상자 옵션":::

1. 주 메뉴에서 **보기** > **패드** > **솔루션**을 선택한 다음 고정 아이콘을 선택하여 패드를 열어 둡니다.

   :::image type="content" source="media/library-with-visual-studio-mac/solution-dock-icon.png" alt-text="솔루션 패드의 고정 아이콘":::

1. **솔루션** 패드에서 `StringLibrary` 노드를 확장하여 템플릿에 제공되는 클래스 파일 *Class1.cs*를 표시합니다. <kbd>ctrl</kbd> 키를 누른 채로 파일을 클릭하고 상황에 맞는 메뉴에서 **이름 바꾸기**를 선택한 후 파일 이름을 *StringLibrary.cs*로 지정합니다. 파일을 열고 내용을 다음 코드로 바꿉니다.

   :::code language="csharp" source="./snippets/library-with-visual-studio/csharp/StringLibrary/Class1.cs":::

1. <kbd>⌘</kbd><kbd>S</kbd>(<kbd>command</kbd>+<kbd>S</kbd>)를 눌러 파일을 저장합니다.

1. IDE 창 아래쪽 여백에서 **오류**를 선택하여 **오류** 패널을 엽니다. **빌드 출력** 단추를 선택합니다.

   :::image type="content" source="media/library-with-visual-studio-mac/visual-studio-mac-error-button.png" alt-text="오류 단추를 표시하는 Visual Studio Mac IDE의 아래쪽 여백":::

1. 메뉴에서 **빌드** > **모두 빌드**를 선택합니다.

   솔루션이 빌드됩니다. 빌드 출력 패널에 빌드가 성공적으로 수행되었다고 표시됩니다.

   :::image type="content" source="media/library-with-visual-studio-mac/visual-studio-mac-build-panel.png" alt-text="빌드 성공 메시지를 표시하는 오류 패널의 Visual Studio Mac 빌드 출력 창":::

## <a name="add-a-console-app-to-the-solution"></a>솔루션에 콘솔 앱 추가

클래스 라이브러리를 사용하는 콘솔 애플리케이션을 추가합니다. 이 앱은 사용자에게 문자열을 입력하라는 메시지를 표시하고 문자열이 대문자로 시작하는지 여부를 보고합니다.

1. **솔루션** 패드에서 <kbd>ctrl</kbd> 키를 누른 채로 `ClassLibraryProjects` 솔루션을 클릭합니다. **웹 및 콘솔** > **앱** 템플릿에서 템플릿을 선택하여 새로운 **콘솔 애플리케이션** 프로젝트를 추가하고 **다음**을 선택합니다.

1. **대상 프레임워크**로 **.NET Core 3.1**을 선택하고 **다음**을 선택합니다.

1. 프로젝트 이름을 **ShowCase**로 지정합니다. **만들기**를 선택하여 솔루션에 프로젝트를 만듭니다.

   :::image type="content" source="media/library-with-visual-studio-mac/add-showcase-project.png" alt-text="ShowCase 프로젝트 추가":::

1. *Program.cs* 파일을 엽니다. 코드를 다음 코드로 바꿉니다.

   :::code language="csharp" source="./snippets/library-with-visual-studio/csharp/ShowCase/Program.cs":::

   프로그램에서 문자열을 입력하라는 메시지를 사용자에게 표시합니다. 문자열이 대문자로 시작하는지 여부를 나타냅니다. 사용자가 문자열을 입력하지 않고 <kbd>enter</kbd> 키를 누르면 애플리케이션이 종료되고 콘솔 창이 닫힙니다.

   코드는 `row` 변수를 사용하여 콘솔 창에 기록된 데이터 행 수를 유지합니다. 25보다 크거나 같으면 코드는 콘솔 창을 지우고 사용자에게 메시지를 표시합니다.

## <a name="add-a-project-reference"></a>프로젝트 참조 추가

처음에는 새 콘솔 앱 프로젝트가 클래스 라이브러리에 액세스할 수 없습니다. 클래스 라이브러리의 메서드를 호출할 수 있도록 허용하려면 클래스 라이브러리 프로젝트에 대한 프로젝트 참조를 만듭니다.

1. **솔루션** 패드에서 <kbd>ctrl</kbd> 키를 누른 채로 새로운 **ShowCase** 프로젝트의 **종속성** 노드를 클릭합니다. 상황에 맞는 메뉴에서 **참조 추가**를 클릭합니다.

1. **참조** 대화 상자에서 **StringLibrary**를 선택하고 **확인**을 선택합니다.

## <a name="run-the-app"></a>앱 실행

1. <kbd>ctrl</kbd> 키를 누른 채로 ShowCase 프로젝트를 클릭하고 상황에 맞는 메뉴뉴에서 **프로젝트 실행**을 선택합니다.

1. 문자열을 입력하고 <kbd>Enter</kbd> 키를 눌러 프로그램을 사용해 본 다음 <kbd>Enter</kbd> 키를 눌러 끝냅니다.

   :::image type="content" source="media/library-with-visual-studio-mac/visual-studio-mac-console-window.png" alt-text="실행 중인 앱을 보여 주는 Mac용 Visual Studio 콘솔 창":::

## <a name="additional-resources"></a>추가 자료

* [.NET Core CLI를 사용하여 라이브러리 개발](libraries.md)
* [지원되는 .NET Standard 버전 및 플랫폼](../../standard/net-standard.md)
* [Mac용 Visual Studio 2019 릴리스 정보](/visualstudio/releasenotes/vs2019-mac-relnotes)

## <a name="next-steps"></a>다음 단계

이 자습서에서는 솔루션과 라이브러리 프로젝트를 만들고 라이브러리를 사용하는 콘솔 앱 프로젝트를 추가했습니다. 다음 자습서에서는 솔루션에 단위 테스트 프로젝트를 추가합니다.

> [!div class="nextstepaction"]
> [Mac용 Visual Studio를 사용하여 .NET Core로 .NET Standard 라이브러리 테스트](testing-library-with-visual-studio-mac.md)
