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
ms.openlocfilehash: e2e279b2c935dd082cbf832265a8ad09e6dffe9e
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/22/2019
ms.locfileid: "74351145"
---
# <a name="implements-statement"></a><span data-ttu-id="fa3ce-102">Implements 문</span><span class="sxs-lookup"><span data-stu-id="fa3ce-102">Implements Statement</span></span>
<span data-ttu-id="fa3ce-103">인터페이스가 표시 되는 클래스 또는 구조체 정의에 구현 해야 하는 인터페이스 또는 인터페이스 멤버를 하나 이상 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="fa3ce-103">Specifies one or more interfaces, or interface members, that must be implemented in the class or structure definition in which it appears.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fa3ce-104">구문</span><span class="sxs-lookup"><span data-stu-id="fa3ce-104">Syntax</span></span>  
  
```vb  
Implements interfacename [, ...]  
' -or-  
Implements interfacename.interfacemember [, ...]  
```  
  
## <a name="parts"></a><span data-ttu-id="fa3ce-105">요소</span><span class="sxs-lookup"><span data-stu-id="fa3ce-105">Parts</span></span>  
 `interfacename`  
 <span data-ttu-id="fa3ce-106">필수입니다.</span><span class="sxs-lookup"><span data-stu-id="fa3ce-106">Required.</span></span> <span data-ttu-id="fa3ce-107">클래스 또는 구조체의 해당 멤버에 의해 구현 되는 속성, 프로시저 및 이벤트를 포함 하는 인터페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="fa3ce-107">An interface whose properties, procedures, and events are to be implemented by corresponding members in the class or structure.</span></span>  
  
 `interfacemember`  
 <span data-ttu-id="fa3ce-108">필수입니다.</span><span class="sxs-lookup"><span data-stu-id="fa3ce-108">Required.</span></span> <span data-ttu-id="fa3ce-109">구현 되는 인터페이스의 멤버입니다.</span><span class="sxs-lookup"><span data-stu-id="fa3ce-109">The member of an interface that is being implemented.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="fa3ce-110">주의</span><span class="sxs-lookup"><span data-stu-id="fa3ce-110">Remarks</span></span>  
 <span data-ttu-id="fa3ce-111">인터페이스는 인터페이스에서 캡슐화 하는 멤버 (속성, 프로시저 및 이벤트)를 나타내는 프로토타입의 컬렉션입니다.</span><span class="sxs-lookup"><span data-stu-id="fa3ce-111">An interface is a collection of prototypes representing the members (properties, procedures, and events) the interface encapsulates.</span></span> <span data-ttu-id="fa3ce-112">인터페이스에는 멤버에 대 한 선언만 포함 됩니다. 클래스와 구조체는 이러한 멤버를 구현 합니다.</span><span class="sxs-lookup"><span data-stu-id="fa3ce-112">Interfaces contain only the declarations for members; classes and structures implement these members.</span></span> <span data-ttu-id="fa3ce-113">자세한 내용은 [인터페이스](../../../visual-basic/programming-guide/language-features/interfaces/index.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="fa3ce-113">For more information, see [Interfaces](../../../visual-basic/programming-guide/language-features/interfaces/index.md).</span></span>  
  
 <span data-ttu-id="fa3ce-114">`Implements` 문은 `Class` 또는 `Structure` 문 바로 뒤에와 야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fa3ce-114">The `Implements` statement must immediately follow the `Class` or `Structure` statement.</span></span>  
  
 <span data-ttu-id="fa3ce-115">인터페이스를 구현 하는 경우 인터페이스에 선언 된 모든 멤버를 구현 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fa3ce-115">When you implement an interface, you must implement all the members declared in the interface.</span></span> <span data-ttu-id="fa3ce-116">멤버를 생략 하면 구문 오류로 간주 됩니다.</span><span class="sxs-lookup"><span data-stu-id="fa3ce-116">Omitting any member is considered to be a syntax error.</span></span> <span data-ttu-id="fa3ce-117">개별 멤버를 구현 하려면 클래스 또는 구조체에서 멤버를 선언할 때 [Implements](../../../visual-basic/language-reference/statements/implements-clause.md) 키워드 (`Implements` 문과 분리 됨)를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="fa3ce-117">To implement an individual member, you specify the [Implements](../../../visual-basic/language-reference/statements/implements-clause.md) keyword (which is separate from the `Implements` statement) when you declare the member in the class or structure.</span></span> <span data-ttu-id="fa3ce-118">자세한 내용은 [인터페이스](../../../visual-basic/programming-guide/language-features/interfaces/index.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="fa3ce-118">For more information, see [Interfaces](../../../visual-basic/programming-guide/language-features/interfaces/index.md).</span></span>  
  
 <span data-ttu-id="fa3ce-119">클래스는 속성 및 프로시저의 [전용](../../../visual-basic/language-reference/modifiers/private.md) 구현을 사용할 수 있지만 이러한 멤버는 구현 클래스의 인스턴스를 인터페이스 형식으로 선언 된 변수로 캐스팅 하 여 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fa3ce-119">Classes can use [Private](../../../visual-basic/language-reference/modifiers/private.md) implementations of properties and procedures, but these members are accessible only by casting an instance of the implementing class into a variable declared to be of the type of the interface.</span></span>  
  
## <a name="example"></a><span data-ttu-id="fa3ce-120">예제</span><span class="sxs-lookup"><span data-stu-id="fa3ce-120">Example</span></span>  
 <span data-ttu-id="fa3ce-121">다음 예제에서는 `Implements` 문을 사용 하 여 인터페이스의 멤버를 구현 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="fa3ce-121">The following example shows how to use the `Implements` statement to implement members of an interface.</span></span> <span data-ttu-id="fa3ce-122">이벤트, 속성 및 프로시저를 사용 하 여 `ICustomerInfo` 이라는 인터페이스를 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="fa3ce-122">It defines an interface named `ICustomerInfo` with an event, a property, and a procedure.</span></span> <span data-ttu-id="fa3ce-123">클래스 `customerInfo` 인터페이스에 정의 된 모든 멤버를 구현 합니다.</span><span class="sxs-lookup"><span data-stu-id="fa3ce-123">The class `customerInfo` implements all the members defined in the interface.</span></span>  
  
 [!code-vb[VbVbalrStatements#33](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#33)]  
  
 <span data-ttu-id="fa3ce-124">클래스 `customerInfo` 별도의 소스 코드 줄에서 `Implements` 문을 사용 하 여 클래스가 `ICustomerInfo` 인터페이스의 모든 멤버를 구현 함을 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="fa3ce-124">Note that the class `customerInfo` uses the `Implements` statement on a separate source code line to indicate that the class implements all the members of the `ICustomerInfo` interface.</span></span> <span data-ttu-id="fa3ce-125">그런 다음 클래스의 각 멤버가 해당 멤버 선언의 일부로 `Implements` 키워드를 사용 하 여 해당 인터페이스 멤버를 구현 함을 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="fa3ce-125">Then each member in the class uses the `Implements` keyword as part of its member declaration to indicate that it implements that interface member.</span></span>  
  
## <a name="example"></a><span data-ttu-id="fa3ce-126">예제</span><span class="sxs-lookup"><span data-stu-id="fa3ce-126">Example</span></span>  
 <span data-ttu-id="fa3ce-127">다음 두 절차에서는 앞의 예제에서 구현 된 인터페이스를 사용 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="fa3ce-127">The following two procedures show how you could use the interface implemented in the preceding example.</span></span> <span data-ttu-id="fa3ce-128">구현을 테스트 하려면 이러한 프로시저를 프로젝트에 추가 하 고 `testImplements` 프로시저를 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="fa3ce-128">To test the implementation, add these procedures to your project and call the `testImplements` procedure.</span></span>  
  
 [!code-vb[VbVbalrStatements#34](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#34)]  
  
## <a name="see-also"></a><span data-ttu-id="fa3ce-129">참고 항목</span><span class="sxs-lookup"><span data-stu-id="fa3ce-129">See also</span></span>

- [<span data-ttu-id="fa3ce-130">Sub New</span><span class="sxs-lookup"><span data-stu-id="fa3ce-130">Implements</span></span>](../../../visual-basic/language-reference/statements/implements-clause.md)
- [<span data-ttu-id="fa3ce-131">Interface 문</span><span class="sxs-lookup"><span data-stu-id="fa3ce-131">Interface Statement</span></span>](../../../visual-basic/language-reference/statements/interface-statement.md)
- [<span data-ttu-id="fa3ce-132">인터페이스</span><span class="sxs-lookup"><span data-stu-id="fa3ce-132">Interfaces</span></span>](../../../visual-basic/programming-guide/language-features/interfaces/index.md)
