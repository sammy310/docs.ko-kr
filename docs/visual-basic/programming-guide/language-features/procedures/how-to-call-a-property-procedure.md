---
title: '방법: 속성 프로시저 호출'
ms.date: 07/20/2015
helpviewer_keywords:
- Visual Basic code, procedures
- Visual Basic code, properties
- procedures [Visual Basic], calling
- properties [Visual Basic], property procedures
- procedure calls [Visual Basic], property procedures
ms.assetid: 96bc4d74-d9c3-4b7a-954d-58ac8553cd94
ms.openlocfilehash: 52e6c62ffb81c480ccc1abf06f04eb780218dbf1
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/22/2019
ms.locfileid: "74340549"
---
# <a name="how-to-call-a-property-procedure-visual-basic"></a><span data-ttu-id="79c30-102">방법: 속성 프로시저 호출(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="79c30-102">How to: Call a Property Procedure (Visual Basic)</span></span>
<span data-ttu-id="79c30-103">속성에 값을 저장 하거나 값을 검색 하 여 속성 프로시저를 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="79c30-103">You call a property procedure by storing a value in the property or retrieving its value.</span></span> <span data-ttu-id="79c30-104">변수에 액세스 하는 것과 동일한 방식으로 속성에 액세스 합니다.</span><span class="sxs-lookup"><span data-stu-id="79c30-104">You access a property the same way you access a variable.</span></span>  
  
 <span data-ttu-id="79c30-105">속성의 `Set` 프로시저는 값을 저장 하 고 해당 `Get` 프로시저는 값을 검색 합니다.</span><span class="sxs-lookup"><span data-stu-id="79c30-105">The property's `Set` procedure stores a value, and its `Get` procedure retrieves the value.</span></span> <span data-ttu-id="79c30-106">그러나 이러한 프로시저를 이름으로 명시적으로 호출 하지는 않습니다.</span><span class="sxs-lookup"><span data-stu-id="79c30-106">However, you do not explicitly call these procedures by name.</span></span> <span data-ttu-id="79c30-107">변수 값을 저장 하거나 검색 하는 것 처럼 대입문 또는 식에서 속성을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="79c30-107">You use the property in an assignment statement or an expression, just as you would store or retrieve the value of a variable.</span></span> <span data-ttu-id="79c30-108">Visual Basic은 속성의 프로시저에 대 한 호출을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="79c30-108">Visual Basic makes the calls to the property's procedures.</span></span>  
  
### <a name="to-call-a-propertys-get-procedure"></a><span data-ttu-id="79c30-109">속성의 Get 프로시저를 호출 하려면</span><span class="sxs-lookup"><span data-stu-id="79c30-109">To call a property's Get procedure</span></span>  
  
1. <span data-ttu-id="79c30-110">변수 이름을 사용 하는 것과 동일한 방식으로 식에 속성 이름을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="79c30-110">Use the property name in an expression the same way you would use a variable name.</span></span> <span data-ttu-id="79c30-111">변수나 상수를 사용할 수 있는 모든 위치에서 속성을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="79c30-111">You can use a property anywhere you can use a variable or a constant.</span></span>  
  
     <span data-ttu-id="79c30-112">-또는-</span><span class="sxs-lookup"><span data-stu-id="79c30-112">-or-</span></span>  
  
     <span data-ttu-id="79c30-113">등호 (`=`) 뒤에 오는 속성 이름을 대입문에 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="79c30-113">Use the property name following the equal (`=`) sign in an assignment statement.</span></span>  
  
     <span data-ttu-id="79c30-114">다음 예제에서는 `Get` 프로시저를 암시적으로 호출 하 여 <xref:Microsoft.VisualBasic.DateAndTime.Now%2A> 속성의 값을 읽습니다.</span><span class="sxs-lookup"><span data-stu-id="79c30-114">The following example reads the value of the <xref:Microsoft.VisualBasic.DateAndTime.Now%2A> property, implicitly calling its `Get` procedure.</span></span>  
  
     [!code-vb[VbVbalrDateProperties#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrDateProperties/VB/Module1.vb#4)]  
  
2. <span data-ttu-id="79c30-115">속성이 인수를 사용 하는 경우 속성 이름에 괄호를 추가 하 여 인수 목록을 묶습니다.</span><span class="sxs-lookup"><span data-stu-id="79c30-115">If the property takes arguments, follow the property name with parentheses to enclose the argument list.</span></span> <span data-ttu-id="79c30-116">인수가 없으면 선택적으로 괄호를 생략할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="79c30-116">If there are no arguments, you can optionally omit the parentheses.</span></span>  
  
3. <span data-ttu-id="79c30-117">인수 목록에서 인수를 쉼표로 구분 하 여 괄호 안에 넣습니다.</span><span class="sxs-lookup"><span data-stu-id="79c30-117">Place the arguments in the argument list within the parentheses, separated by commas.</span></span> <span data-ttu-id="79c30-118">속성이 해당 매개 변수를 정의 하는 순서와 동일한 순서로 인수를 제공 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="79c30-118">Be sure you supply the arguments in the same order that the property defines the corresponding parameters.</span></span>  
  
 <span data-ttu-id="79c30-119">속성의 값은 변수 또는 상수와 마찬가지로 식에 참여 하거나 대입문의 왼쪽에 있는 변수나 속성에 저장 됩니다.</span><span class="sxs-lookup"><span data-stu-id="79c30-119">The value of the property participates in the expression just as a variable or constant would, or it is stored in the variable or property on the left side of the assignment statement.</span></span>  
  
### <a name="to-call-a-propertys-set-procedure"></a><span data-ttu-id="79c30-120">속성의 Set 프로시저를 호출 하려면</span><span class="sxs-lookup"><span data-stu-id="79c30-120">To call a property's Set procedure</span></span>  
  
1. <span data-ttu-id="79c30-121">대입문의 왼쪽에 속성 이름을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="79c30-121">Use the property name on the left side of an assignment statement.</span></span>  
  
     <span data-ttu-id="79c30-122">다음 예에서는 `Set` 프로시저를 암시적으로 호출 하 여 <xref:Microsoft.VisualBasic.DateAndTime.TimeOfDay%2A> 속성의 값을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="79c30-122">The following example sets the value of the <xref:Microsoft.VisualBasic.DateAndTime.TimeOfDay%2A> property, implicitly calling the `Set` procedure.</span></span>  
  
     [!code-vb[VbVbcnProcedures#11](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#11)]  
  
2. <span data-ttu-id="79c30-123">속성이 인수를 사용 하는 경우 속성 이름에 괄호를 추가 하 여 인수 목록을 묶습니다.</span><span class="sxs-lookup"><span data-stu-id="79c30-123">If the property takes arguments, follow the property name with parentheses to enclose the argument list.</span></span> <span data-ttu-id="79c30-124">인수가 없으면 선택적으로 괄호를 생략할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="79c30-124">If there are no arguments, you can optionally omit the parentheses.</span></span>  
  
3. <span data-ttu-id="79c30-125">인수 목록에서 인수를 쉼표로 구분 하 여 괄호 안에 넣습니다.</span><span class="sxs-lookup"><span data-stu-id="79c30-125">Place the arguments in the argument list within the parentheses, separated by commas.</span></span> <span data-ttu-id="79c30-126">속성이 해당 매개 변수를 정의 하는 순서와 동일한 순서로 인수를 제공 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="79c30-126">Be sure you supply the arguments in the same order that the property defines the corresponding parameters.</span></span>  
  
 <span data-ttu-id="79c30-127">대입문의 오른쪽에 생성 된 값은 속성에 저장 됩니다.</span><span class="sxs-lookup"><span data-stu-id="79c30-127">The value generated on the right side of the assignment statement is stored in the property.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="79c30-128">참고 항목</span><span class="sxs-lookup"><span data-stu-id="79c30-128">See also</span></span>

- [<span data-ttu-id="79c30-129">속성 프로시저</span><span class="sxs-lookup"><span data-stu-id="79c30-129">Property Procedures</span></span>](./property-procedures.md)
- [<span data-ttu-id="79c30-130">프로시저 매개 변수 및 인수</span><span class="sxs-lookup"><span data-stu-id="79c30-130">Procedure Parameters and Arguments</span></span>](./procedure-parameters-and-arguments.md)
- [<span data-ttu-id="79c30-131">Property 문</span><span class="sxs-lookup"><span data-stu-id="79c30-131">Property Statement</span></span>](../../../../visual-basic/language-reference/statements/property-statement.md)
- [<span data-ttu-id="79c30-132">Visual Basic에서 속성과 변수의 차이점</span><span class="sxs-lookup"><span data-stu-id="79c30-132">Differences Between Properties and Variables in Visual Basic</span></span>](./differences-between-properties-and-variables.md)
- [<span data-ttu-id="79c30-133">방법: 속성 만들기</span><span class="sxs-lookup"><span data-stu-id="79c30-133">How to: Create a Property</span></span>](./how-to-create-a-property.md)
- [<span data-ttu-id="79c30-134">방법: 액세스 수준이 혼합된 속성 선언</span><span class="sxs-lookup"><span data-stu-id="79c30-134">How to: Declare a Property with Mixed Access Levels</span></span>](./how-to-declare-a-property-with-mixed-access-levels.md)
- [<span data-ttu-id="79c30-135">방법: Visual Basic에서 기본 속성 선언 및 호출</span><span class="sxs-lookup"><span data-stu-id="79c30-135">How to: Declare and Call a Default Property in Visual Basic</span></span>](./how-to-declare-and-call-a-default-property.md)
- [<span data-ttu-id="79c30-136">방법: 속성 값 입력</span><span class="sxs-lookup"><span data-stu-id="79c30-136">How to: Put a Value in a Property</span></span>](./how-to-put-a-value-in-a-property.md)
- [<span data-ttu-id="79c30-137">방법: 속성에서 값 가져오기</span><span class="sxs-lookup"><span data-stu-id="79c30-137">How to: Get a Value from a Property</span></span>](./how-to-get-a-value-from-a-property.md)
- [<span data-ttu-id="79c30-138">Get 문</span><span class="sxs-lookup"><span data-stu-id="79c30-138">Get Statement</span></span>](../../../../visual-basic/language-reference/statements/get-statement.md)
- [<span data-ttu-id="79c30-139">Set 문</span><span class="sxs-lookup"><span data-stu-id="79c30-139">Set Statement</span></span>](../../../../visual-basic/language-reference/statements/set-statement.md)
