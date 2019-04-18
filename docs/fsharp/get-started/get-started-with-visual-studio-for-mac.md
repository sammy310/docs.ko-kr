---
title: Mac 용 Visual Studio에서 F# 시작
description: Mac 용 Visual Studio에서 F#을 사용하는 방법을 알아봅니다.
ms.date: 07/03/2018
ms.openlocfilehash: a6997f139d7e6c5fdf77878442db0b0b75b3d727
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/09/2019
ms.locfileid: "59331873"
---
# <a name="get-started-with-f-in-visual-studio-for-mac"></a><span data-ttu-id="a3e2c-103">Mac 용 Visual Studio에서 F# 시작</span><span class="sxs-lookup"><span data-stu-id="a3e2c-103">Get started with F# in Visual Studio for Mac</span></span>

<span data-ttu-id="a3e2c-104">F#과 F# Visual 도구가 Mac IDE용 Visual Studio에서 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="a3e2c-104">F# and the Visual F# tooling are supported in the Visual Studio for Mac IDE.</span></span> <span data-ttu-id="a3e2c-105">[Mac용 Visual Studio의 설치](install-fsharp.md#install-f-with-visual-studio-for-mac)를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="a3e2c-105">Ensure that you have [Visual Studio for Mac installed](install-fsharp.md#install-f-with-visual-studio-for-mac).</span></span>

## <a name="creating-a-console-application"></a><span data-ttu-id="a3e2c-106">콘솔 응용 프로그램 만들기</span><span class="sxs-lookup"><span data-stu-id="a3e2c-106">Creating a console application</span></span>

<span data-ttu-id="a3e2c-107">Mac 용 Visual Studio에서 가장 기본적인 프로젝트 중 하나는 콘솔 응용 프로그램입니다.</span><span class="sxs-lookup"><span data-stu-id="a3e2c-107">One of the most basic projects in Visual Studio for Mac is the Console Application.</span></span>  <span data-ttu-id="a3e2c-108">방법은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="a3e2c-108">Here's how to do it.</span></span>  <span data-ttu-id="a3e2c-109">Mac 용 Visual Studio를 열고</span><span class="sxs-lookup"><span data-stu-id="a3e2c-109">Once Visual Studio for Mac is open:</span></span>

1. <span data-ttu-id="a3e2c-110">**파일** 메뉴에서 **새 솔루션**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="a3e2c-110">On the **File** menu, point to **New Solution**.</span></span>

2. <span data-ttu-id="a3e2c-111">새 프로젝트 대화 상자에서 콘솔 응용 프로그램에 대 한 2 개의 다른 템플릿이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a3e2c-111">In the New Project dialog, there are 2 different templates for Console Application.</span></span>  <span data-ttu-id="a3e2c-112">다른 하나는.NET Framework를 대상으로 하는.NET-> 합니다.</span><span class="sxs-lookup"><span data-stu-id="a3e2c-112">There is one under Other -> .NET which targets the .NET Framework.</span></span>  <span data-ttu-id="a3e2c-113">.NET Core는 다른 템플릿에->.NET Core를 대상으로 하는 앱입니다.</span><span class="sxs-lookup"><span data-stu-id="a3e2c-113">The other template is under .NET Core -> App which targets .NET Core.</span></span>  <span data-ttu-id="a3e2c-114">이 문서의 목적을 위해 템플릿 작동 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a3e2c-114">Either template should work for the purpose of this article.</span></span>

3. <span data-ttu-id="a3e2c-115">필요에 따라 콘솔 앱을 C#에서 F#으로 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="a3e2c-115">Under console app, change C# to F# if needed.</span></span>  <span data-ttu-id="a3e2c-116">다음으로 진행하기 위해 **다음**버튼을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="a3e2c-116">Choose the **Next** button to move forward!</span></span>  

4. <span data-ttu-id="a3e2c-117">프로젝트 이름을 지정하고 앱에서 사용할 옵션을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="a3e2c-117">Give your project a name, and choose the options you want for the app.</span></span>  <span data-ttu-id="a3e2c-118">화면 측면의 미리 보기 창에는 선택한 옵션을 기반으로 생성될 디렉터리 구조가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="a3e2c-118">Notice, the preview pane to the side of the screen that will show the directory structure that will be created based on the options selected.</span></span>  

5. <span data-ttu-id="a3e2c-119">**만들기**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="a3e2c-119">Click **Create**.</span></span>  <span data-ttu-id="a3e2c-120">이제는 솔루션 탐색기에서 F# 프로젝트를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a3e2c-120">You should now see an F# project in the Solution Explorer.</span></span>

## <a name="writing-your-code"></a><span data-ttu-id="a3e2c-121">코드 작성</span><span class="sxs-lookup"><span data-stu-id="a3e2c-121">Writing your code</span></span>

<span data-ttu-id="a3e2c-122">먼저 코드 작성으로 시작하세요.</span><span class="sxs-lookup"><span data-stu-id="a3e2c-122">Let's get started by writing some code first.</span></span>  <span data-ttu-id="a3e2c-123">`Program.fs` 파일을 열고 다음 내용으로 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="a3e2c-123">Make sure that the `Program.fs` file is open, and then replace its contents with the following:</span></span>

[!code-fsharp[HelloSquare](../../../samples/snippets/fsharp/getting-started/hello-square.fs)]

<span data-ttu-id="a3e2c-124">이 코드 샘플에서는 입력으로 `x`를 가져와 자신과 곱셈하도록 정의된 `square`함수가 정의되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a3e2c-124">In the previous code sample, a function `square` has been defined which takes an input named `x` and multiplies it by itself.</span></span>  <span data-ttu-id="a3e2c-125">F#에서는 [Typeinference](../language-reference/type-inference.md)를 사용하기 때문에 `x`의 형식을 지정할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a3e2c-125">Because F# uses [Type Inference](../language-reference/type-inference.md), the type of `x` doesn't need to be specified.</span></span>  <span data-ttu-id="a3e2c-126">F# 컴파일러는 곱셈에서 유효한 형식을 이해하고 `square`가 호출되는 방식에 따라 `x`의 형식을 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="a3e2c-126">The F# compiler understands the types where multiplication is valid, and will assign a type to `x` based on how `square` is called.</span></span>  <span data-ttu-id="a3e2c-127">`square` 위로 마우스를 가져가면 다음과 같이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="a3e2c-127">If you hover over `square`, you should see the following:</span></span>

```
val square: x:int -> int
```

<span data-ttu-id="a3e2c-128">이 함수 형식 시그니처 라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="a3e2c-128">This is what is known as the function's type signature.</span></span>  <span data-ttu-id="a3e2c-129">다음과 같이 읽을 수 있습니다. "정사각형은 명명 된 정수를 사용 하는 함수 x는 정수를 생성 하 고".</span><span class="sxs-lookup"><span data-stu-id="a3e2c-129">It can be read like this: "Square is a function which takes an integer named x and produces an integer".</span></span>  <span data-ttu-id="a3e2c-130">컴파일러 했습니다 보면 `square` 를 `int` 형식 곱하기에서 제네릭 없기 때문에 이것이-지금은 *모든* 형식 이지만 대신 제네릭 형식의 폐쇄형 집합입니다.</span><span class="sxs-lookup"><span data-stu-id="a3e2c-130">Note that the compiler gave `square` the `int` type for now - this is because multiplication is not generic across *all* types, but rather is generic across a closed set of types.</span></span>  <span data-ttu-id="a3e2c-131">F# 선택 하는 컴파일러 `int` 지금은 지점 하지만 조정 됩니다 형식 시그니처 호출 하는 경우 `square` 다른 입력 형식에 같은 `float`합니다.</span><span class="sxs-lookup"><span data-stu-id="a3e2c-131">The F# compiler picked `int` at this point, but it will adjust the type signature if you call `square` with a different input type, such as a `float`.</span></span>

<span data-ttu-id="a3e2c-132">그 밖에 `main` 함수가 정의되고 F# 컴파일러에게 프로그램 수행이 시작되는 곳이라는 것을 알려주는 `EntryPoint`속성이 데코레이트되었습니다.</span><span class="sxs-lookup"><span data-stu-id="a3e2c-132">Another function, `main`, is defined, which is decorated with the `EntryPoint` attribute to tell the F# compiler that program execution should start there.</span></span>  <span data-ttu-id="a3e2c-133">함수에 명령줄 인수를 전달하고 정수 코드(일반적으로 `0`)를 반환하는 [C 스타일 프로그래밍 언어](https://en.wikipedia.org/wiki/Entry_point#C_and_C.2B.2B)와 동일한 규칙을 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="a3e2c-133">It follows the same convention as other [C-style programming languages](https://en.wikipedia.org/wiki/Entry_point#C_and_C.2B.2B), where command-line arguments can be passed to this function, and an integer code is returned (typically `0`).</span></span>

<span data-ttu-id="a3e2c-134">이 함수에서는 인수로 `12`를 사용하여 `square` 함수를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="a3e2c-134">It is in this function that we call the `square` function with an argument of `12`.</span></span>  <span data-ttu-id="a3e2c-135">F# 컴파일러에는 `square`의 형식을 `int -> int`가 되도록 할당합니다(이것이 `int`를 가지고 `int`를 생성하는 함수입니다).</span><span class="sxs-lookup"><span data-stu-id="a3e2c-135">The F# compiler then assigns the type of `square` to be `int -> int` (that is, a function which takes an `int` and produces an `int`).</span></span>  <span data-ttu-id="a3e2c-136">`printfn` 호출은 서식이 지정된 출력 기능으로, C 스타일 프로그래밍 언어와 유사한 형식 문자열을 사용하고, 형식 문자열의 서식이 지정된 매개 변수와 결과를 새로운 라인에 출력합니다.</span><span class="sxs-lookup"><span data-stu-id="a3e2c-136">The call to `printfn` is a formatted printing function which uses a format string, similar to C-style programming languages, parameters which correspond to those specified in the format string, and then prints the result and a new line.</span></span>

## <a name="running-your-code"></a><span data-ttu-id="a3e2c-137">코드 실행</span><span class="sxs-lookup"><span data-stu-id="a3e2c-137">Running your code</span></span>

<span data-ttu-id="a3e2c-138">최상단 메뉴에서 **실행**과 **디버깅하지 않고 시작**을 순서대로 클릭하여 코드를 실행하고 그 결과를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a3e2c-138">You can run the code and see results by clicking on **Run** from the top level menu and then **Start Without Debugging**.</span></span>  <span data-ttu-id="a3e2c-139">이렇게 하면 디버깅을 하지 않고 프로그램을 실행하여 그 결과 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a3e2c-139">This will run the program without debugging and allows you to see the results.</span></span>

<span data-ttu-id="a3e2c-140">이제 Mac 용 Visual Studio의 콘솔 창에서 다음 내용이 표시되는 것을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a3e2c-140">You should now see the following printed to the console window that Visual Studio for Mac popped up:</span></span>

```
12 squared is 144!
```

<span data-ttu-id="a3e2c-141">지금까지</span><span class="sxs-lookup"><span data-stu-id="a3e2c-141">Congratulations!</span></span>  <span data-ttu-id="a3e2c-142">첫 번째 만든 F# 작성 하는 Mac 용 Visual Studio에서 프로젝트를 F# 함수, 함수 및 일부 결과를 보려면 프로젝트를 실행 하는 호출의 결과 인쇄 합니다.</span><span class="sxs-lookup"><span data-stu-id="a3e2c-142">You've created your first F# project in Visual Studio for Mac, written an F# function printed the results of calling that function, and run the project to see some results.</span></span>

## <a name="using-f-interactive"></a><span data-ttu-id="a3e2c-143">사용 하 여 F# 대화형</span><span class="sxs-lookup"><span data-stu-id="a3e2c-143">Using F# Interactive</span></span>

<span data-ttu-id="a3e2c-144">시각적 개체의 가장 유용한 기능 중 F# Mac에 Visual Studio에서 도구를 F# 대화형 창입니다.</span><span class="sxs-lookup"><span data-stu-id="a3e2c-144">One of the best features of the Visual F# tooling in Visual Studio for Mac is the F# Interactive Window.</span></span>  <span data-ttu-id="a3e2c-145">해당 코드를 호출 하 고 결과 대화형으로 볼 수 있는 프로세스에 코드를 보내야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a3e2c-145">It allows you to send code over to a process where you can call that code and see the result interactively.</span></span>

<span data-ttu-id="a3e2c-146">사용을 시작 하려면 강조 표시 된 `square` 함수 코드에 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="a3e2c-146">To begin using it, highlight the `square` function defined in your code.</span></span>  <span data-ttu-id="a3e2c-147">다음으로, 클릭 **편집** 최상위 메뉴에서.</span><span class="sxs-lookup"><span data-stu-id="a3e2c-147">Next, click on **Edit** from the top level menu.</span></span>  <span data-ttu-id="a3e2c-148">다음 선택 **선택 항목에 보내기 F# 대화형**합니다.</span><span class="sxs-lookup"><span data-stu-id="a3e2c-148">Next select **Send selection to F# Interactive**.</span></span>  <span data-ttu-id="a3e2c-149">이 코드를 실행 합니다 F# 대화형 창입니다.</span><span class="sxs-lookup"><span data-stu-id="a3e2c-149">This executes the code in the F# Interactive Window.</span></span>  <span data-ttu-id="a3e2c-150">선택 영역을 마우스 오른쪽 단추로 클릭 하 고 선택할 수 있습니다 또는 **선택 항목에 보내기 F# 대화형**합니다.</span><span class="sxs-lookup"><span data-stu-id="a3e2c-150">Alternatively, you can right click on the selection and choose **Send selection to F# Interactive**.</span></span>  <span data-ttu-id="a3e2c-151">표시 되어야 합니다 F# 대화형 창에서 다음을 사용 하 여 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="a3e2c-151">You should see the F# Interactive Window appear with the following in it:</span></span>

```
>

val square : x:int -> int

>
```

<span data-ttu-id="a3e2c-152">이 대 한 동일한 함수 시그니처를 보여 줍니다는 `square` 함수 위로 가져갈 때 앞서 보았던는 함수입니다.</span><span class="sxs-lookup"><span data-stu-id="a3e2c-152">This shows the same function signature for the `square` function, which you saw earlier when you hovered over the function.</span></span>  <span data-ttu-id="a3e2c-153">때문에 `square` 에 정의 된 F# 대화형 프로세스를 호출할 수 있습니다 다른 값을 사용 하 여:</span><span class="sxs-lookup"><span data-stu-id="a3e2c-153">Because `square` is now defined in the F# Interactive process, you can call it with different values:</span></span>

```
> square 12;;
val it : int = 144
>square 13;;
val it : int = 169
```

<span data-ttu-id="a3e2c-154">이 함수를 실행, 새 이름으로 결과 바인딩합니다 `it`, 형식 및 값 표시 `it`합니다.</span><span class="sxs-lookup"><span data-stu-id="a3e2c-154">This executes the function, binds the result to a new name `it`, and displays the type and value of `it`.</span></span>  <span data-ttu-id="a3e2c-155">각 줄을 종료 해야 참고 `;;`합니다.</span><span class="sxs-lookup"><span data-stu-id="a3e2c-155">Note that you must terminate each line with `;;`.</span></span>  <span data-ttu-id="a3e2c-156">이 방법을 F# 대화형 함수 호출 완료 되 면 알고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a3e2c-156">This is how F# Interactive knows when your function call is finished.</span></span>  <span data-ttu-id="a3e2c-157">새 함수를 정의할 수도 있습니다 F# Interactive:</span><span class="sxs-lookup"><span data-stu-id="a3e2c-157">You can also define new functions in F# Interactive:</span></span>

```
> let isOdd x = x % 2 <> 0;;

val isOdd : x:int -> bool

> isOdd 12;;
val it : bool = false
```

<span data-ttu-id="a3e2c-158">위의 새 함수를 정의 `isOdd`를 사용 하는 `int` 홀수 인지를 확인!</span><span class="sxs-lookup"><span data-stu-id="a3e2c-158">The above defines a new function, `isOdd`, which takes an `int` and checks to see if it's odd!</span></span>  <span data-ttu-id="a3e2c-159">서로 다른 입력을 사용 하 여 반환 값을 확인 하려면이 함수를 호출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a3e2c-159">You can call this function to see what it returns with different inputs.</span></span>  <span data-ttu-id="a3e2c-160">함수 호출 내에서 함수를 호출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a3e2c-160">You can call functions within function calls:</span></span>

```
> isOdd (square 15);;
val it : bool = true
```

<span data-ttu-id="a3e2c-161">사용할 수도 있습니다는 [파이프 정방향 연산자](../language-reference/symbol-and-operator-reference/index.md) 두 함수에 값을 파이프라인에:</span><span class="sxs-lookup"><span data-stu-id="a3e2c-161">You can also use the [pipe-forward operator](../language-reference/symbol-and-operator-reference/index.md) to pipeline the value into the two functions:</span></span>

```
> 15 |> square |> isOdd;;
val it : bool = true
```

<span data-ttu-id="a3e2c-162">나중에 자습서 정방향 파이프 연산자 등을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="a3e2c-162">The pipe-forward operator, and more, are covered in later tutorials.</span></span>

<span data-ttu-id="a3e2c-163">이 사용 하 여 수행할 수 있는 작업에 대해 간략히만 F# 대화형입니다.</span><span class="sxs-lookup"><span data-stu-id="a3e2c-163">This is only a glimpse into what you can do with F# Interactive.</span></span>  <span data-ttu-id="a3e2c-164">자세한 내용은 체크 아웃 [를 사용한 대화형 프로그래밍 F# ](../tutorials/fsharp-interactive/index.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="a3e2c-164">To learn more, check out [Interactive Programming with F#](../tutorials/fsharp-interactive/index.md).</span></span>

## <a name="next-steps"></a><span data-ttu-id="a3e2c-165">다음 단계</span><span class="sxs-lookup"><span data-stu-id="a3e2c-165">Next steps</span></span>

<span data-ttu-id="a3e2c-166">않았다면, 체크 아웃 합니다 [둘러보기 F# ](../tour.md)의 핵심 기능 중 일부를 포함 합니다 F# 언어.</span><span class="sxs-lookup"><span data-stu-id="a3e2c-166">If you haven't already, check out the [Tour of F#](../tour.md), which covers some of the core features of the F# language.</span></span>  <span data-ttu-id="a3e2c-167">기능 중 몇 가지를 간략하게 제공 합니다 F#, Mac 및 실행에 대 한 Visual Studio에 복사할 수 있는 충분 한 코드 샘플을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="a3e2c-167">It will give you an overview of some of the capabilities of F#, and provide ample code samples that you can copy into Visual Studio for Mac and run.</span></span>  <span data-ttu-id="a3e2c-168">도 유용한 외부 리소스 사용할 수 있습니다에 표시 된 [ F# 가이드](../index.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="a3e2c-168">There are also some great external resources you can use, showcased in the [F# Guide](../index.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="a3e2c-169">참고자료</span><span class="sxs-lookup"><span data-stu-id="a3e2c-169">See also</span></span>

- [<span data-ttu-id="a3e2c-170">Visual F#</span><span class="sxs-lookup"><span data-stu-id="a3e2c-170">Visual F#</span></span>](../index.md)
- [<span data-ttu-id="a3e2c-171">F# 둘러보기</span><span class="sxs-lookup"><span data-stu-id="a3e2c-171">Tour of F#</span></span>](../tour.md)
- [<span data-ttu-id="a3e2c-172">F#언어 참조</span><span class="sxs-lookup"><span data-stu-id="a3e2c-172">F# language reference</span></span>](../language-reference/index.md)
- [<span data-ttu-id="a3e2c-173">형식 유추</span><span class="sxs-lookup"><span data-stu-id="a3e2c-173">Type inference</span></span>](../language-reference/type-inference.md)
- [<span data-ttu-id="a3e2c-174">기호 및 연산자 참조</span><span class="sxs-lookup"><span data-stu-id="a3e2c-174">Symbol and operator reference</span></span>](../language-reference/symbol-and-operator-reference/index.md)
