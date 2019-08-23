---
title: New 연산자(Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.new
- vb.NewConstraint
helpviewer_keywords:
- constraints, Visual Basic generic types
- generics [Visual Basic], constraints
- constraints, New keyword [Visual Basic]
- New constraint
- New keyword [Visual Basic]
ms.assetid: d7d566d7-fe0e-4336-91f7-641a542de4d0
ms.openlocfilehash: 36cf71529b1f81c27881638d788117222c37171d
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/22/2019
ms.locfileid: "69955874"
---
# <a name="new-operator-visual-basic"></a><span data-ttu-id="07536-102">New 연산자(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="07536-102">New Operator (Visual Basic)</span></span>
<span data-ttu-id="07536-103">새 개체 `New` 인스턴스를 만들거나, 형식 매개 변수에 대 한 생성자 제약 조건을 지정 하거나, `Sub` 프로시저를 클래스 생성자로 식별 하는 절을 소개 합니다.</span><span class="sxs-lookup"><span data-stu-id="07536-103">Introduces a `New` clause to create a new object instance, specifies a constructor constraint on a type parameter, or identifies a `Sub` procedure as a class constructor.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="07536-104">설명</span><span class="sxs-lookup"><span data-stu-id="07536-104">Remarks</span></span>  
 <span data-ttu-id="07536-105">선언 또는 대입문에서 절은 `New` 인스턴스를 만들 수 있는 정의 된 클래스를 지정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="07536-105">In a declaration or assignment statement, a `New` clause must specify a defined class from which the instance can be created.</span></span> <span data-ttu-id="07536-106">즉, 클래스가 호출 코드에서 액세스할 수 있는 하나 이상의 생성자를 노출 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="07536-106">This means that the class must expose one or more constructors that the calling code can access.</span></span>  
  
 <span data-ttu-id="07536-107">선언 문이나 대입문에서 `New` 절을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="07536-107">You can use a `New` clause in a declaration statement or an assignment statement.</span></span> <span data-ttu-id="07536-108">문이 실행 될 때 지정한 클래스의 적절 한 생성자를 호출 하 여 제공한 인수를 전달 합니다.</span><span class="sxs-lookup"><span data-stu-id="07536-108">When the statement runs, it calls the appropriate constructor of the specified class, passing any arguments you have supplied.</span></span> <span data-ttu-id="07536-109">다음 예제에서는 두 개의 생성자를 사용 하는 `Customer` 클래스의 인스턴스를 만듭니다. 하나는 매개 변수를 사용 하지 않고 다른 하나는 문자열 매개 변수를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="07536-109">The following example demonstrates this by creating instances of a `Customer` class that has two constructors, one that takes no parameters and one that takes a string parameter.</span></span>  
  
 [!code-vb[VbVbalrKeywords#11](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrKeywords/VB/Class6.vb#11)]  
  
 <span data-ttu-id="07536-110">배열은 클래스 `New` 이므로 다음 예제와 같이 새 배열 인스턴스를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="07536-110">Since arrays are classes, `New` can create a new array instance, as shown in the following examples.</span></span>  
  
 [!code-vb[VbVbalrKeywords#12](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrKeywords/VB/Class6.vb#12)]  
  
 <span data-ttu-id="07536-111">새 인스턴스를 만드는 데 필요한 메모리가 부족 한 <xref:System.OutOfMemoryException> 경우 CLR (공용 언어 런타임)에서 오류를 throw 합니다.</span><span class="sxs-lookup"><span data-stu-id="07536-111">The common language runtime (CLR) throws an <xref:System.OutOfMemoryException> error if there is insufficient memory to create the new instance.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="07536-112">키워드 `New` 는 제공 된 형식이 액세스 가능한 매개 변수가 없는 생성자를 노출 해야 하도록 지정 하기 위해 형식 매개 변수 목록에도 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="07536-112">The `New` keyword is also used in type parameter lists to specify that the supplied type must expose an accessible parameterless constructor.</span></span> <span data-ttu-id="07536-113">형식 매개 변수 및 제약 조건에 대 한 자세한 내용은 [형식 목록](../../../visual-basic/language-reference/statements/type-list.md)을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="07536-113">For more information about type parameters and constraints, see [Type List](../../../visual-basic/language-reference/statements/type-list.md).</span></span>  
  
 <span data-ttu-id="07536-114">클래스에 대 한 생성자 프로시저를 만들려면 `Sub` 프로시저 `New` 의 이름을 키워드로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="07536-114">To create a constructor procedure for a class, set the name of a `Sub` procedure to the `New` keyword.</span></span> <span data-ttu-id="07536-115">자세한 내용은 개체 수명을 [참조 하세요. 개체를 만들고 제거](../../../visual-basic/programming-guide/language-features/objects-and-classes/object-lifetime-how-objects-are-created-and-destroyed.md)하는 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="07536-115">For more information, see [Object Lifetime: How Objects Are Created and Destroyed](../../../visual-basic/programming-guide/language-features/objects-and-classes/object-lifetime-how-objects-are-created-and-destroyed.md).</span></span>  
  
 <span data-ttu-id="07536-116">`New` 키워드는 다음 컨텍스트에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="07536-116">The `New` keyword can be used in these contexts:</span></span>  
  
 [<span data-ttu-id="07536-117">Dim 문</span><span class="sxs-lookup"><span data-stu-id="07536-117">Dim Statement</span></span>](../../../visual-basic/language-reference/statements/dim-statement.md)  
  
 [<span data-ttu-id="07536-118">Of</span><span class="sxs-lookup"><span data-stu-id="07536-118">Of</span></span>](../../../visual-basic/language-reference/statements/of-clause.md)  
  
 [<span data-ttu-id="07536-119">Sub 문</span><span class="sxs-lookup"><span data-stu-id="07536-119">Sub Statement</span></span>](../../../visual-basic/language-reference/statements/sub-statement.md)  
  
## <a name="see-also"></a><span data-ttu-id="07536-120">참고자료</span><span class="sxs-lookup"><span data-stu-id="07536-120">See also</span></span>

- <xref:System.OutOfMemoryException>
- [<span data-ttu-id="07536-121">C++ 키워드</span><span class="sxs-lookup"><span data-stu-id="07536-121">Keywords</span></span>](../../../visual-basic/language-reference/keywords/index.md)
- [<span data-ttu-id="07536-122">형식 목록</span><span class="sxs-lookup"><span data-stu-id="07536-122">Type List</span></span>](../../../visual-basic/language-reference/statements/type-list.md)
- [<span data-ttu-id="07536-123">Visual Basic의 제네릭 형식</span><span class="sxs-lookup"><span data-stu-id="07536-123">Generic Types in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/data-types/generic-types.md)
- [<span data-ttu-id="07536-124">개체 수명: 개체를 만들고 제거 하는 방법</span><span class="sxs-lookup"><span data-stu-id="07536-124">Object Lifetime: How Objects Are Created and Destroyed</span></span>](../../../visual-basic/programming-guide/language-features/objects-and-classes/object-lifetime-how-objects-are-created-and-destroyed.md)
