---
title: 문자열 이름을 사용하여 속성 또는 메서드 호출
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
ms.openlocfilehash: 29072479db36f9f8a81ffd7f3f5b10208ebaa984
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/04/2020
ms.locfileid: "84410659"
---
# <a name="calling-a-property-or-method-using-a-string-name-visual-basic"></a><span data-ttu-id="04244-102">문자열 이름을 사용하여 속성 또는 메서드 호출(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="04244-102">Calling a Property or Method Using a String Name (Visual Basic)</span></span>
<span data-ttu-id="04244-103">대부분의 경우 디자인 타임에 개체의 속성 및 메서드를 검색 하 고이를 처리 하는 코드를 작성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="04244-103">In most cases, you can discover the properties and methods of an object at design time, and write code to handle them.</span></span> <span data-ttu-id="04244-104">그러나 경우에 따라 개체의 속성 및 메서드를 미리 알지 못할 수도 있고, 최종 사용자가 런타임에 속성을 지정 하거나 메서드를 실행할 수 있도록 하는 유연성을 원합니다.</span><span class="sxs-lookup"><span data-stu-id="04244-104">However, in some cases you may not know about an object's properties and methods in advance, or you may just want the flexibility of enabling an end user to specify properties or execute methods at run time.</span></span>  
  
## <a name="callbyname-function"></a><span data-ttu-id="04244-105">CallByName 함수</span><span class="sxs-lookup"><span data-stu-id="04244-105">CallByName Function</span></span>  
 <span data-ttu-id="04244-106">예를 들어, COM 구성 요소에 연산자를 전달 하 여 사용자가 입력 한 식을 평가 하는 클라이언트 응용 프로그램을 고려해 야 합니다.</span><span class="sxs-lookup"><span data-stu-id="04244-106">Consider, for example, a client application that evaluates expressions entered by the user by passing an operator to a COM component.</span></span> <span data-ttu-id="04244-107">새 연산자가 필요한 구성 요소에 새 함수를 지속적으로 추가 한다고 가정 합니다.</span><span class="sxs-lookup"><span data-stu-id="04244-107">Suppose you are constantly adding new functions to the component that require new operators.</span></span> <span data-ttu-id="04244-108">표준 개체 액세스 기술을 사용 하는 경우 새 연산자를 사용 하려면 먼저 클라이언트 응용 프로그램을 다시 컴파일하고 다시 배포 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="04244-108">When you use standard object access techniques, you must recompile and redistribute the client application before it could use the new operators.</span></span> <span data-ttu-id="04244-109">이를 방지 하기 위해 함수를 사용 하 여 `CallByName` 응용 프로그램을 변경 하지 않고 새 연산자를 문자열로 전달할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="04244-109">To avoid this, you can use the `CallByName` function to pass the new operators as strings, without changing the application.</span></span>  
  
 <span data-ttu-id="04244-110">`CallByName`함수를 사용 하면 문자열을 사용 하 여 런타임에 속성이 나 메서드를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="04244-110">The `CallByName` function lets you use a string to specify a property or method at run time.</span></span> <span data-ttu-id="04244-111">함수의 시그니처는 `CallByName` 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="04244-111">The signature for the `CallByName` function looks like this:</span></span>  
  
 <span data-ttu-id="04244-112">*Result*  =  결과 `CallByName` (*Object*, *e*, *calltype*, *Arguments*())</span><span class="sxs-lookup"><span data-stu-id="04244-112">*Result* = `CallByName`(*Object*, *ProcedureName*, *CallType*, *Arguments*())</span></span>  
  
 <span data-ttu-id="04244-113">첫 번째 인수인 *object*는 동작 하려는 개체의 이름을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="04244-113">The first argument, *Object*, takes the name of the object you want to act upon.</span></span> <span data-ttu-id="04244-114">*E* 인수는 호출할 메서드 또는 속성 프로시저의 이름을 포함 하는 문자열을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="04244-114">The *ProcedureName* argument takes a string that contains the name of the method or property procedure to be invoked.</span></span> <span data-ttu-id="04244-115">*Calltype* 인수는 메서드 ( `Microsoft.VisualBasic.CallType.Method` ), 속성 읽기 ( `Microsoft.VisualBasic.CallType.Get` ) 또는 속성 집합 ()을 호출 하는 프로시저의 형식을 나타내는 상수를 사용 합니다 `Microsoft.VisualBasic.CallType.Set` .</span><span class="sxs-lookup"><span data-stu-id="04244-115">The *CallType* argument takes a constant that represents the type of procedure to invoke: a method (`Microsoft.VisualBasic.CallType.Method`), a property read (`Microsoft.VisualBasic.CallType.Get`), or a property set (`Microsoft.VisualBasic.CallType.Set`).</span></span> <span data-ttu-id="04244-116">Optional 인 *arguments* 인수는 `Object` 프로시저에 대 한 인수를 포함 하는 형식의 배열을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="04244-116">The *Arguments* argument, which is optional, takes an array of type `Object` that contains any arguments to the procedure.</span></span>  
  
 <span data-ttu-id="04244-117">`CallByName`현재 솔루션의 클래스와 함께을 사용할 수 있지만 대부분의 경우 .NET Framework 어셈블리에서 COM 개체 또는 개체에 액세스 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="04244-117">You can use `CallByName` with classes in your current solution, but it is most often used to access COM objects or objects from .NET Framework assemblies.</span></span>  
  
 <span data-ttu-id="04244-118">`MathClass`다음 코드와 같이 라는 새 함수가 있는 라는 클래스가 포함 된 어셈블리에 대 한 참조를 추가 한다고 가정 합니다 `SquareRoot` .</span><span class="sxs-lookup"><span data-stu-id="04244-118">Suppose you add a reference to an assembly that contains a class named `MathClass`, which has a new function named `SquareRoot`, as shown in the following code:</span></span>  
  
 [!code-vb[VbVbalrOOP#53](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#53)]  
  
 <span data-ttu-id="04244-119">응용 프로그램은 텍스트 상자 컨트롤을 사용 하 여 호출할 메서드와 해당 인수를 제어할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="04244-119">Your application could use text box controls to control which method will be called and its arguments.</span></span> <span data-ttu-id="04244-120">예를 들어에서 `TextBox1` 평가할 식이 포함 되어 있고 `TextBox2` 이 함수 이름을 입력 하는 데 사용 되는 경우 다음 코드를 사용 하 여 `SquareRoot` 의 식에서 함수를 호출할 수 있습니다 `TextBox1` .</span><span class="sxs-lookup"><span data-stu-id="04244-120">For example, if `TextBox1` contains the expression to be evaluated, and `TextBox2` is used to enter the name of the function, you can use the following code to invoke the `SquareRoot` function on the expression in `TextBox1`:</span></span>  
  
 [!code-vb[VbVbalrOOP#54](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#54)]  
  
 <span data-ttu-id="04244-121">에서 "64"를 입력 하 `TextBox1` 고에서 "SquareRoot"를 입력 한 `TextBox2` 다음 프로시저를 호출 하면 `CallMath` 에 있는 숫자의 제곱근 `TextBox1` 이 계산 됩니다.</span><span class="sxs-lookup"><span data-stu-id="04244-121">If you enter "64" in `TextBox1`, "SquareRoot" in `TextBox2`, and then call the `CallMath` procedure, the square root of the number in `TextBox1` is evaluated.</span></span> <span data-ttu-id="04244-122">예제의 코드는 함수를 호출 합니다 `SquareRoot` .이 함수는 필요한 인수로 계산 되는 식을 포함 하는 문자열을 사용 하 고는 `TextBox1` (64의 제곱근)에서 "8"을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="04244-122">The code in the example invokes the `SquareRoot` function (which takes a string that contains the expression to be evaluated as a required argument) and returns "8" in `TextBox1` (the square root of 64).</span></span> <span data-ttu-id="04244-123">물론, 사용자가에 잘못 된 문자열을 입력 하는 경우 `TextBox2` , 문자열에 메서드 대신 속성 이름이 포함 된 경우 또는 메서드에 추가 필수 인수가 있는 경우 런타임 오류가 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="04244-123">Of course, if the user enters an invalid string in `TextBox2`, if the string contains the name of a property instead of a method, or if the method had an additional required argument, a run-time error occurs.</span></span> <span data-ttu-id="04244-124">를 사용 하 여 `CallByName` 이러한 오류 또는 다른 오류를 예상할 때 강력한 오류 처리 코드를 추가 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="04244-124">You have to add robust error-handling code when you use `CallByName` to anticipate these or any other errors.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="04244-125">함수는 `CallByName` 경우에 따라 유용 하 게 사용 되지만,를 사용 하면 `CallByName` 프로시저를 호출 하는 데를 사용 하는 것이 런타임에 바인딩된 호출 보다 약간 느리기 때문에 성능이 저하 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="04244-125">While the `CallByName` function may be useful in some cases, you must weigh its usefulness against the performance implications — using `CallByName` to invoke a procedure is slightly slower than a late-bound call.</span></span> <span data-ttu-id="04244-126">루프 내부와 같이 반복적으로 호출 되는 함수를 호출 하는 경우 `CallByName` 성능에 심각한 영향을 미칠 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="04244-126">If you are invoking a function that is called repeatedly, such as inside a loop, `CallByName` can have a severe effect on performance.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="04244-127">참고 항목</span><span class="sxs-lookup"><span data-stu-id="04244-127">See also</span></span>

- <xref:Microsoft.VisualBasic.Interaction.CallByName%2A>
- [<span data-ttu-id="04244-128">개체 형식 확인</span><span class="sxs-lookup"><span data-stu-id="04244-128">Determining Object Type</span></span>](determining-object-type.md)
