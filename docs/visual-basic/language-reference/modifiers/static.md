---
title: 정적
ms.date: 07/20/2015
f1_keywords:
- vb.Static
helpviewer_keywords:
- static modifier
- Static keyword [Visual Basic]
ms.assetid: 19013910-4658-47b6-a22e-1744b527979e
ms.openlocfilehash: f020756466888f51298abb423997906ddc7caff7
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/22/2019
ms.locfileid: "74350756"
---
# <a name="static-visual-basic"></a><span data-ttu-id="a2053-102">Static(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="a2053-102">Static (Visual Basic)</span></span>
<span data-ttu-id="a2053-103">선언 된 지역 변수를 하나 이상 유지 하 고 선언 된 프로시저가 종료 된 후에 최신 값을 유지 하도록 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="a2053-103">Specifies that one or more declared local variables are to continue to exist and retain their latest values after termination of the procedure in which they are declared.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a2053-104">주의</span><span class="sxs-lookup"><span data-stu-id="a2053-104">Remarks</span></span>  
 <span data-ttu-id="a2053-105">일반적으로 프로시저의 지역 변수는 프로시저가 중지 되는 즉시 존재 하지 않게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a2053-105">Normally, a local variable in a procedure ceases to exist as soon as the procedure stops.</span></span> <span data-ttu-id="a2053-106">정적 변수는 계속 존재 하며 최신 값을 유지 합니다.</span><span class="sxs-lookup"><span data-stu-id="a2053-106">A static variable continues to exist and retains its most recent value.</span></span> <span data-ttu-id="a2053-107">다음에 코드가 프로시저를 호출 하면 변수가 다시 초기화 되지 않고 사용자가 할당 한 최신 값을 유지 합니다.</span><span class="sxs-lookup"><span data-stu-id="a2053-107">The next time your code calls the procedure, the variable is not reinitialized, and it still holds the latest value that you assigned to it.</span></span> <span data-ttu-id="a2053-108">정적 변수는 정의 된 클래스 또는 모듈의 수명 동안 계속 존재 합니다.</span><span class="sxs-lookup"><span data-stu-id="a2053-108">A static variable continues to exist for the lifetime of the class or module that it is defined in.</span></span>  
  
## <a name="rules"></a><span data-ttu-id="a2053-109">규칙</span><span class="sxs-lookup"><span data-stu-id="a2053-109">Rules</span></span>  
  
- <span data-ttu-id="a2053-110">**선언 컨텍스트입니다.**</span><span class="sxs-lookup"><span data-stu-id="a2053-110">**Declaration Context.**</span></span> <span data-ttu-id="a2053-111">`Static`는 지역 변수에만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a2053-111">You can use `Static` only on local variables.</span></span> <span data-ttu-id="a2053-112">즉, `Static` 변수에 대 한 선언 컨텍스트는 프로시저 또는 프로시저의 블록 이어야 하며 소스 파일, 네임 스페이스, 클래스, 구조체 또는 모듈 일 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a2053-112">This means the declaration context for a `Static` variable must be a procedure or a block in a procedure, and it cannot be a source file, namespace, class, structure, or module.</span></span>  
  
     <span data-ttu-id="a2053-113">구조 프로시저 내에서는 `Static`를 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a2053-113">You cannot use `Static` inside a structure procedure.</span></span>  
  
- <span data-ttu-id="a2053-114">`Static` 지역 변수의 데이터 형식은 유추할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a2053-114">The data types of `Static` local variables cannot be inferred.</span></span> <span data-ttu-id="a2053-115">자세한 내용은 [지역 형식 유추](../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="a2053-115">For more information, see [Local Type Inference](../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md).</span></span>  
  
- <span data-ttu-id="a2053-116">**결합 된 한정자입니다.**</span><span class="sxs-lookup"><span data-stu-id="a2053-116">**Combined Modifiers.**</span></span> <span data-ttu-id="a2053-117">동일한 선언에서 `ReadOnly`, `Shadows`또는 `Shared`와 함께 `Static`를 지정할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a2053-117">You cannot specify `Static` together with `ReadOnly`, `Shadows`, or `Shared` in the same declaration.</span></span>  
  
## <a name="behavior"></a><span data-ttu-id="a2053-118">동작</span><span class="sxs-lookup"><span data-stu-id="a2053-118">Behavior</span></span>  
 <span data-ttu-id="a2053-119">`Shared` 프로시저에서 정적 변수를 선언 하는 경우 전체 응용 프로그램에 대해 정적 변수의 복사본을 하나만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a2053-119">When you declare a static variable in a `Shared` procedure, only one copy of the static variable is available for the whole application.</span></span> <span data-ttu-id="a2053-120">클래스의 인스턴스를 가리키는 변수가 아니라 클래스 이름을 사용 하 여 `Shared` 프로시저를 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="a2053-120">You call a `Shared` procedure by using the class name, not a variable that points to an instance of the class.</span></span>  
  
 <span data-ttu-id="a2053-121">`Shared`하지 않는 프로시저에서 정적 변수를 선언 하는 경우 클래스의 각 인스턴스에 대해 변수의 복사본 하나만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a2053-121">When you declare a static variable in a procedure that isn't `Shared`, only one copy of the variable is available for each instance of the class.</span></span> <span data-ttu-id="a2053-122">클래스의 특정 인스턴스를 가리키는 변수를 사용 하 여 비공유 프로시저를 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="a2053-122">You call a non-shared procedure by using a variable that points to a specific instance of the class.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a2053-123">예제</span><span class="sxs-lookup"><span data-stu-id="a2053-123">Example</span></span>  
 <span data-ttu-id="a2053-124">다음 예에서는 `Static`의 사용법을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="a2053-124">The following example demonstrates the use of `Static`.</span></span>  
  
 [!code-vb[VbVbalrKeywords#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrKeywords/VB/Class1.vb#5)]  
  
 <span data-ttu-id="a2053-125">`Static` 변수 `totalSales` 0으로 한 번만 초기화 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a2053-125">The `Static` variable `totalSales` is initialized to 0 only one time.</span></span> <span data-ttu-id="a2053-126">`updateSales`를 입력할 때마다 `totalSales`에 대해 계산 된 최신 값이 계속 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a2053-126">Each time that you enter `updateSales`, `totalSales` still has the most recent value that you calculated for it.</span></span>  
  
 <span data-ttu-id="a2053-127">이 컨텍스트에서는 `Static` 한정자를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a2053-127">The `Static` modifier can be used in this context:</span></span>  
  
 [<span data-ttu-id="a2053-128">Dim 문</span><span class="sxs-lookup"><span data-stu-id="a2053-128">Dim Statement</span></span>](../../../visual-basic/language-reference/statements/dim-statement.md)  
  
## <a name="see-also"></a><span data-ttu-id="a2053-129">참고 항목</span><span class="sxs-lookup"><span data-stu-id="a2053-129">See also</span></span>

- [<span data-ttu-id="a2053-130">Shadows</span><span class="sxs-lookup"><span data-stu-id="a2053-130">Shadows</span></span>](../../../visual-basic/language-reference/modifiers/shadows.md)
- [<span data-ttu-id="a2053-131">공유</span><span class="sxs-lookup"><span data-stu-id="a2053-131">Shared</span></span>](../../../visual-basic/language-reference/modifiers/shared.md)
- [<span data-ttu-id="a2053-132">Visual Basic 수명</span><span class="sxs-lookup"><span data-stu-id="a2053-132">Lifetime in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/declared-elements/lifetime.md)
- [<span data-ttu-id="a2053-133">변수 선언</span><span class="sxs-lookup"><span data-stu-id="a2053-133">Variable Declaration</span></span>](../../../visual-basic/programming-guide/language-features/variables/variable-declaration.md)
- [<span data-ttu-id="a2053-134">구조체</span><span class="sxs-lookup"><span data-stu-id="a2053-134">Structures</span></span>](../../../visual-basic/programming-guide/language-features/data-types/structures.md)
- [<span data-ttu-id="a2053-135">지역 형식 유추</span><span class="sxs-lookup"><span data-stu-id="a2053-135">Local Type Inference</span></span>](../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)
- [<span data-ttu-id="a2053-136">개체 및 클래스</span><span class="sxs-lookup"><span data-stu-id="a2053-136">Objects and Classes</span></span>](../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)
