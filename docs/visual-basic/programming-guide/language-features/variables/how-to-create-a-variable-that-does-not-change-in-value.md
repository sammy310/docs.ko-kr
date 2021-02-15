---
description: '자세히 알아보기: 방법: 값에서 변경 되지 않는 변수 만들기 (Visual Basic)'
title: '방법: 값을 변경하지 않는 변수 만들기'
ms.date: 07/20/2015
helpviewer_keywords:
- variables [Visual Basic], read-only
- variables [Visual Basic], constant value
ms.assetid: 86b59266-25df-4635-ae15-9b59c411d036
ms.openlocfilehash: 0392a27249de3bf604a73c8f8aaa16caf6f1c3e2
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/14/2021
ms.locfileid: "100481937"
---
# <a name="how-to-create-a-variable-that-does-not-change-in-value-visual-basic"></a><span data-ttu-id="3e0da-103">방법: 값이 변경되지 않는 변수 만들기(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="3e0da-103">How to: Create a Variable that Does Not Change in Value (Visual Basic)</span></span>

<span data-ttu-id="3e0da-104">해당 값을 변경 하지 않는 변수의 개념은 모순 되는 것 처럼 보일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3e0da-104">The notion of a variable that does not change its value might appear to be contradictory.</span></span> <span data-ttu-id="3e0da-105">그러나 상수가 적절 하지 않으며 고정 값이 있는 변수를 사용 하는 것이 유용한 경우가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3e0da-105">But there are situations when a constant is not feasible and it is useful to have a variable with a fixed value.</span></span> <span data-ttu-id="3e0da-106">이 경우 [ReadOnly](../../../language-reference/modifiers/readonly.md) 키워드를 사용 하 여 멤버 변수를 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3e0da-106">In such a case you can define a member variable with the [ReadOnly](../../../language-reference/modifiers/readonly.md) keyword.</span></span>

<span data-ttu-id="3e0da-107">다음과 같은 경우에는 [Const 문을](../../../language-reference/statements/const-statement.md) 사용 하 여 상수 값을 선언 하 고 할당할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="3e0da-107">You cannot use the [Const Statement](../../../language-reference/statements/const-statement.md) to declare and assign a constant value in the following circumstances:</span></span>

- <span data-ttu-id="3e0da-108">`Const`문이 사용 하려는 데이터 형식을 허용 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="3e0da-108">The `Const` statement does not accept the data type you want to use</span></span>

- <span data-ttu-id="3e0da-109">컴파일 시간에 값을 알 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="3e0da-109">You do not know the value at compile time</span></span>

- <span data-ttu-id="3e0da-110">컴파일 시간에 상수 값을 계산할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="3e0da-110">You are unable to compute the constant value at compile time</span></span>

### <a name="to-create-a-variable-that-does-not-change-in-value"></a><span data-ttu-id="3e0da-111">값이 변경 되지 않는 변수를 만들려면</span><span class="sxs-lookup"><span data-stu-id="3e0da-111">To create a variable that does not change in value</span></span>

1. <span data-ttu-id="3e0da-112">모듈 수준에서 [Dim 문을](../../../language-reference/statements/dim-statement.md)사용 하 여 멤버 변수를 선언 하 고 [ReadOnly](../../../language-reference/modifiers/readonly.md) 키워드를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="3e0da-112">At module level, declare a member variable with the [Dim Statement](../../../language-reference/statements/dim-statement.md), and include the [ReadOnly](../../../language-reference/modifiers/readonly.md) keyword.</span></span>

    ```vb
    Dim ReadOnly timeStarted
    ```

    <span data-ttu-id="3e0da-113">`ReadOnly`멤버 변수에만 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3e0da-113">You can specify `ReadOnly` only on a member variable.</span></span> <span data-ttu-id="3e0da-114">즉, 프로시저 외부의 모듈 수준에서 변수를 정의 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3e0da-114">This means you must define the variable at module level, outside of any procedure.</span></span>

2. <span data-ttu-id="3e0da-115">컴파일 시간에 단일 문에서 값을 계산할 수 있는 경우 문에 초기화 절을 사용 `Dim` 합니다.</span><span class="sxs-lookup"><span data-stu-id="3e0da-115">If you can compute the value in a single statement at compile time, use an initialization clause in the `Dim` statement.</span></span> <span data-ttu-id="3e0da-116">[As](../../../language-reference/statements/as-clause.md) 절 뒤에 등호 ()를 추가 하 고 `=` 그 뒤에 식을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="3e0da-116">Follow the [As](../../../language-reference/statements/as-clause.md) clause with an equal sign (`=`), followed by an expression.</span></span> <span data-ttu-id="3e0da-117">컴파일러가이 식을 상수 값으로 계산할 수 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3e0da-117">Be sure the compiler can evaluate this expression to a constant value.</span></span>

    ```vb
    Dim ReadOnly timeStarted As Date = Now
    ```

    <span data-ttu-id="3e0da-118">변수에 값을 `ReadOnly` 한 번만 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3e0da-118">You can assign a value to a `ReadOnly` variable only once.</span></span> <span data-ttu-id="3e0da-119">이렇게 하면 코드에서 해당 값을 변경할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="3e0da-119">Once you do so, no code can ever change its value.</span></span>

    <span data-ttu-id="3e0da-120">컴파일 시간에 값을 알 수 없거나 컴파일 타임에 단일 문에서이 값을 계산할 수 없는 경우 생성자에서 런타임에 해당 값을 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3e0da-120">If you do not know the value at compile time, or cannot compute it at compile time in a single statement, you can still assign it at run time in a constructor.</span></span> <span data-ttu-id="3e0da-121">이렇게 하려면 `ReadOnly` 클래스 또는 구조체 수준에서 변수를 선언 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3e0da-121">To do this, you must declare the `ReadOnly` variable at class or structure level.</span></span> <span data-ttu-id="3e0da-122">해당 클래스 또는 구조체에 대 한 생성자에서 변수의 고정 값을 계산 하 고 생성자에서 반환 하기 전에 변수에 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="3e0da-122">In the constructor for that class or structure, compute the variable's fixed value, and assign it to the variable before returning from the constructor.</span></span>

## <a name="see-also"></a><span data-ttu-id="3e0da-123">추가 정보</span><span class="sxs-lookup"><span data-stu-id="3e0da-123">See also</span></span>

- [<span data-ttu-id="3e0da-124">WriteOnly</span><span class="sxs-lookup"><span data-stu-id="3e0da-124">WriteOnly</span></span>](../../../language-reference/modifiers/writeonly.md)
- [<span data-ttu-id="3e0da-125">Const 문</span><span class="sxs-lookup"><span data-stu-id="3e0da-125">Const Statement</span></span>](../../../language-reference/statements/const-statement.md)
