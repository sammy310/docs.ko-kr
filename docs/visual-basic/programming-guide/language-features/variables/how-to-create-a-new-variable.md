---
title: '방법: 새 변수 만들기'
ms.date: 07/20/2015
helpviewer_keywords:
- Dim statement [Visual Basic]
- variables [Visual Basic], creating
ms.assetid: 35300be3-77b0-4bef-a156-034d3cdedde0
ms.openlocfilehash: 501c8f3aff4c5b204d231bdc26213e13d125a7cf
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/04/2020
ms.locfileid: "84410531"
---
# <a name="how-to-create-a-new-variable-visual-basic"></a><span data-ttu-id="41160-102">방법: 새 변수 만들기(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="41160-102">How to: Create a New Variable (Visual Basic)</span></span>

<span data-ttu-id="41160-103">[Dim 문을](../../../language-reference/statements/dim-statement.md)사용 하 여 변수를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="41160-103">You create a variable with a [Dim Statement](../../../language-reference/statements/dim-statement.md).</span></span>

### <a name="to-create-a-new-variable"></a><span data-ttu-id="41160-104">새 변수를 만들려면</span><span class="sxs-lookup"><span data-stu-id="41160-104">To create a new variable</span></span>

1. <span data-ttu-id="41160-105">문에서 변수를 선언 `Dim` 합니다.</span><span class="sxs-lookup"><span data-stu-id="41160-105">Declare the variable in a `Dim` statement.</span></span>

    ```vb
    Dim newCustomer
    ```

2. <span data-ttu-id="41160-106">[Private](../../../language-reference/modifiers/private.md), [Static](../../../language-reference/modifiers/static.md), [Shadows](../../../language-reference/modifiers/shadows.md)또는 [WithEvents](../../../language-reference/modifiers/withevents.md)와 같은 변수의 특징에 대 한 사양을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="41160-106">Include specifications for the variable's characteristics, such as [Private](../../../language-reference/modifiers/private.md), [Static](../../../language-reference/modifiers/static.md), [Shadows](../../../language-reference/modifiers/shadows.md), or [WithEvents](../../../language-reference/modifiers/withevents.md).</span></span> <span data-ttu-id="41160-107">자세한 내용은 [선언 된 요소 특성](../declared-elements/declared-element-characteristics.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="41160-107">For more information, see [Declared Element Characteristics](../declared-elements/declared-element-characteristics.md).</span></span>

    ```vb
    Public Static newCustomer
    ```

    <span data-ttu-id="41160-108">`Dim`선언에서 다른 키워드를 사용 하는 경우 키워드가 필요 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="41160-108">You do not need the `Dim` keyword if you use other keywords in the declaration.</span></span>

3. <span data-ttu-id="41160-109">규칙 및 규칙 Visual Basic 따라야 하는 변수의 이름을 사용 하 여 사양을 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="41160-109">Follow the specifications with the variable's name, which must follow Visual Basic rules and conventions.</span></span> <span data-ttu-id="41160-110">자세한 내용은 [선언 된 요소 이름](../declared-elements/declared-element-names.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="41160-110">For more information, see [Declared Element Names](../declared-elements/declared-element-names.md).</span></span>

    ```vb
    Public Static newCustomer
    ```

4. <span data-ttu-id="41160-111">이름 뒤에 [As](../../../language-reference/statements/as-clause.md) 절을 추가 하 여 변수의 데이터 형식을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="41160-111">Follow the name with the [As](../../../language-reference/statements/as-clause.md) clause to specify the variable's data type.</span></span>

    ```vb
    Public Static newCustomer As Customer
    ```

    <span data-ttu-id="41160-112">데이터 형식을 지정 하지 않으면 기본적으로가 사용 `Object` 됩니다.</span><span class="sxs-lookup"><span data-stu-id="41160-112">If you do not specify the data type, it uses the default: `Object`.</span></span>

5. <span data-ttu-id="41160-113">`As`등호 ()를 사용 하 여 절을 따르고 `=` 변수의 초기 값을 사용 하 여 등호를 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="41160-113">Follow the `As` clause with an equal sign (`=`) and follow the equal sign with the variable's initial value.</span></span>

    <span data-ttu-id="41160-114">Visual Basic는 문을 실행할 때마다 변수에 지정 된 값을 할당 합니다 `Dim` .</span><span class="sxs-lookup"><span data-stu-id="41160-114">Visual Basic assigns the specified value to the variable every time it runs the `Dim` statement.</span></span> <span data-ttu-id="41160-115">초기 값을 지정 하지 않는 경우 Visual Basic는 먼저 문이 포함 된 코드를 입력할 때 변수의 데이터 형식에 대 한 기본 초기 값을 할당 합니다 `Dim` .</span><span class="sxs-lookup"><span data-stu-id="41160-115">If you do not specify an initial value, Visual Basic assigns the default initial value for the variable's data type when it first enters the code that contains the `Dim` statement.</span></span>

    <span data-ttu-id="41160-116">변수가 참조 형식이 면 절에 [New Operator](../../../language-reference/operators/new-operator.md) 키워드를 포함 하 여 해당 클래스의 인스턴스를 만들 수 있습니다 `As` .</span><span class="sxs-lookup"><span data-stu-id="41160-116">If the variable is a reference type, you can create an instance of its class by including the [New Operator](../../../language-reference/operators/new-operator.md) keyword in the `As` clause.</span></span> <span data-ttu-id="41160-117">을 사용 하지 않는 경우 `New` 변수의 초기 값은 [Nothing](../../../language-reference/nothing.md)입니다.</span><span class="sxs-lookup"><span data-stu-id="41160-117">If you do not use `New`, the initial value of the variable is [Nothing](../../../language-reference/nothing.md).</span></span>

    ```vb
    Public Static newCustomer As New Customer
    ```

## <a name="see-also"></a><span data-ttu-id="41160-118">참고 항목</span><span class="sxs-lookup"><span data-stu-id="41160-118">See also</span></span>

- [<span data-ttu-id="41160-119">변수</span><span class="sxs-lookup"><span data-stu-id="41160-119">Variables</span></span>](index.md)
- [<span data-ttu-id="41160-120">변수 선언</span><span class="sxs-lookup"><span data-stu-id="41160-120">Variable Declaration</span></span>](variable-declaration.md)
- [<span data-ttu-id="41160-121">Declared Element Names</span><span class="sxs-lookup"><span data-stu-id="41160-121">Declared Element Names</span></span>](../declared-elements/declared-element-names.md)
- [<span data-ttu-id="41160-122">선언 요소의 특징</span><span class="sxs-lookup"><span data-stu-id="41160-122">Declared Element Characteristics</span></span>](../declared-elements/declared-element-characteristics.md)
- [<span data-ttu-id="41160-123">Value Types and Reference Types</span><span class="sxs-lookup"><span data-stu-id="41160-123">Value Types and Reference Types</span></span>](../data-types/value-types-and-reference-types.md)
- [<span data-ttu-id="41160-124">문</span><span class="sxs-lookup"><span data-stu-id="41160-124">Statements</span></span>](../../../language-reference/statements/index.md)
- [<span data-ttu-id="41160-125">지역 형식 유추</span><span class="sxs-lookup"><span data-stu-id="41160-125">Local Type Inference</span></span>](local-type-inference.md)
- [<span data-ttu-id="41160-126">Option Infer 문</span><span class="sxs-lookup"><span data-stu-id="41160-126">Option Infer Statement</span></span>](../../../language-reference/statements/option-infer-statement.md)
