---
title: Set 문(Visual Basic)
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
ms.openlocfilehash: 0a8d95ffbabf03a0e6c9d88edb28c248b60f3252
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/02/2019
ms.locfileid: "58839082"
---
# <a name="set-statement-visual-basic"></a><span data-ttu-id="00d6d-102">Set 문(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="00d6d-102">Set Statement (Visual Basic)</span></span>
<span data-ttu-id="00d6d-103">선언 된 `Set` 속성 프로시저 속성에 값을 할당 하는 데 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="00d6d-103">Declares a `Set` property procedure used to assign a value to a property.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="00d6d-104">구문</span><span class="sxs-lookup"><span data-stu-id="00d6d-104">Syntax</span></span>  
  
```  
[ <attributelist> ] [ accessmodifier ] Set (ByVal value [ As datatype ])  
    [ statements ]  
End Set  
```  
  
## <a name="parts"></a><span data-ttu-id="00d6d-105">요소</span><span class="sxs-lookup"><span data-stu-id="00d6d-105">Parts</span></span>  
 `attributelist`  
 <span data-ttu-id="00d6d-106">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="00d6d-106">Optional.</span></span> <span data-ttu-id="00d6d-107">참조 [특성 목록](../../../visual-basic/language-reference/statements/attribute-list.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="00d6d-107">See [Attribute List](../../../visual-basic/language-reference/statements/attribute-list.md).</span></span>  
  
 `accessmodifier`  
 <span data-ttu-id="00d6d-108">옵션 중 하나에 `Get` 및 `Set` 이 속성에는 문.</span><span class="sxs-lookup"><span data-stu-id="00d6d-108">Optional on at most one of the `Get` and `Set` statements in this property.</span></span> <span data-ttu-id="00d6d-109">다음 중 하나일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="00d6d-109">Can be one of the following:</span></span>  
  
-   [<span data-ttu-id="00d6d-110">보호됨</span><span class="sxs-lookup"><span data-stu-id="00d6d-110">Protected</span></span>](../../../visual-basic/language-reference/modifiers/protected.md)  
  
-   [<span data-ttu-id="00d6d-111">Friend</span><span class="sxs-lookup"><span data-stu-id="00d6d-111">Friend</span></span>](../../../visual-basic/language-reference/modifiers/friend.md)  
  
-   [<span data-ttu-id="00d6d-112">전용</span><span class="sxs-lookup"><span data-stu-id="00d6d-112">Private</span></span>](../../../visual-basic/language-reference/modifiers/private.md)  
  
-   `Protected Friend`  
  
 <span data-ttu-id="00d6d-113">[Access levels in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="00d6d-113">See [Access levels in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span></span>  
  
 `value`  
 <span data-ttu-id="00d6d-114">필수 요소.</span><span class="sxs-lookup"><span data-stu-id="00d6d-114">Required.</span></span> <span data-ttu-id="00d6d-115">속성에 대 한 새 값을 포함 하는 매개 변수입니다.</span><span class="sxs-lookup"><span data-stu-id="00d6d-115">Parameter containing the new value for the property.</span></span>  
  
 `datatype`  
 <span data-ttu-id="00d6d-116">필요한 경우 `Option Strict` 는 `On`합니다.</span><span class="sxs-lookup"><span data-stu-id="00d6d-116">Required if `Option Strict` is `On`.</span></span> <span data-ttu-id="00d6d-117">데이터 형식의 `value` 매개 변수입니다.</span><span class="sxs-lookup"><span data-stu-id="00d6d-117">Data type of the `value` parameter.</span></span> <span data-ttu-id="00d6d-118">속성의 데이터 형식으로 지정한 데이터 형식과 같아야 여기서이 `Set` 정보가 선언 됩니다.</span><span class="sxs-lookup"><span data-stu-id="00d6d-118">The data type specified must be the same as the data type of the property where this `Set` statement is declared.</span></span>  
  
 `statements`  
 <span data-ttu-id="00d6d-119">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="00d6d-119">Optional.</span></span> <span data-ttu-id="00d6d-120">될 때 실행 되는 하나 이상의 문을 `Set` 속성 프로시저를 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="00d6d-120">One or more statements that run when the `Set` property procedure is called.</span></span>  
  
 `End Set`  
 <span data-ttu-id="00d6d-121">필수 요소.</span><span class="sxs-lookup"><span data-stu-id="00d6d-121">Required.</span></span> <span data-ttu-id="00d6d-122">정의 종료 합니다 `Set` 속성 프로시저입니다.</span><span class="sxs-lookup"><span data-stu-id="00d6d-122">Terminates the definition of the `Set` property procedure.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="00d6d-123">설명</span><span class="sxs-lookup"><span data-stu-id="00d6d-123">Remarks</span></span>  
 <span data-ttu-id="00d6d-124">모든 속성에 있어야 합니다는 `Set` 속성 프로시저 속성 표시 되어 있지 않으면 `ReadOnly`합니다.</span><span class="sxs-lookup"><span data-stu-id="00d6d-124">Every property must have a `Set` property procedure unless the property is marked `ReadOnly`.</span></span> <span data-ttu-id="00d6d-125">`Set` 방법을 사용 하는 속성의 값을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="00d6d-125">The `Set` procedure is used to set the value of the property.</span></span>  
  
 <span data-ttu-id="00d6d-126">Visual Basic로 속성을 자동으로 호출 `Set` 프로시저 대입문 속성에 저장할 수 있는 값을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="00d6d-126">Visual Basic automatically calls a property's `Set` procedure when an assignment statement provides a value to be stored in the property.</span></span>  
  
 <span data-ttu-id="00d6d-127">Visual Basic에 매개 변수를 전달 합니다 `Set` 속성을 할당 하는 동안 프로시저입니다.</span><span class="sxs-lookup"><span data-stu-id="00d6d-127">Visual Basic passes a parameter to the `Set` procedure during property assignments.</span></span> <span data-ttu-id="00d6d-128">매개 변수를 제공 하지 않는 경우 `Set`, 라는 암시적 매개 변수를 사용 하는 통합된 개발 환경 (IDE) `value`합니다.</span><span class="sxs-lookup"><span data-stu-id="00d6d-128">If you do not supply a parameter for `Set`, the integrated development environment (IDE) uses an implicit parameter named `value`.</span></span> <span data-ttu-id="00d6d-129">매개 변수 속성에 할당할 값을 보유 합니다.</span><span class="sxs-lookup"><span data-stu-id="00d6d-129">The parameter holds the value to be assigned to the property.</span></span> <span data-ttu-id="00d6d-130">일반적으로 개인 로컬 변수에이 값을 저장 하 고 반환할 때마다는 `Get` 프로시저를 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="00d6d-130">You typically store this value in a private local variable and return it whenever the `Get` procedure is called.</span></span>  
  
 <span data-ttu-id="00d6d-131">속성 선언의 본문에만 속성의 포함 될 수 있습니다 `Get` 하 고 `Set` 프로시저 간의 [Property 문](../../../visual-basic/language-reference/statements/property-statement.md) 및 `End Property` 문.</span><span class="sxs-lookup"><span data-stu-id="00d6d-131">The body of the property declaration can contain only the property's `Get` and `Set` procedures between the [Property Statement](../../../visual-basic/language-reference/statements/property-statement.md) and the `End Property` statement.</span></span> <span data-ttu-id="00d6d-132">이러한 프로시저 이외의 저장할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="00d6d-132">It cannot store anything other than those procedures.</span></span> <span data-ttu-id="00d6d-133">특히,이 속성의 현재 값을 저장할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="00d6d-133">In particular, it cannot store the property's current value.</span></span> <span data-ttu-id="00d6d-134">다른 속성 프로시저에서 액세스할 수 없으므로 속성 프로시저 중 어디에 저장 하는 경우에 외부 속성을이 값을 저장 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="00d6d-134">You must store this value outside the property, because if you store it inside either of the property procedures, the other property procedure cannot access it.</span></span> <span data-ttu-id="00d6d-135">에 값을 저장 하는 일반적인 방법입니다를 [개인](../../../visual-basic/language-reference/modifiers/private.md) 속성과 동일한 수준에서 선언 된 변수입니다.</span><span class="sxs-lookup"><span data-stu-id="00d6d-135">The usual approach is to store the value in a [Private](../../../visual-basic/language-reference/modifiers/private.md) variable declared at the same level as the property.</span></span> <span data-ttu-id="00d6d-136">정의 해야 합니다는 `Set` 적용 되는 속성 내의 프로시저입니다.</span><span class="sxs-lookup"><span data-stu-id="00d6d-136">You must define a `Set` procedure inside the property to which it applies.</span></span>  
  
 <span data-ttu-id="00d6d-137">합니다 `Set` 프로시저는 기본적으로 포함 하는 해당 속성의 액세스 수준을 사용 하지 않는 경우 `accessmodifier` 에 `Set` 문.</span><span class="sxs-lookup"><span data-stu-id="00d6d-137">The `Set` procedure defaults to the access level of its containing property unless you use `accessmodifier` in the `Set` statement.</span></span>  
  
## <a name="rules"></a><span data-ttu-id="00d6d-138">규칙</span><span class="sxs-lookup"><span data-stu-id="00d6d-138">Rules</span></span>  
  
-   <span data-ttu-id="00d6d-139">**혼합 된 액세스 수준입니다.**</span><span class="sxs-lookup"><span data-stu-id="00d6d-139">**Mixed Access Levels.**</span></span> <span data-ttu-id="00d6d-140">서로 다른 액세스 수준에 대 한 필요에 따라 지정할 수는 읽기 / 쓰기 속성을 정의 하는 경우는 `Get` 또는 `Set` 절차, 하지만 둘 다.</span><span class="sxs-lookup"><span data-stu-id="00d6d-140">If you are defining a read-write property, you can optionally specify a different access level for either the `Get` or the `Set` procedure, but not both.</span></span> <span data-ttu-id="00d6d-141">이 작업을 수행 하는 경우 프로시저 액세스 수준 속성의 액세스 수준 보다 더 제한적 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="00d6d-141">If you do this, the procedure access level must be more restrictive than the property's access level.</span></span> <span data-ttu-id="00d6d-142">예를 들어, 속성 선언 되 면 `Friend`를 선언할 수 있습니다 합니다 `Set` 프로시저 `Private`, 아닌 `Public`합니다.</span><span class="sxs-lookup"><span data-stu-id="00d6d-142">For example, if the property is declared `Friend`, you can declare the `Set` procedure `Private`, but not `Public`.</span></span>  
  
     <span data-ttu-id="00d6d-143">정의 하는 경우는 `WriteOnly` 속성을 `Set` 프로시저 전체 속성을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="00d6d-143">If you are defining a `WriteOnly` property, the `Set` procedure represents the entire property.</span></span> <span data-ttu-id="00d6d-144">선언할 수 없습니다는 서로 다른 액세스 수준 `Set`이므로 속성에 대 한 두 가지 액세스 수준이 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="00d6d-144">You cannot declare a different access level for `Set`, because that would set two access levels for the property.</span></span>  
  
## <a name="behavior"></a><span data-ttu-id="00d6d-145">동작</span><span class="sxs-lookup"><span data-stu-id="00d6d-145">Behavior</span></span>  
  
-   <span data-ttu-id="00d6d-146">**속성 프로시저에서 반환합니다.**</span><span class="sxs-lookup"><span data-stu-id="00d6d-146">**Returning from a Property Procedure.**</span></span> <span data-ttu-id="00d6d-147">경우는 `Set` 프로시저가 호출 코드에 반환 되 면 저장 될 값을 제공 하는 문을 계속 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="00d6d-147">When the `Set` procedure returns to the calling code, execution continues following the statement that provided the value to be stored.</span></span>  
  
     <span data-ttu-id="00d6d-148">`Set` 속성 프로시저 중 하나를 사용 하 여 반환할 수 있습니다 합니다 [Return 문이](../../../visual-basic/language-reference/statements/return-statement.md) 또는 [Exit 문을](../../../visual-basic/language-reference/statements/exit-statement.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="00d6d-148">`Set` property procedures can return using either the [Return Statement](../../../visual-basic/language-reference/statements/return-statement.md) or the [Exit Statement](../../../visual-basic/language-reference/statements/exit-statement.md).</span></span>  
  
     <span data-ttu-id="00d6d-149">합니다 `Exit Property` 및 `Return` 문은 속성 프로시저를 즉시 종료 합니다.</span><span class="sxs-lookup"><span data-stu-id="00d6d-149">The `Exit Property` and `Return` statements cause an immediate exit from a property procedure.</span></span> <span data-ttu-id="00d6d-150">임의 개수의 `Exit Property` 하 고 `Return` 문을 프로시저에서 아무 곳 이나 나타날 수 있으며 함께 사용할 수 있습니다 `Exit Property` 및 `Return` 문.</span><span class="sxs-lookup"><span data-stu-id="00d6d-150">Any number of `Exit Property` and `Return` statements can appear anywhere in the procedure, and you can mix `Exit Property` and `Return` statements.</span></span>  
  
## <a name="example"></a><span data-ttu-id="00d6d-151">예제</span><span class="sxs-lookup"><span data-stu-id="00d6d-151">Example</span></span>  
 <span data-ttu-id="00d6d-152">다음 예제에서는 `Set` 속성의 값을 설정 하는 문입니다.</span><span class="sxs-lookup"><span data-stu-id="00d6d-152">The following example uses the `Set` statement to set the value of a property.</span></span>  
  
 [!code-vb[VbVbalrStatements#55](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#55)]  
  
## <a name="see-also"></a><span data-ttu-id="00d6d-153">참고자료</span><span class="sxs-lookup"><span data-stu-id="00d6d-153">See also</span></span>

- [<span data-ttu-id="00d6d-154">Get 문</span><span class="sxs-lookup"><span data-stu-id="00d6d-154">Get Statement</span></span>](../../../visual-basic/language-reference/statements/get-statement.md)
- [<span data-ttu-id="00d6d-155">Property 문</span><span class="sxs-lookup"><span data-stu-id="00d6d-155">Property Statement</span></span>](../../../visual-basic/language-reference/statements/property-statement.md)
- [<span data-ttu-id="00d6d-156">Sub 문</span><span class="sxs-lookup"><span data-stu-id="00d6d-156">Sub Statement</span></span>](../../../visual-basic/language-reference/statements/sub-statement.md)
- [<span data-ttu-id="00d6d-157">속성 프로시저</span><span class="sxs-lookup"><span data-stu-id="00d6d-157">Property Procedures</span></span>](../../../visual-basic/programming-guide/language-features/procedures/property-procedures.md)
