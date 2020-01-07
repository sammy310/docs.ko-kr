---
title: Visual Studio에서 F# 시작
description: Visual Studio에서 F#을 사용하는 방법을 알아봅니다.
ms.date: 12/20/2019
ms.openlocfilehash: 9bf47fb08ea3df0aa0d5064043d94f030d45d568
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/25/2019
ms.locfileid: "75337342"
---
# <a name="get-started-with-f-in-visual-studio"></a><span data-ttu-id="14d15-103">Visual Studio에서 F# 시작</span><span class="sxs-lookup"><span data-stu-id="14d15-103">Get started with F# in Visual Studio</span></span>

<span data-ttu-id="14d15-104">F#그리고 비주얼 F# 도구는 VISUAL Studio IDE (통합 개발 환경)에서 지원 됩니다.</span><span class="sxs-lookup"><span data-stu-id="14d15-104">F# and the Visual F# tooling are supported in the Visual Studio integrated development environment (IDE).</span></span>

<span data-ttu-id="14d15-105">시작 하려면 [Visual Studio가 F# 지원 센터에 설치](install-fsharp.md#install-f-with-visual-studio)되어 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="14d15-105">To begin, ensure that you have [Visual Studio installed with F# support](install-fsharp.md#install-f-with-visual-studio).</span></span>

## <a name="create-a-console-application"></a><span data-ttu-id="14d15-106">콘솔 애플리케이션 만들기</span><span class="sxs-lookup"><span data-stu-id="14d15-106">Create a console application</span></span>

<span data-ttu-id="14d15-107">Visual Studio의 가장 기본적인 프로젝트 중 하나는 콘솔 앱입니다.</span><span class="sxs-lookup"><span data-stu-id="14d15-107">One of the most basic projects in Visual Studio is the console app.</span></span> <span data-ttu-id="14d15-108">만드는 방법은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="14d15-108">Here's how to create one:</span></span>

1. <span data-ttu-id="14d15-109">Visual Studio 2019를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="14d15-109">Open Visual Studio 2019.</span></span>

2. <span data-ttu-id="14d15-110">시작 창에서 **새 프로젝트 만들기**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="14d15-110">On the start window, choose **Create a new project**.</span></span>

3. <span data-ttu-id="14d15-111">**새 프로젝트 만들기** 페이지의 언어 목록에서를 **F#** 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="14d15-111">On the **Create a new project** page, choose **F#** from the Language list.</span></span>

4. <span data-ttu-id="14d15-112">**콘솔 앱 (.Net Core)** 템플릿을 선택 하 고 **다음**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="14d15-112">Choose the **Console App (.NET Core)** template, and then choose **Next**.</span></span>

5. <span data-ttu-id="14d15-113">**새 프로젝트 구성** 페이지에서 **프로젝트 이름** 상자에 이름을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="14d15-113">On the **Configure your new project** page, enter a name in the **Project name** box.</span></span> <span data-ttu-id="14d15-114">그런 다음, **만들기**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="14d15-114">Then, choose **Create**.</span></span>

   <span data-ttu-id="14d15-115">Visual Studio에서 새 F# 프로젝트를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="14d15-115">Visual Studio creates the new F# project.</span></span> <span data-ttu-id="14d15-116">솔루션 탐색기 창에서 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="14d15-116">You can see it in the Solution Explorer window.</span></span>

## <a name="write-the-code"></a><span data-ttu-id="14d15-117">코드 작성</span><span class="sxs-lookup"><span data-stu-id="14d15-117">Write the code</span></span>

<span data-ttu-id="14d15-118">몇 가지 코드를 작성 하 여 시작 해 보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="14d15-118">Let's get started by writing some code.</span></span> <span data-ttu-id="14d15-119">`Program.fs` 파일을 열고 다음 내용으로 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="14d15-119">Make sure that the `Program.fs` file is open, and then replace its contents with the following:</span></span>

[!code-fsharp[HelloSquare](~/samples/snippets/fsharp/getting-started/hello-square.fs)]

<span data-ttu-id="14d15-120">위의 코드 샘플은 `x` 라는 입력을 사용 하 고 자신에 게 곱하는 `square` 이라는 함수를 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="14d15-120">The previous code sample defines a function called `square` that takes an input named `x` and multiplies it by itself.</span></span> <span data-ttu-id="14d15-121">에서는 F# [형식 유추](../language-reference/type-inference.md)를 사용 하므로 `x` 형식을 지정할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="14d15-121">Because F# uses [Type inference](../language-reference/type-inference.md), the type of `x` doesn't need to be specified.</span></span> <span data-ttu-id="14d15-122">컴파일러 F# 는 곱하기가 유효한 형식을 이해 하 고 `square` 호출 되는 방법에 따라 `x`에 형식을 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="14d15-122">The F# compiler understands the types where multiplication is valid and assigns a type to `x` based on how `square` is called.</span></span> <span data-ttu-id="14d15-123">`square` 위로 마우스를 가져가면 다음과 같이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="14d15-123">If you hover over `square`, you should see the following:</span></span>

```fsharp
val square: x:int -> int
```

<span data-ttu-id="14d15-124">이것을 함수 형식 시그니처라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="14d15-124">This is what is known as the function's type signature.</span></span> <span data-ttu-id="14d15-125">다음과 같이 읽을 수 있습니다. "Square는 x 라는 정수를 사용 하 고 정수를 생성 하는 함수입니다."</span><span class="sxs-lookup"><span data-stu-id="14d15-125">It can be read like this: "Square is a function that takes an integer named x and produces an integer".</span></span> <span data-ttu-id="14d15-126">컴파일러는 현재 `int` 형식 `square`를 제공 했습니다. 이는 곱하기가 *모든* 형식에서 제네릭이 아니라 폐쇄형 형식의 집합 이기 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="14d15-126">The compiler gave `square` the `int` type for now; this is because multiplication is not generic across *all* types but rather a closed set of types.</span></span> <span data-ttu-id="14d15-127">`float`F# 와 같이 다른 입력 형식으로 `square`를 호출 하는 경우 컴파일러는 형식 서명을 조정 합니다.</span><span class="sxs-lookup"><span data-stu-id="14d15-127">The F# compiler will adjust the type signature if you call `square` with a different input type, such as a `float`.</span></span>

<span data-ttu-id="14d15-128">`EntryPoint` 특성을 사용 하 여 데코레이팅된 다른 함수인 `main`이 정의 됩니다.</span><span class="sxs-lookup"><span data-stu-id="14d15-128">Another function, `main`, is defined, which is decorated with the `EntryPoint` attribute.</span></span> <span data-ttu-id="14d15-129">이 특성은 프로그램 F# 실행을 시작 해야 함을 컴파일러에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="14d15-129">This attribute tells the F# compiler that program execution should start there.</span></span> <span data-ttu-id="14d15-130">함수에 명령줄 인수를 전달하고 정수 코드(일반적으로 `0`)를 반환하는 [C 스타일 프로그래밍 언어](https://en.wikipedia.org/wiki/Entry_point#C_and_C.2B.2B)와 동일한 규칙을 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="14d15-130">It follows the same convention as other [C-style programming languages](https://en.wikipedia.org/wiki/Entry_point#C_and_C.2B.2B), where command-line arguments can be passed to this function, and an integer code is returned (typically `0`).</span></span>

<span data-ttu-id="14d15-131">`12`의 인수로 `square` 함수를 호출 하는 진입점 함수 `main`에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="14d15-131">It is in the entry point function, `main`, that you call the `square` function with an argument of `12`.</span></span> <span data-ttu-id="14d15-132">그런 F# 다음 컴파일러는 `int -> int` 되는 `square` 형식 (즉, `int`를 사용 하 고 `int`를 생성 하는 함수)을 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="14d15-132">The F# compiler then assigns the type of `square` to be `int -> int` (that is, a function that takes an `int` and produces an `int`).</span></span> <span data-ttu-id="14d15-133">`printfn`에 대 한 호출은 서식 문자열을 사용 하 고 결과 (및 새 줄)를 인쇄 하는 형식이 지정 된 인쇄 함수입니다.</span><span class="sxs-lookup"><span data-stu-id="14d15-133">The call to `printfn` is a formatted printing function that uses a format string and prints the result (and a new line).</span></span> <span data-ttu-id="14d15-134">C 스타일의 프로그래밍 언어와 유사한 형식 문자열에는 전달 된 인수에 해당 하는 매개 변수 (`%d`)가 있습니다 .이 경우에는 `12` 및 `(square 12)`입니다.</span><span class="sxs-lookup"><span data-stu-id="14d15-134">The format string, similar to C-style programming languages, has parameters (`%d`) that correspond to the arguments that are passed to it, in this case, `12` and `(square 12)`.</span></span>

## <a name="run-the-code"></a><span data-ttu-id="14d15-135">코드 실행</span><span class="sxs-lookup"><span data-stu-id="14d15-135">Run the code</span></span>

<span data-ttu-id="14d15-136">**Ctrl**+**F5**키를 눌러 코드를 실행 하 고 결과를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="14d15-136">You can run the code and see the results by pressing **Ctrl**+**F5**.</span></span> <span data-ttu-id="14d15-137">또는 최상위 메뉴 모음에서 **디버그** > **디버깅 하지 않고 시작** 을 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="14d15-137">Alternatively, you can choose the **Debug** > **Start Without Debugging** from the top-level menu bar.</span></span> <span data-ttu-id="14d15-138">이렇게 하면 디버깅 하지 않고 프로그램이 실행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="14d15-138">This runs the program without debugging.</span></span>

<span data-ttu-id="14d15-139">다음 출력은 Visual Studio에서 연 콘솔 창에 출력 됩니다.</span><span class="sxs-lookup"><span data-stu-id="14d15-139">The following output prints to the console window that Visual Studio opened:</span></span>

```console
12 squared is: 144!
```

<span data-ttu-id="14d15-140">지금까지</span><span class="sxs-lookup"><span data-stu-id="14d15-140">Congratulations!</span></span> <span data-ttu-id="14d15-141">Visual Studio에서 첫 번째 F# 프로젝트를 만든 다음 값을 계산 F# 하 고 인쇄 하는 함수를 작성 하 고 프로젝트를 실행 하 여 결과를 확인 했습니다.</span><span class="sxs-lookup"><span data-stu-id="14d15-141">You've created your first F# project in Visual Studio, written an F# function that calculates and prints a value, and run the project to see the results.</span></span>

## <a name="next-steps"></a><span data-ttu-id="14d15-142">다음 단계</span><span class="sxs-lookup"><span data-stu-id="14d15-142">Next steps</span></span>

<span data-ttu-id="14d15-143">아직 확인하지 않았다면 F# 언어의 핵심 기능 중 일부를 다루는 [F# 둘러보기](../tour.md)를 확인해보세요.</span><span class="sxs-lookup"><span data-stu-id="14d15-143">If you haven't already, check out the [Tour of F#](../tour.md), which covers some of the core features of the F# language.</span></span> <span data-ttu-id="14d15-144">의 일부 기능과 Visual Studio로 복사 하 여 실행할 F# 수 있는 다양 한 코드 샘플에 대 한 개요를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="14d15-144">It provides an overview of some of the capabilities of F# and ample code samples that you can copy into Visual Studio and run.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="14d15-145">F# 둘러보기</span><span class="sxs-lookup"><span data-stu-id="14d15-145">Tour of F#</span></span>](../tour.md)

## <a name="see-also"></a><span data-ttu-id="14d15-146">참조</span><span class="sxs-lookup"><span data-stu-id="14d15-146">See also</span></span>

- [<span data-ttu-id="14d15-147">F# 언어 참조</span><span class="sxs-lookup"><span data-stu-id="14d15-147">F# language reference</span></span>](../language-reference/index.md)
- [<span data-ttu-id="14d15-148">형식 유추</span><span class="sxs-lookup"><span data-stu-id="14d15-148">Type inference</span></span>](../language-reference/type-inference.md)
- [<span data-ttu-id="14d15-149">기호 및 연산자 참조</span><span class="sxs-lookup"><span data-stu-id="14d15-149">Symbol and operator reference</span></span>](../language-reference/symbol-and-operator-reference/index.md)
