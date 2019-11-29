---
title: Mac용 Visual Studio F# 에서 시작
description: Mac용 Visual Studio와 함께를 F# 사용 하는 방법을 알아봅니다.
ms.date: 07/03/2018
ms.openlocfilehash: cd45ab9c59cef76e4bf85a93f39d8e2ee063d200
ms.sourcegitcommit: 93762e1a0dae1b5f64d82eebb7b705a6d566d839
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/27/2019
ms.locfileid: "74552365"
---
# <a name="get-started-with-f-in-visual-studio-for-mac"></a><span data-ttu-id="78739-103">Mac용 Visual Studio F# 에서 시작</span><span class="sxs-lookup"><span data-stu-id="78739-103">Get started with F# in Visual Studio for Mac</span></span>

<span data-ttu-id="78739-104">F#및 비주얼 F# 도구는 Mac용 Visual Studio IDE에서 지원 됩니다.</span><span class="sxs-lookup"><span data-stu-id="78739-104">F# and the Visual F# tooling are supported in the Visual Studio for Mac IDE.</span></span> <span data-ttu-id="78739-105">[Mac용 Visual Studio 설치](install-fsharp.md#install-f-with-visual-studio-for-mac)되어 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="78739-105">Ensure that you have [Visual Studio for Mac installed](install-fsharp.md#install-f-with-visual-studio-for-mac).</span></span>

## <a name="creating-a-console-application"></a><span data-ttu-id="78739-106">콘솔 응용 프로그램 만들기</span><span class="sxs-lookup"><span data-stu-id="78739-106">Creating a console application</span></span>

<span data-ttu-id="78739-107">Mac용 Visual Studio에서 가장 기본적인 프로젝트 중 하나는 콘솔 응용 프로그램입니다.</span><span class="sxs-lookup"><span data-stu-id="78739-107">One of the most basic projects in Visual Studio for Mac is the Console Application.</span></span>  <span data-ttu-id="78739-108">방법은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="78739-108">Here's how to do it.</span></span>  <span data-ttu-id="78739-109">Mac용 Visual Studio 열리면 다음을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="78739-109">Once Visual Studio for Mac is open:</span></span>

1. <span data-ttu-id="78739-110">**파일** 메뉴에서 **새 솔루션**을 가리킵니다.</span><span class="sxs-lookup"><span data-stu-id="78739-110">On the **File** menu, point to **New Solution**.</span></span>

2. <span data-ttu-id="78739-111">새 프로젝트 대화 상자에는 콘솔 응용 프로그램에 대 한 두 가지 템플릿이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="78739-111">In the New Project dialog, there are 2 different templates for Console Application.</span></span>  <span data-ttu-id="78739-112">.NET Framework를 대상으로 하는 다른 > .NET 아래에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="78739-112">There is one under Other -> .NET which targets the .NET Framework.</span></span>  <span data-ttu-id="78739-113">다른 템플릿은 .net core를 대상으로 하는 .net Core-> 앱 아래에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="78739-113">The other template is under .NET Core -> App which targets .NET Core.</span></span>  <span data-ttu-id="78739-114">이 문서의 목적에 맞게 두 템플릿이 작동 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="78739-114">Either template should work for the purpose of this article.</span></span>

3. <span data-ttu-id="78739-115">콘솔 앱에서 필요한 경우 C# 를 F# 로 변경 합니다.</span><span class="sxs-lookup"><span data-stu-id="78739-115">Under console app, change C# to F# if needed.</span></span>  <span data-ttu-id="78739-116">**다음** 단추를 선택 하 여 앞으로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="78739-116">Choose the **Next** button to move forward!</span></span>  

4. <span data-ttu-id="78739-117">프로젝트에 이름을 지정 하 고 앱에 대해 원하는 옵션을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="78739-117">Give your project a name, and choose the options you want for the app.</span></span>  <span data-ttu-id="78739-118">화면 옆의 미리 보기 창에는 선택한 옵션에 따라 생성 되는 디렉터리 구조가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="78739-118">Notice, the preview pane to the side of the screen that will show the directory structure that will be created based on the options selected.</span></span>  

5. <span data-ttu-id="78739-119">**만들기**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="78739-119">Click **Create**.</span></span>  <span data-ttu-id="78739-120">이제 솔루션 탐색기에 F# 프로젝트가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="78739-120">You should now see an F# project in the Solution Explorer.</span></span>

## <a name="writing-your-code"></a><span data-ttu-id="78739-121">코드 작성</span><span class="sxs-lookup"><span data-stu-id="78739-121">Writing your code</span></span>

<span data-ttu-id="78739-122">먼저 코드를 작성 하 여 시작 해 보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="78739-122">Let's get started by writing some code first.</span></span>  <span data-ttu-id="78739-123">`Program.fs` 파일이 열려 있는지 확인 하 고 해당 내용을 다음으로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="78739-123">Make sure that the `Program.fs` file is open, and then replace its contents with the following:</span></span>

[!code-fsharp[HelloSquare](~/samples/snippets/fsharp/getting-started/hello-square.fs)]

<span data-ttu-id="78739-124">위의 코드 샘플에서는 `x` 라는 입력을 사용 하는 `square` 함수를 정의 하 고 그 자체로 곱합니다.</span><span class="sxs-lookup"><span data-stu-id="78739-124">In the previous code sample, a function `square` has been defined which takes an input named `x` and multiplies it by itself.</span></span>  <span data-ttu-id="78739-125">에서는 F# [형식 유추](../language-reference/type-inference.md)를 사용 하므로 `x` 형식을 지정할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="78739-125">Because F# uses [Type Inference](../language-reference/type-inference.md), the type of `x` doesn't need to be specified.</span></span>  <span data-ttu-id="78739-126">컴파일러 F# 는 곱하기가 유효한 형식을 이해 하 고 `square` 호출 되는 방식에 따라 `x`에 형식을 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="78739-126">The F# compiler understands the types where multiplication is valid, and will assign a type to `x` based on how `square` is called.</span></span>  <span data-ttu-id="78739-127">`square`를 마우스로 가리키면 다음과 같이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="78739-127">If you hover over `square`, you should see the following:</span></span>

```console
val square: x:int -> int
```

<span data-ttu-id="78739-128">이를 함수의 형식 서명 이라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="78739-128">This is what is known as the function's type signature.</span></span>  <span data-ttu-id="78739-129">다음과 같이 읽을 수 있습니다. "Square는 x 라는 정수를 사용 하 고 정수를 생성 하는 함수입니다."</span><span class="sxs-lookup"><span data-stu-id="78739-129">It can be read like this: "Square is a function which takes an integer named x and produces an integer".</span></span>  <span data-ttu-id="78739-130">컴파일러는 현재 `int` 형식 `square`를 제공 했습니다 .이는 곱하기가 *모든* 형식에서 제네릭이 아니라 폐쇄형 형식 집합에 대해 제네릭 이기 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="78739-130">Note that the compiler gave `square` the `int` type for now - this is because multiplication is not generic across *all* types, but rather is generic across a closed set of types.</span></span>  <span data-ttu-id="78739-131">이 F# 시점에서 컴파일러 `int` 선택 되었지만 `float`와 같은 다른 입력 형식으로 `square`를 호출 하는 경우 형식 시그니처를 조정 합니다.</span><span class="sxs-lookup"><span data-stu-id="78739-131">The F# compiler picked `int` at this point, but it will adjust the type signature if you call `square` with a different input type, such as a `float`.</span></span>

<span data-ttu-id="78739-132">`EntryPoint` 특성으로 데코 레이트 된 다른 함수인 `main`를 정의 하 여 프로그램 실행을 시작 해야 F# 함을 컴파일러에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="78739-132">Another function, `main`, is defined, which is decorated with the `EntryPoint` attribute to tell the F# compiler that program execution should start there.</span></span>  <span data-ttu-id="78739-133">이 함수는 명령줄 인수를이 함수에 전달할 수 있는 다른 [C 스타일 프로그래밍 언어](https://en.wikipedia.org/wiki/Entry_point#C_and_C.2B.2B)와 동일한 규칙을 따르며 정수 코드가 반환 됩니다 (일반적으로 `0`).</span><span class="sxs-lookup"><span data-stu-id="78739-133">It follows the same convention as other [C-style programming languages](https://en.wikipedia.org/wiki/Entry_point#C_and_C.2B.2B), where command-line arguments can be passed to this function, and an integer code is returned (typically `0`).</span></span>

<span data-ttu-id="78739-134">이 함수에서는 `12`의 인수를 사용 하 여 `square` 함수를 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="78739-134">It is in this function that we call the `square` function with an argument of `12`.</span></span>  <span data-ttu-id="78739-135">그런 F# 다음 컴파일러는 `int -> int` 되는 `square` 형식 (즉, `int`를 사용 하 고 `int`를 생성 하는 함수)을 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="78739-135">The F# compiler then assigns the type of `square` to be `int -> int` (that is, a function which takes an `int` and produces an `int`).</span></span>  <span data-ttu-id="78739-136">`printfn`에 대 한 호출은 형식 문자열을 사용 하는 서식 있는 인쇄 함수 이며, 형식 문자열에 지정 된 매개 변수에 해당 하는 매개 변수는 C 스타일 프로그래밍 언어와 비슷하며, 결과와 새 줄을 출력 합니다.</span><span class="sxs-lookup"><span data-stu-id="78739-136">The call to `printfn` is a formatted printing function which uses a format string, similar to C-style programming languages, parameters which correspond to those specified in the format string, and then prints the result and a new line.</span></span>

## <a name="running-your-code"></a><span data-ttu-id="78739-137">코드 실행</span><span class="sxs-lookup"><span data-stu-id="78739-137">Running your code</span></span>

<span data-ttu-id="78739-138">최상위 메뉴에서 **실행** 을 클릭 한 다음 **디버깅 하지 않고 시작**을 클릭 하 여 코드를 실행 하 고 결과를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="78739-138">You can run the code and see results by clicking on **Run** from the top level menu and then **Start Without Debugging**.</span></span>  <span data-ttu-id="78739-139">이렇게 하면 디버깅 하지 않고 프로그램을 실행 하 고 결과를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="78739-139">This will run the program without debugging and allows you to see the results.</span></span>

<span data-ttu-id="78739-140">이제 콘솔 창에 다음으로 표시 된 Mac용 Visual Studio 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="78739-140">You should now see the following printed to the console window that Visual Studio for Mac popped up:</span></span>

```console
12 squared is 144!
```

<span data-ttu-id="78739-141">지금까지</span><span class="sxs-lookup"><span data-stu-id="78739-141">Congratulations!</span></span>  <span data-ttu-id="78739-142">Mac용 Visual Studio에서 첫 번째 F# 프로젝트를 만들고 함수를 작성 F# 하 여 해당 함수를 호출한 결과를 출력 하 고 프로젝트를 실행 하 여 일부 결과를 확인 했습니다.</span><span class="sxs-lookup"><span data-stu-id="78739-142">You've created your first F# project in Visual Studio for Mac, written an F# function printed the results of calling that function, and run the project to see some results.</span></span>

## <a name="using-f-interactive"></a><span data-ttu-id="78739-143">대화형 F# 사용</span><span class="sxs-lookup"><span data-stu-id="78739-143">Using F# Interactive</span></span>

<span data-ttu-id="78739-144">Mac용 Visual Studio에서 비주얼 F# 도구의 가장 유용한 기능 중 하나는 F# 대화형 창입니다.</span><span class="sxs-lookup"><span data-stu-id="78739-144">One of the best features of the Visual F# tooling in Visual Studio for Mac is the F# Interactive Window.</span></span>  <span data-ttu-id="78739-145">이를 통해 해당 코드를 호출 하 고 결과를 대화형으로 볼 수 있는 프로세스에 코드를 보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="78739-145">It allows you to send code over to a process where you can call that code and see the result interactively.</span></span>

<span data-ttu-id="78739-146">사용을 시작 하려면 코드에 정의 된 `square` 함수를 강조 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="78739-146">To begin using it, highlight the `square` function defined in your code.</span></span>  <span data-ttu-id="78739-147">그런 다음 최상위 메뉴에서 **편집** 을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="78739-147">Next, click on **Edit** from the top level menu.</span></span>  <span data-ttu-id="78739-148">그런 다음 선택 **영역을 F# 대화형으로 보내기를**선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="78739-148">Next select **Send selection to F# Interactive**.</span></span>  <span data-ttu-id="78739-149">그러면 F# 대화형 창에서 코드가 실행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="78739-149">This executes the code in the F# Interactive Window.</span></span>  <span data-ttu-id="78739-150">또는 선택 영역을 마우스 오른쪽 단추로 클릭 하 고 **대화형으로 선택 항목 F# 보내기를**선택할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="78739-150">Alternatively, you can right click on the selection and choose **Send selection to F# Interactive**.</span></span>  <span data-ttu-id="78739-151">F# 대화형 창이 다음과 같이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="78739-151">You should see the F# Interactive Window appear with the following in it:</span></span>

```console
>

val square : x:int -> int

>
```

<span data-ttu-id="78739-152">이는 함수를 마우스로 가리킬 때 앞서 살펴본 `square` 함수에 대 한 동일한 함수 시그니처를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="78739-152">This shows the same function signature for the `square` function, which you saw earlier when you hovered over the function.</span></span>  <span data-ttu-id="78739-153">`square`은 이제 F# 대화형 프로세스에서 정의 되었으므로 다른 값으로 호출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="78739-153">Because `square` is now defined in the F# Interactive process, you can call it with different values:</span></span>

```console
> square 12;;
val it : int = 144
>square 13;;
val it : int = 169
```

<span data-ttu-id="78739-154">그러면 함수를 실행 하 `it`새 이름에 결과를 바인딩하고 `it`의 형식과 값을 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="78739-154">This executes the function, binds the result to a new name `it`, and displays the type and value of `it`.</span></span>  <span data-ttu-id="78739-155">`;;`를 사용 하 여 각 줄을 종료 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="78739-155">Note that you must terminate each line with `;;`.</span></span>  <span data-ttu-id="78739-156">이는 함수 F# 호출이 완료 될 때 대화형으로 인식 되는 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="78739-156">This is how F# Interactive knows when your function call is finished.</span></span>  <span data-ttu-id="78739-157">대화형으로 F# 새 함수를 정의할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="78739-157">You can also define new functions in F# Interactive:</span></span>

```console
> let isOdd x = x % 2 <> 0;;

val isOdd : x:int -> bool

> isOdd 12;;
val it : bool = false
```

<span data-ttu-id="78739-158">위의에서는 `int`를 사용 하 고 홀수 인지 확인 하는 새 함수인 `isOdd`를 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="78739-158">The above defines a new function, `isOdd`, which takes an `int` and checks to see if it's odd!</span></span>  <span data-ttu-id="78739-159">이 함수를 호출 하 여 다른 입력으로 반환 되는 항목을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="78739-159">You can call this function to see what it returns with different inputs.</span></span>  <span data-ttu-id="78739-160">함수 호출 내에서 함수를 호출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="78739-160">You can call functions within function calls:</span></span>

```console
> isOdd (square 15);;
val it : bool = true
```

<span data-ttu-id="78739-161">[파이프 전달 연산자](../language-reference/symbol-and-operator-reference/index.md) 를 사용 하 여 값을 두 개의 함수로 파이프라인 할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="78739-161">You can also use the [pipe-forward operator](../language-reference/symbol-and-operator-reference/index.md) to pipeline the value into the two functions:</span></span>

```console
> 15 |> square |> isOdd;;
val it : bool = true
```

<span data-ttu-id="78739-162">파이프 전달 연산자는 이후 자습서에서 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="78739-162">The pipe-forward operator, and more, are covered in later tutorials.</span></span>

<span data-ttu-id="78739-163">이는 대화형으로 F# 수행할 수 있는 작업에만 해당 됩니다.</span><span class="sxs-lookup"><span data-stu-id="78739-163">This is only a glimpse into what you can do with F# Interactive.</span></span>  <span data-ttu-id="78739-164">자세히 알아보려면를 [사용 하 F#여 대화형 프로그래밍 ](../tutorials/fsharp-interactive/index.md)을 확인 하세요.</span><span class="sxs-lookup"><span data-stu-id="78739-164">To learn more, check out [Interactive Programming with F#](../tutorials/fsharp-interactive/index.md).</span></span>

## <a name="next-steps"></a><span data-ttu-id="78739-165">다음 단계</span><span class="sxs-lookup"><span data-stu-id="78739-165">Next steps</span></span>

<span data-ttu-id="78739-166">아직 없는 경우 F# 언어의 핵심 기능 중 일부를 포함 하는 [둘러보기 F# ](../tour.md)를 확인 하세요.</span><span class="sxs-lookup"><span data-stu-id="78739-166">If you haven't already, check out the [Tour of F#](../tour.md), which covers some of the core features of the F# language.</span></span>  <span data-ttu-id="78739-167">의 F#기능 중 일부에 대 한 개요를 제공 하 고 Mac용 Visual Studio로 복사 하 여 실행할 수 있는 충분 한 코드 샘플을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="78739-167">It will give you an overview of some of the capabilities of F#, and provide ample code samples that you can copy into Visual Studio for Mac and run.</span></span>  <span data-ttu-id="78739-168">또한 사용할 수 있는 몇 가지 유용한 외부 리소스도 [ F# 가이드](../index.yml)에서 전시 있습니다.</span><span class="sxs-lookup"><span data-stu-id="78739-168">There are also some great external resources you can use, showcased in the [F# Guide](../index.yml).</span></span>

## <a name="see-also"></a><span data-ttu-id="78739-169">참조</span><span class="sxs-lookup"><span data-stu-id="78739-169">See also</span></span>

- [<span data-ttu-id="78739-170">F#도움이</span><span class="sxs-lookup"><span data-stu-id="78739-170">F# guide</span></span>](../index.yml)
- [<span data-ttu-id="78739-171">F# 둘러보기</span><span class="sxs-lookup"><span data-stu-id="78739-171">Tour of F#</span></span>](../tour.md)
- [<span data-ttu-id="78739-172">F#언어 참조</span><span class="sxs-lookup"><span data-stu-id="78739-172">F# language reference</span></span>](../language-reference/index.md)
- [<span data-ttu-id="78739-173">형식 유추</span><span class="sxs-lookup"><span data-stu-id="78739-173">Type inference</span></span>](../language-reference/type-inference.md)
- [<span data-ttu-id="78739-174">기호 및 연산자 참조</span><span class="sxs-lookup"><span data-stu-id="78739-174">Symbol and operator reference</span></span>](../language-reference/symbol-and-operator-reference/index.md)
