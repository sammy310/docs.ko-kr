---
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
ms.openlocfilehash: 75ad6d87f1785fea13a282d953f117c9c234e203
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/22/2019
ms.locfileid: "74349561"
---
# <a name="set-statement-visual-basic"></a><span data-ttu-id="ca78f-102">Set 문(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="ca78f-102">Set Statement (Visual Basic)</span></span>
<span data-ttu-id="ca78f-103">속성에 값을 할당 하는 데 사용 되는 `Set` 속성 프로시저를 선언 합니다.</span><span class="sxs-lookup"><span data-stu-id="ca78f-103">Declares a `Set` property procedure used to assign a value to a property.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ca78f-104">구문</span><span class="sxs-lookup"><span data-stu-id="ca78f-104">Syntax</span></span>  
  
```vb  
[ <attributelist> ] [ accessmodifier ] Set (ByVal value [ As datatype ])  
    [ statements ]  
End Set  
```  
  
## <a name="parts"></a><span data-ttu-id="ca78f-105">요소</span><span class="sxs-lookup"><span data-stu-id="ca78f-105">Parts</span></span>  
 `attributelist`  
 <span data-ttu-id="ca78f-106">(선택 사항)</span><span class="sxs-lookup"><span data-stu-id="ca78f-106">Optional.</span></span> <span data-ttu-id="ca78f-107">[특성 목록](../../../visual-basic/language-reference/statements/attribute-list.md)을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="ca78f-107">See [Attribute List](../../../visual-basic/language-reference/statements/attribute-list.md).</span></span>  
  
 `accessmodifier`  
 <span data-ttu-id="ca78f-108">이 속성의 `Get` 및 `Set` 문 중 최대 하나에 대해 선택적입니다.</span><span class="sxs-lookup"><span data-stu-id="ca78f-108">Optional on at most one of the `Get` and `Set` statements in this property.</span></span> <span data-ttu-id="ca78f-109">다음 중 하나일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ca78f-109">Can be one of the following:</span></span>  
  
- [<span data-ttu-id="ca78f-110">Protected</span><span class="sxs-lookup"><span data-stu-id="ca78f-110">Protected</span></span>](../../../visual-basic/language-reference/modifiers/protected.md)  
  
- [<span data-ttu-id="ca78f-111">Friend</span><span class="sxs-lookup"><span data-stu-id="ca78f-111">Friend</span></span>](../../../visual-basic/language-reference/modifiers/friend.md)  
  
- [<span data-ttu-id="ca78f-112">Private</span><span class="sxs-lookup"><span data-stu-id="ca78f-112">Private</span></span>](../../../visual-basic/language-reference/modifiers/private.md)  
  
- `Protected Friend`  
  
 <span data-ttu-id="ca78f-113">[Access levels in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ca78f-113">See [Access levels in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span></span>  
  
 `value`  
 <span data-ttu-id="ca78f-114">필수입니다.</span><span class="sxs-lookup"><span data-stu-id="ca78f-114">Required.</span></span> <span data-ttu-id="ca78f-115">속성의 새 값을 포함 하는 매개 변수입니다.</span><span class="sxs-lookup"><span data-stu-id="ca78f-115">Parameter containing the new value for the property.</span></span>  
  
 `datatype`  
 <span data-ttu-id="ca78f-116">`Option Strict` `On`경우 필수입니다.</span><span class="sxs-lookup"><span data-stu-id="ca78f-116">Required if `Option Strict` is `On`.</span></span> <span data-ttu-id="ca78f-117">`value` 매개 변수의 데이터 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="ca78f-117">Data type of the `value` parameter.</span></span> <span data-ttu-id="ca78f-118">지정 된 데이터 형식은이 `Set` 문이 선언 된 속성의 데이터 형식과 동일 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ca78f-118">The data type specified must be the same as the data type of the property where this `Set` statement is declared.</span></span>  
  
 `statements`  
 <span data-ttu-id="ca78f-119">(선택 사항)</span><span class="sxs-lookup"><span data-stu-id="ca78f-119">Optional.</span></span> <span data-ttu-id="ca78f-120">`Set` 속성 프로시저가 호출 될 때 실행 되는 하나 이상의 문입니다.</span><span class="sxs-lookup"><span data-stu-id="ca78f-120">One or more statements that run when the `Set` property procedure is called.</span></span>  
  
 `End Set`  
 <span data-ttu-id="ca78f-121">필수입니다.</span><span class="sxs-lookup"><span data-stu-id="ca78f-121">Required.</span></span> <span data-ttu-id="ca78f-122">`Set` 속성 프로시저의 정의를 종료 합니다.</span><span class="sxs-lookup"><span data-stu-id="ca78f-122">Terminates the definition of the `Set` property procedure.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ca78f-123">주의</span><span class="sxs-lookup"><span data-stu-id="ca78f-123">Remarks</span></span>  
 <span data-ttu-id="ca78f-124">속성이 `ReadOnly`로 표시 되지 않은 경우 모든 속성에는 `Set` 속성 프로시저가 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ca78f-124">Every property must have a `Set` property procedure unless the property is marked `ReadOnly`.</span></span> <span data-ttu-id="ca78f-125">`Set` 프로시저는 속성의 값을 설정 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ca78f-125">The `Set` procedure is used to set the value of the property.</span></span>  
  
 <span data-ttu-id="ca78f-126">Visual Basic는 대입문이 속성에 저장 될 값을 제공 하는 경우 속성의 `Set` 프로시저를 자동으로 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="ca78f-126">Visual Basic automatically calls a property's `Set` procedure when an assignment statement provides a value to be stored in the property.</span></span>  
  
 <span data-ttu-id="ca78f-127">Visual Basic는 속성을 할당 하는 동안 매개 변수를 `Set` 프로시저에 전달 합니다.</span><span class="sxs-lookup"><span data-stu-id="ca78f-127">Visual Basic passes a parameter to the `Set` procedure during property assignments.</span></span> <span data-ttu-id="ca78f-128">`Set`에 대 한 매개 변수를 제공 하지 않으면 IDE (통합 개발 환경)에서 `value`라는 암시적 매개 변수를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="ca78f-128">If you do not supply a parameter for `Set`, the integrated development environment (IDE) uses an implicit parameter named `value`.</span></span> <span data-ttu-id="ca78f-129">매개 변수는 속성에 할당 되는 값을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="ca78f-129">The parameter holds the value to be assigned to the property.</span></span> <span data-ttu-id="ca78f-130">일반적으로이 값을 개인 지역 변수에 저장 하 고 `Get` 프로시저가 호출 될 때마다 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="ca78f-130">You typically store this value in a private local variable and return it whenever the `Get` procedure is called.</span></span>  
  
 <span data-ttu-id="ca78f-131">속성 선언의 본문은 속성의 `Get` 및 [속성 문과](../../../visual-basic/language-reference/statements/property-statement.md) `End Property` 문 간의 `Set` 프로시저만 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ca78f-131">The body of the property declaration can contain only the property's `Get` and `Set` procedures between the [Property Statement](../../../visual-basic/language-reference/statements/property-statement.md) and the `End Property` statement.</span></span> <span data-ttu-id="ca78f-132">이러한 프로시저 이외의 항목은 저장할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="ca78f-132">It cannot store anything other than those procedures.</span></span> <span data-ttu-id="ca78f-133">특히 속성의 현재 값을 저장할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="ca78f-133">In particular, it cannot store the property's current value.</span></span> <span data-ttu-id="ca78f-134">속성 프로시저 중 하나에 저장 하는 경우 다른 속성 프로시저에서 액세스할 수 없기 때문에이 값을 속성 외부에 저장 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ca78f-134">You must store this value outside the property, because if you store it inside either of the property procedures, the other property procedure cannot access it.</span></span> <span data-ttu-id="ca78f-135">일반적인 방법은 속성과 같은 수준에서 선언 된 [전용](../../../visual-basic/language-reference/modifiers/private.md) 변수에 값을 저장 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="ca78f-135">The usual approach is to store the value in a [Private](../../../visual-basic/language-reference/modifiers/private.md) variable declared at the same level as the property.</span></span> <span data-ttu-id="ca78f-136">속성이 적용 되는 속성 내에 `Set` 프로시저를 정의 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ca78f-136">You must define a `Set` procedure inside the property to which it applies.</span></span>  
  
 <span data-ttu-id="ca78f-137">`Set` 프로시저는 `Set` 문에서 `accessmodifier`를 사용 하지 않는 경우 포함 하는 속성의 액세스 수준으로 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ca78f-137">The `Set` procedure defaults to the access level of its containing property unless you use `accessmodifier` in the `Set` statement.</span></span>  
  
## <a name="rules"></a><span data-ttu-id="ca78f-138">규칙</span><span class="sxs-lookup"><span data-stu-id="ca78f-138">Rules</span></span>  
  
- <span data-ttu-id="ca78f-139">**혼합 액세스 수준.**</span><span class="sxs-lookup"><span data-stu-id="ca78f-139">**Mixed Access Levels.**</span></span> <span data-ttu-id="ca78f-140">읽기/쓰기 속성을 정의 하는 경우 필요에 따라 `Get` 또는 `Set` 프로시저에 대해 다른 액세스 수준을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ca78f-140">If you are defining a read-write property, you can optionally specify a different access level for either the `Get` or the `Set` procedure, but not both.</span></span> <span data-ttu-id="ca78f-141">이 작업을 수행 하는 경우 프로시저 액세스 수준이 속성의 액세스 수준 보다 더 제한적 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ca78f-141">If you do this, the procedure access level must be more restrictive than the property's access level.</span></span> <span data-ttu-id="ca78f-142">예를 들어 속성을 `Friend`선언 하는 경우 `Set` 프로시저 `Private`선언할 수 있지만 `Public`는 선언할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="ca78f-142">For example, if the property is declared `Friend`, you can declare the `Set` procedure `Private`, but not `Public`.</span></span>  
  
     <span data-ttu-id="ca78f-143">`WriteOnly` 속성을 정의 하는 경우 `Set` 프로시저는 전체 속성을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="ca78f-143">If you are defining a `WriteOnly` property, the `Set` procedure represents the entire property.</span></span> <span data-ttu-id="ca78f-144">속성에 대해 두 개의 액세스 수준을 설정 하므로 `Set`에 대해 다른 액세스 수준을 선언할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="ca78f-144">You cannot declare a different access level for `Set`, because that would set two access levels for the property.</span></span>  
  
## <a name="behavior"></a><span data-ttu-id="ca78f-145">동작</span><span class="sxs-lookup"><span data-stu-id="ca78f-145">Behavior</span></span>  
  
- <span data-ttu-id="ca78f-146">**속성 프로시저에서 반환**</span><span class="sxs-lookup"><span data-stu-id="ca78f-146">**Returning from a Property Procedure.**</span></span> <span data-ttu-id="ca78f-147">`Set` 프로시저가 호출 코드로 반환 되 면 저장 될 값을 제공한 문 다음에 실행이 계속 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ca78f-147">When the `Set` procedure returns to the calling code, execution continues following the statement that provided the value to be stored.</span></span>  
  
     <span data-ttu-id="ca78f-148">`Set` 속성 프로시저는 [Return 문](../../../visual-basic/language-reference/statements/return-statement.md) 또는 [Exit 문](../../../visual-basic/language-reference/statements/exit-statement.md)중 하나를 사용 하 여를 반환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ca78f-148">`Set` property procedures can return using either the [Return Statement](../../../visual-basic/language-reference/statements/return-statement.md) or the [Exit Statement](../../../visual-basic/language-reference/statements/exit-statement.md).</span></span>  
  
     <span data-ttu-id="ca78f-149">`Exit Property` 및 `Return` 문은 속성 프로시저에서 즉시 종료를 발생 시킵니다.</span><span class="sxs-lookup"><span data-stu-id="ca78f-149">The `Exit Property` and `Return` statements cause an immediate exit from a property procedure.</span></span> <span data-ttu-id="ca78f-150">프로시저의 어디에 든 많은 `Exit Property` 및 `Return` 문이 표시 될 수 있으며 `Exit Property` 문과 `Return` 문을 혼합할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ca78f-150">Any number of `Exit Property` and `Return` statements can appear anywhere in the procedure, and you can mix `Exit Property` and `Return` statements.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ca78f-151">예제</span><span class="sxs-lookup"><span data-stu-id="ca78f-151">Example</span></span>  
 <span data-ttu-id="ca78f-152">다음 예에서는 `Set` 문을 사용 하 여 속성의 값을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="ca78f-152">The following example uses the `Set` statement to set the value of a property.</span></span>  
  
 [!code-vb[VbVbalrStatements#55](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#55)]  
  
## <a name="see-also"></a><span data-ttu-id="ca78f-153">참고 항목</span><span class="sxs-lookup"><span data-stu-id="ca78f-153">See also</span></span>

- [<span data-ttu-id="ca78f-154">Get 문</span><span class="sxs-lookup"><span data-stu-id="ca78f-154">Get Statement</span></span>](../../../visual-basic/language-reference/statements/get-statement.md)
- [<span data-ttu-id="ca78f-155">Property 문</span><span class="sxs-lookup"><span data-stu-id="ca78f-155">Property Statement</span></span>](../../../visual-basic/language-reference/statements/property-statement.md)
- [<span data-ttu-id="ca78f-156">Sub 문</span><span class="sxs-lookup"><span data-stu-id="ca78f-156">Sub Statement</span></span>](../../../visual-basic/language-reference/statements/sub-statement.md)
- [<span data-ttu-id="ca78f-157">속성 프로시저</span><span class="sxs-lookup"><span data-stu-id="ca78f-157">Property Procedures</span></span>](../../../visual-basic/programming-guide/language-features/procedures/property-procedures.md)
