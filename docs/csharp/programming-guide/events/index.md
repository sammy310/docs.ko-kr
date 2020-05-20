---
title: 이벤트 - C# 프로그래밍 가이드
ms.date: 07/20/2015
helpviewer_keywords:
- classes [C#], events
- C# language, events
- events [C#]
ms.assetid: a8e51b22-d294-44fb-9539-0072f06c4cb3
ms.openlocfilehash: 183f53a579bdd9f70deb16ca9157c377fa3aff3f
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/15/2020
ms.locfileid: "75712314"
---
# <a name="events-c-programming-guide"></a><span data-ttu-id="6b7d6-102">이벤트(C# 프로그래밍 가이드)</span><span class="sxs-lookup"><span data-stu-id="6b7d6-102">Events (C# Programming Guide)</span></span>
<span data-ttu-id="6b7d6-103">[클래스](../../language-reference/keywords/class.md) 나 개체에서는 특정 상황이 발생할 때 이벤트를 통해 다른 클래스나 개체에 이를 알려줄 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6b7d6-103">Events enable a [class](../../language-reference/keywords/class.md) or object to notify other classes or objects when something of interest occurs.</span></span> <span data-ttu-id="6b7d6-104">이벤트를 보내거나 *발생시키는*클래스를 *게시자* 라고 하며 이벤트를 받거나 *처리하는*클래스를 *구독자*라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="6b7d6-104">The class that sends (or *raises*) the event is called the *publisher* and the classes that receive (or *handle*) the event are called *subscribers*.</span></span>  
  
<span data-ttu-id="6b7d6-105">일반적인 C# Windows Forms 또는 웹 애플리케이션, 단추 및 목록 상자 같은 컨트롤에 의해 발생하는 이벤트를 구독합니다.</span><span class="sxs-lookup"><span data-stu-id="6b7d6-105">In a typical C# Windows Forms or Web application, you subscribe to events raised by controls such as buttons and list boxes.</span></span> <span data-ttu-id="6b7d6-106">컨트롤이 게시하는 이벤트를 찾아보고 처리할 이벤트를 선택하려면 Visual C# IDE(통합 개발 환경)를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6b7d6-106">You can use the Visual C# integrated development environment (IDE) to browse the events that a control publishes and select the ones that you want to handle.</span></span> <span data-ttu-id="6b7d6-107">IDE는 빈 이벤트 처리기 메서드 및 이벤트를 구독하기 위한 코드를 자동으로 추가하는 편리한 방법을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="6b7d6-107">The IDE provides an easy way to automatically add an empty event handler method and the code to subscribe to the event.</span></span> <span data-ttu-id="6b7d6-108">자세한 내용은 [이벤트를 구독 및 구독 취소하는 방법](./how-to-subscribe-to-and-unsubscribe-from-events.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="6b7d6-108">For more information, see [How to subscribe to and unsubscribe from events](./how-to-subscribe-to-and-unsubscribe-from-events.md).</span></span>
  
## <a name="events-overview"></a><span data-ttu-id="6b7d6-109">이벤트 개요</span><span class="sxs-lookup"><span data-stu-id="6b7d6-109">Events Overview</span></span>  
 <span data-ttu-id="6b7d6-110">이벤트에는 다음과 같은 속성이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6b7d6-110">Events have the following properties:</span></span>  
  
- <span data-ttu-id="6b7d6-111">게시자는 이벤트 발생 시기를 결정합니다. 구독자는 이벤트에 대한 응답으로 수행할 작업을 결정합니다.</span><span class="sxs-lookup"><span data-stu-id="6b7d6-111">The publisher determines when an event is raised; the subscribers determine what action is taken in response to the event.</span></span>  
  
- <span data-ttu-id="6b7d6-112">한 이벤트에는 여러 구독자가 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6b7d6-112">An event can have multiple subscribers.</span></span> <span data-ttu-id="6b7d6-113">구독자는 여러 게시자의 여러 이벤트를 처리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6b7d6-113">A subscriber can handle multiple events from multiple publishers.</span></span>  
  
- <span data-ttu-id="6b7d6-114">구독자가 없는 이벤트는 발생하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="6b7d6-114">Events that have no subscribers are never raised.</span></span>  
  
- <span data-ttu-id="6b7d6-115">이벤트는 일반적으로 그래픽 사용자 인터페이스에서 단추 클릭이나 메뉴 선택 같은 사용자 작업을 표시하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="6b7d6-115">Events are typically used to signal user actions such as button clicks or menu selections in graphical user interfaces.</span></span>  
  
- <span data-ttu-id="6b7d6-116">이벤트에 여러 구독자가 있는 경우 이벤트 처리기는 이벤트가 발생할 때 동기적으로 호출됩니다.</span><span class="sxs-lookup"><span data-stu-id="6b7d6-116">When an event has multiple subscribers, the event handlers are invoked synchronously when an event is raised.</span></span> <span data-ttu-id="6b7d6-117">이벤트를 비동기적으로 호출하려면 [Calling Synchronous Methods Asynchronously](../../../standard/asynchronous-programming-patterns/calling-synchronous-methods-asynchronously.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="6b7d6-117">To invoke events asynchronously, see [Calling Synchronous Methods Asynchronously](../../../standard/asynchronous-programming-patterns/calling-synchronous-methods-asynchronously.md).</span></span>  
  
- <span data-ttu-id="6b7d6-118">.NET Framework 클래스 라이브러리에서 이벤트는 <xref:System.EventHandler> 대리자 및 <xref:System.EventArgs> 기본 클래스를 기반으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="6b7d6-118">In the .NET Framework class library, events are based on the <xref:System.EventHandler> delegate and the <xref:System.EventArgs> base class.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="6b7d6-119">관련 단원</span><span class="sxs-lookup"><span data-stu-id="6b7d6-119">Related Sections</span></span>  
 <span data-ttu-id="6b7d6-120">자세한 내용은 다음을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="6b7d6-120">For more information, see:</span></span>  
  
- [<span data-ttu-id="6b7d6-121">이벤트를 구독 및 구독 취소하는 방법</span><span class="sxs-lookup"><span data-stu-id="6b7d6-121">How to subscribe to and unsubscribe from events</span></span>](./how-to-subscribe-to-and-unsubscribe-from-events.md)

- [<span data-ttu-id="6b7d6-122">.NET Framework 지침을 따르는 이벤트를 게시하는 방법</span><span class="sxs-lookup"><span data-stu-id="6b7d6-122">How to publish events that conform to .NET Framework Guidelines</span></span>](./how-to-publish-events-that-conform-to-net-framework-guidelines.md)

- [<span data-ttu-id="6b7d6-123">파생 클래스에서 기본 클래스 이벤트를 발생하는 방법</span><span class="sxs-lookup"><span data-stu-id="6b7d6-123">How to raise base class events in derived classes</span></span>](./how-to-raise-base-class-events-in-derived-classes.md)

- [<span data-ttu-id="6b7d6-124">인터페이스 이벤트를 구현하는 방법</span><span class="sxs-lookup"><span data-stu-id="6b7d6-124">How to implement interface events</span></span>](./how-to-implement-interface-events.md)

- [<span data-ttu-id="6b7d6-125">사용자 지정 이벤트 접근자를 구현하는 방법</span><span class="sxs-lookup"><span data-stu-id="6b7d6-125">How to implement custom event accessors</span></span>](./how-to-implement-custom-event-accessors.md)

## <a name="c-language-specification"></a><span data-ttu-id="6b7d6-126">C# 언어 사양</span><span class="sxs-lookup"><span data-stu-id="6b7d6-126">C# Language Specification</span></span>  

<span data-ttu-id="6b7d6-127">자세한 내용은 [C# 언어 사양](/dotnet/csharp/language-reference/language-specification/introduction)의 [이벤트](~/_csharplang/spec/classes.md#events)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="6b7d6-127">For more information, see [Events](~/_csharplang/spec/classes.md#events) in the [C# Language Specification](/dotnet/csharp/language-reference/language-specification/introduction).</span></span> <span data-ttu-id="6b7d6-128">언어 사양은 C# 구문 및 사용법에 대 한 신뢰할 수 있는 소스 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6b7d6-128">The language specification is the definitive source for C# syntax and usage.</span></span>
  
## <a name="featured-book-chapters"></a><span data-ttu-id="6b7d6-129">중요 설명서 장</span><span class="sxs-lookup"><span data-stu-id="6b7d6-129">Featured Book Chapters</span></span>  
 <span data-ttu-id="6b7d6-130">[C# 3.0 Cookbook, Third Edition: More than 250 solutions for C# 3.0 programmers](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/ff518994%28v=orm.10%29) 의 [Delegates, Events, and Lambda Expressions](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/ff518995%28v=orm.10%29)</span><span class="sxs-lookup"><span data-stu-id="6b7d6-130">[Delegates, Events, and Lambda Expressions](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/ff518994%28v=orm.10%29) in [C# 3.0 Cookbook, Third Edition: More than 250 solutions for C# 3.0 programmers](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/ff518995%28v=orm.10%29)</span></span>  
  
 <span data-ttu-id="6b7d6-131">[Delegates and Events](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/ff652490%28v=orm.10%29) in [Learning C# 3.0: Master the fundamentals of C# 3.0](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/ff652493%28v=orm.10%29)</span><span class="sxs-lookup"><span data-stu-id="6b7d6-131">[Delegates and Events](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/ff652490%28v=orm.10%29) in [Learning C# 3.0: Master the fundamentals of C# 3.0](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/ff652493%28v=orm.10%29)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6b7d6-132">참고 항목</span><span class="sxs-lookup"><span data-stu-id="6b7d6-132">See also</span></span>

- <xref:System.EventHandler>
- [<span data-ttu-id="6b7d6-133">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="6b7d6-133">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="6b7d6-134">대리자</span><span class="sxs-lookup"><span data-stu-id="6b7d6-134">Delegates</span></span>](../delegates/index.md)
- [<span data-ttu-id="6b7d6-135">Windows Forms에서 이벤트 처리기 만들기</span><span class="sxs-lookup"><span data-stu-id="6b7d6-135">Creating Event Handlers in Windows Forms</span></span>](../../../framework/winforms/creating-event-handlers-in-windows-forms.md)
