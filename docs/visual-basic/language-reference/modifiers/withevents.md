---
title: WithEvents(Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.WithEvents
- WithEvents
helpviewer_keywords:
- WithEvents keyword [Visual Basic]
ms.assetid: 19d461f5-d72f-4de9-8c1d-0a6650316990
ms.openlocfilehash: 50d5a768393e90d28d150b451405e35e6f4c7953
ms.sourcegitcommit: 1f12db2d852d05bed8c53845f0b5a57a762979c8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2019
ms.locfileid: "72583037"
---
# <a name="withevents-visual-basic"></a><span data-ttu-id="585d5-102">WithEvents(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="585d5-102">WithEvents (Visual Basic)</span></span>
<span data-ttu-id="585d5-103">하나 이상의 선언 된 멤버 변수가 이벤트를 발생 시킬 수 있는 클래스의 인스턴스를 참조 하도록 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="585d5-103">Specifies that one or more declared member variables refer to an instance of a class that can raise events.</span></span>

## <a name="remarks"></a><span data-ttu-id="585d5-104">주의</span><span class="sxs-lookup"><span data-stu-id="585d5-104">Remarks</span></span>

<span data-ttu-id="585d5-105">@No__t_0를 사용 하 여 변수를 정의 하는 경우 메서드가 `Handles` 키워드를 사용 하 여 변수의 이벤트를 처리 하도록 선언적으로 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="585d5-105">When a variable is defined using `WithEvents`, you can declaratively specify that a method handles the variable's events using the `Handles` keyword.</span></span>

<span data-ttu-id="585d5-106">클래스 또는 모듈 수준 에서만 `WithEvents`를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="585d5-106">You can use `WithEvents` only at class or module level.</span></span> <span data-ttu-id="585d5-107">즉, `WithEvents` 변수의 선언 컨텍스트는 클래스 또는 모듈 이어야 하며 소스 파일, 네임 스페이스, 구조 또는 프로시저일 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="585d5-107">This means the declaration context for a `WithEvents` variable must be a class or module and cannot be a source file, namespace, structure, or procedure.</span></span>

<span data-ttu-id="585d5-108">구조체 멤버에는 `WithEvents`를 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="585d5-108">You cannot use `WithEvents` on a structure member.</span></span>

<span data-ttu-id="585d5-109">@No__t_0를 사용 하 여 배열이 아닌 개별 변수만 선언할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="585d5-109">You can declare only individual variables—not arrays—with `WithEvents`.</span></span>

## <a name="rules"></a><span data-ttu-id="585d5-110">규칙</span><span class="sxs-lookup"><span data-stu-id="585d5-110">Rules</span></span>

<span data-ttu-id="585d5-111">**요소 형식.**</span><span class="sxs-lookup"><span data-stu-id="585d5-111">**Element Types.**</span></span> <span data-ttu-id="585d5-112">클래스 인스턴스를 사용할 수 있도록 `WithEvents` 변수를 개체 변수로 선언 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="585d5-112">You must declare `WithEvents` variables to be object variables so that they can accept class instances.</span></span> <span data-ttu-id="585d5-113">그러나 `Object`로 선언할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="585d5-113">However, you cannot declare them as `Object`.</span></span> <span data-ttu-id="585d5-114">이벤트를 발생 시킬 수 있는 특정 클래스로 선언 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="585d5-114">You must declare them as the specific class that can raise the events.</span></span>

<span data-ttu-id="585d5-115">이 컨텍스트에서는 `WithEvents` 한정자를 사용할 수 있습니다. [Dim 문](../../../visual-basic/language-reference/statements/dim-statement.md)</span><span class="sxs-lookup"><span data-stu-id="585d5-115">The `WithEvents` modifier can be used in this context: [Dim Statement](../../../visual-basic/language-reference/statements/dim-statement.md)</span></span>

## <a name="example"></a><span data-ttu-id="585d5-116">예제</span><span class="sxs-lookup"><span data-stu-id="585d5-116">Example</span></span>

```vb
Dim WithEvents app As Application
```

## <a name="see-also"></a><span data-ttu-id="585d5-117">참조</span><span class="sxs-lookup"><span data-stu-id="585d5-117">See also</span></span>

- [<span data-ttu-id="585d5-118">Handles</span><span class="sxs-lookup"><span data-stu-id="585d5-118">Handles</span></span>](../../../visual-basic/language-reference/statements/handles-clause.md)
- [<span data-ttu-id="585d5-119">C++ 키워드</span><span class="sxs-lookup"><span data-stu-id="585d5-119">Keywords</span></span>](../../../visual-basic/language-reference/keywords/index.md)
- [<span data-ttu-id="585d5-120">이벤트</span><span class="sxs-lookup"><span data-stu-id="585d5-120">Events</span></span>](../../../visual-basic/programming-guide/language-features/events/index.md)
