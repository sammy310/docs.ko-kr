---
description: '자세히 알아보기: Set 문 (Visual Basic)'
title: Set 문
ms.date: 07/20/2015
f1_keywords:
- vb.Set
helpviewer_keywords:
- property procedures [Visual Basic], Set statements
- Set statement [Visual Basic]
- Set statement [Visual Basic], syntax
- write-only properties
- properties [Visual Basic], write-only
ms.assetid: 9ecc27b4-df84-420d-9075-db25455fb3cd
ms.openlocfilehash: 5ee27b35a4639bc20d5b6634de8332c6ede9bf12
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99741122"
---
# <a name="set-statement-visual-basic"></a><span data-ttu-id="bb745-103">Set 문(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="bb745-103">Set Statement (Visual Basic)</span></span>

<span data-ttu-id="bb745-104">`Set`속성에 값을 할당 하는 데 사용 되는 속성 프로시저를 선언 합니다.</span><span class="sxs-lookup"><span data-stu-id="bb745-104">Declares a `Set` property procedure used to assign a value to a property.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bb745-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="bb745-105">Syntax</span></span>  
  
```vb  
[ <attributelist> ] [ accessmodifier ] Set (ByVal value [ As datatype ])  
    [ statements ]  
End Set  
```  
  
## <a name="parts"></a><span data-ttu-id="bb745-106">부분</span><span class="sxs-lookup"><span data-stu-id="bb745-106">Parts</span></span>  

 `attributelist`  
 <span data-ttu-id="bb745-107">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="bb745-107">Optional.</span></span> <span data-ttu-id="bb745-108">[특성 목록](attribute-list.md)을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="bb745-108">See [Attribute List](attribute-list.md).</span></span>  
  
 `accessmodifier`  
 <span data-ttu-id="bb745-109">`Get`이 속성의 및 문 중 최대 하나에 대해 선택적입니다 `Set` .</span><span class="sxs-lookup"><span data-stu-id="bb745-109">Optional on at most one of the `Get` and `Set` statements in this property.</span></span> <span data-ttu-id="bb745-110">다음 중 하나일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bb745-110">Can be one of the following:</span></span>  
  
- [<span data-ttu-id="bb745-111">보호됨</span><span class="sxs-lookup"><span data-stu-id="bb745-111">Protected</span></span>](../modifiers/protected.md)  
  
- [<span data-ttu-id="bb745-112">Friend</span><span class="sxs-lookup"><span data-stu-id="bb745-112">Friend</span></span>](../modifiers/friend.md)  
  
- [<span data-ttu-id="bb745-113">개인</span><span class="sxs-lookup"><span data-stu-id="bb745-113">Private</span></span>](../modifiers/private.md)  
  
- `Protected Friend`  
  
 <span data-ttu-id="bb745-114">[Access levels in Visual Basic](../../programming-guide/language-features/declared-elements/access-levels.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="bb745-114">See [Access levels in Visual Basic](../../programming-guide/language-features/declared-elements/access-levels.md).</span></span>  
  
 `value`  
 <span data-ttu-id="bb745-115">필수 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="bb745-115">Required.</span></span> <span data-ttu-id="bb745-116">속성의 새 값을 포함 하는 매개 변수입니다.</span><span class="sxs-lookup"><span data-stu-id="bb745-116">Parameter containing the new value for the property.</span></span>  
  
 `datatype`  
 <span data-ttu-id="bb745-117">필요한 경우 `Option Strict` 는 `On`합니다.</span><span class="sxs-lookup"><span data-stu-id="bb745-117">Required if `Option Strict` is `On`.</span></span> <span data-ttu-id="bb745-118">매개 변수의 데이터 형식 `value` 입니다.</span><span class="sxs-lookup"><span data-stu-id="bb745-118">Data type of the `value` parameter.</span></span> <span data-ttu-id="bb745-119">지정 된 데이터 형식은이 문이 선언 된 속성의 데이터 형식과 동일 해야 합니다 `Set` .</span><span class="sxs-lookup"><span data-stu-id="bb745-119">The data type specified must be the same as the data type of the property where this `Set` statement is declared.</span></span>  
  
 `statements`  
 <span data-ttu-id="bb745-120">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="bb745-120">Optional.</span></span> <span data-ttu-id="bb745-121">속성 프로시저가 호출 될 때 실행 되는 하나 이상의 문입니다 `Set` .</span><span class="sxs-lookup"><span data-stu-id="bb745-121">One or more statements that run when the `Set` property procedure is called.</span></span>  
  
 `End Set`  
 <span data-ttu-id="bb745-122">필수 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="bb745-122">Required.</span></span> <span data-ttu-id="bb745-123">속성 프로시저의 정의를 종료 `Set` 합니다.</span><span class="sxs-lookup"><span data-stu-id="bb745-123">Terminates the definition of the `Set` property procedure.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="bb745-124">설명</span><span class="sxs-lookup"><span data-stu-id="bb745-124">Remarks</span></span>  

 <span data-ttu-id="bb745-125">`Set`속성이로 표시 되지 않은 경우 모든 속성에 속성 프로시저가 있어야 합니다 `ReadOnly` .</span><span class="sxs-lookup"><span data-stu-id="bb745-125">Every property must have a `Set` property procedure unless the property is marked `ReadOnly`.</span></span> <span data-ttu-id="bb745-126">`Set`프로시저는 속성의 값을 설정 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="bb745-126">The `Set` procedure is used to set the value of the property.</span></span>  
  
 <span data-ttu-id="bb745-127">`Set`대입문은 속성에 저장 되는 값을 제공 하는 경우 속성의 프로시저를 자동으로 호출 Visual Basic 합니다.</span><span class="sxs-lookup"><span data-stu-id="bb745-127">Visual Basic automatically calls a property's `Set` procedure when an assignment statement provides a value to be stored in the property.</span></span>  
  
 <span data-ttu-id="bb745-128">Visual Basic는 속성을 할당 하는 동안 매개 변수를 프로시저에 전달 `Set` 합니다.</span><span class="sxs-lookup"><span data-stu-id="bb745-128">Visual Basic passes a parameter to the `Set` procedure during property assignments.</span></span> <span data-ttu-id="bb745-129">에 대 한 매개 변수를 제공 하지 않으면 `Set` IDE (통합 개발 환경)에서 라는 암시적 매개 변수를 사용 합니다 `value` .</span><span class="sxs-lookup"><span data-stu-id="bb745-129">If you do not supply a parameter for `Set`, the integrated development environment (IDE) uses an implicit parameter named `value`.</span></span> <span data-ttu-id="bb745-130">매개 변수는 속성에 할당 되는 값을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="bb745-130">The parameter holds the value to be assigned to the property.</span></span> <span data-ttu-id="bb745-131">일반적으로이 값을 private 지역 변수에 저장 하 고 프로시저가 호출 될 때마다 반환 `Get` 합니다.</span><span class="sxs-lookup"><span data-stu-id="bb745-131">You typically store this value in a private local variable and return it whenever the `Get` procedure is called.</span></span>  
  
 <span data-ttu-id="bb745-132">속성 선언의 본문은 속성 `Get` `Set` [문과](property-statement.md) 문 사이에 속성의 및 프로시저만 포함할 수 있습니다 `End Property` .</span><span class="sxs-lookup"><span data-stu-id="bb745-132">The body of the property declaration can contain only the property's `Get` and `Set` procedures between the [Property Statement](property-statement.md) and the `End Property` statement.</span></span> <span data-ttu-id="bb745-133">이러한 프로시저 이외의 항목은 저장할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="bb745-133">It cannot store anything other than those procedures.</span></span> <span data-ttu-id="bb745-134">특히 속성의 현재 값을 저장할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="bb745-134">In particular, it cannot store the property's current value.</span></span> <span data-ttu-id="bb745-135">속성 프로시저 중 하나에 저장 하는 경우 다른 속성 프로시저에서 액세스할 수 없기 때문에이 값을 속성 외부에 저장 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="bb745-135">You must store this value outside the property, because if you store it inside either of the property procedures, the other property procedure cannot access it.</span></span> <span data-ttu-id="bb745-136">일반적인 방법은 속성과 같은 수준에서 선언 된 [전용](../modifiers/private.md) 변수에 값을 저장 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="bb745-136">The usual approach is to store the value in a [Private](../modifiers/private.md) variable declared at the same level as the property.</span></span> <span data-ttu-id="bb745-137">`Set`속성이 적용 되는 속성 내에 프로시저를 정의 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="bb745-137">You must define a `Set` procedure inside the property to which it applies.</span></span>  
  
 <span data-ttu-id="bb745-138">`Set`문에서를 사용 하지 않는 경우 프로시저는 포함 하는 속성의 액세스 수준으로 설정 `accessmodifier` `Set` 됩니다.</span><span class="sxs-lookup"><span data-stu-id="bb745-138">The `Set` procedure defaults to the access level of its containing property unless you use `accessmodifier` in the `Set` statement.</span></span>  
  
## <a name="rules"></a><span data-ttu-id="bb745-139">규칙</span><span class="sxs-lookup"><span data-stu-id="bb745-139">Rules</span></span>  
  
- <span data-ttu-id="bb745-140">**혼합 액세스 수준.**</span><span class="sxs-lookup"><span data-stu-id="bb745-140">**Mixed Access Levels.**</span></span> <span data-ttu-id="bb745-141">읽기/쓰기 속성을 정의 하는 경우 필요에 따라 또는 프로시저 중 하나에 다른 액세스 수준을 지정할 수 있습니다 `Get` `Set` .</span><span class="sxs-lookup"><span data-stu-id="bb745-141">If you are defining a read-write property, you can optionally specify a different access level for either the `Get` or the `Set` procedure, but not both.</span></span> <span data-ttu-id="bb745-142">이 작업을 수행 하는 경우 프로시저 액세스 수준이 속성의 액세스 수준 보다 더 제한적 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="bb745-142">If you do this, the procedure access level must be more restrictive than the property's access level.</span></span> <span data-ttu-id="bb745-143">예를 들어 속성이 선언 된 경우 `Friend` 프로시저를 선언할 수 있지만는 선언할 수 `Set` `Private` 없습니다 `Public` .</span><span class="sxs-lookup"><span data-stu-id="bb745-143">For example, if the property is declared `Friend`, you can declare the `Set` procedure `Private`, but not `Public`.</span></span>  
  
     <span data-ttu-id="bb745-144">속성을 정의 하는 경우 `WriteOnly` 프로시저는 `Set` 전체 속성을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="bb745-144">If you are defining a `WriteOnly` property, the `Set` procedure represents the entire property.</span></span> <span data-ttu-id="bb745-145">`Set`속성에 대해 두 개의 액세스 수준을 설정 하므로에 대해 다른 액세스 수준을 선언할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="bb745-145">You cannot declare a different access level for `Set`, because that would set two access levels for the property.</span></span>  
  
## <a name="behavior"></a><span data-ttu-id="bb745-146">동작</span><span class="sxs-lookup"><span data-stu-id="bb745-146">Behavior</span></span>  
  
- <span data-ttu-id="bb745-147">**속성 프로시저에서 반환**</span><span class="sxs-lookup"><span data-stu-id="bb745-147">**Returning from a Property Procedure.**</span></span> <span data-ttu-id="bb745-148">`Set`프로시저가 호출 코드로 반환 될 때 저장 되는 값을 제공 하는 문 다음에 실행이 계속 됩니다.</span><span class="sxs-lookup"><span data-stu-id="bb745-148">When the `Set` procedure returns to the calling code, execution continues following the statement that provided the value to be stored.</span></span>  
  
     <span data-ttu-id="bb745-149">`Set` 속성 프로시저는 [Return 문](return-statement.md) 또는 [Exit 문](exit-statement.md)중 하나를 사용 하 여를 반환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bb745-149">`Set` property procedures can return using either the [Return Statement](return-statement.md) or the [Exit Statement](exit-statement.md).</span></span>  
  
     <span data-ttu-id="bb745-150">`Exit Property`및 `Return` 문을 실행 하면 속성 프로시저에서 즉시 종료 됩니다.</span><span class="sxs-lookup"><span data-stu-id="bb745-150">The `Exit Property` and `Return` statements cause an immediate exit from a property procedure.</span></span> <span data-ttu-id="bb745-151">프로시저의 모든 위치에는 개수와 `Exit Property` `Return` 문이 모두 표시 될 수 있으며 `Exit Property` 문과 문을 혼합할 수 있습니다 `Return` .</span><span class="sxs-lookup"><span data-stu-id="bb745-151">Any number of `Exit Property` and `Return` statements can appear anywhere in the procedure, and you can mix `Exit Property` and `Return` statements.</span></span>  
  
## <a name="example"></a><span data-ttu-id="bb745-152">예제</span><span class="sxs-lookup"><span data-stu-id="bb745-152">Example</span></span>  

 <span data-ttu-id="bb745-153">다음 예에서는 문을 사용 하 여 `Set` 속성의 값을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="bb745-153">The following example uses the `Set` statement to set the value of a property.</span></span>  
  
 [!code-vb[VbVbalrStatements#55](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#55)]  
  
## <a name="see-also"></a><span data-ttu-id="bb745-154">참고 항목</span><span class="sxs-lookup"><span data-stu-id="bb745-154">See also</span></span>

- [<span data-ttu-id="bb745-155">Get 문</span><span class="sxs-lookup"><span data-stu-id="bb745-155">Get Statement</span></span>](get-statement.md)
- [<span data-ttu-id="bb745-156">Property Statement</span><span class="sxs-lookup"><span data-stu-id="bb745-156">Property Statement</span></span>](property-statement.md)
- [<span data-ttu-id="bb745-157">Sub 문</span><span class="sxs-lookup"><span data-stu-id="bb745-157">Sub Statement</span></span>](sub-statement.md)
- [<span data-ttu-id="bb745-158">속성 프로시저</span><span class="sxs-lookup"><span data-stu-id="bb745-158">Property Procedures</span></span>](../../programming-guide/language-features/procedures/property-procedures.md)
