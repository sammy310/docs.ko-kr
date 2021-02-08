---
description: '자세한 정보: Implements 절 (Visual Basic)'
title: Implements 절
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
ms.openlocfilehash: 360d8812a7c49d6462818246b1448e171dcd597f
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99769002"
---
# <a name="implements-clause-visual-basic"></a><span data-ttu-id="643db-103">Implements 절(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="643db-103">Implements Clause (Visual Basic)</span></span>

<span data-ttu-id="643db-104">클래스 또는 구조체 멤버가 인터페이스에 정의 된 멤버에 대 한 구현을 제공 함을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="643db-104">Indicates that a class or structure member is providing the implementation for a member defined in an interface.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="643db-105">설명</span><span class="sxs-lookup"><span data-stu-id="643db-105">Remarks</span></span>  

<span data-ttu-id="643db-106">`Implements`키워드는 [Implements 문과](implements-statement.md)다릅니다.</span><span class="sxs-lookup"><span data-stu-id="643db-106">The `Implements` keyword is not the same as the [Implements Statement](implements-statement.md).</span></span> <span data-ttu-id="643db-107">문을 사용 하 여 `Implements` 하나 이상의 인터페이스를 구현 하는 클래스 또는 구조체를 지정 하 고 각 멤버에 대해 키워드를 사용 하 여 `Implements` 인터페이스 및 인터페이스를 구현 하는 멤버를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="643db-107">You use the `Implements` statement to specify that a class or structure implements one or more interfaces, and then for each member you use the `Implements` keyword to specify which interface and which member it implements.</span></span>

<span data-ttu-id="643db-108">클래스 또는 구조체에서 인터페이스를 구현 하는 경우 `Implements` [클래스 문](class-statement.md) 또는 [구조체 문](structure-statement.md)바로 뒤에 문을 포함 해야 하며, 인터페이스에서 정의 된 모든 멤버를 구현 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="643db-108">If a class or structure implements an interface, it must include the `Implements` statement immediately after the [Class Statement](class-statement.md) or [Structure Statement](structure-statement.md), and it must implement all the members defined by the interface.</span></span>

## <a name="reimplementation"></a><span data-ttu-id="643db-109">재구현</span><span class="sxs-lookup"><span data-stu-id="643db-109">Reimplementation</span></span>  

<span data-ttu-id="643db-110">파생 클래스에서 기본 클래스가 이미 구현 된 인터페이스 멤버를 다시 구현할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="643db-110">In a derived class, you can reimplement an interface member that the base class has already implemented.</span></span> <span data-ttu-id="643db-111">이는 다음과 같은 측면에서 기본 클래스 멤버를 재정의 하는 것과는 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="643db-111">This is different from overriding the base class member in the following respects:</span></span>

- <span data-ttu-id="643db-112">기본 클래스 멤버는 다시 구현 수 있도록 [재정의할](../modifiers/overridable.md) 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="643db-112">The base class member does not need to be [Overridable](../modifiers/overridable.md) to be reimplemented.</span></span>
- <span data-ttu-id="643db-113">다른 이름을 사용 하 여 멤버를 다시 구현할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="643db-113">You can reimplement the member with a different name.</span></span>

<span data-ttu-id="643db-114">`Implements`키워드는 다음 컨텍스트에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="643db-114">The `Implements` keyword can be used in the following contexts:</span></span>

- [<span data-ttu-id="643db-115">Event 문</span><span class="sxs-lookup"><span data-stu-id="643db-115">Event Statement</span></span>](event-statement.md)
- [<span data-ttu-id="643db-116">Function 문</span><span class="sxs-lookup"><span data-stu-id="643db-116">Function Statement</span></span>](function-statement.md)
- [<span data-ttu-id="643db-117">Property Statement</span><span class="sxs-lookup"><span data-stu-id="643db-117">Property Statement</span></span>](property-statement.md)
- [<span data-ttu-id="643db-118">Sub 문</span><span class="sxs-lookup"><span data-stu-id="643db-118">Sub Statement</span></span>](sub-statement.md)  
  
## <a name="see-also"></a><span data-ttu-id="643db-119">참고 항목</span><span class="sxs-lookup"><span data-stu-id="643db-119">See also</span></span>

- [<span data-ttu-id="643db-120">Implements 문</span><span class="sxs-lookup"><span data-stu-id="643db-120">Implements Statement</span></span>](implements-statement.md)
- [<span data-ttu-id="643db-121">Interface 문</span><span class="sxs-lookup"><span data-stu-id="643db-121">Interface Statement</span></span>](interface-statement.md)
- [<span data-ttu-id="643db-122">Class 문</span><span class="sxs-lookup"><span data-stu-id="643db-122">Class Statement</span></span>](class-statement.md)
- [<span data-ttu-id="643db-123">Structure 문</span><span class="sxs-lookup"><span data-stu-id="643db-123">Structure Statement</span></span>](structure-statement.md)
