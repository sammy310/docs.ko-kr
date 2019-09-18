---
title: Visual Studio에서 F# 시작
description: Visual Studio에서 F#을 사용하는 방법을 알아봅니다.
ms.date: 07/03/2018
ms.openlocfilehash: e573af67a1fc00b0a340f8c73ab1ee0ed2b97810
ms.sourcegitcommit: a2d0e1f66367367065bc8dc0dde488ab536da73f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/18/2019
ms.locfileid: "71082693"
---
# <a name="get-started-with-f-in-visual-studio"></a><span data-ttu-id="c32dd-103">Visual Studio에서 F# 시작</span><span class="sxs-lookup"><span data-stu-id="c32dd-103">Get started with F# in Visual Studio</span></span>

<span data-ttu-id="c32dd-104">F#과 Visual F# 도구가 Visual Studio IDE에서 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="c32dd-104">F# and the Visual F# tooling are supported in the Visual Studio IDE.</span></span>

<span data-ttu-id="c32dd-105">시작하기 위해서는 [F#이 설치된 Visual Studio](install-fsharp.md#install-f-with-visual-studio)가 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c32dd-105">To begin, ensure that you have [Visual Studio installed with F#](install-fsharp.md#install-f-with-visual-studio).</span></span>

## <a name="creating-a-console-application"></a><span data-ttu-id="c32dd-106">콘솔 응용 프로그램 만들기</span><span class="sxs-lookup"><span data-stu-id="c32dd-106">Creating a console application</span></span>

<span data-ttu-id="c32dd-107">Visual Studio에서 가장 기본적인 프로젝트 중 하나가 콘솔 응용 프로그램입니다.</span><span class="sxs-lookup"><span data-stu-id="c32dd-107">One of the most basic projects in Visual Studio is the Console Application.</span></span>  <span data-ttu-id="c32dd-108">방법은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="c32dd-108">Here's how to do it.</span></span>  <span data-ttu-id="c32dd-109">Visual Studio를 열고</span><span class="sxs-lookup"><span data-stu-id="c32dd-109">Once Visual Studio is open:</span></span>

1. <span data-ttu-id="c32dd-110">**파일** 메뉴에서 **새로 만들기**를 선택한 후 **프로젝트**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="c32dd-110">On the **File** menu, point to **New**, and then choose **Project**.</span></span>

2. <span data-ttu-id="c32dd-111">새 프로젝트에서 대화 상자의 **템플릿**에서 **Visual F#** 을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="c32dd-111">In the New Project dialog, under **Templates**, you should see **Visual F#**.</span></span>  <span data-ttu-id="c32dd-112">F# 템플릿을 표시하려면 이 옵션을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="c32dd-112">Choose this to show the F# templates.</span></span>

3. <span data-ttu-id="c32dd-113">**.NET Core 콘솔 앱**이나 **콘솔 앱**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="c32dd-113">Select either **.NET Core Console app** or **Console app**.</span></span>

4. <span data-ttu-id="c32dd-114">F# 프로젝트를 만들기 위해 **확인** 버튼을 클릭힙니다.</span><span class="sxs-lookup"><span data-stu-id="c32dd-114">Choose the **Okay** button to create the F# project!</span></span>  <span data-ttu-id="c32dd-115">이제 솔루션 탐색기에서 F# 프로젝트를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c32dd-115">You should now see an F# project in the Solution Explorer.</span></span>

## <a name="writing-your-code"></a><span data-ttu-id="c32dd-116">코드 작성</span><span class="sxs-lookup"><span data-stu-id="c32dd-116">Writing your code</span></span>

<span data-ttu-id="c32dd-117">먼저 코드 작성으로 시작하세요.</span><span class="sxs-lookup"><span data-stu-id="c32dd-117">Let's get started by writing some code first.</span></span>  <span data-ttu-id="c32dd-118">`Program.fs` 파일을 열고 다음 내용으로 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="c32dd-118">Make sure that the `Program.fs` file is open, and then replace its contents with the following:</span></span>

[!code-fsharp[HelloSquare](~/samples/snippets/fsharp/getting-started/hello-square.fs)]

<span data-ttu-id="c32dd-119">이 코드 샘플에서는 입력으로 `x`를 가져와 자신과 곱셈하도록 정의된 `square`함수가 정의되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c32dd-119">In the previous code sample, a function `square` has been defined which takes an input named `x` and multiplies it by itself.</span></span>  <span data-ttu-id="c32dd-120">F#에서는 [Typeinference](../language-reference/type-inference.md)를 사용하기 때문에 `x`의 형식을 지정할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="c32dd-120">Because F# uses [Type Inference](../language-reference/type-inference.md), the type of `x` doesn't need to be specified.</span></span>  <span data-ttu-id="c32dd-121">F# 컴파일러는 곱셈에서 유효한 형식을 이해하고 `square`가 호출되는 방식에 따라 `x`의 형식을 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="c32dd-121">The F# compiler understands the types where multiplication is valid, and will assign a type to `x` based on how `square` is called.</span></span>  <span data-ttu-id="c32dd-122">`square` 위로 마우스를 가져가면 다음과 같이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="c32dd-122">If you hover over `square`, you should see the following:</span></span>

```fsharp
val square: x:int -> int
```

<span data-ttu-id="c32dd-123">이것을 함수 형식 시그니처라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="c32dd-123">This is what is known as the function's type signature.</span></span>  <span data-ttu-id="c32dd-124">다음과 같이 "square는 정수 x를 사용하고 정수를 생성하는 함수"라고 읽을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c32dd-124">It can be read like this: "Square is a function which takes an integer named x and produces an integer".</span></span>  <span data-ttu-id="c32dd-125">컴파일러가 `square`를 `int`형식으로 지정한 것에 주목하십시오. 곱셈은 *모든* 형식에서 제네릭이 아니라, 폐쇄형 집합 형식에서 제네릭이기 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="c32dd-125">Note that the compiler gave `square` the `int` type for now - this is because multiplication is not generic across *all* types, but rather is generic across a closed set of types.</span></span>  <span data-ttu-id="c32dd-126">F# 컴파일러에서 지금은 `int`를 선택하지만, `float` 같은 다른 입력 형식으로 `square`를 호출 하는 경우는 형식 시그니처가 조정됩니다.</span><span class="sxs-lookup"><span data-stu-id="c32dd-126">The F# compiler picked `int` at this point, but it will adjust the type signature if you call `square` with a different input type, such as a `float`.</span></span>

<span data-ttu-id="c32dd-127">그 밖에 `main` 함수가 정의되고 F# 컴파일러에게 프로그램 수행이 시작되는 곳이라는 것을 알려주는 `EntryPoint`속성이 데코레이트되었습니다.</span><span class="sxs-lookup"><span data-stu-id="c32dd-127">Another function, `main`, is defined, which is decorated with the `EntryPoint` attribute to tell the F# compiler that program execution should start there.</span></span>  <span data-ttu-id="c32dd-128">함수에 명령줄 인수를 전달하고 정수 코드(일반적으로 `0`)를 반환하는 [C 스타일 프로그래밍 언어](https://en.wikipedia.org/wiki/Entry_point#C_and_C.2B.2B)와 동일한 규칙을 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="c32dd-128">It follows the same convention as other [C-style programming languages](https://en.wikipedia.org/wiki/Entry_point#C_and_C.2B.2B), where command-line arguments can be passed to this function, and an integer code is returned (typically `0`).</span></span>

<span data-ttu-id="c32dd-129">이 함수에서는 인수로 `12`를 사용하여 `square` 함수를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="c32dd-129">It is in this function that we call the `square` function with an argument of `12`.</span></span>  <span data-ttu-id="c32dd-130">F# 컴파일러에는 `square`의 형식을 `int -> int`가 되도록 할당합니다(이것이 `int`를 가지고 `int`를 생성하는 함수입니다).</span><span class="sxs-lookup"><span data-stu-id="c32dd-130">The F# compiler then assigns the type of `square` to be `int -> int` (that is, a function which takes an `int` and produces an `int`).</span></span>  <span data-ttu-id="c32dd-131">`printfn` 호출은 서식이 지정된 출력 기능으로, C 스타일 프로그래밍 언어와 유사한 형식 문자열을 사용하고, 형식 문자열의 서식이 지정된 매개 변수와 결과를 새로운 라인에 출력합니다.</span><span class="sxs-lookup"><span data-stu-id="c32dd-131">The call to `printfn` is a formatted printing function which uses a format string, similar to C-style programming languages, parameters which correspond to those specified in the format string, and then prints the result and a new line.</span></span>

## <a name="running-your-code"></a><span data-ttu-id="c32dd-132">코드 실행</span><span class="sxs-lookup"><span data-stu-id="c32dd-132">Running your code</span></span>

<span data-ttu-id="c32dd-133">**Ctrl**+**F5**를 눌러 코드를 실행 하 고 결과를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c32dd-133">You can run the code and see results by pressing **Ctrl**+**F5**.</span></span>  <span data-ttu-id="c32dd-134">이렇게 하면 프로그램을 디버깅 하지 않고 실행 하 고 결과를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c32dd-134">This runs the program without debugging and allows you to see the results.</span></span>  <span data-ttu-id="c32dd-135">또는 Visual Studio에서 **디버그** 최상위 메뉴 항목을 선택 하 고 **디버깅 하지 않고 시작**을 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c32dd-135">Alternatively, you can choose the **Debug** top-level menu item in Visual Studio and choose **Start Without Debugging**.</span></span>

<span data-ttu-id="c32dd-136">이제 Visual Studio가 표시 된 콘솔 창에 다음과 같이 출력 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c32dd-136">You should now see the following printed to the console window that Visual Studio popped up:</span></span>

```console
12 squared is 144!
```

<span data-ttu-id="c32dd-137">지금까지</span><span class="sxs-lookup"><span data-stu-id="c32dd-137">Congratulations!</span></span>  <span data-ttu-id="c32dd-138">Visual Studio에서 첫 번째 F# 프로젝트를 만들고 함수를 작성 F# 하 여 해당 함수를 호출한 결과를 출력 하 고 프로젝트를 실행 하 여 일부 결과를 확인 했습니다.</span><span class="sxs-lookup"><span data-stu-id="c32dd-138">You've created your first F# project in Visual Studio, written an F# function printed the results of calling that function, and run the project to see some results.</span></span>

## <a name="next-steps"></a><span data-ttu-id="c32dd-139">다음 단계</span><span class="sxs-lookup"><span data-stu-id="c32dd-139">Next steps</span></span>

<span data-ttu-id="c32dd-140">아직 확인하지 않았다면 F# 언어의 핵심 기능 중 일부를 다루는 [F# 둘러보기](../tour.md)를 확인해보세요.</span><span class="sxs-lookup"><span data-stu-id="c32dd-140">If you haven't already, check out the [Tour of F#](../tour.md), which covers some of the core features of the F# language.</span></span>  <span data-ttu-id="c32dd-141">의 F#기능 중 일부에 대 한 개요를 제공 하 고 Visual Studio로 복사 하 여 실행할 수 있는 충분 한 코드 샘플을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="c32dd-141">It will give you an overview of some of the capabilities of F#, and provide ample code samples that you can copy into Visual Studio and run.</span></span>  <span data-ttu-id="c32dd-142">[F# 가이드](../index.md)에서 소개된 훌륭한 외부 리소스도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c32dd-142">There are also some great external resources you can use, showcased in the [F# Guide](../index.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="c32dd-143">참고자료</span><span class="sxs-lookup"><span data-stu-id="c32dd-143">See also</span></span>

- [<span data-ttu-id="c32dd-144">F# 둘러보기</span><span class="sxs-lookup"><span data-stu-id="c32dd-144">Tour of F#</span></span>](../tour.md)
- [<span data-ttu-id="c32dd-145">F# 언어 참조</span><span class="sxs-lookup"><span data-stu-id="c32dd-145">F# language reference</span></span>](../language-reference/index.md)
- [<span data-ttu-id="c32dd-146">형식 유추</span><span class="sxs-lookup"><span data-stu-id="c32dd-146">Type inference</span></span>](../language-reference/type-inference.md)
- [<span data-ttu-id="c32dd-147">기호 및 연산자 참조</span><span class="sxs-lookup"><span data-stu-id="c32dd-147">Symbol and operator reference</span></span>](../language-reference/symbol-and-operator-reference/index.md)
