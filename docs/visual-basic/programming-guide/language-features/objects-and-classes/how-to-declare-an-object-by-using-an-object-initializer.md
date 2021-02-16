---
description: '자세히 알아보기: 방법: 개체 이니셜라이저를 사용 하 여 개체 선언 (Visual Basic)'
title: '방법: 개체 이니셜라이저를 사용하여 개체 선언'
ms.date: 07/20/2015
helpviewer_keywords:
- declaring objects using object initializer
- object initializers [Visual Basic]
- initializers [Visual Basic]
- Video How tos, Visual Basic
ms.assetid: 0f53a553-efd6-466d-80bf-6b679e5cd174
ms.openlocfilehash: 12f64dc4d1efb3ed2654084203241e6606ad4da6
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/14/2021
ms.locfileid: "100483913"
---
# <a name="how-to-declare-an-object-by-using-an-object-initializer-visual-basic"></a><span data-ttu-id="65249-103">방법: 개체 이니셜라이저를 사용하여 개체 선언(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="65249-103">How to: Declare an Object by Using an Object Initializer (Visual Basic)</span></span>

<span data-ttu-id="65249-104">개체 이니셜라이저를 사용 하면 단일 문에서 클래스의 인스턴스를 선언 하 고 인스턴스화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="65249-104">Object initializers enable you to declare and instantiate an instance of a class in a single statement.</span></span> <span data-ttu-id="65249-105">또한 매개 변수가 있는 생성자를 호출 하지 않고 인스턴스의 멤버를 한 번에 하나 이상 초기화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="65249-105">In addition, you can initialize one or more members of the instance at the same time, without invoking a parameterized constructor.</span></span>  
  
 <span data-ttu-id="65249-106">개체 이니셜라이저를 사용 하 여 명명 된 형식의 인스턴스를 만드는 경우 클래스에 대 한 매개 변수가 없는 생성자가 호출 된 다음 지정 된 순서로 지정 된 멤버를 초기화 합니다.</span><span class="sxs-lookup"><span data-stu-id="65249-106">When you use an object initializer to create an instance of a named type, the parameterless constructor for the class is called, followed by initialization of designated members in the order you specify.</span></span>  
  
 <span data-ttu-id="65249-107">다음 절차에서는 세 가지 방법으로 클래스의 인스턴스를 만드는 방법을 보여 줍니다 `Student` .</span><span class="sxs-lookup"><span data-stu-id="65249-107">The following procedure shows how to create an instance of a `Student` class in three different ways.</span></span> <span data-ttu-id="65249-108">클래스에는 이름, 성 및 클래스 year 속성이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="65249-108">The class has first name, last name, and class year properties, among others.</span></span> <span data-ttu-id="65249-109">세 선언 각각은 `Student` 속성을 `First` "Michael"로 설정 하 고, 속성을 `Last` "Tucker"로 설정 하 고, 다른 모든 멤버를 기본값으로 설정 하 여의 새 인스턴스를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="65249-109">Each of the three declarations creates a new instance of `Student`, with property `First` set to "Michael", property `Last` set to "Tucker", and all other members set to their default values.</span></span> <span data-ttu-id="65249-110">프로시저의 각 선언 결과는 개체 이니셜라이저를 사용 하지 않는 다음 예제와 동일 합니다.</span><span class="sxs-lookup"><span data-stu-id="65249-110">The result of each declaration in the procedure is equivalent to the following example, which does not use an object initializer.</span></span>  
  
 [!code-vb[VbVbalrObjectInit#20](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrObjectInit/VB/Class2.vb#20)]  
  
 <span data-ttu-id="65249-111">클래스의 구현에 대 한 자세한 `Student` 내용은 [방법: 항목 목록 만들기](../../concepts/linq/how-to-create-a-list-of-items.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="65249-111">For an implementation of the `Student` class, see [How to: Create a List of Items](../../concepts/linq/how-to-create-a-list-of-items.md).</span></span> <span data-ttu-id="65249-112">해당 항목에서 코드를 복사 하 여 클래스를 설정 하 고 사용할 개체 목록을 만들 수 있습니다 `Student` .</span><span class="sxs-lookup"><span data-stu-id="65249-112">You can copy the code from that topic to set up the class and create a list of `Student` objects to work with.</span></span>  
  
### <a name="to-create-an-object-of-a-named-class-by-using-an-object-initializer"></a><span data-ttu-id="65249-113">개체 이니셜라이저를 사용 하 여 명명 된 클래스의 개체를 만들려면</span><span class="sxs-lookup"><span data-stu-id="65249-113">To create an object of a named class by using an object initializer</span></span>  
  
1. <span data-ttu-id="65249-114">생성자를 사용 하기 위해 계획 한 것 처럼 선언을 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="65249-114">Begin the declaration as if you planned to use a constructor.</span></span>  
  
     `Dim student1 As New Student`  
  
2. <span data-ttu-id="65249-115">키워드를 입력 `With` 한 다음 중괄호에 초기화 목록을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="65249-115">Type the keyword `With`, followed by an initialization list in braces.</span></span>  
  
     `Dim student1 As New Student With { <initialization list> }`  
  
3. <span data-ttu-id="65249-116">초기화 목록에서 초기화 하려는 각 속성을 포함 하 고 초기 값을 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="65249-116">In the initialization list, include each property that you want to initialize and assign an initial value to it.</span></span> <span data-ttu-id="65249-117">속성 이름 앞에는 마침표가와 야 합니다.</span><span class="sxs-lookup"><span data-stu-id="65249-117">The name of the property is preceded by a period.</span></span>  
  
     [!code-vb[VbVbalrObjectInit#21](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrObjectInit/VB/Class2.vb#21)]  
  
     <span data-ttu-id="65249-118">클래스의 멤버를 하나 이상 초기화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="65249-118">You can initialize one or more members of the class.</span></span>  
  
4. <span data-ttu-id="65249-119">또는 클래스의 새 인스턴스를 선언 하 고 여기에 값을 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="65249-119">Alternatively, you can declare a new instance of the class and then assign a value to it.</span></span> <span data-ttu-id="65249-120">먼저의 인스턴스를 선언 합니다 `Student` .</span><span class="sxs-lookup"><span data-stu-id="65249-120">First, declare an instance of `Student`:</span></span>  
  
     `Dim student2 As Student`  
  
5. <span data-ttu-id="65249-121">일반적인 방법으로 인스턴스 만들기를 시작 `Student` 합니다.</span><span class="sxs-lookup"><span data-stu-id="65249-121">Begin the creation of an instance of `Student` in the normal way.</span></span>  
  
     `Dim student2 As Student = New Student`  
  
6. <span data-ttu-id="65249-122">를 입력 한 `With` 다음 개체 이니셜라이저를 입력 하 여 새 인스턴스의 멤버를 하나 이상 초기화 합니다.</span><span class="sxs-lookup"><span data-stu-id="65249-122">Type `With` and then an object initializer to initialize one or more members of the new instance.</span></span>  
  
     [!code-vb[VbVbalrObjectInit#22](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrObjectInit/VB/Class2.vb#22)]  
  
7. <span data-ttu-id="65249-123">를 생략 하 여 이전 단계에서 정의를 단순화할 수 있습니다 `As Student` .</span><span class="sxs-lookup"><span data-stu-id="65249-123">You can simplify the definition in the previous step by omitting `As Student`.</span></span> <span data-ttu-id="65249-124">이 작업을 수행 하는 경우 컴파일러는 `student3` 로컬 형식 유추를 사용 하 여가의 인스턴스인지를 확인 합니다 `Student` .</span><span class="sxs-lookup"><span data-stu-id="65249-124">If you do this, the compiler determines that `student3` is an instance of `Student` by using local type inference.</span></span>  
  
     [!code-vb[VbVbalrObjectInit#23](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrObjectInit/VB/Class2.vb#23)]  
  
     <span data-ttu-id="65249-125">자세한 내용은 [지역 형식 유추](../variables/local-type-inference.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="65249-125">For more information, see [Local Type Inference](../variables/local-type-inference.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="65249-126">추가 정보</span><span class="sxs-lookup"><span data-stu-id="65249-126">See also</span></span>

- [<span data-ttu-id="65249-127">지역 형식 유추</span><span class="sxs-lookup"><span data-stu-id="65249-127">Local Type Inference</span></span>](../variables/local-type-inference.md)
- [<span data-ttu-id="65249-128">방법: 항목 목록 만들기</span><span class="sxs-lookup"><span data-stu-id="65249-128">How to: Create a List of Items</span></span>](../../concepts/linq/how-to-create-a-list-of-items.md)
- [<span data-ttu-id="65249-129">개체 이니셜라이저: 명명된 형식 및 무명 형식</span><span class="sxs-lookup"><span data-stu-id="65249-129">Object Initializers: Named and Anonymous Types</span></span>](object-initializers-named-and-anonymous-types.md)
- [<span data-ttu-id="65249-130">익명 형식</span><span class="sxs-lookup"><span data-stu-id="65249-130">Anonymous Types</span></span>](anonymous-types.md)
