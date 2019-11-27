---
title: Option Infer 문
ms.date: 07/20/2015
f1_keywords:
- vb.OptionInfer
- vb.Infer
helpviewer_keywords:
- variables [Visual Basic], declaring
- Option Infer statement [Visual Basic]
- Infer keyword [Visual Basic]
- declaring variables [Visual Basic], inferred
- inferred variable declaration
ms.assetid: 4ad3e6e9-8f5b-4209-a248-de22ef6e4652
ms.openlocfilehash: 53bc9d41f28f63061db2012395480aa6be7515dd
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/22/2019
ms.locfileid: "74346492"
---
# <a name="option-infer-statement"></a><span data-ttu-id="d125b-102">Option Infer 문</span><span class="sxs-lookup"><span data-stu-id="d125b-102">Option Infer Statement</span></span>

<span data-ttu-id="d125b-103">변수를 선언할 때 지역 형식 유추를 사용하도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="d125b-103">Enables the use of local type inference in declaring variables.</span></span>

## <a name="syntax"></a><span data-ttu-id="d125b-104">구문</span><span class="sxs-lookup"><span data-stu-id="d125b-104">Syntax</span></span>

```vb
Option Infer { On | Off }
```

## <a name="parts"></a><span data-ttu-id="d125b-105">요소</span><span class="sxs-lookup"><span data-stu-id="d125b-105">Parts</span></span>

|<span data-ttu-id="d125b-106">용어</span><span class="sxs-lookup"><span data-stu-id="d125b-106">Term</span></span>|<span data-ttu-id="d125b-107">정의</span><span class="sxs-lookup"><span data-stu-id="d125b-107">Definition</span></span>|
|---|---|
|`On`|<span data-ttu-id="d125b-108">(선택 사항)</span><span class="sxs-lookup"><span data-stu-id="d125b-108">Optional.</span></span> <span data-ttu-id="d125b-109">지역 형식 유추를 사용하도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="d125b-109">Enables local type inference.</span></span>|
|`Off`|<span data-ttu-id="d125b-110">(선택 사항)</span><span class="sxs-lookup"><span data-stu-id="d125b-110">Optional.</span></span> <span data-ttu-id="d125b-111">지역 형식 유추를 사용하지 않도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="d125b-111">Disables local type inference.</span></span>|

## <a name="remarks"></a><span data-ttu-id="d125b-112">주의</span><span class="sxs-lookup"><span data-stu-id="d125b-112">Remarks</span></span>

<span data-ttu-id="d125b-113">파일에서 `Option Infer`를 설정하려면 파일 맨 위(기타 모든 소스 코드 앞)에 `Option Infer On` 또는 `Option Infer Off`를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="d125b-113">To set `Option Infer` in a file, type `Option Infer On` or `Option Infer Off` at the top of the file, before any other source code.</span></span> <span data-ttu-id="d125b-114">파일에서 `Option Infer`에 대해 설정된 값이 IDE 또는 명령줄에 설정된 값과 충돌하는 경우에는 파일의 값이 우선적으로 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="d125b-114">If the value set for `Option Infer` in a file conflicts with the value set in the IDE or on the command line, the value in the file has precedence.</span></span>

<span data-ttu-id="d125b-115">`Option Infer`를 `On`으로 설정하면 데이터 형식을 명시적으로 설명하지 않고 로컬 변수를 선언할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d125b-115">When you set `Option Infer` to `On`, you can declare local variables without explicitly stating a data type.</span></span> <span data-ttu-id="d125b-116">컴파일러는 초기화 식의 형식에서 변수의 데이터 형식을 유추합니다.</span><span class="sxs-lookup"><span data-stu-id="d125b-116">The compiler infers the data type of a variable from the type of its initialization expression.</span></span>

<span data-ttu-id="d125b-117">다음 그림에서는 `Option Infer`가 설정되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d125b-117">In the following illustration, `Option Infer` is turned on.</span></span> <span data-ttu-id="d125b-118">`Dim someVar = 2` 선언의 변수는 형식 유추에 의해 정수로 선언됩니다.</span><span class="sxs-lookup"><span data-stu-id="d125b-118">The variable in the declaration `Dim someVar = 2` is declared as an integer by type inference.</span></span>

<span data-ttu-id="d125b-119">다음 스크린샷은 추론 옵션이 설정 된 경우 IntelliSense를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="d125b-119">The following screenshot shows IntelliSense when Option Infer is on:</span></span>

![옵션 추론을 on으로 설정 하는 경우 IntelliSense 보기를 보여 주는 스크린샷](./media/option-infer-statement/option-infer-as-integer-on.png)

<span data-ttu-id="d125b-121">다음 그림에서는 `Option Infer`가 해제되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d125b-121">In the following illustration, `Option Infer` is turned off.</span></span> <span data-ttu-id="d125b-122">`Dim someVar = 2` 선언의 변수는 형식 유추에 의해 `Object`로 선언됩니다.</span><span class="sxs-lookup"><span data-stu-id="d125b-122">The variable in the declaration `Dim someVar = 2` is declared as an `Object` by type inference.</span></span> <span data-ttu-id="d125b-123">이 예제에서 **Option Strict** 설정은 [컴파일 페이지, 프로젝트 디자이너 (Visual Basic)](/visualstudio/ide/reference/compile-page-project-designer-visual-basic)에서 **Off** 로 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d125b-123">In this example, the **Option Strict** setting is set to **Off** on the [Compile Page, Project Designer (Visual Basic)](/visualstudio/ide/reference/compile-page-project-designer-visual-basic).</span></span>

<span data-ttu-id="d125b-124">다음 스크린샷은 추론 옵션이 해제 된 경우 IntelliSense를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="d125b-124">The following screenshot shows IntelliSense when Option Infer is off:</span></span>

![옵션 추론을 해제 한 경우 IntelliSense 보기를 보여 주는 스크린샷](./media/option-infer-statement/option-infer-as-object-off.png)

> [!NOTE]
> <span data-ttu-id="d125b-126">변수가 `Object`로 선언되면 프로그램을 실행하는 동안 런타임 형식이 변경될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d125b-126">When a variable is declared as an `Object`, the run-time type can change while the program is running.</span></span> <span data-ttu-id="d125b-127">Visual Basic은 *boxing* 및 *unboxing* 이라는 작업을 수행 하 여 `Object`와 값 형식 간에 변환 하 여 실행 속도를 느리게 합니다.</span><span class="sxs-lookup"><span data-stu-id="d125b-127">Visual Basic performs operations called *boxing* and *unboxing* to convert between an `Object` and a value type, which makes execution slower.</span></span> <span data-ttu-id="d125b-128">Boxing 및 unboxing에 대 한 자세한 내용은 [Visual Basic 언어 사양](~/_vblang/spec/conversions.md#value-type-conversions)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="d125b-128">For information about boxing and unboxing, see the [Visual Basic Language Specification](~/_vblang/spec/conversions.md#value-type-conversions).</span></span>

<span data-ttu-id="d125b-129">형식 유추는 프로시저 수준에서 적용되며 클래스, 구조체, 모듈 또는 인터페이스의 프로시저 외부에는 적용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d125b-129">Type inference applies at the procedure level, and does not apply outside a procedure in a class, structure, module, or interface.</span></span>

<span data-ttu-id="d125b-130">자세한 내용은 [지역 형식 유추](../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="d125b-130">For additional information, see [Local Type Inference](../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md).</span></span>

## <a name="when-an-option-infer-statement-is-not-present"></a><span data-ttu-id="d125b-131">Option Infer 문이 없는 경우</span><span class="sxs-lookup"><span data-stu-id="d125b-131">When an Option Infer Statement Is Not Present</span></span>

<span data-ttu-id="d125b-132">소스 코드에 `Option Infer` 문이 포함 되어 있지 않은 경우 [컴파일 페이지, 프로젝트 디자이너 (Visual Basic)](/visualstudio/ide/reference/compile-page-project-designer-visual-basic) 에 대 한 **옵션 유추 옵션이** 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d125b-132">If the source code does not contain an `Option Infer` statement, the **Option Infer** setting on the [Compile Page, Project Designer (Visual Basic)](/visualstudio/ide/reference/compile-page-project-designer-visual-basic) is used.</span></span> <span data-ttu-id="d125b-133">명령줄 컴파일러를 사용 하는 경우 [-옵션 추론](../../../visual-basic/reference/command-line-compiler/optioninfer.md) 컴파일러 옵션이 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d125b-133">If the command-line compiler is used, the [-optioninfer](../../../visual-basic/reference/command-line-compiler/optioninfer.md) compiler option is used.</span></span>

#### <a name="to-set-option-infer-in-the-ide"></a><span data-ttu-id="d125b-134">IDE에서 Option Infer를 설정하려면</span><span class="sxs-lookup"><span data-stu-id="d125b-134">To set Option Infer in the IDE</span></span>

1. <span data-ttu-id="d125b-135">**솔루션 탐색기**에서 프로젝트를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="d125b-135">In **Solution Explorer**, select a project.</span></span> <span data-ttu-id="d125b-136">**프로젝트** 메뉴에서 **속성**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="d125b-136">On the **Project** menu, click **Properties**.</span></span>

2. <span data-ttu-id="d125b-137">**컴파일** 탭을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="d125b-137">Click the **Compile** tab.</span></span>

3. <span data-ttu-id="d125b-138">**유추 옵션** 상자에서 값을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="d125b-138">Set the value in the **Option infer** box.</span></span>

<span data-ttu-id="d125b-139">새 프로젝트를 만들 때 **컴파일** 탭의 **유추 설정 옵션이** **VB 기본값** 대화 상자의 **유추 옵션** 으로 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d125b-139">When you create a new project, the **Option Infer** setting on the **Compile** tab is set to the **Option Infer** setting in the **VB Defaults** dialog box.</span></span> <span data-ttu-id="d125b-140">**VB 기본값** 대화 상자에 액세스 하려면 **도구** 메뉴에서 **옵션**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="d125b-140">To access the **VB Defaults** dialog box, on the **Tools** menu, click **Options**.</span></span> <span data-ttu-id="d125b-141">**옵션** 대화 상자에서 **프로젝트 및 솔루션**을 확장하고 **VB 기본값**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="d125b-141">In the **Options** dialog box, expand **Projects and Solutions**, and then click **VB Defaults**.</span></span> <span data-ttu-id="d125b-142">**VB 기본값** 의 초기 기본 설정은 `On`입니다.</span><span class="sxs-lookup"><span data-stu-id="d125b-142">The initial default setting in **VB Defaults** is `On`.</span></span>

#### <a name="to-set-option-infer-on-the-command-line"></a><span data-ttu-id="d125b-143">명령줄에서 Option Infer를 설정하려면</span><span class="sxs-lookup"><span data-stu-id="d125b-143">To set Option Infer on the command line</span></span>

<span data-ttu-id="d125b-144">**Vbc** 명령에 [-옵션 추론](../../../visual-basic/reference/command-line-compiler/optioninfer.md) 컴파일러 옵션을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="d125b-144">Include the [-optioninfer](../../../visual-basic/reference/command-line-compiler/optioninfer.md) compiler option in the **vbc** command.</span></span>

## <a name="default-data-types-and-values"></a><span data-ttu-id="d125b-145">기본 데이터 형식 및 값</span><span class="sxs-lookup"><span data-stu-id="d125b-145">Default Data Types and Values</span></span>

<span data-ttu-id="d125b-146">다음 테이블에는 `Dim` 문에서 데이터 형식과 이니셜라이저를 지정하는 다양한 조합의 결과에 대한 설명이 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d125b-146">The following table describes the results of various combinations of specifying the data type and initializer in a `Dim` statement.</span></span>

|<span data-ttu-id="d125b-147">데이터 형식 지정 여부</span><span class="sxs-lookup"><span data-stu-id="d125b-147">Data type specified?</span></span>|<span data-ttu-id="d125b-148">이니셜라이저 지정 여부</span><span class="sxs-lookup"><span data-stu-id="d125b-148">Initializer specified?</span></span>|<span data-ttu-id="d125b-149">예제</span><span class="sxs-lookup"><span data-stu-id="d125b-149">Example</span></span>|<span data-ttu-id="d125b-150">결과</span><span class="sxs-lookup"><span data-stu-id="d125b-150">Result</span></span>|
|---|---|---|---|
|<span data-ttu-id="d125b-151">아니요</span><span class="sxs-lookup"><span data-stu-id="d125b-151">No</span></span>|<span data-ttu-id="d125b-152">아니요</span><span class="sxs-lookup"><span data-stu-id="d125b-152">No</span></span>|`Dim qty`|<span data-ttu-id="d125b-153">`Option Strict`가 off(기본값)이면 변수는 `Nothing`으로 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="d125b-153">If `Option Strict` is off (the default), the variable is set to `Nothing`.</span></span><br /><br /> <span data-ttu-id="d125b-154">`Option Strict`가 on이면 컴파일 시간 오류가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="d125b-154">If `Option Strict` is on, a compile-time error occurs.</span></span>|
|<span data-ttu-id="d125b-155">아니요</span><span class="sxs-lookup"><span data-stu-id="d125b-155">No</span></span>|<span data-ttu-id="d125b-156">예</span><span class="sxs-lookup"><span data-stu-id="d125b-156">Yes</span></span>|`Dim qty = 5`|<span data-ttu-id="d125b-157">`Option Infer`가 on(기본값)이면 변수가 이니셜라이저의 데이터 형식을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="d125b-157">If `Option Infer` is on (the default), the variable takes the data type of the initializer.</span></span> <span data-ttu-id="d125b-158">[지역 형식 유추](../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="d125b-158">See [Local Type Inference](../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md).</span></span><br /><br /> <span data-ttu-id="d125b-159">`Option Infer`가 off이고 `Option Strict`고 off이면 변수가 `Object`의 데이터 형식을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="d125b-159">If `Option Infer` is off and `Option Strict` is off, the variable takes the data type of `Object`.</span></span><br /><br /> <span data-ttu-id="d125b-160">`Option Infer`가 off이고 `Option Strict`는 on이면 컴파일 시간 오류가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="d125b-160">If `Option Infer` is off and `Option Strict` is on, a compile-time error occurs.</span></span>|
|<span data-ttu-id="d125b-161">예</span><span class="sxs-lookup"><span data-stu-id="d125b-161">Yes</span></span>|<span data-ttu-id="d125b-162">아니요</span><span class="sxs-lookup"><span data-stu-id="d125b-162">No</span></span>|`Dim qty As Integer`|<span data-ttu-id="d125b-163">변수는 데이터 형식의 기본값으로 초기화됩니다.</span><span class="sxs-lookup"><span data-stu-id="d125b-163">The variable is initialized to the default value for the data type.</span></span> <span data-ttu-id="d125b-164">자세한 내용은 [Dim 문](../../../visual-basic/language-reference/statements/dim-statement.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="d125b-164">For more information, see [Dim Statement](../../../visual-basic/language-reference/statements/dim-statement.md).</span></span>|
|<span data-ttu-id="d125b-165">예</span><span class="sxs-lookup"><span data-stu-id="d125b-165">Yes</span></span>|<span data-ttu-id="d125b-166">예</span><span class="sxs-lookup"><span data-stu-id="d125b-166">Yes</span></span>|`Dim qty  As Integer = 5`|<span data-ttu-id="d125b-167">이니셜라이저의 데이터 형식을 지정한 데이터 형식으로 변환할 수 없으면 컴파일 시간 오류가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="d125b-167">If the data type of the initializer is not convertible to the specified data type, a compile-time error occurs.</span></span>|

## <a name="example"></a><span data-ttu-id="d125b-168">예제</span><span class="sxs-lookup"><span data-stu-id="d125b-168">Example</span></span>

<span data-ttu-id="d125b-169">다음 예제에서는 `Option Infer` 문이 지역 형식 유추를 사용하도록 설정하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="d125b-169">The following examples demonstrate how the `Option Infer` statement enables local type inference.</span></span>

[!code-vb[VbVbalrTypeInference#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrTypeInference/VB/Class1.vb#6)]

## <a name="example"></a><span data-ttu-id="d125b-170">예제</span><span class="sxs-lookup"><span data-stu-id="d125b-170">Example</span></span>

<span data-ttu-id="d125b-171">다음 예제에서는 변수가 `Object`로 식별되는 경우 런타임 형식이 달라질 수 있음을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="d125b-171">The following example demonstrates that the run-time type can differ when a variable is identified as an `Object`.</span></span>

[!code-vb[VbVbalrTypeInference#11](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrTypeInference/VB/Class1.vb#11)]

## <a name="see-also"></a><span data-ttu-id="d125b-172">참고 항목</span><span class="sxs-lookup"><span data-stu-id="d125b-172">See also</span></span>

- [<span data-ttu-id="d125b-173">Dim 문</span><span class="sxs-lookup"><span data-stu-id="d125b-173">Dim Statement</span></span>](../../../visual-basic/language-reference/statements/dim-statement.md)
- [<span data-ttu-id="d125b-174">지역 형식 유추</span><span class="sxs-lookup"><span data-stu-id="d125b-174">Local Type Inference</span></span>](../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)
- [<span data-ttu-id="d125b-175">Option Compare 문</span><span class="sxs-lookup"><span data-stu-id="d125b-175">Option Compare Statement</span></span>](../../../visual-basic/language-reference/statements/option-compare-statement.md)
- [<span data-ttu-id="d125b-176">Option Explicit 문</span><span class="sxs-lookup"><span data-stu-id="d125b-176">Option Explicit Statement</span></span>](../../../visual-basic/language-reference/statements/option-explicit-statement.md)
- [<span data-ttu-id="d125b-177">Option Strict 문</span><span class="sxs-lookup"><span data-stu-id="d125b-177">Option Strict Statement</span></span>](../../../visual-basic/language-reference/statements/option-strict-statement.md)
- [<span data-ttu-id="d125b-178">옵션 대화 상자, 프로젝트, Visual Basic 기본값</span><span class="sxs-lookup"><span data-stu-id="d125b-178">Visual Basic Defaults, Projects, Options Dialog Box</span></span>](/visualstudio/ide/reference/visual-basic-defaults-projects-options-dialog-box)
- [<span data-ttu-id="d125b-179">-optioninfer</span><span class="sxs-lookup"><span data-stu-id="d125b-179">-optioninfer</span></span>](../../../visual-basic/reference/command-line-compiler/optioninfer.md)
- [<span data-ttu-id="d125b-180">boxing 및 unboxing</span><span class="sxs-lookup"><span data-stu-id="d125b-180">Boxing and Unboxing</span></span>](../../../csharp/programming-guide/types/boxing-and-unboxing.md)
