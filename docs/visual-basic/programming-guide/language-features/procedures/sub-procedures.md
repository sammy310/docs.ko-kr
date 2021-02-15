---
description: '자세한 정보: 하위 프로시저 (Visual Basic)'
title: Sub 프로시저
ms.date: 07/20/2015
helpviewer_keywords:
- Sub procedures [Visual Basic], about Sub procedures
- statement blocks
- Sub procedures [Visual Basic], calling
- procedures [Visual Basic], calling
- Sub procedures [Visual Basic], syntax
- Sub procedures
- procedures [Visual Basic], Sub
- syntax [Visual Basic], Sub procedures
ms.assetid: 6a0a4958-ed0a-4d3d-8d31-0772c82bda58
ms.openlocfilehash: fe9d26fb2d18fbd29820af7aca96b826d7b45d0b
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/14/2021
ms.locfileid: "100466512"
---
# <a name="sub-procedures-visual-basic"></a><span data-ttu-id="22133-103">하위 프로시저 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="22133-103">Sub procedures (Visual Basic)</span></span>

<span data-ttu-id="22133-104">`Sub`프로시저는 및 문으로 묶인 일련의 Visual Basic 문입니다 `Sub` `End Sub` .</span><span class="sxs-lookup"><span data-stu-id="22133-104">A `Sub` procedure is a series of Visual Basic statements enclosed by the `Sub` and `End Sub` statements.</span></span> <span data-ttu-id="22133-105">`Sub`프로시저는 작업을 수행한 다음 호출 코드에 대 한 제어를 반환 하지만 호출 코드에는 값을 반환 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="22133-105">The `Sub` procedure performs a task and then returns control to the calling code, but it does not return a value to the calling code.</span></span>

<span data-ttu-id="22133-106">프로시저가 호출 될 때마다 문 뒤의 첫 번째 실행 가능 문부터 시작 `Sub` 하 여 첫 번째 `End Sub` , `Exit Sub` 또는 문으로 끝나는 문이 실행 됩니다 `Return` .</span><span class="sxs-lookup"><span data-stu-id="22133-106">Each time the procedure is called, its statements are executed, starting with the first executable statement after the `Sub` statement and ending with the first `End Sub`, `Exit Sub`, or `Return` statement encountered.</span></span>

<span data-ttu-id="22133-107">`Sub`모듈, 클래스 및 구조체에서 프로시저를 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="22133-107">You can define a `Sub` procedure in modules, classes, and structures.</span></span> <span data-ttu-id="22133-108">기본적으로이 클래스는 `Public` 정의 된 모듈, 클래스 또는 구조체에 대 한 액세스 권한이 있는 응용 프로그램의 어디에서 나 호출할 수 있음을 의미 합니다.</span><span class="sxs-lookup"><span data-stu-id="22133-108">By default, it is `Public`, which means you can call it from anywhere in your application that has access to the module, class, or structure in which you defined it.</span></span> <span data-ttu-id="22133-109">용어 *메서드* 는 `Sub` `Function` 정의 모듈, 클래스 또는 구조체 외부에서 액세스 하는 또는 프로시저를 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="22133-109">The term *method* describes a `Sub` or `Function` procedure that is accessed from outside its defining module, class, or structure.</span></span> <span data-ttu-id="22133-110">자세한 내용은 [프로시저](./index.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="22133-110">For more information, see [Procedures](./index.md).</span></span>

<span data-ttu-id="22133-111">`Sub`프로시저는 호출 코드를 통해 전달 되는 상수, 변수 또는 식과 같은 인수를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="22133-111">A `Sub` procedure can take arguments, such as constants, variables, or expressions, which are passed to it by the calling code.</span></span>

## <a name="declaration-syntax"></a><span data-ttu-id="22133-112">선언 구문</span><span class="sxs-lookup"><span data-stu-id="22133-112">Declaration syntax</span></span>

<span data-ttu-id="22133-113">프로시저를 선언 하는 구문은 다음과 같습니다 `Sub` .</span><span class="sxs-lookup"><span data-stu-id="22133-113">The syntax for declaring a `Sub` procedure is as follows:</span></span>

```vb
[modifiers] Sub SubName[(parameterList)]
    ' Statements of the Sub procedure.
End Sub
```

<span data-ttu-id="22133-114">는 `modifiers` 오버 로드, 재정의, 공유 및 숨기기에 대 한 액세스 수준 및 정보를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="22133-114">The `modifiers` can specify access level and information about overloading, overriding, sharing, and shadowing.</span></span> <span data-ttu-id="22133-115">자세한 내용은 [Sub 문](../../../language-reference/statements/sub-statement.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="22133-115">For more information, see [Sub Statement](../../../language-reference/statements/sub-statement.md).</span></span>

## <a name="parameter-declaration"></a><span data-ttu-id="22133-116">매개 변수 선언</span><span class="sxs-lookup"><span data-stu-id="22133-116">Parameter declaration</span></span>

<span data-ttu-id="22133-117">매개 변수 이름 및 데이터 형식을 지정 하 여 변수를 선언 하는 방법과 유사 하 게 각 프로시저 매개 변수를 선언 합니다.</span><span class="sxs-lookup"><span data-stu-id="22133-117">You declare each procedure parameter similarly to how you declare a variable, specifying the parameter name and data type.</span></span> <span data-ttu-id="22133-118">전달 메커니즘을 지정 하 고 매개 변수가 선택적 요소 인지 아니면 매개 변수 배열 인지를 지정할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="22133-118">You can also specify the passing mechanism, and whether the parameter is optional or a parameter array.</span></span>

<span data-ttu-id="22133-119">매개 변수 목록의 각 매개 변수에 대 한 구문은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="22133-119">The syntax for each parameter in the parameter list is as follows:</span></span>

```vb
[Optional] [ByVal | ByRef] [ParamArray] parameterName As DataType
```

<span data-ttu-id="22133-120">매개 변수가 선택 사항인 경우에는 해당 선언의 일부로도 기본값을 제공 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="22133-120">If the parameter is optional, you must also supply a default value as part of its declaration.</span></span> <span data-ttu-id="22133-121">기본값을 지정 하는 구문은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="22133-121">The syntax for specifying a default value is as follows:</span></span>

```vb
Optional [ByVal | ByRef]  parameterName As DataType = defaultValue
```

### <a name="parameters-as-local-variables"></a><span data-ttu-id="22133-122">로컬 변수로 서의 매개 변수</span><span class="sxs-lookup"><span data-stu-id="22133-122">Parameters as local variables</span></span>

<span data-ttu-id="22133-123">제어가 프로시저에 전달 되 면 각 매개 변수는 지역 변수로 처리 됩니다.</span><span class="sxs-lookup"><span data-stu-id="22133-123">When control passes to the procedure, each parameter is treated as a local variable.</span></span> <span data-ttu-id="22133-124">즉, 수명이 프로시저와 동일 하 고 해당 범위가 전체 프로시저 임을 의미 합니다.</span><span class="sxs-lookup"><span data-stu-id="22133-124">This means that its lifetime is the same as that of the procedure, and its scope is the whole procedure.</span></span>

## <a name="calling-syntax"></a><span data-ttu-id="22133-125">호출 구문</span><span class="sxs-lookup"><span data-stu-id="22133-125">Calling syntax</span></span>

<span data-ttu-id="22133-126">`Sub`독립 실행형 호출 문을 사용 하 여 명시적으로 프로시저를 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="22133-126">You invoke a `Sub` procedure explicitly with a stand-alone calling statement.</span></span> <span data-ttu-id="22133-127">식에서 해당 이름을 사용 하 여 호출할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="22133-127">You cannot call it by using its name in an expression.</span></span> <span data-ttu-id="22133-128">선택 사항이 아닌 모든 인수에 대 한 값을 제공 해야 하며 인수 목록을 괄호로 묶어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="22133-128">You must provide values for all arguments that are not optional, and you must enclose the argument list in parentheses.</span></span> <span data-ttu-id="22133-129">인수를 제공 하지 않으면 필요에 따라 괄호를 생략할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="22133-129">If no arguments are supplied, you can optionally omit the parentheses.</span></span> <span data-ttu-id="22133-130">키워드를 사용 하는 것 `Call` 은 선택 사항 이지만 권장 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="22133-130">The use of the `Call` keyword is optional but not recommended.</span></span>

<span data-ttu-id="22133-131">프로시저에 대 한 호출 구문은 `Sub` 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="22133-131">The syntax for a call to a `Sub` procedure is as follows:</span></span>

```vb
[Call] SubName[(argumentlist)]
```

<span data-ttu-id="22133-132">`Sub`메서드를 정의 하는 클래스 외부에서 메서드를 호출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="22133-132">You can call a `Sub` method from outside the class that defines it.</span></span> <span data-ttu-id="22133-133">먼저 키워드를 사용 하 여 `New` 클래스의 인스턴스를 만들거나 클래스의 인스턴스를 반환 하는 메서드를 호출 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="22133-133">First, you have to use the `New` keyword to create an instance of the class, or call a method that returns an instance of the class.</span></span> <span data-ttu-id="22133-134">자세한 내용은 [New Operator](../../../language-reference/operators/new-operator.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="22133-134">For more information, see [New Operator](../../../language-reference/operators/new-operator.md).</span></span> <span data-ttu-id="22133-135">그런 다음, 다음 구문을 사용 하 여 `Sub` 인스턴스 개체에 대해 메서드를 호출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="22133-135">Then, you can use the following syntax to call the `Sub` method on the instance object:</span></span>

```vb
object.MethodName[(argumentList)]
```

### <a name="illustration-of-declaration-and-call"></a><span data-ttu-id="22133-136">선언 및 호출에 대 한 그림</span><span class="sxs-lookup"><span data-stu-id="22133-136">Illustration of declaration and call</span></span>

<span data-ttu-id="22133-137">다음 `Sub` 절차에서는 응용 프로그램에서 수행 하려는 작업을 컴퓨터 운영자에 게 지시 하 고 타임 스탬프를 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="22133-137">The following `Sub` procedure tells the computer operator which task the application is about to perform, and also displays a time stamp.</span></span> <span data-ttu-id="22133-138">모든 작업을 시작할 때이 코드를 복제 하는 대신 응용 프로그램은 `tellOperator` 다양 한 위치에서를 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="22133-138">Instead of duplicating this code at the start of every task, the application just calls `tellOperator` from various locations.</span></span> <span data-ttu-id="22133-139">각 호출은 `task` 시작할 작업을 식별 하는 문자열을 인수에 전달 합니다.</span><span class="sxs-lookup"><span data-stu-id="22133-139">Each call passes a string in the `task` argument that identifies the task being started.</span></span>

[!code-vb[VbVbcnProcedures#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#2)]

<span data-ttu-id="22133-140">다음 예제에서는에 대 한 일반적인 호출을 보여 줍니다 `tellOperator` .</span><span class="sxs-lookup"><span data-stu-id="22133-140">The following example shows a typical call to `tellOperator`.</span></span>

[!code-vb[VbVbcnProcedures#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#3)]

## <a name="see-also"></a><span data-ttu-id="22133-141">추가 정보</span><span class="sxs-lookup"><span data-stu-id="22133-141">See also</span></span>

- [<span data-ttu-id="22133-142">절차</span><span class="sxs-lookup"><span data-stu-id="22133-142">Procedures</span></span>](./index.md)
- [<span data-ttu-id="22133-143">함수 프로시저</span><span class="sxs-lookup"><span data-stu-id="22133-143">Function Procedures</span></span>](./function-procedures.md)
- [<span data-ttu-id="22133-144">속성 프로시저</span><span class="sxs-lookup"><span data-stu-id="22133-144">Property Procedures</span></span>](./property-procedures.md)
- [<span data-ttu-id="22133-145">연산자 프로시저</span><span class="sxs-lookup"><span data-stu-id="22133-145">Operator Procedures</span></span>](./operator-procedures.md)
- [<span data-ttu-id="22133-146">프로시저 매개 변수 및 인수</span><span class="sxs-lookup"><span data-stu-id="22133-146">Procedure Parameters and Arguments</span></span>](./procedure-parameters-and-arguments.md)
- [<span data-ttu-id="22133-147">Sub 문</span><span class="sxs-lookup"><span data-stu-id="22133-147">Sub Statement</span></span>](../../../language-reference/statements/sub-statement.md)
- [<span data-ttu-id="22133-148">방법: 값을 반환하지 않는 프로시저 호출</span><span class="sxs-lookup"><span data-stu-id="22133-148">How to: Call a Procedure that Does Not Return a Value</span></span>](./how-to-call-a-procedure-that-does-not-return-a-value.md)
- [<span data-ttu-id="22133-149">방법: Visual Basic에서 이벤트 처리기 호출</span><span class="sxs-lookup"><span data-stu-id="22133-149">How to: Call an Event Handler in Visual Basic</span></span>](./how-to-call-an-event-handler.md)
