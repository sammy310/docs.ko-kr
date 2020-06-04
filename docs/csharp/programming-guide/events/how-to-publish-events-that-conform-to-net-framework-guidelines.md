---
title: .NET Framework 지침을 따르는 이벤트를 게시하는 방법 - C# 프로그래밍 가이드
ms.date: 05/26/2020
helpviewer_keywords:
- events [C#], implementation guidelines
ms.assetid: 9310ae16-8627-44a2-b08c-05e5976202b1
ms.openlocfilehash: 137e52b80703491a4528a3eddc7fa12f9dce6f52
ms.sourcegitcommit: ee5b798427f81237a3c23d1fd81fff7fdc21e8d3
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/28/2020
ms.locfileid: "84144801"
---
# <a name="how-to-publish-events-that-conform-to-net-framework-guidelines-c-programming-guide"></a><span data-ttu-id="5c45c-102">.NET Framework 지침을 따르는 이벤트를 게시하는 방법(C# 프로그래밍 가이드)</span><span class="sxs-lookup"><span data-stu-id="5c45c-102">How to publish events that conform to .NET Framework Guidelines (C# Programming Guide)</span></span>

<span data-ttu-id="5c45c-103">다음 절차에서는 표준 .NET Framework 패턴을 따르는 이벤트를 클래스와 구조체에 추가하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="5c45c-103">The following procedure demonstrates how to add events that follow the standard .NET Framework pattern to your classes and structs.</span></span> <span data-ttu-id="5c45c-104">.NET Framework 클래스 라이브러리의 모든 이벤트는 다음과 같이 정의된 <xref:System.EventHandler> 대리자를 기반으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="5c45c-104">All events in the .NET Framework class library are based on the <xref:System.EventHandler> delegate, which is defined as follows:</span></span>

```csharp
public delegate void EventHandler(object sender, EventArgs e);
```

> [!NOTE]
> <span data-ttu-id="5c45c-105">.NET Framework 2.0에서는 이 대리자의 제네릭 버전인 <xref:System.EventHandler%601>가 도입되었습니다.</span><span class="sxs-lookup"><span data-stu-id="5c45c-105">The .NET Framework 2.0 introduces a generic version of this delegate, <xref:System.EventHandler%601>.</span></span> <span data-ttu-id="5c45c-106">다음 예제에서는 두 버전을 사용하는 방법을 모두 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="5c45c-106">The following examples show how to use both versions.</span></span>

<span data-ttu-id="5c45c-107">정의하는 클래스의 이벤트는 값을 반환하는 대리자를 포함하여 유효한 모든 대리자 형식을 기반으로 할 수 있지만 다음 예제와 같이 <xref:System.EventHandler>를 사용하여 .NET Framework 패턴에 따라 이벤트를 만드는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="5c45c-107">Although events in classes that you define can be based on any valid delegate type, even delegates that return a value, it is generally recommended that you base your events on the .NET Framework pattern by using <xref:System.EventHandler>, as shown in the following example.</span></span>

<span data-ttu-id="5c45c-108">이름 `EventHandler`는 이벤트를 실제로 처리하지는 않으므로 약간의 혼동을 일으킬 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5c45c-108">The name `EventHandler` can lead to a bit of confusion as it doesn't actually handle the event.</span></span> <span data-ttu-id="5c45c-109"><xref:System.EventHandler> 및 제네릭 <xref:System.EventHandler%601>는 대리자 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="5c45c-109">The <xref:System.EventHandler>, and generic <xref:System.EventHandler%601> are delegate types.</span></span> <span data-ttu-id="5c45c-110">시그니처가 대리자 정의와 일치하는 메서드 또는 람다 식은 이벤트 처리기이며, 이벤트가 발생할 때 호출됩니다.</span><span class="sxs-lookup"><span data-stu-id="5c45c-110">A method or lambda expression whose signature matches the delegate definition is the *event handler* and will be invoked when the event is raised.</span></span>

### <a name="to-publish-events-based-on-the-eventhandler-pattern"></a><span data-ttu-id="5c45c-111">EventHandler 패턴에 따라 이벤트를 게시하려면</span><span class="sxs-lookup"><span data-stu-id="5c45c-111">To publish events based on the EventHandler pattern</span></span>

1. <span data-ttu-id="5c45c-112">이벤트와 함께 사용자 지정 데이터를 보낼 필요가 없는 경우 이 단계를 건너뛰고 3a 단계로 이동합니다. 게시자 및 구독자 클래스 둘 다에 표시되는 범위에서 사용자 지정 데이터에 대한 클래스를 선언합니다.</span><span class="sxs-lookup"><span data-stu-id="5c45c-112">(Skip this step and go to Step 3a if you do not have to send custom data with your event.) Declare the class for your custom data at a scope that is visible to both your publisher and subscriber classes.</span></span> <span data-ttu-id="5c45c-113">그런 다음 사용자 지정 이벤트 데이터를 저장하는 데 필요한 멤버를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="5c45c-113">Then add the required members to hold your custom event data.</span></span> <span data-ttu-id="5c45c-114">이 예제에서는 간단한 문자열이 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="5c45c-114">In this example, a simple string is returned.</span></span>

    ```csharp
    public class CustomEventArgs : EventArgs
    {
        public CustomEventArgs(string message)
        {
            Message = message;
        }

        public string Message { get; set; }
    }
    ```

2. <span data-ttu-id="5c45c-115"><xref:System.EventHandler%601>의 제네릭 버전을 사용하는 경우 이 단계를 건너뜁니다. 게시 클래스에서 대리자를 선언합니다.</span><span class="sxs-lookup"><span data-stu-id="5c45c-115">(Skip this step if you are using the generic version of <xref:System.EventHandler%601>.) Declare a delegate in your publishing class.</span></span> <span data-ttu-id="5c45c-116">`EventHandler`로 끝나는 이름을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="5c45c-116">Give it a name that ends with `EventHandler`.</span></span> <span data-ttu-id="5c45c-117">두 번째 매개 변수는 사용자 지정 `EventArgs` 형식을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="5c45c-117">The second parameter specifies your custom `EventArgs` type.</span></span>

    ```csharp
    public delegate void CustomEventHandler(object sender, CustomEventArgs args);
    ```

3. <span data-ttu-id="5c45c-118">다음 단계 중 하나를 사용하여 게시 클래스에서 이벤트를 선언합니다.</span><span class="sxs-lookup"><span data-stu-id="5c45c-118">Declare the event in your publishing class by using one of the following steps.</span></span>

    1. <span data-ttu-id="5c45c-119">사용자 지정 EventArgs 클래스가 없는 경우 이벤트 유형은 제네릭이 아닌 EventHandler 대리자가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5c45c-119">If you have no custom EventArgs class, your Event type will be the non-generic EventHandler delegate.</span></span> <span data-ttu-id="5c45c-120">C# 프로젝트를 만들 때 포함된 <xref:System> 네임스페이스에서 이미 선언되었기 때문에 대리자를 선언할 필요는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="5c45c-120">You do not have to declare the delegate because it is already declared in the <xref:System> namespace that is included when you create your C# project.</span></span> <span data-ttu-id="5c45c-121">게시자 클래스에 다음 코드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="5c45c-121">Add the following code to your publisher class.</span></span>

        ```csharp
        public event EventHandler RaiseCustomEvent;
        ```

    2. <span data-ttu-id="5c45c-122">제네릭이 아닌 버전의 <xref:System.EventHandler>를 사용 중이고 <xref:System.EventArgs>에서 파생된 사용자 지정 클래스가 있는 경우 게시 클래스 내에서 이벤트를 선언하고 2단계의 대리자를 형식으로 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="5c45c-122">If you are using the non-generic version of <xref:System.EventHandler> and you have a custom class derived from <xref:System.EventArgs>, declare your event inside your publishing class and use your delegate from step 2 as the type.</span></span>

        ```csharp
        public event CustomEventHandler RaiseCustomEvent;
        ```

    3. <span data-ttu-id="5c45c-123">제네릭 버전을 사용하는 경우에는 사용자 지정 대리자가 필요하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="5c45c-123">If you are using the generic version, you do not need a custom delegate.</span></span> <span data-ttu-id="5c45c-124">대신, 게시 클래스에서 이벤트 유형을 `EventHandler<CustomEventArgs>`로 지정하고 고유한 클래스 이름을 꺾쇠 괄호로 묶어 대체합니다.</span><span class="sxs-lookup"><span data-stu-id="5c45c-124">Instead, in your publishing class, you specify your event type as `EventHandler<CustomEventArgs>`, substituting the name of your own class between the angle brackets.</span></span>

        ```csharp
        public event EventHandler<CustomEventArgs> RaiseCustomEvent;
        ```

## <a name="example"></a><span data-ttu-id="5c45c-125">예제</span><span class="sxs-lookup"><span data-stu-id="5c45c-125">Example</span></span>

<span data-ttu-id="5c45c-126">다음 예제에서는 사용자 지정 EventArgs 클래스와 <xref:System.EventHandler%601>를 이벤트 유형으로 사용하여 이전 단계를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="5c45c-126">The following example demonstrates the previous steps by using a custom EventArgs class and <xref:System.EventHandler%601> as the event type.</span></span>

[!code-csharp[csProgGuideEvents#2](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideEvents/CS/Events.cs#2)]

## <a name="see-also"></a><span data-ttu-id="5c45c-127">참조</span><span class="sxs-lookup"><span data-stu-id="5c45c-127">See also</span></span>

- <xref:System.Delegate>
- [<span data-ttu-id="5c45c-128">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="5c45c-128">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="5c45c-129">이벤트</span><span class="sxs-lookup"><span data-stu-id="5c45c-129">Events</span></span>](index.md)
- [<span data-ttu-id="5c45c-130">대리자</span><span class="sxs-lookup"><span data-stu-id="5c45c-130">Delegates</span></span>](../delegates/index.md)
