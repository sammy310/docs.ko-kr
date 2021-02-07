---
description: '자세한 정보: 정적 (Visual Basic)'
title: 정적
ms.date: 07/20/2015
f1_keywords:
- vb.Static
helpviewer_keywords:
- static modifier
- Static keyword [Visual Basic]
ms.assetid: 19013910-4658-47b6-a22e-1744b527979e
ms.openlocfilehash: 03c2e3f64ac9052a0c604b8bc34782af16edbf34
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99700743"
---
# <a name="static-visual-basic"></a><span data-ttu-id="e25aa-103">Static(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="e25aa-103">Static (Visual Basic)</span></span>

<span data-ttu-id="e25aa-104">선언 된 지역 변수를 하나 이상 유지 하 고 선언 된 프로시저가 종료 된 후에 최신 값을 유지 하도록 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="e25aa-104">Specifies that one or more declared local variables are to continue to exist and retain their latest values after termination of the procedure in which they are declared.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e25aa-105">설명</span><span class="sxs-lookup"><span data-stu-id="e25aa-105">Remarks</span></span>  

 <span data-ttu-id="e25aa-106">일반적으로 프로시저의 지역 변수는 프로시저가 중지 되는 즉시 존재 하지 않게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e25aa-106">Normally, a local variable in a procedure ceases to exist as soon as the procedure stops.</span></span> <span data-ttu-id="e25aa-107">정적 변수는 계속 존재 하며 최신 값을 유지 합니다.</span><span class="sxs-lookup"><span data-stu-id="e25aa-107">A static variable continues to exist and retains its most recent value.</span></span> <span data-ttu-id="e25aa-108">다음에 코드가 프로시저를 호출 하면 변수가 다시 초기화 되지 않고 사용자가 할당 한 최신 값을 유지 합니다.</span><span class="sxs-lookup"><span data-stu-id="e25aa-108">The next time your code calls the procedure, the variable is not reinitialized, and it still holds the latest value that you assigned to it.</span></span> <span data-ttu-id="e25aa-109">정적 변수는 정의 된 클래스 또는 모듈의 수명 동안 계속 존재 합니다.</span><span class="sxs-lookup"><span data-stu-id="e25aa-109">A static variable continues to exist for the lifetime of the class or module that it is defined in.</span></span>  
  
## <a name="rules"></a><span data-ttu-id="e25aa-110">규칙</span><span class="sxs-lookup"><span data-stu-id="e25aa-110">Rules</span></span>  
  
- <span data-ttu-id="e25aa-111">**선언 컨텍스트.**</span><span class="sxs-lookup"><span data-stu-id="e25aa-111">**Declaration Context.**</span></span> <span data-ttu-id="e25aa-112">`Static`로컬 변수에만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e25aa-112">You can use `Static` only on local variables.</span></span> <span data-ttu-id="e25aa-113">즉, 변수에 대 한 선언 컨텍스트는 프로시저 `Static` 또는 프로시저의 블록 이어야 하며 소스 파일, 네임 스페이스, 클래스, 구조체 또는 모듈 일 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="e25aa-113">This means the declaration context for a `Static` variable must be a procedure or a block in a procedure, and it cannot be a source file, namespace, class, structure, or module.</span></span>  
  
     <span data-ttu-id="e25aa-114">`Static`구조 프로시저 내에서는를 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="e25aa-114">You cannot use `Static` inside a structure procedure.</span></span>  
  
- <span data-ttu-id="e25aa-115">지역 변수의 데이터 형식은 `Static` 유추할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="e25aa-115">The data types of `Static` local variables cannot be inferred.</span></span> <span data-ttu-id="e25aa-116">자세한 내용은 [지역 형식 유추](../../programming-guide/language-features/variables/local-type-inference.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="e25aa-116">For more information, see [Local Type Inference](../../programming-guide/language-features/variables/local-type-inference.md).</span></span>  
  
- <span data-ttu-id="e25aa-117">**결합된 한정자.**</span><span class="sxs-lookup"><span data-stu-id="e25aa-117">**Combined Modifiers.**</span></span> <span data-ttu-id="e25aa-118">`Static` `ReadOnly` `Shadows` 동일한 선언에서, 또는를 함께 지정할 수 없습니다 `Shared` .</span><span class="sxs-lookup"><span data-stu-id="e25aa-118">You cannot specify `Static` together with `ReadOnly`, `Shadows`, or `Shared` in the same declaration.</span></span>  
  
## <a name="behavior"></a><span data-ttu-id="e25aa-119">동작</span><span class="sxs-lookup"><span data-stu-id="e25aa-119">Behavior</span></span>  

 <span data-ttu-id="e25aa-120">프로시저에서 정적 변수를 선언 하는 경우 `Shared` 전체 응용 프로그램에 대해 정적 변수의 복사본을 하나만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e25aa-120">When you declare a static variable in a `Shared` procedure, only one copy of the static variable is available for the whole application.</span></span> <span data-ttu-id="e25aa-121">클래스 `Shared` 의 인스턴스를 가리키는 변수가 아니라 클래스 이름을 사용 하 여 프로시저를 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="e25aa-121">You call a `Shared` procedure by using the class name, not a variable that points to an instance of the class.</span></span>  
  
 <span data-ttu-id="e25aa-122">프로시저가 아닌 프로시저에서 정적 변수를 선언 하는 경우 `Shared` 클래스의 각 인스턴스에 대해 변수의 복사본을 하나만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e25aa-122">When you declare a static variable in a procedure that isn't `Shared`, only one copy of the variable is available for each instance of the class.</span></span> <span data-ttu-id="e25aa-123">클래스의 특정 인스턴스를 가리키는 변수를 사용 하 여 비공유 프로시저를 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="e25aa-123">You call a non-shared procedure by using a variable that points to a specific instance of the class.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e25aa-124">예제</span><span class="sxs-lookup"><span data-stu-id="e25aa-124">Example</span></span>  

 <span data-ttu-id="e25aa-125">다음 예에서는 `Static`의 사용법을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="e25aa-125">The following example demonstrates the use of `Static`.</span></span>  
  
 [!code-vb[VbVbalrKeywords#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrKeywords/VB/Class1.vb#5)]  
  
 <span data-ttu-id="e25aa-126">`Static`변수는 `totalSales` 한 번만 0으로 초기화 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e25aa-126">The `Static` variable `totalSales` is initialized to 0 only one time.</span></span> <span data-ttu-id="e25aa-127">를 입력할 때마다 `updateSales` 에서 `totalSales` 가장 최근의 값을 계산 합니다.</span><span class="sxs-lookup"><span data-stu-id="e25aa-127">Each time that you enter `updateSales`, `totalSales` still has the most recent value that you calculated for it.</span></span>  
  
 <span data-ttu-id="e25aa-128">`Static`이 컨텍스트에서는 한정자를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e25aa-128">The `Static` modifier can be used in this context:</span></span>  
  
 [<span data-ttu-id="e25aa-129">Dim 문</span><span class="sxs-lookup"><span data-stu-id="e25aa-129">Dim Statement</span></span>](../statements/dim-statement.md)  
  
## <a name="see-also"></a><span data-ttu-id="e25aa-130">참고 항목</span><span class="sxs-lookup"><span data-stu-id="e25aa-130">See also</span></span>

- [<span data-ttu-id="e25aa-131">Overloads</span><span class="sxs-lookup"><span data-stu-id="e25aa-131">Shadows</span></span>](shadows.md)
- [<span data-ttu-id="e25aa-132">공유</span><span class="sxs-lookup"><span data-stu-id="e25aa-132">Shared</span></span>](shared.md)
- [<span data-ttu-id="e25aa-133">Visual Basic의 수명</span><span class="sxs-lookup"><span data-stu-id="e25aa-133">Lifetime in Visual Basic</span></span>](../../programming-guide/language-features/declared-elements/lifetime.md)
- [<span data-ttu-id="e25aa-134">변수 선언</span><span class="sxs-lookup"><span data-stu-id="e25aa-134">Variable Declaration</span></span>](../../programming-guide/language-features/variables/variable-declaration.md)
- [<span data-ttu-id="e25aa-135">구조체</span><span class="sxs-lookup"><span data-stu-id="e25aa-135">Structures</span></span>](../../programming-guide/language-features/data-types/structures.md)
- [<span data-ttu-id="e25aa-136">지역 형식 유추</span><span class="sxs-lookup"><span data-stu-id="e25aa-136">Local Type Inference</span></span>](../../programming-guide/language-features/variables/local-type-inference.md)
- [<span data-ttu-id="e25aa-137">개체 및 클래스</span><span class="sxs-lookup"><span data-stu-id="e25aa-137">Objects and Classes</span></span>](../../programming-guide/language-features/objects-and-classes/index.md)
