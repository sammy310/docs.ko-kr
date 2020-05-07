---
title: C# 및 Visual Studio Code 시작
description: Visual Studio Code를 사용하여 C#에서 첫 번째 .NET Core 애플리케이션을 만들고 디버그하는 방법을 알아봅니다.
author: kendrahavens
ms.date: 04/23/2020
ms.openlocfilehash: 3dd7c4602fbb27e29bad977f8d3df34b6061bc23
ms.sourcegitcommit: 1cb64b53eb1f253e6a3f53ca9510ef0be1fd06fe
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/29/2020
ms.locfileid: "82506904"
---
# <a name="get-started-with-c-and-visual-studio-code"></a>C# 및 Visual Studio Code 시작

.NET Core는 Windows, Linux 및 macOS에서 실행되는 애플리케이션을 만들기 위한 빠른 모듈식 플랫폼을 제공합니다. C# 확장이 있는 Visual Studio Code를 사용하면 C# IntelliSense(스마트 코드 완성) 및 디버깅을 완벽하게 지원하는 강력한 편집 환경이 구현됩니다.

## <a name="prerequisites"></a>사전 요구 사항

1. [Visual Studio Code](https://code.visualstudio.com/)를 설치합니다.
2. [.NET Core SDK](https://dotnet.microsoft.com/download)를 설치합니다.
3. Visual Studio Code의 [C# 확장](https://marketplace.visualstudio.com/items?itemName=ms-dotnettools.csharp)을 설치합니다. Visual Studio Code의 확장을 설치하는 방법에 대한 자세한 내용은 [VS Code Extension Marketplace](https://code.visualstudio.com/docs/editor/extension-gallery)(VS Code 확장 마켓플레이스)를 참조하세요.

## <a name="hello-world"></a>Hello World

.NET Core에서 간단한 “Hello World” 프로그램으로 시작:

1. 프로젝트 열기

    - Visual Studio Code를 엽니다.
    - 주 메뉴에서 **파일** > **폴더 열기**를 선택합니다.
    - *HelloWorld* 폴더를 만들고 **폴더 선택**을 클릭합니다. 기본적으로 폴더 이름은 프로젝트 이름 및 네임스페이스 이름이 됩니다. 프로젝트 네임스페이스가 `HelloWorld`라고 가정하는 코드를 자습서의 뒷부분에 추가합니다.

1. C# 프로젝트 초기화

    - 주 메뉴에서 **보기** > **터미널**을 선택하여 Visual Studio Code에서 터미널을 엽니다.
    - 터미널 창에서 `dotnet new console`을 입력합니다.

      이 명령은 폴더에 이미 작성된 간단한 “헬로 월드” 프로그램이 있는 *Program.cs* 파일을 만들고 *HelloWorld.csproj*라는 C# 프로젝트 파일을 만듭니다.

      ![dotnet new 명령](media/with-visual-studio-code/dotnet-new-command.png)

1. "Hello World" 프로그램 실행

    - 터미널 창에서 `dotnet run`을 입력합니다.

      ![dotnet run 명령](media/with-visual-studio-code/dotnet-run-command.png)

## <a name="debug"></a>디버그

1. *Program.cs*를 클릭하여 엽니다. Visual Studio Code에서 C# 파일을 처음 열면 [OmniSharp](https://www.omnisharp.net/)에서 편집기가 로드됩니다.

    ![Program.cs 파일 열기](media/with-visual-studio-code/open-program-cs.png)

1. Visual Studio Code는 앱을 빌드하고 디버그하기 위해 누락된 자산을 추가하라는 메시지를 표시합니다. **Yes**를 선택합니다.

    ![누락된 자산에 대한 프롬프트](media/with-visual-studio-code/missing-assets.png)

1. 디버그 보기를 열려면 왼쪽 메뉴에서 디버깅 아이콘을 클릭합니다.

    ![Visual Studio Code에서 [디버그] 탭 열기](media/with-visual-studio-code/open-debug-tab.png)

1. 창 위쪽에서 녹색 화살표를 찾습니다. 옆에 있는 드롭다운 목록에서 **.NET Core Launch(콘솔)** 가 선택되어 있는지 확인합니다.

    ![Visual Studio Code에서.NET Core 선택](media/with-visual-studio-code/select-net-core.png)

1. 9번째 줄 옆에 있는 **편집기 여백**(편집기에서 줄 번호 왼쪽에 있는 공간)을 클릭하거나 편집기에서 9번째 줄로 이동하여 <kbd>F9</kbd>를 눌러서 프로젝트에 중단점을 추가합니다.

    ![중단점 설정](media/with-visual-studio-code/set-breakpoint-vs-code.png)

1. 디버깅을 시작하려면 <kbd>F5</kbd>를 누르거나 또는 녹색 화살표를 선택합니다. 이전 단계에서 설정한 중단점에 도달하면 디버거에서 프로그램 실행을 중지합니다.
    - 디버깅 동안 왼쪽 위에 있는 창에서 지역 변수를 보거나 디버그 콘솔을 사용할 수 있습니다.

1. 디버깅을 계속하려면 맨 위에 있는 파란색 화살표를 선택하고, 중지하려면 맨 위에 있는 빨간색 사각형을 선택합니다.

    ![Visual Studio Code에서 실행 및 디버그](media/with-visual-studio-code/run-debug-vs-code.png)

> [!TIP]
> Visual Studio Code에서 OmniSharp를 사용한 .NET Core 디버깅에 대한 자세한 내용과 문제 해결 정보는 [Instructions for setting up the .NET Core debugger](https://github.com/OmniSharp/omnisharp-vscode/blob/master/debugger.md)(.NET Core 디버거 설정 지침)를 참조하세요.

## <a name="add-a-class"></a>클래스 추가

1. 새 클래스를 추가하려면 *Program.cs* 아래 VSCode 탐색기에서 마우스 오른쪽 단추를 클릭하고 **새 파일**을 선택합니다. VSCode에서 열어 놓은 폴더에 새 파일이 추가됩니다.
1. 파일 이름을 *MyClass.cs*로 지정합니다. csharp 파일로 인식되도록 끝에 `.cs` 확장명을 추가해서 저장해야 합니다.
1. 다음 코드를 추가하여 첫 번째 클래스를 만듭니다.

    ``` csharp
    using System;

    namespace HelloWorld
    {
        public class MyClass
        {
            public string ReturnMessage()
            {
                return "Happy coding!";
            }
        }
    }
    ```

1. *Program.cs*의 코드를 다음 코드로 바꿔서 `Main` 메서드에서 새 클래스를 호출합니다.

    ```csharp
    using System;

    namespace HelloWorld
    {
        class Program
        {
            static void Main(string[] args)
            {
                var c1 = new MyClass();
                Console.WriteLine($"Hello World! {c1.ReturnMessage()}");
            }
        }
    }
    ```

1. 변경 내용을 저장합니다.

1. 프로그램을 다시 실행합니다.

    ```dotnetcli
    dotnet run
    ```

    추가된 문자열을 포함하는 새 메시지가 표시됩니다.

    ```console
    Hello World! Happy coding!
    ```

## <a name="faq"></a>FAQ

### <a name="im-missing-required-assets-to-build-and-debug-c-in-visual-studio-code-my-debugger-says-no-configuration"></a>Visual Studio Code에서 C#을 빌드하고 디버그하는 데 필요한 자산이 누락되었습니다. 내 디버거에서 "구성 없음"이라고 표시됩니다.

Visual Studio Code C# 확장에서 빌드 및 디버그할 자산을 생성할 수 있습니다. C# 프로젝트를 처음 열면 Visual Studio Code에 이러한 자산을 생성하라는 메시지가 표시됩니다. 자산을 생성하지 않은 경우 명령 팔레트(**보기 > 명령 팔레트**)를 열고 ">.NET: Generate Assets Build and Debug"를 입력하여 이 명령을 실행할 수 있습니다. 이를 선택하면 필요한 . *.vscode*, *launch.json* 및 *tasks.json* 구성 파일이 생성됩니다.

## <a name="see-also"></a>참조

- [Visual Studio Code 설치](https://code.visualstudio.com/docs/setup/setup-overview)
- [Visual Studio Code의 디버깅](https://code.visualstudio.com/Docs/editor/debugging)
