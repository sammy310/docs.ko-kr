---
title: 일정 기간 이후 비동기 작업 취소(C#)
description: 일정 기간 내에 완료되지 않은 연결된 작업의 취소를 예약하는 방법을 알아봅니다.
ms.date: 02/03/2021
ms.topic: tutorial
ms.assetid: 194282c2-399f-46da-a7a6-96674e00b0b3
ms.openlocfilehash: 98c42a2df6153d668b99b6dec49ffe380293b205
ms.sourcegitcommit: 65af0f0ad316858882845391d60ef7e303b756e8
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/05/2021
ms.locfileid: "99585379"
---
# <a name="cancel-async-tasks-after-a-period-of-time-c"></a><span data-ttu-id="7e3bc-103">일정 기간 이후 비동기 작업 취소(C#)</span><span class="sxs-lookup"><span data-stu-id="7e3bc-103">Cancel async tasks after a period of time (C#)</span></span>

<span data-ttu-id="7e3bc-104">작업이 완료될 때까지 대기하지 않으려는 경우 일정 기간 후에 <xref:System.Threading.CancellationTokenSource.CancelAfter%2A?displayProperty=nameWithType> 메서드를 사용하여 비동기 작업을 취소할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7e3bc-104">You can cancel an asynchronous operation after a period of time by using the <xref:System.Threading.CancellationTokenSource.CancelAfter%2A?displayProperty=nameWithType> method if you don't want to wait for the operation to finish.</span></span> <span data-ttu-id="7e3bc-105">이 메서드는 `CancelAfter` 식으로 지정된 일정 기간 내에 완료되지 않은 연결된 작업의 취소를 예약합니다.</span><span class="sxs-lookup"><span data-stu-id="7e3bc-105">This method schedules the cancellation of any associated tasks that aren't complete within the period of time that's designated by the `CancelAfter` expression.</span></span>

<span data-ttu-id="7e3bc-106">이 예제는 [작업 목록 취소(C#)](cancel-an-async-task-or-a-list-of-tasks.md)에서 개발된 코드에 추가되어 웹 사이트 목록을 다운로드하고 각 웹 사이트의 콘텐츠 길이를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="7e3bc-106">This example adds to the code that's developed in [Cancel a list of tasks (C#)](cancel-an-async-task-or-a-list-of-tasks.md) to download a list of websites and to display the length of the contents of each one.</span></span>

<span data-ttu-id="7e3bc-107">이 자습서에서는 다음 내용을 다룹니다.</span><span class="sxs-lookup"><span data-stu-id="7e3bc-107">This tutorial covers:</span></span>

> [!div class="checklist"]
>
> - <span data-ttu-id="7e3bc-108">기존 .NET 콘솔 애플리케이션 업데이트</span><span class="sxs-lookup"><span data-stu-id="7e3bc-108">Updating an existing .NET console application</span></span>
> - <span data-ttu-id="7e3bc-109">취소 예약</span><span class="sxs-lookup"><span data-stu-id="7e3bc-109">Scheduling a cancellation</span></span>

## <a name="prerequisites"></a><span data-ttu-id="7e3bc-110">필수 구성 요소</span><span class="sxs-lookup"><span data-stu-id="7e3bc-110">Prerequisites</span></span>

<span data-ttu-id="7e3bc-111">이 자습서를 사용하려면 다음이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="7e3bc-111">This tutorial requires the following:</span></span>

- <span data-ttu-id="7e3bc-112">[작업 목록 취소(C#)](cancel-an-async-task-or-a-list-of-tasks.md) 자습서에서 애플리케이션을 만들었어야 함</span><span class="sxs-lookup"><span data-stu-id="7e3bc-112">You're expected to have created an application in the [Cancel a list of tasks (C#)](cancel-an-async-task-or-a-list-of-tasks.md) tutorial</span></span>
- [<span data-ttu-id="7e3bc-113">.NET 5.0 이상 SDK</span><span class="sxs-lookup"><span data-stu-id="7e3bc-113">.NET 5.0 or later SDK</span></span>](https://dotnet.microsoft.com/download/dotnet/5.0)
- <span data-ttu-id="7e3bc-114">IDE(통합 개발 환경)</span><span class="sxs-lookup"><span data-stu-id="7e3bc-114">Integrated development environment (IDE)</span></span>
  - [<span data-ttu-id="7e3bc-115">Visual Studio, Visual Studio Code 또는 Mac용 Visual Studio 권장</span><span class="sxs-lookup"><span data-stu-id="7e3bc-115">We recommend Visual Studio, Visual Studio Code, or Visual Studio for Mac</span></span>](https://visualstudio.microsoft.com)

## <a name="update-application-entry-point"></a><span data-ttu-id="7e3bc-116">애플리케이션 진입점 업데이트</span><span class="sxs-lookup"><span data-stu-id="7e3bc-116">Update application entry point</span></span>

<span data-ttu-id="7e3bc-117">기존 `Main` 메서드를 다음으로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="7e3bc-117">Replace the existing `Main` method with the following:</span></span>

```csharp
static async Task Main()
{
    Console.WriteLine("Application started.");

    try
    {
        s_cts.CancelAfter(3500);

        await SumPageSizesAsync();
    }
    catch (TaskCanceledException)
    {
        Console.WriteLine("\nTasks cancelled: timed out.\n");
    }
    finally
    {
        s_cts.Dispose();
    }

    Console.WriteLine("Application ending.");
}
```

<span data-ttu-id="7e3bc-118">업데이트된 `Main` 메서드는 몇 가지 지침 메시지를 콘솔에 기록합니다.</span><span class="sxs-lookup"><span data-stu-id="7e3bc-118">The updated `Main` method writes a few instructional messages to the console.</span></span> <span data-ttu-id="7e3bc-119">[try catch](../../../language-reference/keywords/try-catch.md) 내에서 <xref:System.Threading.CancellationTokenSource.CancelAfter(System.Int32)?displayProperty=nameWithType> 호출은 취소를 예약합니다.</span><span class="sxs-lookup"><span data-stu-id="7e3bc-119">Within the [try catch](../../../language-reference/keywords/try-catch.md), a call to <xref:System.Threading.CancellationTokenSource.CancelAfter(System.Int32)?displayProperty=nameWithType> schedules a cancellation.</span></span> <span data-ttu-id="7e3bc-120">이렇게 하면 일정 기간 후에 취소하라는 신호가 전송됩니다.</span><span class="sxs-lookup"><span data-stu-id="7e3bc-120">This will signal cancellation after a period of time.</span></span>

<span data-ttu-id="7e3bc-121">다음으로, `SumPageSizesAsync` 메서드는 대기합니다.</span><span class="sxs-lookup"><span data-stu-id="7e3bc-121">Next, the `SumPageSizesAsync` method is awaited.</span></span> <span data-ttu-id="7e3bc-122">예약된 취소보다 모든 URL이 더 빠르게 처리되면 애플리케이션이 종료됩니다.</span><span class="sxs-lookup"><span data-stu-id="7e3bc-122">If processing all of the URLs occurs faster than the scheduled cancellation, the application ends.</span></span> <span data-ttu-id="7e3bc-123">그러나 모든 URL이 처리되기 전에 예약된 취소가 트리거되면 <xref:System.Threading.Tasks.TaskCanceledException>이 throw됩니다.</span><span class="sxs-lookup"><span data-stu-id="7e3bc-123">However, if the scheduled cancellation is triggered before all of the URLs are processed, a <xref:System.Threading.Tasks.TaskCanceledException> is thrown.</span></span>

### <a name="example-application-output"></a><span data-ttu-id="7e3bc-124">예제 애플리케이션 출력</span><span class="sxs-lookup"><span data-stu-id="7e3bc-124">Example application output</span></span>

```console
Application started.

https://docs.microsoft.com                                       37,357
https://docs.microsoft.com/aspnet/core                           85,589
https://docs.microsoft.com/azure                                398,939
https://docs.microsoft.com/azure/devops                          73,663

Tasks cancelled: timed out.

Application ending.
```

## <a name="complete-example"></a><span data-ttu-id="7e3bc-125">전체 예제</span><span class="sxs-lookup"><span data-stu-id="7e3bc-125">Complete example</span></span>

<span data-ttu-id="7e3bc-126">다음 코드는 예제에 관한 *Program.cs* 파일의 전체 텍스트입니다.</span><span class="sxs-lookup"><span data-stu-id="7e3bc-126">The following code is the complete text of the *Program.cs* file for the example.</span></span>

:::code language="csharp" source="snippets/cancel-tasks/cancel-task-after-period-of-time/Program.cs":::

## <a name="see-also"></a><span data-ttu-id="7e3bc-127">참고 항목</span><span class="sxs-lookup"><span data-stu-id="7e3bc-127">See also</span></span>

- <xref:System.Threading.CancellationToken>
- <xref:System.Threading.CancellationTokenSource>
- [<span data-ttu-id="7e3bc-128">async 및 await를 사용한 비동기 프로그래밍(C#)</span><span class="sxs-lookup"><span data-stu-id="7e3bc-128">Asynchronous programming with async and await (C#)</span></span>](index.md)
- [<span data-ttu-id="7e3bc-129">작업 목록 취소(C#)</span><span class="sxs-lookup"><span data-stu-id="7e3bc-129">Cancel a list of tasks (C#)</span></span>](cancel-an-async-task-or-a-list-of-tasks.md)
