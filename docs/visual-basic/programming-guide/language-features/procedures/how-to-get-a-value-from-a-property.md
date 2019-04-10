---
title: '방법: (Visual Basic) 속성에서 값 가져오기'
ms.date: 07/20/2015
helpviewer_keywords:
- property values [Visual Basic]
- Visual Basic code, procedures
- values [Visual Basic], properties
- Visual Basic code, properties
- properties [Visual Basic], values
ms.assetid: 3954423e-6ab7-4a4c-b55c-a8d27be47891
ms.openlocfilehash: 5e2676a0880092a78405fe5dafa0469161b85610
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/09/2019
ms.locfileid: "59302935"
---
# <a name="how-to-get-a-value-from-a-property-visual-basic"></a><span data-ttu-id="fe058-102">방법: (Visual Basic) 속성에서 값 가져오기</span><span class="sxs-lookup"><span data-stu-id="fe058-102">How to: Get a Value from a Property (Visual Basic)</span></span>
<span data-ttu-id="fe058-103">식에서 속성 이름을 포함 하 여 속성의 값을 검색 합니다.</span><span class="sxs-lookup"><span data-stu-id="fe058-103">You retrieve a property's value by including the property name in an expression.</span></span>  
  
 <span data-ttu-id="fe058-104">속성의 `Get` 프로시저는 값을 검색 하지만 명시적으로 호출 하지 해당 이름으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="fe058-104">The property's `Get` procedure retrieves the value, but you do not explicitly call it by name.</span></span> <span data-ttu-id="fe058-105">변수를 사용할 때 처럼 속성을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="fe058-105">You use the property just as you would use a variable.</span></span> <span data-ttu-id="fe058-106">Visual Basic에서는 속성의 프로시저를 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="fe058-106">Visual Basic makes the calls to the property's procedures.</span></span>  
  
### <a name="to-retrieve-a-value-from-a-property"></a><span data-ttu-id="fe058-107">속성에서 값을 검색 하려면</span><span class="sxs-lookup"><span data-stu-id="fe058-107">To retrieve a value from a property</span></span>  
  
1. <span data-ttu-id="fe058-108">변수 이름을 사용 하는 동일한 방식으로 식에서 속성 이름을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="fe058-108">Use the property name in an expression the same way you would use a variable name.</span></span> <span data-ttu-id="fe058-109">속성을 사용 하 여 어디서 나 변수 또는 상수를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fe058-109">You can use a property anywhere you can use a variable or a constant.</span></span>  
  
     <span data-ttu-id="fe058-110">또는</span><span class="sxs-lookup"><span data-stu-id="fe058-110">-or-</span></span>  
  
     <span data-ttu-id="fe058-111">다음에 오는 속성 이름 사용 (`=`) 대입문에 로그인 합니다.</span><span class="sxs-lookup"><span data-stu-id="fe058-111">Use the property name following the equal (`=`) sign in an assignment statement.</span></span>  
  
     <span data-ttu-id="fe058-112">다음 예제에서는 Visual Basic의 값을 읽습니다 `Now` 속성을 호출 하는 암시적으로 해당 `Get` 프로시저입니다.</span><span class="sxs-lookup"><span data-stu-id="fe058-112">The following example reads the value of the Visual Basic `Now` property, implicitly calling its `Get` procedure.</span></span>  
  
     [!code-vb[VbVbalrDateProperties#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrDateProperties/VB/Module1.vb#4)]  
  
2. <span data-ttu-id="fe058-113">속성 인수를 사용 하는 경우에 속성 이름을 괄호로 묶어 인수 목록에 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="fe058-113">If the property takes arguments, follow the property name with parentheses to enclose the argument list.</span></span> <span data-ttu-id="fe058-114">인수가 없는 경우에 필요에 따라 괄호를 생략할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fe058-114">If there are no arguments, you can optionally omit the parentheses.</span></span>  
  
3. <span data-ttu-id="fe058-115">쉼표로 구분 하 여 괄호 안에 인수 목록의 인수를 배치 합니다.</span><span class="sxs-lookup"><span data-stu-id="fe058-115">Place the arguments in the argument list within the parentheses, separated by commas.</span></span> <span data-ttu-id="fe058-116">속성은 해당 매개 변수 정의 동일한 순서로 인수를 지정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fe058-116">Be sure you supply the arguments in the same order that the property defines the corresponding parameters.</span></span>  
  
 <span data-ttu-id="fe058-117">변수 처럼 식에 참여 하는 속성의 값 또는 상수 또는 변수 또는 대입문의 왼쪽에는 속성에 저장 됩니다.</span><span class="sxs-lookup"><span data-stu-id="fe058-117">The value of the property participates in the expression just as a variable or constant would, or it is stored in the variable or property on the left side of the assignment statement.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fe058-118">참고자료</span><span class="sxs-lookup"><span data-stu-id="fe058-118">See also</span></span>

- [<span data-ttu-id="fe058-119">절차</span><span class="sxs-lookup"><span data-stu-id="fe058-119">Procedures</span></span>](./index.md)
- [<span data-ttu-id="fe058-120">속성 프로시저</span><span class="sxs-lookup"><span data-stu-id="fe058-120">Property Procedures</span></span>](./property-procedures.md)
- [<span data-ttu-id="fe058-121">프로시저 매개 변수 및 인수</span><span class="sxs-lookup"><span data-stu-id="fe058-121">Procedure Parameters and Arguments</span></span>](./procedure-parameters-and-arguments.md)
- [<span data-ttu-id="fe058-122">Property Statement</span><span class="sxs-lookup"><span data-stu-id="fe058-122">Property Statement</span></span>](../../../../visual-basic/language-reference/statements/property-statement.md)
- [<span data-ttu-id="fe058-123">Visual Basic에서 속성과 변수의 차이점</span><span class="sxs-lookup"><span data-stu-id="fe058-123">Differences Between Properties and Variables in Visual Basic</span></span>](./differences-between-properties-and-variables.md)
- [<span data-ttu-id="fe058-124">방법: 속성 만들기</span><span class="sxs-lookup"><span data-stu-id="fe058-124">How to: Create a Property</span></span>](./how-to-create-a-property.md)
- [<span data-ttu-id="fe058-125">방법: 액세스 수준이 혼합된 속성 선언</span><span class="sxs-lookup"><span data-stu-id="fe058-125">How to: Declare a Property with Mixed Access Levels</span></span>](./how-to-declare-a-property-with-mixed-access-levels.md)
- [<span data-ttu-id="fe058-126">방법: 속성 프로시저 호출</span><span class="sxs-lookup"><span data-stu-id="fe058-126">How to: Call a Property Procedure</span></span>](./how-to-call-a-property-procedure.md)
- [<span data-ttu-id="fe058-127">방법: 선언 및 Visual Basic의 기본 속성을 호출</span><span class="sxs-lookup"><span data-stu-id="fe058-127">How to: Declare and Call a Default Property in Visual Basic</span></span>](./how-to-declare-and-call-a-default-property.md)
- [<span data-ttu-id="fe058-128">방법: 속성 값 입력</span><span class="sxs-lookup"><span data-stu-id="fe058-128">How to: Put a Value in a Property</span></span>](./how-to-put-a-value-in-a-property.md)
