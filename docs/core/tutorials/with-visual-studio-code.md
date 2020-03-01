---
title: C# 및 Visual Studio Code 시작
description: Visual Studio Code를 사용하여 C#에서 첫 번째 .NET Core 애플리케이션을 만들고 디버그하는 방법을 알아봅니다.
author: kendrahavens
ms.date: 12/05/2018
ms.openlocfilehash: ef7134e26c1ded3926faa51748c1b6d4a461008f
ms.sourcegitcommit: 00aa62e2f469c2272a457b04e66b4cc3c97a800b
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/28/2020
ms.locfileid: "78156610"
---
# <a name="get-started-with-c-and-visual-studio-code"></a><span data-ttu-id="5966e-103">C# 및 Visual Studio Code 시작</span><span class="sxs-lookup"><span data-stu-id="5966e-103">Get started with C# and Visual Studio Code</span></span>

<span data-ttu-id="5966e-104">.NET Core는 Windows, Linux 및 macOS에서 실행되는 애플리케이션을 만들기 위한 빠른 모듈식 플랫폼을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="5966e-104">.NET Core gives you a fast and modular platform for creating applications that run on Windows, Linux, and macOS.</span></span> <span data-ttu-id="5966e-105">C# 확장이 있는 Visual Studio Code를 사용하면 C# IntelliSense(스마트 코드 완성) 및 디버깅을 완벽하게 지원하는 강력한 편집 환경이 구현됩니다.</span><span class="sxs-lookup"><span data-stu-id="5966e-105">Use Visual Studio Code with the C# extension to get a powerful editing experience with full support for C# IntelliSense (smart code completion) and debugging.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="5966e-106">사전 요구 사항</span><span class="sxs-lookup"><span data-stu-id="5966e-106">Prerequisites</span></span>

1. <span data-ttu-id="5966e-107">[Visual Studio Code](https://code.visualstudio.com/)를 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="5966e-107">Install [Visual Studio Code](https://code.visualstudio.com/).</span></span>
2. <span data-ttu-id="5966e-108">[.NET Core SDK](https://dotnet.microsoft.com/download)를 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="5966e-108">Install the [.NET Core SDK](https://dotnet.microsoft.com/download).</span></span>
3. <span data-ttu-id="5966e-109">Visual Studio Code의 [C# 확장](https://marketplace.visualstudio.com/items?itemName=ms-vscode.csharp)을 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="5966e-109">Install the [C# extension](https://marketplace.visualstudio.com/items?itemName=ms-vscode.csharp) for Visual Studio Code.</span></span> <span data-ttu-id="5966e-110">Visual Studio Code의 확장을 설치하는 방법에 대한 자세한 내용은 [VS Code Extension Marketplace](https://code.visualstudio.com/docs/editor/extension-gallery)(VS Code 확장 마켓플레이스)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="5966e-110">For more information about how to install extensions on Visual Studio Code, see [VS Code Extension Marketplace](https://code.visualstudio.com/docs/editor/extension-gallery).</span></span>

## <a name="hello-world"></a><span data-ttu-id="5966e-111">Hello World</span><span class="sxs-lookup"><span data-stu-id="5966e-111">Hello World</span></span>

<span data-ttu-id="5966e-112">.NET Core에서 간단한 "Hello World" 프로그램으로 시작해 보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="5966e-112">Let's get started with a simple "Hello World" program on .NET Core:</span></span>

1. <span data-ttu-id="5966e-113">프로젝트 열기</span><span class="sxs-lookup"><span data-stu-id="5966e-113">Open a project:</span></span>

    - <span data-ttu-id="5966e-114">Visual Studio Code를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="5966e-114">Open Visual Studio Code.</span></span>
    - <span data-ttu-id="5966e-115">왼쪽 메뉴에 있는 탐색기 아이콘을 클릭한 다음 **폴더 열기**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="5966e-115">Click on the Explorer icon on the left menu and then click **Open Folder**.</span></span>
    - <span data-ttu-id="5966e-116">주 메뉴에서 **파일** > **폴더 열기**를 선택하여 C# 프로젝트를 저장하려는 폴더를 열고 **폴더 선택**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="5966e-116">Select **File** > **Open Folder** from the main menu to open the folder you want your C# project to be in and click **Select Folder**.</span></span> <span data-ttu-id="5966e-117">이 예제에서는 *HelloWorld*라는 프로젝트에 대한 폴더를 만들어 봅니다.</span><span class="sxs-lookup"><span data-stu-id="5966e-117">For our example, we're creating a folder for our project named *HelloWorld*.</span></span>

      ![Visual Studio Code 폴더 열기](media/with-visual-studio-code/vs-code-open-folder.png)

2. <span data-ttu-id="5966e-119">C# 프로젝트 초기화</span><span class="sxs-lookup"><span data-stu-id="5966e-119">Initialize a C# project:</span></span>

    - <span data-ttu-id="5966e-120">주 메뉴에서 **보기** > **통합 터미널**을 선택하여 Visual Studio Code에서 통합 터미널을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="5966e-120">Open the Integrated Terminal from Visual Studio Code by selecting **View** > **Integrated Terminal** from the main menu.</span></span>
    - <span data-ttu-id="5966e-121">터미널 창에서 `dotnet new console`을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="5966e-121">In the terminal window, type `dotnet new console`.</span></span>
    - <span data-ttu-id="5966e-122">이 명령은 폴더에 이미 작성된 간단한 “헬로 월드” 프로그램이 있는 *Program.cs* 파일을 만들고 *HelloWorld.csproj*라는 C# 프로젝트 파일을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="5966e-122">This command creates a *Program.cs* file in your folder with a simple "Hello World" program already written, along with a C# project file named *HelloWorld.csproj*.</span></span>

      ![dotnet new 명령](media/with-visual-studio-code/dotnet-new-command.png)

3. <span data-ttu-id="5966e-124">빌드 자산 확인</span><span class="sxs-lookup"><span data-stu-id="5966e-124">Resolve the build assets:</span></span>

    - <span data-ttu-id="5966e-125">**.NET Core 1.x**의 경우 `dotnet restore`를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="5966e-125">For **.NET Core 1.x**, type `dotnet restore`.</span></span> <span data-ttu-id="5966e-126">`dotnet restore`를 실행하면 프로젝트를 빌드하는 데 필요한 필수 .NET Core 패키지에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5966e-126">Running `dotnet restore` gives you access to the  required .NET Core packages that are needed to build your project.</span></span>

      ![dotnet restore 명령](media/with-visual-studio-code/dotnet-restore-command.png)

      [!INCLUDE[DotNet Restore Note](~/includes/dotnet-restore-note.md)]

4. <span data-ttu-id="5966e-128">"Hello World" 프로그램 실행</span><span class="sxs-lookup"><span data-stu-id="5966e-128">Run the "Hello World" program:</span></span>

    - <span data-ttu-id="5966e-129">`dotnet run`을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="5966e-129">Type `dotnet run`.</span></span>

      ![dotnet run 명령](media/with-visual-studio-code/dotnet-run-command.png)

<span data-ttu-id="5966e-131">[Windows](https://channel9.msdn.com/Blogs/dotnet/Get-started-with-VS-Code-using-CSharp-and-NET-Core), [macOS](https://channel9.msdn.com/Blogs/dotnet/Get-started-with-VS-Code-using-CSharp-and-NET-Core-on-MacOS) 또는 [Linux](https://channel9.msdn.com/Blogs/dotnet/Get-started-with-VS-Code-Csharp-dotnet-Core-Ubuntu)에 대한 추가 설치 도움말이 제공되는 짧은 비디오 자습서를 볼 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5966e-131">You can also watch a short video tutorial for further setup help on [Windows](https://channel9.msdn.com/Blogs/dotnet/Get-started-with-VS-Code-using-CSharp-and-NET-Core), [macOS](https://channel9.msdn.com/Blogs/dotnet/Get-started-with-VS-Code-using-CSharp-and-NET-Core-on-MacOS), or [Linux](https://channel9.msdn.com/Blogs/dotnet/Get-started-with-VS-Code-Csharp-dotnet-Core-Ubuntu).</span></span>

## <a name="debug"></a><span data-ttu-id="5966e-132">디버그</span><span class="sxs-lookup"><span data-stu-id="5966e-132">Debug</span></span>

1. <span data-ttu-id="5966e-133">*Program.cs*를 클릭하여 엽니다.</span><span class="sxs-lookup"><span data-stu-id="5966e-133">Open *Program.cs* by clicking on it.</span></span> <span data-ttu-id="5966e-134">Visual Studio Code에서 C# 파일을 처음 열면 [OmniSharp](https://www.omnisharp.net/)에서 편집기가 로드됩니다.</span><span class="sxs-lookup"><span data-stu-id="5966e-134">The first time you open a C# file in Visual Studio Code, [OmniSharp](https://www.omnisharp.net/) loads in the editor.</span></span>

    ![Program.cs 파일 열기](media/with-visual-studio-code/open-program-cs.png)

2. <span data-ttu-id="5966e-136">Visual Studio Code에 앱을 빌드하고 디버그하기 위해 누락된 자산을 추가하라는 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="5966e-136">Visual Studio Code should prompt you to add the missing assets to build and debug your app.</span></span> <span data-ttu-id="5966e-137">**Yes**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="5966e-137">Select **Yes**.</span></span>

    ![누락된 자산에 대한 프롬프트](media/with-visual-studio-code/missing-assets.png)

3. <span data-ttu-id="5966e-139">디버그 보기를 열려면 왼쪽 메뉴에서 디버깅 아이콘을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="5966e-139">To open the Debug view, click on the Debugging icon on the left side menu.</span></span>

    ![Visual Studio Code에서 [디버그] 탭 열기](media/with-visual-studio-code/open-debug-tab.png)

4. <span data-ttu-id="5966e-141">창 위쪽에서 녹색 화살표를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="5966e-141">Locate the green arrow at the top of the pane.</span></span> <span data-ttu-id="5966e-142">옆에 있는 드롭다운 목록에서 **.NET Core Launch(콘솔)** 가 선택되어 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="5966e-142">Make sure the drop-down next to it has **.NET Core Launch (console)** selected.</span></span>

    ![Visual Studio Code에서.NET Core 선택](media/with-visual-studio-code/select-net-core.png)

5. <span data-ttu-id="5966e-144">9번째 줄 옆에 있는 **편집기 여백**(편집기에서 줄 번호 왼쪽에 있는 공간)을 클릭하거나 편집기에서 9번째 줄로 이동하여 <kbd>F9</kbd>를 눌러서 프로젝트에 중단점을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="5966e-144">Add a breakpoint to your project by clicking on the **editor margin**, which is the space on the left of the line numbers in the editor, next to line 9, or move the text cursor onto line 9 in the editor and  press <kbd>F9</kbd>.</span></span>

    ![중단점 설정](media/with-visual-studio-code/set-breakpoint-vs-code.png)

6. <span data-ttu-id="5966e-146">디버깅을 시작하려면 <kbd>F5</kbd>를 누르거나 또는 녹색 화살표를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="5966e-146">To start debugging, press <kbd>F5</kbd> or select the green arrow.</span></span> <span data-ttu-id="5966e-147">이전 단계에서 설정한 중단점에 도달하면 디버거에서 프로그램 실행을 중지합니다.</span><span class="sxs-lookup"><span data-stu-id="5966e-147">The debugger stops execution of your program when it reaches the breakpoint you set in the previous step.</span></span>
    - <span data-ttu-id="5966e-148">디버깅 동안 왼쪽 위에 있는 창에서 지역 변수를 보거나 디버그 콘솔을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5966e-148">While debugging, you can view your local variables in the top left pane or use the debug console.</span></span>

7. <span data-ttu-id="5966e-149">디버깅을 계속하려면 맨 위에 있는 파란색 화살표를 선택하고, 중지하려면 맨 위에 있는 빨간색 사각형을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="5966e-149">Select the blue arrow at the top to continue debugging, or select the red square at the top to stop.</span></span>

    ![Visual Studio Code에서 실행 및 디버그](media/with-visual-studio-code/run-debug-vs-code.png)

> [!TIP]
> <span data-ttu-id="5966e-151">Visual Studio Code에서 OmniSharp를 사용한 .NET Core 디버깅에 대한 자세한 내용과 문제 해결 정보는 [Instructions for setting up the .NET Core debugger](https://github.com/OmniSharp/omnisharp-vscode/blob/master/debugger.md)(.NET Core 디버거 설정 지침)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="5966e-151">For more information and troubleshooting tips on .NET Core debugging with OmniSharp in Visual Studio Code, see [Instructions for setting up the .NET Core debugger](https://github.com/OmniSharp/omnisharp-vscode/blob/master/debugger.md).</span></span>

## <a name="add-a-class"></a><span data-ttu-id="5966e-152">클래스 추가</span><span class="sxs-lookup"><span data-stu-id="5966e-152">Add a class</span></span>

1. <span data-ttu-id="5966e-153">새 클래스를 추가하려면 VSCode 탐색기에서 마우스 오른쪽 단추를 클릭하고 **새 파일**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="5966e-153">To add a new class, right click in the VSCode Explorer and select **New File**.</span></span> <span data-ttu-id="5966e-154">VSCode에서 열어 놓은 폴더에 새 파일이 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="5966e-154">This adds a new file to the folder you have open in VSCode.</span></span>
2. <span data-ttu-id="5966e-155">파일 이름을 *MyClass.cs*로 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="5966e-155">Name your file *MyClass.cs*.</span></span> <span data-ttu-id="5966e-156">csharp 파일로 인식되도록 끝에 `.cs` 확장명을 추가해서 저장해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5966e-156">You must save it with a `.cs` extension at the end for it to be recognized as a csharp file.</span></span>
3. <span data-ttu-id="5966e-157">아래 코드를 추가하여 첫 번째 클래스를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="5966e-157">Add the code below to create your first class.</span></span> <span data-ttu-id="5966e-158">*Program.cs* 파일에서 참조할 수 있도록 올바른 네임스페이스를 포함해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5966e-158">Make sure to include the correct namespace so you can reference it from your *Program.cs* file:</span></span>

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

4. <span data-ttu-id="5966e-159">아래 코드를 추가하여 *Program.cs*의 main 메서드에서 새 클래스를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="5966e-159">Call your new class from your main method in *Program.cs* by adding the code below:</span></span>

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

5. <span data-ttu-id="5966e-160">변경 내용을 저장하고 프로그램을 다시 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="5966e-160">Save your changes and run your program again.</span></span> <span data-ttu-id="5966e-161">추가된 문자열을 포함하는 새 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="5966e-161">The new message should appear with the appended string.</span></span>

    ```dotnetcli
    dotnet run
    ```

    <span data-ttu-id="5966e-162">다음과 같은 출력을 얻습니다.</span><span class="sxs-lookup"><span data-stu-id="5966e-162">You get the following output:</span></span>

    ```console
    Hello World! Happy coding!
    ```

## <a name="faq"></a><span data-ttu-id="5966e-163">FAQ</span><span class="sxs-lookup"><span data-stu-id="5966e-163">FAQ</span></span>

### <a name="im-missing-required-assets-to-build-and-debug-c-in-visual-studio-code-my-debugger-says-no-configuration"></a><span data-ttu-id="5966e-164">Visual Studio Code에서 C#을 빌드하고 디버그하는 데 필요한 자산이 누락되었습니다.</span><span class="sxs-lookup"><span data-stu-id="5966e-164">I'm missing required assets to build and debug C# in Visual Studio Code.</span></span> <span data-ttu-id="5966e-165">내 디버거에서 "구성 없음"이라고 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="5966e-165">My debugger says "No Configuration."</span></span>

<span data-ttu-id="5966e-166">Visual Studio Code C# 확장에서 빌드 및 디버그할 자산을 생성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5966e-166">The Visual Studio Code C# extension can generate assets to build and debug for you.</span></span> <span data-ttu-id="5966e-167">C# 프로젝트를 처음 열면 Visual Studio Code에 이러한 자산을 생성하라는 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="5966e-167">Visual Studio Code prompts you to generate these assets when you first open a C# project.</span></span> <span data-ttu-id="5966e-168">자산을 생성하지 않은 경우 명령 팔레트(**보기 > 명령 팔레트**)를 열고 ">.NET: Generate Assets Build and Debug"를 입력하여 이 명령을 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5966e-168">If you didn't generate assets then, you can still run this command by opening the Command Palette (**View > Command Palette**) and typing ">.NET: Generate Assets for Build and Debug".</span></span> <span data-ttu-id="5966e-169">이를 선택하면 필요한 . *.vscode*, *launch.json* 및 *tasks.json* 구성 파일이 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="5966e-169">Selecting this generates the *.vscode*, *launch.json*, and *tasks.json* configuration files that you need.</span></span>

## <a name="see-also"></a><span data-ttu-id="5966e-170">참조</span><span class="sxs-lookup"><span data-stu-id="5966e-170">See also</span></span>

- [<span data-ttu-id="5966e-171">Visual Studio Code 설치</span><span class="sxs-lookup"><span data-stu-id="5966e-171">Setting up Visual Studio Code</span></span>](https://code.visualstudio.com/docs/setup/setup-overview)
- [<span data-ttu-id="5966e-172">Visual Studio Code의 디버깅</span><span class="sxs-lookup"><span data-stu-id="5966e-172">Debugging in Visual Studio Code</span></span>](https://code.visualstudio.com/Docs/editor/debugging)
