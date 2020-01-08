---
title: '방법: 인수가 값으로 전달되도록 설정'
ms.date: 07/20/2015
helpviewer_keywords:
- procedures [Visual Basic], arguments
- procedures [Visual Basic], parameters
- procedure arguments
- Visual Basic code, procedures
- arguments [Visual Basic], ByVal
- arguments [Visual Basic], passing by value
- procedure parameters
- procedures [Visual Basic], calling
- arguments [Visual Basic], in parentheses
- procedure arguments [Visual Basic], in parentheses
- arguments [Visual Basic], changing value
ms.assetid: 77b4f2d2-1055-4c2f-a521-874d1db86946
ms.openlocfilehash: 047738a2cbadc6b7d72f41aade22bbeff16d1bac
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/25/2019
ms.locfileid: "75347604"
---
# <a name="how-to-force-an-argument-to-be-passed-by-value-visual-basic"></a><span data-ttu-id="f0c60-102">방법: 인수가 값으로 전달되도록 설정(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="f0c60-102">How to: Force an Argument to Be Passed by Value (Visual Basic)</span></span>
<span data-ttu-id="f0c60-103">프로시저 선언은 전달 메커니즘을 결정 합니다.</span><span class="sxs-lookup"><span data-stu-id="f0c60-103">The procedure declaration determines the passing mechanism.</span></span> <span data-ttu-id="f0c60-104">매개 변수가 [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md)로 선언 된 경우 Visual Basic는 해당 인수를 참조로 전달 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f0c60-104">If a parameter is declared [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md), Visual Basic expects to pass the corresponding argument by reference.</span></span> <span data-ttu-id="f0c60-105">이렇게 하면 호출 코드에서 인수를 기반으로 하는 프로그래밍 요소의 값을 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f0c60-105">This allows the procedure to change the value of the programming element underlying the argument in the calling code.</span></span> <span data-ttu-id="f0c60-106">이러한 변경 으로부터 기본 요소를 보호 하려는 경우 인수 이름을 괄호로 묶으면 프로시저 호출에서 `ByRef` 전달 메커니즘을 재정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f0c60-106">If you wish to protect the underlying element against such change, you can override the `ByRef` passing mechanism in the procedure call by enclosing the argument name in parentheses.</span></span> <span data-ttu-id="f0c60-107">이러한 괄호는 호출에서 인수 목록을 묶는 괄호에 추가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f0c60-107">These parentheses are in addition to the parentheses enclosing the argument list in the call.</span></span>  
  
 <span data-ttu-id="f0c60-108">호출 코드는 [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md) 메커니즘을 재정의할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="f0c60-108">The calling code cannot override a [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md) mechanism.</span></span>  
  
### <a name="to-force-an-argument-to-be-passed-by-value"></a><span data-ttu-id="f0c60-109">인수가 값으로 전달 되도록 하려면</span><span class="sxs-lookup"><span data-stu-id="f0c60-109">To force an argument to be passed by value</span></span>  
  
- <span data-ttu-id="f0c60-110">해당 매개 변수가 프로시저에서 `ByVal` 선언 된 경우 추가 단계를 수행할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="f0c60-110">If the corresponding parameter is declared `ByVal` in the procedure, you do not need to take any additional steps.</span></span> <span data-ttu-id="f0c60-111">Visual Basic는 이미 인수를 값으로 전달할 것으로 예상 합니다.</span><span class="sxs-lookup"><span data-stu-id="f0c60-111">Visual Basic already expects to pass the argument by value.</span></span>  
  
- <span data-ttu-id="f0c60-112">해당 매개 변수가 프로시저에서 `ByRef` 선언 되 면 프로시저 호출에서 인수를 괄호로 묶습니다.</span><span class="sxs-lookup"><span data-stu-id="f0c60-112">If the corresponding parameter is declared `ByRef` in the procedure, enclose the argument in parentheses in the procedure call.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f0c60-113">예</span><span class="sxs-lookup"><span data-stu-id="f0c60-113">Example</span></span>  
 <span data-ttu-id="f0c60-114">다음 예제에서는 `ByRef` 매개 변수 선언을 재정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="f0c60-114">The following example overrides a `ByRef` parameter declaration.</span></span> <span data-ttu-id="f0c60-115">강제로 `ByVal`하는 호출에서 두 가지 수준의 괄호를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="f0c60-115">In the call that forces `ByVal`, note the two levels of parentheses.</span></span>  
  
 [!code-vb[VbVbcnProcedures#39](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#39)]  
  
 [!code-vb[VbVbcnProcedures#40](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#40)]  
  
 <span data-ttu-id="f0c60-116">`str` 인수 목록 내에서 추가 괄호 안에 포함 되 면 `setNewString` 프로시저는 호출 코드에서 해당 값을 변경할 수 없으며, "ByVal 전달 된 경우 바꿀 수 없음"이 표시 `MsgBox`.</span><span class="sxs-lookup"><span data-stu-id="f0c60-116">When `str` is enclosed in extra parentheses within the argument list, the `setNewString` procedure cannot change its value in the calling code, and `MsgBox` displays "Cannot be replaced if passed ByVal".</span></span> <span data-ttu-id="f0c60-117">`str` 추가 괄호 안에 포함 되지 않은 경우 프로시저에서이를 변경 하 고 `MsgBox` "This is This is new value for inString argument"를 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="f0c60-117">When `str` is not enclosed in extra parentheses, the procedure can change it, and `MsgBox` displays "This is a new value for the inString argument."</span></span>  
  
## <a name="compile-the-code"></a><span data-ttu-id="f0c60-118">코드 컴파일</span><span class="sxs-lookup"><span data-stu-id="f0c60-118">Compile the code</span></span>  
 <span data-ttu-id="f0c60-119">변수를 참조로 전달 하는 경우에는 `ByRef` 키워드를 사용 하 여이 메커니즘을 지정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f0c60-119">When you pass a variable by reference, you must use the `ByRef` keyword to specify this mechanism.</span></span>  
  
 <span data-ttu-id="f0c60-120">Visual Basic의 기본값은 인수를 값으로 전달 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="f0c60-120">The default in Visual Basic is to pass arguments by value.</span></span> <span data-ttu-id="f0c60-121">그러나 선언 된 모든 매개 변수와 함께 [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md) 또는 [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md) 키워드를 포함 하는 것이 좋은 프로그래밍 습관입니다.</span><span class="sxs-lookup"><span data-stu-id="f0c60-121">However, it is good programming practice to include either the [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md) or [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md) keyword with every declared parameter.</span></span> <span data-ttu-id="f0c60-122">이렇게 하면 코드를 보다 쉽게 읽을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f0c60-122">This makes your code easier to read.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="f0c60-123">강력한 프로그래밍</span><span class="sxs-lookup"><span data-stu-id="f0c60-123">Robust Programming</span></span>  
 <span data-ttu-id="f0c60-124">프로시저에서 [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md)매개 변수를 선언 하는 경우 코드의 올바른 실행은 호출 코드의 기본 요소를 변경할 수 있는지 여부에 따라 달라질 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f0c60-124">If a procedure declares a parameter [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md), the correct execution of the code might depend on being able to change the underlying element in the calling code.</span></span> <span data-ttu-id="f0c60-125">호출 코드가 인수를 괄호 안에 포함 하 여이 호출 메커니즘을 재정의 하거나 수정할 수 없는 인수를 전달 하는 경우 프로시저는 내부 요소를 변경할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="f0c60-125">If the calling code overrides this calling mechanism by enclosing the argument in parentheses, or if it passes a nonmodifiable argument, the procedure cannot change the underlying element.</span></span> <span data-ttu-id="f0c60-126">이렇게 하면 호출 코드에서 예기치 않은 결과가 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f0c60-126">This might produce unexpected results in the calling code.</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="f0c60-127">.NET Framework 보안</span><span class="sxs-lookup"><span data-stu-id="f0c60-127">.NET Framework Security</span></span>  
 <span data-ttu-id="f0c60-128">프로시저에서 호출 코드의 인수를 기반으로 하는 값을 변경 하는 것이 항상 발생할 수 있는 위험이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f0c60-128">There is always a potential risk in allowing a procedure to change the value underlying an argument in the calling code.</span></span> <span data-ttu-id="f0c60-129">이 값을 변경 하 고이 값을 사용 하기 전에 유효성 검사를 수행할 준비를 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f0c60-129">Make sure you expect this value to be changed, and be prepared to check it for validity before using it.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f0c60-130">참조</span><span class="sxs-lookup"><span data-stu-id="f0c60-130">See also</span></span>

- [<span data-ttu-id="f0c60-131">절차</span><span class="sxs-lookup"><span data-stu-id="f0c60-131">Procedures</span></span>](./index.md)
- [<span data-ttu-id="f0c60-132">프로시저 매개 변수 및 인수</span><span class="sxs-lookup"><span data-stu-id="f0c60-132">Procedure Parameters and Arguments</span></span>](./procedure-parameters-and-arguments.md)
- [<span data-ttu-id="f0c60-133">방법: 프로시저에 인수 전달</span><span class="sxs-lookup"><span data-stu-id="f0c60-133">How to: Pass Arguments to a Procedure</span></span>](./how-to-pass-arguments-to-a-procedure.md)
- [<span data-ttu-id="f0c60-134">값 또는 참조로 인수 전달</span><span class="sxs-lookup"><span data-stu-id="f0c60-134">Passing Arguments by Value and by Reference</span></span>](./passing-arguments-by-value-and-by-reference.md)
- [<span data-ttu-id="f0c60-135">수정할 수 있는 인수와 수정할 수 없는 인수 사이의 차이점</span><span class="sxs-lookup"><span data-stu-id="f0c60-135">Differences Between Modifiable and Nonmodifiable Arguments</span></span>](./differences-between-modifiable-and-nonmodifiable-arguments.md)
- [<span data-ttu-id="f0c60-136">인수를 값으로 전달할 때와 참조로 전달할 때의 차이점</span><span class="sxs-lookup"><span data-stu-id="f0c60-136">Differences Between Passing an Argument By Value and By Reference</span></span>](./differences-between-passing-an-argument-by-value-and-by-reference.md)
- [<span data-ttu-id="f0c60-137">방법: 프로시저 인수의 값 변경</span><span class="sxs-lookup"><span data-stu-id="f0c60-137">How to: Change the Value of a Procedure Argument</span></span>](./how-to-change-the-value-of-a-procedure-argument.md)
- [<span data-ttu-id="f0c60-138">방법: 값 변경에 대해 프로시저 인수 보호</span><span class="sxs-lookup"><span data-stu-id="f0c60-138">How to: Protect a Procedure Argument Against Value Changes</span></span>](./how-to-protect-a-procedure-argument-against-value-changes.md)
- [<span data-ttu-id="f0c60-139">위치 및 이름으로 인수 전달</span><span class="sxs-lookup"><span data-stu-id="f0c60-139">Passing Arguments by Position and by Name</span></span>](./passing-arguments-by-position-and-by-name.md)
- [<span data-ttu-id="f0c60-140">값 형식과 참조 형식</span><span class="sxs-lookup"><span data-stu-id="f0c60-140">Value Types and Reference Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)
