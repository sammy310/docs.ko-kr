---
title: Visual Studio Code에서 F# 시작
description: Visual Studio Code와 Ionide 플러그인 도구 모음으로 F#을 사용하는 방법을 알아봅니다.
ms.date: 12/23/2018
ms.openlocfilehash: 7c2ecab14b3351d441249e7fc7cb3188a4ee7eba
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61949552"
---
# <a name="get-started-with-f-in-visual-studio-code"></a><span data-ttu-id="c786c-103">Visual Studio Code에서 F# 시작</span><span class="sxs-lookup"><span data-stu-id="c786c-103">Get Started with F# in Visual Studio Code</span></span>

<span data-ttu-id="c786c-104">[Visual Studio Code](https://code.visualstudio.com)에서 [Ionide 플러그인](https://marketplace.visualstudio.com/items?itemName=Ionide.Ionide-fsharp)을 사용하여 F# 코드를 작성하면 IntelliSense와 기본적인 코드 리팩토링이 가능한 경량이면서 다양한 플랫폼에서 사용할 수 있는 IDE(Integrated Development Environment) 환경을 얻을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c786c-104">You can write F# in [Visual Studio Code](https://code.visualstudio.com) with the [Ionide plugin](https://marketplace.visualstudio.com/items?itemName=Ionide.Ionide-fsharp) to get a great cross-platform, lightweight Integrated Development Environment (IDE) experience with IntelliSense and basic code refactorings.</span></span> <span data-ttu-id="c786c-105">이 플러그인을 더 자세히 알고 싶다면 [Ionide.io](http://ionide.io)를 방문합니다.</span><span class="sxs-lookup"><span data-stu-id="c786c-105">Visit [Ionide.io](http://ionide.io) to learn more about the plugin.</span></span>

<span data-ttu-id="c786c-106">시작하려면 [F#과 Ionide 플러그인의 설치](install-fsharp.md#install-f-with-visual-studio-code)가 올바르게 되어있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="c786c-106">To begin, ensure that you have [F# and the Ionide plugin correctly installed](install-fsharp.md#install-f-with-visual-studio-code).</span></span>

> [!NOTE]
> <span data-ttu-id="c786c-107">Ionide는 플랫폼 간 호환성 문제가 발생할 수 있는 닷넷 코어가 아닌 .NET Framework F# 프로젝트를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="c786c-107">Ionide will generate .NET Framework F# projects, not dotnet core, which can have cross-platform compatibility issues.</span></span> <span data-ttu-id="c786c-108">**Linux** 또는 **OSX**에서 실행하는 경우 시작하기 쉬운 방법은 [명령줄 도구](https://docs.microsoft.com/en-us/dotnet/fsharp/get-started/get-started-command-line)를 사용하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="c786c-108">If you are running on **Linux** or **OSX**, a simpler way to get started is to use the [command line tools](https://docs.microsoft.com/en-us/dotnet/fsharp/get-started/get-started-command-line).</span></span>

## <a name="creating-your-first-project-with-ionide"></a><span data-ttu-id="c786c-109">Ionide를 사용하여 첫 번째 프로젝트 만들기</span><span class="sxs-lookup"><span data-stu-id="c786c-109">Creating your first project with Ionide</span></span>

<span data-ttu-id="c786c-110">새 F# 프로젝트를 생성하기 위해 새 폴더(원하는 이름을 지정할 수 있습니다)에서 Visual Studio Code를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="c786c-110">To create a new F# project, open Visual Studio Code in a new folder (you can name it whatever you like).</span></span>

<span data-ttu-id="c786c-111">다음으로, 명령 팔레트를 엽니다 (**보기 > 명령 팔레트**) 다음을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="c786c-111">Next, open the command palette (**View > Command Palette**) and type the following:</span></span>

```
> F# new project
```

<span data-ttu-id="c786c-112">[FORGE](https://github.com/fsharp-editing/Forge) 프로젝트에 의해 동작합니다.</span><span class="sxs-lookup"><span data-stu-id="c786c-112">This is powered by the [FORGE](https://github.com/fsharp-editing/Forge) project.</span></span>

> [!NOTE]
> <span data-ttu-id="c786c-113">템플릿 옵션을 보이지 않으면 명령 팔레트에서 다음 명령을 실행 하 여 서식 파일을 새로 고쳐 보세요. `>F#: Refresh Project Templates`합니다.</span><span class="sxs-lookup"><span data-stu-id="c786c-113">If you don't see template options, try refreshing templates by running the following command in the Command Palette: `>F#: Refresh Project Templates`.</span></span>

<span data-ttu-id="c786c-114">선택 "F#: 새 프로젝트 "를 눌러 **Enter**합니다.</span><span class="sxs-lookup"><span data-stu-id="c786c-114">Select "F#: New Project" by hitting **Enter**.</span></span> <span data-ttu-id="c786c-115">이 프로젝트 템플릿을 선택 하는 다음 단계를 안내 합니다.</span><span class="sxs-lookup"><span data-stu-id="c786c-115">This takes you to the next step, which is for selecting a project template.</span></span>

<span data-ttu-id="c786c-116">`classlib` 템플릿을 선택하고 **Enter**를 칩니다.</span><span class="sxs-lookup"><span data-stu-id="c786c-116">Pick the `classlib` template and hit **Enter**.</span></span>

<span data-ttu-id="c786c-117">그런 다음에 프로젝트를 생성하기 위한 디렉터리를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="c786c-117">Next, pick a directory to create the project in.</span></span> <span data-ttu-id="c786c-118">비워 두면 현재 디렉터리를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="c786c-118">If you leave it blank, it uses the current directory.</span></span>

<span data-ttu-id="c786c-119">마지막으로, 마지막 단계에서 프로젝트를 이름을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="c786c-119">Finally, name your project in the final step.</span></span> <span data-ttu-id="c786c-120">F#사용 하 여 [파스칼식 대 / 소문자](http://c2.com/cgi/wiki?PascalCase) 프로젝트 이름에 대 한 합니다.</span><span class="sxs-lookup"><span data-stu-id="c786c-120">F# uses [Pascal case](http://c2.com/cgi/wiki?PascalCase) for project names.</span></span> <span data-ttu-id="c786c-121">이 문서에서는 `ClassLibraryDemo` 이름으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="c786c-121">This article uses `ClassLibraryDemo` as the name.</span></span> <span data-ttu-id="c786c-122">프로젝트에 대해 원하는 이름을 입력 한 후 적중 **Enter**합니다.</span><span class="sxs-lookup"><span data-stu-id="c786c-122">Once you've entered the name you want for your project, hit **Enter**.</span></span>

<span data-ttu-id="c786c-123">이전 단계를 수행한 경우 Visual Studio 코드에서 작업 영역의 왼쪽에 있는 다음 표시할 얻게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c786c-123">If you followed the previous step, you should get the Visual Studio Code Workspace on the left-hand side to appear with the following:</span></span>

1. <span data-ttu-id="c786c-124">F# 프로젝트 자체는 `ClassLibraryDemo` 폴더 하위에 존재합니다.</span><span class="sxs-lookup"><span data-stu-id="c786c-124">The F# project itself, underneath the `ClassLibraryDemo` folder.</span></span>
2. <span data-ttu-id="c786c-125">통해 패키지를 추가 하기 위한 올바른 디렉터리 구조 [ `Paket` ](https://fsprojects.github.io/Paket/)합니다.</span><span class="sxs-lookup"><span data-stu-id="c786c-125">The correct directory structure for adding packages via [`Paket`](https://fsprojects.github.io/Paket/).</span></span>
3. <span data-ttu-id="c786c-126">[`FAKE`](https://fsharp.github.io/FAKE/)를 통한 크로스 플랫폼 빌드 스크립트.</span><span class="sxs-lookup"><span data-stu-id="c786c-126">A cross-platform build script with [`FAKE`](https://fsharp.github.io/FAKE/).</span></span>
4. <span data-ttu-id="c786c-127">패키지를 설치하고 종속성을 해결할 수 있는 `paket.exe` 실행 파일.</span><span class="sxs-lookup"><span data-stu-id="c786c-127">The `paket.exe` executable that can fetch packages and resolve dependencies for you.</span></span>
5. <span data-ttu-id="c786c-128">이 프로젝트를 Git 기반 소스 컨트롤에 추가하려는 경우 `.gitignore` 파일</span><span class="sxs-lookup"><span data-stu-id="c786c-128">A `.gitignore` file if you wish to add this project to Git-based source control.</span></span>

## <a name="writing-some-code"></a><span data-ttu-id="c786c-129">코드 작성</span><span class="sxs-lookup"><span data-stu-id="c786c-129">Writing some code</span></span>

<span data-ttu-id="c786c-130">*ClassLibraryDemo* 폴더를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="c786c-130">Open the *ClassLibraryDemo* folder.</span></span>  <span data-ttu-id="c786c-131">다음과 같은 파일이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="c786c-131">You should see the following files:</span></span>

1. <span data-ttu-id="c786c-132">클래스가 정의된 F# 구현 파일인`ClassLibraryDemo.fs`</span><span class="sxs-lookup"><span data-stu-id="c786c-132">`ClassLibraryDemo.fs`, an F# implementation file with a class defined.</span></span>
2. <span data-ttu-id="c786c-133">이 프로젝트를 빌드하는 데 사용되는 F# 프로젝트 파일인 `ClassLibraryDemo.fsproj`</span><span class="sxs-lookup"><span data-stu-id="c786c-133">`ClassLibraryDemo.fsproj`, an F# project file used to build this project.</span></span>
3. <span data-ttu-id="c786c-134">`Script.fsx`에 F# 소스 파일을 로드 하는 스크립트 파일입니다.</span><span class="sxs-lookup"><span data-stu-id="c786c-134">`Script.fsx`, an F# script file that loads the source file.</span></span>
4. <span data-ttu-id="c786c-135">프로젝트 종속성을 지정하는 Paket 파일인 `paket.references`</span><span class="sxs-lookup"><span data-stu-id="c786c-135">`paket.references`, a Paket file that specifies the project dependencies.</span></span>

<span data-ttu-id="c786c-136">열기 `Script.fsx`의 끝에 다음 코드를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="c786c-136">Open `Script.fsx`, and add the following code at the end of it:</span></span>

[!code-fsharp[ToPigLatin](../../../samples/snippets/fsharp/getting-started/to-pig-latin.fsx)]

<span data-ttu-id="c786c-137">이 함수는 형태의 단어 변환 [Pig Latin](https://en.wikipedia.org/wiki/Pig_Latin)합니다.</span><span class="sxs-lookup"><span data-stu-id="c786c-137">This function converts a word to a form of [Pig Latin](https://en.wikipedia.org/wiki/Pig_Latin).</span></span> <span data-ttu-id="c786c-138">다음 단계를 사용 하 여 평가 하는 F# 대화형 (FSI).</span><span class="sxs-lookup"><span data-stu-id="c786c-138">The next step is to evaluate it using F# Interactive (FSI).</span></span>

<span data-ttu-id="c786c-139">(11 줄 이어야 함)은 전체 함수를 강조 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="c786c-139">Highlight the entire function (it should be 11 lines long).</span></span> <span data-ttu-id="c786c-140">이 강조 표시 되 면 저장 합니다 **Alt** 키 및 적중 **Enter**합니다.</span><span class="sxs-lookup"><span data-stu-id="c786c-140">Once it is highlighted, hold the **Alt** key and hit **Enter**.</span></span> <span data-ttu-id="c786c-141">아래 팝업 창을 보면 하 고 다음과 같이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c786c-141">You'll notice a window pop up below, and it should show something like this:</span></span>

![예 F# 대화형 Ionide를 사용 하 여 출력](media/getting-started-vscode/vscode-fsi.png)

<span data-ttu-id="c786c-143">이 세 가지 작업을 수행 했습니다.</span><span class="sxs-lookup"><span data-stu-id="c786c-143">This did three things:</span></span>

1. <span data-ttu-id="c786c-144">FSI 프로세스를 시작 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="c786c-144">It started the FSI process.</span></span>
2. <span data-ttu-id="c786c-145">강조 표시 된 코드 FSI 프로세스를 통해 보낸 합니다.</span><span class="sxs-lookup"><span data-stu-id="c786c-145">It sent the code you highlighted over the FSI process.</span></span>
3. <span data-ttu-id="c786c-146">FSI 프로세스를 통해 전송 된 코드를 평가 합니다.</span><span class="sxs-lookup"><span data-stu-id="c786c-146">The FSI process evaluated the code you sent over.</span></span>

<span data-ttu-id="c786c-147">통해 전달 되는 내용 때문에 [함수](../language-reference/functions/index.md), 이제 FSI 사용 하 여 해당 함수를 호출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c786c-147">Because what you sent over was a [function](../language-reference/functions/index.md), you can now call that function with FSI!</span></span> <span data-ttu-id="c786c-148">대화형 창에서 다음을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="c786c-148">In the interactive window, type the following:</span></span>

```fsharp
toPigLatin "banana";;
```

<span data-ttu-id="c786c-149">다음과 같은 결과가 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="c786c-149">You should see the following result:</span></span>

```fsharp
val it : string = "ananabay"
```

<span data-ttu-id="c786c-150">이제 첫 번째 문자로 모음을 사용 하 여 시도해 보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="c786c-150">Now, let's try with a vowel as the first letter.</span></span> <span data-ttu-id="c786c-151">다음을 입력하세요.</span><span class="sxs-lookup"><span data-stu-id="c786c-151">Enter the following:</span></span>

```fsharp
toPigLatin "apple";;
```

<span data-ttu-id="c786c-152">다음과 같은 결과가 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="c786c-152">You should see the following result:</span></span>

```fsharp
val it : string = "appleyay"
```

<span data-ttu-id="c786c-153">예상 대로 작동 하는 함수 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c786c-153">The function appears to be working as expected.</span></span> <span data-ttu-id="c786c-154">축 하 여 방금 작성 한 첫 번째 F# Visual Studio Code에서 함수 및 FSI를 사용 하 여 평가!</span><span class="sxs-lookup"><span data-stu-id="c786c-154">Congratulations, you just wrote your first F# function in Visual Studio Code and evaluated it with FSI!</span></span>

> [!NOTE]
> <span data-ttu-id="c786c-155">FSI의 선이 끝납니다 했을 수에 따라 `;;`합니다.</span><span class="sxs-lookup"><span data-stu-id="c786c-155">As you may have noticed, the lines in FSI are terminated with `;;`.</span></span> <span data-ttu-id="c786c-156">즉, FSI을 사용 하면 여러 줄을 입력할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c786c-156">This is because FSI allows you to enter multiple lines.</span></span> <span data-ttu-id="c786c-157">`;;` 끝 FSI 코드가 완료 되었을 때를 알 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c786c-157">The `;;` at the end lets FSI know when the code is finished.</span></span>

## <a name="explaining-the-code"></a><span data-ttu-id="c786c-158">코드를 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="c786c-158">Explaining the code</span></span>

<span data-ttu-id="c786c-159">코드를 실제로 수행 하는 방법에 대 한 잘 모르는 경우 다음을 단계별은입니다.</span><span class="sxs-lookup"><span data-stu-id="c786c-159">If you're not sure about what the code is actually doing, here's a step-by-step.</span></span>

<span data-ttu-id="c786c-160">알 수 있듯이 `toPigLatin` 함수는 입력으로 단어 및 단어의 Pig Latin 표현으로 변환 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="c786c-160">As you can see, `toPigLatin` is a function that takes a word as its input and converts it to a Pig-Latin representation of that word.</span></span> <span data-ttu-id="c786c-161">이 대 한 규칙 아래와 같습니다.</span><span class="sxs-lookup"><span data-stu-id="c786c-161">The rules for this are as follows:</span></span>

<span data-ttu-id="c786c-162">단어의 첫 번째 문자 모음에서 시작 하는 경우 "yay" 라는 단어의 끝에 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="c786c-162">If the first character in a word starts with a vowel, add "yay" to the end of the word.</span></span> <span data-ttu-id="c786c-163">모음을 사용 하 여 시작 되지 않으면 첫 번째 문자는 단어의 끝으로 이동 및 "살펴보고"를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="c786c-163">If it doesn't start with a vowel, move that first character to the end of the word and add "ay" to it.</span></span>

<span data-ttu-id="c786c-164">FSI에서 다음을 알 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c786c-164">You may have noticed the following in FSI:</span></span>

```fsharp
val toPigLatin : word:string -> string
```

<span data-ttu-id="c786c-165">이 나타내는 `toPigLatin` 에서 사용 하는 함수는를 `string` 입력으로 (호출 `word`)를 반환 하는 값 및 `string`합니다.</span><span class="sxs-lookup"><span data-stu-id="c786c-165">This states that `toPigLatin` is a function that takes in a `string` as input (called `word`), and returns another `string`.</span></span> <span data-ttu-id="c786c-166">이 [함수 형식 시그니처](https://fsharpforfunandprofit.com/posts/function-signatures/), 기본 부분 F# 이해 하기 위한 열쇠입니다 F# 코드.</span><span class="sxs-lookup"><span data-stu-id="c786c-166">This is known as the [type signature of the function](https://fsharpforfunandprofit.com/posts/function-signatures/), a fundamental piece of F# that's key to understanding F# code.</span></span> <span data-ttu-id="c786c-167">또한 보면이 Visual Studio Code에서 함수를 가리키면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c786c-167">You'll also notice this if you hover over the function in Visual Studio Code.</span></span>

<span data-ttu-id="c786c-168">함수 본문에는 두 가지 부분 알려줍니다.</span><span class="sxs-lookup"><span data-stu-id="c786c-168">In the body of the function, you'll notice two distinct parts:</span></span>

1. <span data-ttu-id="c786c-169">내부 함수 호출 `isVowel`를 결정 하는 경우 지정 된 문자 (`c`)를 통해 제공 된 패턴 중 하 나와 일치 하는 경우를 확인 하 여이 모음인 [패턴 일치](../language-reference/pattern-matching.md):</span><span class="sxs-lookup"><span data-stu-id="c786c-169">An inner function, called `isVowel`, that determines if a given character (`c`) is a vowel by checking if it matches one of the provided patterns via [Pattern Matching](../language-reference/pattern-matching.md):</span></span>

   [!code-fsharp[ToPigLatin](../../../samples/snippets/fsharp/getting-started/to-pig-latin.fsx#L2-L6)]

2. <span data-ttu-id="c786c-170">[ `if..then..else` ](../language-reference/conditional-expressions-if-then-else.md) 첫 번째 문자에 모음이 오는 형태로 되며 반환 값에서 문자를 입력된 하는 구문 인지에 따라 첫 번째 문자를 확인 하는 식 모음 되었거나:</span><span class="sxs-lookup"><span data-stu-id="c786c-170">An [`if..then..else`](../language-reference/conditional-expressions-if-then-else.md) expression that checks if the first character is a vowel, and constructs a return value out of the input characters based on if the first character was a vowel or not:</span></span>

   [!code-fsharp[ToPigLatin](../../../samples/snippets/fsharp/getting-started/to-pig-latin.fsx#L8-L11)]

<span data-ttu-id="c786c-171">흐름을 `toPigLatin` 따라서:</span><span class="sxs-lookup"><span data-stu-id="c786c-171">The flow of `toPigLatin` is thus:</span></span>

<span data-ttu-id="c786c-172">입력된 된 단어의 첫 번째 문자에 모음이 오는 형태로 인지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="c786c-172">Check if the first character of the input word is a vowel.</span></span> <span data-ttu-id="c786c-173">이 경우 "yay" 라는 단어의 끝에 연결 합니다.</span><span class="sxs-lookup"><span data-stu-id="c786c-173">If it is, attach "yay" to the end of the word.</span></span> <span data-ttu-id="c786c-174">이 고, 그렇지 첫 번째 문자는 단어의 끝으로 이동 하 고를 "살펴보고"를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="c786c-174">Otherwise, move that first character to the end of the word and add "ay" to it.</span></span>

<span data-ttu-id="c786c-175">이 주의 해야 할 사항이 하나는:는 여러 다른 언어와 달리 가지 함수에서 반환할 명시적 명령 없습니다.</span><span class="sxs-lookup"><span data-stu-id="c786c-175">There's one final thing to notice about this: there's no explicit instruction to return from the function, unlike many other languages out there.</span></span> <span data-ttu-id="c786c-176">왜냐하면 F# 이 식을 기반 고 함수 본문의 마지막 식 반환 값입니다.</span><span class="sxs-lookup"><span data-stu-id="c786c-176">This is because F# is Expression-based, and the last expression in the body of a function is the return value.</span></span> <span data-ttu-id="c786c-177">때문에 `if..then..else` 는 식의 본문 자체를 `then` 블록 또는 본문에는 `else` 블록 입력된 값에 따라 반환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c786c-177">Because `if..then..else` is itself an expression, the body of the `then` block or the body of the `else` block will be returned depending on the input value.</span></span>

## <a name="moving-your-script-code-into-the-implementation-file"></a><span data-ttu-id="c786c-178">스크립트 코드 구현 파일로 이동</span><span class="sxs-lookup"><span data-stu-id="c786c-178">Moving your script code into the implementation file</span></span>

<span data-ttu-id="c786c-179">이 문서의 이전 섹션의에서 일반적인 첫 번째 단계를 보여 줍니다. F# 코드: 초기 함수를 작성 및 FSI를 사용 하 여 대화형으로 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="c786c-179">The previous sections in this article demonstrated a common first step in writing F# code: writing an initial function and executing it interactively with FSI.</span></span> <span data-ttu-id="c786c-180">REPL 기반 개발 이라고 위치 [REPL](https://en.wikipedia.org/wiki/Read%E2%80%93eval%E2%80%93print_loop) "읽기-평가-인쇄 루프"는 의미입니다.</span><span class="sxs-lookup"><span data-stu-id="c786c-180">This is known as REPL-driven development, where [REPL](https://en.wikipedia.org/wiki/Read%E2%80%93eval%E2%80%93print_loop) stands for "Read-Evaluate-Print Loop".</span></span> <span data-ttu-id="c786c-181">작업 항목 수 있을 때까지 기능을 사용 하 여 실험에 유용한 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="c786c-181">It's a great way to experiment with functionality until you have something working.</span></span>

<span data-ttu-id="c786c-182">REPL 기반 개발의 다음 단계를 작업 코드를 이동 하는 것을 F# 구현 파일입니다.</span><span class="sxs-lookup"><span data-stu-id="c786c-182">The next step in REPL-driven development is to move working code into an F# implementation file.</span></span> <span data-ttu-id="c786c-183">다음으로 컴파일할 수는 F# 를 실행할 수 있는 어셈블리로 컴파일러.</span><span class="sxs-lookup"><span data-stu-id="c786c-183">It can then be compiled by the F# compiler into an assembly that can be executed.</span></span>

<span data-ttu-id="c786c-184">시작 하려면 열기 `ClassLibraryDemo.fs`합니다.</span><span class="sxs-lookup"><span data-stu-id="c786c-184">To begin, open `ClassLibraryDemo.fs`.</span></span>  <span data-ttu-id="c786c-185">일부 코드가 이미 있는 것을 알 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c786c-185">You'll notice that some code is already in there.</span></span> <span data-ttu-id="c786c-186">계속 해 서 클래스 정의 삭제 하며 유지 해야 합니다 [ `namespace` ](../language-reference/namespaces.md) 맨 위에 있는 선언 합니다.</span><span class="sxs-lookup"><span data-stu-id="c786c-186">Go ahead and delete the class definition, but make sure to leave the [`namespace`](../language-reference/namespaces.md) declaration at the top.</span></span>

<span data-ttu-id="c786c-187">다음으로 새를 만듭니다 [ `module` ](../language-reference/modules.md) 호출 `PigLatin` 복사는 `toPigLatin` 같이 함수에:</span><span class="sxs-lookup"><span data-stu-id="c786c-187">Next, create a new [`module`](../language-reference/modules.md) called `PigLatin` and copy the `toPigLatin` function into it as such:</span></span>

[!code-fsharp[ToPigLatin](../../../samples/snippets/fsharp/getting-started/pig-latin.fs#L1-L14)]

<span data-ttu-id="c786c-188">을 엽니다는 `Script.fsx` 다시 파일 및 전체 삭제 `toPigLatin` 하지만 파일에 다음 두 줄을 유지 하도록 확인:</span><span class="sxs-lookup"><span data-stu-id="c786c-188">Next, open the `Script.fsx` file again, and delete the entire `toPigLatin` function, but make sure to keep the following two lines in the file:</span></span>

```fsharp
#load "ClassLibraryDemo.fs"
open ClassLibraryDemo
```

<span data-ttu-id="c786c-189">텍스트 줄이 모두를 선택 하 고 FSI에서 다음이 줄을 실행 하려면 Alt + Enter 키를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="c786c-189">Select both lines of text and press Alt+Enter to execute these lines in FSI.</span></span> <span data-ttu-id="c786c-190">Pig Latin 라이브러리의 내용을 FSI 프로세스로 로드 됩니다 이러한 및 `open` 는 `ClassLibraryDemo` 네임 스페이스 기능에 액세스할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="c786c-190">These will load the contents of the Pig Latin library into the FSI process and `open` the `ClassLibraryDemo` namespace so that you have access to the functionality.</span></span>

<span data-ttu-id="c786c-191">그런 다음 FSI 창에서 사용 하 여 함수를 호출 합니다 `PigLatin` 이전에 정의한 모듈:</span><span class="sxs-lookup"><span data-stu-id="c786c-191">Next, in the FSI window, call the function with the `PigLatin` module that you defined earlier:</span></span>

```
> PigLatin.toPigLatin "banana";;
val it : string = "ananabay"
> PigLatin.toPigLatin "apple";;
val it : string = "appleyay"
```

<span data-ttu-id="c786c-192">성공</span><span class="sxs-lookup"><span data-stu-id="c786c-192">Success!</span></span> <span data-ttu-id="c786c-193">동일한 결과 얻게에서 로드 하지만, 이제는 F# 구현 파일입니다.</span><span class="sxs-lookup"><span data-stu-id="c786c-193">You get the same results as before, but now loaded from an F# implementation file.</span></span> <span data-ttu-id="c786c-194">여기서 주요 차이점은 F# 소스 파일이 FSI에서 뿐 아니라 어디서 나 실행할 수 있는 어셈블리에 컴파일됩니다.</span><span class="sxs-lookup"><span data-stu-id="c786c-194">The major difference here is that F# source files are compiled into assemblies that can be executed anywhere, not just in FSI.</span></span>

## <a name="summary"></a><span data-ttu-id="c786c-195">요약</span><span class="sxs-lookup"><span data-stu-id="c786c-195">Summary</span></span>

<span data-ttu-id="c786c-196">이 문서에서는 알아보았습니다.</span><span class="sxs-lookup"><span data-stu-id="c786c-196">In this article, you've learned:</span></span>

1. <span data-ttu-id="c786c-197">Ionide 사용 하 여 Visual Studio Code를 설정 하는 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="c786c-197">How to set up Visual Studio Code with Ionide.</span></span>
2. <span data-ttu-id="c786c-198">첫 번째를 만드는 방법 F# Ionide 사용 하 여 프로젝트입니다.</span><span class="sxs-lookup"><span data-stu-id="c786c-198">How to create your first F# project with Ionide.</span></span>
3. <span data-ttu-id="c786c-199">사용 하는 방법 F# 첫 번째 쓸 스크립팅 F# Ionide에서 작동 하 고 FSI에서 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="c786c-199">How to use F# Scripting to write your first F# function in Ionide and then execute it in FSI.</span></span>
4. <span data-ttu-id="c786c-200">스크립트 코드를 마이그레이션하는 방법 F# 원본 및 다음 FSI에서 해당 코드를 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="c786c-200">How to migrate your script code to F# source and then call that code from FSI.</span></span>

<span data-ttu-id="c786c-201">많은 쓸 엔드가 이제는 F# Visual Studio Code 및 Ionide를 사용 하는 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="c786c-201">You're now equipped to write much more F# code using Visual Studio Code and Ionide.</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="c786c-202">문제 해결</span><span class="sxs-lookup"><span data-stu-id="c786c-202">Troubleshooting</span></span>

<span data-ttu-id="c786c-203">여기 몇 가지 방법으로에 실행 될 수 있는 특정 문제를 해결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c786c-203">Here are a few ways you can troubleshoot certain problems that you might run into:</span></span>

1. <span data-ttu-id="c786c-204">Ionide의 기능을 편집 하는 코드를 가져오려면 사용자 F# 파일은 Visual Studio Code 작업 영역에 열려 있는 폴더 내에서 디스크에 저장 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c786c-204">To get the code editing features of Ionide, your F# files need to be saved to disk and inside of a folder that is open in the Visual Studio Code workspace.</span></span>
2. <span data-ttu-id="c786c-205">시스템 변경 내용을 적용 하거나 열려 있는 Visual Studio Code를 사용 하 여 Ionide 필수 구성 요소를 설치, Visual Studio Code를 다시 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="c786c-205">If you've made changes to your system or installed Ionide prerequisites with Visual Studio Code open, restart Visual Studio Code.</span></span>
3. <span data-ttu-id="c786c-206">사용할 수 있는지 확인 합니다 F# 컴파일러 및 F# 정규화 된 경로 사용 하지 않고 명령줄에서 대화형입니다.</span><span class="sxs-lookup"><span data-stu-id="c786c-206">Check that you can use the F# compiler and F# interactive from the command line without a fully-qualified path.</span></span> <span data-ttu-id="c786c-207">입력 하 여 수행할 수 `fsc` 에 대 한 명령줄에는 F# 컴파일러, 및 `fsi` 또는 `fsharpi` 시각적 개체에 대 한 F# 각각 Windows 및 linux/Mac에서 Mono에서 도구.</span><span class="sxs-lookup"><span data-stu-id="c786c-207">You can do so by typing `fsc` in a command line for the F# compiler, and `fsi` or `fsharpi` for the Visual F# tools on Windows and Mono on Mac/Linux, respectively.</span></span>
4. <span data-ttu-id="c786c-208">잘못 된 문자가 프로젝트 디렉터리에 있는 Ionide 작동 하지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c786c-208">If you have invalid characters in your project directories, Ionide might not work.</span></span>  <span data-ttu-id="c786c-209">이 경우 프로젝트 디렉터리를 이름을 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="c786c-209">Rename your project directories if this is the case.</span></span>
5. <span data-ttu-id="c786c-210">Ionide 명령의 none으로 작업 하는 경우 확인 프로그램 [Visual Studio Code keybindings](https://code.visualstudio.com/docs/customization/keybindings#_customizing-shortcuts) 확인 하는 경우 실수로 재정의 하 고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c786c-210">If none of the Ionide commands are working, check your [Visual Studio Code keybindings](https://code.visualstudio.com/docs/customization/keybindings#_customizing-shortcuts) to see if you're overriding them by accident.</span></span>
6. <span data-ttu-id="c786c-211">Ionide 컴퓨터 손상 되었습니다. 문제는 수정 사항이 제거해 봅니다는 `ionide-fsharp` 컴퓨터에 디렉터리 및 플러그 인 도구 모음을 다시 설치 합니다.</span><span class="sxs-lookup"><span data-stu-id="c786c-211">If Ionide is broken on your machine and none of the above has fixed your problem, try removing the `ionide-fsharp` directory on your machine and reinstall the plugin suite.</span></span>

<span data-ttu-id="c786c-212">Ionide는 오픈 소스 프로젝트 작성 및의 멤버에 의해 유지 관리는 F# 커뮤니티입니다.</span><span class="sxs-lookup"><span data-stu-id="c786c-212">Ionide is an open source project built and maintained by members of the F# community.</span></span> <span data-ttu-id="c786c-213">문제를 보고 하 고 자유롭게에 기여 하세요는 [Ionide VSCode: FSharp GitHub 리포지토리](https://github.com/ionide/ionide-vscode-fsharp)합니다.</span><span class="sxs-lookup"><span data-stu-id="c786c-213">Please report issues and feel free to contribute at the [Ionide-VSCode: FSharp GitHub repository](https://github.com/ionide/ionide-vscode-fsharp).</span></span>

<span data-ttu-id="c786c-214">보고서에 문제가 있다면 따르세요 [문제를 보고할 때 사용 하 여 로그를 가져오는 데 필요한 지침](https://github.com/ionide/ionide-vscode-fsharp#how-to-get-logs-for-debugging--issue-reporting)합니다.</span><span class="sxs-lookup"><span data-stu-id="c786c-214">If you have an issue to report, please follow [the instructions for getting logs to use when reporting an issue](https://github.com/ionide/ionide-vscode-fsharp#how-to-get-logs-for-debugging--issue-reporting).</span></span>

<span data-ttu-id="c786c-215">Ionide 개발자가 자세한 도움말도 요청할 수 있습니다 하 고 F# 커뮤니티에는 [Ionide Gitter 채널](https://gitter.im/ionide/ionide-project)합니다.</span><span class="sxs-lookup"><span data-stu-id="c786c-215">You can also ask for further help from the Ionide developers and F# community in the [Ionide Gitter channel](https://gitter.im/ionide/ionide-project).</span></span>

## <a name="next-steps"></a><span data-ttu-id="c786c-216">다음 단계</span><span class="sxs-lookup"><span data-stu-id="c786c-216">Next steps</span></span>

<span data-ttu-id="c786c-217">에 대 한 자세한 내용은 F# 언어의 기능을 확인 하 고 [둘러보기 F# ](../tour.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="c786c-217">To learn more about F# and the features of the language, check out [Tour of F#](../tour.md).</span></span>
