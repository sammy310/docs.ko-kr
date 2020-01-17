---
title: Visual Studio에서 .NET Standard 라이브러리 사용
description: Visual Studio 2019를 사용하여 다른 클래스 라이브러리의 멤버를 호출하는 .NET Core 애플리케이션을 빌드합니다.
ms.date: 12/20/2019
dev_langs:
- csharp
- vb
ms.custom: vs-dotnet
ms.openlocfilehash: ec9c6f992bcd4a76e2f70018f3facca42b7b660c
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/07/2020
ms.locfileid: "75714065"
---
# <a name="consume-a-net-standard-library-in-visual-studio"></a>Visual Studio에서 .NET Standard 라이브러리 사용

.NET Standard 클래스 라이브러리를 만들고 테스트했으며 라이브러리의 릴리스 버전을 빌드한 경우 다음 단계는 호출자에게 이를 제공하는 것입니다. 이 작업은

- 라이브러리가 단일 솔루션에 사용되는 경우(예: 단일 대형 애플리케이션의 구성 요소인 경우) 솔루션에 프로젝트로 포함할 수 있습니다.
- 라이브러리를 공개적으로 사용 가능한 경우 NuGet 패키지로 배포할 수 있습니다.

이 자습서에서는 다음과 같은 작업을 수행하는 방법을 살펴봅니다.
> [!div class="checklist"]
>
> - .NET Standard 라이브러리 프로젝트를 참조하는 솔루션에 콘솔 앱을 추가합니다.
> - .NET Standard 라이브러리를 포함하는 NuGet 패키지를 만듭니다.

## <a name="add-a-console-app-to-your-solution"></a>솔루션에 콘솔 앱 추가

[Visual Studio에서 .NET Standard 라이브러리 테스트](testing-library-with-visual-studio.md)의 클래스 라이브러리와 동일한 솔루션에 단위 테스트를 포함한 것처럼 애플리케이션을 해당 솔루션의 일부로 포함할 수 있습니다. 예를 들어 사용자가 문자열을 입력하도록 요구하고 첫 번째 문자가 대문자인지 여부를 보고하는 콘솔 애플리케이션에서 이 클래스 라이브러리를 사용할 수 있습니다.

1. [Visual Studio에서 .NET Standard 라이브러리 빌드](library-with-visual-studio.md) 문서에서 만든 `ClassLibraryProjects` 솔루션을 엽니다.

1. "ShowCase"라는 새 .NET Core 콘솔 애플리케이션을 솔루션에 추가합니다.

   1. **솔루션 탐색기**에서 솔루션을 마우스 오른쪽 단추로 클릭하고 **추가** > **새 프로젝트**를 선택합니다.

   1. **새 프로젝트 추가** 페이지의 검색 상자에 **console**을 입력합니다. 언어 목록에서 **C#** 또는 **Visual Basic**을 선택한 다음, 플랫폼 목록에서 **모든 플랫폼**을 선택합니다. **콘솔 앱(.NET Core)** 템플릿을 선택하고 **다음**을 선택합니다.

   1. **새 프로젝트 구성** 페이지에서 **프로젝트 이름** 상자에 **ShowCase**를 입력합니다. 그런 다음, **만들기**를 선택합니다.

1. **솔루션 탐색기**에서 **ShowCase** 프로젝트를 마우스 오른쪽 단추로 클릭하고 상황에 맞는 메뉴에서 **시작 프로젝트로 설정**을 선택합니다.

   ![Visual Studio 프로젝트 상황에 맞는 메뉴로 시작 프로젝트 설정](./media/consuming-library-with-visual-studio/set-startup-project-context-menu.png)

1. 처음에는 프로젝트에서 클래스 라이브러리에 액세스할 수 없습니다. 클래스 라이브러리의 메서드를 호출할 수 있도록 허용하려면 클래스 라이브러리에 대한 참조를 만듭니다. **솔루션 탐색기**에서 `ShowCase` 프로젝트의 **종속성** 노드를 마우스 오른쪽 단추로 클릭하고 **참조 추가**를 선택합니다.

   ![Visual Studio의 참조 추가 상황에 맞는 메뉴](./media/consuming-library-with-visual-studio/add-reference-context-menu.png)

1. **참조 관리자** 대화 상자에서 **StringLibrary**, 해당 클래스 라이브러리 프로젝트를 차례로 선택한 다음 **확인** 단추를 선택합니다.

   ![StringLibrary를 선택한 참조 관리자 대화 상자](./media/consuming-library-with-visual-studio/manage-project-references.png)

1. *Program.cs* 또는 *Program.vb* 파일의 코드 창에서 모든 코드를 다음 코드로 바꿉니다.

   [!code-csharp[UsingClassLib#1](~/samples/snippets/csharp/getting_started/with_visual_studio_2017/showcase.cs)]
   [!code-vb[UsingClassLib#1](~/samples/snippets/core/tutorials/vb-library-with-visual-studio/showcase.vb)]

   코드는 `row` 변수를 사용하여 콘솔 창에 기록된 데이터 행 수를 유지합니다. 25보다 크거나 같으면 코드는 콘솔 창을 지우고 사용자에게 메시지를 표시합니다.

   프로그램에서 문자열을 입력하라는 메시지를 사용자에게 표시합니다. 문자열이 대문자로 시작하는지 여부를 나타냅니다. 사용자가 문자열을 입력하지 않고 Enter 키를 누르면 애플리케이션이 종료되고 콘솔 창이 닫힙니다.

1. 필요한 경우 도구 모음을 변경하여 컴파일하는 `ShowCase` 프로젝트의 **디버그** 릴리스를 컴파일합니다. **ShowCase** 단추에서 녹색 화살표를 선택하여 프로그램을 컴파일하고 실행합니다.

   ![Visual Studio 프로젝트 도구 모음 디버그 단추 표시](./media/consuming-library-with-visual-studio/visual-studio-project-toolbar.png)

[Visual Studio를 사용하여 C# 또는 Visual Basic .NET Core Hello World 애플리케이션 디버그](debugging-with-visual-studio.md) 및 [Visual Studio를 사용하여 .NET Core Hello World 애플리케이션 게시](publishing-with-visual-studio.md)의 단계에 따라 이 라이브러리를 사용하는 애플리케이션을 디버그하고 게시할 수 있습니다.

## <a name="create-a-nuget-package"></a>NuGet 패키지 만들기

클래스 라이브러리를 NuGet 패키지로 게시하여 광범위하게 사용하도록 할 수 있습니다. Visual Studio에서는 NuGet 패키지의 생성을 지원하지 않습니다. 이를 만들려면 .NET Core CLI 명령을 사용해야 합니다.

1. 콘솔 창이 열립니다.

   예를 들어 Windows 작업 표시줄의 검색 상자에서 **명령 프롬프트**를 입력합니다. **명령 프롬프트** 데스크톱 앱을 선택 하거나 검색 결과에서 이미 선택되어 있는 경우 **Enter** 키를 누릅니다.

1. 라이브러리의 프로젝트 디렉터리로 이동합니다. 이 디렉터리에는 소스 코드 및 프로젝트 파일 *StringLibrary.csproj* 또는 *StringLibrary.vbproj*가 있습니다.

1. [dotnet pack](../tools/dotnet-pack.md) 명령을 실행하여 *.nupkg* 확장명을 포함하는 패키지를 생성합니다.

   ```dotnetcli
   dotnet pack --no-build
   ```

   > [!TIP]
   > *dotnet.exe*를 포함하는 디렉터리가 해당 PATH에 없는 경우 콘솔 창에 `where dotnet.exe`를 입력하여 해당 위치를 찾을 수 있습니다.

NuGet 패키지를 만드는 방법에 대한 자세한 내용은 [플랫폼 간 도구로 NuGet 패키지를 만드는 방법](../deploying/creating-nuget-packages.md)을 참조하세요.
