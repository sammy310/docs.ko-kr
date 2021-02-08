---
description: '자세히 알아보기: Handles 절 (Visual Basic)'
title: Handles 절
ms.date: 07/20/2015
f1_keywords:
- Handles
- vb.Handles
helpviewer_keywords:
- Handles keyword [Visual Basic]
ms.assetid: 1b051c0e-f499-42f6-acb5-6f4f27824b40
ms.openlocfilehash: 2bddfdecc163feacaaf042a7928ab16af324b0a3
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99769028"
---
# <a name="handles-clause-visual-basic"></a><span data-ttu-id="ed085-103">Handles 절(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="ed085-103">Handles Clause (Visual Basic)</span></span>

<span data-ttu-id="ed085-104">지정된 이벤트를 처리하는 프로시저를 선언합니다.</span><span class="sxs-lookup"><span data-stu-id="ed085-104">Declares that a procedure handles a specified event.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ed085-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="ed085-105">Syntax</span></span>  
  
```vb  
proceduredeclaration Handles eventlist  
```  
  
## <a name="parts"></a><span data-ttu-id="ed085-106">부분</span><span class="sxs-lookup"><span data-stu-id="ed085-106">Parts</span></span>  

 `proceduredeclaration`  
 <span data-ttu-id="ed085-107">이벤트를 처리할 프로시저에 대한 `Sub` 프로시저 선언입니다.</span><span class="sxs-lookup"><span data-stu-id="ed085-107">The `Sub` procedure declaration for the procedure that will handle the event.</span></span>  
  
 `eventlist`  
 <span data-ttu-id="ed085-108">처리할 `proceduredeclaration`에 대한 이벤트 목록으로, 쉼표로 구분합니다.</span><span class="sxs-lookup"><span data-stu-id="ed085-108">List of the events for `proceduredeclaration` to handle, separated by commas.</span></span> <span data-ttu-id="ed085-109">이벤트는 현재 클래스에 대한 기본 클래스 또는 `WithEvents` 키워드를 사용하여 선언된 개체에 의해 발생해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ed085-109">The events must be raised by either the base class for the current class, or by an object declared using the `WithEvents` keyword.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ed085-110">설명</span><span class="sxs-lookup"><span data-stu-id="ed085-110">Remarks</span></span>  

 <span data-ttu-id="ed085-111">프로시저 선언의 끝에서 `Handles` 키워드를 사용하여 `WithEvents` 키워드로 선언된 개체 변수에 의해 발생된 이벤트를 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="ed085-111">Use the `Handles` keyword at the end of a procedure declaration to cause it to handle events raised by an object variable declared using the `WithEvents` keyword.</span></span> <span data-ttu-id="ed085-112">`Handles` 키워드는 파생 클래스에서 기본 클래스의 이벤트를 처리하는 데도 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ed085-112">The `Handles` keyword can also be used in a derived class to handle events from a base class.</span></span>  
  
 <span data-ttu-id="ed085-113">`Handles` 키워드와 `AddHandler` 문 모두 특정 프로시저에서 특정 이벤트를 처리하도록 지정하는 데 사용할 수 있지만 차이가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ed085-113">The `Handles` keyword and the `AddHandler` statement both allow you to specify that particular procedures handle particular events, but there are differences.</span></span> <span data-ttu-id="ed085-114">특정 이벤트를 처리하도록 지정하는 프로시저를 정의할 때 `Handles` 키워드를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="ed085-114">Use the `Handles` keyword when defining a procedure to specify that it handles a particular event.</span></span> <span data-ttu-id="ed085-115">`AddHandler` 문은 런타임에 프로시저를 이벤트에 연결합니다.</span><span class="sxs-lookup"><span data-stu-id="ed085-115">The `AddHandler` statement connects procedures to events at run time.</span></span> <span data-ttu-id="ed085-116">자세한 내용은 [AddHandler 문](addhandler-statement.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="ed085-116">For more information, see [AddHandler Statement](addhandler-statement.md).</span></span>  
  
 <span data-ttu-id="ed085-117">사용자 지정 이벤트의 경우 애플리케이션은 이벤트 처리기로 프로시저를 추가할 때 이벤트의 `AddHandler` 접근자를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="ed085-117">For custom events, the application invokes the event's `AddHandler` accessor when it adds the procedure as an event handler.</span></span> <span data-ttu-id="ed085-118">사용자 지정 이벤트에 대 한 자세한 내용은 [이벤트 문](event-statement.md)을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="ed085-118">For more information on custom events, see [Event Statement](event-statement.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="ed085-119">예제</span><span class="sxs-lookup"><span data-stu-id="ed085-119">Example</span></span>  

 [!code-vb[VbVbalrEvents#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrEvents/VB/Class1.vb#2)]  
  
 <span data-ttu-id="ed085-120">다음 예제에서는 파생 클래스가 `Handles` 문을 사용하여 기본 클래스의 이벤트를 처리하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="ed085-120">The following example demonstrates how a derived class can use the `Handles` statement to handle an event from a base class.</span></span>  
  
 [!code-vb[VbVbalrEvents#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrEvents/VB/Class1.vb#3)]  
  
## <a name="example"></a><span data-ttu-id="ed085-121">예제</span><span class="sxs-lookup"><span data-stu-id="ed085-121">Example</span></span>  

 <span data-ttu-id="ed085-122">다음 예제에는 **WPF 응용 프로그램** 프로젝트에 대 한 두 개의 단추 이벤트 처리기가 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ed085-122">The following example contains two button event handlers for a **WPF Application** project.</span></span>  
  
 [!code-vb[VbVbalrEvents#41](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrEvents/VB/class3.vb#41)]  
  
## <a name="example"></a><span data-ttu-id="ed085-123">예제</span><span class="sxs-lookup"><span data-stu-id="ed085-123">Example</span></span>  

 <span data-ttu-id="ed085-124">다음 예제는 이전 예제와 동일합니다.</span><span class="sxs-lookup"><span data-stu-id="ed085-124">The following example is equivalent to the previous example.</span></span> <span data-ttu-id="ed085-125">`Handles` 절의 `eventlist`에는 두 단추에 대한 이벤트가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ed085-125">The `eventlist` in the `Handles` clause contains the events for both buttons.</span></span>  
  
 [!code-vb[VbVbalrEvents#42](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrEvents/VB/class3.vb#42)]  
  
## <a name="see-also"></a><span data-ttu-id="ed085-126">참고 항목</span><span class="sxs-lookup"><span data-stu-id="ed085-126">See also</span></span>

- [<span data-ttu-id="ed085-127">WithEvents</span><span class="sxs-lookup"><span data-stu-id="ed085-127">WithEvents</span></span>](../modifiers/withevents.md)
- [<span data-ttu-id="ed085-128">AddHandler 문</span><span class="sxs-lookup"><span data-stu-id="ed085-128">AddHandler Statement</span></span>](addhandler-statement.md)
- [<span data-ttu-id="ed085-129">RemoveHandler 문</span><span class="sxs-lookup"><span data-stu-id="ed085-129">RemoveHandler Statement</span></span>](removehandler-statement.md)
- [<span data-ttu-id="ed085-130">Event 문</span><span class="sxs-lookup"><span data-stu-id="ed085-130">Event Statement</span></span>](event-statement.md)
- [<span data-ttu-id="ed085-131">RaiseEvent 문</span><span class="sxs-lookup"><span data-stu-id="ed085-131">RaiseEvent Statement</span></span>](raiseevent-statement.md)
- [<span data-ttu-id="ed085-132">이벤트</span><span class="sxs-lookup"><span data-stu-id="ed085-132">Events</span></span>](../../programming-guide/language-features/events/index.md)
