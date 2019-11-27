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
# <a name="withevents-visual-basic"></a><span data-ttu-id="50205-102">WithEvents(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="50205-102">WithEvents (Visual Basic)</span></span>
<span data-ttu-id="50205-103">하나 이상의 선언 된 멤버 변수가 이벤트를 발생 시킬 수 있는 클래스의 인스턴스를 참조 하도록 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="50205-103">Specifies that one or more declared member variables refer to an instance of a class that can raise events.</span></span>

## <a name="remarks"></a><span data-ttu-id="50205-104">주의</span><span class="sxs-lookup"><span data-stu-id="50205-104">Remarks</span></span>

<span data-ttu-id="50205-105">`WithEvents`를 사용 하 여 변수를 정의 하는 경우 메서드가 `Handles` 키워드를 사용 하 여 변수의 이벤트를 처리 하도록 선언적으로 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="50205-105">When a variable is defined using `WithEvents`, you can declaratively specify that a method handles the variable's events using the `Handles` keyword.</span></span>

<span data-ttu-id="50205-106">클래스 또는 모듈 수준 에서만 `WithEvents`를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="50205-106">You can use `WithEvents` only at class or module level.</span></span> <span data-ttu-id="50205-107">즉, `WithEvents` 변수의 선언 컨텍스트는 클래스 또는 모듈 이어야 하며 소스 파일, 네임 스페이스, 구조 또는 프로시저일 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="50205-107">This means the declaration context for a `WithEvents` variable must be a class or module and cannot be a source file, namespace, structure, or procedure.</span></span>

<span data-ttu-id="50205-108">구조체 멤버에는 `WithEvents`를 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="50205-108">You cannot use `WithEvents` on a structure member.</span></span>

<span data-ttu-id="50205-109">`WithEvents`를 사용 하 여 배열이 아닌 개별 변수만 선언할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="50205-109">You can declare only individual variables—not arrays—with `WithEvents`.</span></span>

## <a name="rules"></a><span data-ttu-id="50205-110">규칙</span><span class="sxs-lookup"><span data-stu-id="50205-110">Rules</span></span>

<span data-ttu-id="50205-111">**요소 형식.**</span><span class="sxs-lookup"><span data-stu-id="50205-111">**Element Types.**</span></span> <span data-ttu-id="50205-112">클래스 인스턴스를 사용할 수 있도록 `WithEvents` 변수를 개체 변수로 선언 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="50205-112">You must declare `WithEvents` variables to be object variables so that they can accept class instances.</span></span> <span data-ttu-id="50205-113">그러나 `Object`로 선언할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="50205-113">However, you cannot declare them as `Object`.</span></span> <span data-ttu-id="50205-114">이벤트를 발생 시킬 수 있는 특정 클래스로 선언 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="50205-114">You must declare them as the specific class that can raise the events.</span></span>

<span data-ttu-id="50205-115">이 컨텍스트에서는 `WithEvents` 한정자를 사용할 수 있습니다. [Dim 문](../../../visual-basic/language-reference/statements/dim-statement.md)</span><span class="sxs-lookup"><span data-stu-id="50205-115">The `WithEvents` modifier can be used in this context: [Dim Statement](../../../visual-basic/language-reference/statements/dim-statement.md)</span></span>

## <a name="example"></a><span data-ttu-id="50205-116">예제</span><span class="sxs-lookup"><span data-stu-id="50205-116">Example</span></span>

```vb
Dim WithEvents app As Application
```

## <a name="see-also"></a><span data-ttu-id="50205-117">참고 항목</span><span class="sxs-lookup"><span data-stu-id="50205-117">See also</span></span>

- <span data-ttu-id="50205-118">[!](../../../visual-basic/language-reference/statements/handles-clause.md)</span><span class="sxs-lookup"><span data-stu-id="50205-118">[Handles](../../../visual-basic/language-reference/statements/handles-clause.md)</span></span>
- [<span data-ttu-id="50205-119">키워드</span><span class="sxs-lookup"><span data-stu-id="50205-119">Keywords</span></span>](../../../visual-basic/language-reference/keywords/index.md)
- [<span data-ttu-id="50205-120">이벤트</span><span class="sxs-lookup"><span data-stu-id="50205-120">Events</span></span>](../../../visual-basic/programming-guide/language-features/events/index.md)
