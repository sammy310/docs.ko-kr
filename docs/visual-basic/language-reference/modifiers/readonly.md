---
title: ReadOnly(Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.ReadOnly
helpviewer_keywords:
- ReadOnly keyword [Visual Basic]
- variables [Visual Basic], read-only
- ReadOnly property
- properties [Visual Basic], read-only
- read-only variables
ms.assetid: e868185d-6142-4359-a2fd-a7965cadfce8
ms.openlocfilehash: 1a486d0fadce8135fe01d9eecd611081c986bfae
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/28/2019
ms.locfileid: "64647696"
---
# <a name="readonly-visual-basic"></a><span data-ttu-id="5418c-102">ReadOnly(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="5418c-102">ReadOnly (Visual Basic)</span></span>
<span data-ttu-id="5418c-103">변수 또는 속성을 읽을 수 있지만 기록 되지 않습니다 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="5418c-103">Specifies that a variable or property can be read but not written.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5418c-104">설명</span><span class="sxs-lookup"><span data-stu-id="5418c-104">Remarks</span></span>  
  
## <a name="rules"></a><span data-ttu-id="5418c-105">규칙</span><span class="sxs-lookup"><span data-stu-id="5418c-105">Rules</span></span>  
  
- <span data-ttu-id="5418c-106">**선언 컨텍스트입니다.**</span><span class="sxs-lookup"><span data-stu-id="5418c-106">**Declaration Context.**</span></span> <span data-ttu-id="5418c-107">`ReadOnly`는 모듈 수준에서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5418c-107">You can use `ReadOnly` only at module level.</span></span> <span data-ttu-id="5418c-108">즉, 선언 컨텍스트는 `ReadOnly` 요소 클래스, 구조체 또는 모듈 이어야 하며 원본 파일, 네임 스페이스 또는 프로시저 수는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="5418c-108">This means the declaration context for a `ReadOnly` element must be a class, structure, or module, and cannot be a source file, namespace, or procedure.</span></span>  
  
- <span data-ttu-id="5418c-109">**결합 된 한정자입니다.**</span><span class="sxs-lookup"><span data-stu-id="5418c-109">**Combined Modifiers.**</span></span> <span data-ttu-id="5418c-110">지정할 수 없습니다 `ReadOnly` 와 함께 `Static` 같은 선언에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5418c-110">You cannot specify `ReadOnly` together with `Static` in the same declaration.</span></span>  
  
- <span data-ttu-id="5418c-111">**값을 할당 합니다.**</span><span class="sxs-lookup"><span data-stu-id="5418c-111">**Assigning a Value.**</span></span> <span data-ttu-id="5418c-112">사용 하는 코드는 `ReadOnly` 속성의 값을 설정할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="5418c-112">Code consuming a `ReadOnly` property cannot set its value.</span></span> <span data-ttu-id="5418c-113">하지만 기본 저장소에 액세스할 수 있는 코드에 할당 하거나 언제 든 지 값을 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5418c-113">But code that has access to the underlying storage can assign or change the value at any time.</span></span>  
  
     <span data-ttu-id="5418c-114">값을 할당할 수 있습니다는 `ReadOnly` 변수 선언 또는 클래스 또는 구조체 정의 되어 있는 생성자만 합니다.</span><span class="sxs-lookup"><span data-stu-id="5418c-114">You can assign a value to a `ReadOnly` variable only in its declaration or in the constructor of a class or structure in which it is defined.</span></span>  
  
## <a name="when-to-use-a-readonly-variable"></a><span data-ttu-id="5418c-115">읽기 전용 변수를 사용 하는 경우</span><span class="sxs-lookup"><span data-stu-id="5418c-115">When to Use a ReadOnly Variable</span></span>  
 <span data-ttu-id="5418c-116">경우에는 사용할 수 없습니다는 [Const 문](../../../visual-basic/language-reference/statements/const-statement.md) 선언 및 상수 값을 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="5418c-116">There are situations in which you cannot use a [Const Statement](../../../visual-basic/language-reference/statements/const-statement.md) to declare and assign a constant value.</span></span> <span data-ttu-id="5418c-117">예를 들어를 `Const` 문을 할당 하려는 데이터 형식이 허용 되지 않거나 상수 식 사용 하 여 컴파일 타임에 값을 계산할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5418c-117">For example, the `Const` statement might not accept the data type you want to assign, or you might not be able to compute the value at compile time with a constant expression.</span></span> <span data-ttu-id="5418c-118">모를 수도 있습니다도 값을 컴파일 시간에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5418c-118">You might not even know the value at compile time.</span></span> <span data-ttu-id="5418c-119">이러한 경우에 사용할 수는 `ReadOnly` 상수 값을 보유할 변수로 대체 합니다.</span><span class="sxs-lookup"><span data-stu-id="5418c-119">In these cases, you can use a `ReadOnly` variable to hold a constant value.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="5418c-120">변수 자체는 경우에 해당 멤버를 변경할 수 있습니다 변수의 데이터 형식은 참조 형식, 배열 또는 클래스 인스턴스를 같은 경우 `ReadOnly`합니다.</span><span class="sxs-lookup"><span data-stu-id="5418c-120">If the data type of the variable is a reference type, such as an array or a class instance, its members can be changed even if the variable itself is `ReadOnly`.</span></span> <span data-ttu-id="5418c-121">다음은 이에 대한 예입니다.</span><span class="sxs-lookup"><span data-stu-id="5418c-121">The following example illustrates this.</span></span>  
  
 `ReadOnly characterArray() As Char = {"x"c, "y"c, "z"c}`  
  
 `Sub changeArrayElement()`  
  
 `characterArray(1) = "M"c`  
  
 `End Sub`  
  
 <span data-ttu-id="5418c-122">를 초기화할 때 배열을 가리키는 `characterArray()` 포함 "x", "y" 및 "z"입니다.</span><span class="sxs-lookup"><span data-stu-id="5418c-122">When initialized, the array pointed to by `characterArray()` holds "x", "y", and "z".</span></span> <span data-ttu-id="5418c-123">때문에 변수의 `characterArray` 는 `ReadOnly`초기화 된 후;는 해당 값을 변경할 수 없습니다, 새 배열을 할당할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="5418c-123">Because the variable `characterArray` is `ReadOnly`, you cannot change its value once it is initialized; that is, you cannot assign a new array to it.</span></span> <span data-ttu-id="5418c-124">그러나 하나 이상의 배열 멤버의 값을 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5418c-124">However, you can change the values of one or more of the array members.</span></span> <span data-ttu-id="5418c-125">다음 절차에 대 한 호출 `changeArrayElement`를 가리키는 배열 `characterArray()` 포함 "x", "M" 및 "z"입니다.</span><span class="sxs-lookup"><span data-stu-id="5418c-125">Following a call to the procedure `changeArrayElement`, the array pointed to by `characterArray()` holds "x", "M", and "z".</span></span>  
  
 <span data-ttu-id="5418c-126">이 프로시저 매개 변수를 선언 비슷합니다 [ByVal](../../../visual-basic/language-reference/modifiers/byval.md)를 하면 프로시저가 호출 인수 자체를 변경할 수 있지만 해당 멤버를 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5418c-126">Note that this is similar to declaring a procedure parameter to be [ByVal](../../../visual-basic/language-reference/modifiers/byval.md), which prevents the procedure from changing the calling argument itself but allows it to change its members.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5418c-127">예제</span><span class="sxs-lookup"><span data-stu-id="5418c-127">Example</span></span>  
 <span data-ttu-id="5418c-128">다음 예제에서는 정의 `ReadOnly` 직원 고용 날짜에 대 한 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="5418c-128">The following example defines a `ReadOnly` property for the date on which an employee was hired.</span></span> <span data-ttu-id="5418c-129">속성 값을 내부적으로 클래스 저장소는 `Private` 변수와 유일한 코드 클래스 내에서 해당 값을 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5418c-129">The class stores the property value internally as a `Private` variable, and only code inside the class can change that value.</span></span> <span data-ttu-id="5418c-130">그러나 속성은 `Public`, 클래스에 액세스할 수 있는 모든 코드는 속성을 읽을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5418c-130">However, the property is `Public`, and any code that can access the class can read the property.</span></span>  
  
 [!code-vb[VbVbalrKeywords#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrKeywords/VB/Class1.vb#4)]  
  
 <span data-ttu-id="5418c-131">`ReadOnly` 한정자는 다음 컨텍스트에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5418c-131">The `ReadOnly` modifier can be used in these contexts:</span></span>  
  
 [<span data-ttu-id="5418c-132">Dim 문</span><span class="sxs-lookup"><span data-stu-id="5418c-132">Dim Statement</span></span>](../../../visual-basic/language-reference/statements/dim-statement.md)  
  
 [<span data-ttu-id="5418c-133">Property 문</span><span class="sxs-lookup"><span data-stu-id="5418c-133">Property Statement</span></span>](../../../visual-basic/language-reference/statements/property-statement.md)  
  
## <a name="see-also"></a><span data-ttu-id="5418c-134">참고자료</span><span class="sxs-lookup"><span data-stu-id="5418c-134">See also</span></span>

- [<span data-ttu-id="5418c-135">WriteOnly</span><span class="sxs-lookup"><span data-stu-id="5418c-135">WriteOnly</span></span>](../../../visual-basic/language-reference/modifiers/writeonly.md)
- [<span data-ttu-id="5418c-136">C++ 키워드</span><span class="sxs-lookup"><span data-stu-id="5418c-136">Keywords</span></span>](../../../visual-basic/language-reference/keywords/index.md)
