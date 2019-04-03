---
title: 문자열 이름을 사용하여 속성 또는 메서드 호출(Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- passing operators [Visual Basic]
- strings [Visual Basic], passing new operators as
- objects [Visual Basic], setting properties
- setting properties, object properties at run time
- method calls [Visual Basic], strings
- methods [Visual Basic], calling with string names
- calling methods [Visual Basic], string names
- properties [Visual Basic], setting at run time
- CallByName function
ms.assetid: 79a7b8b4-b8c7-4ad8-aca8-12a9a2b32f03
ms.openlocfilehash: e267c0c4d1d3e8f986348863d933c984f686b33b
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/02/2019
ms.locfileid: "58842644"
---
# <a name="calling-a-property-or-method-using-a-string-name-visual-basic"></a><span data-ttu-id="c1cf7-102">문자열 이름을 사용하여 속성 또는 메서드 호출(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c1cf7-102">Calling a Property or Method Using a String Name (Visual Basic)</span></span>
<span data-ttu-id="c1cf7-103">대부분의 경우에서 디자인 타임에 개체의 메서드와 속성을 검색 하 고 처리 하는 코드를 작성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c1cf7-103">In most cases, you can discover the properties and methods of an object at design time, and write code to handle them.</span></span> <span data-ttu-id="c1cf7-104">그러나 경우에 따라 모르고 개체의 속성 및 메서드에 대 한 사전에 또는 속성을 지정 하거나 런타임에 메서드를 실행 하려면 최종 사용자의 유연성 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c1cf7-104">However, in some cases you may not know about an object's properties and methods in advance, or you may just want the flexibility of enabling an end user to specify properties or execute methods at run time.</span></span>  
  
## <a name="callbyname-function"></a><span data-ttu-id="c1cf7-105">CallByName 함수</span><span class="sxs-lookup"><span data-stu-id="c1cf7-105">CallByName Function</span></span>  
 <span data-ttu-id="c1cf7-106">예를 들어 운영자는 COM 구성 요소에 전달 하 여 사용자가 입력 한 식을 계산 하는 클라이언트 응용 프로그램을 고려 합니다.</span><span class="sxs-lookup"><span data-stu-id="c1cf7-106">Consider, for example, a client application that evaluates expressions entered by the user by passing an operator to a COM component.</span></span> <span data-ttu-id="c1cf7-107">새 연산자를 요구 하는 구성 요소에 새 함수를 추가할 지속적으로 가정 합니다.</span><span class="sxs-lookup"><span data-stu-id="c1cf7-107">Suppose you are constantly adding new functions to the component that require new operators.</span></span> <span data-ttu-id="c1cf7-108">표준 개체 액세스 기법을 사용 하는 경우에 다시 컴파일해야 하 고 새 연산자를 사용 하려면 클라이언트 응용 프로그램을 재배포 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c1cf7-108">When you use standard object access techniques, you must recompile and redistribute the client application before it could use the new operators.</span></span> <span data-ttu-id="c1cf7-109">이 문제를 방지 하려면 사용할 수 있습니다는 `CallByName` 응용 프로그램을 변경 하지 않고도 새 연산자를 문자열로 전달 하는 함수입니다.</span><span class="sxs-lookup"><span data-stu-id="c1cf7-109">To avoid this, you can use the `CallByName` function to pass the new operators as strings, without changing the application.</span></span>  
  
 <span data-ttu-id="c1cf7-110">`CallByName` 함수는 문자열을 사용 하 여 런타임 시 속성이 나 메서드를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c1cf7-110">The `CallByName` function lets you use a string to specify a property or method at run time.</span></span> <span data-ttu-id="c1cf7-111">시그니처는 `CallByName` 함수는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="c1cf7-111">The signature for the `CallByName` function looks like this:</span></span>  
  
 <span data-ttu-id="c1cf7-112">*Result* = `CallByName`(*Object*, *ProcedureName*, *CallType*, *Arguments*())</span><span class="sxs-lookup"><span data-stu-id="c1cf7-112">*Result* = `CallByName`(*Object*, *ProcedureName*, *CallType*, *Arguments*())</span></span>  
  
 <span data-ttu-id="c1cf7-113">첫 번째 인수 *개체*, 취할 하려는 개체의 이름을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="c1cf7-113">The first argument, *Object*, takes the name of the object you want to act upon.</span></span> <span data-ttu-id="c1cf7-114">합니다 *ProcedureName* 인수가 호출할 메서드 또는 속성 프로시저의 이름을 포함 하는 문자열을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="c1cf7-114">The *ProcedureName* argument takes a string that contains the name of the method or property procedure to be invoked.</span></span> <span data-ttu-id="c1cf7-115">*CallType* 를 호출 하는 프로시저의 유형을 나타내는 상수를 사용 하는 인수: 메서드 (`Microsoft.VisualBasic.CallType.Method`), 속성 읽기 (`Microsoft.VisualBasic.CallType.Get`), 또는 속성 설정 (`Microsoft.VisualBasic.CallType.Set`).</span><span class="sxs-lookup"><span data-stu-id="c1cf7-115">The *CallType* argument takes a constant that represents the type of procedure to invoke: a method (`Microsoft.VisualBasic.CallType.Method`), a property read (`Microsoft.VisualBasic.CallType.Get`), or a property set (`Microsoft.VisualBasic.CallType.Set`).</span></span> <span data-ttu-id="c1cf7-116">합니다 *인수* 인수는 선택 사항인 형식의 배열을 사용 `Object` 프로시저에 인수를 포함 하는 합니다.</span><span class="sxs-lookup"><span data-stu-id="c1cf7-116">The *Arguments* argument, which is optional, takes an array of type `Object` that contains any arguments to the procedure.</span></span>  
  
 <span data-ttu-id="c1cf7-117">사용할 수 있습니다 `CallByName` 현재 솔루션에 클래스를 사용 하 여는 주로 COM 개체에 액세스할 수 또는 개체에서 [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] 어셈블리입니다.</span><span class="sxs-lookup"><span data-stu-id="c1cf7-117">You can use `CallByName` with classes in your current solution, but it is most often used to access COM objects or objects from [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] assemblies.</span></span>  
  
 <span data-ttu-id="c1cf7-118">클래스를 포함 하는 어셈블리에 대 한 참조를 추가 한다고 가정 `MathClass`, 라는 새 함수를 있는 `SquareRoot`다음 코드 에서처럼:</span><span class="sxs-lookup"><span data-stu-id="c1cf7-118">Suppose you add a reference to an assembly that contains a class named `MathClass`, which has a new function named `SquareRoot`, as shown in the following code:</span></span>  
  
 [!code-vb[VbVbalrOOP#53](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#53)]  
  
 <span data-ttu-id="c1cf7-119">응용 프로그램 컨트롤 호출 되는 메서드 및 해당 인수에 텍스트 상자 컨트롤을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="c1cf7-119">Your application could use text box controls to control which method will be called and its arguments.</span></span> <span data-ttu-id="c1cf7-120">예를 들어 경우 `TextBox1` 평가할 식이 포함 및 `TextBox2` 는 함수의 이름을 입력 하는 데에 사용할 수는 다음 코드를 호출 하는 `SquareRoot` 의 식에서 함수 `TextBox1`:</span><span class="sxs-lookup"><span data-stu-id="c1cf7-120">For example, if `TextBox1` contains the expression to be evaluated, and `TextBox2` is used to enter the name of the function, you can use the following code to invoke the `SquareRoot` function on the expression in `TextBox1`:</span></span>  
  
 [!code-vb[VbVbalrOOP#54](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#54)]  
  
 <span data-ttu-id="c1cf7-121">"64"를 입력 하는 경우 `TextBox1`, "SquareRoot"에서 `TextBox2`를 호출 합니다 `CallMath` 프로시저, 숫자의 제곱근 `TextBox1` 평가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c1cf7-121">If you enter "64" in `TextBox1`, "SquareRoot" in `TextBox2`, and then call the `CallMath` procedure, the square root of the number in `TextBox1` is evaluated.</span></span> <span data-ttu-id="c1cf7-122">예제에서 코드를 호출 하는 `SquareRoot` 함수 (그러면 필수 인수로 평가할 식이 포함 된 문자열) 및 "8"을 반환 `TextBox1` (64의 제곱근).</span><span class="sxs-lookup"><span data-stu-id="c1cf7-122">The code in the example invokes the `SquareRoot` function (which takes a string that contains the expression to be evaluated as a required argument) and returns "8" in `TextBox1` (the square root of 64).</span></span> <span data-ttu-id="c1cf7-123">물론에서 잘못 된 문자열을 입력 하면 `TextBox2`메서드는 추가 필수 인수 있으면 런타임 오류가 발생 하는 경우 문자열 메서드를 대신 속성의 이름을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="c1cf7-123">Of course, if the user enters an invalid string in `TextBox2`, if the string contains the name of a property instead of a method, or if the method had an additional required argument, a run-time error occurs.</span></span> <span data-ttu-id="c1cf7-124">사용 하는 경우 강력한 오류 처리 코드를 추가 해야 `CallByName` 이러한 또는 다른 오류를 예상할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c1cf7-124">You have to add robust error-handling code when you use `CallByName` to anticipate these or any other errors.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c1cf7-125">하는 동안 합니다 `CallByName` 함수는 일부 경우에 유용할 수 있습니다, 성능에 미치는 영향에 대 한 유용성을 평가 해야 합니다-사용 하 여 `CallByName` 프로시저를 호출 하는 런타임에 바인딩된 호출 보다 약간 더 느려집니다.</span><span class="sxs-lookup"><span data-stu-id="c1cf7-125">While the `CallByName` function may be useful in some cases, you must weigh its usefulness against the performance implications — using `CallByName` to invoke a procedure is slightly slower than a late-bound call.</span></span> <span data-ttu-id="c1cf7-126">호출 되는 반복 해 서 같은 루프 내에서 함수를 호출 하는 경우 `CallByName` 성능에 심각한 영향을 줄 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c1cf7-126">If you are invoking a function that is called repeatedly, such as inside a loop, `CallByName` can have a severe effect on performance.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c1cf7-127">참고자료</span><span class="sxs-lookup"><span data-stu-id="c1cf7-127">See also</span></span>

- <xref:Microsoft.VisualBasic.Interaction.CallByName%2A>
- [<span data-ttu-id="c1cf7-128">개체 형식 확인</span><span class="sxs-lookup"><span data-stu-id="c1cf7-128">Determining Object Type</span></span>](../../../../visual-basic/programming-guide/language-features/early-late-binding/determining-object-type.md)
