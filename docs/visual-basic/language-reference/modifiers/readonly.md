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
ms.openlocfilehash: 748c38835cec83cefe54535f90d40ec3a030e4f4
ms.sourcegitcommit: d7c298f6c2e3aab0c7498bfafc0a0a94ea1fe23e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/10/2019
ms.locfileid: "72250386"
---
# <a name="readonly-visual-basic"></a><span data-ttu-id="d4146-102">ReadOnly(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="d4146-102">ReadOnly (Visual Basic)</span></span>
<span data-ttu-id="d4146-103">변수 또는 속성을 읽을 수 있지만 쓸 수는 없도록 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="d4146-103">Specifies that a variable or property can be read but not written.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d4146-104">설명</span><span class="sxs-lookup"><span data-stu-id="d4146-104">Remarks</span></span>  
  
## <a name="rules"></a><span data-ttu-id="d4146-105">규칙</span><span class="sxs-lookup"><span data-stu-id="d4146-105">Rules</span></span>  
  
- <span data-ttu-id="d4146-106">**선언 컨텍스트입니다.**</span><span class="sxs-lookup"><span data-stu-id="d4146-106">**Declaration Context.**</span></span> <span data-ttu-id="d4146-107">`ReadOnly`는 모듈 수준에서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d4146-107">You can use `ReadOnly` only at module level.</span></span> <span data-ttu-id="d4146-108">즉, `ReadOnly` 요소의 선언 컨텍스트는 클래스, 구조체 또는 모듈 이어야 하며 소스 파일, 네임 스페이스 또는 프로시저일 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d4146-108">This means the declaration context for a `ReadOnly` element must be a class, structure, or module, and cannot be a source file, namespace, or procedure.</span></span>  
  
- <span data-ttu-id="d4146-109">**결합 된 한정자입니다.**</span><span class="sxs-lookup"><span data-stu-id="d4146-109">**Combined Modifiers.**</span></span> <span data-ttu-id="d4146-110">동일한 선언에서-0을 `Static`과 함께 @no__t 지정할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d4146-110">You cannot specify `ReadOnly` together with `Static` in the same declaration.</span></span>  
  
- <span data-ttu-id="d4146-111">**값 할당**</span><span class="sxs-lookup"><span data-stu-id="d4146-111">**Assigning a Value.**</span></span> <span data-ttu-id="d4146-112">@No__t-0 속성을 사용 하는 코드는 해당 값을 설정할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d4146-112">Code consuming a `ReadOnly` property cannot set its value.</span></span> <span data-ttu-id="d4146-113">하지만 기본 저장소에 대 한 액세스 권한이 있는 코드는 언제 든 지 값을 할당 하거나 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d4146-113">But code that has access to the underlying storage can assign or change the value at any time.</span></span>  
  
     <span data-ttu-id="d4146-114">선언 또는 정의 된 클래스 또는 구조체의 생성자 에서만 `ReadOnly` 변수에 값을 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d4146-114">You can assign a value to a `ReadOnly` variable only in its declaration or in the constructor of a class or structure in which it is defined.</span></span>  
  
## <a name="when-to-use-a-readonly-variable"></a><span data-ttu-id="d4146-115">ReadOnly 변수를 사용 하는 경우</span><span class="sxs-lookup"><span data-stu-id="d4146-115">When to Use a ReadOnly Variable</span></span>  
 <span data-ttu-id="d4146-116">상수 값을 선언 하 고 할당 하는 데 [Const 문을](../../../visual-basic/language-reference/statements/const-statement.md) 사용할 수 없는 경우가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d4146-116">There are situations in which you cannot use a [Const Statement](../../../visual-basic/language-reference/statements/const-statement.md) to declare and assign a constant value.</span></span> <span data-ttu-id="d4146-117">예를 들어 `Const` 문은 할당 하려는 데이터 형식을 허용 하지 않거나 컴파일 타임에 상수 식으로 값을 계산할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d4146-117">For example, the `Const` statement might not accept the data type you want to assign, or you might not be able to compute the value at compile time with a constant expression.</span></span> <span data-ttu-id="d4146-118">컴파일 시간에 값을 알 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d4146-118">You might not even know the value at compile time.</span></span> <span data-ttu-id="d4146-119">이 경우 `ReadOnly` 변수를 사용 하 여 상수 값을 저장할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d4146-119">In these cases, you can use a `ReadOnly` variable to hold a constant value.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="d4146-120">변수의 데이터 형식이 배열 또는 클래스 인스턴스와 같은 참조 형식이 면 변수 자체가-0 @no__t 경우에도 해당 멤버를 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d4146-120">If the data type of the variable is a reference type, such as an array or a class instance, its members can be changed even if the variable itself is `ReadOnly`.</span></span> <span data-ttu-id="d4146-121">다음은 이에 대한 예입니다.</span><span class="sxs-lookup"><span data-stu-id="d4146-121">The following example illustrates this.</span></span>  
  
 ```vb
 ReadOnly characterArray() As Char = {"x"c, "y"c, "z"c}
 Sub ChangeArrayElement()
     characterArray(1) = "M"c
 End Sub
 ```
  
 <span data-ttu-id="d4146-122">초기화 될 때 `characterArray()`이 가리키는 배열은 "x", "y" 및 "z"를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="d4146-122">When initialized, the array pointed to by `characterArray()` holds "x", "y", and "z".</span></span> <span data-ttu-id="d4146-123">변수 `characterArray`은 @no__t 이므로 값을 초기화 한 후에는 변경할 수 없습니다. 즉, 새 배열을 할당할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d4146-123">Because the variable `characterArray` is `ReadOnly`, you cannot change its value once it is initialized; that is, you cannot assign a new array to it.</span></span> <span data-ttu-id="d4146-124">그러나 하나 이상의 배열 멤버의 값을 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d4146-124">However, you can change the values of one or more of the array members.</span></span> <span data-ttu-id="d4146-125">@No__t-0 프로시저를 호출 하 고 `characterArray()`에서 가리키는 배열은 "x", "M" 및 "z"를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="d4146-125">Following a call to the procedure `ChangeArrayElement`, the array pointed to by `characterArray()` holds "x", "M", and "z".</span></span>
  
 <span data-ttu-id="d4146-126">프로시저 매개 변수를 [ByVal](byval.md)로 선언 하는 것과 유사 합니다. 그러면 프로시저에서 호출 인수 자체를 변경 하는 것이 아니라 해당 멤버를 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d4146-126">Note that this is similar to declaring a procedure parameter to be [ByVal](byval.md), which prevents the procedure from changing the calling argument itself but allows it to change its members.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d4146-127">예제</span><span class="sxs-lookup"><span data-stu-id="d4146-127">Example</span></span>

<span data-ttu-id="d4146-128">다음 예에서는 직원이 고용 된 날짜에 대 한 `ReadOnly` 속성을 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="d4146-128">The following example defines a `ReadOnly` property for the date on which an employee was hired.</span></span> <span data-ttu-id="d4146-129">클래스는 내부적으로 `Private` 변수로 속성 값을 저장 하 고 클래스 내의 코드만이 값을 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d4146-129">The class stores the property value internally as a `Private` variable, and only code inside the class can change that value.</span></span> <span data-ttu-id="d4146-130">그러나 속성은 `Public` 이며 클래스에 액세스할 수 있는 모든 코드는 속성을 읽을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d4146-130">However, the property is `Public`, and any code that can access the class can read the property.</span></span>
  
[!code-vb[VbVbalrKeywords#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrKeywords/VB/Class1.vb#4)]
  
<span data-ttu-id="d4146-131">`ReadOnly` 한정자는 다음 컨텍스트에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d4146-131">The `ReadOnly` modifier can be used in these contexts:</span></span>
  
- [<span data-ttu-id="d4146-132">Dim 문</span><span class="sxs-lookup"><span data-stu-id="d4146-132">Dim Statement</span></span>](../statements/dim-statement.md) 
- [<span data-ttu-id="d4146-133">Property 문</span><span class="sxs-lookup"><span data-stu-id="d4146-133">Property Statement</span></span>](../statements/property-statement.md)  
  
## <a name="see-also"></a><span data-ttu-id="d4146-134">참조</span><span class="sxs-lookup"><span data-stu-id="d4146-134">See also</span></span>

- [<span data-ttu-id="d4146-135">WriteOnly</span><span class="sxs-lookup"><span data-stu-id="d4146-135">WriteOnly</span></span>](writeonly.md)
- [<span data-ttu-id="d4146-136">C++ 키워드</span><span class="sxs-lookup"><span data-stu-id="d4146-136">Keywords</span></span>](../keywords/index.md)
