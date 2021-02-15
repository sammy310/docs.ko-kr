---
description: '자세한 정보: 지역 형식 유추 (Visual Basic)'
title: 지역 형식 유추
ms.date: 07/20/2015
f1_keywords:
- local type inference
- vb.TypeInfer
helpviewer_keywords:
- Option Infer statement [Visual Basic]
- local type inference [Visual Basic]
- implicitly-typed local variables [Visual Basic]
- variables [Visual Basic], type inference
- inference [Visual Basic]
- type inference [Visual Basic]
ms.assetid: b8307f18-2e56-4ab3-a45a-826873f400f6
ms.openlocfilehash: 50be8544229360287d2aef27f31360d7140640ac
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/14/2021
ms.locfileid: "100481703"
---
# <a name="local-type-inference-visual-basic"></a><span data-ttu-id="2eacc-103">지역 형식 유추(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="2eacc-103">Local Type Inference (Visual Basic)</span></span>

<span data-ttu-id="2eacc-104">Visual Basic 컴파일러는 *형식 유추* 를 사용 하 여 절 없이 선언 된 지역 변수의 데이터 형식을 확인 합니다 `As` .</span><span class="sxs-lookup"><span data-stu-id="2eacc-104">The Visual Basic compiler uses *type inference* to determine the data types of local variables declared without an `As` clause.</span></span> <span data-ttu-id="2eacc-105">컴파일러는 초기화 식의 형식에서 변수 형식을 유추 합니다.</span><span class="sxs-lookup"><span data-stu-id="2eacc-105">The compiler infers the type of the variable from the type of the initialization expression.</span></span> <span data-ttu-id="2eacc-106">이렇게 하면 다음 예제와 같이 형식을 명시적으로 명시 하지 않고 변수를 선언할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2eacc-106">This enables you to declare variables without explicitly stating a type, as shown in the following example.</span></span> <span data-ttu-id="2eacc-107">선언 결과로 `num1` 및 `num2` 는 모두 정수로 강력 하 게 형식화 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2eacc-107">As a result of the declarations, both `num1` and `num2` are strongly typed as integers.</span></span>

[!code-vb[VbVbalrTypeInference#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrTypeInference/VB/Class1.vb#1)]

> [!NOTE]
> <span data-ttu-id="2eacc-108">`num2`이전 예제에서로 형식화 하지 않으려는 경우 `Integer` 또는와 같은 선언을 사용 하 여 다른 형식을 지정할 수 있습니다 `Dim num3 As Object = 3` `Dim num4 As Double = 3` .</span><span class="sxs-lookup"><span data-stu-id="2eacc-108">If you do not want `num2` in the previous example to be typed as an `Integer`, you can specify another type by using a declaration like `Dim num3 As Object = 3` or `Dim num4 As Double = 3`.</span></span>

> [!NOTE]
> <span data-ttu-id="2eacc-109">형식 유추는 비정적 지역 변수에만 사용할 수 있습니다. 클래스 필드, 속성 또는 함수의 형식을 결정 하는 데 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="2eacc-109">Type inference can be used only for non-static local variables; it cannot be used to determine the type of class fields, properties, or functions.</span></span>

<span data-ttu-id="2eacc-110">지역 형식 유추는 프로시저 수준에서 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2eacc-110">Local type inference applies at procedure level.</span></span> <span data-ttu-id="2eacc-111">모듈 수준에서 변수를 선언 하는 데 사용할 수 없습니다 (클래스, 구조체, 모듈 또는 인터페이스 내에서 프로시저나 블록 내에서 제외).</span><span class="sxs-lookup"><span data-stu-id="2eacc-111">It cannot be used to declare variables at module level (within a class, structure, module, or interface but not within a procedure or block).</span></span> <span data-ttu-id="2eacc-112">`num2`이전 예제에서 프로시저의 지역 변수가 아닌 클래스의 필드인 경우 선언으로 인해에 오류가 발생 `Option Strict` 하 고가 off로 분류 됩니다 `num2` `Object` `Option Strict` .</span><span class="sxs-lookup"><span data-stu-id="2eacc-112">If `num2` in the previous example were a field of a class instead of a local variable in a procedure, the declaration would cause an error with `Option Strict` on, and would classify `num2` as an `Object` with `Option Strict` off.</span></span> <span data-ttu-id="2eacc-113">마찬가지로 지역 형식 유추는로 선언 된 프로시저 수준 변수에는 적용 되지 않습니다 `Static` .</span><span class="sxs-lookup"><span data-stu-id="2eacc-113">Similarly, local type inference does not apply to procedure level variables declared as `Static`.</span></span>

## <a name="type-inference-vs-late-binding"></a><span data-ttu-id="2eacc-114">형식 유추 및 런타임에 바인딩</span><span class="sxs-lookup"><span data-stu-id="2eacc-114">Type Inference vs. Late Binding</span></span>

<span data-ttu-id="2eacc-115">형식 유추를 사용 하는 코드는 런타임에 바인딩을 사용 하는 코드와 비슷합니다.</span><span class="sxs-lookup"><span data-stu-id="2eacc-115">Code that uses type inference resembles code that relies on late binding.</span></span> <span data-ttu-id="2eacc-116">그러나 형식 유추는 변수를 그대로 유지 하는 대신 강력한 형식을 갖습니다 `Object` .</span><span class="sxs-lookup"><span data-stu-id="2eacc-116">However, type inference strongly types the variable instead of leaving it as `Object`.</span></span> <span data-ttu-id="2eacc-117">컴파일러는 변수의 이니셜라이저를 사용 하 여 컴파일 시간에 변수의 형식을 확인 하 여 초기 바인딩된 코드를 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="2eacc-117">The compiler uses a variable's initializer to determine the variable's type at compile time to produce early-bound code.</span></span> <span data-ttu-id="2eacc-118">이전 예제에서와 `num2` 마찬가지로는 `num1` 로 형식화 됩니다 `Integer` .</span><span class="sxs-lookup"><span data-stu-id="2eacc-118">In the previous example, `num2`, like `num1`, is typed as an `Integer`.</span></span>

<span data-ttu-id="2eacc-119">초기 바인딩된 변수의 동작은 런타임에 바인딩된 변수의 동작과 다르며이는 런타임에만 형식을 알 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2eacc-119">The behavior of early-bound variables differs from that of late-bound variables, for which the type is known only at run time.</span></span> <span data-ttu-id="2eacc-120">초기 형식을 알면 컴파일러가 실행 전에 문제를 식별 하 고, 메모리를 정확 하 게 할당 하 고, 기타 최적화를 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2eacc-120">Knowing the type early enables the compiler to identify problems before execution, allocate memory precisely, and perform other optimizations.</span></span> <span data-ttu-id="2eacc-121">또한 초기 바인딩을 사용 하면 Visual Basic IDE (통합 개발 환경)에서 개체의 멤버에 대 한 IntelliSense 도움말을 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2eacc-121">Early binding also enables the Visual Basic integrated development environment (IDE) to provide IntelliSense Help about the members of an object.</span></span> <span data-ttu-id="2eacc-122">성능에 대 한 초기 바인딩도 선호 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2eacc-122">Early binding is also preferred for performance.</span></span> <span data-ttu-id="2eacc-123">이는 런타임에 바인딩된 변수에 저장 된 모든 데이터를 형식으로 래핑해야 하 `Object` 고 런타임에 형식의 멤버에 액세스 하는 것 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="2eacc-123">This is because all data stored in a late-bound variable must be wrapped as type `Object`, and accessing members of the type at run time makes the program slower.</span></span>

## <a name="examples"></a><span data-ttu-id="2eacc-124">예제</span><span class="sxs-lookup"><span data-stu-id="2eacc-124">Examples</span></span>

<span data-ttu-id="2eacc-125">형식 유추는 지역 변수가 절 없이 선언 되 고 초기화 될 때 발생 `As` 합니다.</span><span class="sxs-lookup"><span data-stu-id="2eacc-125">Type inference occurs when a local variable is declared without an `As` clause and initialized.</span></span> <span data-ttu-id="2eacc-126">컴파일러는 할당 된 초기 값의 형식을 변수 형식으로 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="2eacc-126">The compiler uses the type of the assigned initial value as the type of the variable.</span></span> <span data-ttu-id="2eacc-127">예를 들어 다음 코드 줄은 각각 형식의 변수를 선언 `String` 합니다.</span><span class="sxs-lookup"><span data-stu-id="2eacc-127">For example, each of the following lines of code declares a variable of type `String`.</span></span>

[!code-vb[VbVbalrTypeInference#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrTypeInference/VB/Class1.vb#2)]

<span data-ttu-id="2eacc-128">다음 코드에서는 두 가지 동일한 방법으로 정수 배열을 만드는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="2eacc-128">The following code demonstrates two equivalent ways to create an array of integers.</span></span>

[!code-vb[VbVbalrTypeInference#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrTypeInference/VB/Class1.vb#3)]

<span data-ttu-id="2eacc-129">형식 유추를 사용 하 여 루프 제어 변수의 형식을 결정 하는 것이 편리 합니다.</span><span class="sxs-lookup"><span data-stu-id="2eacc-129">It is convenient to use type inference to determine the type of a loop control variable.</span></span> <span data-ttu-id="2eacc-130">다음 코드에서 컴파일러는 `number` `Integer` `someNumbers2` 이전 예제에서 정수 배열 이기 때문에가 인 것으로 유추 합니다.</span><span class="sxs-lookup"><span data-stu-id="2eacc-130">In the following code, the compiler infers that `number` is an `Integer` because `someNumbers2` from the previous example is an array of integers.</span></span>

[!code-vb[VbVbalrTypeInference#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrTypeInference/VB/Class1.vb#4)]

<span data-ttu-id="2eacc-131">`Using`다음 예제에서 보여 주는 것 처럼 문에서 지역 형식 유추를 사용 하 여 리소스 이름의 형식을 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2eacc-131">Local type inference can be used in `Using` statements to establish the type of the resource name, as the following example demonstrates.</span></span>

[!code-vb[VbVbalrTypeInference#7](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrTypeInference/VB/Class1.vb#7)]

<span data-ttu-id="2eacc-132">다음 예제와 같이 함수의 반환 값에서 변수의 형식을 유추할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2eacc-132">The type of a variable can also be inferred from the return values of functions, as the following example demonstrates.</span></span> <span data-ttu-id="2eacc-133">`pList1`및 `pList2` 는 모두 프로세스의 배열을 반환 하기 때문에 프로세스의 배열 `Process.GetProcesses` 입니다.</span><span class="sxs-lookup"><span data-stu-id="2eacc-133">Both `pList1` and `pList2` are arrays of processes because `Process.GetProcesses` returns an array of processes.</span></span>

[!code-vb[VbVbalrTypeInference#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrTypeInference/VB/Class1.vb#5)]

## <a name="option-infer"></a><span data-ttu-id="2eacc-134">Option Infer</span><span class="sxs-lookup"><span data-stu-id="2eacc-134">Option Infer</span></span>

<span data-ttu-id="2eacc-135">`Option Infer` 특정 파일에서 로컬 형식 유추가 허용 되는지 여부를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2eacc-135">`Option Infer` enables you specify whether local type inference is allowed in a particular file.</span></span> <span data-ttu-id="2eacc-136">옵션을 사용 하도록 설정 하거나 차단 하려면 파일의 시작 부분에 다음 문 중 하나를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="2eacc-136">To enable or to block the option, type one of the following statements at the start of the file.</span></span>

`Option Infer On`

`Option Infer Off`

<span data-ttu-id="2eacc-137">코드에 값을 지정 하지 않으면 `Option Infer` 컴파일러 기본값은 `Option Infer On` 입니다.</span><span class="sxs-lookup"><span data-stu-id="2eacc-137">If you do not specify a value for `Option Infer` in your code, the compiler default is `Option Infer On`.</span></span>

<span data-ttu-id="2eacc-138">파일에서 `Option Infer`에 대해 설정된 값이 IDE 또는 명령줄에 설정된 값과 충돌하는 경우에는 파일의 값이 우선적으로 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="2eacc-138">If the value set for `Option Infer` in a file conflicts with the value set in the IDE or on the command line, the value in the file has precedence.</span></span>

<span data-ttu-id="2eacc-139">자세한 내용은 [Option 유추 문](../../../language-reference/statements/option-infer-statement.md) 및 [컴파일 페이지, 프로젝트 디자이너 (Visual Basic)](/visualstudio/ide/reference/compile-page-project-designer-visual-basic)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="2eacc-139">For more information, see [Option Infer Statement](../../../language-reference/statements/option-infer-statement.md) and [Compile Page, Project Designer (Visual Basic)](/visualstudio/ide/reference/compile-page-project-designer-visual-basic).</span></span>

## <a name="see-also"></a><span data-ttu-id="2eacc-140">추가 정보</span><span class="sxs-lookup"><span data-stu-id="2eacc-140">See also</span></span>

- [<span data-ttu-id="2eacc-141">익명 형식</span><span class="sxs-lookup"><span data-stu-id="2eacc-141">Anonymous Types</span></span>](../objects-and-classes/anonymous-types.md)
- [<span data-ttu-id="2eacc-142">초기 바인딩 및 런타임에 바인딩</span><span class="sxs-lookup"><span data-stu-id="2eacc-142">Early and Late Binding</span></span>](../early-late-binding/index.md)
- [<span data-ttu-id="2eacc-143">For Each...Next 문</span><span class="sxs-lookup"><span data-stu-id="2eacc-143">For Each...Next Statement</span></span>](../../../language-reference/statements/for-each-next-statement.md)
- [<span data-ttu-id="2eacc-144">For...Next 문</span><span class="sxs-lookup"><span data-stu-id="2eacc-144">For...Next Statement</span></span>](../../../language-reference/statements/for-next-statement.md)
- [<span data-ttu-id="2eacc-145">Option Infer 문</span><span class="sxs-lookup"><span data-stu-id="2eacc-145">Option Infer Statement</span></span>](../../../language-reference/statements/option-infer-statement.md)
- [<span data-ttu-id="2eacc-146">-optioninfer</span><span class="sxs-lookup"><span data-stu-id="2eacc-146">-optioninfer</span></span>](../../../reference/command-line-compiler/optioninfer.md)
- [<span data-ttu-id="2eacc-147">Visual Basic의 LINQ 소개</span><span class="sxs-lookup"><span data-stu-id="2eacc-147">Introduction to LINQ in Visual Basic</span></span>](../linq/introduction-to-linq.md)
