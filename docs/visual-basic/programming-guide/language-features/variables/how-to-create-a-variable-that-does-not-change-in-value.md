---
title: '방법: (Visual Basic) 값이 변경 되지 않는 변수 만들기'
ms.date: 07/20/2015
helpviewer_keywords:
- variables [Visual Basic], read-only
- variables [Visual Basic], constant value
ms.assetid: 86b59266-25df-4635-ae15-9b59c411d036
ms.openlocfilehash: 3a9fa93b69c9abb42b2dd7eae623048f3628999e
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/28/2019
ms.locfileid: "64663566"
---
# <a name="how-to-create-a-variable-that-does-not-change-in-value-visual-basic"></a><span data-ttu-id="1961c-102">방법: (Visual Basic) 값이 변경 되지 않는 변수 만들기</span><span class="sxs-lookup"><span data-stu-id="1961c-102">How to: Create a Variable that Does Not Change in Value (Visual Basic)</span></span>
<span data-ttu-id="1961c-103">해당 값을 변경 하지 않는 변수의 개념 모순 되 게 나타날 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1961c-103">The notion of a variable that does not change its value might appear to be contradictory.</span></span> <span data-ttu-id="1961c-104">상수 불가능 한 경우에 있고 변수를 fixed 값을 가진 것이 유용 합니다.</span><span class="sxs-lookup"><span data-stu-id="1961c-104">But there are situations when a constant is not feasible and it is useful to have a variable with a fixed value.</span></span> <span data-ttu-id="1961c-105">이러한 경우에 사용 하 여 멤버 변수를 정의할 수 있습니다 합니다 [ReadOnly](../../../../visual-basic/language-reference/modifiers/readonly.md) 키워드입니다.</span><span class="sxs-lookup"><span data-stu-id="1961c-105">In such a case you can define a member variable with the [ReadOnly](../../../../visual-basic/language-reference/modifiers/readonly.md) keyword.</span></span>  
  
 <span data-ttu-id="1961c-106">사용할 수 없습니다는 [Const 문](../../../../visual-basic/language-reference/statements/const-statement.md) 선언 하 고 다음과 같은 경우에서 상수 값을 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="1961c-106">You cannot use the [Const Statement](../../../../visual-basic/language-reference/statements/const-statement.md) to declare and assign a constant value in the following circumstances:</span></span>  
  
- <span data-ttu-id="1961c-107">`Const` 문에서 사용 하려는 데이터 형식을 허용 하지 않는</span><span class="sxs-lookup"><span data-stu-id="1961c-107">The `Const` statement does not accept the data type you want to use</span></span>  
  
- <span data-ttu-id="1961c-108">컴파일 타임에 값을 모르는</span><span class="sxs-lookup"><span data-stu-id="1961c-108">You do not know the value at compile time</span></span>  
  
- <span data-ttu-id="1961c-109">컴파일 시간에 상수 값을 계산할 수 없습니다</span><span class="sxs-lookup"><span data-stu-id="1961c-109">You are unable to compute the constant value at compile time</span></span>  
  
### <a name="to-create-a-variable-that-does-not-change-in-value"></a><span data-ttu-id="1961c-110">값이 변경 되지 않는 변수를 만들려면</span><span class="sxs-lookup"><span data-stu-id="1961c-110">To create a variable that does not change in value</span></span>  
  
1. <span data-ttu-id="1961c-111">모듈 수준에서 멤버 변수를 선언 합니다 [Dim 문](../../../../visual-basic/language-reference/statements/dim-statement.md), 포함 합니다 [ReadOnly](../../../../visual-basic/language-reference/modifiers/readonly.md) 키워드.</span><span class="sxs-lookup"><span data-stu-id="1961c-111">At module level, declare a member variable with the [Dim Statement](../../../../visual-basic/language-reference/statements/dim-statement.md), and include the [ReadOnly](../../../../visual-basic/language-reference/modifiers/readonly.md) keyword.</span></span>  
  
    ```  
    Dim ReadOnly timeStarted  
    ```  
  
     <span data-ttu-id="1961c-112">지정할 수 있습니다 `ReadOnly` 멤버 변수 에서만.</span><span class="sxs-lookup"><span data-stu-id="1961c-112">You can specify `ReadOnly` only on a member variable.</span></span> <span data-ttu-id="1961c-113">즉, 기존 프로시저 외부의 모듈 수준 변수를 정의 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1961c-113">This means you must define the variable at module level, outside of any procedure.</span></span>  
  
2. <span data-ttu-id="1961c-114">컴파일 시간에 단일 문에서 값을 계산할 수, 하는 경우에 초기화 절을 사용 합니다 `Dim` 문입니다.</span><span class="sxs-lookup"><span data-stu-id="1961c-114">If you can compute the value in a single statement at compile time, use an initialization clause in the `Dim` statement.</span></span> <span data-ttu-id="1961c-115">수행 합니다 [으로](../../../../visual-basic/language-reference/statements/as-clause.md) 등호를 사용 하 여 절 (`=`) 식 뒤에.</span><span class="sxs-lookup"><span data-stu-id="1961c-115">Follow the [As](../../../../visual-basic/language-reference/statements/as-clause.md) clause with an equal sign (`=`), followed by an expression.</span></span> <span data-ttu-id="1961c-116">컴파일러는 상수 값이이 식을 평가할 수 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1961c-116">Be sure the compiler can evaluate this expression to a constant value.</span></span>  
  
    ```  
    Dim ReadOnly timeStarted As Date = Now  
    ```  
  
     <span data-ttu-id="1961c-117">값을 할당할 수 있습니다는 `ReadOnly` 변수 한 번만 합니다.</span><span class="sxs-lookup"><span data-stu-id="1961c-117">You can assign a value to a `ReadOnly` variable only once.</span></span> <span data-ttu-id="1961c-118">이렇게 하면 코드가 없습니다. 해당 값을 변경 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1961c-118">Once you do so, no code can ever change its value.</span></span>  
  
     <span data-ttu-id="1961c-119">컴파일 타임에 값을 알지 못하는 하거나 단일 문에서 컴파일 시간에 계산할 수 없습니다. 생성자에서 런타임 시 계속 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1961c-119">If you do not know the value at compile time, or cannot compute it at compile time in a single statement, you can still assign it at run time in a constructor.</span></span> <span data-ttu-id="1961c-120">이 작업을 수행 하려면 선언 해야 합니다 `ReadOnly` 클래스 또는 구조 수준에서 변수입니다.</span><span class="sxs-lookup"><span data-stu-id="1961c-120">To do this, you must declare the `ReadOnly` variable at class or structure level.</span></span> <span data-ttu-id="1961c-121">해당 클래스 또는 구조체에 대 한 생성자에서 변수의 고정된 값을 계산 하 고 생성자에서 반환 하기 전에를 변수에 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="1961c-121">In the constructor for that class or structure, compute the variable's fixed value, and assign it to the variable before returning from the constructor.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1961c-122">참고자료</span><span class="sxs-lookup"><span data-stu-id="1961c-122">See also</span></span>

- [<span data-ttu-id="1961c-123">WriteOnly</span><span class="sxs-lookup"><span data-stu-id="1961c-123">WriteOnly</span></span>](../../../../visual-basic/language-reference/modifiers/writeonly.md)
- [<span data-ttu-id="1961c-124">Const 문</span><span class="sxs-lookup"><span data-stu-id="1961c-124">Const Statement</span></span>](../../../../visual-basic/language-reference/statements/const-statement.md)
