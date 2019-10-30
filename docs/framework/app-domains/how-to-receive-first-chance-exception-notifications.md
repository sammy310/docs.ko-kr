---
title: '방법: 첫째 예외 알림 받기'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- first-chance exception notifications
- exceptions, first chance notifications
ms.assetid: 66f002b8-a97d-4a6e-a503-2cec01689113
ms.openlocfilehash: da60dfca424f7c10e810b5e083ff7fa63a688218
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73119871"
---
# <a name="how-to-receive-first-chance-exception-notifications"></a><span data-ttu-id="5f58c-102">방법: 첫째 예외 알림 받기</span><span class="sxs-lookup"><span data-stu-id="5f58c-102">How to: Receive First-Chance Exception Notifications</span></span>
<span data-ttu-id="5f58c-103"><xref:System.AppDomain> 클래스의 <xref:System.AppDomain.FirstChanceException> 이벤트를 사용하면 공용 언어 런타임이 예외 처리기 검색을 시작하기 전에 예외가 throw되었다는 알림을 받을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5f58c-103">The <xref:System.AppDomain.FirstChanceException> event of the <xref:System.AppDomain> class lets you receive a notification that an exception has been thrown, before the common language runtime has begun searching for exception handlers.</span></span>

 <span data-ttu-id="5f58c-104">이 이벤트는 애플리케이션 도메인 수준에서 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="5f58c-104">The event is raised at the application domain level.</span></span> <span data-ttu-id="5f58c-105">하나의 실행 스레드가 여러 애플리케이션 도메인을 통과할 수 있으므로 한 애플리케이션 도메인에서 처리되지 않은 예외가 다른 애플리케이션 도메인에서 처리될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5f58c-105">A thread of execution can pass through multiple application domains, so an exception that is unhandled in one application domain could be handled in another application domain.</span></span> <span data-ttu-id="5f58c-106">애플리케이션 도메인이 예외를 처리할 때까지 이벤트 처리기를 추가한 각 애플리케이션 도메인에서 알림이 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="5f58c-106">The notification occurs in each application domain that has added a handler for the event, until an application domain handles the exception.</span></span>

 <span data-ttu-id="5f58c-107">이 문서의 절차 및 예제에서는 애플리케이션 도메인 하나가 있는 간단한 프로그램과 직접 만든 애플리케이션 도메인에서 첫째 예외 알림을 받는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="5f58c-107">The procedures and examples in this article show how to receive first-chance exception notifications in a simple program that has one application domain, and in an application domain that you create.</span></span>

 <span data-ttu-id="5f58c-108">여러 애플리케이션 도메인에 걸쳐 있는 좀 더 복잡한 예제의 경우 <xref:System.AppDomain.FirstChanceException> 이벤트에 대한 예제를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="5f58c-108">For a more complex example that spans several application domains, see the example for the <xref:System.AppDomain.FirstChanceException> event.</span></span>

## <a name="receiving-first-chance-exception-notifications-in-the-default-application-domain"></a><span data-ttu-id="5f58c-109">기본 애플리케이션 도메인에서 첫째 예외 알림 받기</span><span class="sxs-lookup"><span data-stu-id="5f58c-109">Receiving First-Chance Exception Notifications in the Default Application Domain</span></span>
 <span data-ttu-id="5f58c-110">다음 절차에서는 애플리케이션에 대한 진입점인 `Main()` 메서드는 기본 애플리케이션 도메인에서 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="5f58c-110">In the following procedure, the entry point for the application, the `Main()` method, runs in the default application domain.</span></span>

#### <a name="to-demonstrate-first-chance-exception-notifications-in-the-default-application-domain"></a><span data-ttu-id="5f58c-111">기본 애플리케이션 도메인에서 첫째 예외 알림을 보여 주려면</span><span class="sxs-lookup"><span data-stu-id="5f58c-111">To demonstrate first-chance exception notifications in the default application domain</span></span>

1. <span data-ttu-id="5f58c-112">람다 함수를 사용하여 <xref:System.AppDomain.FirstChanceException> 이벤트에 대한 이벤트 처리기를 정의하고 이벤트에 연결합니다.</span><span class="sxs-lookup"><span data-stu-id="5f58c-112">Define an event handler for the <xref:System.AppDomain.FirstChanceException> event, using a lambda function, and attach it to the event.</span></span> <span data-ttu-id="5f58c-113">이 예제에서 이벤트 처리기는 이벤트가 처리된 애플리케이션 도메인의 이름 및 해당 예외의 <xref:System.Exception.Message%2A> 속성을 출력합니다.</span><span class="sxs-lookup"><span data-stu-id="5f58c-113">In this example, the event handler prints the name of the application domain where the event was handled and the exception's <xref:System.Exception.Message%2A> property.</span></span>

     [!code-csharp[System.AppDomain.FirstChanceException_howto_simple#2](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.appdomain.firstchanceexception_howto_simple/cs/example.cs#2)]
     [!code-vb[System.AppDomain.FirstChanceException_howto_simple#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.appdomain.firstchanceexception_howto_simple/vb/example.vb#2)]

2. <span data-ttu-id="5f58c-114">예외를 throw 및 catch합니다.</span><span class="sxs-lookup"><span data-stu-id="5f58c-114">Throw an exception and catch it.</span></span> <span data-ttu-id="5f58c-115">런타임에서 예외 처리기를 찾기 전에 <xref:System.AppDomain.FirstChanceException> 이벤트가 발생하고 메시지를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="5f58c-115">Before the runtime locates the exception handler, the <xref:System.AppDomain.FirstChanceException> event is raised and displays a message.</span></span> <span data-ttu-id="5f58c-116">이 메시지 다음에는 예외 처리기에 의해 표시되는 메시지가 옵니다.</span><span class="sxs-lookup"><span data-stu-id="5f58c-116">This message is followed by the message that is displayed by the exception handler.</span></span>

     [!code-csharp[System.AppDomain.FirstChanceException_howto_simple#3](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.appdomain.firstchanceexception_howto_simple/cs/example.cs#3)]
     [!code-vb[System.AppDomain.FirstChanceException_howto_simple#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.appdomain.firstchanceexception_howto_simple/vb/example.vb#3)]

3. <span data-ttu-id="5f58c-117">예외를 throw하지만 catch하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="5f58c-117">Throw an exception, but do not catch it.</span></span> <span data-ttu-id="5f58c-118">런타임에서 예외 처리기를 찾기 전에 <xref:System.AppDomain.FirstChanceException> 이벤트가 발생하고 메시지를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="5f58c-118">Before the runtime looks for an exception handler, the <xref:System.AppDomain.FirstChanceException> event is raised and displays a message.</span></span> <span data-ttu-id="5f58c-119">예외 처리기가 없으므로 애플리케이션이 종료됩니다.</span><span class="sxs-lookup"><span data-stu-id="5f58c-119">There is no exception handler, so the application terminates.</span></span>

     [!code-csharp[System.AppDomain.FirstChanceException_howto_simple#4](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.appdomain.firstchanceexception_howto_simple/cs/example.cs#4)]
     [!code-vb[System.AppDomain.FirstChanceException_howto_simple#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.appdomain.firstchanceexception_howto_simple/vb/example.vb#4)]

     <span data-ttu-id="5f58c-120">이 절차의 처음 세 단계에 표시된 코드는 완전한 콘솔 애플리케이션을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="5f58c-120">The code that is shown in the first three steps of this procedure forms a complete console application.</span></span> <span data-ttu-id="5f58c-121">애플리케이션의 출력은 .exe 파일의 이름에 따라 달라집니다. 기본 애플리케이션 도메인의 이름이 .exe 파일의 이름 및 확장명으로 구성되기 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="5f58c-121">The output from the application varies, depending on the name of the .exe file, because the name of the default application domain consists of the name and extension of the .exe file.</span></span> <span data-ttu-id="5f58c-122">샘플 출력은 다음을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="5f58c-122">See the following for sample output.</span></span>

     [!code-csharp[System.AppDomain.FirstChanceException_howto_simple#5](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.appdomain.firstchanceexception_howto_simple/cs/example.cs#5)]
     [!code-vb[System.AppDomain.FirstChanceException_howto_simple#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.appdomain.firstchanceexception_howto_simple/vb/example.vb#5)]

## <a name="receiving-first-chance-exception-notifications-in-another-application-domain"></a><span data-ttu-id="5f58c-123">다른 애플리케이션 도메인에서 첫째 예외 알림 받기</span><span class="sxs-lookup"><span data-stu-id="5f58c-123">Receiving First-Chance Exception Notifications in Another Application Domain</span></span>
 <span data-ttu-id="5f58c-124">프로그램이 둘 이상의 애플리케이션 도메인을 포함하는 경우 알림을 받는 애플리케이션 도메인을 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5f58c-124">If your program contains more than one application domain, you can choose which application domains receive notifications.</span></span>

#### <a name="to-receive-first-chance-exception-notifications-in-an-application-domain-that-you-create"></a><span data-ttu-id="5f58c-125">직접 만든 애플리케이션 도메인에서 첫째 예외 알림을 받으려면</span><span class="sxs-lookup"><span data-stu-id="5f58c-125">To receive first-chance exception notifications in an application domain that you create</span></span>

1. <span data-ttu-id="5f58c-126"><xref:System.AppDomain.FirstChanceException> 이벤트에 대한 이벤트 처리기를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="5f58c-126">Define an event handler for the <xref:System.AppDomain.FirstChanceException> event.</span></span> <span data-ttu-id="5f58c-127">이 예제에서는 이벤트가 처리된 애플리케이션 도메인의 이름 및 해당 예외의 `static` 속성을 출력하는 `Shared` 메서드(Visual Basic에서는 <xref:System.Exception.Message%2A> 메서드)를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="5f58c-127">This example uses a `static` method (`Shared` method in Visual Basic) that prints the name of the application domain where the event was handled and the exception's <xref:System.Exception.Message%2A> property.</span></span>

     [!code-csharp[System.AppDomain.FirstChanceException_howto#3](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.appdomain.firstchanceexception_howto/cs/example.cs#3)]
     [!code-vb[System.AppDomain.FirstChanceException_howto#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.appdomain.firstchanceexception_howto/vb/example.vb#3)]

2. <span data-ttu-id="5f58c-128">애플리케이션 도메인을 만들고 해당 애플리케이션 도메인에 대한 <xref:System.AppDomain.FirstChanceException> 이벤트에 이벤트 처리기를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="5f58c-128">Create an application domain and add the event handler to the <xref:System.AppDomain.FirstChanceException> event for that application domain.</span></span> <span data-ttu-id="5f58c-129">이 예제에서 애플리케이션 도메인의 이름은 `AD1`입니다.</span><span class="sxs-lookup"><span data-stu-id="5f58c-129">In this example, the application domain is named `AD1`.</span></span>

     [!code-csharp[System.AppDomain.FirstChanceException_howto#2](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.appdomain.firstchanceexception_howto/cs/example.cs#2)]
     [!code-vb[System.AppDomain.FirstChanceException_howto#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.appdomain.firstchanceexception_howto/vb/example.vb#2)]

     <span data-ttu-id="5f58c-130">동일한 방식으로 기본 애플리케이션 도메인에서 이 이벤트를 처리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5f58c-130">You can handle this event in the default application domain in the same way.</span></span> <span data-ttu-id="5f58c-131">`Main()`의 `static`(Visual Basic에서는 `Shared`) <xref:System.AppDomain.CurrentDomain%2A?displayProperty=nameWithType> 속성을 사용하여 기본 애플리케이션 도메인에 대한 참조를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="5f58c-131">Use the `static` (`Shared` in Visual Basic) <xref:System.AppDomain.CurrentDomain%2A?displayProperty=nameWithType> property in `Main()` to get a reference to the default application domain.</span></span>

#### <a name="to-demonstrate-first-chance-exception-notifications-in-the-application-domain"></a><span data-ttu-id="5f58c-132">애플리케이션 도메인에서 첫째 예외 알림을 보여 주려면</span><span class="sxs-lookup"><span data-stu-id="5f58c-132">To demonstrate first-chance exception notifications in the application domain</span></span>

1. <span data-ttu-id="5f58c-133">이전 절차에서 만든 애플리케이션 도메인에 `Worker` 개체를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="5f58c-133">Create a `Worker` object in the application domain that you created in the previous procedure.</span></span> <span data-ttu-id="5f58c-134">이 문서의 끝에 있는 전체 예제와 같이 `Worker` 클래스는 public이어야 하고 <xref:System.MarshalByRefObject>에서 파생되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5f58c-134">The `Worker` class must be public, and must derive from <xref:System.MarshalByRefObject>, as shown in the complete example at the end of this article.</span></span>

     [!code-csharp[System.AppDomain.FirstChanceException_howto#4](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.appdomain.firstchanceexception_howto/cs/example.cs#4)]
     [!code-vb[System.AppDomain.FirstChanceException_howto#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.appdomain.firstchanceexception_howto/vb/example.vb#4)]

2. <span data-ttu-id="5f58c-135">예외를 throw하는 `Worker` 개체의 메서드를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="5f58c-135">Call a method of the `Worker` object that throws an exception.</span></span> <span data-ttu-id="5f58c-136">이 예제에서는 `Thrower` 메서드가 두 번 호출됩니다.</span><span class="sxs-lookup"><span data-stu-id="5f58c-136">In this example, the `Thrower` method is called twice.</span></span> <span data-ttu-id="5f58c-137">첫 번째 호출에서는 메서드 인수가 `true`이므로 메서드가 자체 예외를 catch합니다.</span><span class="sxs-lookup"><span data-stu-id="5f58c-137">The first time, the method argument is `true`, which causes the method to catch its own exception.</span></span> <span data-ttu-id="5f58c-138">두 번째 호출에서는 인수가 `false`이며, `Main()` 메서드가 기본 애플리케이션 도메인에서 예외를 catch합니다.</span><span class="sxs-lookup"><span data-stu-id="5f58c-138">The second time, the argument is `false`, and the `Main()` method catches the exception in the default application domain.</span></span>

     [!code-csharp[System.AppDomain.FirstChanceException_howto#6](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.appdomain.firstchanceexception_howto/cs/example.cs#6)]
     [!code-vb[System.AppDomain.FirstChanceException_howto#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.appdomain.firstchanceexception_howto/vb/example.vb#6)]

3. <span data-ttu-id="5f58c-139">`Thrower` 메서드에 코드를 배치하여 메서드가 자체 예외를 처리하는지 여부를 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="5f58c-139">Place code in the `Thrower` method to control whether the method handles its own exception.</span></span>

     [!code-csharp[System.AppDomain.FirstChanceException_howto#5](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.appdomain.firstchanceexception_howto/cs/example.cs#5)]
     [!code-vb[System.AppDomain.FirstChanceException_howto#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.appdomain.firstchanceexception_howto/vb/example.vb#5)]

## <a name="example"></a><span data-ttu-id="5f58c-140">예제</span><span class="sxs-lookup"><span data-stu-id="5f58c-140">Example</span></span>
 <span data-ttu-id="5f58c-141">다음 예제에서는 `AD1`이라는 애플리케이션 도메인을 만들고 애플리케이션 도메인의 <xref:System.AppDomain.FirstChanceException> 이벤트에 이벤트 처리기를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="5f58c-141">The following example creates an application domain named `AD1` and adds an event handler to the application domain's <xref:System.AppDomain.FirstChanceException> event.</span></span> <span data-ttu-id="5f58c-142">예제에서는 애플리케이션 도메인에서 `Worker` 클래스 인스턴스를 만들고 <xref:System.ArgumentException>을 throw하는 `Thrower` 메서드를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="5f58c-142">The example creates an instance of the `Worker` class in the application domain, and calls a method named `Thrower` that throws an <xref:System.ArgumentException>.</span></span> <span data-ttu-id="5f58c-143">인수 값에 따라 메서드가 예외를 catch하거나 예외를 처리하지 못합니다.</span><span class="sxs-lookup"><span data-stu-id="5f58c-143">Depending on the value of its argument, the method either catches the exception or fails to handle it.</span></span>

 <span data-ttu-id="5f58c-144">`Thrower` 메서드가 `AD1`에서 예외를 throw할 때마다 `AD1`에서 <xref:System.AppDomain.FirstChanceException> 이벤트가 발생하고 이벤트 처리기가 메시지를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="5f58c-144">Each time the `Thrower` method throws an exception in `AD1`, the <xref:System.AppDomain.FirstChanceException> event is raised in `AD1`, and the event handler displays a message.</span></span> <span data-ttu-id="5f58c-145">그러면 런타임이 예외 처리기를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="5f58c-145">The runtime then looks for an exception handler.</span></span> <span data-ttu-id="5f58c-146">첫 번째 경우에는 예외 처리기가 `AD1`에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5f58c-146">In the first case, the exception handler is found in `AD1`.</span></span> <span data-ttu-id="5f58c-147">두 번째 경우에는 예외가 `AD1`에서 처리되지 않고 기본 애플리케이션 도메인에서 catch됩니다.</span><span class="sxs-lookup"><span data-stu-id="5f58c-147">In the second case, the exception is unhandled in `AD1`, and instead is caught in the default application domain.</span></span>

> [!NOTE]
> <span data-ttu-id="5f58c-148">기본 애플리케이션 도메인의 이름은 실행 파일의 이름과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="5f58c-148">The name of the default application domain is the same as the name of the executable.</span></span>

 <span data-ttu-id="5f58c-149">기본 애플리케이션 도메인에 <xref:System.AppDomain.FirstChanceException> 이벤트 처리기를 추가하면 기본 애플리케이션 도메인이 예외를 처리하기 전에 이벤트가 발생하고 처리됩니다.</span><span class="sxs-lookup"><span data-stu-id="5f58c-149">If you add a handler for the <xref:System.AppDomain.FirstChanceException> event to the default application domain, the event is raised and handled before the default application domain handles the exception.</span></span> <span data-ttu-id="5f58c-150">이를 확인하려면 `Main()`의 시작 부분에 C# 코드 `AppDomain.CurrentDomain.FirstChanceException += FirstChanceException;`(Visual Basic에서는 `AddHandler AppDomain.CurrentDomain.FirstChanceException, FirstChanceException`)을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="5f58c-150">To see this, add the C# code `AppDomain.CurrentDomain.FirstChanceException += FirstChanceException;` (in Visual Basic, `AddHandler AppDomain.CurrentDomain.FirstChanceException, FirstChanceException`) at the beginning of `Main()`.</span></span>

 [!code-csharp[System.AppDomain.FirstChanceException_howto#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.appdomain.firstchanceexception_howto/cs/example.cs#1)]
 [!code-vb[System.AppDomain.FirstChanceException_howto#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.appdomain.firstchanceexception_howto/vb/example.vb#1)]

## <a name="see-also"></a><span data-ttu-id="5f58c-151">참조</span><span class="sxs-lookup"><span data-stu-id="5f58c-151">See also</span></span>

- <xref:System.AppDomain.FirstChanceException>
