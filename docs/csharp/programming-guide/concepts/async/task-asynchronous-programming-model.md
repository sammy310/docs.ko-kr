---
title: async 및 await를 사용한 TAP(작업 비동기 프로그래밍) 모델(C#)
ms.date: 05/22/2017
ms.assetid: 9bcf896a-5826-4189-8c1a-3e35fa08243a
ms.openlocfilehash: 2fde365acfab3342082e2ca286decc00ca73a19d
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59295967"
---
# <a name="task-asynchronous-programming-model"></a><span data-ttu-id="150dc-102">작업 비동기 프로그래밍 모델</span><span class="sxs-lookup"><span data-stu-id="150dc-102">Task asynchronous programming model</span></span>
<span data-ttu-id="150dc-103">비동기 프로그래밍을 사용하여 성능 병목 현상을 방지하고 애플리케이션의 전체적인 응답성을 향상할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="150dc-103">You can avoid performance bottlenecks and enhance the overall responsiveness of your application by using asynchronous programming.</span></span> <span data-ttu-id="150dc-104">그러나 비동기 애플리케이션을 쓰는 일반적인 기술이 복잡하여 해당 애플리케이션을 쓰고, 디버깅하고, 유지 관리하기 어려울 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="150dc-104">However, traditional techniques for writing asynchronous applications can be complicated, making them difficult to write, debug, and maintain.</span></span>  
  
<span data-ttu-id="150dc-105">[C# 5](../../../whats-new/csharp-version-history.md#c-version-50)에는 .NET Framework 4.5 이상, .NET Core 및 Windows 런타임의 비동기 지원을 활용하는 간단한 비동기 프로그래밍 접근 방법이 도입되었습니다.</span><span class="sxs-lookup"><span data-stu-id="150dc-105">[C# 5](../../../whats-new/csharp-version-history.md#c-version-50) introduced a simplified approach, async programming, that leverages asynchronous support in the .NET Framework 4.5 and higher, .NET Core, and the Windows Runtime.</span></span> <span data-ttu-id="150dc-106">컴파일러는 개발자가 하던 어려운 작업을 수행하고, 애플리케이션은 동기 코드와 비슷한 논리 구조를 유지합니다.</span><span class="sxs-lookup"><span data-stu-id="150dc-106">The compiler does the difficult work that the developer used to do, and your application retains a logical structure that resembles synchronous code.</span></span> <span data-ttu-id="150dc-107">따라서 약간의 노력만으로도 비동기 프로그래밍의 모든 장점을 누릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="150dc-107">As a result, you get all the advantages of asynchronous programming with a fraction of the effort.</span></span>  
  
<span data-ttu-id="150dc-108">이 항목에서는 비동기 프로그래밍을 사용하는 시기 및 방법에 대한 개요를 제공하고 특정 세부 정보 및 예제가 포함된 지원 항목에 대한 링크가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="150dc-108">This topic provides an overview of when and how to use async programming and includes links to support topics that contain details and examples.</span></span>  
  
## <a name="BKMK_WhentoUseAsynchrony"></a> <span data-ttu-id="150dc-109">반응성을 향상시키는 비동기</span><span class="sxs-lookup"><span data-stu-id="150dc-109">Async improves responsiveness</span></span>  
 <span data-ttu-id="150dc-110">비동기는 웹 액세스와 같이 차단 가능성이 있는 작업에 반드시 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="150dc-110">Asynchrony is essential for activities that are potentially blocking, such as web access.</span></span> <span data-ttu-id="150dc-111">웹 리소스에 대한 액세스 속도가 느리거나 지연됩니다.</span><span class="sxs-lookup"><span data-stu-id="150dc-111">Access to a web resource sometimes is slow or delayed.</span></span> <span data-ttu-id="150dc-112">동기 프로세스 안에서 이러한 활동이 차단되면 전체 애플리케이션이 기다려야 합니다.</span><span class="sxs-lookup"><span data-stu-id="150dc-112">If such an activity is blocked in a synchronous process, the entire application must wait.</span></span> <span data-ttu-id="150dc-113">비동기 프로세스에서 애플리케이션은 잠재적인 차단 작업이 완료될 때까지 웹 리소스에 의존하지 않는 다른 작업을 계속 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="150dc-113">In an asynchronous process, the application can continue with other work that doesn't depend on the web resource until the potentially blocking task finishes.</span></span>  
  
 <span data-ttu-id="150dc-114">다음 표에는 비동기 프로그래밍으로 응답성이 향상되는 일반적인 영역이 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="150dc-114">The following table shows typical areas where asynchronous programming improves responsiveness.</span></span> <span data-ttu-id="150dc-115">.NET 및 Windows 런타임에서 나열된 API에는 비동기 프로그래밍을 지원하는 메서드가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="150dc-115">The listed APIs from .NET and the Windows Runtime contain methods that support async programming.</span></span>  
  
| <span data-ttu-id="150dc-116">애플리케이션 영역</span><span class="sxs-lookup"><span data-stu-id="150dc-116">Application area</span></span>    | <span data-ttu-id="150dc-117">비동기 메서드가 있는 .NET 형식</span><span class="sxs-lookup"><span data-stu-id="150dc-117">.NET types with async methods</span></span>     | <span data-ttu-id="150dc-118">비동기 메서드가 있는 Windows 런타임 형식</span><span class="sxs-lookup"><span data-stu-id="150dc-118">Windows Runtime types with async methods</span></span>  |
|---------------------|-----------------------------------|-------------------------------------------|
|<span data-ttu-id="150dc-119">웹 액세스</span><span class="sxs-lookup"><span data-stu-id="150dc-119">Web access</span></span>|<xref:System.Net.Http.HttpClient>|<xref:Windows.Web.Syndication.SyndicationClient>|
|<span data-ttu-id="150dc-120">파일 작업</span><span class="sxs-lookup"><span data-stu-id="150dc-120">Working with files</span></span>|<span data-ttu-id="150dc-121"><xref:System.IO.StreamWriter>, <xref:System.IO.StreamReader>, <xref:System.Xml.XmlReader></span><span class="sxs-lookup"><span data-stu-id="150dc-121"><xref:System.IO.StreamWriter>, <xref:System.IO.StreamReader>, <xref:System.Xml.XmlReader></span></span>|<xref:Windows.Storage.StorageFile>|  
|<span data-ttu-id="150dc-122">이미지 작업</span><span class="sxs-lookup"><span data-stu-id="150dc-122">Working with images</span></span>||<span data-ttu-id="150dc-123"><xref:Windows.Media.Capture.MediaCapture>, <xref:Windows.Graphics.Imaging.BitmapEncoder>, <xref:Windows.Graphics.Imaging.BitmapDecoder></span><span class="sxs-lookup"><span data-stu-id="150dc-123"><xref:Windows.Media.Capture.MediaCapture>, <xref:Windows.Graphics.Imaging.BitmapEncoder>, <xref:Windows.Graphics.Imaging.BitmapDecoder></span></span>|  
|<span data-ttu-id="150dc-124">WCF 프로그래밍</span><span class="sxs-lookup"><span data-stu-id="150dc-124">WCF programming</span></span>|[<span data-ttu-id="150dc-125">동기 및 비동기 작업</span><span class="sxs-lookup"><span data-stu-id="150dc-125">Synchronous and Asynchronous Operations</span></span>](../../../../framework/wcf/synchronous-and-asynchronous-operations.md)||  
  
<span data-ttu-id="150dc-126">모든 UI 관련 작업은 대체로 스레드 한 개를 공유하기 때문에 비동기화는 UI 스레드에 액세스하는 애플리케이션에게 특히 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="150dc-126">Asynchrony proves especially valuable for applications that access the UI thread because all UI-related activity usually shares one thread.</span></span> <span data-ttu-id="150dc-127">동기 애플리케이션에서 임의의 프로세스가 차단되면 모든 프로세스가 차단됩니다.</span><span class="sxs-lookup"><span data-stu-id="150dc-127">If any process is blocked in a synchronous application, all are blocked.</span></span> <span data-ttu-id="150dc-128">만약 애플리케이션이 응답하지 않으면 응답을 기다리는 대신에 애플리케이션이 실패했다고 결론을 내리게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="150dc-128">Your application stops responding, and you might conclude that it has failed when instead it's just waiting.</span></span>  
  
 <span data-ttu-id="150dc-129">비동기 메서드를 사용하면 애플리케이션이 UI에 계속 응답합니다.</span><span class="sxs-lookup"><span data-stu-id="150dc-129">When you use asynchronous methods, the application continues to respond to the UI.</span></span> <span data-ttu-id="150dc-130">예를 들어 창의 크기를 조정하거나 최소화할 수 있습니다. 또는 애플리케이션이 완료될 때까지 기다리지 않으려면 애플리케이션을 종료할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="150dc-130">You can resize or minimize a window, for example, or you can close the application if you don't want to wait for it to finish.</span></span>  
  
 <span data-ttu-id="150dc-131">비동기 기반 접근 방식을 사용하면 비동기 작업을 디자인할 때 선택할 수 있는 옵션 목록에 자동 전송과 동일한 기능을 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="150dc-131">The async-based approach adds the equivalent of an automatic transmission to the list of options that you can choose from when designing asynchronous operations.</span></span> <span data-ttu-id="150dc-132">즉, 더 적은 개발자의 노력으로 기존 비동기 프로그래밍의 이점을 모두 활용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="150dc-132">That is, you get all the benefits of traditional asynchronous programming but with much less effort from the developer.</span></span>  
  
## <a name="BKMK_HowtoWriteanAsyncMethod"></a> <span data-ttu-id="150dc-133">작성이 간편한 비동기 메서드</span><span class="sxs-lookup"><span data-stu-id="150dc-133">Async methods are easier to write</span></span>  
 <span data-ttu-id="150dc-134">C#의 [async](../../../../csharp/language-reference/keywords/async.md) 및 [await](../../../../csharp/language-reference/keywords/await.md) 키워드는 비동기 프로그래밍의 핵심입니다.</span><span class="sxs-lookup"><span data-stu-id="150dc-134">The [async](../../../../csharp/language-reference/keywords/async.md) and [await](../../../../csharp/language-reference/keywords/await.md) keywords in C# are the heart of async programming.</span></span> <span data-ttu-id="150dc-135">이 두 개의 키워드를 사용하면 .NET Framework, .NET Core 또는 Windows 런타임의 리소스를 사용하여 동기 메서드를 만드는 것만큼 쉽게 비동기 메서드를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="150dc-135">By using those two keywords, you can use resources in the .NET Framework, .NET Core, or the Windows Runtime to create an asynchronous method almost as easily as you create a synchronous method.</span></span> <span data-ttu-id="150dc-136">`async` 키워드를 사용하여 정의하는 비동기 메서드를 *비동기 메서드*라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="150dc-136">Asynchronous methods that you define by using the `async` keyword are referred to as *async methods*.</span></span>  
  
 <span data-ttu-id="150dc-137">다음 예제에서는 비동기 메서드를 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="150dc-137">The following example shows an async method.</span></span> <span data-ttu-id="150dc-138">코드의 거의 모든 내용이 익숙할 것입니다.</span><span class="sxs-lookup"><span data-stu-id="150dc-138">Almost everything in the code should look completely familiar to you.</span></span> 
  
 <span data-ttu-id="150dc-139">이 항목의 마지막에 완전한 WPF(Windows Presentation Foundation) 예제 파일이 있으며, [비동기 샘플: "Async 및 Await를 사용하는 비동기 프로그래밍"의 예제](https://code.msdn.microsoft.com/Async-Sample-Example-from-9b9f505c)에서 샘플을 다운로드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="150dc-139">You can find a complete Windows Presentation Foundation (WPF) example file at the end of this topic, and you can download the sample from [Async Sample: Example from "Asynchronous Programming with Async and Await"](https://code.msdn.microsoft.com/Async-Sample-Example-from-9b9f505c).</span></span>  
  
```csharp  
async Task<int> AccessTheWebAsync()  
{   
    // You need to add a reference to System.Net.Http to declare client.  
    using (HttpClient client = new HttpClient())  
    {  
        Task<string> getStringTask = client.GetStringAsync("https://docs.microsoft.com");  
  
        DoIndependentWork();  
  
        string urlContents = await getStringTask;  
  
        return urlContents.Length;  
    }  
}  
```  

 <span data-ttu-id="150dc-140">위의 샘플에서 몇 가지 사례를 알아볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="150dc-140">You can learn several practices from the preceding sample.</span></span> <span data-ttu-id="150dc-141">메서드 서명을 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="150dc-141">start with the method signature.</span></span> <span data-ttu-id="150dc-142">여기에는 `async` 한정자가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="150dc-142">It includes the `async` modifier.</span></span> <span data-ttu-id="150dc-143">반환 형식은 `Task<int>`입니다(추가 옵션은 "반환 형식" 섹션 참조).</span><span class="sxs-lookup"><span data-stu-id="150dc-143">The return type is `Task<int>` (See "Return Types" section for more options).</span></span> <span data-ttu-id="150dc-144">메서드 이름은 `Async`로 끝납니다.</span><span class="sxs-lookup"><span data-stu-id="150dc-144">The method name ends in `Async`.</span></span> <span data-ttu-id="150dc-145">메서드의 본문에서 `GetStringAsync`가 `Task<string>`을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="150dc-145">In the body of the method, `GetStringAsync` returns a `Task<string>`.</span></span> <span data-ttu-id="150dc-146">즉, 작업을 `await`하는 경우 `string`을 받게 됩니다(`urlContents`).</span><span class="sxs-lookup"><span data-stu-id="150dc-146">That means that when you `await` the task you'll get a `string` (`urlContents`).</span></span>  <span data-ttu-id="150dc-147">작업을 대기하기 전에 `GetStringAsync`의 `string`을 사용하지 않는 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="150dc-147">Before awaiting the task, you can do work that doesn't rely on the `string` from `GetStringAsync`.</span></span>  

 <span data-ttu-id="150dc-148">`await` 연산자에 주의하세요.</span><span class="sxs-lookup"><span data-stu-id="150dc-148">Pay close attention to the `await` operator.</span></span> <span data-ttu-id="150dc-149">`AccessTheWebAsync`를 일시 중단합니다.</span><span class="sxs-lookup"><span data-stu-id="150dc-149">It suspends `AccessTheWebAsync`;</span></span>
 
- <span data-ttu-id="150dc-150">`AccessTheWebAsync`는 `getStringTask`가 완료될 때까지 계속할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="150dc-150">`AccessTheWebAsync` can't continue until `getStringTask` is complete.</span></span>  
- <span data-ttu-id="150dc-151">반면 제어는 `AccessTheWebAsync`의 호출자에 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="150dc-151">Meanwhile, control returns to the caller of `AccessTheWebAsync`.</span></span>  
- <span data-ttu-id="150dc-152">`getStringTask`가 완료되면 컨트롤이 다시 시작됩니다.</span><span class="sxs-lookup"><span data-stu-id="150dc-152">Control resumes here when `getStringTask` is complete.</span></span>   
- <span data-ttu-id="150dc-153">그런 다음, `await` 연산자가 `getStringTask`에서 `string` 결과를 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="150dc-153">The `await` operator then retrieves the `string` result from `getStringTask`.</span></span>  

 <span data-ttu-id="150dc-154">반환 문은 정수 결과를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="150dc-154">The return statement specifies an integer result.</span></span> <span data-ttu-id="150dc-155">`AccessTheWebAsync`를 대기하는 메서드는 길이 값을 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="150dc-155">Any methods that are awaiting `AccessTheWebAsync` retrieve the length value.</span></span>  

 <span data-ttu-id="150dc-156">`AccessTheWebAsync`에 `GetStringAsync` 호출과 해당 완료 대기 사이에 수행할 수 있는 작업이 없는 경우 다음 단일 문을 호출하고 대기하여 코드를 단순화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="150dc-156">If `AccessTheWebAsync` doesn't have any work that it can do between calling `GetStringAsync` and awaiting its completion, you can simplify your code by calling and awaiting in the following single statement.</span></span>  
  
```csharp  
string urlContents = await client.GetStringAsync("https://docs.microsoft.com");  
```  
 
<span data-ttu-id="150dc-157">이전 예제가 비동기 메서드인 이유는 다음과 같은 특성 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="150dc-157">The following characteristics summarize what makes the previous example an async method.</span></span>  
  
-   <span data-ttu-id="150dc-158">메서드 시그니처에 `async` 한정자가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="150dc-158">The method signature includes an `async` modifier.</span></span>  
  
-   <span data-ttu-id="150dc-159">비동기 메서드의 이름은 규칙에 따라 "Async" 접미사로 끝납니다.</span><span class="sxs-lookup"><span data-stu-id="150dc-159">The name of an async method, by convention, ends with an "Async" suffix.</span></span>  
  
-   <span data-ttu-id="150dc-160">반환 형식은 다음 형식 중 하나입니다.</span><span class="sxs-lookup"><span data-stu-id="150dc-160">The return type is one of the following types:</span></span>  
  
    -   <span data-ttu-id="150dc-161">메서드에 연산자 형식이 `TResult`인 Return 문이 있는 경우 <xref:System.Threading.Tasks.Task%601>입니다.</span><span class="sxs-lookup"><span data-stu-id="150dc-161"><xref:System.Threading.Tasks.Task%601> if your method has a return statement in which the operand has type `TResult`.</span></span>  
  
    -   <span data-ttu-id="150dc-162">메서드에 반환 문이 포함되지 않았거나 피연산자가 없는 반환 문이 포함된 경우 <xref:System.Threading.Tasks.Task>입니다.</span><span class="sxs-lookup"><span data-stu-id="150dc-162"><xref:System.Threading.Tasks.Task> if your method has no return statement or has a return statement with no operand.</span></span>  
  
    -   <span data-ttu-id="150dc-163">비동기 이벤트 처리기를 작성하는 경우 `void`입니다.</span><span class="sxs-lookup"><span data-stu-id="150dc-163">`void` if you're writing an async event handler.</span></span>  

    -   <span data-ttu-id="150dc-164">`GetAwaiter` 메서드가 포함된 모든 기타 형식(C# 7.0부터).</span><span class="sxs-lookup"><span data-stu-id="150dc-164">Any other type that has a `GetAwaiter` method (starting with C# 7.0).</span></span>
  
     <span data-ttu-id="150dc-165">자세한 내용은 [반환 형식 및 매개 변수](#BKMK_ReturnTypesandParameters) 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="150dc-165">For more information, see the [Return Types and Parameters](#BKMK_ReturnTypesandParameters) section.</span></span>  
  
-   <span data-ttu-id="150dc-166">메서드는 일반적으로 비동기 작업이 완료될 때까지 메서드가 계속될 수 없는 지점을 표시하는 하나 이상의 `await` 표현을 포함하고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="150dc-166">The method usually includes at least one `await` expression, which marks a point where the method can't continue until the awaited asynchronous operation is complete.</span></span> <span data-ttu-id="150dc-167">한편, 메서드가 일시 중단되고 컨트롤이 메서드의 호출자로 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="150dc-167">In the meantime, the method is suspended, and control returns to the method's caller.</span></span> <span data-ttu-id="150dc-168">이 항목의 다음 단원은 일시 중단 지점에서 발생하는 상황을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="150dc-168">The next section of this topic illustrates what happens at the suspension point.</span></span>  
  
 <span data-ttu-id="150dc-169">비동기 메서드에서는 제공된 키워드 및 형식을 사용해서 수행하려는 작업을 나타내고, 컴파일러는 일시 중단된 메서드에서 컨트롤이 대기 지점으로 반환될 때 수행되어야 하는 항목을 추적하는 등의 나머지 작업을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="150dc-169">In async methods, you use the provided keywords and types to indicate what you want to do, and the compiler does the rest, including keeping track of what must happen when control returns to an await point in a suspended method.</span></span> <span data-ttu-id="150dc-170">루프 및 예외 처리와 같은 일부 루틴 프로세스는 기존의 비동기 코드에서 처리하기 어려울 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="150dc-170">Some routine processes, such as loops and exception handling, can be difficult to handle in traditional asynchronous code.</span></span> <span data-ttu-id="150dc-171">비동기 메서드에서는 동기 솔루션에서와 같이 필요한 만큼 이러한 요소를 작성하여 문제를 해결합니다.</span><span class="sxs-lookup"><span data-stu-id="150dc-171">In an async method, you write these elements much as you would in a synchronous solution, and the problem is solved.</span></span>  
  
 <span data-ttu-id="150dc-172">이전 버전의 .NET Framework의 비동기에 대한 자세한 내용은 [TPL 및 일반적인 .NET Framework 비동기 프로그래밍](../../../../standard/parallel-programming/tpl-and-traditional-async-programming.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="150dc-172">For more information about asynchrony in previous versions of the .NET Framework, see [TPL and Traditional .NET Framework Asynchronous Programming](../../../../standard/parallel-programming/tpl-and-traditional-async-programming.md).</span></span>  
  
## <a name="BKMK_WhatHappensUnderstandinganAsyncMethod"></a> <span data-ttu-id="150dc-173">비동기 메서드에서 수행되는 작업</span><span class="sxs-lookup"><span data-stu-id="150dc-173">What happens in an async method</span></span>  
 <span data-ttu-id="150dc-174">비동기 프로그래밍을 이해하는 데 있어 가장 중요한 점은 메서드에서 메서드로 제어 흐름을 이동하는 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="150dc-174">The most important thing to understand in asynchronous programming is how the control flow moves from method to method.</span></span> <span data-ttu-id="150dc-175">다음 다이어그램이 과정을 안내합니다.</span><span class="sxs-lookup"><span data-stu-id="150dc-175">The following diagram leads you through the process.</span></span>  
  
 <span data-ttu-id="150dc-176">![비동기 프로그램 추적](./media/task-asynchronous-programming-model/navigation-trace-async-program.png "NavigationTrace")</span><span class="sxs-lookup"><span data-stu-id="150dc-176">![Trace an async program](./media/task-asynchronous-programming-model/navigation-trace-async-program.png "NavigationTrace")</span></span>  
  
 <span data-ttu-id="150dc-177">다이어그램의 숫자는 다음 단계에 해당하고 사용자가 "시작" 단추를 클릭할 때 시작됩니다.</span><span class="sxs-lookup"><span data-stu-id="150dc-177">The numbers in the diagram correspond to the following steps, initiated when the user clicks the "start" button.</span></span>
  
1. <span data-ttu-id="150dc-178">이벤트 처리기가 호출되어 `AccessTheWebAsync` 비동기 메서드를 기다립니다.</span><span class="sxs-lookup"><span data-stu-id="150dc-178">An event handler calls and awaits the  `AccessTheWebAsync` async method.</span></span>  
  
2. <span data-ttu-id="150dc-179">`AccessTheWebAsync`는 <xref:System.Net.Http.HttpClient> 인스턴스를 만들고 <xref:System.Net.Http.HttpClient.GetStringAsync%2A> 비동기 메서드를 호출하여 웹 사이트의 내용을 문자열로 다운로드합니다.</span><span class="sxs-lookup"><span data-stu-id="150dc-179">`AccessTheWebAsync` creates an <xref:System.Net.Http.HttpClient> instance and calls the <xref:System.Net.Http.HttpClient.GetStringAsync%2A> asynchronous method to download the contents of a website as a string.</span></span>  
  
3. <span data-ttu-id="150dc-180">`GetStringAsync`에서 특정 작업이 발생하여 진행이 일시 중단됩니다.</span><span class="sxs-lookup"><span data-stu-id="150dc-180">Something happens in `GetStringAsync` that suspends its progress.</span></span> <span data-ttu-id="150dc-181">웹 사이트에서 다운로드 또는 다른 차단 작업을 수행할 때까지 기다려야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="150dc-181">Perhaps it must wait for a website to download or some other blocking activity.</span></span> <span data-ttu-id="150dc-182">리소스를 차단하지 않기 위해 `GetStringAsync`는 해당 호출자인 `AccessTheWebAsync`에 제어 권한을 양도합니다.</span><span class="sxs-lookup"><span data-stu-id="150dc-182">To avoid blocking resources, `GetStringAsync` yields control to its caller, `AccessTheWebAsync`.</span></span>  
  
     <span data-ttu-id="150dc-183">`GetStringAsync`는 `TResult`가 문자열인 <xref:System.Threading.Tasks.Task%601>를 반환하고, `AccessTheWebAsync`는 `getStringTask` 변수에 작업을 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="150dc-183">`GetStringAsync` returns a <xref:System.Threading.Tasks.Task%601>, where `TResult` is a string, and `AccessTheWebAsync` assigns the task to the `getStringTask` variable.</span></span> <span data-ttu-id="150dc-184">이 작업은 작업이 완료될 때 실제 문자열 값을 생성하기 위한 코드와 함께 `GetStringAsync`를 호출하는 지속적인 프로세스를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="150dc-184">The task represents the ongoing process for the call to `GetStringAsync`, with a commitment to produce an actual string value when the work is complete.</span></span>  
  
4. <span data-ttu-id="150dc-185">`getStringTask`가 아직 대기되지 않았으므로 `AccessTheWebAsync`가 `GetStringAsync`의 최종 결과에 무관한 다른 작업을 계속할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="150dc-185">Because `getStringTask` hasn't been awaited yet, `AccessTheWebAsync` can continue with other work that doesn't depend on the final result from `GetStringAsync`.</span></span> <span data-ttu-id="150dc-186">이 작업은 동기 메서드 `DoIndependentWork`를 호출하여 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="150dc-186">That work is represented by a call to the synchronous method `DoIndependentWork`.</span></span>  
  
5. <span data-ttu-id="150dc-187">`DoIndependentWork`는 작업을 수행하고 호출자에게 반환하는 동기 메서드입니다.</span><span class="sxs-lookup"><span data-stu-id="150dc-187">`DoIndependentWork` is a synchronous method that does its work and returns to its caller.</span></span>  
  
6. <span data-ttu-id="150dc-188">`AccessTheWebAsync`에 `getStringTask` 결과 없이 수행할 수 있는 작업이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="150dc-188">`AccessTheWebAsync` has run out of work that it can do without a result from `getStringTask`.</span></span> <span data-ttu-id="150dc-189">다음으로 `AccessTheWebAsync`는 다운로드한 문자열의 길이를 계산하여 반환하려 하지만, 메서드가 문자열을 확인할 때까지 해당 값을 계산할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="150dc-189">`AccessTheWebAsync` next wants to calculate and return the length of the downloaded string, but the method can't calculate that value until the method has the string.</span></span>  
  
     <span data-ttu-id="150dc-190">따라서 `AccessTheWebAsync`는 await 연산자를 사용해서 해당 프로세스를 일시 중단하고 `AccessTheWebAsync`를 호출한 메서드에 제어 권한을 양도합니다.</span><span class="sxs-lookup"><span data-stu-id="150dc-190">Therefore, `AccessTheWebAsync` uses an await operator to suspend its progress and to yield control to the method that called `AccessTheWebAsync`.</span></span> <span data-ttu-id="150dc-191">`AccessTheWebAsync`는 `Task<int>`를 호출자에게 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="150dc-191">`AccessTheWebAsync` returns a `Task<int>` to the caller.</span></span> <span data-ttu-id="150dc-192">작업은 다운로드한 문자열의 길이인 정수 결과를 만든다는 약속을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="150dc-192">The task represents a promise to produce an integer result that's the length of the downloaded string.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="150dc-193">`AccessTheWebAsync`가 대기하기 전에 `GetStringAsync`(및 `getStringTask`)가 완료되면 `AccessTheWebAsync`에서 컨트롤이 유지됩니다.</span><span class="sxs-lookup"><span data-stu-id="150dc-193">If `GetStringAsync` (and therefore `getStringTask`) completes before `AccessTheWebAsync` awaits it, control remains in `AccessTheWebAsync`.</span></span> <span data-ttu-id="150dc-194">일시 중단 및 `AccessTheWebAsync`의 반환 비용은 호출된 비동기 프로세스(`getStringTask`)가 이미 완료되었고 `AccessTheWebSync`가 최종 결과를 기다릴 필요가 없다면 낭비됩니다.</span><span class="sxs-lookup"><span data-stu-id="150dc-194">The expense of suspending and then returning to `AccessTheWebAsync` would be wasted if the called asynchronous process (`getStringTask`) has already completed and `AccessTheWebSync` doesn't have to wait for the final result.</span></span>  
  
     <span data-ttu-id="150dc-195">호출자(이 예제의 이벤트 처리기) 내에서 처리 패턴이 계속됩니다.</span><span class="sxs-lookup"><span data-stu-id="150dc-195">Inside the caller (the event handler in this example), the processing pattern continues.</span></span> <span data-ttu-id="150dc-196">호출자가 해당 결과를 기다리거나 즉시 기다리기 전에 `AccessTheWebAsync`에서 결과에 의존하지 않는 다른 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="150dc-196">The caller might do other work that doesn't depend on the result from `AccessTheWebAsync` before awaiting that result, or the caller might await immediately.</span></span>   <span data-ttu-id="150dc-197">`AccessTheWebAsync`에 대한 이벤트가 대기 중이며 `AccessTheWebAsync`가 `GetStringAsync`를 대기 중입니다.</span><span class="sxs-lookup"><span data-stu-id="150dc-197">The event handler is waiting for `AccessTheWebAsync`, and `AccessTheWebAsync` is waiting for `GetStringAsync`.</span></span>  
  
7. <span data-ttu-id="150dc-198">`GetStringAsync`가 완료되고 문자열 결과를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="150dc-198">`GetStringAsync` completes and produces a string result.</span></span> <span data-ttu-id="150dc-199">`GetStringAsync`를 호출할 경우 문자열 결과가 예상대로 반환되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="150dc-199">The string result isn't returned by the call to `GetStringAsync` in the way that you might expect.</span></span> <span data-ttu-id="150dc-200">(메서드가 이미 3단계에서 작업을 반환했습니다.) 대신 문자열 결과가 메서드 `getStringTask`의 완료를 나타내는 작업에 저장됩니다.</span><span class="sxs-lookup"><span data-stu-id="150dc-200">(Remember that the method already returned a task in step 3.) Instead, the string result is stored in the task that represents the completion of the method, `getStringTask`.</span></span> <span data-ttu-id="150dc-201">await 연산자가 `getStringTask`에서 결과를 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="150dc-201">The await operator retrieves the result from `getStringTask`.</span></span> <span data-ttu-id="150dc-202">할당 문은 검색된 결과를 `urlContents`에 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="150dc-202">The assignment statement assigns the retrieved result to `urlContents`.</span></span>  
  
8. <span data-ttu-id="150dc-203">`AccessTheWebAsync`에 문자열 결과가 있는 경우 메서드가 문자열 길이를 계산할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="150dc-203">When `AccessTheWebAsync` has the string result, the method can calculate the length of the string.</span></span> <span data-ttu-id="150dc-204">그런 다음 `AccessTheWebAsync` 작업도 완료되고 대기 이벤트 처리기를 다시 시작할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="150dc-204">Then the work of `AccessTheWebAsync` is also complete, and the waiting event handler can resume.</span></span> <span data-ttu-id="150dc-205">이 항목 뒷부분의 전체 예에서는 이벤트 처리기가 길이 결과 값을 검색하고 출력하는지 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="150dc-205">In the full example at the end of the topic, you can confirm that the event handler retrieves and prints the value of the length result.</span></span>    
<span data-ttu-id="150dc-206">비동기 프로그래밍을 처음 접하는 사용자인 경우 동기 동작과 비동기 동작의 차이점을 살펴보세요.</span><span class="sxs-lookup"><span data-stu-id="150dc-206">If you are new to asynchronous programming, take a minute to consider the difference between synchronous and asynchronous behavior.</span></span> <span data-ttu-id="150dc-207">비동기 메서드는 작업이 완료될 때 반환되지만(5단계) 비동기 메서드는 작업이 일시 중단될 때 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="150dc-207">A synchronous method returns when its work is complete (step 5), but an async method returns a task value when its work is suspended (steps 3 and 6).</span></span> <span data-ttu-id="150dc-208">비동기 메서드가 해당 작업을 완료하면 작업이 완료된 것으로 표시되고 결과가 있을 경우 작업에 저장됩니다.</span><span class="sxs-lookup"><span data-stu-id="150dc-208">When the async method eventually completes its work, the task is marked as completed and the result, if any, is stored in the task.</span></span>  
  
<span data-ttu-id="150dc-209">제어 흐름에 대한 자세한 내용은 [비동기 프로그램의 제어 흐름(C#)](../../../../csharp/programming-guide/concepts/async/control-flow-in-async-programs.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="150dc-209">For more information about control flow, see [Control Flow in Async Programs (C#)](../../../../csharp/programming-guide/concepts/async/control-flow-in-async-programs.md).</span></span>  
  
## <a name="BKMK_APIAsyncMethods"></a> <span data-ttu-id="150dc-210">API 비동기 메서드</span><span class="sxs-lookup"><span data-stu-id="150dc-210">API async methods</span></span>  
 <span data-ttu-id="150dc-211">`GetStringAsync`와 같이 비동기 프로그래밍을 지원하는 메서드를 어디에서 검색해야 할지 궁금했을 것입니다.</span><span class="sxs-lookup"><span data-stu-id="150dc-211">You might be wondering where to find methods such as `GetStringAsync` that support async programming.</span></span> <span data-ttu-id="150dc-212">.NET Framework 4.5 이상 및 .NET Core에는 `async` 및 `await`에 작동하는 많은 멤버가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="150dc-212">The  .NET Framework 4.5 or higher and .NET Core contain many members that work with `async` and `await`.</span></span> <span data-ttu-id="150dc-213">멤버 이름에 붙는 "Async" 접미사와 <xref:System.Threading.Tasks.Task> 또는 <xref:System.Threading.Tasks.Task%601>의 반환 형식으로 멤버를 인식할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="150dc-213">You can recognize them by the "Async" suffix that’s appended to the member name, and by their return type of <xref:System.Threading.Tasks.Task> or <xref:System.Threading.Tasks.Task%601>.</span></span> <span data-ttu-id="150dc-214">예를 들어, `System.IO.Stream` 클래스는 동기 메서드인 <xref:System.IO.Stream.CopyTo%2A>, <xref:System.IO.Stream.Read%2A> 및 <xref:System.IO.Stream.Write%2A>와 함께 <xref:System.IO.Stream.CopyToAsync%2A>, <xref:System.IO.Stream.ReadAsync%2A> 및 <xref:System.IO.Stream.WriteAsync%2A>와 같은 메서드를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="150dc-214">For example, the `System.IO.Stream` class contains methods such as <xref:System.IO.Stream.CopyToAsync%2A>, <xref:System.IO.Stream.ReadAsync%2A>, and <xref:System.IO.Stream.WriteAsync%2A> alongside the synchronous methods <xref:System.IO.Stream.CopyTo%2A>, <xref:System.IO.Stream.Read%2A>, and <xref:System.IO.Stream.Write%2A>.</span></span>  
  
 <span data-ttu-id="150dc-215">Windows 런타임에는 Windows 앱에서 `async` 및 `await`와 함께 사용할 수 있는 많은 메서드도 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="150dc-215">The Windows Runtime also contains many methods that you can use with `async` and `await` in Windows apps.</span></span> <span data-ttu-id="150dc-216">자세한 내용은 UWP 개발의 경우 [스레딩 및 비동기 프로그래밍](/windows/uwp/threading-async/)을 참조하세요. Windows 런타임 이전 버전을 사용하는 경우 [비동기 프로그래밍(Windows 스토어 앱)](https://docs.microsoft.com/previous-versions/windows/apps/hh464924(v=win.10)) 및 [빠른 시작: C# 또는 Visual Basic에서 비동기 API 호출](https://docs.microsoft.com/previous-versions/windows/apps/hh452713(v=win.10))을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="150dc-216">For more information, see [Threading and async programming](/windows/uwp/threading-async/) for UWP development, and [Asynchronous programming (Windows Store apps)](https://docs.microsoft.com/previous-versions/windows/apps/hh464924(v=win.10)) and [Quickstart: Calling asynchronous APIs in C# or Visual Basic](https://docs.microsoft.com/previous-versions/windows/apps/hh452713(v=win.10)) if you use earlier versions of the Windows Runtime.</span></span>  
  
## <a name="BKMK_Threads"></a> <span data-ttu-id="150dc-217">스레드</span><span class="sxs-lookup"><span data-stu-id="150dc-217">Threads</span></span>  
<span data-ttu-id="150dc-218">비동기 메서드는 비차단 작업으로 의도되었습니다.</span><span class="sxs-lookup"><span data-stu-id="150dc-218">Async methods are intended to be non-blocking operations.</span></span> <span data-ttu-id="150dc-219">비동기 메서드의 `await` 식은 대기한 작업이 실행되는 동안 현재 스레드를 차단하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="150dc-219">An `await` expression in an async method doesn’t block the current thread while the awaited task is running.</span></span> <span data-ttu-id="150dc-220">대신에 이 식은 메서드의 나머지를 연속으로 등록하고 제어 기능을 비동기 메서드 호출자에게 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="150dc-220">Instead, the expression signs up the rest of the method as a continuation and returns control to the caller of the async method.</span></span>  
  
<span data-ttu-id="150dc-221">`async` 및 `await` 키워드로 인해 추가 스레드가 생성되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="150dc-221">The `async` and `await` keywords don't cause additional threads to be created.</span></span> <span data-ttu-id="150dc-222">비동기 메서드는 자체 스레드에서 실행되지 않으므로 다중 스레드가 필요하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="150dc-222">Async methods don't require multithreading because an async method doesn't run on its own thread.</span></span> <span data-ttu-id="150dc-223">메서드는 현재 동기화 컨텍스트에서 실행되고 메서드가 활성화된 경우에만 스레드에서 시간을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="150dc-223">The method runs on the current synchronization context and uses time on the thread only when the method is active.</span></span> <span data-ttu-id="150dc-224"><xref:System.Threading.Tasks.Task.Run%2A?displayProperty=nameWithType>을 사용하여 CPU 바인딩 작업을 백그라운드 스레드로 이동할 수 있지만 백그라운드 스레드는 결과를 사용할 수 있을 때까지 기다리는 프로세스를 도와주지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="150dc-224">You can use <xref:System.Threading.Tasks.Task.Run%2A?displayProperty=nameWithType> to move CPU-bound work to a background thread, but a background thread doesn't help with a process that's just waiting for results to become available.</span></span>  
  
<span data-ttu-id="150dc-225">비동기 프로그래밍에 대한 비동기 기반 접근 방법은 거의 모든 경우에 기존 방법보다 선호됩니다.</span><span class="sxs-lookup"><span data-stu-id="150dc-225">The async-based approach to asynchronous programming is preferable to existing approaches in almost every case.</span></span> <span data-ttu-id="150dc-226">특히, 이 접근 방식은 코드가 더 간단하고 경합 조건을 방지할 필요가 없기 때문에 I/O 바인딩 작업의 <xref:System.ComponentModel.BackgroundWorker> 클래스보다 효과적입니다.</span><span class="sxs-lookup"><span data-stu-id="150dc-226">In particular, this approach is better than the <xref:System.ComponentModel.BackgroundWorker> class for I/O-bound operations because the code is simpler and you don't have to guard against race conditions.</span></span> <span data-ttu-id="150dc-227">비동기 프로그래밍은 코드 실행에 대한 조합 세부 정보를 `Task.Run`가 스레드 풀로 변환하는 작업과 구분하기 때문에 <xref:System.Threading.Tasks.Task.Run%2A?displayProperty=nameWithType> 메서드를 함께 사용하는 비동기 프로그래밍은 CPU 바인딩 작업을 위한 <xref:System.ComponentModel.BackgroundWorker>보다 효과가 뛰어납니다.</span><span class="sxs-lookup"><span data-stu-id="150dc-227">In combination with the <xref:System.Threading.Tasks.Task.Run%2A?displayProperty=nameWithType> method, async programming is better than <xref:System.ComponentModel.BackgroundWorker> for CPU-bound operations because async programming separates the coordination details of running your code from the work that `Task.Run` transfers to the threadpool.</span></span>  
  
## <a name="BKMK_AsyncandAwait"></a> <span data-ttu-id="150dc-228">async 및 await</span><span class="sxs-lookup"><span data-stu-id="150dc-228">async and await</span></span>  
 <span data-ttu-id="150dc-229">[async](../../../../csharp/language-reference/keywords/async.md) 한정자를 사용해서 메서드를 비동기 메서드로 지정하면 다음 두 기능이 활성화됩니다.</span><span class="sxs-lookup"><span data-stu-id="150dc-229">If you specify that a method is an async method by using the [async](../../../../csharp/language-reference/keywords/async.md) modifier, you enable the following two capabilities.</span></span>  
  
-   <span data-ttu-id="150dc-230">표시된 비동기 메서드는 [Await](../../../../csharp/language-reference/keywords/await.md)를 사용하여 일시 중단 지점을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="150dc-230">The marked async method can use [await](../../../../csharp/language-reference/keywords/await.md) to designate suspension points.</span></span> <span data-ttu-id="150dc-231">`await` 연산자는 대기된 비동기 프로세스가 완료될 때까지 비동기 메서드가 해당 지점을 지나 계속할 수 없도록 컴파일러에 지시합니다.</span><span class="sxs-lookup"><span data-stu-id="150dc-231">The `await` operator tells the compiler that the async method can't continue past that point until the awaited asynchronous process is complete.</span></span> <span data-ttu-id="150dc-232">한편, 컨트롤이 비동기 메서드의 호출자로 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="150dc-232">In the meantime, control returns to the caller of the async method.</span></span>  
  
     <span data-ttu-id="150dc-233">`await` 식에서 비동기 메서드를 일시 중단하더라도 메서드가 종료되지는 않으며 `finally` 블록이 실행되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="150dc-233">The suspension of an async method at an `await` expression doesn't constitute an exit from the method, and `finally` blocks don’t run.</span></span>  
  
-   <span data-ttu-id="150dc-234">표시된 비동기 메서드는 이 메서드를 호출한 다른 메서드에 의해 대기할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="150dc-234">The marked async method can itself be awaited by methods that call it.</span></span>  
  
<span data-ttu-id="150dc-235">비동기 메서드는 일반적으로 `await` 연산자를 하나 이상 가지고 있지만, `await` 식이 없는 경우 컴파일러 오류가 발생하지는 않습니다.</span><span class="sxs-lookup"><span data-stu-id="150dc-235">An async method typically contains one or more occurrences of an `await` operator, but the absence of `await` expressions doesn’t cause a compiler error.</span></span> <span data-ttu-id="150dc-236">비동기 메서드에서 `await` 연산자를 사용하여 일시 중단 시점을 표시하지 않는 경우 메서드가 `async` 한정자에 상관없이 동기 메서드가 실행되는 방식으로 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="150dc-236">If an async method doesn’t use an `await` operator to mark a suspension point, the method executes as a synchronous method does, despite the `async` modifier.</span></span> <span data-ttu-id="150dc-237">컴파일러는 해당 메서드에 대해 경고를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="150dc-237">The compiler issues a warning for such methods.</span></span>  
  
 <span data-ttu-id="150dc-238">`async` 및 `await`은 상황별 키워드입니다.</span><span class="sxs-lookup"><span data-stu-id="150dc-238">`async` and `await` are contextual keywords.</span></span> <span data-ttu-id="150dc-239">자세한 내용과 예제는 다음 항목을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="150dc-239">For more information and examples, see the following topics:</span></span>  
  
-   [<span data-ttu-id="150dc-240">async</span><span class="sxs-lookup"><span data-stu-id="150dc-240">async</span></span>](../../../../csharp/language-reference/keywords/async.md)  
  
-   [<span data-ttu-id="150dc-241">await</span><span class="sxs-lookup"><span data-stu-id="150dc-241">await</span></span>](../../../../csharp/language-reference/keywords/await.md)  
  
## <a name="BKMK_ReturnTypesandParameters"></a> <span data-ttu-id="150dc-242">반환 형식 및 매개 변수</span><span class="sxs-lookup"><span data-stu-id="150dc-242">Return types and parameters</span></span>  
<span data-ttu-id="150dc-243">비동기 메서드는 일반적으로 <xref:System.Threading.Tasks.Task> 또는 <xref:System.Threading.Tasks.Task%601>를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="150dc-243">An async method typically returns a <xref:System.Threading.Tasks.Task> or a <xref:System.Threading.Tasks.Task%601>.</span></span> <span data-ttu-id="150dc-244">비동기 메서드 내에서 `await` 연산자는 호출에서 다른 비동기 메서드로 전환되는 작업에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="150dc-244">Inside an async method, an `await` operator is applied to a task that's returned from a call to another async method.</span></span>  
  
<span data-ttu-id="150dc-245">메서드에 `TResult` 형식의 피연산자를 지정하는 [`return`](../../../../csharp/language-reference/keywords/return.md) 문이 포함되어 있을 경우 <xref:System.Threading.Tasks.Task%601>를 반환 형식으로 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="150dc-245">You specify <xref:System.Threading.Tasks.Task%601> as the return type if the method contains a [`return`](../../../../csharp/language-reference/keywords/return.md) statement that specifies an operand of type `TResult`.</span></span> 
  
<span data-ttu-id="150dc-246">메서드에 return 문이 없거나 피연산자를 반환하지 않는 return 문이 있을 경우 반환 형식으로 <xref:System.Threading.Tasks.Task>를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="150dc-246">You use <xref:System.Threading.Tasks.Task>  as the return type if the method has no return statement or has a return statement that doesn't return an operand.</span></span>  

<span data-ttu-id="150dc-247">C# 7.0부터는 형식에 `GetAwaiter` 메서드가 포함된 경우 다른 반환 형식을 지정할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="150dc-247">Starting with C# 7.0, you can also specify any other return type, provided that the type includes a `GetAwaiter` method.</span></span> <span data-ttu-id="150dc-248"><xref:System.Threading.Tasks.ValueTask%601>가 이러한 형식의 예입니다.</span><span class="sxs-lookup"><span data-stu-id="150dc-248"><xref:System.Threading.Tasks.ValueTask%601> is an example of such a type.</span></span> <span data-ttu-id="150dc-249">[System.Threading.Tasks.Extension](https://www.nuget.org/packages/System.Threading.Tasks.Extensions/) NuGet 패키지에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="150dc-249">It is available in the [System.Threading.Tasks.Extension](https://www.nuget.org/packages/System.Threading.Tasks.Extensions/) NuGet package.</span></span>
  
 <span data-ttu-id="150dc-250">다음 예제는 <xref:System.Threading.Tasks.Task%601> 또는 <xref:System.Threading.Tasks.Task>를 반환하는 메서드를 선언하고 호출하는 방법을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="150dc-250">The following example shows how you declare and call a method that returns a <xref:System.Threading.Tasks.Task%601> or a <xref:System.Threading.Tasks.Task>.</span></span>  
  
```csharp  
// Signature specifies Task<TResult>  
async Task<int> GetTaskOfTResultAsync()  
{  
    int hours = 0;  
    await Task.Delay(0);  
    // Return statement specifies an integer result.  
    return hours;  
}  
  
// Calls to GetTaskOfTResultAsync  
Task<int> returnedTaskTResult = GetTaskOfTResultAsync();  
int intResult = await returnedTaskTResult;  
// or, in a single statement  
int intResult = await GetTaskOfTResultAsync();  
  
// Signature specifies Task  
async Task GetTaskAsync()  
{  
    await Task.Delay(0);  
    // The method has no return statement.    
}  
  
// Calls to GetTaskAsync  
Task returnedTask = GetTaskAsync();  
await returnedTask;  
// or, in a single statement  
await GetTaskAsync();  
```  
  
<span data-ttu-id="150dc-251">반환된 각 작업은 진행 중인 작업을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="150dc-251">Each returned task represents ongoing work.</span></span> <span data-ttu-id="150dc-252">작업은 비동기 프로세스 상태에 대한 정보를 캡슐화하며, 결과적으로 프로세스의 최종 결과 또는 성공하지 못한 경우 프로세스가 발생시키는 예외에 대한 정보를 캡슐화합니다.</span><span class="sxs-lookup"><span data-stu-id="150dc-252">A task encapsulates information about the state of the asynchronous process and, eventually, either the final result from the process or the exception that the process raises if it doesn't succeed.</span></span>  
  
<span data-ttu-id="150dc-253">비동기 메서드의 반환 형식은 `void`일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="150dc-253">An async method can also have a `void` return type.</span></span> <span data-ttu-id="150dc-254">이 반환 형식은 기본적으로 `void` 반환 형식이 필요할 때 이벤트 처리기를 정의하는 데 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="150dc-254">This return type is used primarily to define event handlers, where a `void` return type is required.</span></span> <span data-ttu-id="150dc-255">비동기 이벤트 처리기는 비동기 프로그램의 시작점 역할을 하는 경우가 많습니다.</span><span class="sxs-lookup"><span data-stu-id="150dc-255">Async event handlers often serve as the starting point for async programs.</span></span>  
  
<span data-ttu-id="150dc-256">`void` 반환 형식을 가진 비동기 메서드는 대기할 수 없습니다. 또한 void를 반환하는 메서드의 호출자는 메서드가 throw하는 예외를 catch할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="150dc-256">An async method that has a `void` return type can’t be awaited, and the caller of a void-returning method can't catch any exceptions that the method throws.</span></span>  
  
<span data-ttu-id="150dc-257">비동기 메서드는 모든 [in](../../../../csharp/language-reference/keywords/in-parameter-modifier.md), [ref](../../../../csharp/language-reference/keywords/ref.md) 또는 [out](../../../../csharp/language-reference/keywords/out-parameter-modifier.md) 매개 변수를 선언할 수 없지만, 이러한 매개 변수가 있는 메서드를 호출할 수는 있습니다.</span><span class="sxs-lookup"><span data-stu-id="150dc-257">An async method can't declare [in](../../../../csharp/language-reference/keywords/in-parameter-modifier.md), [ref](../../../../csharp/language-reference/keywords/ref.md) or [out](../../../../csharp/language-reference/keywords/out-parameter-modifier.md) parameters, but the method can call methods that have such parameters.</span></span> <span data-ttu-id="150dc-258">마찬가지로 비동기 메서드는 참조 반환 값을 사용하여 메서드를 호출할 수 있지만 참조를 통해 값을 반환할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="150dc-258">Similarly, an async method can't return a value by reference, although it can call methods with ref return values.</span></span> 
  
<span data-ttu-id="150dc-259">자세한 내용과 예제는 [비동기 반환 형식(C#)](../../../../csharp/programming-guide/concepts/async/async-return-types.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="150dc-259">For more information and examples, see [Async Return Types (C#)](../../../../csharp/programming-guide/concepts/async/async-return-types.md).</span></span> <span data-ttu-id="150dc-260">비동기 메서드에서 예외를 처리하는 방법에 대한 자세한 내용은 [try-catch](../../../../csharp/language-reference/keywords/try-catch.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="150dc-260">For more information about how to catch exceptions in async methods, see [try-catch](../../../../csharp/language-reference/keywords/try-catch.md).</span></span> 
  
<span data-ttu-id="150dc-261">Windows 런타임 프로그래밍의 비동기 API에는 작업과 유사한 다음 반환 형식 중 하나가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="150dc-261">Asynchronous APIs in Windows Runtime programming have one of the following return types, which are similar to tasks:</span></span>  
  
-   <span data-ttu-id="150dc-262"><xref:System.Threading.Tasks.Task%601>에 해당하는 <xref:Windows.Foundation.IAsyncOperation%601></span><span class="sxs-lookup"><span data-stu-id="150dc-262"><xref:Windows.Foundation.IAsyncOperation%601>, which corresponds to <xref:System.Threading.Tasks.Task%601></span></span>  
  
-   <span data-ttu-id="150dc-263"><xref:System.Threading.Tasks.Task>에 해당하는 <xref:Windows.Foundation.IAsyncAction></span><span class="sxs-lookup"><span data-stu-id="150dc-263"><xref:Windows.Foundation.IAsyncAction>, which corresponds to <xref:System.Threading.Tasks.Task></span></span>  
  
-   <xref:Windows.Foundation.IAsyncActionWithProgress%601>  
  
-   <xref:Windows.Foundation.IAsyncOperationWithProgress%602>  

## <a name="BKMK_NamingConvention"></a> <span data-ttu-id="150dc-264">명명 규칙</span><span class="sxs-lookup"><span data-stu-id="150dc-264">Naming convention</span></span>  
<span data-ttu-id="150dc-265">규칙에 따라 일반적으로 대기 가능한 형식(예: `Task`, `Task<T>`, `ValueTask`, `ValueTask<T>`)을 반환하는 메서드에는 "Async"로 끝나는 이름을 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="150dc-265">By convention, methods that return commonly awaitable types (e.g. `Task`, `Task<T>`, `ValueTask`, `ValueTask<T>`) should have names that end with "Async".</span></span> <span data-ttu-id="150dc-266">비동기 작업을 시작하지만 대기 가능한 형식을 반환하지 않는 메서드는 "Async"로 끝나는 이름을 사용하지 않아야 하지만, "Begin", "Start" 또는 일부 다른 동사로 시작하여 이 메서드가 작업 결과를 반환하거나 throw하지 않도록 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="150dc-266">Methods that start an asynchronous operation but do not return an awaitable type should not have names that end with "Async", but may start with "Begin", "Start", or some other verb to suggest this method does not return or throw the result of the operation.</span></span>
  
 <span data-ttu-id="150dc-267">여기서 이벤트, 기본 클래스 또는 인터페이스 계약으로 다른 이름을 제안하는 규칙을 무시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="150dc-267">You can ignore the convention where an event, base class, or interface contract suggests a different name.</span></span> <span data-ttu-id="150dc-268">예를 들어, `Button1_Click`과 같은 공용 이벤트 처리기의 이름을 변경할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="150dc-268">For example, you shouldn’t rename common event handlers, such as `Button1_Click`.</span></span>  
  
## <a name="BKMK_RelatedTopics"></a> <span data-ttu-id="150dc-269">관련 항목 및 샘플(Visual Studio)</span><span class="sxs-lookup"><span data-stu-id="150dc-269">Related topics and samples (Visual Studio)</span></span>  
  
|<span data-ttu-id="150dc-270">제목</span><span class="sxs-lookup"><span data-stu-id="150dc-270">Title</span></span>|<span data-ttu-id="150dc-271">설명</span><span class="sxs-lookup"><span data-stu-id="150dc-271">Description</span></span>|<span data-ttu-id="150dc-272">샘플</span><span class="sxs-lookup"><span data-stu-id="150dc-272">Sample</span></span>|  
|-----------|-----------------|------------|  
|[<span data-ttu-id="150dc-273">연습: async 및 await를 사용하여 웹에 액세스(C#)</span><span class="sxs-lookup"><span data-stu-id="150dc-273">Walkthrough: Accessing the Web by Using async and await (C#)</span></span>](../../../../csharp/programming-guide/concepts/async/walkthrough-accessing-the-web-by-using-async-and-await.md)|<span data-ttu-id="150dc-274">동기 WPF 솔루션을 비동기 WPF 솔루션으로 변환하는 방법을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="150dc-274">Shows how to convert a synchronous WPF solution to an asynchronous WPF solution.</span></span> <span data-ttu-id="150dc-275">이 애플리케이션은 일련의 웹 사이트를 다운로드합니다.</span><span class="sxs-lookup"><span data-stu-id="150dc-275">The application downloads a series of websites.</span></span>|[<span data-ttu-id="150dc-276">비동기 샘플: 웹 연습에 액세스</span><span class="sxs-lookup"><span data-stu-id="150dc-276">Async Sample: Accessing the Web Walkthrough</span></span>](https://code.msdn.microsoft.com/Async-Sample-Accessing-the-9c10497f)|  
|[<span data-ttu-id="150dc-277">방법: Task.WhenAll을 사용하여 비동기 연습 확장(C#)</span><span class="sxs-lookup"><span data-stu-id="150dc-277">How to: Extend the async Walkthrough by Using Task.WhenAll (C#)</span></span>](../../../../csharp/programming-guide/concepts/async/how-to-extend-the-async-walkthrough-by-using-task-whenall.md)|<span data-ttu-id="150dc-278">이전 연습에 <xref:System.Threading.Tasks.Task.WhenAll%2A?displayProperty=nameWithType>을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="150dc-278">Adds <xref:System.Threading.Tasks.Task.WhenAll%2A?displayProperty=nameWithType> to the previous walkthrough.</span></span> <span data-ttu-id="150dc-279">`WhenAll`을 사용하면 모든 다운로드가 동시에 시작됩니다.</span><span class="sxs-lookup"><span data-stu-id="150dc-279">The use of `WhenAll` starts all the downloads at the same time.</span></span>||  
|[<span data-ttu-id="150dc-280">방법: async 및 await를 사용하여 병렬로 여러 웹 요청 만들기(C#)</span><span class="sxs-lookup"><span data-stu-id="150dc-280">How to: Make Multiple Web Requests in Parallel by Using async and await (C#)</span></span>](../../../../csharp/programming-guide/concepts/async/how-to-make-multiple-web-requests-in-parallel-by-using-async-and-await.md)|<span data-ttu-id="150dc-281">동시에 여러 작업을 시작하는 방법을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="150dc-281">Demonstrates how to start several tasks at the same time.</span></span>|[<span data-ttu-id="150dc-282">비동기 샘플: 병렬로 여러 웹 요청 만들기</span><span class="sxs-lookup"><span data-stu-id="150dc-282">Async Sample: Make Multiple Web Requests in Parallel</span></span>](https://code.msdn.microsoft.com/Async-Make-Multiple-Web-49adb82e)|  
|[<span data-ttu-id="150dc-283">비동기 반환 형식(C#)</span><span class="sxs-lookup"><span data-stu-id="150dc-283">Async Return Types (C#)</span></span>](../../../../csharp/programming-guide/concepts/async/async-return-types.md)|<span data-ttu-id="150dc-284">비동기 메서드에서 반환할 수 있는 형식을 설명하고 각 형식이 언제 적절한가를 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="150dc-284">Illustrates the types that async methods can return and explains when each type is appropriate.</span></span>||  
|[<span data-ttu-id="150dc-285">비동기 프로그램의 제어 흐름(C#)</span><span class="sxs-lookup"><span data-stu-id="150dc-285">Control Flow in Async Programs (C#)</span></span>](../../../../csharp/programming-guide/concepts/async/control-flow-in-async-programs.md)|<span data-ttu-id="150dc-286">비동기 프로그램에서 연속적 await 표현을 통한 컨트롤의 흐름을 자세히 추적합니다.</span><span class="sxs-lookup"><span data-stu-id="150dc-286">Traces in detail the flow of control through a succession of await expressions in an asynchronous program.</span></span>|[<span data-ttu-id="150dc-287">비동기 샘플: 비동기 프로그램의 제어 흐름</span><span class="sxs-lookup"><span data-stu-id="150dc-287">Async Sample: Control Flow in Async Programs</span></span>](https://code.msdn.microsoft.com/Async-Sample-Control-Flow-5c804fc0)|  
|[<span data-ttu-id="150dc-288">Async 애플리케이션 미세 조정(C#)</span><span class="sxs-lookup"><span data-stu-id="150dc-288">Fine-Tuning Your Async Application (C#)</span></span>](../../../../csharp/programming-guide/concepts/async/fine-tuning-your-async-application.md)|<span data-ttu-id="150dc-289">비동기 솔루션에 다음과 같은 기능을 추가하는 방법을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="150dc-289">Shows how to add the following functionality to your async solution:</span></span><br /><br /> <span data-ttu-id="150dc-290">-   [비동기 작업 또는 작업 목록 취소(C#)](../../../../csharp/programming-guide/concepts/async/cancel-an-async-task-or-a-list-of-tasks.md)</span><span class="sxs-lookup"><span data-stu-id="150dc-290">-   [Cancel an Async Task or a List of Tasks (C#)](../../../../csharp/programming-guide/concepts/async/cancel-an-async-task-or-a-list-of-tasks.md)</span></span><br /><span data-ttu-id="150dc-291">-   [일정 기간 이후 비동기 작업 취소(C#)](../../../../csharp/programming-guide/concepts/async/cancel-async-tasks-after-a-period-of-time.md)</span><span class="sxs-lookup"><span data-stu-id="150dc-291">-   [Cancel Async Tasks after a Period of Time (C#)](../../../../csharp/programming-guide/concepts/async/cancel-async-tasks-after-a-period-of-time.md)</span></span><br /><span data-ttu-id="150dc-292">-   [비동기 작업 하나가 완료되면 남은 비동기 작업 취소(C#)](../../../../csharp/programming-guide/concepts/async/cancel-remaining-async-tasks-after-one-is-complete.md)</span><span class="sxs-lookup"><span data-stu-id="150dc-292">-   [Cancel Remaining Async Tasks after One Is Complete (C#)](../../../../csharp/programming-guide/concepts/async/cancel-remaining-async-tasks-after-one-is-complete.md)</span></span><br /><span data-ttu-id="150dc-293">-   [비동기 작업을 여러 개 시작하고 완료될 때마다 처리(C#)](../../../../csharp/programming-guide/concepts/async/start-multiple-async-tasks-and-process-them-as-they-complete.md)</span><span class="sxs-lookup"><span data-stu-id="150dc-293">-   [Start Multiple Async Tasks and Process Them As They Complete (C#)](../../../../csharp/programming-guide/concepts/async/start-multiple-async-tasks-and-process-them-as-they-complete.md)</span></span>|[<span data-ttu-id="150dc-294">비동기 샘플: 애플리케이션 미세 조정</span><span class="sxs-lookup"><span data-stu-id="150dc-294">Async Sample: Fine Tuning Your Application</span></span>](https://code.msdn.microsoft.com/Async-Fine-Tuning-Your-a676abea)|  
|[<span data-ttu-id="150dc-295">비동기 앱에서 재진입 처리(C#)</span><span class="sxs-lookup"><span data-stu-id="150dc-295">Handling Reentrancy in Async Apps (C#)</span></span>](../../../../csharp/programming-guide/concepts/async/handling-reentrancy-in-async-apps.md)|<span data-ttu-id="150dc-296">비동기 작업이 실행되는 동안 현재 비동기 작업을 다시 시작하는 경우 처리 방법을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="150dc-296">Shows how to handle cases in which an active asynchronous operation is restarted while it’s running.</span></span>||  
|<span data-ttu-id="150dc-297">[WhenAny: .NET Framework와 Windows 런타임 간 브리징](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/jj635140(v=vs.120))</span><span class="sxs-lookup"><span data-stu-id="150dc-297">[WhenAny: Bridging between the .NET Framework and the Windows Runtime](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/jj635140(v=vs.120))</span></span>|<span data-ttu-id="150dc-298">[!INCLUDE[wrt](~/includes/wrt-md.md)] 메서드에 <xref:System.Threading.Tasks.Task.WhenAny%2A>를 사용할 수 있도록 .NET Framework의 작업 형식과 [!INCLUDE[wrt](~/includes/wrt-md.md)]의 IAsyncOperations 사이의 연결 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="150dc-298">Shows how to bridge between Task types in the .NET Framework and IAsyncOperations in the [!INCLUDE[wrt](~/includes/wrt-md.md)] so that you can use <xref:System.Threading.Tasks.Task.WhenAny%2A> with a [!INCLUDE[wrt](~/includes/wrt-md.md)] method.</span></span>|[<span data-ttu-id="150dc-299">비동기 샘플: .NET 및 Windows 런타임 간 연결(AsTask 및 WhenAny)</span><span class="sxs-lookup"><span data-stu-id="150dc-299">Async Sample: Bridging between .NET and Windows Runtime (AsTask and WhenAny)</span></span>](https://code.msdn.microsoft.com/Async-Sample-Bridging-d6a2f739)|  
|<span data-ttu-id="150dc-300">비동기 취소: .NET Framework와 Windows 런타임 간 브리징</span><span class="sxs-lookup"><span data-stu-id="150dc-300">Async Cancellation: Bridging between the .NET Framework and the Windows Runtime</span></span>|<span data-ttu-id="150dc-301">[!INCLUDE[wrt](~/includes/wrt-md.md)] 메서드에 <xref:System.Threading.CancellationTokenSource>를 사용할 수 있도록 .NET Framework의 작업 형식과 [!INCLUDE[wrt](~/includes/wrt-md.md)]의 IAsyncOperations 사이의 연결 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="150dc-301">Shows how to bridge between Task types in the .NET Framework and IAsyncOperations in the [!INCLUDE[wrt](~/includes/wrt-md.md)] so that you can use <xref:System.Threading.CancellationTokenSource> with a [!INCLUDE[wrt](~/includes/wrt-md.md)] method.</span></span>|[<span data-ttu-id="150dc-302">비동기 샘플: .NET 및 Windows 런타임 간 연결(AsTask & 취소)</span><span class="sxs-lookup"><span data-stu-id="150dc-302">Async Sample: Bridging between .NET and Windows Runtime (AsTask & Cancellation)</span></span>](https://code.msdn.microsoft.com/Async-Sample-Bridging-9479eca3)|  
|[<span data-ttu-id="150dc-303">파일 액세스에 Async 사용(C#)</span><span class="sxs-lookup"><span data-stu-id="150dc-303">Using Async for File Access (C#)</span></span>](../../../../csharp/programming-guide/concepts/async/using-async-for-file-access.md)|<span data-ttu-id="150dc-304">async 및 await를 사용하여 파일에 액세스하는 이점을 나열하고 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="150dc-304">Lists and demonstrates the benefits of using async and await to access files.</span></span>||  
|[<span data-ttu-id="150dc-305">TAP(작업 기반 비동기 패턴)</span><span class="sxs-lookup"><span data-stu-id="150dc-305">Task-based Asynchronous Pattern (TAP)</span></span>](../../../../standard/asynchronous-programming-patterns/task-based-asynchronous-pattern-tap.md)|<span data-ttu-id="150dc-306">.NET Framework의 새로운 비동기 패턴에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="150dc-306">Describes a new pattern for asynchrony in the .NET Framework.</span></span> <span data-ttu-id="150dc-307">패턴은 <xref:System.Threading.Tasks.Task> 및 <xref:System.Threading.Tasks.Task%601> 형식을 기반으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="150dc-307">The pattern is based on the <xref:System.Threading.Tasks.Task> and <xref:System.Threading.Tasks.Task%601> types.</span></span>||  
|[<span data-ttu-id="150dc-308">비동기 Channel 9 비디오</span><span class="sxs-lookup"><span data-stu-id="150dc-308">Async Videos on Channel 9</span></span>](https://channel9.msdn.com/search?term=async%20&type=All#pubDate=year&ch9Search&lang-en=en)|<span data-ttu-id="150dc-309">비동기 프로그래밍에 대한 다양한 비디오로 연결되는 링크를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="150dc-309">Provides links to a variety of videos about async programming.</span></span>||  
  
## <a name="BKMK_CompleteExample"></a> <span data-ttu-id="150dc-310">전체 예제</span><span class="sxs-lookup"><span data-stu-id="150dc-310">Complete example</span></span>  
 <span data-ttu-id="150dc-311">다음 코드는 이 항목에서 설명하는 WPF(Windows Presentation Foundation) 애플리케이션의 MainWindow.xaml.cs 파일입니다.</span><span class="sxs-lookup"><span data-stu-id="150dc-311">The following code is the MainWindow.xaml.cs file from the Windows Presentation Foundation (WPF) application that this topic discusses.</span></span> <span data-ttu-id="150dc-312">[비동기 샘플: "Async 및 Await를 사용하는 비동기 프로그래밍"의 예제](https://code.msdn.microsoft.com/Async-Sample-Example-from-9b9f505c)에서 샘플을 다운로드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="150dc-312">You can download the sample from [Async Sample: Example from "Asynchronous Programming with Async and Await"](https://code.msdn.microsoft.com/Async-Sample-Example-from-9b9f505c).</span></span>  
  
```csharp  
using System;  
using System.Collections.Generic;  
using System.Linq;  
using System.Text;  
using System.Threading.Tasks;  
using System.Windows;  
using System.Windows.Controls;  
using System.Windows.Data;  
using System.Windows.Documents;  
using System.Windows.Input;  
using System.Windows.Media;  
using System.Windows.Media.Imaging;  
using System.Windows.Navigation;  
using System.Windows.Shapes;  
  
// Add a using directive and a reference for System.Net.Http;  
using System.Net.Http;  
  
namespace AsyncFirstExample  
{  
    public partial class MainWindow : Window  
    {  
        // Mark the event handler with async so you can use await in it.  
        private async void StartButton_Click(object sender, RoutedEventArgs e)  
        {  
            // Call and await separately.  
            //Task<int> getLengthTask = AccessTheWebAsync();  
            //// You can do independent work here.  
            //int contentLength = await getLengthTask;  
  
            int contentLength = await AccessTheWebAsync();  
  
            resultsTextBox.Text +=
                $"\r\nLength of the downloaded string: {contentLength}.\r\n";
        }  
  
        // Three things to note in the signature:  
        //  - The method has an async modifier.   
        //  - The return type is Task or Task<T>. (See "Return Types" section.)  
        //    Here, it is Task<int> because the return statement returns an integer.  
        //  - The method name ends in "Async."  
        async Task<int> AccessTheWebAsync()  
        {   
            // You need to add a reference to System.Net.Http to declare client.  
            using (HttpClient client = new HttpClient())  
            {  
                    // GetStringAsync returns a Task<string>. That means that when you await the  
                    // task you'll get a string (urlContents).  
                    Task<string> getStringTask = client.GetStringAsync("https://docs.microsoft.com");  
  
                    // You can do work here that doesn't rely on the string from GetStringAsync.  
                    DoIndependentWork();  
  
                    // The await operator suspends AccessTheWebAsync.  
                    //  - AccessTheWebAsync can't continue until getStringTask is complete.  
                    //  - Meanwhile, control returns to the caller of AccessTheWebAsync.  
                    //  - Control resumes here when getStringTask is complete.   
                    //  - The await operator then retrieves the string result from getStringTask.  
                    string urlContents = await getStringTask;  
  
                    // The return statement specifies an integer result.  
                    // Any methods that are awaiting AccessTheWebAsync retrieve the length value.  
                    return urlContents.Length;  
            }  
        }  
  
        void DoIndependentWork()  
        {  
            resultsTextBox.Text += "Working . . . . . . .\r\n";  
        }  
    }  
}  
  
// Sample Output:  
  
// Working . . . . . . .  
  
// Length of the downloaded string: 25035.  
```  
  
## <a name="see-also"></a><span data-ttu-id="150dc-313">참고 항목</span><span class="sxs-lookup"><span data-stu-id="150dc-313">See also</span></span>

- [<span data-ttu-id="150dc-314">async</span><span class="sxs-lookup"><span data-stu-id="150dc-314">async</span></span>](../../../../csharp/language-reference/keywords/async.md)
- [<span data-ttu-id="150dc-315">await</span><span class="sxs-lookup"><span data-stu-id="150dc-315">await</span></span>](../../../../csharp/language-reference/keywords/await.md)
- [<span data-ttu-id="150dc-316">비동기 프로그래밍</span><span class="sxs-lookup"><span data-stu-id="150dc-316">Asynchronous programming</span></span>](../../../../csharp/async.md)
- [<span data-ttu-id="150dc-317">비동기 개요</span><span class="sxs-lookup"><span data-stu-id="150dc-317">Async overview</span></span>](../../../../standard/async.md)
