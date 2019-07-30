---
title: Visual Studio Code에서 F# 시작
description: Visual Studio Code와 Ionide 플러그인 도구 모음으로 F#을 사용하는 방법을 알아봅니다.
ms.date: 12/23/2018
ms.openlocfilehash: baaa87207122cfe314972aee5dfaf8a41de2c394
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/30/2019
ms.locfileid: "68629974"
---
# <a name="get-started-with-f-in-visual-studio-code"></a><span data-ttu-id="d1f6b-103">Visual Studio Code에서 F# 시작</span><span class="sxs-lookup"><span data-stu-id="d1f6b-103">Get Started with F# in Visual Studio Code</span></span>

<span data-ttu-id="d1f6b-104">[Visual Studio Code](https://code.visualstudio.com)에서 [Ionide 플러그인](https://marketplace.visualstudio.com/items?itemName=Ionide.Ionide-fsharp)을 사용하여 F# 코드를 작성하면 IntelliSense와 기본적인 코드 리팩토링이 가능한 경량이면서 다양한 플랫폼에서 사용할 수 있는 IDE(Integrated Development Environment) 환경을 얻을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d1f6b-104">You can write F# in [Visual Studio Code](https://code.visualstudio.com) with the [Ionide plugin](https://marketplace.visualstudio.com/items?itemName=Ionide.Ionide-fsharp) to get a great cross-platform, lightweight Integrated Development Environment (IDE) experience with IntelliSense and basic code refactorings.</span></span> <span data-ttu-id="d1f6b-105">이 플러그인을 더 자세히 알고 싶다면 [Ionide.io](http://ionide.io)를 방문합니다.</span><span class="sxs-lookup"><span data-stu-id="d1f6b-105">Visit [Ionide.io](http://ionide.io) to learn more about the plugin.</span></span>

<span data-ttu-id="d1f6b-106">시작하려면 [F#과 Ionide 플러그인의 설치](install-fsharp.md#install-f-with-visual-studio-code)가 올바르게 되어있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="d1f6b-106">To begin, ensure that you have [F# and the Ionide plugin correctly installed](install-fsharp.md#install-f-with-visual-studio-code).</span></span>

> [!NOTE]
> <span data-ttu-id="d1f6b-107">Ionide는 플랫폼 간 호환성 문제가 발생할 수 있는 닷넷 코어가 아닌 .NET Framework F# 프로젝트를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="d1f6b-107">Ionide will generate .NET Framework F# projects, not dotnet core, which can have cross-platform compatibility issues.</span></span> <span data-ttu-id="d1f6b-108">**Linux** 또는 **OSX**에서 실행 하는 경우 [명령줄 도구](get-started-command-line.md)를 사용 하 여 시작 하는 것이 더 간단 합니다.</span><span class="sxs-lookup"><span data-stu-id="d1f6b-108">If you are running on **Linux** or **OSX**, a simpler way to get started is to use the [command-line tools](get-started-command-line.md).</span></span>

## <a name="creating-your-first-project-with-ionide"></a><span data-ttu-id="d1f6b-109">Ionide를 사용하여 첫 번째 프로젝트 만들기</span><span class="sxs-lookup"><span data-stu-id="d1f6b-109">Creating your first project with Ionide</span></span>

<span data-ttu-id="d1f6b-110">새 F# 프로젝트를 생성하기 위해 새 폴더(원하는 이름을 지정할 수 있습니다)에서 Visual Studio Code를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="d1f6b-110">To create a new F# project, open Visual Studio Code in a new folder (you can name it whatever you like).</span></span>

<span data-ttu-id="d1f6b-111">다음으로, 명령 팔레트를 열고(**보기 > 명령 팔레트**) 다음을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="d1f6b-111">Next, open the command palette (**View > Command Palette**) and type the following:</span></span>

```
> F# new project
```

<span data-ttu-id="d1f6b-112">[FORGE](https://github.com/fsharp-editing/Forge) 프로젝트에 의해 동작합니다.</span><span class="sxs-lookup"><span data-stu-id="d1f6b-112">This is powered by the [FORGE](https://github.com/fsharp-editing/Forge) project.</span></span>

> [!NOTE]
> <span data-ttu-id="d1f6b-113">템플릿 옵션을 보이지 않으면 명령 팔레트에서 다음 명령을 실행하여 템플릿을 새로 고쳐보세요: `>F#: Refresh Project Templates`</span><span class="sxs-lookup"><span data-stu-id="d1f6b-113">If you don't see template options, try refreshing templates by running the following command in the Command Palette: `>F#: Refresh Project Templates`.</span></span>

<span data-ttu-id="d1f6b-114">Enter를 눌러서 "F#: new project"를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="d1f6b-114">Select "F#: New Project" by hitting **Enter**.</span></span> <span data-ttu-id="d1f6b-115">이렇게 하면 프로젝트 템플릿을 선택하는 다음 단계로 넘어갑니다.</span><span class="sxs-lookup"><span data-stu-id="d1f6b-115">This takes you to the next step, which is for selecting a project template.</span></span>

<span data-ttu-id="d1f6b-116">`classlib` 템플릿을 선택하고 **Enter**를 칩니다.</span><span class="sxs-lookup"><span data-stu-id="d1f6b-116">Pick the `classlib` template and hit **Enter**.</span></span>

<span data-ttu-id="d1f6b-117">그런 다음에 프로젝트를 생성하기 위한 디렉터리를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="d1f6b-117">Next, pick a directory to create the project in.</span></span> <span data-ttu-id="d1f6b-118">비워 두면 현재 디렉터리를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="d1f6b-118">If you leave it blank, it uses the current directory.</span></span>

<span data-ttu-id="d1f6b-119">끝으로, 마지막 단계에서는 프로젝트의 이름을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="d1f6b-119">Finally, name your project in the final step.</span></span> <span data-ttu-id="d1f6b-120">F#에서는 [파스칼식 대/소문자](http://c2.com/cgi/wiki?PascalCase)를 프로젝트 이름으로 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="d1f6b-120">F# uses [Pascal case](http://c2.com/cgi/wiki?PascalCase) for project names.</span></span> <span data-ttu-id="d1f6b-121">이 문서에서는 `ClassLibraryDemo`를 이름으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="d1f6b-121">This article uses `ClassLibraryDemo` as the name.</span></span> <span data-ttu-id="d1f6b-122">자신이 원하는 프로젝트 이름을 입력한 후 **Enter**를 칩니다.</span><span class="sxs-lookup"><span data-stu-id="d1f6b-122">Once you've entered the name you want for your project, hit **Enter**.</span></span>

<span data-ttu-id="d1f6b-123">지금까지의 단계를 수행했다면 Visual Studio 코드의 좌측 작업 영역에 다음 내용이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="d1f6b-123">If you followed the previous step, you should get the Visual Studio Code Workspace on the left-hand side to appear with the following:</span></span>

1. <span data-ttu-id="d1f6b-124">F# 프로젝트 자체는 `ClassLibraryDemo` 폴더 하위에 존재합니다.</span><span class="sxs-lookup"><span data-stu-id="d1f6b-124">The F# project itself, underneath the `ClassLibraryDemo` folder.</span></span>
2. <span data-ttu-id="d1f6b-125">[`Paket`](https://fsprojects.github.io/Paket/)을 통해 패키지를 추가하기 위한 올바른 디렉터리 구조.</span><span class="sxs-lookup"><span data-stu-id="d1f6b-125">The correct directory structure for adding packages via [`Paket`](https://fsprojects.github.io/Paket/).</span></span>
3. <span data-ttu-id="d1f6b-126">[`FAKE`](https://fsharp.github.io/FAKE/)를 통한 크로스 플랫폼 빌드 스크립트.</span><span class="sxs-lookup"><span data-stu-id="d1f6b-126">A cross-platform build script with [`FAKE`](https://fsharp.github.io/FAKE/).</span></span>
4. <span data-ttu-id="d1f6b-127">패키지를 설치하고 종속성을 해결할 수 있는 `paket.exe` 실행 파일.</span><span class="sxs-lookup"><span data-stu-id="d1f6b-127">The `paket.exe` executable that can fetch packages and resolve dependencies for you.</span></span>
5. <span data-ttu-id="d1f6b-128">이 프로젝트를 Git 기반 소스 컨트롤에 추가하려는 경우 `.gitignore` 파일</span><span class="sxs-lookup"><span data-stu-id="d1f6b-128">A `.gitignore` file if you wish to add this project to Git-based source control.</span></span>

## <a name="writing-some-code"></a><span data-ttu-id="d1f6b-129">코드 작성</span><span class="sxs-lookup"><span data-stu-id="d1f6b-129">Writing some code</span></span>

<span data-ttu-id="d1f6b-130">*ClassLibraryDemo* 폴더를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="d1f6b-130">Open the *ClassLibraryDemo* folder.</span></span>  <span data-ttu-id="d1f6b-131">다음과 같은 파일이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="d1f6b-131">You should see the following files:</span></span>

1. <span data-ttu-id="d1f6b-132">클래스가 정의된 F# 구현 파일인`ClassLibraryDemo.fs`</span><span class="sxs-lookup"><span data-stu-id="d1f6b-132">`ClassLibraryDemo.fs`, an F# implementation file with a class defined.</span></span>
2. <span data-ttu-id="d1f6b-133">이 프로젝트를 빌드하는 데 사용되는 F# 프로젝트 파일인 `ClassLibraryDemo.fsproj`</span><span class="sxs-lookup"><span data-stu-id="d1f6b-133">`ClassLibraryDemo.fsproj`, an F# project file used to build this project.</span></span>
3. <span data-ttu-id="d1f6b-134">소스 파일을 로드하는 F# 스크립트 파일인 `Script.fsx`.</span><span class="sxs-lookup"><span data-stu-id="d1f6b-134">`Script.fsx`, an F# script file that loads the source file.</span></span>
4. <span data-ttu-id="d1f6b-135">프로젝트 종속성을 지정하는 Paket 파일인 `paket.references`</span><span class="sxs-lookup"><span data-stu-id="d1f6b-135">`paket.references`, a Paket file that specifies the project dependencies.</span></span>

<span data-ttu-id="d1f6b-136">`Script.fsx`를 열고 마지막에 다음 코드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="d1f6b-136">Open `Script.fsx`, and add the following code at the end of it:</span></span>

[!code-fsharp[ToPigLatin](~/samples/snippets/fsharp/getting-started/to-pig-latin.fsx)]

<span data-ttu-id="d1f6b-137">이 함수는 단어를 [Pig Latin](https://en.wikipedia.org/wiki/Pig_Latin) 형태로 변환합니다.</span><span class="sxs-lookup"><span data-stu-id="d1f6b-137">This function converts a word to a form of [Pig Latin](https://en.wikipedia.org/wiki/Pig_Latin).</span></span> <span data-ttu-id="d1f6b-138">다음으로 F# Interactive (FSI)를 사용하여 평가합니다.</span><span class="sxs-lookup"><span data-stu-id="d1f6b-138">The next step is to evaluate it using F# Interactive (FSI).</span></span>

<span data-ttu-id="d1f6b-139">전체 함수를 강조 표시합니다(11줄 길이여야 함).</span><span class="sxs-lookup"><span data-stu-id="d1f6b-139">Highlight the entire function (it should be 11 lines long).</span></span> <span data-ttu-id="d1f6b-140">강조 표시되면 **Alt** 키를 누른 상태에서 **Enter**를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="d1f6b-140">Once it is highlighted, hold the **Alt** key and hit **Enter**.</span></span> <span data-ttu-id="d1f6b-141">팝업창이 표시되며 다음과 같이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="d1f6b-141">You'll notice a window pop up below, and it should show something like this:</span></span>

![Ionide를 사용한 F# Interactive 출력 예시](./media/getting-started-vscode/vscode-fsi.png)

<span data-ttu-id="d1f6b-143">여기서 다음 세 가지 작업이 수행되었습니다.</span><span class="sxs-lookup"><span data-stu-id="d1f6b-143">This did three things:</span></span>

1. <span data-ttu-id="d1f6b-144">FSI 프로세스를 시작했습니다.</span><span class="sxs-lookup"><span data-stu-id="d1f6b-144">It started the FSI process.</span></span>
2. <span data-ttu-id="d1f6b-145">FSI 프로세스로 강조 표시된 코드를 전송했습니다.</span><span class="sxs-lookup"><span data-stu-id="d1f6b-145">It sent the code you highlighted over the FSI process.</span></span>
3. <span data-ttu-id="d1f6b-146">FSI 프로세스에서 전송한 코드를 평가합니다.</span><span class="sxs-lookup"><span data-stu-id="d1f6b-146">The FSI process evaluated the code you sent over.</span></span>

<span data-ttu-id="d1f6b-147">[함수](../language-reference/functions/index.md)를 전송했으므로 이제 FSI를 사용하여 해당 함수를 호출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d1f6b-147">Because what you sent over was a [function](../language-reference/functions/index.md), you can now call that function with FSI!</span></span> <span data-ttu-id="d1f6b-148">대화형 창에서 다음을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="d1f6b-148">In the interactive window, type the following:</span></span>

```fsharp
toPigLatin "banana";;
```

<span data-ttu-id="d1f6b-149">다음과 같은 결과가 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="d1f6b-149">You should see the following result:</span></span>

```fsharp
val it : string = "ananabay"
```

<span data-ttu-id="d1f6b-150">이제 모음을 첫 글자로 사용해 보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="d1f6b-150">Now, let's try with a vowel as the first letter.</span></span> <span data-ttu-id="d1f6b-151">다음과 같이 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="d1f6b-151">Enter the following:</span></span>

```fsharp
toPigLatin "apple";;
```

<span data-ttu-id="d1f6b-152">다음과 같은 결과가 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="d1f6b-152">You should see the following result:</span></span>

```fsharp
val it : string = "appleyay"
```

<span data-ttu-id="d1f6b-153">예상대로 함수가 작동합니다.</span><span class="sxs-lookup"><span data-stu-id="d1f6b-153">The function appears to be working as expected.</span></span> <span data-ttu-id="d1f6b-154">축하합니다. 첫 번째 F#함수를 Visual Studio Code에서 작성하고 FSI를 사용하여 평가했습니다!</span><span class="sxs-lookup"><span data-stu-id="d1f6b-154">Congratulations, you just wrote your first F# function in Visual Studio Code and evaluated it with FSI!</span></span>

> [!NOTE]
> <span data-ttu-id="d1f6b-155">FSI에서는 `;;`가 라인의 끝입니다.</span><span class="sxs-lookup"><span data-stu-id="d1f6b-155">As you may have noticed, the lines in FSI are terminated with `;;`.</span></span> <span data-ttu-id="d1f6b-156">FSI에서는 여러 줄의 입력을 허용하기 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="d1f6b-156">This is because FSI allows you to enter multiple lines.</span></span> <span data-ttu-id="d1f6b-157">마지막에 있는 `;;`는 FSI가 코드의 마지막이라는 것을 인지할 수 있게 해줍니다.</span><span class="sxs-lookup"><span data-stu-id="d1f6b-157">The `;;` at the end lets FSI know when the code is finished.</span></span>

## <a name="explaining-the-code"></a><span data-ttu-id="d1f6b-158">코드 설명</span><span class="sxs-lookup"><span data-stu-id="d1f6b-158">Explaining the code</span></span>

<span data-ttu-id="d1f6b-159">코드가 실제로 수행 하는 작업을 잘 모르는 경우에는 다음 단계를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="d1f6b-159">If you're not sure about what the code is actually doing, here's a step-by-step.</span></span>

<span data-ttu-id="d1f6b-160">여기서 볼 `toPigLatin` 수 있듯이는 단어를 입력으로 사용 하 고 해당 단어의 Pig 표현으로 변환 하는 함수입니다.</span><span class="sxs-lookup"><span data-stu-id="d1f6b-160">As you can see, `toPigLatin` is a function that takes a word as its input and converts it to a Pig-Latin representation of that word.</span></span> <span data-ttu-id="d1f6b-161">이에 대 한 규칙은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="d1f6b-161">The rules for this are as follows:</span></span>

<span data-ttu-id="d1f6b-162">단어의 첫 문자가 모음으로 시작 하는 경우 단어의 끝에 "yay"를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="d1f6b-162">If the first character in a word starts with a vowel, add "yay" to the end of the word.</span></span> <span data-ttu-id="d1f6b-163">모음으로 시작 하지 않으면 첫 번째 문자를 단어의 끝으로 이동 하 여 "ay"를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="d1f6b-163">If it doesn't start with a vowel, move that first character to the end of the word and add "ay" to it.</span></span>

<span data-ttu-id="d1f6b-164">FSI.EXE에서 다음을 발견할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d1f6b-164">You may have noticed the following in FSI:</span></span>

```fsharp
val toPigLatin : word:string -> string
```

<span data-ttu-id="d1f6b-165">이는를 `toPigLatin` 입력 `string` `word`으로 사용 하 고 다른 `string`를 반환 하는 함수입니다.</span><span class="sxs-lookup"><span data-stu-id="d1f6b-165">This states that `toPigLatin` is a function that takes in a `string` as input (called `word`), and returns another `string`.</span></span> <span data-ttu-id="d1f6b-166">이를 [함수의 형식 서명](https://fsharpforfunandprofit.com/posts/function-signatures/)이라고 하며, 코드를 이해 F# F# 하는 데 해당 키의 기본 부분입니다.</span><span class="sxs-lookup"><span data-stu-id="d1f6b-166">This is known as the [type signature of the function](https://fsharpforfunandprofit.com/posts/function-signatures/), a fundamental piece of F# that's key to understanding F# code.</span></span> <span data-ttu-id="d1f6b-167">또한 Visual Studio Code에서 함수를 가리키면이를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d1f6b-167">You'll also notice this if you hover over the function in Visual Studio Code.</span></span>

<span data-ttu-id="d1f6b-168">함수의 본문에는 다음과 같은 두 가지 요소가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d1f6b-168">In the body of the function, you'll notice two distinct parts:</span></span>

1. <span data-ttu-id="d1f6b-169">지정 된 문자 () `isVowel`가 [패턴 일치](../language-reference/pattern-matching.md)를 통해 제공 된 패턴`c`중 하 나와 일치 하는지 확인 하 여 해당 문자 ()가 모음 인지 여부를 확인 하는 이라는 내부 함수입니다.</span><span class="sxs-lookup"><span data-stu-id="d1f6b-169">An inner function, called `isVowel`, that determines if a given character (`c`) is a vowel by checking if it matches one of the provided patterns via [Pattern Matching](../language-reference/pattern-matching.md):</span></span>

   [!code-fsharp[ToPigLatin](~/samples/snippets/fsharp/getting-started/to-pig-latin.fsx#L2-L6)]

2. <span data-ttu-id="d1f6b-170">첫 번째 문자가 모음 인지 확인 하 고 첫 번째 문자가 모음 인지 여부를 기준으로 입력 문자에서 반환 값을 생성 하는 [식입니다.`if..then..else`](../language-reference/conditional-expressions-if-then-else.md)</span><span class="sxs-lookup"><span data-stu-id="d1f6b-170">An [`if..then..else`](../language-reference/conditional-expressions-if-then-else.md) expression that checks if the first character is a vowel, and constructs a return value out of the input characters based on if the first character was a vowel or not:</span></span>

   [!code-fsharp[ToPigLatin](~/samples/snippets/fsharp/getting-started/to-pig-latin.fsx#L8-L11)]

<span data-ttu-id="d1f6b-171">따라서의 `toPigLatin` 흐름은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="d1f6b-171">The flow of `toPigLatin` is thus:</span></span>

<span data-ttu-id="d1f6b-172">입력 단어의 첫 문자가 모음 인지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="d1f6b-172">Check if the first character of the input word is a vowel.</span></span> <span data-ttu-id="d1f6b-173">이 경우 "yay"를 단어 끝에 연결 합니다.</span><span class="sxs-lookup"><span data-stu-id="d1f6b-173">If it is, attach "yay" to the end of the word.</span></span> <span data-ttu-id="d1f6b-174">그렇지 않으면 첫 번째 문자를 단어의 끝으로 이동 하 여 "ay"를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="d1f6b-174">Otherwise, move that first character to the end of the word and add "ay" to it.</span></span>

<span data-ttu-id="d1f6b-175">이에 대 한 최종 정보는 다음과 같습니다. 다른 많은 언어와 달리 함수에서 반환할 명시적인 명령이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d1f6b-175">There's one final thing to notice about this: there's no explicit instruction to return from the function, unlike many other languages out there.</span></span> <span data-ttu-id="d1f6b-176">가 식 기반 F# 이 고 함수 본문의 마지막 식이 반환 값 이기 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="d1f6b-176">This is because F# is Expression-based, and the last expression in the body of a function is the return value.</span></span> <span data-ttu-id="d1f6b-177">는 `if..then..else` 자체로 식 `then` 이므로 블록의 본문이 `else` 나 블록의 본문은 입력 값에 따라 반환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d1f6b-177">Because `if..then..else` is itself an expression, the body of the `then` block or the body of the `else` block will be returned depending on the input value.</span></span>

## <a name="moving-your-script-code-into-the-implementation-file"></a><span data-ttu-id="d1f6b-178">스크립트 코드를 구현 파일로 이동</span><span class="sxs-lookup"><span data-stu-id="d1f6b-178">Moving your script code into the implementation file</span></span>

<span data-ttu-id="d1f6b-179">이 문서의 이전 섹션에서는 초기 함수를 작성 하 고 FSI.EXE를 F# 사용 하 여 대화형으로 실행 하는 코드를 작성 하는 일반적인 첫 번째 단계를 보여 주었습니다.</span><span class="sxs-lookup"><span data-stu-id="d1f6b-179">The previous sections in this article demonstrated a common first step in writing F# code: writing an initial function and executing it interactively with FSI.</span></span> <span data-ttu-id="d1f6b-180">이를 repl 기반 개발 이라고 하며, 여기서 [repl](https://en.wikipedia.org/wiki/Read%E2%80%93eval%E2%80%93print_loop) 은 "읽기-평가-인쇄 루프"를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="d1f6b-180">This is known as REPL-driven development, where [REPL](https://en.wikipedia.org/wiki/Read%E2%80%93eval%E2%80%93print_loop) stands for "Read-Evaluate-Print Loop".</span></span> <span data-ttu-id="d1f6b-181">작업을 수행할 때까지 기능을 시험해 볼 수 있는 좋은 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="d1f6b-181">It's a great way to experiment with functionality until you have something working.</span></span>

<span data-ttu-id="d1f6b-182">REPL 기반 개발의 다음 단계는 작업 코드를 F# 구현 파일로 이동 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="d1f6b-182">The next step in REPL-driven development is to move working code into an F# implementation file.</span></span> <span data-ttu-id="d1f6b-183">그런 다음 F# 컴파일러에서 실행할 수 있는 어셈블리로 컴파일할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d1f6b-183">It can then be compiled by the F# compiler into an assembly that can be executed.</span></span>

<span data-ttu-id="d1f6b-184">시작 하려면를 엽니다 `ClassLibraryDemo.fs`.</span><span class="sxs-lookup"><span data-stu-id="d1f6b-184">To begin, open `ClassLibraryDemo.fs`.</span></span>  <span data-ttu-id="d1f6b-185">일부 코드는 이미 여기에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d1f6b-185">You'll notice that some code is already in there.</span></span> <span data-ttu-id="d1f6b-186">계속 해 서 클래스 정의를 삭제 하 되, [`namespace`](../language-reference/namespaces.md) 선언을 맨 위에 두어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d1f6b-186">Go ahead and delete the class definition, but make sure to leave the [`namespace`](../language-reference/namespaces.md) declaration at the top.</span></span>

<span data-ttu-id="d1f6b-187">다음으로, 라는 [`module`](../language-reference/modules.md) `PigLatin` 새를 만들고 `toPigLatin` 함수를 다음과 같이 복사 합니다.</span><span class="sxs-lookup"><span data-stu-id="d1f6b-187">Next, create a new [`module`](../language-reference/modules.md) called `PigLatin` and copy the `toPigLatin` function into it as such:</span></span>

[!code-fsharp[ToPigLatin](~/samples/snippets/fsharp/getting-started/pig-latin.fs#L1-L14)]

<span data-ttu-id="d1f6b-188">그런 다음 `Script.fsx` 파일을 다시 열고 전체 `toPigLatin` 함수를 삭제 하지만 파일에서 다음 두 줄을 유지 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d1f6b-188">Next, open the `Script.fsx` file again, and delete the entire `toPigLatin` function, but make sure to keep the following two lines in the file:</span></span>

```fsharp
#load "ClassLibraryDemo.fs"
open ClassLibraryDemo
```

<span data-ttu-id="d1f6b-189">텍스트의 두 줄을 모두 선택 하 고 Alt + Enter를 눌러 FSI.EXE에서 이러한 줄을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="d1f6b-189">Select both lines of text and press Alt+Enter to execute these lines in FSI.</span></span> <span data-ttu-id="d1f6b-190">그러면 Pig 라틴어 라이브러리의 내용이 fsi.exe 프로세스 및 `open` `ClassLibraryDemo` 네임 스페이스에 로드 되어 해당 기능에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d1f6b-190">These will load the contents of the Pig Latin library into the FSI process and `open` the `ClassLibraryDemo` namespace so that you have access to the functionality.</span></span>

<span data-ttu-id="d1f6b-191">그런 다음 fsi.exe 창에서 앞에서 정의한 `PigLatin` 모듈을 사용 하 여 함수를 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="d1f6b-191">Next, in the FSI window, call the function with the `PigLatin` module that you defined earlier:</span></span>

```
> PigLatin.toPigLatin "banana";;
val it : string = "ananabay"
> PigLatin.toPigLatin "apple";;
val it : string = "appleyay"
```

<span data-ttu-id="d1f6b-192">성공</span><span class="sxs-lookup"><span data-stu-id="d1f6b-192">Success!</span></span> <span data-ttu-id="d1f6b-193">이전 처럼 동일한 결과를 얻을 수 있지만 이제는 F# 구현 파일에서 로드 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d1f6b-193">You get the same results as before, but now loaded from an F# implementation file.</span></span> <span data-ttu-id="d1f6b-194">여기서 주요 차이점은 F# 원본 파일이 fsi.exe 뿐만 아니라 어디에서 나 실행할 수 있는 어셈블리로 컴파일되기 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="d1f6b-194">The major difference here is that F# source files are compiled into assemblies that can be executed anywhere, not just in FSI.</span></span>

## <a name="summary"></a><span data-ttu-id="d1f6b-195">요약</span><span class="sxs-lookup"><span data-stu-id="d1f6b-195">Summary</span></span>

<span data-ttu-id="d1f6b-196">이 문서에서는 다음을 배웠습니다.</span><span class="sxs-lookup"><span data-stu-id="d1f6b-196">In this article, you've learned:</span></span>

1. <span data-ttu-id="d1f6b-197">충돌 Ide를 사용 하 여 Visual Studio Code를 설정 하는 방법</span><span class="sxs-lookup"><span data-stu-id="d1f6b-197">How to set up Visual Studio Code with Ionide.</span></span>
2. <span data-ttu-id="d1f6b-198">충돌 Ide를 사용 하 F# 여 첫 번째 프로젝트를 만드는 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="d1f6b-198">How to create your first F# project with Ionide.</span></span>
3. <span data-ttu-id="d1f6b-199">스크립트를 사용 F# 하 여 fsi.exe에서 첫 F# 번째 함수를 작성 하 고이를에서 실행 하는 방법을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="d1f6b-199">How to use F# Scripting to write your first F# function in Ionide and then execute it in FSI.</span></span>
4. <span data-ttu-id="d1f6b-200">스크립트 코드를 F# 소스로 마이그레이션한 다음 fsi.exe에서 해당 코드를 호출 하는 방법을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="d1f6b-200">How to migrate your script code to F# source and then call that code from FSI.</span></span>

<span data-ttu-id="d1f6b-201">이제 Visual Studio Code 및 이상 Ide를 사용 하 F# 여 훨씬 더 많은 코드를 작성할 준비가 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="d1f6b-201">You're now equipped to write much more F# code using Visual Studio Code and Ionide.</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="d1f6b-202">문제 해결</span><span class="sxs-lookup"><span data-stu-id="d1f6b-202">Troubleshooting</span></span>

<span data-ttu-id="d1f6b-203">다음은 발생할 수 있는 특정 문제를 해결할 수 있는 몇 가지 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="d1f6b-203">Here are a few ways you can troubleshoot certain problems that you might run into:</span></span>

1. <span data-ttu-id="d1f6b-204">F# 파일을 디스크에 저장 하 고 Visual Studio Code 작업 영역에 열려 있는 폴더 내에 저장 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d1f6b-204">To get the code editing features of Ionide, your F# files need to be saved to disk and inside of a folder that is open in the Visual Studio Code workspace.</span></span>
2. <span data-ttu-id="d1f6b-205">시스템이 열려 있는 상태에서 시스템을 변경 하거나 Visual Studio Code를 설치한 경우 Visual Studio Code를 다시 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="d1f6b-205">If you've made changes to your system or installed Ionide prerequisites with Visual Studio Code open, restart Visual Studio Code.</span></span>
3. <span data-ttu-id="d1f6b-206">정규화 된 경로 없이 명령줄에서 F# 컴파일러와 F# interactive를 사용할 수 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="d1f6b-206">Check that you can use the F# compiler and F# interactive from the command line without a fully-qualified path.</span></span> <span data-ttu-id="d1f6b-207">이렇게 하려면 F# 컴파일러에 대 한 `fsc` 명령줄을 입력 하 고 `fsi` , 또는 `fsharpi` Windows의 시각적 F# 도구와 Mac/Linux의 Mono를 입력 하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d1f6b-207">You can do so by typing `fsc` in a command line for the F# compiler, and `fsi` or `fsharpi` for the Visual F# tools on Windows and Mono on Mac/Linux, respectively.</span></span>
4. <span data-ttu-id="d1f6b-208">프로젝트 디렉터리에 잘못 된 문자가 있는 경우에는 작동 하지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d1f6b-208">If you have invalid characters in your project directories, Ionide might not work.</span></span>  <span data-ttu-id="d1f6b-209">이 경우 프로젝트 디렉터리의 이름을 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="d1f6b-209">Rename your project directories if this is the case.</span></span>
5. <span data-ttu-id="d1f6b-210">작동 하는 지 여부 Ide 명령이 없으면 [Visual Studio Code 키 바인딩을](https://code.visualstudio.com/docs/customization/keybindings#_customizing-shortcuts) 확인 하 여 실수로 재정의 하 고 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="d1f6b-210">If none of the Ionide commands are working, check your [Visual Studio Code keybindings](https://code.visualstudio.com/docs/customization/keybindings#_customizing-shortcuts) to see if you're overriding them by accident.</span></span>
6. <span data-ttu-id="d1f6b-211">컴퓨터에서 손상 된 ide가 손상 된 경우 어떤 것도 문제가 해결 되지 않으면 컴퓨터에서 디렉터리를 `ionide-fsharp` 제거 하 고 플러그 인 도구 모음을 다시 설치 하세요.</span><span class="sxs-lookup"><span data-stu-id="d1f6b-211">If Ionide is broken on your machine and none of the above has fixed your problem, try removing the `ionide-fsharp` directory on your machine and reinstall the plugin suite.</span></span>

<span data-ttu-id="d1f6b-212">이상 ide는 F# 커뮤니티의 구성원이 빌드하고 유지 관리 하는 오픈 소스 프로젝트입니다.</span><span class="sxs-lookup"><span data-stu-id="d1f6b-212">Ionide is an open source project built and maintained by members of the F# community.</span></span> <span data-ttu-id="d1f6b-213">문제를 보고 하 고 무료 ide-vscode [에 참여 하세요. Fsharp.core GitHub 리포지토리](https://github.com/ionide/ionide-vscode-fsharp).</span><span class="sxs-lookup"><span data-stu-id="d1f6b-213">Please report issues and feel free to contribute at the [Ionide-VSCode: FSharp GitHub repository](https://github.com/ionide/ionide-vscode-fsharp).</span></span>

<span data-ttu-id="d1f6b-214">보고 하는 데 문제가 있는 경우 [문제를 보고할 때 사용할 로그를 가져오는 방법에 대 한 지침](https://github.com/ionide/ionide-vscode-fsharp#how-to-get-logs-for-debugging--issue-reporting)을 따르세요.</span><span class="sxs-lookup"><span data-stu-id="d1f6b-214">If you have an issue to report, please follow [the instructions for getting logs to use when reporting an issue](https://github.com/ionide/ionide-vscode-fsharp#how-to-get-logs-for-debugging--issue-reporting).</span></span>

<span data-ttu-id="d1f6b-215">이상 ide 개발자와 F# 커뮤니티의 [Gitter channel](https://gitter.im/ionide/ionide-project)에서 추가 도움을 요청할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d1f6b-215">You can also ask for further help from the Ionide developers and F# community in the [Ionide Gitter channel](https://gitter.im/ionide/ionide-project).</span></span>

## <a name="next-steps"></a><span data-ttu-id="d1f6b-216">다음 단계</span><span class="sxs-lookup"><span data-stu-id="d1f6b-216">Next steps</span></span>

<span data-ttu-id="d1f6b-217">F# 및 해당 언어의 기능에 대해 자세히 알아보려면 [둘러보기 F# ](../tour.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="d1f6b-217">To learn more about F# and the features of the language, check out [Tour of F#](../tour.md).</span></span>
