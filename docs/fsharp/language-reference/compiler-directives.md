---
title: 컴파일러 지시문
description: 'F # 언어 전처리기 지시문, 조건부 컴파일 지시문, 줄 지시문 및 컴파일러 지시문에 대해 알아봅니다.'
ms.date: 12/10/2018
f1_keywords:
- '#endif_FS'
ms.openlocfilehash: c3e1a07e0e09b5ae090c550368f8a9f8ee575bfb
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/15/2020
ms.locfileid: "90557322"
---
# <a name="compiler-directives"></a><span data-ttu-id="4b124-103">컴파일러 지시문</span><span class="sxs-lookup"><span data-stu-id="4b124-103">Compiler Directives</span></span>

<span data-ttu-id="4b124-104">이 항목에서는 처리기 지시문과 컴파일러 지시문에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="4b124-104">This topic describes processor directives and compiler directives.</span></span>

## <a name="preprocessor-directives"></a><span data-ttu-id="4b124-105">전처리기 지시문</span><span class="sxs-lookup"><span data-stu-id="4b124-105">Preprocessor Directives</span></span>

<span data-ttu-id="4b124-106">전처리기 지시문은 # 기호를 접두사로 사용하며 따로 한 줄을 할애하여 지시문을 작성합니다.</span><span class="sxs-lookup"><span data-stu-id="4b124-106">A preprocessor directive is prefixed with the # symbol and appears on a line by itself.</span></span> <span data-ttu-id="4b124-107">이 지시문은 컴파일러 자체보다 먼저 실행되는 전처리기를 통해 해석됩니다.</span><span class="sxs-lookup"><span data-stu-id="4b124-107">It is interpreted by the preprocessor, which runs before the compiler itself.</span></span>

<span data-ttu-id="4b124-108">다음 표에는 F#에서 사용할 수 있는 전처리기 지시문의 목록이 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4b124-108">The following table lists the preprocessor directives that are available in F#.</span></span>

|<span data-ttu-id="4b124-109">지시문</span><span class="sxs-lookup"><span data-stu-id="4b124-109">Directive</span></span>|<span data-ttu-id="4b124-110">설명</span><span class="sxs-lookup"><span data-stu-id="4b124-110">Description</span></span>|
|---------|-----------|
|<span data-ttu-id="4b124-111">`#if`*기호*</span><span class="sxs-lookup"><span data-stu-id="4b124-111">`#if` *symbol*</span></span>|<span data-ttu-id="4b124-112">조건부 컴파일을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="4b124-112">Supports conditional compilation.</span></span> <span data-ttu-id="4b124-113">`#if` *기호가* 정의 된 경우이 포함 된 후의 섹션에 있는 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="4b124-113">Code in the section after the `#if` is included if the *symbol* is defined.</span></span> <span data-ttu-id="4b124-114">기호는로 부정할 수도 있습니다 `!` .</span><span class="sxs-lookup"><span data-stu-id="4b124-114">The symbol can also be negated with `!`.</span></span>|
|`#else`|<span data-ttu-id="4b124-115">조건부 컴파일을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="4b124-115">Supports conditional compilation.</span></span> <span data-ttu-id="4b124-116">위의 `#if`와 함께 사용되는 기호를 정의하지 않은 경우 포함할 코드 섹션을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="4b124-116">Marks a section of code to include if the symbol used with the previous `#if` is not defined.</span></span>|
|`#endif`|<span data-ttu-id="4b124-117">조건부 컴파일을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="4b124-117">Supports conditional compilation.</span></span> <span data-ttu-id="4b124-118">코드의 조건부 섹션이 끝나는 지점을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="4b124-118">Marks the end of a conditional section of code.</span></span>|
|<span data-ttu-id="4b124-119">`#`꺽은선형 *int*,</span><span class="sxs-lookup"><span data-stu-id="4b124-119">`#`[line] *int*,</span></span><br/><span data-ttu-id="4b124-120">`#`꺽은선형 *int* *문자열*,</span><span class="sxs-lookup"><span data-stu-id="4b124-120">`#`[line] *int* *string*,</span></span><br/><span data-ttu-id="4b124-121">`#`꺽은선형 *int* *축 자-문자열*</span><span class="sxs-lookup"><span data-stu-id="4b124-121">`#`[line] *int* *verbatim-string*</span></span>|<span data-ttu-id="4b124-122">디버깅을 위해 원본 소스 코드 줄과 파일 이름을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="4b124-122">Indicates the original source code line and file name, for debugging.</span></span> <span data-ttu-id="4b124-123">이 기능은 F# 소스 코드를 생성하는 도구에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4b124-123">This feature is provided for tools that generate F# source code.</span></span>|
|<span data-ttu-id="4b124-124">`#nowarn`*warningcode*</span><span class="sxs-lookup"><span data-stu-id="4b124-124">`#nowarn` *warningcode*</span></span>|<span data-ttu-id="4b124-125">컴파일러 경고를 해제합니다.</span><span class="sxs-lookup"><span data-stu-id="4b124-125">Disables a compiler warning or warnings.</span></span> <span data-ttu-id="4b124-126">경고를 해제하려면 컴파일러 출력에서 해당 번호를 찾아 따옴표에 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="4b124-126">To disable a warning, find its number from the compiler output and include it in quotation marks.</span></span> <span data-ttu-id="4b124-127">"FS" 접두사를 생략합니다.</span><span class="sxs-lookup"><span data-stu-id="4b124-127">Omit the "FS" prefix.</span></span> <span data-ttu-id="4b124-128">같은 줄에서 여러 경고 번호를 해제하려면 각 번호를 따옴표에 포함하고 각 문자열을 공백으로 구분합니다.</span><span class="sxs-lookup"><span data-stu-id="4b124-128">To disable multiple warning numbers on the same line, include each number in quotation marks, and separate each string by a space.</span></span> <span data-ttu-id="4b124-129">예를 들어:</span><span class="sxs-lookup"><span data-stu-id="4b124-129">For example:</span></span>

`#nowarn "9" "40"`

<span data-ttu-id="4b124-130">경고를 사용 하지 않도록 설정 하는 영향은 지시문 앞에 있는 파일의 일부를 포함 하 여 전체 파일에 적용 됩니다. |</span><span class="sxs-lookup"><span data-stu-id="4b124-130">The effect of disabling a warning applies to the entire file, including portions of the file that precede the directive.|</span></span>

## <a name="conditional-compilation-directives"></a><span data-ttu-id="4b124-131">조건부 컴파일 지시문</span><span class="sxs-lookup"><span data-stu-id="4b124-131">Conditional Compilation Directives</span></span>

<span data-ttu-id="4b124-132">이러한 지시문 중 하나로 비활성화 된 코드는 Visual Studio Code 편집기에서 흐리게 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4b124-132">Code that is deactivated by one of these directives appears dimmed in the Visual Studio Code Editor.</span></span>

> [!NOTE]
> <span data-ttu-id="4b124-133">다른 언어에 있는 그대로 동일한 조건부 컴파일 지시문의 동작을 볼 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="4b124-133">The behavior of the conditional compilation directives is not the same as it is in other languages.</span></span> <span data-ttu-id="4b124-134">예를 들어 기호가 포함된 부울 식은 사용할 수 없으며 `true` 및 `false`가 특별한 의미를 가지지도 않습니다.</span><span class="sxs-lookup"><span data-stu-id="4b124-134">For example, you cannot use Boolean expressions involving symbols, and `true` and `false` have no special meaning.</span></span> <span data-ttu-id="4b124-135">`if` 지시문에 사용하는 기호는 명령줄이나 프로젝트 설정에서 정의해야 합니다. `define` 전처리기 지시문이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="4b124-135">Symbols that you use in the `if` directive must be defined by the command line or in the project settings; there is no `define` preprocessor directive.</span></span>

<span data-ttu-id="4b124-136">다음 코드에서는 `#if`, `#else` 및 `#endif` 지시문을 사용하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="4b124-136">The following code illustrates the use of the `#if`, `#else`, and `#endif` directives.</span></span> <span data-ttu-id="4b124-137">이 예제의 코드에는 `function1`에 대한 두 가지 버전의 정의가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4b124-137">In this example, the code contains two versions of the definition of `function1`.</span></span> <span data-ttu-id="4b124-138">`VERSION1` [-Define 컴파일러 옵션](./compiler-options.md)을 사용 하 여가 정의 되 면 지시문과 지시문 사이에 있는 코드가 `#if` `#else` 활성화 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4b124-138">When `VERSION1` is defined by using the [-define compiler option](./compiler-options.md), the code between the `#if` directive and the `#else` directive is activated.</span></span> <span data-ttu-id="4b124-139">그렇지 않은 경우에는 `#else`와 `#endif` 사이의 코드가 활성화됩니다.</span><span class="sxs-lookup"><span data-stu-id="4b124-139">Otherwise, the code between `#else` and `#endif` is activated.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet7301.fs)]

<span data-ttu-id="4b124-140">F#에는 `#define` 전처리기 지시문이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="4b124-140">There is no `#define` preprocessor directive in F#.</span></span> <span data-ttu-id="4b124-141">`#if` 지시문에 사용되는 기호를 정의하려면 컴파일러 옵션이나 프로젝트 설정을 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4b124-141">You must use the compiler option or project settings to define the symbols used by the `#if` directive.</span></span>

<span data-ttu-id="4b124-142">조건부 컴파일 지시문은 중첩하여 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4b124-142">Conditional compilation directives can be nested.</span></span> <span data-ttu-id="4b124-143">전처리기 지시문에서 들여쓰기는 중요하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="4b124-143">Indentation is not significant for preprocessor directives.</span></span>

<span data-ttu-id="4b124-144">를 사용 하 여 기호를 부정할 수도 있습니다 `!` .</span><span class="sxs-lookup"><span data-stu-id="4b124-144">You can also negate a symbol with `!`.</span></span> <span data-ttu-id="4b124-145">이 예제에서 문자열의 값은 디버깅 _하지 않을_ 경우에만 해당 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4b124-145">In this example, a string's value is something only when _not_ debugging:</span></span>

```fsharp
#if !DEBUG
let str = "Not debugging!"
#else
let str = "Debugging!"
#endif
```

## <a name="line-directives"></a><span data-ttu-id="4b124-146">줄 지시문</span><span class="sxs-lookup"><span data-stu-id="4b124-146">Line Directives</span></span>

<span data-ttu-id="4b124-147">빌드 과정에서 컴파일러를 통해 F# 코드의 오류를 보고할 때는 각 오류의 발생 지점에 해당하는 줄 번호가 참조 정보로 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="4b124-147">When building, the compiler reports errors in F# code by referencing line numbers on which each error occurs.</span></span> <span data-ttu-id="4b124-148">이러한 줄 번호는 1부터 시작합니다. 파일의 맨 첫 줄이 1번입니다.</span><span class="sxs-lookup"><span data-stu-id="4b124-148">These line numbers start at 1 for the first line in a file.</span></span> <span data-ttu-id="4b124-149">그러나 다른 도구를 사용하여 F# 소스 코드를 생성하는 경우에는 생성된 코드의 줄 번호가 일반적으로 크게 중요하지 않습니다. 생성된 F# 코드의 오류가 다른 소스에서 발생한 것일 가능성이 높기 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="4b124-149">However, if you are generating F# source code from another tool, the line numbers in the generated code are generally not of interest, because the errors in the generated F# code most likely arise from another source.</span></span> <span data-ttu-id="4b124-150">`#line` 지시문을 사용하면 다른 도구를 통해 F# 소스 코드를 생성할 때 원래 줄 번호와 소스 파일에 대한 정보를 생성된 F# 코드에 전달할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4b124-150">The `#line` directive provides a way for authors of tools that generate F# source code to pass information about the original line numbers and source files to the generated F# code.</span></span>

<span data-ttu-id="4b124-151">`#line` 지시문을 사용하는 경우 파일 이름을 따옴표로 묶어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4b124-151">When you use the `#line` directive, file names must be enclosed in quotation marks.</span></span> <span data-ttu-id="4b124-152">문자열 앞에 축자 토큰(`@`)이 오지 않는 경우 백슬래시 문자를 경로에 사용하려면 한 개가 아닌 두 개의 백슬래시 문자를 사용하여 이를 이스케이프해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4b124-152">Unless the verbatim token (`@`) appears in front of the string, you must escape backslash characters by using two backslash characters instead of one in order to use them in the path.</span></span> <span data-ttu-id="4b124-153">다음은 유효한 줄 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="4b124-153">The following are valid line tokens.</span></span> <span data-ttu-id="4b124-154">이 예제에서는 도구를 사용하여 원래 파일 `Script1`을 실행한 결과로 F# 코드 파일이 자동 생성되며 이러한 지시문이 있는 위치의 코드가 파일 `Script1`의 25번 줄에 있는 몇몇 토큰으로부터 생성되는 것으로 가정합니다.</span><span class="sxs-lookup"><span data-stu-id="4b124-154">In these examples, assume that the original file `Script1` results in an automatically generated F# code file when it is run through a tool, and that the code at the location of these directives is generated from some tokens at line 25 in file `Script1`.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet7303.fs)]

<span data-ttu-id="4b124-155">이 토큰은 해당 위치에서 생성되는 F# 코드가 `Script1`의 `25`번 줄 또는 그 부근에 있는 몇몇 구문으로부터 파생됨을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="4b124-155">These tokens indicate that the F# code generated at this location is derived from some constructs at or near line `25` in `Script1`.</span></span>

## <a name="compiler-directives"></a><span data-ttu-id="4b124-156">컴파일러 지시문</span><span class="sxs-lookup"><span data-stu-id="4b124-156">Compiler Directives</span></span>

<span data-ttu-id="4b124-157">컴파일러 지시문은 # 기호가 접두사로 사용된다는 점에서 전처리기 지시문과 형태가 비슷하지만 전처리기에 의해 해석되지 않고 컴파일러를 통해 해석 및 처리되도록 남겨진다는 점에서 차이가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4b124-157">Compiler directives resemble preprocessor directives, because they are prefixed with a # sign, but instead of being interpreted by the preprocessor, they are left for the compiler to interpret and act on.</span></span>

<span data-ttu-id="4b124-158">다음 표에는 F#에서 사용할 수 있는 컴파일러 지시문이 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4b124-158">The following table lists the compiler directive that is available in F#.</span></span>

|<span data-ttu-id="4b124-159">지시문</span><span class="sxs-lookup"><span data-stu-id="4b124-159">Directive</span></span>|<span data-ttu-id="4b124-160">설명</span><span class="sxs-lookup"><span data-stu-id="4b124-160">Description</span></span>|
|---------|-----------|
|<span data-ttu-id="4b124-161">`#light` ["&#124;" 꺼짐 "]</span><span class="sxs-lookup"><span data-stu-id="4b124-161">`#light` ["on"&#124;"off"]</span></span>|<span data-ttu-id="4b124-162">다른 ML 버전과의 호환성을 위해 간단한 구문을 사용하거나 사용하지 않도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="4b124-162">Enables or disables lightweight syntax, for compatibility with other versions of ML.</span></span> <span data-ttu-id="4b124-163">기본적으로 간단한 구문을 사용하도록 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="4b124-163">By default, lightweight syntax is enabled.</span></span> <span data-ttu-id="4b124-164">자세한 구문은 항상 사용할 수 있도록 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="4b124-164">Verbose syntax is always enabled.</span></span> <span data-ttu-id="4b124-165">따라서 간단한 구문과 자세한 구문을 함께 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4b124-165">Therefore, you can use both lightweight syntax and verbose syntax.</span></span> <span data-ttu-id="4b124-166">`#light` 지시문 자체는 `#light "on"`과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="4b124-166">The directive `#light` by itself is equivalent to `#light "on"`.</span></span> <span data-ttu-id="4b124-167">`#light "off"`를 지정하는 경우에는 모든 언어 구문에 대해 자세한 구문 형식을 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4b124-167">If you specify `#light "off"`, you must use verbose syntax for all language constructs.</span></span> <span data-ttu-id="4b124-168">F# 관련 설명에 나오는 구문은 간단한 구문을 사용하는 것을 전제로 하여 제시됩니다.</span><span class="sxs-lookup"><span data-stu-id="4b124-168">Syntax in the documentation for F# is presented with the assumption that you are using lightweight syntax.</span></span> <span data-ttu-id="4b124-169">자세한 내용은 자세한 [구문](verbose-syntax.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="4b124-169">For more information, see [Verbose Syntax](verbose-syntax.md).</span></span>|

<span data-ttu-id="4b124-170">인터프리터 (fsi.exe) 지시문은 [F #을 사용한 대화형 프로그래밍](../tutorials/fsharp-interactive/index.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="4b124-170">For interpreter (fsi.exe) directives, see [Interactive Programming with F#](../tutorials/fsharp-interactive/index.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="4b124-171">참고 항목</span><span class="sxs-lookup"><span data-stu-id="4b124-171">See also</span></span>

- [<span data-ttu-id="4b124-172">F# 언어 참조</span><span class="sxs-lookup"><span data-stu-id="4b124-172">F# Language Reference</span></span>](index.md)
- [<span data-ttu-id="4b124-173">컴파일러 옵션</span><span class="sxs-lookup"><span data-stu-id="4b124-173">Compiler Options</span></span>](compiler-options.md)
