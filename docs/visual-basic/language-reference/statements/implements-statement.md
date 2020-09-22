---
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
ms.openlocfilehash: b982057d2094f807b68d5190dfad388fb9a2c65a
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/22/2020
ms.locfileid: "90873240"
---
# <a name="implements-statement"></a><span data-ttu-id="44ad2-102">Implements 문</span><span class="sxs-lookup"><span data-stu-id="44ad2-102">Implements Statement</span></span>

<span data-ttu-id="44ad2-103">인터페이스가 표시 되는 클래스 또는 구조체 정의에 구현 해야 하는 인터페이스 또는 인터페이스 멤버를 하나 이상 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="44ad2-103">Specifies one or more interfaces, or interface members, that must be implemented in the class or structure definition in which it appears.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="44ad2-104">구문</span><span class="sxs-lookup"><span data-stu-id="44ad2-104">Syntax</span></span>  
  
```vb  
Implements interfacename [, ...]  
' -or-  
Implements interfacename.interfacemember [, ...]  
```  
  
## <a name="parts"></a><span data-ttu-id="44ad2-105">부분</span><span class="sxs-lookup"><span data-stu-id="44ad2-105">Parts</span></span>  

 `interfacename`  
 <span data-ttu-id="44ad2-106">필수 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="44ad2-106">Required.</span></span> <span data-ttu-id="44ad2-107">클래스 또는 구조체의 해당 멤버에 의해 구현 되는 속성, 프로시저 및 이벤트를 포함 하는 인터페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="44ad2-107">An interface whose properties, procedures, and events are to be implemented by corresponding members in the class or structure.</span></span>  
  
 `interfacemember`  
 <span data-ttu-id="44ad2-108">필수 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="44ad2-108">Required.</span></span> <span data-ttu-id="44ad2-109">구현 되는 인터페이스의 멤버입니다.</span><span class="sxs-lookup"><span data-stu-id="44ad2-109">The member of an interface that is being implemented.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="44ad2-110">설명</span><span class="sxs-lookup"><span data-stu-id="44ad2-110">Remarks</span></span>  

 <span data-ttu-id="44ad2-111">인터페이스는 인터페이스에서 캡슐화 하는 멤버 (속성, 프로시저 및 이벤트)를 나타내는 프로토타입의 컬렉션입니다.</span><span class="sxs-lookup"><span data-stu-id="44ad2-111">An interface is a collection of prototypes representing the members (properties, procedures, and events) the interface encapsulates.</span></span> <span data-ttu-id="44ad2-112">인터페이스에는 멤버에 대 한 선언만 포함 됩니다. 클래스와 구조체는 이러한 멤버를 구현 합니다.</span><span class="sxs-lookup"><span data-stu-id="44ad2-112">Interfaces contain only the declarations for members; classes and structures implement these members.</span></span> <span data-ttu-id="44ad2-113">자세한 내용은 [인터페이스](../../programming-guide/language-features/interfaces/index.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="44ad2-113">For more information, see [Interfaces](../../programming-guide/language-features/interfaces/index.md).</span></span>  
  
 <span data-ttu-id="44ad2-114">`Implements`문은 또는 문 바로 뒤에와 야 합니다 `Class` `Structure` .</span><span class="sxs-lookup"><span data-stu-id="44ad2-114">The `Implements` statement must immediately follow the `Class` or `Structure` statement.</span></span>  
  
 <span data-ttu-id="44ad2-115">인터페이스를 구현 하는 경우 인터페이스에 선언 된 모든 멤버를 구현 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="44ad2-115">When you implement an interface, you must implement all the members declared in the interface.</span></span> <span data-ttu-id="44ad2-116">멤버를 생략 하면 구문 오류로 간주 됩니다.</span><span class="sxs-lookup"><span data-stu-id="44ad2-116">Omitting any member is considered to be a syntax error.</span></span> <span data-ttu-id="44ad2-117">개별 멤버를 구현 하려면 [Implements](implements-clause.md) `Implements` 클래스 또는 구조체에서 멤버를 선언할 때 Implements 키워드 (문과 분리 됨)를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="44ad2-117">To implement an individual member, you specify the [Implements](implements-clause.md) keyword (which is separate from the `Implements` statement) when you declare the member in the class or structure.</span></span> <span data-ttu-id="44ad2-118">자세한 내용은 [인터페이스](../../programming-guide/language-features/interfaces/index.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="44ad2-118">For more information, see [Interfaces](../../programming-guide/language-features/interfaces/index.md).</span></span>  
  
 <span data-ttu-id="44ad2-119">클래스는 속성 및 프로시저의 [전용](../modifiers/private.md) 구현을 사용할 수 있지만 이러한 멤버는 구현 클래스의 인스턴스를 인터페이스 형식으로 선언 된 변수로 캐스팅 하 여 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="44ad2-119">Classes can use [Private](../modifiers/private.md) implementations of properties and procedures, but these members are accessible only by casting an instance of the implementing class into a variable declared to be of the type of the interface.</span></span>  
  
## <a name="example"></a><span data-ttu-id="44ad2-120">예제</span><span class="sxs-lookup"><span data-stu-id="44ad2-120">Example</span></span>  

 <span data-ttu-id="44ad2-121">다음 예제에서는 문을 사용 하 여 인터페이스의 멤버를 구현 하는 방법을 보여 줍니다 `Implements` .</span><span class="sxs-lookup"><span data-stu-id="44ad2-121">The following example shows how to use the `Implements` statement to implement members of an interface.</span></span> <span data-ttu-id="44ad2-122">`ICustomerInfo`이벤트, 속성 및 프로시저를 사용 하 여 라는 인터페이스를 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="44ad2-122">It defines an interface named `ICustomerInfo` with an event, a property, and a procedure.</span></span> <span data-ttu-id="44ad2-123">클래스는 `customerInfo` 인터페이스에 정의 된 모든 멤버를 구현 합니다.</span><span class="sxs-lookup"><span data-stu-id="44ad2-123">The class `customerInfo` implements all the members defined in the interface.</span></span>  
  
 [!code-vb[VbVbalrStatements#33](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#33)]  
  
 <span data-ttu-id="44ad2-124">클래스는 클래스에서 `customerInfo` `Implements` 인터페이스의 모든 멤버를 구현 한다는 것을 나타내기 위해 문을 별도의 소스 코드 줄에 사용 합니다 `ICustomerInfo` .</span><span class="sxs-lookup"><span data-stu-id="44ad2-124">Note that the class `customerInfo` uses the `Implements` statement on a separate source code line to indicate that the class implements all the members of the `ICustomerInfo` interface.</span></span> <span data-ttu-id="44ad2-125">그런 다음 클래스의 각 멤버가 해당 멤버 선언의 일부로 키워드를 사용 하 여 해당 `Implements` 인터페이스 멤버를 구현 함을 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="44ad2-125">Then each member in the class uses the `Implements` keyword as part of its member declaration to indicate that it implements that interface member.</span></span>  
  
## <a name="example"></a><span data-ttu-id="44ad2-126">예제</span><span class="sxs-lookup"><span data-stu-id="44ad2-126">Example</span></span>  

 <span data-ttu-id="44ad2-127">다음 두 절차에서는 앞의 예제에서 구현 된 인터페이스를 사용 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="44ad2-127">The following two procedures show how you could use the interface implemented in the preceding example.</span></span> <span data-ttu-id="44ad2-128">구현을 테스트 하려면 이러한 프로시저를 프로젝트에 추가 하 고 프로시저를 호출 `testImplements` 합니다.</span><span class="sxs-lookup"><span data-stu-id="44ad2-128">To test the implementation, add these procedures to your project and call the `testImplements` procedure.</span></span>  
  
 [!code-vb[VbVbalrStatements#34](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#34)]  
  
## <a name="see-also"></a><span data-ttu-id="44ad2-129">참조</span><span class="sxs-lookup"><span data-stu-id="44ad2-129">See also</span></span>

- [<span data-ttu-id="44ad2-130">구현</span><span class="sxs-lookup"><span data-stu-id="44ad2-130">Implements</span></span>](implements-clause.md)
- [<span data-ttu-id="44ad2-131">Interface 문</span><span class="sxs-lookup"><span data-stu-id="44ad2-131">Interface Statement</span></span>](interface-statement.md)
- [<span data-ttu-id="44ad2-132">인터페이스</span><span class="sxs-lookup"><span data-stu-id="44ad2-132">Interfaces</span></span>](../../programming-guide/language-features/interfaces/index.md)
