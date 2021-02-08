---
description: '자세히 알아보기: Implements 문'
title: Implements 문
ms.date: 07/20/2015
f1_keywords:
- vb.Implements
- Implements
helpviewer_keywords:
- Implements statement [Visual Basic], syntax
- Implements statement [Visual Basic]
- interface implementation [Visual Basic], Implements statement
ms.assetid: 1fafb83f-f55a-4215-8ea9-681e8622613d
ms.openlocfilehash: aa53d1f3b4ba9d9111f5ffb09198a11511f8d9e9
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99768989"
---
# <a name="implements-statement"></a><span data-ttu-id="d49b0-103">Implements 문</span><span class="sxs-lookup"><span data-stu-id="d49b0-103">Implements Statement</span></span>

<span data-ttu-id="d49b0-104">인터페이스가 표시 되는 클래스 또는 구조체 정의에 구현 해야 하는 인터페이스 또는 인터페이스 멤버를 하나 이상 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="d49b0-104">Specifies one or more interfaces, or interface members, that must be implemented in the class or structure definition in which it appears.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d49b0-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="d49b0-105">Syntax</span></span>  
  
```vb  
Implements interfacename [, ...]  
' -or-  
Implements interfacename.interfacemember [, ...]  
```  
  
## <a name="parts"></a><span data-ttu-id="d49b0-106">부분</span><span class="sxs-lookup"><span data-stu-id="d49b0-106">Parts</span></span>  

 `interfacename`  
 <span data-ttu-id="d49b0-107">필수 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="d49b0-107">Required.</span></span> <span data-ttu-id="d49b0-108">클래스 또는 구조체의 해당 멤버에 의해 구현 되는 속성, 프로시저 및 이벤트를 포함 하는 인터페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="d49b0-108">An interface whose properties, procedures, and events are to be implemented by corresponding members in the class or structure.</span></span>  
  
 `interfacemember`  
 <span data-ttu-id="d49b0-109">필수 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="d49b0-109">Required.</span></span> <span data-ttu-id="d49b0-110">구현 되는 인터페이스의 멤버입니다.</span><span class="sxs-lookup"><span data-stu-id="d49b0-110">The member of an interface that is being implemented.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d49b0-111">설명</span><span class="sxs-lookup"><span data-stu-id="d49b0-111">Remarks</span></span>  

 <span data-ttu-id="d49b0-112">인터페이스는 인터페이스에서 캡슐화 하는 멤버 (속성, 프로시저 및 이벤트)를 나타내는 프로토타입의 컬렉션입니다.</span><span class="sxs-lookup"><span data-stu-id="d49b0-112">An interface is a collection of prototypes representing the members (properties, procedures, and events) the interface encapsulates.</span></span> <span data-ttu-id="d49b0-113">인터페이스에는 멤버에 대 한 선언만 포함 됩니다. 클래스와 구조체는 이러한 멤버를 구현 합니다.</span><span class="sxs-lookup"><span data-stu-id="d49b0-113">Interfaces contain only the declarations for members; classes and structures implement these members.</span></span> <span data-ttu-id="d49b0-114">자세한 내용은 [인터페이스](../../programming-guide/language-features/interfaces/index.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d49b0-114">For more information, see [Interfaces](../../programming-guide/language-features/interfaces/index.md).</span></span>  
  
 <span data-ttu-id="d49b0-115">`Implements`문은 또는 문 바로 뒤에와 야 합니다 `Class` `Structure` .</span><span class="sxs-lookup"><span data-stu-id="d49b0-115">The `Implements` statement must immediately follow the `Class` or `Structure` statement.</span></span>  
  
 <span data-ttu-id="d49b0-116">인터페이스를 구현 하는 경우 인터페이스에 선언 된 모든 멤버를 구현 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d49b0-116">When you implement an interface, you must implement all the members declared in the interface.</span></span> <span data-ttu-id="d49b0-117">멤버를 생략 하면 구문 오류로 간주 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d49b0-117">Omitting any member is considered to be a syntax error.</span></span> <span data-ttu-id="d49b0-118">개별 멤버를 구현 하려면 [](implements-clause.md) `Implements` 클래스 또는 구조체에서 멤버를 선언할 때 Implements 키워드 (문과 분리 됨)를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="d49b0-118">To implement an individual member, you specify the [Implements](implements-clause.md) keyword (which is separate from the `Implements` statement) when you declare the member in the class or structure.</span></span> <span data-ttu-id="d49b0-119">자세한 내용은 [인터페이스](../../programming-guide/language-features/interfaces/index.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d49b0-119">For more information, see [Interfaces](../../programming-guide/language-features/interfaces/index.md).</span></span>  
  
 <span data-ttu-id="d49b0-120">클래스는 속성 및 프로시저의 [전용](../modifiers/private.md) 구현을 사용할 수 있지만 이러한 멤버는 구현 클래스의 인스턴스를 인터페이스 형식으로 선언 된 변수로 캐스팅 하 여 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d49b0-120">Classes can use [Private](../modifiers/private.md) implementations of properties and procedures, but these members are accessible only by casting an instance of the implementing class into a variable declared to be of the type of the interface.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d49b0-121">예제</span><span class="sxs-lookup"><span data-stu-id="d49b0-121">Example</span></span>  

 <span data-ttu-id="d49b0-122">다음 예제에서는 문을 사용 하 여 인터페이스의 멤버를 구현 하는 방법을 보여 줍니다 `Implements` .</span><span class="sxs-lookup"><span data-stu-id="d49b0-122">The following example shows how to use the `Implements` statement to implement members of an interface.</span></span> <span data-ttu-id="d49b0-123">`ICustomerInfo`이벤트, 속성 및 프로시저를 사용 하 여 라는 인터페이스를 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="d49b0-123">It defines an interface named `ICustomerInfo` with an event, a property, and a procedure.</span></span> <span data-ttu-id="d49b0-124">클래스는 `customerInfo` 인터페이스에 정의 된 모든 멤버를 구현 합니다.</span><span class="sxs-lookup"><span data-stu-id="d49b0-124">The class `customerInfo` implements all the members defined in the interface.</span></span>  
  
 [!code-vb[VbVbalrStatements#33](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#33)]  
  
 <span data-ttu-id="d49b0-125">클래스는 클래스에서 `customerInfo` `Implements` 인터페이스의 모든 멤버를 구현 한다는 것을 나타내기 위해 문을 별도의 소스 코드 줄에 사용 합니다 `ICustomerInfo` .</span><span class="sxs-lookup"><span data-stu-id="d49b0-125">Note that the class `customerInfo` uses the `Implements` statement on a separate source code line to indicate that the class implements all the members of the `ICustomerInfo` interface.</span></span> <span data-ttu-id="d49b0-126">그런 다음 클래스의 각 멤버가 해당 멤버 선언의 일부로 키워드를 사용 하 여 해당 `Implements` 인터페이스 멤버를 구현 함을 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="d49b0-126">Then each member in the class uses the `Implements` keyword as part of its member declaration to indicate that it implements that interface member.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d49b0-127">예제</span><span class="sxs-lookup"><span data-stu-id="d49b0-127">Example</span></span>  

 <span data-ttu-id="d49b0-128">다음 두 절차에서는 앞의 예제에서 구현 된 인터페이스를 사용 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="d49b0-128">The following two procedures show how you could use the interface implemented in the preceding example.</span></span> <span data-ttu-id="d49b0-129">구현을 테스트 하려면 이러한 프로시저를 프로젝트에 추가 하 고 프로시저를 호출 `testImplements` 합니다.</span><span class="sxs-lookup"><span data-stu-id="d49b0-129">To test the implementation, add these procedures to your project and call the `testImplements` procedure.</span></span>  
  
 [!code-vb[VbVbalrStatements#34](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#34)]  
  
## <a name="see-also"></a><span data-ttu-id="d49b0-130">참고 항목</span><span class="sxs-lookup"><span data-stu-id="d49b0-130">See also</span></span>

- [<span data-ttu-id="d49b0-131">구현</span><span class="sxs-lookup"><span data-stu-id="d49b0-131">Implements</span></span>](implements-clause.md)
- [<span data-ttu-id="d49b0-132">Interface 문</span><span class="sxs-lookup"><span data-stu-id="d49b0-132">Interface Statement</span></span>](interface-statement.md)
- [<span data-ttu-id="d49b0-133">인터페이스</span><span class="sxs-lookup"><span data-stu-id="d49b0-133">Interfaces</span></span>](../../programming-guide/language-features/interfaces/index.md)
