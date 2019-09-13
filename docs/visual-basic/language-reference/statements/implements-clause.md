---
title: Implements 절(Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.ImplementsClause
helpviewer_keywords:
- interface implementation [Visual Basic], reimplementation
- interface members [Visual Basic], reimplementation
- interface members [Visual Basic], Implements keyword
- interface members
- members [Visual Basic], reimplementation
- interface implementation [Visual Basic], Implements keyword
- interface members [Visual Basic], implementing
- Implements keyword [Visual Basic]
- Implements statement [Visual Basic], about Implements
- members [Visual Basic], implementing
- members [Visual Basic], Implements keyword
- reimplementation
ms.assetid: 5252cdf9-964d-4fc6-af0f-0449b7126b5a
ms.openlocfilehash: dcd20f21a989c327dcfcf27d5638d500b6e4b6da
ms.sourcegitcommit: 33c8d6f7342a4bb2c577842b7f075b0e20a2fa40
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/12/2019
ms.locfileid: "70929313"
---
# <a name="implements-clause-visual-basic"></a><span data-ttu-id="1d9e1-102">Implements 절(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="1d9e1-102">Implements Clause (Visual Basic)</span></span>
<span data-ttu-id="1d9e1-103">클래스 또는 구조체 멤버가 인터페이스에 정의 된 멤버에 대 한 구현을 제공 함을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="1d9e1-103">Indicates that a class or structure member is providing the implementation for a member defined in an interface.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="1d9e1-104">설명</span><span class="sxs-lookup"><span data-stu-id="1d9e1-104">Remarks</span></span>  
<span data-ttu-id="1d9e1-105">키워드는 [Implements 문과 다릅니다.](../../../visual-basic/language-reference/statements/implements-statement.md) `Implements`</span><span class="sxs-lookup"><span data-stu-id="1d9e1-105">The `Implements` keyword is not the same as the [Implements Statement](../../../visual-basic/language-reference/statements/implements-statement.md).</span></span> <span data-ttu-id="1d9e1-106">`Implements` 문을 사용 하 여 하나 이상의 인터페이스를 구현 하는 클래스 또는 구조체를 지정 하 고 각 멤버에 대해 `Implements` 키워드를 사용 하 여 인터페이스 및 인터페이스를 구현 하는 멤버를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d9e1-106">You use the `Implements` statement to specify that a class or structure implements one or more interfaces, and then for each member you use the `Implements` keyword to specify which interface and which member it implements.</span></span>

<span data-ttu-id="1d9e1-107">클래스 또는 구조체에서 인터페이스를 구현 하는 경우 [클래스 문](../../../visual-basic/language-reference/statements/class-statement.md) 또는 `Implements` [구조체 문](../../../visual-basic/language-reference/statements/structure-statement.md)바로 뒤에 문을 포함 해야 하며, 인터페이스에서 정의 된 모든 멤버를 구현 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d9e1-107">If a class or structure implements an interface, it must include the `Implements` statement immediately after the [Class Statement](../../../visual-basic/language-reference/statements/class-statement.md) or [Structure Statement](../../../visual-basic/language-reference/statements/structure-statement.md), and it must implement all the members defined by the interface.</span></span>

## <a name="reimplementation"></a><span data-ttu-id="1d9e1-108">재구현</span><span class="sxs-lookup"><span data-stu-id="1d9e1-108">Reimplementation</span></span>  
<span data-ttu-id="1d9e1-109">파생 클래스에서 기본 클래스가 이미 구현 된 인터페이스 멤버를 다시 구현할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1d9e1-109">In a derived class, you can reimplement an interface member that the base class has already implemented.</span></span> <span data-ttu-id="1d9e1-110">이는 다음과 같은 측면에서 기본 클래스 멤버를 재정의 하는 것과는 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="1d9e1-110">This is different from overriding the base class member in the following respects:</span></span>

- <span data-ttu-id="1d9e1-111">기본 클래스 멤버는 다시 구현 수 있도록 [재정의할](../../../visual-basic/language-reference/modifiers/overridable.md) 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="1d9e1-111">The base class member does not need to be [Overridable](../../../visual-basic/language-reference/modifiers/overridable.md) to be reimplemented.</span></span>
- <span data-ttu-id="1d9e1-112">다른 이름을 사용 하 여 멤버를 다시 구현할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1d9e1-112">You can reimplement the member with a different name.</span></span>

<span data-ttu-id="1d9e1-113">키워드 `Implements` 는 다음 컨텍스트에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1d9e1-113">The `Implements` keyword can be used in the following contexts:</span></span>

- [<span data-ttu-id="1d9e1-114">Event 문</span><span class="sxs-lookup"><span data-stu-id="1d9e1-114">Event Statement</span></span>](../../../visual-basic/language-reference/statements/event-statement.md)
- [<span data-ttu-id="1d9e1-115">Function 문</span><span class="sxs-lookup"><span data-stu-id="1d9e1-115">Function Statement</span></span>](../../../visual-basic/language-reference/statements/function-statement.md)
- [<span data-ttu-id="1d9e1-116">Property 문</span><span class="sxs-lookup"><span data-stu-id="1d9e1-116">Property Statement</span></span>](../../../visual-basic/language-reference/statements/property-statement.md)
- [<span data-ttu-id="1d9e1-117">Sub 문</span><span class="sxs-lookup"><span data-stu-id="1d9e1-117">Sub Statement</span></span>](../../../visual-basic/language-reference/statements/sub-statement.md)  
  
## <a name="see-also"></a><span data-ttu-id="1d9e1-118">참고자료</span><span class="sxs-lookup"><span data-stu-id="1d9e1-118">See also</span></span>

- [<span data-ttu-id="1d9e1-119">Implements 문</span><span class="sxs-lookup"><span data-stu-id="1d9e1-119">Implements Statement</span></span>](../../../visual-basic/language-reference/statements/implements-statement.md)
- [<span data-ttu-id="1d9e1-120">Interface 문</span><span class="sxs-lookup"><span data-stu-id="1d9e1-120">Interface Statement</span></span>](../../../visual-basic/language-reference/statements/interface-statement.md)
- [<span data-ttu-id="1d9e1-121">Class 문</span><span class="sxs-lookup"><span data-stu-id="1d9e1-121">Class Statement</span></span>](../../../visual-basic/language-reference/statements/class-statement.md)
- [<span data-ttu-id="1d9e1-122">Structure 문</span><span class="sxs-lookup"><span data-stu-id="1d9e1-122">Structure Statement</span></span>](../../../visual-basic/language-reference/statements/structure-statement.md)
