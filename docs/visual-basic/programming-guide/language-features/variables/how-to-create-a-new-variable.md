---
title: '방법: 새 변수 (Visual Basic) 만들기'
ms.date: 07/20/2015
helpviewer_keywords:
- Dim statement [Visual Basic]
- variables [Visual Basic], creating
ms.assetid: 35300be3-77b0-4bef-a156-034d3cdedde0
ms.openlocfilehash: ee1e93b4e9819992f17738eb024004a4d66210d1
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59332588"
---
# <a name="how-to-create-a-new-variable-visual-basic"></a><span data-ttu-id="e8d09-102">방법: 새 변수 (Visual Basic) 만들기</span><span class="sxs-lookup"><span data-stu-id="e8d09-102">How to: Create a New Variable (Visual Basic)</span></span>
<span data-ttu-id="e8d09-103">변수를 만들 수는 [Dim 문](../../../../visual-basic/language-reference/statements/dim-statement.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="e8d09-103">You create a variable with a [Dim Statement](../../../../visual-basic/language-reference/statements/dim-statement.md).</span></span>  
  
### <a name="to-create-a-new-variable"></a><span data-ttu-id="e8d09-104">새 변수를 만들려면</span><span class="sxs-lookup"><span data-stu-id="e8d09-104">To create a new variable</span></span>  
  
1. <span data-ttu-id="e8d09-105">변수를 선언 하는 `Dim` 문입니다.</span><span class="sxs-lookup"><span data-stu-id="e8d09-105">Declare the variable in a `Dim` statement.</span></span>  
  
    ```  
    Dim newCustomer  
    ```  
  
2. <span data-ttu-id="e8d09-106">같은 변수 특성에 대 한 사양 포함 [개인](../../../../visual-basic/language-reference/modifiers/private.md)를 [정적](../../../../visual-basic/language-reference/modifiers/static.md)를 [그림자](../../../../visual-basic/language-reference/modifiers/shadows.md), 또는 [WithEvents](../../../../visual-basic/language-reference/modifiers/withevents.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="e8d09-106">Include specifications for the variable's characteristics, such as [Private](../../../../visual-basic/language-reference/modifiers/private.md), [Static](../../../../visual-basic/language-reference/modifiers/static.md), [Shadows](../../../../visual-basic/language-reference/modifiers/shadows.md), or [WithEvents](../../../../visual-basic/language-reference/modifiers/withevents.md).</span></span> <span data-ttu-id="e8d09-107">자세한 내용은 [선언 요소의 특징](../../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-characteristics.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="e8d09-107">For more information, see [Declared Element Characteristics](../../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-characteristics.md).</span></span>  
  
    ```  
    Public Static newCustomer  
    ```  
  
     <span data-ttu-id="e8d09-108">않아도 `Dim` 키워드는 선언에서 다른 키워드를 사용 하는 경우.</span><span class="sxs-lookup"><span data-stu-id="e8d09-108">You do not need the `Dim` keyword if you use other keywords in the declaration.</span></span>  
  
3. <span data-ttu-id="e8d09-109">Visual Basic 규칙 및 규칙을 따라야 하는 변수 이름의 사양을 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="e8d09-109">Follow the specifications with the variable's name, which must follow Visual Basic rules and conventions.</span></span> <span data-ttu-id="e8d09-110">자세한 내용은 [선언 요소 이름](../../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="e8d09-110">For more information, see [Declared Element Names](../../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).</span></span>  
  
    ```  
    Public Static newCustomer  
    ```  
  
4. <span data-ttu-id="e8d09-111">이름 뒤에 [으로](../../../../visual-basic/language-reference/statements/as-clause.md) 절 변수의 데이터 형식을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="e8d09-111">Follow the name with the [As](../../../../visual-basic/language-reference/statements/as-clause.md) clause to specify the variable's data type.</span></span>  
  
    ```  
    Public Static newCustomer As Customer  
    ```  
  
     <span data-ttu-id="e8d09-112">데이터 형식, 지정 하지 않으면 기본 사용: `Object`합니다.</span><span class="sxs-lookup"><span data-stu-id="e8d09-112">If you do not specify the data type, it uses the default: `Object`.</span></span>  
  
5. <span data-ttu-id="e8d09-113">수행 합니다 `As` 등호를 사용 하 여 절 (`=`) 변수의 초기 값을 사용 하 여 등호 기호에 따라 합니다.</span><span class="sxs-lookup"><span data-stu-id="e8d09-113">Follow the `As` clause with an equal sign (`=`) and follow the equal sign with the variable's initial value.</span></span>  
  
     <span data-ttu-id="e8d09-114">Visual Basic 실행 될 때마다 변수에 지정된 된 값을 할당 합니다 `Dim` 문입니다.</span><span class="sxs-lookup"><span data-stu-id="e8d09-114">Visual Basic assigns the specified value to the variable every time it runs the `Dim` statement.</span></span> <span data-ttu-id="e8d09-115">초기 값을 지정 하지 않으면 하는 경우 Visual Basic 코드를 포함 하는 처음 실행 하는 경우 변수의 데이터 형식에 대 한 초기 기본값을 할당 하는 `Dim` 문입니다.</span><span class="sxs-lookup"><span data-stu-id="e8d09-115">If you do not specify an initial value, Visual Basic assigns the default initial value for the variable's data type when it first enters the code that contains the `Dim` statement.</span></span>  
  
     <span data-ttu-id="e8d09-116">변수 참조 형식인 경우를 포함 하 여 해당 클래스의 인스턴스를 만들 수 있습니다 합니다 [New 연산자](../../../../visual-basic/language-reference/operators/new-operator.md) 키워드를 `As` 절.</span><span class="sxs-lookup"><span data-stu-id="e8d09-116">If the variable is a reference type, you can create an instance of its class by including the [New Operator](../../../../visual-basic/language-reference/operators/new-operator.md) keyword in the `As` clause.</span></span> <span data-ttu-id="e8d09-117">사용 하지 않는 경우 `New`, 변수의 초기 값은 [Nothing](../../../../visual-basic/language-reference/nothing.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="e8d09-117">If you do not use `New`, the initial value of the variable is [Nothing](../../../../visual-basic/language-reference/nothing.md).</span></span>  
  
    ```  
    Public Static newCustomer As New Customer  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="e8d09-118">참고자료</span><span class="sxs-lookup"><span data-stu-id="e8d09-118">See also</span></span>

- [<span data-ttu-id="e8d09-119">변수</span><span class="sxs-lookup"><span data-stu-id="e8d09-119">Variables</span></span>](../../../../visual-basic/programming-guide/language-features/variables/index.md)
- [<span data-ttu-id="e8d09-120">변수 선언</span><span class="sxs-lookup"><span data-stu-id="e8d09-120">Variable Declaration</span></span>](../../../../visual-basic/programming-guide/language-features/variables/variable-declaration.md)
- [<span data-ttu-id="e8d09-121">선언 요소 이름</span><span class="sxs-lookup"><span data-stu-id="e8d09-121">Declared Element Names</span></span>](../../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md)
- [<span data-ttu-id="e8d09-122">선언 요소의 특징</span><span class="sxs-lookup"><span data-stu-id="e8d09-122">Declared Element Characteristics</span></span>](../../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-characteristics.md)
- [<span data-ttu-id="e8d09-123">Value Types and Reference Types</span><span class="sxs-lookup"><span data-stu-id="e8d09-123">Value Types and Reference Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)
- [<span data-ttu-id="e8d09-124">문(C++)</span><span class="sxs-lookup"><span data-stu-id="e8d09-124">Statements</span></span>](../../../../visual-basic/language-reference/statements/index.md)
- [<span data-ttu-id="e8d09-125">지역 형식 유추</span><span class="sxs-lookup"><span data-stu-id="e8d09-125">Local Type Inference</span></span>](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)
- [<span data-ttu-id="e8d09-126">Option Infer 문</span><span class="sxs-lookup"><span data-stu-id="e8d09-126">Option Infer Statement</span></span>](../../../../visual-basic/language-reference/statements/option-infer-statement.md)
