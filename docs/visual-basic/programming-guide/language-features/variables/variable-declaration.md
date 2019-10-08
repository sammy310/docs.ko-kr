---
title: Visual Basic의 변수 선언
ms.date: 07/20/2015
helpviewer_keywords:
- variables [Visual Basic], declaring
- member variables [Visual Basic], declarations
- Dim statement [Visual Basic], variable declaration
- declaring variables [Visual Basic]
- variables [Visual Basic], scope
- variables [Visual Basic], data types
- data types [Visual Basic], variable declarations
- lifetime [Visual Basic], variables
- variables [Visual Basic], lifetime
- access levels [Visual Basic], variables
- scope [Visual Basic], declaration statements
- variables [Visual Basic], access level
- local variables [Visual Basic], declarations
- scope [Visual Basic], variables
ms.assetid: d8f10226-92b1-480f-9f53-df377b2d7e15
ms.openlocfilehash: 726347efc2e12100f7d89348a316037babc785e5
ms.sourcegitcommit: eff6adb61852369ab690f3f047818c90580e7eb1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/07/2019
ms.locfileid: "72003302"
---
# <a name="variable-declaration-in-visual-basic"></a><span data-ttu-id="13456-102">Visual Basic의 변수 선언</span><span class="sxs-lookup"><span data-stu-id="13456-102">Variable Declaration in Visual Basic</span></span>
<span data-ttu-id="13456-103">변수를 선언 하 여 해당 이름 및 특성을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="13456-103">You declare a variable to specify its name and characteristics.</span></span> <span data-ttu-id="13456-104">변수에 대 한 선언문은 [Dim 문](../../../../visual-basic/language-reference/statements/dim-statement.md)입니다.</span><span class="sxs-lookup"><span data-stu-id="13456-104">The declaration statement for variables is the [Dim Statement](../../../../visual-basic/language-reference/statements/dim-statement.md).</span></span> <span data-ttu-id="13456-105">해당 위치 및 내용에 따라 변수의 특징이 결정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="13456-105">Its location and contents determine the variable's characteristics.</span></span>  
  
 <span data-ttu-id="13456-106">변수 명명 규칙 및 고려 사항은 선언 된 [요소 이름](../../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="13456-106">For variable naming rules and considerations, see [Declared Element Names](../../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).</span></span>  
  
## <a name="declaration-levels"></a><span data-ttu-id="13456-107">선언 수준</span><span class="sxs-lookup"><span data-stu-id="13456-107">Declaration Levels</span></span>  
  
### <a name="local-and-member-variables"></a><span data-ttu-id="13456-108">지역 변수 및 멤버 변수</span><span class="sxs-lookup"><span data-stu-id="13456-108">Local and Member Variables</span></span>  
 <span data-ttu-id="13456-109">*지역 변수* 는 프로시저 내에서 선언 된 변수입니다.</span><span class="sxs-lookup"><span data-stu-id="13456-109">A *local variable* is one that is declared within a procedure.</span></span> <span data-ttu-id="13456-110">*멤버 변수* 는 Visual Basic 형식의 멤버입니다. 이 클래스는 모듈 수준에서 클래스, 구조체 또는 모듈 내에서 선언 되지만 해당 클래스, 구조체 또는 모듈 내부의 프로시저 내에서는 선언 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="13456-110">A *member variable* is a member of a Visual Basic type; it is declared at module level, inside a class, structure, or module, but not within any procedure internal to that class, structure, or module.</span></span>  
  
### <a name="shared-and-instance-variables"></a><span data-ttu-id="13456-111">공유 및 인스턴스 변수</span><span class="sxs-lookup"><span data-stu-id="13456-111">Shared and Instance Variables</span></span>  
 <span data-ttu-id="13456-112">클래스 또는 구조체에서 멤버 변수의 범주는 공유 여부에 따라 달라 집니다.</span><span class="sxs-lookup"><span data-stu-id="13456-112">In a class or structure, the category of a member variable depends on whether or not it is shared.</span></span> <span data-ttu-id="13456-113">[Shared](../../../../visual-basic/language-reference/modifiers/shared.md) 키워드를 사용 하 여 선언 된 경우 *공유 변수*이며, 클래스 또는 구조체의 모든 인스턴스 간에 공유 되는 단일 복사본에 존재 합니다.</span><span class="sxs-lookup"><span data-stu-id="13456-113">If it is declared with the [Shared](../../../../visual-basic/language-reference/modifiers/shared.md) keyword, it is a *shared variable*, and it exists in a single copy shared among all instances of the class or structure.</span></span>  
  
 <span data-ttu-id="13456-114">그렇지 않으면 *인스턴스 변수*이며, 클래스 또는 구조체의 각 인스턴스에 대해 별도의 복사본을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="13456-114">Otherwise it is an *instance variable*, and a separate copy of it is created for each instance of the class or structure.</span></span> <span data-ttu-id="13456-115">인스턴스 변수의 지정 된 복사본은 해당 복사본이 생성 된 클래스 또는 구조체의 인스턴스에만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="13456-115">A given copy of an instance variable is available only to the instance of the class or structure in which it was created.</span></span> <span data-ttu-id="13456-116">클래스 또는 구조체의 다른 인스턴스에 있는 인스턴스 변수의 복사본과는 독립적입니다.</span><span class="sxs-lookup"><span data-stu-id="13456-116">It is independent of a copy of the instance variable in any other instance of the class or structure.</span></span>  
  
## <a name="declaring-data-type"></a><span data-ttu-id="13456-117">데이터 형식 선언</span><span class="sxs-lookup"><span data-stu-id="13456-117">Declaring Data Type</span></span>  
 <span data-ttu-id="13456-118">선언문의 [As](../../../../visual-basic/language-reference/statements/as-clause.md) 절을 사용 하 여 선언 하는 변수의 데이터 형식 또는 개체 유형을 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="13456-118">The [As](../../../../visual-basic/language-reference/statements/as-clause.md) clause in the declaration statement allows you to define the data type or object type of the variable you are declaring.</span></span> <span data-ttu-id="13456-119">변수에 대해 다음 형식 중 하나를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="13456-119">You can specify any of the following types for a variable:</span></span>  
  
- <span data-ttu-id="13456-120">@No__t-0, `Long` 또는 `Decimal`와 같은 기본 데이터 형식</span><span class="sxs-lookup"><span data-stu-id="13456-120">An elementary data type, such as `Boolean`, `Long`, or `Decimal`</span></span>  
  
- <span data-ttu-id="13456-121">복합 데이터 형식 (예: 배열 또는 구조체)</span><span class="sxs-lookup"><span data-stu-id="13456-121">A composite data type, such as an array or structure</span></span>  
  
- <span data-ttu-id="13456-122">응용 프로그램 또는 다른 응용 프로그램에서 정의 된 개체 형식 또는 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="13456-122">An object type, or class, defined either in your application or in another application</span></span>  
  
- <span data-ttu-id="13456-123">@No__t-0 또는 <xref:System.Windows.Forms.TextBox>과 같은 .NET Framework 클래스</span><span class="sxs-lookup"><span data-stu-id="13456-123">A .NET Framework class, such as <xref:System.Windows.Forms.Label> or <xref:System.Windows.Forms.TextBox></span></span>  
  
- <span data-ttu-id="13456-124">@No__t-0 또는 <xref:System.IDisposable>과 같은 인터페이스 형식</span><span class="sxs-lookup"><span data-stu-id="13456-124">An interface type, such as <xref:System.IComparable> or <xref:System.IDisposable></span></span>  
  
 <span data-ttu-id="13456-125">데이터 형식을 반복할 필요 없이 하나의 문에서 여러 변수를 선언할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="13456-125">You can declare several variables in one statement without having to repeat the data type.</span></span> <span data-ttu-id="13456-126">다음 문에서는 변수 `i`, `j`, `k` `Integer`, `l`, `m`, `x`, `Single`, 로 선언 됩니다.</span><span class="sxs-lookup"><span data-stu-id="13456-126">In the following statements, the variables `i`, `j`, and `k` are declared as type `Integer`, `l` and `m` as `Long`, and `x` and `y` as `Single`:</span></span>  
  
```vb  
Dim i, j, k As Integer  
' All three variables in the preceding statement are declared as Integer.  
Dim l, m As Long, x, y As Single  
' In the preceding statement, l and m are Long, x and y are Single.  
```  
  
 <span data-ttu-id="13456-127">데이터 형식에 대 한 자세한 내용은 [데이터 형식](../../../../visual-basic/programming-guide/language-features/data-types/index.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="13456-127">For more information on data types, see [Data Types](../../../../visual-basic/programming-guide/language-features/data-types/index.md).</span></span> <span data-ttu-id="13456-128">개체에 대 한 자세한 내용은 [개체 및 클래스](../../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md) 및 [구성 요소를 사용한 프로그래밍](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/0ffkdtkf(v=vs.120))을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="13456-128">For more information on objects, see [Objects and Classes](../../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md) and [Programming with Components](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/0ffkdtkf(v=vs.120)).</span></span>  
  
## <a name="local-type-inference"></a><span data-ttu-id="13456-129">지역 형식 유추</span><span class="sxs-lookup"><span data-stu-id="13456-129">Local Type Inference</span></span>  
 <span data-ttu-id="13456-130">*형식 유추* 는 `As` 절 없이 선언 된 지역 변수의 데이터 형식을 결정 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="13456-130">*Type inference* is used to determine the data types of local variables declared without an `As` clause.</span></span> <span data-ttu-id="13456-131">컴파일러는 초기화 식의 형식에서 변수 형식을 유추 합니다.</span><span class="sxs-lookup"><span data-stu-id="13456-131">The compiler infers the type of the variable from the type of the initialization expression.</span></span> <span data-ttu-id="13456-132">이렇게 하면 명시적으로 형식을 명시 하지 않고도 변수를 선언할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="13456-132">This enables you to declare variables without explicitly stating a type.</span></span> <span data-ttu-id="13456-133">다음 예제에서는 `num1`과 `num2` 모두 정수로 강력 하 게 형식화 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="13456-133">In the following example, both `num1` and `num2` are strongly typed as integers.</span></span>  
  
 [!code-vb[VbVbalrTypeInference#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrTypeInference/VB/Class1.vb#1)]  
  
 <span data-ttu-id="13456-134">로컬 형식 유추를 사용 하려는 경우 `Option Infer`을 `On`로 설정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="13456-134">If you want to use local type inference, `Option Infer` must be set to `On`.</span></span> <span data-ttu-id="13456-135">자세한 내용은 [지역 형식 유추](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md) 및 [Option Infer 문](../../../../visual-basic/language-reference/statements/option-infer-statement.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="13456-135">For more information, see [Local Type Inference](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md) and [Option Infer Statement](../../../../visual-basic/language-reference/statements/option-infer-statement.md).</span></span>  
  
## <a name="characteristics-of-declared-variables"></a><span data-ttu-id="13456-136">선언 된 변수의 특성</span><span class="sxs-lookup"><span data-stu-id="13456-136">Characteristics of Declared Variables</span></span>  
 <span data-ttu-id="13456-137">변수의 *수명은* 이를 사용할 수 있는 기간입니다.</span><span class="sxs-lookup"><span data-stu-id="13456-137">The *lifetime* of a variable is the period of time during which it is available for use.</span></span> <span data-ttu-id="13456-138">일반적으로 변수는 해당 변수를 선언 하는 요소 (예: 프로시저 또는 클래스)가 계속 존재 하는 동안 존재 합니다.</span><span class="sxs-lookup"><span data-stu-id="13456-138">In general, a variable exists as long as the element that declares it (such as a procedure or class) continues to exist.</span></span> <span data-ttu-id="13456-139">변수가 포함 하는 요소의 수명을 초과 하 여 기존에 계속할 필요가 없으면 선언에서 특별 한 작업을 수행할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="13456-139">If the variable does not need to continue existing beyond the lifetime of its containing element, you do not need to do anything special in the declaration.</span></span> <span data-ttu-id="13456-140">변수가 포함 하는 요소 보다 더 오래 지속 되어야 하는 경우 `Static` 또는 `Shared` 키워드를 `Dim` 문에 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="13456-140">If the variable needs to continue to exist longer than its containing element, you can include the `Static` or `Shared` keyword in its `Dim` statement.</span></span> <span data-ttu-id="13456-141">자세한 내용은 [Visual Basic 수명](../../../../visual-basic/programming-guide/language-features/declared-elements/lifetime.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="13456-141">For more information, see [Lifetime in Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/lifetime.md).</span></span>  
  
 <span data-ttu-id="13456-142">변수의 *범위* 는 이름을 한정 하지 않고 참조할 수 있는 모든 코드 집합입니다.</span><span class="sxs-lookup"><span data-stu-id="13456-142">The *scope* of a variable is the set of all code that can refer to it without qualifying its name.</span></span> <span data-ttu-id="13456-143">변수의 범위는 선언 된 위치에 따라 결정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="13456-143">A variable's scope is determined by where it is declared.</span></span> <span data-ttu-id="13456-144">지정 된 지역에 있는 코드는 해당 영역에 정의 된 변수를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="13456-144">Code located in a given region can use the variables defined in that region without having to qualify their names.</span></span> <span data-ttu-id="13456-145">자세한 내용은 [Scope in Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/scope.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="13456-145">For more information, see [Scope in Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/scope.md).</span></span>  
  
 <span data-ttu-id="13456-146">변수의 *액세스 수준은* 액세스 권한이 있는 코드의 범위입니다.</span><span class="sxs-lookup"><span data-stu-id="13456-146">A variable's *access level* is the extent of code that has permission to access it.</span></span> <span data-ttu-id="13456-147">이는 `Dim` 문에서 사용 하는 액세스 한정자 (예: [공용](../../../../visual-basic/language-reference/modifiers/public.md) 또는 [개인](../../../../visual-basic/language-reference/modifiers/private.md))에 의해 결정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="13456-147">This is determined by the access modifier (such as [Public](../../../../visual-basic/language-reference/modifiers/public.md) or [Private](../../../../visual-basic/language-reference/modifiers/private.md)) that you use in the `Dim` statement.</span></span> <span data-ttu-id="13456-148">자세한 내용은 [Visual Basic의 액세스 수준](../../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="13456-148">For more information, see [Access levels in Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="13456-149">참조</span><span class="sxs-lookup"><span data-stu-id="13456-149">See also</span></span>

- <span data-ttu-id="13456-150">[방법: 새 변수 @ no__t-0 만들기</span><span class="sxs-lookup"><span data-stu-id="13456-150">[How to: Create a New Variable](../../../../visual-basic/programming-guide/language-features/variables/how-to-create-a-new-variable.md)</span></span>
- <span data-ttu-id="13456-151">[방법: 변수 내/외부로 데이터 이동 @ no__t-0</span><span class="sxs-lookup"><span data-stu-id="13456-151">[How to: Move Data Into and Out of a Variable](../../../../visual-basic/programming-guide/language-features/variables/how-to-move-data-into-and-out-of-a-variable.md)</span></span>
- [<span data-ttu-id="13456-152">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="13456-152">Data Types</span></span>](../../../../visual-basic/language-reference/data-types/index.md)
- [<span data-ttu-id="13456-153">보호됨</span><span class="sxs-lookup"><span data-stu-id="13456-153">Protected</span></span>](../../../../visual-basic/language-reference/modifiers/protected.md)
- [<span data-ttu-id="13456-154">Friend</span><span class="sxs-lookup"><span data-stu-id="13456-154">Friend</span></span>](../../../../visual-basic/language-reference/modifiers/friend.md)
- [<span data-ttu-id="13456-155">정적</span><span class="sxs-lookup"><span data-stu-id="13456-155">Static</span></span>](../../../../visual-basic/language-reference/modifiers/static.md)
- [<span data-ttu-id="13456-156">선언 요소의 특징</span><span class="sxs-lookup"><span data-stu-id="13456-156">Declared Element Characteristics</span></span>](../../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-characteristics.md)
- [<span data-ttu-id="13456-157">지역 형식 유추</span><span class="sxs-lookup"><span data-stu-id="13456-157">Local Type Inference</span></span>](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)
- [<span data-ttu-id="13456-158">Option Infer 문</span><span class="sxs-lookup"><span data-stu-id="13456-158">Option Infer Statement</span></span>](../../../../visual-basic/language-reference/statements/option-infer-statement.md)
