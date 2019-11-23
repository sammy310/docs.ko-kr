---
title: WithEvents
ms.date: 07/20/2015
f1_keywords:
- vb.WithEvents
- WithEvents
helpviewer_keywords:
- WithEvents keyword [Visual Basic]
ms.assetid: 19d461f5-d72f-4de9-8c1d-0a6650316990
ms.openlocfilehash: 2309c675b50a2025d73841a47fe8e30e7cecd522
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/22/2019
ms.locfileid: "74350750"
---
# <a name="withevents-visual-basic"></a><span data-ttu-id="796cc-102">WithEvents(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="796cc-102">WithEvents (Visual Basic)</span></span>
<span data-ttu-id="796cc-103">Specifies that one or more declared member variables refer to an instance of a class that can raise events.</span><span class="sxs-lookup"><span data-stu-id="796cc-103">Specifies that one or more declared member variables refer to an instance of a class that can raise events.</span></span>

## <a name="remarks"></a><span data-ttu-id="796cc-104">주의</span><span class="sxs-lookup"><span data-stu-id="796cc-104">Remarks</span></span>

<span data-ttu-id="796cc-105">When a variable is defined using `WithEvents`, you can declaratively specify that a method handles the variable's events using the `Handles` keyword.</span><span class="sxs-lookup"><span data-stu-id="796cc-105">When a variable is defined using `WithEvents`, you can declaratively specify that a method handles the variable's events using the `Handles` keyword.</span></span>

<span data-ttu-id="796cc-106">You can use `WithEvents` only at class or module level.</span><span class="sxs-lookup"><span data-stu-id="796cc-106">You can use `WithEvents` only at class or module level.</span></span> <span data-ttu-id="796cc-107">This means the declaration context for a `WithEvents` variable must be a class or module and cannot be a source file, namespace, structure, or procedure.</span><span class="sxs-lookup"><span data-stu-id="796cc-107">This means the declaration context for a `WithEvents` variable must be a class or module and cannot be a source file, namespace, structure, or procedure.</span></span>

<span data-ttu-id="796cc-108">You cannot use `WithEvents` on a structure member.</span><span class="sxs-lookup"><span data-stu-id="796cc-108">You cannot use `WithEvents` on a structure member.</span></span>

<span data-ttu-id="796cc-109">You can declare only individual variables—not arrays—with `WithEvents`.</span><span class="sxs-lookup"><span data-stu-id="796cc-109">You can declare only individual variables—not arrays—with `WithEvents`.</span></span>

## <a name="rules"></a><span data-ttu-id="796cc-110">규칙</span><span class="sxs-lookup"><span data-stu-id="796cc-110">Rules</span></span>

<span data-ttu-id="796cc-111">**Element Types.**</span><span class="sxs-lookup"><span data-stu-id="796cc-111">**Element Types.**</span></span> <span data-ttu-id="796cc-112">You must declare `WithEvents` variables to be object variables so that they can accept class instances.</span><span class="sxs-lookup"><span data-stu-id="796cc-112">You must declare `WithEvents` variables to be object variables so that they can accept class instances.</span></span> <span data-ttu-id="796cc-113">However, you cannot declare them as `Object`.</span><span class="sxs-lookup"><span data-stu-id="796cc-113">However, you cannot declare them as `Object`.</span></span> <span data-ttu-id="796cc-114">You must declare them as the specific class that can raise the events.</span><span class="sxs-lookup"><span data-stu-id="796cc-114">You must declare them as the specific class that can raise the events.</span></span>

<span data-ttu-id="796cc-115">The `WithEvents` modifier can be used in this context: [Dim Statement](../../../visual-basic/language-reference/statements/dim-statement.md)</span><span class="sxs-lookup"><span data-stu-id="796cc-115">The `WithEvents` modifier can be used in this context: [Dim Statement](../../../visual-basic/language-reference/statements/dim-statement.md)</span></span>

## <a name="example"></a><span data-ttu-id="796cc-116">예제</span><span class="sxs-lookup"><span data-stu-id="796cc-116">Example</span></span>

```vb
Dim WithEvents app As Application
```

## <a name="see-also"></a><span data-ttu-id="796cc-117">참조</span><span class="sxs-lookup"><span data-stu-id="796cc-117">See also</span></span>

- [<span data-ttu-id="796cc-118">Handles</span><span class="sxs-lookup"><span data-stu-id="796cc-118">Handles</span></span>](../../../visual-basic/language-reference/statements/handles-clause.md)
- [<span data-ttu-id="796cc-119">C++ 키워드</span><span class="sxs-lookup"><span data-stu-id="796cc-119">Keywords</span></span>](../../../visual-basic/language-reference/keywords/index.md)
- [<span data-ttu-id="796cc-120">이벤트</span><span class="sxs-lookup"><span data-stu-id="796cc-120">Events</span></span>](../../../visual-basic/programming-guide/language-features/events/index.md)
