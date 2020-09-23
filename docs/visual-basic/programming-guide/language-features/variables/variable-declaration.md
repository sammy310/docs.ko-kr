---
title: 변수 선언
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
ms.openlocfilehash: 8d78509e1604fee4a151608f6166de6fc8ccfdaa
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/23/2020
ms.locfileid: "91080155"
---
# <a name="variable-declaration-in-visual-basic"></a><span data-ttu-id="acafe-102">Visual Basic의 변수 선언</span><span class="sxs-lookup"><span data-stu-id="acafe-102">Variable Declaration in Visual Basic</span></span>

<span data-ttu-id="acafe-103">변수를 선언 하 여 해당 이름 및 특성을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="acafe-103">You declare a variable to specify its name and characteristics.</span></span> <span data-ttu-id="acafe-104">변수에 대 한 선언문은 [Dim 문](../../../language-reference/statements/dim-statement.md)입니다.</span><span class="sxs-lookup"><span data-stu-id="acafe-104">The declaration statement for variables is the [Dim Statement](../../../language-reference/statements/dim-statement.md).</span></span> <span data-ttu-id="acafe-105">해당 위치 및 내용에 따라 변수의 특징이 결정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="acafe-105">Its location and contents determine the variable's characteristics.</span></span>  
  
 <span data-ttu-id="acafe-106">변수 명명 규칙 및 고려 사항은 선언 된 [요소 이름](../declared-elements/declared-element-names.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="acafe-106">For variable naming rules and considerations, see [Declared Element Names](../declared-elements/declared-element-names.md).</span></span>  
  
## <a name="declaration-levels"></a><span data-ttu-id="acafe-107">선언 수준</span><span class="sxs-lookup"><span data-stu-id="acafe-107">Declaration Levels</span></span>  
  
### <a name="local-and-member-variables"></a><span data-ttu-id="acafe-108">지역 변수 및 멤버 변수</span><span class="sxs-lookup"><span data-stu-id="acafe-108">Local and Member Variables</span></span>  

 <span data-ttu-id="acafe-109">*지역 변수* 는 프로시저 내에서 선언 된 변수입니다.</span><span class="sxs-lookup"><span data-stu-id="acafe-109">A *local variable* is one that is declared within a procedure.</span></span> <span data-ttu-id="acafe-110">*멤버 변수* 는 Visual Basic 형식의 멤버입니다. 이 클래스는 모듈 수준에서 클래스, 구조체 또는 모듈 내에서 선언 되지만 해당 클래스, 구조체 또는 모듈 내부의 프로시저 내에서는 선언 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="acafe-110">A *member variable* is a member of a Visual Basic type; it is declared at module level, inside a class, structure, or module, but not within any procedure internal to that class, structure, or module.</span></span>  
  
### <a name="shared-and-instance-variables"></a><span data-ttu-id="acafe-111">공유 및 인스턴스 변수</span><span class="sxs-lookup"><span data-stu-id="acafe-111">Shared and Instance Variables</span></span>  

 <span data-ttu-id="acafe-112">클래스 또는 구조체에서 멤버 변수의 범주는 공유 여부에 따라 달라 집니다.</span><span class="sxs-lookup"><span data-stu-id="acafe-112">In a class or structure, the category of a member variable depends on whether or not it is shared.</span></span> <span data-ttu-id="acafe-113">[Shared](../../../language-reference/modifiers/shared.md) 키워드를 사용 하 여 선언 된 경우 *공유 변수*이며, 클래스 또는 구조체의 모든 인스턴스 간에 공유 되는 단일 복사본에 존재 합니다.</span><span class="sxs-lookup"><span data-stu-id="acafe-113">If it is declared with the [Shared](../../../language-reference/modifiers/shared.md) keyword, it is a *shared variable*, and it exists in a single copy shared among all instances of the class or structure.</span></span>  
  
 <span data-ttu-id="acafe-114">그렇지 않으면 *인스턴스 변수*이며, 클래스 또는 구조체의 각 인스턴스에 대해 별도의 복사본을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="acafe-114">Otherwise it is an *instance variable*, and a separate copy of it is created for each instance of the class or structure.</span></span> <span data-ttu-id="acafe-115">인스턴스 변수의 지정 된 복사본은 해당 복사본이 생성 된 클래스 또는 구조체의 인스턴스에만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="acafe-115">A given copy of an instance variable is available only to the instance of the class or structure in which it was created.</span></span> <span data-ttu-id="acafe-116">클래스 또는 구조체의 다른 인스턴스에 있는 인스턴스 변수의 복사본과는 독립적입니다.</span><span class="sxs-lookup"><span data-stu-id="acafe-116">It is independent of a copy of the instance variable in any other instance of the class or structure.</span></span>  
  
## <a name="declaring-data-type"></a><span data-ttu-id="acafe-117">데이터 형식 선언</span><span class="sxs-lookup"><span data-stu-id="acafe-117">Declaring Data Type</span></span>  

 <span data-ttu-id="acafe-118">선언문의 [As](../../../language-reference/statements/as-clause.md) 절을 사용 하 여 선언 하는 변수의 데이터 형식 또는 개체 유형을 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="acafe-118">The [As](../../../language-reference/statements/as-clause.md) clause in the declaration statement allows you to define the data type or object type of the variable you are declaring.</span></span> <span data-ttu-id="acafe-119">변수에 대해 다음 형식 중 하나를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="acafe-119">You can specify any of the following types for a variable:</span></span>  
  
- <span data-ttu-id="acafe-120">기본 데이터 형식 (예: `Boolean` , `Long` 또는) `Decimal`</span><span class="sxs-lookup"><span data-stu-id="acafe-120">An elementary data type, such as `Boolean`, `Long`, or `Decimal`</span></span>  
  
- <span data-ttu-id="acafe-121">복합 데이터 형식 (예: 배열 또는 구조체)</span><span class="sxs-lookup"><span data-stu-id="acafe-121">A composite data type, such as an array or structure</span></span>  
  
- <span data-ttu-id="acafe-122">응용 프로그램 또는 다른 응용 프로그램에서 정의 된 개체 형식 또는 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="acafe-122">An object type, or class, defined either in your application or in another application</span></span>  
  
- <span data-ttu-id="acafe-123">또는와 같은 .NET Framework 클래스 <xref:System.Windows.Forms.Label><xref:System.Windows.Forms.TextBox></span><span class="sxs-lookup"><span data-stu-id="acafe-123">A .NET Framework class, such as <xref:System.Windows.Forms.Label> or <xref:System.Windows.Forms.TextBox></span></span>  
  
- <span data-ttu-id="acafe-124">인터페이스 형식 (예: <xref:System.IComparable> 또는) <xref:System.IDisposable></span><span class="sxs-lookup"><span data-stu-id="acafe-124">An interface type, such as <xref:System.IComparable> or <xref:System.IDisposable></span></span>  
  
 <span data-ttu-id="acafe-125">데이터 형식을 반복할 필요 없이 하나의 문에서 여러 변수를 선언할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="acafe-125">You can declare several variables in one statement without having to repeat the data type.</span></span> <span data-ttu-id="acafe-126">다음 문에서, 및 변수는 `i` `j` `k` 형식으로 선언 되 고 및는로 선언 됩니다 `Integer` `l` `m` `Long` `x` `y` `Single` .</span><span class="sxs-lookup"><span data-stu-id="acafe-126">In the following statements, the variables `i`, `j`, and `k` are declared as type `Integer`, `l` and `m` as `Long`, and `x` and `y` as `Single`:</span></span>  
  
```vb  
Dim i, j, k As Integer  
' All three variables in the preceding statement are declared as Integer.  
Dim l, m As Long, x, y As Single  
' In the preceding statement, l and m are Long, x and y are Single.  
```  
  
 <span data-ttu-id="acafe-127">데이터 형식에 대 한 자세한 내용은 [데이터 형식](../data-types/index.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="acafe-127">For more information on data types, see [Data Types](../data-types/index.md).</span></span> <span data-ttu-id="acafe-128">개체에 대 한 자세한 내용은 [개체 및 클래스](../objects-and-classes/index.md) 및 [구성 요소를 사용한 프로그래밍](/previous-versions/visualstudio/visual-studio-2013/0ffkdtkf(v=vs.120))을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="acafe-128">For more information on objects, see [Objects and Classes](../objects-and-classes/index.md) and [Programming with Components](/previous-versions/visualstudio/visual-studio-2013/0ffkdtkf(v=vs.120)).</span></span>  
  
## <a name="local-type-inference"></a><span data-ttu-id="acafe-129">지역 형식 유추</span><span class="sxs-lookup"><span data-stu-id="acafe-129">Local Type Inference</span></span>  

 <span data-ttu-id="acafe-130">*형식 유추* 는 절 없이 선언 된 지역 변수의 데이터 형식을 결정 하는 데 사용 됩니다 `As` .</span><span class="sxs-lookup"><span data-stu-id="acafe-130">*Type inference* is used to determine the data types of local variables declared without an `As` clause.</span></span> <span data-ttu-id="acafe-131">컴파일러는 초기화 식의 형식에서 변수 형식을 유추 합니다.</span><span class="sxs-lookup"><span data-stu-id="acafe-131">The compiler infers the type of the variable from the type of the initialization expression.</span></span> <span data-ttu-id="acafe-132">이렇게 하면 명시적으로 형식을 명시 하지 않고도 변수를 선언할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="acafe-132">This enables you to declare variables without explicitly stating a type.</span></span> <span data-ttu-id="acafe-133">다음 예제에서 `num1` 및 `num2` 는 모두 정수로 강력 하 게 형식화 됩니다.</span><span class="sxs-lookup"><span data-stu-id="acafe-133">In the following example, both `num1` and `num2` are strongly typed as integers.</span></span>  
  
 [!code-vb[VbVbalrTypeInference#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrTypeInference/VB/Class1.vb#1)]  
  
 <span data-ttu-id="acafe-134">로컬 형식 유추를 사용 하려면를 `Option Infer` 로 설정 해야 합니다 `On` .</span><span class="sxs-lookup"><span data-stu-id="acafe-134">If you want to use local type inference, `Option Infer` must be set to `On`.</span></span> <span data-ttu-id="acafe-135">자세한 내용은 [지역 형식 유추](local-type-inference.md) 및 [Option Infer 문](../../../language-reference/statements/option-infer-statement.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="acafe-135">For more information, see [Local Type Inference](local-type-inference.md) and [Option Infer Statement](../../../language-reference/statements/option-infer-statement.md).</span></span>  
  
## <a name="characteristics-of-declared-variables"></a><span data-ttu-id="acafe-136">선언 된 변수의 특성</span><span class="sxs-lookup"><span data-stu-id="acafe-136">Characteristics of Declared Variables</span></span>  

 <span data-ttu-id="acafe-137">변수의 *수명은* 이를 사용할 수 있는 기간입니다.</span><span class="sxs-lookup"><span data-stu-id="acafe-137">The *lifetime* of a variable is the period of time during which it is available for use.</span></span> <span data-ttu-id="acafe-138">일반적으로 변수는 해당 변수를 선언 하는 요소 (예: 프로시저 또는 클래스)가 계속 존재 하는 동안 존재 합니다.</span><span class="sxs-lookup"><span data-stu-id="acafe-138">In general, a variable exists as long as the element that declares it (such as a procedure or class) continues to exist.</span></span> <span data-ttu-id="acafe-139">변수가 포함 하는 요소의 수명을 초과 하 여 기존에 계속할 필요가 없으면 선언에서 특별 한 작업을 수행할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="acafe-139">If the variable does not need to continue existing beyond the lifetime of its containing element, you do not need to do anything special in the declaration.</span></span> <span data-ttu-id="acafe-140">변수가 포함 하는 요소 보다 더 오래 지속 되어야 하는 경우 `Static` 해당 문에 또는 키워드를 포함할 수 있습니다 `Shared` `Dim` .</span><span class="sxs-lookup"><span data-stu-id="acafe-140">If the variable needs to continue to exist longer than its containing element, you can include the `Static` or `Shared` keyword in its `Dim` statement.</span></span> <span data-ttu-id="acafe-141">자세한 내용은 [Visual Basic 수명](../declared-elements/lifetime.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="acafe-141">For more information, see [Lifetime in Visual Basic](../declared-elements/lifetime.md).</span></span>  
  
 <span data-ttu-id="acafe-142">변수의 *범위* 는 이름을 한정 하지 않고 참조할 수 있는 모든 코드 집합입니다.</span><span class="sxs-lookup"><span data-stu-id="acafe-142">The *scope* of a variable is the set of all code that can refer to it without qualifying its name.</span></span> <span data-ttu-id="acafe-143">변수의 범위는 선언 된 위치에 따라 결정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="acafe-143">A variable's scope is determined by where it is declared.</span></span> <span data-ttu-id="acafe-144">지정 된 지역에 있는 코드는 해당 영역에 정의 된 변수를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="acafe-144">Code located in a given region can use the variables defined in that region without having to qualify their names.</span></span> <span data-ttu-id="acafe-145">자세한 내용은 [Scope in Visual Basic](../declared-elements/scope.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="acafe-145">For more information, see [Scope in Visual Basic](../declared-elements/scope.md).</span></span>  
  
 <span data-ttu-id="acafe-146">변수의 *액세스 수준은* 액세스 권한이 있는 코드의 범위입니다.</span><span class="sxs-lookup"><span data-stu-id="acafe-146">A variable's *access level* is the extent of code that has permission to access it.</span></span> <span data-ttu-id="acafe-147">이는 문에 사용 하는 액세스 한정자 (예: [공용](../../../language-reference/modifiers/public.md) 또는 [개인](../../../language-reference/modifiers/private.md))에 의해 결정 됩니다 `Dim` .</span><span class="sxs-lookup"><span data-stu-id="acafe-147">This is determined by the access modifier (such as [Public](../../../language-reference/modifiers/public.md) or [Private](../../../language-reference/modifiers/private.md)) that you use in the `Dim` statement.</span></span> <span data-ttu-id="acafe-148">자세한 내용은 [Visual Basic의 액세스 수준](../declared-elements/access-levels.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="acafe-148">For more information, see [Access levels in Visual Basic](../declared-elements/access-levels.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="acafe-149">참조</span><span class="sxs-lookup"><span data-stu-id="acafe-149">See also</span></span>

- [<span data-ttu-id="acafe-150">방법: 새 변수 만들기</span><span class="sxs-lookup"><span data-stu-id="acafe-150">How to: Create a New Variable</span></span>](how-to-create-a-new-variable.md)
- [<span data-ttu-id="acafe-151">방법: 변수 값 저장 및 검색</span><span class="sxs-lookup"><span data-stu-id="acafe-151">How to: Move Data Into and Out of a Variable</span></span>](how-to-move-data-into-and-out-of-a-variable.md)
- [<span data-ttu-id="acafe-152">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="acafe-152">Data Types</span></span>](../../../language-reference/data-types/index.md)
- [<span data-ttu-id="acafe-153">보호</span><span class="sxs-lookup"><span data-stu-id="acafe-153">Protected</span></span>](../../../language-reference/modifiers/protected.md)
- [<span data-ttu-id="acafe-154">Friend</span><span class="sxs-lookup"><span data-stu-id="acafe-154">Friend</span></span>](../../../language-reference/modifiers/friend.md)
- [<span data-ttu-id="acafe-155">정적</span><span class="sxs-lookup"><span data-stu-id="acafe-155">Static</span></span>](../../../language-reference/modifiers/static.md)
- [<span data-ttu-id="acafe-156">선언 요소의 특징</span><span class="sxs-lookup"><span data-stu-id="acafe-156">Declared Element Characteristics</span></span>](../declared-elements/declared-element-characteristics.md)
- [<span data-ttu-id="acafe-157">지역 형식 유추</span><span class="sxs-lookup"><span data-stu-id="acafe-157">Local Type Inference</span></span>](local-type-inference.md)
- [<span data-ttu-id="acafe-158">Option Infer 문</span><span class="sxs-lookup"><span data-stu-id="acafe-158">Option Infer Statement</span></span>](../../../language-reference/statements/option-infer-statement.md)
