---
title: Visual Studio F# 에서 시작 하기
description: Visual Studio에서를 F# 사용 하는 방법을 알아봅니다.
ms.date: 07/03/2018
ms.openlocfilehash: 80b4fc5b7631eace719832fe32003cad578ead27
ms.sourcegitcommit: 93762e1a0dae1b5f64d82eebb7b705a6d566d839
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/27/2019
ms.locfileid: "74552824"
---
# <a name="get-started-with-f-in-visual-studio"></a><span data-ttu-id="96961-103">Visual Studio F# 에서 시작 하기</span><span class="sxs-lookup"><span data-stu-id="96961-103">Get started with F# in Visual Studio</span></span>

<span data-ttu-id="96961-104">F#그리고 visual Studio F# IDE에서 비주얼 도구가 지원 됩니다.</span><span class="sxs-lookup"><span data-stu-id="96961-104">F# and the Visual F# tooling are supported in the Visual Studio IDE.</span></span>

<span data-ttu-id="96961-105">먼저를 [사용 하 여 F#Visual Studio를 설치 ](install-fsharp.md#install-f-with-visual-studio)했는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="96961-105">To begin, ensure that you have [Visual Studio installed with F#](install-fsharp.md#install-f-with-visual-studio).</span></span>

## <a name="creating-a-console-application"></a><span data-ttu-id="96961-106">콘솔 응용 프로그램 만들기</span><span class="sxs-lookup"><span data-stu-id="96961-106">Creating a console application</span></span>

<span data-ttu-id="96961-107">Visual Studio의 가장 기본적인 프로젝트 중 하나는 콘솔 응용 프로그램입니다.</span><span class="sxs-lookup"><span data-stu-id="96961-107">One of the most basic projects in Visual Studio is the Console Application.</span></span>  <span data-ttu-id="96961-108">방법은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="96961-108">Here's how to do it.</span></span>  <span data-ttu-id="96961-109">Visual Studio가 열리면 다음을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="96961-109">Once Visual Studio is open:</span></span>

1. <span data-ttu-id="96961-110">**파일** 메뉴에서 **새로 만들기**를 가리킨 다음 **프로젝트**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="96961-110">On the **File** menu, point to **New**, and then choose **Project**.</span></span>

2. <span data-ttu-id="96961-111">새 프로젝트 대화 상자의 **템플릿**아래에 **시각적 개체 F#** 가 표시 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="96961-111">In the New Project dialog, under **Templates**, you should see **Visual F#**.</span></span>  <span data-ttu-id="96961-112">F# 템플릿을 표시 하려면이를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="96961-112">Choose this to show the F# templates.</span></span>

3. <span data-ttu-id="96961-113">**.Net Core 콘솔 앱** 또는 **콘솔 앱**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="96961-113">Select either **.NET Core Console app** or **Console app**.</span></span>

4. <span data-ttu-id="96961-114">확인 단추 **를 선택 하 여** F# 프로젝트를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="96961-114">Choose the **Okay** button to create the F# project!</span></span>  <span data-ttu-id="96961-115">이제 솔루션 탐색기에 F# 프로젝트가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="96961-115">You should now see an F# project in the Solution Explorer.</span></span>

## <a name="writing-your-code"></a><span data-ttu-id="96961-116">코드 작성</span><span class="sxs-lookup"><span data-stu-id="96961-116">Writing your code</span></span>

<span data-ttu-id="96961-117">먼저 코드를 작성 하 여 시작 해 보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="96961-117">Let's get started by writing some code first.</span></span>  <span data-ttu-id="96961-118">`Program.fs` 파일이 열려 있는지 확인 하 고 해당 내용을 다음으로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="96961-118">Make sure that the `Program.fs` file is open, and then replace its contents with the following:</span></span>

[!code-fsharp[HelloSquare](~/samples/snippets/fsharp/getting-started/hello-square.fs)]

<span data-ttu-id="96961-119">위의 코드 샘플에서는 `x` 라는 입력을 사용 하는 `square` 함수를 정의 하 고 그 자체로 곱합니다.</span><span class="sxs-lookup"><span data-stu-id="96961-119">In the previous code sample, a function `square` has been defined which takes an input named `x` and multiplies it by itself.</span></span>  <span data-ttu-id="96961-120">에서는 F# [형식 유추](../language-reference/type-inference.md)를 사용 하므로 `x` 형식을 지정할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="96961-120">Because F# uses [Type Inference](../language-reference/type-inference.md), the type of `x` doesn't need to be specified.</span></span>  <span data-ttu-id="96961-121">컴파일러 F# 는 곱하기가 유효한 형식을 이해 하 고 `square` 호출 되는 방식에 따라 `x`에 형식을 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="96961-121">The F# compiler understands the types where multiplication is valid, and will assign a type to `x` based on how `square` is called.</span></span>  <span data-ttu-id="96961-122">`square`를 마우스로 가리키면 다음과 같이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="96961-122">If you hover over `square`, you should see the following:</span></span>

```fsharp
val square: x:int -> int
```

<span data-ttu-id="96961-123">이를 함수의 형식 서명 이라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="96961-123">This is what is known as the function's type signature.</span></span>  <span data-ttu-id="96961-124">다음과 같이 읽을 수 있습니다. "Square는 x 라는 정수를 사용 하 고 정수를 생성 하는 함수입니다."</span><span class="sxs-lookup"><span data-stu-id="96961-124">It can be read like this: "Square is a function which takes an integer named x and produces an integer".</span></span>  <span data-ttu-id="96961-125">컴파일러는 현재 `int` 형식 `square`를 제공 했습니다 .이는 곱하기가 *모든* 형식에서 제네릭이 아니라 폐쇄형 형식 집합에 대해 제네릭 이기 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="96961-125">Note that the compiler gave `square` the `int` type for now - this is because multiplication is not generic across *all* types, but rather is generic across a closed set of types.</span></span>  <span data-ttu-id="96961-126">이 F# 시점에서 컴파일러 `int` 선택 되었지만 `float`와 같은 다른 입력 형식으로 `square`를 호출 하는 경우 형식 시그니처를 조정 합니다.</span><span class="sxs-lookup"><span data-stu-id="96961-126">The F# compiler picked `int` at this point, but it will adjust the type signature if you call `square` with a different input type, such as a `float`.</span></span>

<span data-ttu-id="96961-127">`EntryPoint` 특성으로 데코 레이트 된 다른 함수인 `main`를 정의 하 여 프로그램 실행을 시작 해야 F# 함을 컴파일러에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="96961-127">Another function, `main`, is defined, which is decorated with the `EntryPoint` attribute to tell the F# compiler that program execution should start there.</span></span>  <span data-ttu-id="96961-128">이 함수는 명령줄 인수를이 함수에 전달할 수 있는 다른 [C 스타일 프로그래밍 언어](https://en.wikipedia.org/wiki/Entry_point#C_and_C.2B.2B)와 동일한 규칙을 따르며 정수 코드가 반환 됩니다 (일반적으로 `0`).</span><span class="sxs-lookup"><span data-stu-id="96961-128">It follows the same convention as other [C-style programming languages](https://en.wikipedia.org/wiki/Entry_point#C_and_C.2B.2B), where command-line arguments can be passed to this function, and an integer code is returned (typically `0`).</span></span>

<span data-ttu-id="96961-129">이 함수에서는 `12`의 인수를 사용 하 여 `square` 함수를 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="96961-129">It is in this function that we call the `square` function with an argument of `12`.</span></span>  <span data-ttu-id="96961-130">그런 F# 다음 컴파일러는 `int -> int` 되는 `square` 형식 (즉, `int`를 사용 하 고 `int`를 생성 하는 함수)을 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="96961-130">The F# compiler then assigns the type of `square` to be `int -> int` (that is, a function which takes an `int` and produces an `int`).</span></span>  <span data-ttu-id="96961-131">`printfn`에 대 한 호출은 형식 문자열을 사용 하는 서식 있는 인쇄 함수 이며, 형식 문자열에 지정 된 매개 변수에 해당 하는 매개 변수는 C 스타일 프로그래밍 언어와 비슷하며, 결과와 새 줄을 출력 합니다.</span><span class="sxs-lookup"><span data-stu-id="96961-131">The call to `printfn` is a formatted printing function which uses a format string, similar to C-style programming languages, parameters which correspond to those specified in the format string, and then prints the result and a new line.</span></span>

## <a name="running-your-code"></a><span data-ttu-id="96961-132">코드 실행</span><span class="sxs-lookup"><span data-stu-id="96961-132">Running your code</span></span>

<span data-ttu-id="96961-133">**Ctrl**+**F5**키를 눌러 코드를 실행 하 고 결과를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="96961-133">You can run the code and see results by pressing **Ctrl**+**F5**.</span></span>  <span data-ttu-id="96961-134">이렇게 하면 프로그램을 디버깅 하지 않고 실행 하 고 결과를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="96961-134">This runs the program without debugging and allows you to see the results.</span></span>  <span data-ttu-id="96961-135">또는 Visual Studio에서 **디버그** 최상위 메뉴 항목을 선택 하 고 **디버깅 하지 않고 시작**을 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="96961-135">Alternatively, you can choose the **Debug** top-level menu item in Visual Studio and choose **Start Without Debugging**.</span></span>

<span data-ttu-id="96961-136">이제 Visual Studio가 표시 된 콘솔 창에 다음과 같이 출력 됩니다.</span><span class="sxs-lookup"><span data-stu-id="96961-136">You should now see the following printed to the console window that Visual Studio popped up:</span></span>

```console
12 squared is 144!
```

<span data-ttu-id="96961-137">지금까지</span><span class="sxs-lookup"><span data-stu-id="96961-137">Congratulations!</span></span>  <span data-ttu-id="96961-138">Visual Studio에서 첫 번째 F# 프로젝트를 만들고 함수를 작성 F# 하 여 해당 함수를 호출한 결과를 출력 하 고 프로젝트를 실행 하 여 일부 결과를 확인 했습니다.</span><span class="sxs-lookup"><span data-stu-id="96961-138">You've created your first F# project in Visual Studio, written an F# function printed the results of calling that function, and run the project to see some results.</span></span>

## <a name="next-steps"></a><span data-ttu-id="96961-139">다음 단계</span><span class="sxs-lookup"><span data-stu-id="96961-139">Next steps</span></span>

<span data-ttu-id="96961-140">아직 없는 경우 F# 언어의 핵심 기능 중 일부를 포함 하는 [둘러보기 F# ](../tour.md)를 확인 하세요.</span><span class="sxs-lookup"><span data-stu-id="96961-140">If you haven't already, check out the [Tour of F#](../tour.md), which covers some of the core features of the F# language.</span></span>  <span data-ttu-id="96961-141">의 F#기능 중 일부에 대 한 개요를 제공 하 고 Visual Studio로 복사 하 여 실행할 수 있는 충분 한 코드 샘플을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="96961-141">It will give you an overview of some of the capabilities of F#, and provide ample code samples that you can copy into Visual Studio and run.</span></span>  <span data-ttu-id="96961-142">F# 문서 [ F# 홈페이지](../index.yml)에서 설명서에 대해 자세히 알아볼 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="96961-142">You can also learn more about the F# documentation in the [F# docs homepage](../index.yml).</span></span>

## <a name="see-also"></a><span data-ttu-id="96961-143">참조</span><span class="sxs-lookup"><span data-stu-id="96961-143">See also</span></span>

- [<span data-ttu-id="96961-144">F# 둘러보기</span><span class="sxs-lookup"><span data-stu-id="96961-144">Tour of F#</span></span>](../tour.md)
- [<span data-ttu-id="96961-145">F#언어 참조</span><span class="sxs-lookup"><span data-stu-id="96961-145">F# language reference</span></span>](../language-reference/index.md)
- [<span data-ttu-id="96961-146">형식 유추</span><span class="sxs-lookup"><span data-stu-id="96961-146">Type inference</span></span>](../language-reference/type-inference.md)
- [<span data-ttu-id="96961-147">기호 및 연산자 참조</span><span class="sxs-lookup"><span data-stu-id="96961-147">Symbol and operator reference</span></span>](../language-reference/symbol-and-operator-reference/index.md)
