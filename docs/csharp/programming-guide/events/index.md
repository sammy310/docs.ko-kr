---
title: 이벤트 - C# 프로그래밍 가이드
description: 이벤트에 대해 알아봅니다. 클래스나 개체에서는 특정 상황이 발생할 때 이벤트를 통해 다른 클래스나 개체에 이를 알려 줄 수 있습니다.
ms.date: 07/20/2015
helpviewer_keywords:
- classes [C#], events
- C# language, events
- events [C#]
ms.assetid: a8e51b22-d294-44fb-9539-0072f06c4cb3
ms.openlocfilehash: 14c18006e393dece5d32d30c2a727d797515c779
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/24/2020
ms.locfileid: "91167459"
---
# <a name="events-c-programming-guide"></a><span data-ttu-id="b5365-104">이벤트(C# 프로그래밍 가이드)</span><span class="sxs-lookup"><span data-stu-id="b5365-104">Events (C# Programming Guide)</span></span>

<span data-ttu-id="b5365-105">[클래스](../../language-reference/keywords/class.md) 나 개체에서는 특정 상황이 발생할 때 이벤트를 통해 다른 클래스나 개체에 이를 알려줄 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b5365-105">Events enable a [class](../../language-reference/keywords/class.md) or object to notify other classes or objects when something of interest occurs.</span></span> <span data-ttu-id="b5365-106">이벤트를 보내거나 *발생시키는*클래스를 *게시자* 라고 하며 이벤트를 받거나 *처리하는*클래스를 *구독자*라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="b5365-106">The class that sends (or *raises*) the event is called the *publisher* and the classes that receive (or *handle*) the event are called *subscribers*.</span></span>  
  
<span data-ttu-id="b5365-107">일반적인 C# Windows Forms 또는 웹 애플리케이션, 단추 및 목록 상자 같은 컨트롤에 의해 발생하는 이벤트를 구독합니다.</span><span class="sxs-lookup"><span data-stu-id="b5365-107">In a typical C# Windows Forms or Web application, you subscribe to events raised by controls such as buttons and list boxes.</span></span> <span data-ttu-id="b5365-108">컨트롤이 게시하는 이벤트를 찾아보고 처리할 이벤트를 선택하려면 Visual C# IDE(통합 개발 환경)를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b5365-108">You can use the Visual C# integrated development environment (IDE) to browse the events that a control publishes and select the ones that you want to handle.</span></span> <span data-ttu-id="b5365-109">IDE는 빈 이벤트 처리기 메서드 및 이벤트를 구독하기 위한 코드를 자동으로 추가하는 편리한 방법을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="b5365-109">The IDE provides an easy way to automatically add an empty event handler method and the code to subscribe to the event.</span></span> <span data-ttu-id="b5365-110">자세한 내용은 [이벤트를 구독 및 구독 취소하는 방법](./how-to-subscribe-to-and-unsubscribe-from-events.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="b5365-110">For more information, see [How to subscribe to and unsubscribe from events](./how-to-subscribe-to-and-unsubscribe-from-events.md).</span></span>
  
## <a name="events-overview"></a><span data-ttu-id="b5365-111">이벤트 개요</span><span class="sxs-lookup"><span data-stu-id="b5365-111">Events Overview</span></span>  

 <span data-ttu-id="b5365-112">이벤트에는 다음과 같은 속성이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b5365-112">Events have the following properties:</span></span>  
  
- <span data-ttu-id="b5365-113">게시자는 이벤트 발생 시기를 결정합니다. 구독자는 이벤트에 대한 응답으로 수행할 작업을 결정합니다.</span><span class="sxs-lookup"><span data-stu-id="b5365-113">The publisher determines when an event is raised; the subscribers determine what action is taken in response to the event.</span></span>  
  
- <span data-ttu-id="b5365-114">한 이벤트에는 여러 구독자가 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b5365-114">An event can have multiple subscribers.</span></span> <span data-ttu-id="b5365-115">구독자는 여러 게시자의 여러 이벤트를 처리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b5365-115">A subscriber can handle multiple events from multiple publishers.</span></span>  
  
- <span data-ttu-id="b5365-116">구독자가 없는 이벤트는 발생하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b5365-116">Events that have no subscribers are never raised.</span></span>  
  
- <span data-ttu-id="b5365-117">이벤트는 일반적으로 그래픽 사용자 인터페이스에서 단추 클릭이나 메뉴 선택 같은 사용자 작업을 표시하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="b5365-117">Events are typically used to signal user actions such as button clicks or menu selections in graphical user interfaces.</span></span>  
  
- <span data-ttu-id="b5365-118">이벤트에 여러 구독자가 있는 경우 이벤트 처리기는 이벤트가 발생할 때 동기적으로 호출됩니다.</span><span class="sxs-lookup"><span data-stu-id="b5365-118">When an event has multiple subscribers, the event handlers are invoked synchronously when an event is raised.</span></span> <span data-ttu-id="b5365-119">이벤트를 비동기적으로 호출하려면 [동기 메서드를 비동기 방식으로 호출](../../../standard/asynchronous-programming-patterns/calling-synchronous-methods-asynchronously.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="b5365-119">To invoke events asynchronously, see [Calling Synchronous Methods Asynchronously](../../../standard/asynchronous-programming-patterns/calling-synchronous-methods-asynchronously.md).</span></span>  
  
- <span data-ttu-id="b5365-120">.NET 클래스 라이브러리에서 이벤트는 <xref:System.EventHandler> 대리자 및 <xref:System.EventArgs> 기본 클래스를 기반으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="b5365-120">In the .NET class library, events are based on the <xref:System.EventHandler> delegate and the <xref:System.EventArgs> base class.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="b5365-121">관련 단원</span><span class="sxs-lookup"><span data-stu-id="b5365-121">Related Sections</span></span>  

 <span data-ttu-id="b5365-122">자세한 내용은 다음을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="b5365-122">For more information, see:</span></span>  
  
- [<span data-ttu-id="b5365-123">이벤트를 구독 및 구독 취소하는 방법</span><span class="sxs-lookup"><span data-stu-id="b5365-123">How to subscribe to and unsubscribe from events</span></span>](./how-to-subscribe-to-and-unsubscribe-from-events.md)

- [<span data-ttu-id="b5365-124">.NET 지침을 따르는 이벤트를 게시하는 방법</span><span class="sxs-lookup"><span data-stu-id="b5365-124">How to publish events that conform to .NET Guidelines</span></span>](./how-to-publish-events-that-conform-to-net-framework-guidelines.md)

- [<span data-ttu-id="b5365-125">파생 클래스에서 기본 클래스 이벤트를 발생하는 방법</span><span class="sxs-lookup"><span data-stu-id="b5365-125">How to raise base class events in derived classes</span></span>](./how-to-raise-base-class-events-in-derived-classes.md)

- [<span data-ttu-id="b5365-126">인터페이스 이벤트를 구현하는 방법</span><span class="sxs-lookup"><span data-stu-id="b5365-126">How to implement interface events</span></span>](./how-to-implement-interface-events.md)

- [<span data-ttu-id="b5365-127">사용자 지정 이벤트 접근자를 구현하는 방법</span><span class="sxs-lookup"><span data-stu-id="b5365-127">How to implement custom event accessors</span></span>](./how-to-implement-custom-event-accessors.md)

## <a name="c-language-specification"></a><span data-ttu-id="b5365-128">C# 언어 사양</span><span class="sxs-lookup"><span data-stu-id="b5365-128">C# Language Specification</span></span>  

<span data-ttu-id="b5365-129">자세한 내용은 [C# 언어 사양](/dotnet/csharp/language-reference/language-specification/introduction)의 [이벤트](~/_csharplang/spec/classes.md#events)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="b5365-129">For more information, see [Events](~/_csharplang/spec/classes.md#events) in the [C# Language Specification](/dotnet/csharp/language-reference/language-specification/introduction).</span></span> <span data-ttu-id="b5365-130">언어 사양은 C# 구문 및 사용법에 대 한 신뢰할 수 있는 소스 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b5365-130">The language specification is the definitive source for C# syntax and usage.</span></span>
  
## <a name="featured-book-chapters"></a><span data-ttu-id="b5365-131">중요 설명서 장</span><span class="sxs-lookup"><span data-stu-id="b5365-131">Featured Book Chapters</span></span>  

 <span data-ttu-id="b5365-132">[대리자, Events, and Lambda Expressions](/previous-versions/visualstudio/visual-studio-2008/ff518994(v=orm.10)) 에 [ C# 3.0 Cookbook, Third Edition: 250 개 이상의 솔루션에 대 한 C# 3.0 프로그래머](/previous-versions/visualstudio/visual-studio-2008/ff518995(v=orm.10))</span><span class="sxs-lookup"><span data-stu-id="b5365-132">[Delegates, Events, and Lambda Expressions](/previous-versions/visualstudio/visual-studio-2008/ff518994(v=orm.10)) in [C# 3.0 Cookbook, Third Edition: More than 250 solutions for C# 3.0 programmers](/previous-versions/visualstudio/visual-studio-2008/ff518995(v=orm.10))</span></span>  
  
 <span data-ttu-id="b5365-133">[대리자 및 이벤트](/previous-versions/visualstudio/visual-studio-2008/ff652490(v=orm.10)) 에 [학습 C# 3.0. 기본 사항 마스터 C# 3.0](/previous-versions/visualstudio/visual-studio-2008/ff652493(v=orm.10))</span><span class="sxs-lookup"><span data-stu-id="b5365-133">[Delegates and Events](/previous-versions/visualstudio/visual-studio-2008/ff652490(v=orm.10)) in [Learning C# 3.0: Master the fundamentals of C# 3.0](/previous-versions/visualstudio/visual-studio-2008/ff652493(v=orm.10))</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b5365-134">참조</span><span class="sxs-lookup"><span data-stu-id="b5365-134">See also</span></span>

- <xref:System.EventHandler>
- [<span data-ttu-id="b5365-135">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="b5365-135">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="b5365-136">대리자</span><span class="sxs-lookup"><span data-stu-id="b5365-136">Delegates</span></span>](../delegates/index.md)
- [<span data-ttu-id="b5365-137">Windows Forms에서 이벤트 처리기 만들기</span><span class="sxs-lookup"><span data-stu-id="b5365-137">Creating Event Handlers in Windows Forms</span></span>](/dotnet/desktop/winforms/creating-event-handlers-in-windows-forms)
