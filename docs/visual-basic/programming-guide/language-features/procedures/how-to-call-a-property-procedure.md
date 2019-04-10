---
title: '방법: 속성 프로시저 (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- Visual Basic code, procedures
- Visual Basic code, properties
- procedures [Visual Basic], calling
- properties [Visual Basic], property procedures
- procedure calls [Visual Basic], property procedures
ms.assetid: 96bc4d74-d9c3-4b7a-954d-58ac8553cd94
ms.openlocfilehash: d05c1b63f5567ade9935f80ecc022eb4840e0af0
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/09/2019
ms.locfileid: "59318756"
---
# <a name="how-to-call-a-property-procedure-visual-basic"></a><span data-ttu-id="963eb-102">방법: 속성 프로시저 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="963eb-102">How to: Call a Property Procedure (Visual Basic)</span></span>
<span data-ttu-id="963eb-103">속성에 값을 저장 하거나 해당 값을 검색 하는 속성 프로시저를 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="963eb-103">You call a property procedure by storing a value in the property or retrieving its value.</span></span> <span data-ttu-id="963eb-104">변수에 액세스할 때 동일한 방식으로 속성에 액세스 합니다.</span><span class="sxs-lookup"><span data-stu-id="963eb-104">You access a property the same way you access a variable.</span></span>  
  
 <span data-ttu-id="963eb-105">속성의 `Set` 프로시저에서 값을 저장 및 해당 `Get` 값을 검색 하는 프로시저입니다.</span><span class="sxs-lookup"><span data-stu-id="963eb-105">The property's `Set` procedure stores a value, and its `Get` procedure retrieves the value.</span></span> <span data-ttu-id="963eb-106">그러나 명시적으로 호출 하지 이러한 프로시저 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="963eb-106">However, you do not explicitly call these procedures by name.</span></span> <span data-ttu-id="963eb-107">저장 하거나 변수의 값을 검색할 것 처럼 대입문 또는 식에서 속성을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="963eb-107">You use the property in an assignment statement or an expression, just as you would store or retrieve the value of a variable.</span></span> <span data-ttu-id="963eb-108">Visual Basic에서는 속성의 프로시저를 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="963eb-108">Visual Basic makes the calls to the property's procedures.</span></span>  
  
### <a name="to-call-a-propertys-get-procedure"></a><span data-ttu-id="963eb-109">속성의 Get 프로시저를 호출 하려면</span><span class="sxs-lookup"><span data-stu-id="963eb-109">To call a property's Get procedure</span></span>  
  
1. <span data-ttu-id="963eb-110">변수 이름을 사용 하는 동일한 방식으로 식에서 속성 이름을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="963eb-110">Use the property name in an expression the same way you would use a variable name.</span></span> <span data-ttu-id="963eb-111">속성을 사용 하 여 어디서 나 변수 또는 상수를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="963eb-111">You can use a property anywhere you can use a variable or a constant.</span></span>  
  
     <span data-ttu-id="963eb-112">또는</span><span class="sxs-lookup"><span data-stu-id="963eb-112">-or-</span></span>  
  
     <span data-ttu-id="963eb-113">다음에 오는 속성 이름 사용 (`=`) 대입문에 로그인 합니다.</span><span class="sxs-lookup"><span data-stu-id="963eb-113">Use the property name following the equal (`=`) sign in an assignment statement.</span></span>  
  
     <span data-ttu-id="963eb-114">다음 예제에서는 값을 읽습니다 합니다 <xref:Microsoft.VisualBasic.DateAndTime.Now%2A> 속성을 호출 하는 암시적으로 해당 `Get` 프로시저입니다.</span><span class="sxs-lookup"><span data-stu-id="963eb-114">The following example reads the value of the <xref:Microsoft.VisualBasic.DateAndTime.Now%2A> property, implicitly calling its `Get` procedure.</span></span>  
  
     [!code-vb[VbVbalrDateProperties#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrDateProperties/VB/Module1.vb#4)]  
  
2. <span data-ttu-id="963eb-115">속성 인수를 사용 하는 경우에 속성 이름을 괄호로 묶어 인수 목록에 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="963eb-115">If the property takes arguments, follow the property name with parentheses to enclose the argument list.</span></span> <span data-ttu-id="963eb-116">인수가 없는 경우에 필요에 따라 괄호를 생략할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="963eb-116">If there are no arguments, you can optionally omit the parentheses.</span></span>  
  
3. <span data-ttu-id="963eb-117">쉼표로 구분 하 여 괄호 안에 인수 목록의 인수를 배치 합니다.</span><span class="sxs-lookup"><span data-stu-id="963eb-117">Place the arguments in the argument list within the parentheses, separated by commas.</span></span> <span data-ttu-id="963eb-118">속성은 해당 매개 변수 정의 동일한 순서로 인수를 지정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="963eb-118">Be sure you supply the arguments in the same order that the property defines the corresponding parameters.</span></span>  
  
 <span data-ttu-id="963eb-119">변수 처럼 식에 참여 하는 속성의 값 또는 상수 또는 변수 또는 대입문의 왼쪽에는 속성에 저장 됩니다.</span><span class="sxs-lookup"><span data-stu-id="963eb-119">The value of the property participates in the expression just as a variable or constant would, or it is stored in the variable or property on the left side of the assignment statement.</span></span>  
  
### <a name="to-call-a-propertys-set-procedure"></a><span data-ttu-id="963eb-120">프로시저의 집합 속성을 호출 하려면</span><span class="sxs-lookup"><span data-stu-id="963eb-120">To call a property's Set procedure</span></span>  
  
1. <span data-ttu-id="963eb-121">대입문의 왼쪽에 속성 이름을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="963eb-121">Use the property name on the left side of an assignment statement.</span></span>  
  
     <span data-ttu-id="963eb-122">다음 예제에서는 값을 설정 합니다 <xref:Microsoft.VisualBasic.DateAndTime.TimeOfDay%2A> 속성을 암시적으로 호출는 `Set` 프로시저.</span><span class="sxs-lookup"><span data-stu-id="963eb-122">The following example sets the value of the <xref:Microsoft.VisualBasic.DateAndTime.TimeOfDay%2A> property, implicitly calling the `Set` procedure.</span></span>  
  
     [!code-vb[VbVbcnProcedures#11](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#11)]  
  
2. <span data-ttu-id="963eb-123">속성 인수를 사용 하는 경우에 속성 이름을 괄호로 묶어 인수 목록에 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="963eb-123">If the property takes arguments, follow the property name with parentheses to enclose the argument list.</span></span> <span data-ttu-id="963eb-124">인수가 없는 경우에 필요에 따라 괄호를 생략할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="963eb-124">If there are no arguments, you can optionally omit the parentheses.</span></span>  
  
3. <span data-ttu-id="963eb-125">쉼표로 구분 하 여 괄호 안에 인수 목록의 인수를 배치 합니다.</span><span class="sxs-lookup"><span data-stu-id="963eb-125">Place the arguments in the argument list within the parentheses, separated by commas.</span></span> <span data-ttu-id="963eb-126">속성은 해당 매개 변수 정의 동일한 순서로 인수를 지정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="963eb-126">Be sure you supply the arguments in the same order that the property defines the corresponding parameters.</span></span>  
  
 <span data-ttu-id="963eb-127">대입문의 오른쪽에 생성 된 값을 속성에 저장 됩니다.</span><span class="sxs-lookup"><span data-stu-id="963eb-127">The value generated on the right side of the assignment statement is stored in the property.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="963eb-128">참고자료</span><span class="sxs-lookup"><span data-stu-id="963eb-128">See also</span></span>

- [<span data-ttu-id="963eb-129">속성 프로시저</span><span class="sxs-lookup"><span data-stu-id="963eb-129">Property Procedures</span></span>](./property-procedures.md)
- [<span data-ttu-id="963eb-130">프로시저 매개 변수 및 인수</span><span class="sxs-lookup"><span data-stu-id="963eb-130">Procedure Parameters and Arguments</span></span>](./procedure-parameters-and-arguments.md)
- [<span data-ttu-id="963eb-131">Property Statement</span><span class="sxs-lookup"><span data-stu-id="963eb-131">Property Statement</span></span>](../../../../visual-basic/language-reference/statements/property-statement.md)
- [<span data-ttu-id="963eb-132">Visual Basic에서 속성과 변수의 차이점</span><span class="sxs-lookup"><span data-stu-id="963eb-132">Differences Between Properties and Variables in Visual Basic</span></span>](./differences-between-properties-and-variables.md)
- [<span data-ttu-id="963eb-133">방법: 속성 만들기</span><span class="sxs-lookup"><span data-stu-id="963eb-133">How to: Create a Property</span></span>](./how-to-create-a-property.md)
- [<span data-ttu-id="963eb-134">방법: 액세스 수준이 혼합된 속성 선언</span><span class="sxs-lookup"><span data-stu-id="963eb-134">How to: Declare a Property with Mixed Access Levels</span></span>](./how-to-declare-a-property-with-mixed-access-levels.md)
- [<span data-ttu-id="963eb-135">방법: 선언 및 Visual Basic의 기본 속성을 호출</span><span class="sxs-lookup"><span data-stu-id="963eb-135">How to: Declare and Call a Default Property in Visual Basic</span></span>](./how-to-declare-and-call-a-default-property.md)
- [<span data-ttu-id="963eb-136">방법: 속성 값 입력</span><span class="sxs-lookup"><span data-stu-id="963eb-136">How to: Put a Value in a Property</span></span>](./how-to-put-a-value-in-a-property.md)
- [<span data-ttu-id="963eb-137">방법: 속성에서 값 가져오기</span><span class="sxs-lookup"><span data-stu-id="963eb-137">How to: Get a Value from a Property</span></span>](./how-to-get-a-value-from-a-property.md)
- [<span data-ttu-id="963eb-138">Get 문</span><span class="sxs-lookup"><span data-stu-id="963eb-138">Get Statement</span></span>](../../../../visual-basic/language-reference/statements/get-statement.md)
- [<span data-ttu-id="963eb-139">Set 문</span><span class="sxs-lookup"><span data-stu-id="963eb-139">Set Statement</span></span>](../../../../visual-basic/language-reference/statements/set-statement.md)
