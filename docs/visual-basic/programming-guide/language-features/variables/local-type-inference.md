---
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
ms.openlocfilehash: f79ac70aecb5805a3a4a4fea8f7e7ccd3f8243fc
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/22/2019
ms.locfileid: "74351842"
---
# <a name="local-type-inference-visual-basic"></a><span data-ttu-id="b88b3-102">지역 형식 유추(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="b88b3-102">Local Type Inference (Visual Basic)</span></span>

<span data-ttu-id="b88b3-103">Visual Basic 컴파일러는 *형식 유추* 를 사용 하 여 `As` 절 없이 선언 된 지역 변수의 데이터 형식을 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="b88b3-103">The Visual Basic compiler uses *type inference* to determine the data types of local variables declared without an `As` clause.</span></span> <span data-ttu-id="b88b3-104">컴파일러는 초기화 식의 형식에서 변수 형식을 유추 합니다.</span><span class="sxs-lookup"><span data-stu-id="b88b3-104">The compiler infers the type of the variable from the type of the initialization expression.</span></span> <span data-ttu-id="b88b3-105">이렇게 하면 다음 예제와 같이 형식을 명시적으로 명시 하지 않고 변수를 선언할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b88b3-105">This enables you to declare variables without explicitly stating a type, as shown in the following example.</span></span> <span data-ttu-id="b88b3-106">선언 결과로 `num1`와 `num2`는 모두 정수로 강력 하 게 형식화 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b88b3-106">As a result of the declarations, both `num1` and `num2` are strongly typed as integers.</span></span>

[!code-vb[VbVbalrTypeInference#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrTypeInference/VB/Class1.vb#1)]

> [!NOTE]
> <span data-ttu-id="b88b3-107">이전 예제에서 `num2` `Integer`으로 형식화 하지 않으려는 경우 `Dim num3 As Object = 3` 또는 `Dim num4 As Double = 3`같은 선언을 사용 하 여 다른 형식을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b88b3-107">If you do not want `num2` in the previous example to be typed as an `Integer`, you can specify another type by using a declaration like `Dim num3 As Object = 3` or `Dim num4 As Double = 3`.</span></span>

> [!NOTE]
> <span data-ttu-id="b88b3-108">형식 유추는 비정적 지역 변수에만 사용할 수 있습니다. 클래스 필드, 속성 또는 함수의 형식을 결정 하는 데 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="b88b3-108">Type inference can be used only for non-static local variables; it cannot be used to determine the type of class fields, properties, or functions.</span></span>

<span data-ttu-id="b88b3-109">지역 형식 유추는 프로시저 수준에서 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b88b3-109">Local type inference applies at procedure level.</span></span> <span data-ttu-id="b88b3-110">모듈 수준에서 변수를 선언 하는 데 사용할 수 없습니다 (클래스, 구조체, 모듈 또는 인터페이스 내에서 프로시저나 블록 내에서 제외).</span><span class="sxs-lookup"><span data-stu-id="b88b3-110">It cannot be used to declare variables at module level (within a class, structure, module, or interface but not within a procedure or block).</span></span> <span data-ttu-id="b88b3-111">이전 예제에서 `num2` 프로시저에서 지역 변수가 아닌 클래스의 필드인 경우 선언으로 인해에 `Option Strict` 오류가 발생 하 고 `Option Strict` off를 사용 하 여 `num2`를 `Object` 분류 합니다.</span><span class="sxs-lookup"><span data-stu-id="b88b3-111">If `num2` in the previous example were a field of a class instead of a local variable in a procedure, the declaration would cause an error with `Option Strict` on, and would classify `num2` as an `Object` with `Option Strict` off.</span></span> <span data-ttu-id="b88b3-112">마찬가지로 지역 형식 유추는 `Static`로 선언 된 프로시저 수준 변수에는 적용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b88b3-112">Similarly, local type inference does not apply to procedure level variables declared as `Static`.</span></span>

## <a name="type-inference-vs-late-binding"></a><span data-ttu-id="b88b3-113">형식 유추 및 런타임에 바인딩</span><span class="sxs-lookup"><span data-stu-id="b88b3-113">Type Inference vs. Late Binding</span></span>

<span data-ttu-id="b88b3-114">형식 유추를 사용 하는 코드는 런타임에 바인딩을 사용 하는 코드와 비슷합니다.</span><span class="sxs-lookup"><span data-stu-id="b88b3-114">Code that uses type inference resembles code that relies on late binding.</span></span> <span data-ttu-id="b88b3-115">그러나 형식 유추는 변수를 `Object`로 유지 하는 대신 강력한 형식의 변수를 강력한 형식으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="b88b3-115">However, type inference strongly types the variable instead of leaving it as `Object`.</span></span> <span data-ttu-id="b88b3-116">컴파일러는 변수의 이니셜라이저를 사용 하 여 컴파일 시간에 변수의 형식을 확인 하 여 초기 바인딩된 코드를 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="b88b3-116">The compiler uses a variable's initializer to determine the variable's type at compile time to produce early-bound code.</span></span> <span data-ttu-id="b88b3-117">앞의 예제에서 `num1`와 같이 `num2`은 `Integer`으로 형식화 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b88b3-117">In the previous example, `num2`, like `num1`, is typed as an `Integer`.</span></span>

<span data-ttu-id="b88b3-118">초기 바인딩된 변수의 동작은 런타임에 바인딩된 변수의 동작과 다르며이는 런타임에만 형식을 알 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b88b3-118">The behavior of early-bound variables differs from that of late-bound variables, for which the type is known only at run time.</span></span> <span data-ttu-id="b88b3-119">초기 형식을 알면 컴파일러가 실행 전에 문제를 식별 하 고, 메모리를 정확 하 게 할당 하 고, 기타 최적화를 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b88b3-119">Knowing the type early enables the compiler to identify problems before execution, allocate memory precisely, and perform other optimizations.</span></span> <span data-ttu-id="b88b3-120">또한 초기 바인딩을 사용 하면 Visual Basic IDE (통합 개발 환경)에서 개체의 멤버에 대 한 IntelliSense 도움말을 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b88b3-120">Early binding also enables the Visual Basic integrated development environment (IDE) to provide IntelliSense Help about the members of an object.</span></span> <span data-ttu-id="b88b3-121">성능에 대 한 초기 바인딩도 선호 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b88b3-121">Early binding is also preferred for performance.</span></span> <span data-ttu-id="b88b3-122">이는 런타임에 바인딩된 변수에 저장 된 모든 데이터를 `Object`형식으로 래핑해야 하 고 런타임에 형식의 멤버에 액세스 하는 것 이기 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="b88b3-122">This is because all data stored in a late-bound variable must be wrapped as type `Object`, and accessing members of the type at run time makes the program slower.</span></span>

## <a name="examples"></a><span data-ttu-id="b88b3-123">예</span><span class="sxs-lookup"><span data-stu-id="b88b3-123">Examples</span></span>

<span data-ttu-id="b88b3-124">형식 유추는 지역 변수가 `As` 절 없이 선언 되 고 초기화 될 때 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="b88b3-124">Type inference occurs when a local variable is declared without an `As` clause and initialized.</span></span> <span data-ttu-id="b88b3-125">컴파일러는 할당 된 초기 값의 형식을 변수 형식으로 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="b88b3-125">The compiler uses the type of the assigned initial value as the type of the variable.</span></span> <span data-ttu-id="b88b3-126">예를 들어 다음 코드 줄은 모두 `String`형식의 변수를 선언 합니다.</span><span class="sxs-lookup"><span data-stu-id="b88b3-126">For example, each of the following lines of code declares a variable of type `String`.</span></span>

[!code-vb[VbVbalrTypeInference#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrTypeInference/VB/Class1.vb#2)]

<span data-ttu-id="b88b3-127">다음 코드에서는 두 가지 동일한 방법으로 정수 배열을 만드는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="b88b3-127">The following code demonstrates two equivalent ways to create an array of integers.</span></span>

[!code-vb[VbVbalrTypeInference#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrTypeInference/VB/Class1.vb#3)]

<span data-ttu-id="b88b3-128">형식 유추를 사용 하 여 루프 제어 변수의 형식을 결정 하는 것이 편리 합니다.</span><span class="sxs-lookup"><span data-stu-id="b88b3-128">It is convenient to use type inference to determine the type of a loop control variable.</span></span> <span data-ttu-id="b88b3-129">다음 코드에서 컴파일러는 이전 예제의 `someNumbers2` 정수의 배열 이기 때문에 `number` `Integer`를 유추 합니다.</span><span class="sxs-lookup"><span data-stu-id="b88b3-129">In the following code, the compiler infers that `number` is an `Integer` because `someNumbers2` from the previous example is an array of integers.</span></span>

[!code-vb[VbVbalrTypeInference#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrTypeInference/VB/Class1.vb#4)]

<span data-ttu-id="b88b3-130">다음 예제가 보여 주는 것 처럼 `Using` 문에서 지역 형식 유추를 사용 하 여 리소스 이름의 형식을 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b88b3-130">Local type inference can be used in `Using` statements to establish the type of the resource name, as the following example demonstrates.</span></span>

[!code-vb[VbVbalrTypeInference#7](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrTypeInference/VB/Class1.vb#7)]

<span data-ttu-id="b88b3-131">다음 예제와 같이 함수의 반환 값에서 변수의 형식을 유추할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b88b3-131">The type of a variable can also be inferred from the return values of functions, as the following example demonstrates.</span></span> <span data-ttu-id="b88b3-132">`Process.GetProcesses` 프로세스의 배열을 반환 하기 때문에 `pList1`와 `pList2`는 모두 프로세스의 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="b88b3-132">Both `pList1` and `pList2` are arrays of processes because `Process.GetProcesses` returns an array of processes.</span></span>

[!code-vb[VbVbalrTypeInference#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrTypeInference/VB/Class1.vb#5)]

## <a name="option-infer"></a><span data-ttu-id="b88b3-133">옵션 유추</span><span class="sxs-lookup"><span data-stu-id="b88b3-133">Option Infer</span></span>

<span data-ttu-id="b88b3-134">`Option Infer`를 사용 하 여 특정 파일에서 로컬 형식 유추가 허용 되는지 여부를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b88b3-134">`Option Infer` enables you specify whether local type inference is allowed in a particular file.</span></span> <span data-ttu-id="b88b3-135">옵션을 사용 하도록 설정 하거나 차단 하려면 파일의 시작 부분에 다음 문 중 하나를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="b88b3-135">To enable or to block the option, type one of the following statements at the start of the file.</span></span>

`Option Infer On`

`Option Infer Off`

<span data-ttu-id="b88b3-136">코드에 `Option Infer` 값을 지정 하지 않으면 컴파일러 기본값은 `Option Infer On`됩니다.</span><span class="sxs-lookup"><span data-stu-id="b88b3-136">If you do not specify a value for `Option Infer` in your code, the compiler default is `Option Infer On`.</span></span>

<span data-ttu-id="b88b3-137">파일에서 `Option Infer`에 대해 설정된 값이 IDE 또는 명령줄에 설정된 값과 충돌하는 경우에는 파일의 값이 우선적으로 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="b88b3-137">If the value set for `Option Infer` in a file conflicts with the value set in the IDE or on the command line, the value in the file has precedence.</span></span>

<span data-ttu-id="b88b3-138">자세한 내용은 [Option 유추 문](../../../../visual-basic/language-reference/statements/option-infer-statement.md) 및 [컴파일 페이지, 프로젝트 디자이너 (Visual Basic)](/visualstudio/ide/reference/compile-page-project-designer-visual-basic)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="b88b3-138">For more information, see [Option Infer Statement](../../../../visual-basic/language-reference/statements/option-infer-statement.md) and [Compile Page, Project Designer (Visual Basic)](/visualstudio/ide/reference/compile-page-project-designer-visual-basic).</span></span>

## <a name="see-also"></a><span data-ttu-id="b88b3-139">참고 항목</span><span class="sxs-lookup"><span data-stu-id="b88b3-139">See also</span></span>

- [<span data-ttu-id="b88b3-140">익명 형식</span><span class="sxs-lookup"><span data-stu-id="b88b3-140">Anonymous Types</span></span>](../../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md)
- [<span data-ttu-id="b88b3-141">초기 바인딩 및 런타임에 바인딩</span><span class="sxs-lookup"><span data-stu-id="b88b3-141">Early and Late Binding</span></span>](../../../../visual-basic/programming-guide/language-features/early-late-binding/index.md)
- [<span data-ttu-id="b88b3-142">For Each...Next 문</span><span class="sxs-lookup"><span data-stu-id="b88b3-142">For Each...Next Statement</span></span>](../../../../visual-basic/language-reference/statements/for-each-next-statement.md)
- [<span data-ttu-id="b88b3-143">For...Next 문</span><span class="sxs-lookup"><span data-stu-id="b88b3-143">For...Next Statement</span></span>](../../../../visual-basic/language-reference/statements/for-next-statement.md)
- [<span data-ttu-id="b88b3-144">Option Infer 문</span><span class="sxs-lookup"><span data-stu-id="b88b3-144">Option Infer Statement</span></span>](../../../../visual-basic/language-reference/statements/option-infer-statement.md)
- [<span data-ttu-id="b88b3-145">-optioninfer</span><span class="sxs-lookup"><span data-stu-id="b88b3-145">-optioninfer</span></span>](../../../../visual-basic/reference/command-line-compiler/optioninfer.md)
- [<span data-ttu-id="b88b3-146">Visual Basic의 LINQ 소개</span><span class="sxs-lookup"><span data-stu-id="b88b3-146">Introduction to LINQ in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)
