---
description: '자세한 정보: WithEvents (Visual Basic)'
title: WithEvents
ms.date: 07/20/2015
f1_keywords:
- vb.WithEvents
- WithEvents
helpviewer_keywords:
- WithEvents keyword [Visual Basic]
ms.assetid: 19d461f5-d72f-4de9-8c1d-0a6650316990
ms.openlocfilehash: b27f84fe54aaa10bc9b2359cd74fad3d3ace1ad5
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99674768"
---
# <a name="withevents-visual-basic"></a><span data-ttu-id="e0d8f-103">WithEvents(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="e0d8f-103">WithEvents (Visual Basic)</span></span>

<span data-ttu-id="e0d8f-104">하나 이상의 선언 된 멤버 변수가 이벤트를 발생 시킬 수 있는 클래스의 인스턴스를 참조 하도록 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="e0d8f-104">Specifies that one or more declared member variables refer to an instance of a class that can raise events.</span></span>

## <a name="remarks"></a><span data-ttu-id="e0d8f-105">설명</span><span class="sxs-lookup"><span data-stu-id="e0d8f-105">Remarks</span></span>

<span data-ttu-id="e0d8f-106">를 사용 하 여 변수를 정의 하는 경우 `WithEvents` 메서드가 키워드를 사용 하 여 변수의 이벤트를 처리 하도록 선언적으로 지정할 수 있습니다 `Handles` .</span><span class="sxs-lookup"><span data-stu-id="e0d8f-106">When a variable is defined using `WithEvents`, you can declaratively specify that a method handles the variable's events using the `Handles` keyword.</span></span>

<span data-ttu-id="e0d8f-107">는 `WithEvents` 클래스 또는 모듈 수준 에서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e0d8f-107">You can use `WithEvents` only at class or module level.</span></span> <span data-ttu-id="e0d8f-108">즉, 변수에 대 한 선언 컨텍스트는 `WithEvents` 클래스 또는 모듈 이어야 하며 소스 파일, 네임 스페이스, 구조 또는 프로시저일 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="e0d8f-108">This means the declaration context for a `WithEvents` variable must be a class or module and cannot be a source file, namespace, structure, or procedure.</span></span>

<span data-ttu-id="e0d8f-109">`WithEvents`구조체 멤버에는를 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="e0d8f-109">You cannot use `WithEvents` on a structure member.</span></span>

<span data-ttu-id="e0d8f-110">에서는 배열이 아니라 개별 변수만 선언할 수 있습니다 `WithEvents` .</span><span class="sxs-lookup"><span data-stu-id="e0d8f-110">You can declare only individual variables—not arrays—with `WithEvents`.</span></span>

## <a name="rules"></a><span data-ttu-id="e0d8f-111">규칙</span><span class="sxs-lookup"><span data-stu-id="e0d8f-111">Rules</span></span>

<span data-ttu-id="e0d8f-112">**요소 형식.**</span><span class="sxs-lookup"><span data-stu-id="e0d8f-112">**Element Types.**</span></span> <span data-ttu-id="e0d8f-113">`WithEvents`클래스 인스턴스를 사용할 수 있도록 변수를 개체 변수로 선언 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e0d8f-113">You must declare `WithEvents` variables to be object variables so that they can accept class instances.</span></span> <span data-ttu-id="e0d8f-114">그러나이를로 선언할 수는 없습니다 `Object` .</span><span class="sxs-lookup"><span data-stu-id="e0d8f-114">However, you cannot declare them as `Object`.</span></span> <span data-ttu-id="e0d8f-115">이벤트를 발생 시킬 수 있는 특정 클래스로 선언 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e0d8f-115">You must declare them as the specific class that can raise the events.</span></span>

<span data-ttu-id="e0d8f-116">`WithEvents`이 컨텍스트에서 한정자를 사용할 수 있습니다. [Dim 문](../statements/dim-statement.md)</span><span class="sxs-lookup"><span data-stu-id="e0d8f-116">The `WithEvents` modifier can be used in this context: [Dim Statement](../statements/dim-statement.md)</span></span>

## <a name="example"></a><span data-ttu-id="e0d8f-117">예제</span><span class="sxs-lookup"><span data-stu-id="e0d8f-117">Example</span></span>

```vb
Dim WithEvents app As Application
```

## <a name="see-also"></a><span data-ttu-id="e0d8f-118">참고 항목</span><span class="sxs-lookup"><span data-stu-id="e0d8f-118">See also</span></span>

- [<span data-ttu-id="e0d8f-119">핸들</span><span class="sxs-lookup"><span data-stu-id="e0d8f-119">Handles</span></span>](../statements/handles-clause.md)
- [<span data-ttu-id="e0d8f-120">C++ 키워드</span><span class="sxs-lookup"><span data-stu-id="e0d8f-120">Keywords</span></span>](../keywords/index.md)
- [<span data-ttu-id="e0d8f-121">이벤트</span><span class="sxs-lookup"><span data-stu-id="e0d8f-121">Events</span></span>](../../programming-guide/language-features/events/index.md)
