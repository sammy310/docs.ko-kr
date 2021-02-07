---
description: '다음에 대 한 자세한 정보: New 연산자 (Visual Basic)'
title: New 연산자
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
ms.openlocfilehash: f52dd7606127c7587173de8a78e618ceb3e4681d
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99665382"
---
# <a name="new-operator-visual-basic"></a><span data-ttu-id="152b5-103">New 연산자(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="152b5-103">New Operator (Visual Basic)</span></span>

<span data-ttu-id="152b5-104">`New`새 개체 인스턴스를 만들거나, 형식 매개 변수에 대 한 생성자 제약 조건을 지정 하거나, `Sub` 프로시저를 클래스 생성자로 식별 하는 절을 소개 합니다.</span><span class="sxs-lookup"><span data-stu-id="152b5-104">Introduces a `New` clause to create a new object instance, specifies a constructor constraint on a type parameter, or identifies a `Sub` procedure as a class constructor.</span></span>

## <a name="remarks"></a><span data-ttu-id="152b5-105">설명</span><span class="sxs-lookup"><span data-stu-id="152b5-105">Remarks</span></span>

<span data-ttu-id="152b5-106">선언 또는 대입문에서 절은 인스턴스를 `New` 만들 수 있는 정의 된 클래스를 지정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="152b5-106">In a declaration or assignment statement, a `New` clause must specify a defined class from which the instance can be created.</span></span> <span data-ttu-id="152b5-107">즉, 클래스가 호출 코드에서 액세스할 수 있는 하나 이상의 생성자를 노출 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="152b5-107">This means that the class must expose one or more constructors that the calling code can access.</span></span>

<span data-ttu-id="152b5-108">`New`선언 문이나 대입문에서 절을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="152b5-108">You can use a `New` clause in a declaration statement or an assignment statement.</span></span> <span data-ttu-id="152b5-109">문이 실행 될 때 지정한 클래스의 적절 한 생성자를 호출 하 여 제공한 인수를 전달 합니다.</span><span class="sxs-lookup"><span data-stu-id="152b5-109">When the statement runs, it calls the appropriate constructor of the specified class, passing any arguments you have supplied.</span></span> <span data-ttu-id="152b5-110">다음 예제에서는 `Customer` 두 개의 생성자가 있는 클래스의 인스턴스를 만듭니다. 하나는 매개 변수를 사용 하지 않고 다른 하나는 문자열 매개 변수를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="152b5-110">The following example demonstrates this by creating instances of a `Customer` class that has two constructors, one that takes no parameters and one that takes a string parameter:</span></span>

[!code-vb[VbVbalrKeywords#11](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrKeywords/VB/Class6.vb#11)]

<span data-ttu-id="152b5-111">배열은 클래스 이므로 `New` 다음 예제와 같이 새 배열 인스턴스를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="152b5-111">Since arrays are classes, `New` can create a new array instance, as shown in the following example:</span></span>

[!code-vb[VbVbalrKeywords#12](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrKeywords/VB/Class6.vb#12)]

<span data-ttu-id="152b5-112"><xref:System.OutOfMemoryException>새 인스턴스를 만드는 데 필요한 메모리가 부족 한 경우 CLR (공용 언어 런타임)에서 오류를 throw 합니다.</span><span class="sxs-lookup"><span data-stu-id="152b5-112">The common language runtime (CLR) throws an <xref:System.OutOfMemoryException> error if there is insufficient memory to create the new instance.</span></span>

> [!NOTE]
> <span data-ttu-id="152b5-113">`New`키워드는 제공 된 형식이 액세스 가능한 매개 변수가 없는 생성자를 노출 해야 하도록 지정 하기 위해 형식 매개 변수 목록에도 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="152b5-113">The `New` keyword is also used in type parameter lists to specify that the supplied type must expose an accessible parameterless constructor.</span></span> <span data-ttu-id="152b5-114">형식 매개 변수 및 제약 조건에 대 한 자세한 내용은 [형식 목록](../statements/type-list.md)을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="152b5-114">For more information about type parameters and constraints, see [Type List](../statements/type-list.md).</span></span>

<span data-ttu-id="152b5-115">클래스에 대 한 생성자 프로시저를 만들려면 프로시저의 이름을 키워드로 설정 합니다 `Sub` `New` .</span><span class="sxs-lookup"><span data-stu-id="152b5-115">To create a constructor procedure for a class, set the name of a `Sub` procedure to the `New` keyword.</span></span> <span data-ttu-id="152b5-116">자세한 내용은 [개체 수명: 개체가 만들어지고 소멸 되는 방법](../../programming-guide/language-features/objects-and-classes/object-lifetime-how-objects-are-created-and-destroyed.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="152b5-116">For more information, see [Object Lifetime: How Objects Are Created and Destroyed](../../programming-guide/language-features/objects-and-classes/object-lifetime-how-objects-are-created-and-destroyed.md).</span></span>

<span data-ttu-id="152b5-117">`New` 키워드는 다음 컨텍스트에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="152b5-117">The `New` keyword can be used in these contexts:</span></span>

- [<span data-ttu-id="152b5-118">Dim 문</span><span class="sxs-lookup"><span data-stu-id="152b5-118">Dim Statement</span></span>](../statements/dim-statement.md)
- [<span data-ttu-id="152b5-119">으로</span><span class="sxs-lookup"><span data-stu-id="152b5-119">Of</span></span>](../statements/of-clause.md)
- [<span data-ttu-id="152b5-120">Sub 문</span><span class="sxs-lookup"><span data-stu-id="152b5-120">Sub Statement</span></span>](../statements/sub-statement.md)

## <a name="see-also"></a><span data-ttu-id="152b5-121">참고 항목</span><span class="sxs-lookup"><span data-stu-id="152b5-121">See also</span></span>

- <xref:System.OutOfMemoryException>
- [<span data-ttu-id="152b5-122">C++ 키워드</span><span class="sxs-lookup"><span data-stu-id="152b5-122">Keywords</span></span>](../keywords/index.md)
- [<span data-ttu-id="152b5-123">Type List</span><span class="sxs-lookup"><span data-stu-id="152b5-123">Type List</span></span>](../statements/type-list.md)
- [<span data-ttu-id="152b5-124">Visual Basic의 제네릭 형식</span><span class="sxs-lookup"><span data-stu-id="152b5-124">Generic Types in Visual Basic</span></span>](../../programming-guide/language-features/data-types/generic-types.md)
- [<span data-ttu-id="152b5-125">개체 수명: 개체가 만들어지고 제거되는 방법</span><span class="sxs-lookup"><span data-stu-id="152b5-125">Object Lifetime: How Objects Are Created and Destroyed</span></span>](../../programming-guide/language-features/objects-and-classes/object-lifetime-how-objects-are-created-and-destroyed.md)
