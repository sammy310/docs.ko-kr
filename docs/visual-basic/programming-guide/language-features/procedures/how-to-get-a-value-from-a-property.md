---
title: '방법: 속성에서 값 가져오기'
ms.date: 07/20/2015
helpviewer_keywords:
- property values [Visual Basic]
- Visual Basic code, procedures
- values [Visual Basic], properties
- Visual Basic code, properties
- properties [Visual Basic], values
ms.assetid: 3954423e-6ab7-4a4c-b55c-a8d27be47891
ms.openlocfilehash: 983e2fd22badf4296004404d885df0a07ab2dc74
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/23/2020
ms.locfileid: "91071562"
---
# <a name="how-to-get-a-value-from-a-property-visual-basic"></a><span data-ttu-id="6513f-102">방법: 속성에서 값 가져오기(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="6513f-102">How to: Get a Value from a Property (Visual Basic)</span></span>

<span data-ttu-id="6513f-103">식에 속성 이름을 포함 하 여 속성의 값을 검색 합니다.</span><span class="sxs-lookup"><span data-stu-id="6513f-103">You retrieve a property's value by including the property name in an expression.</span></span>  
  
 <span data-ttu-id="6513f-104">속성의 `Get` 프로시저에서 값을 검색 하지만 이름으로 명시적으로 호출 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="6513f-104">The property's `Get` procedure retrieves the value, but you do not explicitly call it by name.</span></span> <span data-ttu-id="6513f-105">변수를 사용 하는 것 처럼 속성을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="6513f-105">You use the property just as you would use a variable.</span></span> <span data-ttu-id="6513f-106">Visual Basic은 속성의 프로시저에 대 한 호출을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="6513f-106">Visual Basic makes the calls to the property's procedures.</span></span>  
  
### <a name="to-retrieve-a-value-from-a-property"></a><span data-ttu-id="6513f-107">속성에서 값을 검색 하려면</span><span class="sxs-lookup"><span data-stu-id="6513f-107">To retrieve a value from a property</span></span>  
  
1. <span data-ttu-id="6513f-108">변수 이름을 사용 하는 것과 동일한 방식으로 식에 속성 이름을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="6513f-108">Use the property name in an expression the same way you would use a variable name.</span></span> <span data-ttu-id="6513f-109">변수나 상수를 사용할 수 있는 모든 위치에서 속성을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6513f-109">You can use a property anywhere you can use a variable or a constant.</span></span>  
  
     <span data-ttu-id="6513f-110">또는</span><span class="sxs-lookup"><span data-stu-id="6513f-110">-or-</span></span>  
  
     <span data-ttu-id="6513f-111">대입문에 등호 () 기호를 사용 하 여 속성 이름을 사용 `=` 합니다.</span><span class="sxs-lookup"><span data-stu-id="6513f-111">Use the property name following the equal (`=`) sign in an assignment statement.</span></span>  
  
     <span data-ttu-id="6513f-112">다음 예제에서는 `Now` 해당 프로시저를 암시적으로 호출 하 여 Visual Basic 속성의 값을 읽습니다 `Get` .</span><span class="sxs-lookup"><span data-stu-id="6513f-112">The following example reads the value of the Visual Basic `Now` property, implicitly calling its `Get` procedure.</span></span>  
  
     [!code-vb[VbVbalrDateProperties#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrDateProperties/VB/Module1.vb#4)]  
  
2. <span data-ttu-id="6513f-113">속성이 인수를 사용 하는 경우 속성 이름에 괄호를 추가 하 여 인수 목록을 묶습니다.</span><span class="sxs-lookup"><span data-stu-id="6513f-113">If the property takes arguments, follow the property name with parentheses to enclose the argument list.</span></span> <span data-ttu-id="6513f-114">인수가 없으면 선택적으로 괄호를 생략할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6513f-114">If there are no arguments, you can optionally omit the parentheses.</span></span>  
  
3. <span data-ttu-id="6513f-115">인수 목록에서 인수를 쉼표로 구분 하 여 괄호 안에 넣습니다.</span><span class="sxs-lookup"><span data-stu-id="6513f-115">Place the arguments in the argument list within the parentheses, separated by commas.</span></span> <span data-ttu-id="6513f-116">속성이 해당 매개 변수를 정의 하는 순서와 동일한 순서로 인수를 제공 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6513f-116">Be sure you supply the arguments in the same order that the property defines the corresponding parameters.</span></span>  
  
 <span data-ttu-id="6513f-117">속성의 값은 변수 또는 상수와 마찬가지로 식에 참여 하거나 대입문의 왼쪽에 있는 변수나 속성에 저장 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6513f-117">The value of the property participates in the expression just as a variable or constant would, or it is stored in the variable or property on the left side of the assignment statement.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6513f-118">참조</span><span class="sxs-lookup"><span data-stu-id="6513f-118">See also</span></span>

- [<span data-ttu-id="6513f-119">절차</span><span class="sxs-lookup"><span data-stu-id="6513f-119">Procedures</span></span>](./index.md)
- [<span data-ttu-id="6513f-120">속성 프로시저</span><span class="sxs-lookup"><span data-stu-id="6513f-120">Property Procedures</span></span>](./property-procedures.md)
- [<span data-ttu-id="6513f-121">프로시저 매개 변수 및 인수</span><span class="sxs-lookup"><span data-stu-id="6513f-121">Procedure Parameters and Arguments</span></span>](./procedure-parameters-and-arguments.md)
- [<span data-ttu-id="6513f-122">Property Statement</span><span class="sxs-lookup"><span data-stu-id="6513f-122">Property Statement</span></span>](../../../language-reference/statements/property-statement.md)
- [<span data-ttu-id="6513f-123">Visual Basic에서 속성과 변수의 차이점</span><span class="sxs-lookup"><span data-stu-id="6513f-123">Differences Between Properties and Variables in Visual Basic</span></span>](./differences-between-properties-and-variables.md)
- [<span data-ttu-id="6513f-124">방법: 속성 만들기</span><span class="sxs-lookup"><span data-stu-id="6513f-124">How to: Create a Property</span></span>](./how-to-create-a-property.md)
- [<span data-ttu-id="6513f-125">방법: 액세스 수준이 혼합된 속성 선언</span><span class="sxs-lookup"><span data-stu-id="6513f-125">How to: Declare a Property with Mixed Access Levels</span></span>](./how-to-declare-a-property-with-mixed-access-levels.md)
- [<span data-ttu-id="6513f-126">방법: 속성 프로시저 호출</span><span class="sxs-lookup"><span data-stu-id="6513f-126">How to: Call a Property Procedure</span></span>](./how-to-call-a-property-procedure.md)
- [<span data-ttu-id="6513f-127">방법: Visual Basic에서 기본 속성 선언 및 호출</span><span class="sxs-lookup"><span data-stu-id="6513f-127">How to: Declare and Call a Default Property in Visual Basic</span></span>](./how-to-declare-and-call-a-default-property.md)
- [<span data-ttu-id="6513f-128">방법: 속성 값 입력</span><span class="sxs-lookup"><span data-stu-id="6513f-128">How to: Put a Value in a Property</span></span>](./how-to-put-a-value-in-a-property.md)
