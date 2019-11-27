---
title: Get 문
ms.date: 07/20/2015
f1_keywords:
- vb.Get
helpviewer_keywords:
- Get statement [Visual Basic], syntax
- Get statement [Visual Basic]
- properties [Visual Basic], read-only
- read-only properties
- Get keyword [Visual Basic]
- property procedures [Visual Basic], Get statements
ms.assetid: 56b05cdc-bd64-4dfd-bb12-824eacec6f94
ms.openlocfilehash: 9560faf90d531c32f104dbd053a7c1f5584cfb1b
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/22/2019
ms.locfileid: "74351180"
---
# <a name="get-statement"></a><span data-ttu-id="d7842-102">Get 문</span><span class="sxs-lookup"><span data-stu-id="d7842-102">Get Statement</span></span>
<span data-ttu-id="d7842-103">속성의 값을 검색 하는 데 사용 되는 `Get` 속성 프로시저를 선언 합니다.</span><span class="sxs-lookup"><span data-stu-id="d7842-103">Declares a `Get` property procedure used to retrieve the value of a property.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d7842-104">구문</span><span class="sxs-lookup"><span data-stu-id="d7842-104">Syntax</span></span>  
  
```vb  
[ <attributelist> ] [ accessmodifier ] Get()  
    [ statements ]  
End Get  
```  
  
## <a name="parts"></a><span data-ttu-id="d7842-105">요소</span><span class="sxs-lookup"><span data-stu-id="d7842-105">Parts</span></span>  
  
|<span data-ttu-id="d7842-106">용어</span><span class="sxs-lookup"><span data-stu-id="d7842-106">Term</span></span>|<span data-ttu-id="d7842-107">정의</span><span class="sxs-lookup"><span data-stu-id="d7842-107">Definition</span></span>|  
|---|---|  
|`attributelist`|<span data-ttu-id="d7842-108">(선택 사항)</span><span class="sxs-lookup"><span data-stu-id="d7842-108">Optional.</span></span> <span data-ttu-id="d7842-109">[특성 목록](../../../visual-basic/language-reference/statements/attribute-list.md)을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="d7842-109">See [Attribute List](../../../visual-basic/language-reference/statements/attribute-list.md).</span></span>|  
|`accessmodifier`|<span data-ttu-id="d7842-110">이 속성의 `Get` 및 `Set` 문 중 최대 하나에 대해 선택적입니다.</span><span class="sxs-lookup"><span data-stu-id="d7842-110">Optional on at most one of the `Get` and `Set` statements in this property.</span></span> <span data-ttu-id="d7842-111">다음 중 하나일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d7842-111">Can be one of the following:</span></span><br /><br /> <span data-ttu-id="d7842-112">-   [보호](../../../visual-basic/language-reference/modifiers/protected.md) 됨</span><span class="sxs-lookup"><span data-stu-id="d7842-112">-   [Protected](../../../visual-basic/language-reference/modifiers/protected.md)</span></span><br /><span data-ttu-id="d7842-113">-   [Friend](../../../visual-basic/language-reference/modifiers/friend.md)</span><span class="sxs-lookup"><span data-stu-id="d7842-113">-   [Friend](../../../visual-basic/language-reference/modifiers/friend.md)</span></span><br /><span data-ttu-id="d7842-114">-   [개인](../../../visual-basic/language-reference/modifiers/private.md)</span><span class="sxs-lookup"><span data-stu-id="d7842-114">-   [Private](../../../visual-basic/language-reference/modifiers/private.md)</span></span><br />-   `Protected Friend`<br /><br /> <span data-ttu-id="d7842-115">[Access levels in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d7842-115">See [Access levels in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span></span>|  
|`statements`|<span data-ttu-id="d7842-116">(선택 사항)</span><span class="sxs-lookup"><span data-stu-id="d7842-116">Optional.</span></span> <span data-ttu-id="d7842-117">`Get` 속성 프로시저가 호출 될 때 실행 되는 하나 이상의 문입니다.</span><span class="sxs-lookup"><span data-stu-id="d7842-117">One or more statements that run when the `Get` property procedure is called.</span></span>|  
|`End Get`|<span data-ttu-id="d7842-118">필수입니다.</span><span class="sxs-lookup"><span data-stu-id="d7842-118">Required.</span></span> <span data-ttu-id="d7842-119">`Get` 속성 프로시저의 정의를 종료 합니다.</span><span class="sxs-lookup"><span data-stu-id="d7842-119">Terminates the definition of the `Get` property procedure.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d7842-120">주의</span><span class="sxs-lookup"><span data-stu-id="d7842-120">Remarks</span></span>  
 <span data-ttu-id="d7842-121">속성이 `WriteOnly`로 표시 되지 않은 경우 모든 속성에는 `Get` 속성 프로시저가 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d7842-121">Every property must have a `Get` property procedure unless the property is marked `WriteOnly`.</span></span> <span data-ttu-id="d7842-122">`Get` 프로시저는 속성의 현재 값을 반환 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d7842-122">The `Get` procedure is used to return the current value of the property.</span></span>  
  
 <span data-ttu-id="d7842-123">Visual Basic은 식에서 속성의 값을 요청할 때 속성의 `Get` 프로시저를 자동으로 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="d7842-123">Visual Basic automatically calls a property's `Get` procedure when an expression requests the property's value.</span></span>  
  
 <span data-ttu-id="d7842-124">속성 선언의 본문은 속성의 `Get` 및 [속성 문과](../../../visual-basic/language-reference/statements/property-statement.md) `End Property` 문 간의 `Set` 프로시저만 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d7842-124">The body of the property declaration can contain only the property's `Get` and `Set` procedures between the [Property Statement](../../../visual-basic/language-reference/statements/property-statement.md) and the `End Property` statement.</span></span> <span data-ttu-id="d7842-125">이러한 프로시저 이외의 항목은 저장할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d7842-125">It cannot store anything other than those procedures.</span></span> <span data-ttu-id="d7842-126">특히 속성의 현재 값을 저장할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d7842-126">In particular, it cannot store the property's current value.</span></span> <span data-ttu-id="d7842-127">속성 프로시저 중 하나에 저장 하는 경우 다른 속성 프로시저에서 액세스할 수 없기 때문에이 값을 속성 외부에 저장 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d7842-127">You must store this value outside the property, because if you store it inside either of the property procedures, the other property procedure cannot access it.</span></span> <span data-ttu-id="d7842-128">일반적인 방법은 속성과 같은 수준에서 선언 된 [전용](../../../visual-basic/language-reference/modifiers/private.md) 변수에 값을 저장 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="d7842-128">The usual approach is to store the value in a [Private](../../../visual-basic/language-reference/modifiers/private.md) variable declared at the same level as the property.</span></span> <span data-ttu-id="d7842-129">속성이 적용 되는 속성 내에 `Get` 프로시저를 정의 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d7842-129">You must define a `Get` procedure inside the property to which it applies.</span></span>  
  
 <span data-ttu-id="d7842-130">`Get` 프로시저는 `Get` 문에서 `accessmodifier`를 사용 하지 않는 경우 포함 하는 속성의 액세스 수준으로 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d7842-130">The `Get` procedure defaults to the access level of its containing property unless you use `accessmodifier` in the `Get` statement.</span></span>  
  
## <a name="rules"></a><span data-ttu-id="d7842-131">규칙</span><span class="sxs-lookup"><span data-stu-id="d7842-131">Rules</span></span>  
  
- <span data-ttu-id="d7842-132">**혼합 액세스 수준.**</span><span class="sxs-lookup"><span data-stu-id="d7842-132">**Mixed Access Levels.**</span></span> <span data-ttu-id="d7842-133">읽기/쓰기 속성을 정의 하는 경우 필요에 따라 `Get` 또는 `Set` 프로시저에 대해 다른 액세스 수준을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d7842-133">If you are defining a read-write property, you can optionally specify a different access level for either the `Get` or the `Set` procedure, but not both.</span></span> <span data-ttu-id="d7842-134">이 작업을 수행 하는 경우 프로시저 액세스 수준이 속성의 액세스 수준 보다 더 제한적 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d7842-134">If you do this, the procedure access level must be more restrictive than the property's access level.</span></span> <span data-ttu-id="d7842-135">예를 들어 속성을 `Friend`선언 하는 경우 `Get` 프로시저 `Private`선언할 수 있지만 `Public`는 선언할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d7842-135">For example, if the property is declared `Friend`, you can declare the `Get` procedure `Private`, but not `Public`.</span></span>  
  
     <span data-ttu-id="d7842-136">`ReadOnly` 속성을 정의 하는 경우 `Get` 프로시저는 전체 속성을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="d7842-136">If you are defining a `ReadOnly` property, the `Get` procedure represents the entire property.</span></span> <span data-ttu-id="d7842-137">속성에 대해 두 개의 액세스 수준을 설정 하므로 `Get`에 대해 다른 액세스 수준을 선언할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d7842-137">You cannot declare a different access level for `Get`, because that would set two access levels for the property.</span></span>  
  
- <span data-ttu-id="d7842-138">**반환 형식입니다.**</span><span class="sxs-lookup"><span data-stu-id="d7842-138">**Return Type.**</span></span> <span data-ttu-id="d7842-139">[Property 문은](../../../visual-basic/language-reference/statements/property-statement.md) 반환 하는 값의 데이터 형식을 선언할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d7842-139">The [Property Statement](../../../visual-basic/language-reference/statements/property-statement.md) can declare the data type of the value it returns.</span></span> <span data-ttu-id="d7842-140">`Get` 프로시저는 해당 데이터 형식을 자동으로 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="d7842-140">The `Get` procedure automatically returns that data type.</span></span> <span data-ttu-id="d7842-141">모든 데이터 형식 또는 열거형, 구조체, 클래스 또는 인터페이스의 이름을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d7842-141">You can specify any data type or the name of an enumeration, structure, class, or interface.</span></span>  
  
     <span data-ttu-id="d7842-142">`Property` 문에서 `returntype`를 지정 하지 않는 경우 프로시저는 `Object`반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="d7842-142">If the `Property` statement does not specify `returntype`, the procedure returns `Object`.</span></span>  
  
## <a name="behavior"></a><span data-ttu-id="d7842-143">동작</span><span class="sxs-lookup"><span data-stu-id="d7842-143">Behavior</span></span>  
  
- <span data-ttu-id="d7842-144">**프로시저에서 반환**</span><span class="sxs-lookup"><span data-stu-id="d7842-144">**Returning from a Procedure.**</span></span> <span data-ttu-id="d7842-145">`Get` 프로시저가 호출 코드로 반환 되 면 속성 값을 요청한 문 내에서 실행이 계속 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d7842-145">When the `Get` procedure returns to the calling code, execution continues within the statement that requested the property value.</span></span>  
  
     <span data-ttu-id="d7842-146">`Get` 속성 프로시저는 [Return 문](../../../visual-basic/language-reference/statements/return-statement.md) 중 하나를 사용 하거나 반환 값을 속성 이름에 할당 하 여 값을 반환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d7842-146">`Get` property procedures can return a value using either the [Return Statement](../../../visual-basic/language-reference/statements/return-statement.md) or by assigning the return value to the property name.</span></span> <span data-ttu-id="d7842-147">자세한 내용은 [함수 문의](../../../visual-basic/language-reference/statements/function-statement.md)"반환 값"을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="d7842-147">For more information, see "Return Value" in [Function Statement](../../../visual-basic/language-reference/statements/function-statement.md).</span></span>  
  
     <span data-ttu-id="d7842-148">`Exit Property` 및 `Return` 문은 속성 프로시저에서 즉시 종료를 발생 시킵니다.</span><span class="sxs-lookup"><span data-stu-id="d7842-148">The `Exit Property` and `Return` statements cause an immediate exit from a property procedure.</span></span> <span data-ttu-id="d7842-149">프로시저의 어디에 든 많은 `Exit Property` 및 `Return` 문이 표시 될 수 있으며 `Exit Property` 문과 `Return` 문을 혼합할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d7842-149">Any number of `Exit Property` and `Return` statements can appear anywhere in the procedure, and you can mix `Exit Property` and `Return` statements.</span></span>  
  
- <span data-ttu-id="d7842-150">**반환 값입니다.**</span><span class="sxs-lookup"><span data-stu-id="d7842-150">**Return Value.**</span></span> <span data-ttu-id="d7842-151">`Get` 프로시저에서 값을 반환 하려면 속성 이름에 값을 할당 하거나 [Return 문에](../../../visual-basic/language-reference/statements/return-statement.md)값을 포함 하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d7842-151">To return a value from a `Get` procedure, you can either assign the value to the property name or include it in a [Return Statement](../../../visual-basic/language-reference/statements/return-statement.md).</span></span> <span data-ttu-id="d7842-152">`Return` 문은 `Get` 프로시저 반환 값을 동시에 할당 하 고 프로시저를 종료 합니다.</span><span class="sxs-lookup"><span data-stu-id="d7842-152">The `Return` statement simultaneously assigns the `Get` procedure return value and exits the procedure.</span></span>  
  
     <span data-ttu-id="d7842-153">속성 이름에 값을 할당 하지 않고 `Exit Property`를 사용 하는 경우 `Get` 프로시저는 속성의 데이터 형식에 대 한 기본값을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="d7842-153">If you use `Exit Property` without assigning a value to the property name, the `Get` procedure returns the default value for the property's data type.</span></span> <span data-ttu-id="d7842-154">자세한 내용은 [함수 문의](../../../visual-basic/language-reference/statements/function-statement.md)"반환 값"을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="d7842-154">For more information, see "Return Value" in [Function Statement](../../../visual-basic/language-reference/statements/function-statement.md).</span></span>  
  
     <span data-ttu-id="d7842-155">다음 예제에서는 읽기 전용 속성 `quoteForTheDay` `quoteValue`개인 변수에 저장 된 값을 반환할 수 있는 두 가지 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="d7842-155">The following example illustrates two ways the read-only property `quoteForTheDay` can return the value held in the private variable `quoteValue`.</span></span>  
  
     [!code-vb[VbVbalrStatements#27](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#27)]  
  
     [!code-vb[VbVbalrStatements#28](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#28)]  
  
     [!code-vb[VbVbalrStatements#29](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#29)]  
  
## <a name="example"></a><span data-ttu-id="d7842-156">예제</span><span class="sxs-lookup"><span data-stu-id="d7842-156">Example</span></span>  
 <span data-ttu-id="d7842-157">다음 예에서는 `Get` 문을 사용 하 여 속성의 값을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="d7842-157">The following example uses the `Get` statement to return the value of a property.</span></span>  
  
 [!code-vb[VbVbalrStatements#30](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#30)]  
  
## <a name="see-also"></a><span data-ttu-id="d7842-158">참고 항목</span><span class="sxs-lookup"><span data-stu-id="d7842-158">See also</span></span>

- [<span data-ttu-id="d7842-159">Set 문</span><span class="sxs-lookup"><span data-stu-id="d7842-159">Set Statement</span></span>](../../../visual-basic/language-reference/statements/set-statement.md)
- [<span data-ttu-id="d7842-160">Property 문</span><span class="sxs-lookup"><span data-stu-id="d7842-160">Property Statement</span></span>](../../../visual-basic/language-reference/statements/property-statement.md)
- [<span data-ttu-id="d7842-161">Exit 문</span><span class="sxs-lookup"><span data-stu-id="d7842-161">Exit Statement</span></span>](../../../visual-basic/language-reference/statements/exit-statement.md)
- [<span data-ttu-id="d7842-162">개체 및 클래스</span><span class="sxs-lookup"><span data-stu-id="d7842-162">Objects and Classes</span></span>](../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)
- [<span data-ttu-id="d7842-163">연습: 클래스 정의</span><span class="sxs-lookup"><span data-stu-id="d7842-163">Walkthrough: Defining Classes</span></span>](../../../visual-basic/programming-guide/language-features/objects-and-classes/walkthrough-defining-classes.md)
