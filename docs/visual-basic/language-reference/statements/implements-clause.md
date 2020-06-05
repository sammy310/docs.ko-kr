---
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
ms.openlocfilehash: 46ab1a1148e8d73d91293aedfc407e5efdc7cfb4
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/04/2020
ms.locfileid: "84404565"
---
# <a name="implements-clause-visual-basic"></a><span data-ttu-id="1a430-102">Implements 절(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="1a430-102">Implements Clause (Visual Basic)</span></span>
<span data-ttu-id="1a430-103">클래스 또는 구조체 멤버가 인터페이스에 정의 된 멤버에 대 한 구현을 제공 함을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="1a430-103">Indicates that a class or structure member is providing the implementation for a member defined in an interface.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="1a430-104">설명</span><span class="sxs-lookup"><span data-stu-id="1a430-104">Remarks</span></span>  
<span data-ttu-id="1a430-105">`Implements`키워드는 [Implements 문과](implements-statement.md)다릅니다.</span><span class="sxs-lookup"><span data-stu-id="1a430-105">The `Implements` keyword is not the same as the [Implements Statement](implements-statement.md).</span></span> <span data-ttu-id="1a430-106">문을 사용 하 여 `Implements` 하나 이상의 인터페이스를 구현 하는 클래스 또는 구조체를 지정 하 고 각 멤버에 대해 키워드를 사용 하 여 `Implements` 인터페이스 및 인터페이스를 구현 하는 멤버를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="1a430-106">You use the `Implements` statement to specify that a class or structure implements one or more interfaces, and then for each member you use the `Implements` keyword to specify which interface and which member it implements.</span></span>

<span data-ttu-id="1a430-107">클래스 또는 구조체에서 인터페이스를 구현 하는 경우 `Implements` [클래스 문](class-statement.md) 또는 [구조체 문](structure-statement.md)바로 뒤에 문을 포함 해야 하며, 인터페이스에서 정의 된 모든 멤버를 구현 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1a430-107">If a class or structure implements an interface, it must include the `Implements` statement immediately after the [Class Statement](class-statement.md) or [Structure Statement](structure-statement.md), and it must implement all the members defined by the interface.</span></span>

## <a name="reimplementation"></a><span data-ttu-id="1a430-108">재구현</span><span class="sxs-lookup"><span data-stu-id="1a430-108">Reimplementation</span></span>  
<span data-ttu-id="1a430-109">파생 클래스에서 기본 클래스가 이미 구현 된 인터페이스 멤버를 다시 구현할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1a430-109">In a derived class, you can reimplement an interface member that the base class has already implemented.</span></span> <span data-ttu-id="1a430-110">이는 다음과 같은 측면에서 기본 클래스 멤버를 재정의 하는 것과는 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="1a430-110">This is different from overriding the base class member in the following respects:</span></span>

- <span data-ttu-id="1a430-111">기본 클래스 멤버는 다시 구현 수 있도록 [재정의할](../modifiers/overridable.md) 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="1a430-111">The base class member does not need to be [Overridable](../modifiers/overridable.md) to be reimplemented.</span></span>
- <span data-ttu-id="1a430-112">다른 이름을 사용 하 여 멤버를 다시 구현할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1a430-112">You can reimplement the member with a different name.</span></span>

<span data-ttu-id="1a430-113">`Implements`키워드는 다음 컨텍스트에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1a430-113">The `Implements` keyword can be used in the following contexts:</span></span>

- [<span data-ttu-id="1a430-114">Event 문</span><span class="sxs-lookup"><span data-stu-id="1a430-114">Event Statement</span></span>](event-statement.md)
- [<span data-ttu-id="1a430-115">Function 문</span><span class="sxs-lookup"><span data-stu-id="1a430-115">Function Statement</span></span>](function-statement.md)
- [<span data-ttu-id="1a430-116">Property Statement</span><span class="sxs-lookup"><span data-stu-id="1a430-116">Property Statement</span></span>](property-statement.md)
- [<span data-ttu-id="1a430-117">Sub 문</span><span class="sxs-lookup"><span data-stu-id="1a430-117">Sub Statement</span></span>](sub-statement.md)  
  
## <a name="see-also"></a><span data-ttu-id="1a430-118">참고 항목</span><span class="sxs-lookup"><span data-stu-id="1a430-118">See also</span></span>

- [<span data-ttu-id="1a430-119">Implements 문</span><span class="sxs-lookup"><span data-stu-id="1a430-119">Implements Statement</span></span>](implements-statement.md)
- [<span data-ttu-id="1a430-120">Interface 문</span><span class="sxs-lookup"><span data-stu-id="1a430-120">Interface Statement</span></span>](interface-statement.md)
- [<span data-ttu-id="1a430-121">Class 문</span><span class="sxs-lookup"><span data-stu-id="1a430-121">Class Statement</span></span>](class-statement.md)
- [<span data-ttu-id="1a430-122">Structure 문</span><span class="sxs-lookup"><span data-stu-id="1a430-122">Structure Statement</span></span>](structure-statement.md)
