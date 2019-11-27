---
title: '방법: 개체 이니셜라이저를 사용하여 개체 선언'
ms.date: 07/20/2015
helpviewer_keywords:
- declaring objects using object initializer
- object initializers [Visual Basic]
- initializers [Visual Basic]
- Video How tos, Visual Basic
ms.assetid: 0f53a553-efd6-466d-80bf-6b679e5cd174
ms.openlocfilehash: ae04d338b61027c3917ad3a7f62ff40f0a95e53e
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/22/2019
ms.locfileid: "74347130"
---
# <a name="how-to-declare-an-object-by-using-an-object-initializer-visual-basic"></a><span data-ttu-id="5037b-102">방법: 개체 이니셜라이저를 사용하여 개체 선언(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="5037b-102">How to: Declare an Object by Using an Object Initializer (Visual Basic)</span></span>
<span data-ttu-id="5037b-103">개체 이니셜라이저를 사용 하면 단일 문에서 클래스의 인스턴스를 선언 하 고 인스턴스화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5037b-103">Object initializers enable you to declare and instantiate an instance of a class in a single statement.</span></span> <span data-ttu-id="5037b-104">또한 매개 변수가 있는 생성자를 호출 하지 않고 인스턴스의 멤버를 한 번에 하나 이상 초기화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5037b-104">In addition, you can initialize one or more members of the instance at the same time, without invoking a parameterized constructor.</span></span>  
  
 <span data-ttu-id="5037b-105">개체 이니셜라이저를 사용 하 여 명명 된 형식의 인스턴스를 만드는 경우 클래스에 대 한 매개 변수가 없는 생성자가 호출 된 다음 지정 된 순서로 지정 된 멤버를 초기화 합니다.</span><span class="sxs-lookup"><span data-stu-id="5037b-105">When you use an object initializer to create an instance of a named type, the parameterless constructor for the class is called, followed by initialization of designated members in the order you specify.</span></span>  
  
 <span data-ttu-id="5037b-106">다음 절차에서는 세 가지 방법으로 `Student` 클래스의 인스턴스를 만드는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="5037b-106">The following procedure shows how to create an instance of a `Student` class in three different ways.</span></span> <span data-ttu-id="5037b-107">클래스에는 이름, 성 및 클래스 year 속성이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5037b-107">The class has first name, last name, and class year properties, among others.</span></span> <span data-ttu-id="5037b-108">세 선언 각각은 속성 `First` "Michael"로 설정 되 고, 속성 `Last` "Tucker"로 설정 되 고, 다른 모든 멤버가 기본값으로 설정 된 `Student`의 새 인스턴스를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="5037b-108">Each of the three declarations creates a new instance of `Student`, with property `First` set to "Michael", property `Last` set to "Tucker", and all other members set to their default values.</span></span> <span data-ttu-id="5037b-109">프로시저의 각 선언 결과는 개체 이니셜라이저를 사용 하지 않는 다음 예제와 동일 합니다.</span><span class="sxs-lookup"><span data-stu-id="5037b-109">The result of each declaration in the procedure is equivalent to the following example, which does not use an object initializer.</span></span>  
  
 [!code-vb[VbVbalrObjectInit#20](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrObjectInit/VB/Class2.vb#20)]  
  
 <span data-ttu-id="5037b-110">`Student` 클래스의 구현에 대 한 자세한 내용은 [방법: 항목 목록 만들기](../../../../visual-basic/programming-guide/concepts/linq/how-to-create-a-list-of-items.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="5037b-110">For an implementation of the `Student` class, see [How to: Create a List of Items](../../../../visual-basic/programming-guide/concepts/linq/how-to-create-a-list-of-items.md).</span></span> <span data-ttu-id="5037b-111">해당 항목에서 코드를 복사 하 여 클래스를 설정 하 고 작업할 `Student` 개체 목록을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5037b-111">You can copy the code from that topic to set up the class and create a list of `Student` objects to work with.</span></span>  
  
### <a name="to-create-an-object-of-a-named-class-by-using-an-object-initializer"></a><span data-ttu-id="5037b-112">개체 이니셜라이저를 사용 하 여 명명 된 클래스의 개체를 만들려면</span><span class="sxs-lookup"><span data-stu-id="5037b-112">To create an object of a named class by using an object initializer</span></span>  
  
1. <span data-ttu-id="5037b-113">생성자를 사용 하기 위해 계획 한 것 처럼 선언을 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="5037b-113">Begin the declaration as if you planned to use a constructor.</span></span>  
  
     `Dim student1 As New Student`  
  
2. <span data-ttu-id="5037b-114">`With`키워드를 입력 한 다음 중괄호에 초기화 목록을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="5037b-114">Type the keyword `With`, followed by an initialization list in braces.</span></span>  
  
     `Dim student1 As New Student With { <initialization list> }`  
  
3. <span data-ttu-id="5037b-115">초기화 목록에서 초기화 하려는 각 속성을 포함 하 고 초기 값을 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="5037b-115">In the initialization list, include each property that you want to initialize and assign an initial value to it.</span></span> <span data-ttu-id="5037b-116">속성 이름 앞에는 마침표가와 야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5037b-116">The name of the property is preceded by a period.</span></span>  
  
     [!code-vb[VbVbalrObjectInit#21](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrObjectInit/VB/Class2.vb#21)]  
  
     <span data-ttu-id="5037b-117">클래스의 멤버를 하나 이상 초기화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5037b-117">You can initialize one or more members of the class.</span></span>  
  
4. <span data-ttu-id="5037b-118">또는 클래스의 새 인스턴스를 선언 하 고 여기에 값을 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5037b-118">Alternatively, you can declare a new instance of the class and then assign a value to it.</span></span> <span data-ttu-id="5037b-119">먼저 `Student`의 인스턴스를 선언 합니다.</span><span class="sxs-lookup"><span data-stu-id="5037b-119">First, declare an instance of `Student`:</span></span>  
  
     `Dim student2 As Student`  
  
5. <span data-ttu-id="5037b-120">일반적인 방법으로 `Student` 인스턴스 만들기를 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="5037b-120">Begin the creation of an instance of `Student` in the normal way.</span></span>  
  
     `Dim student2 As Student = New Student`  
  
6. <span data-ttu-id="5037b-121">`With`를 입력 한 다음 개체 이니셜라이저를 입력 하 여 새 인스턴스의 멤버를 하나 이상 초기화 합니다.</span><span class="sxs-lookup"><span data-stu-id="5037b-121">Type `With` and then an object initializer to initialize one or more members of the new instance.</span></span>  
  
     [!code-vb[VbVbalrObjectInit#22](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrObjectInit/VB/Class2.vb#22)]  
  
7. <span data-ttu-id="5037b-122">`As Student`를 생략 하 여 이전 단계에서 정의를 단순화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5037b-122">You can simplify the definition in the previous step by omitting `As Student`.</span></span> <span data-ttu-id="5037b-123">이 작업을 수행 하는 경우 컴파일러는 `student3` 로컬 형식 유추를 사용 하 여 `Student` 인스턴스인지를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="5037b-123">If you do this, the compiler determines that `student3` is an instance of `Student` by using local type inference.</span></span>  
  
     [!code-vb[VbVbalrObjectInit#23](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrObjectInit/VB/Class2.vb#23)]  
  
     <span data-ttu-id="5037b-124">자세한 내용은 [지역 형식 유추](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="5037b-124">For more information, see [Local Type Inference](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5037b-125">참고 항목</span><span class="sxs-lookup"><span data-stu-id="5037b-125">See also</span></span>

- [<span data-ttu-id="5037b-126">지역 형식 유추</span><span class="sxs-lookup"><span data-stu-id="5037b-126">Local Type Inference</span></span>](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)
- [<span data-ttu-id="5037b-127">방법: 항목 목록 만들기</span><span class="sxs-lookup"><span data-stu-id="5037b-127">How to: Create a List of Items</span></span>](../../../../visual-basic/programming-guide/concepts/linq/how-to-create-a-list-of-items.md)
- [<span data-ttu-id="5037b-128">개체 이니셜라이저: 명명된 형식과 익명 형식</span><span class="sxs-lookup"><span data-stu-id="5037b-128">Object Initializers: Named and Anonymous Types</span></span>](../../../../visual-basic/programming-guide/language-features/objects-and-classes/object-initializers-named-and-anonymous-types.md)
- [<span data-ttu-id="5037b-129">익명 형식</span><span class="sxs-lookup"><span data-stu-id="5037b-129">Anonymous Types</span></span>](../../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md)
