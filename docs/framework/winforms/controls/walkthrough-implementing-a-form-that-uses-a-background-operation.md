---
title: '연습: 백그라운드 작업을 사용하는 양식 구현'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- threading [Windows Forms], forms
- BackgroundWorker component
- background tasks
- forms [Windows Forms], multithreading
- threading [Windows Forms], walkthroughs
- forms [Windows Forms], background operations
- threading [Windows Forms], background operations
- background operations
ms.assetid: 4691b796-9200-471a-89c3-ba4c7cc78c03
ms.openlocfilehash: 1988ebd8c5f46346babe212962b617d30d765385
ms.sourcegitcommit: 0d0a6e96737dfe24d3257b7c94f25d9500f383ea
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/07/2019
ms.locfileid: "65211529"
---
# <a name="walkthrough-implementing-a-form-that-uses-a-background-operation"></a><span data-ttu-id="4a31b-102">연습: 백그라운드 작업을 사용하는 양식 구현</span><span class="sxs-lookup"><span data-stu-id="4a31b-102">Walkthrough: Implementing a Form That Uses a Background Operation</span></span>

<span data-ttu-id="4a31b-103">를 완료 하려면 시간이 오래 걸리는 작업을 해야 하 고 원하지 않는 사용자 인터페이스 (UI) 응답을 중지 하거나 사용할 수 있습니다 "중단" 하는 경우는 <xref:System.ComponentModel.BackgroundWorker> 다른 스레드에서 작업을 실행 하는 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="4a31b-103">If you have an operation that will take a long time to complete, and you do not want your user interface (UI) to stop responding or "hang," you can use the <xref:System.ComponentModel.BackgroundWorker> class to execute the operation on another thread.</span></span>

<span data-ttu-id="4a31b-104">이 연습에 사용 하는 방법을 보여 줍니다는 <xref:System.ComponentModel.BackgroundWorker> "백그라운드"에서 시간이 오래 걸리는 계산을 수행 하는 클래스 사용자 인터페이스의 응답성을 유지 하는 동안.</span><span class="sxs-lookup"><span data-stu-id="4a31b-104">This walkthrough illustrates how to use the <xref:System.ComponentModel.BackgroundWorker> class to perform time-consuming computations "in the background," while the user interface remains responsive.</span></span>  <span data-ttu-id="4a31b-105">완료하면 피보나치 수를 비동기적으로 계산하는 애플리케이션이 생깁니다.</span><span class="sxs-lookup"><span data-stu-id="4a31b-105">When you are through, you will have an application that computes Fibonacci numbers asynchronously.</span></span> <span data-ttu-id="4a31b-106">큰 피보나치 수를 계산하는 데는 상당한 시간이 걸릴 수도 있지만 이 지연으로 주 UI 스레드가 중단되지 않으며 계산 중에도 폼이 응답하게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4a31b-106">Even though computing a large Fibonacci number can take a noticeable amount of time, the main UI thread will not be interrupted by this delay, and the form will be responsive during the calculation.</span></span>

<span data-ttu-id="4a31b-107">이 연습에서 설명하는 작업은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="4a31b-107">Tasks illustrated in this walkthrough include:</span></span>

- <span data-ttu-id="4a31b-108">Windows 기반 애플리케이션 만들기</span><span class="sxs-lookup"><span data-stu-id="4a31b-108">Creating a Windows-based Application</span></span>

- <span data-ttu-id="4a31b-109">만들기는 <xref:System.ComponentModel.BackgroundWorker> 폼에서</span><span class="sxs-lookup"><span data-stu-id="4a31b-109">Creating a <xref:System.ComponentModel.BackgroundWorker> in Your Form</span></span>

- <span data-ttu-id="4a31b-110">비동기 이벤트 처리기 추가</span><span class="sxs-lookup"><span data-stu-id="4a31b-110">Adding Asynchronous Event Handlers</span></span>

- <span data-ttu-id="4a31b-111">진행률 보고 및 취소에 대한 지원 추가</span><span class="sxs-lookup"><span data-stu-id="4a31b-111">Adding Progress Reporting and Support for Cancellation</span></span>

<span data-ttu-id="4a31b-112">이 예제에서 사용 되는 코드의 전체 목록은 참조 하세요. [방법: 백그라운드 작업을 사용 하는 폼 구현](how-to-implement-a-form-that-uses-a-background-operation.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="4a31b-112">For a complete listing of the code used in this example, see [How to: Implement a Form That Uses a Background Operation](how-to-implement-a-form-that-uses-a-background-operation.md).</span></span>

## <a name="create-a-form-that-uses-a-background-operation"></a><span data-ttu-id="4a31b-113">백그라운드 작업을 사용 하는 폼 만들기</span><span class="sxs-lookup"><span data-stu-id="4a31b-113">Create a form that uses a background operation</span></span>

1. <span data-ttu-id="4a31b-114">Visual Studio에서 이라는 Windows 기반 응용 프로그램 프로젝트를 만듭니다 `BackgroundWorkerExample` (**파일** > **New** > **프로젝트**  >  **시각적 C#**  하거나 **Visual Basic** > **클래식 데스크톱** > **Windows Forms 응용 프로그램**).</span><span class="sxs-lookup"><span data-stu-id="4a31b-114">In Visual Studio, create a Windows-based application project called `BackgroundWorkerExample` (**File** > **New** > **Project** > **Visual C#** or **Visual Basic** > **Classic Desktop** > **Windows Forms Application**).</span></span>

2. <span data-ttu-id="4a31b-115">**솔루션 탐색기**에서 **Form1**을 마우스 오른쪽 단추로 클릭한 다음 바로 가기 메뉴에서 **이름 바꾸기**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="4a31b-115">In **Solution Explorer**, right-click **Form1** and select **Rename** from the shortcut menu.</span></span> <span data-ttu-id="4a31b-116">파일 이름을 `FibonacciCalculator`로 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="4a31b-116">Change the file name to `FibonacciCalculator`.</span></span> <span data-ttu-id="4a31b-117">코드 요소 '`Form1`'에 대한 모든 참조 이름을 변경할지 묻는 메시지가 표시되면 **예** 단추를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="4a31b-117">Click the **Yes** button when you are asked if you want to rename all references to the code element '`Form1`'.</span></span>

3. <span data-ttu-id="4a31b-118">끌어서를 <xref:System.Windows.Forms.NumericUpDown> 에서 제어 합니다 **도구 상자** 폼입니다.</span><span class="sxs-lookup"><span data-stu-id="4a31b-118">Drag a <xref:System.Windows.Forms.NumericUpDown> control from the **Toolbox** onto the form.</span></span> <span data-ttu-id="4a31b-119">설정 된 <xref:System.Windows.Forms.NumericUpDown.Minimum%2A> 속성을 `1` 하며 <xref:System.Windows.Forms.NumericUpDown.Maximum%2A> 속성을 `91`입니다.</span><span class="sxs-lookup"><span data-stu-id="4a31b-119">Set the <xref:System.Windows.Forms.NumericUpDown.Minimum%2A> property to `1` and the <xref:System.Windows.Forms.NumericUpDown.Maximum%2A> property to `91`.</span></span>

4. <span data-ttu-id="4a31b-120">두 개의 추가 <xref:System.Windows.Forms.Button> 폼에 컨트롤을 합니다.</span><span class="sxs-lookup"><span data-stu-id="4a31b-120">Add two <xref:System.Windows.Forms.Button> controls to the form.</span></span>

5. <span data-ttu-id="4a31b-121">첫 번째 이름 바꾸기 <xref:System.Windows.Forms.Button> 제어 `startAsyncButton` 설정 된 <xref:System.Windows.Forms.Control.Text%2A> 속성을 `Start Async`입니다.</span><span class="sxs-lookup"><span data-stu-id="4a31b-121">Rename the first <xref:System.Windows.Forms.Button> control `startAsyncButton` and set the <xref:System.Windows.Forms.Control.Text%2A> property to `Start Async`.</span></span> <span data-ttu-id="4a31b-122">두 번째 이름을 바꿀 <xref:System.Windows.Forms.Button> 컨트롤 `cancelAsyncButton`를 설정 합니다 <xref:System.Windows.Forms.Control.Text%2A> 속성을 `Cancel Async`합니다.</span><span class="sxs-lookup"><span data-stu-id="4a31b-122">Rename the second <xref:System.Windows.Forms.Button> control `cancelAsyncButton`, and set the <xref:System.Windows.Forms.Control.Text%2A> property to `Cancel Async`.</span></span> <span data-ttu-id="4a31b-123">설정 해당 <xref:System.Windows.Forms.Control.Enabled%2A> 속성을 `false`입니다.</span><span class="sxs-lookup"><span data-stu-id="4a31b-123">Set its <xref:System.Windows.Forms.Control.Enabled%2A> property to `false`.</span></span>

6. <span data-ttu-id="4a31b-124">둘 다에 대해 이벤트 처리기를 만들고 합니다 <xref:System.Windows.Forms.Button> 컨트롤의 <xref:System.Windows.Forms.Control.Click> 이벤트입니다.</span><span class="sxs-lookup"><span data-stu-id="4a31b-124">Create an event handler for both of the <xref:System.Windows.Forms.Button> controls' <xref:System.Windows.Forms.Control.Click> events.</span></span> <span data-ttu-id="4a31b-125">자세한 내용은 [방법: 디자이너를 사용 하 여 이벤트 처리기를 만들](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/zwwsdtbk(v=vs.100))합니다.</span><span class="sxs-lookup"><span data-stu-id="4a31b-125">For details, see [How to: Create Event Handlers Using the Designer](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/zwwsdtbk(v=vs.100)).</span></span>

7. <span data-ttu-id="4a31b-126">끌어서를 <xref:System.Windows.Forms.Label> 에서 제어 합니다 **도구 상자** 폼 하 고 이름을 `resultLabel`입니다.</span><span class="sxs-lookup"><span data-stu-id="4a31b-126">Drag a <xref:System.Windows.Forms.Label> control from the **Toolbox** onto the form and rename it `resultLabel`.</span></span>

8. <span data-ttu-id="4a31b-127">끌어서를 <xref:System.Windows.Forms.ProgressBar> 에서 제어 합니다 **도구 상자** 폼입니다.</span><span class="sxs-lookup"><span data-stu-id="4a31b-127">Drag a <xref:System.Windows.Forms.ProgressBar> control from the **Toolbox** onto the form.</span></span>

## <a name="create-a-backgroundworker-with-the-designer"></a><span data-ttu-id="4a31b-128">디자이너로 BackgroundWorker를 만들려면</span><span class="sxs-lookup"><span data-stu-id="4a31b-128">Create a BackgroundWorker with the Designer</span></span>

<span data-ttu-id="4a31b-129">만들 수 있습니다 합니다 <xref:System.ComponentModel.BackgroundWorker> 를 사용 하 여 비동기 작업에는 **Windows** **Forms 디자이너**합니다.</span><span class="sxs-lookup"><span data-stu-id="4a31b-129">You can create the <xref:System.ComponentModel.BackgroundWorker> for your asynchronous operation using the **Windows** **Forms Designer**.</span></span>

<span data-ttu-id="4a31b-130">**구성 요소** 탭을 **도구 상자**를 끌어를 <xref:System.ComponentModel.BackgroundWorker> 폼에.</span><span class="sxs-lookup"><span data-stu-id="4a31b-130">From the **Components** tab of the **Toolbox**, drag a <xref:System.ComponentModel.BackgroundWorker> onto the form.</span></span>

## <a name="add-asynchronous-event-handlers"></a><span data-ttu-id="4a31b-131">비동기 이벤트 처리기를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="4a31b-131">Add asynchronous event handlers</span></span>

<span data-ttu-id="4a31b-132">에 대 한 이벤트 처리기를 추가할 준비가 된 <xref:System.ComponentModel.BackgroundWorker> 구성 요소의 비동기 이벤트입니다.</span><span class="sxs-lookup"><span data-stu-id="4a31b-132">You are now ready to add event handlers for the <xref:System.ComponentModel.BackgroundWorker> component's asynchronous events.</span></span> <span data-ttu-id="4a31b-133">백그라운드로 실행되는 시간이 많이 소요되는 작업(예: 피보나치 수 계산)은 이러한 이벤트 처리기 중 하나에 의해 호출됩니다.</span><span class="sxs-lookup"><span data-stu-id="4a31b-133">The time-consuming operation that will run in the background, which computes Fibonacci numbers, is called by one of these event handlers.</span></span>

1. <span data-ttu-id="4a31b-134">에 **속성** 창 사용 하 여를 <xref:System.ComponentModel.BackgroundWorker> 구성 요소가 여전히 선택를 클릭 합니다 **이벤트** 단추.</span><span class="sxs-lookup"><span data-stu-id="4a31b-134">In the **Properties** window, with the <xref:System.ComponentModel.BackgroundWorker> component still selected, click the **Events** button.</span></span> <span data-ttu-id="4a31b-135">두 번 클릭 합니다 <xref:System.ComponentModel.BackgroundWorker.DoWork> 및 <xref:System.ComponentModel.BackgroundWorker.RunWorkerCompleted> 이벤트를 이벤트 처리기를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="4a31b-135">Double-click the <xref:System.ComponentModel.BackgroundWorker.DoWork> and <xref:System.ComponentModel.BackgroundWorker.RunWorkerCompleted> events to create event handlers.</span></span> <span data-ttu-id="4a31b-136">이벤트 처리기를 사용 하는 방법에 대 한 자세한 내용은 참조 하세요. [방법: 디자이너를 사용 하 여 이벤트 처리기를 만들](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/zwwsdtbk(v=vs.100))합니다.</span><span class="sxs-lookup"><span data-stu-id="4a31b-136">For more information about how to use event handlers, see [How to: Create Event Handlers Using the Designer](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/zwwsdtbk(v=vs.100)).</span></span>

2. <span data-ttu-id="4a31b-137">사용자 폼에서 `ComputeFibonacci`라는 새 메서드를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="4a31b-137">Create a new method, called `ComputeFibonacci`, in your form.</span></span> <span data-ttu-id="4a31b-138">이 메서드는 실제 작업을 수행하며 백그라운드에서 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="4a31b-138">This method does the actual work, and it will run in the background.</span></span> <span data-ttu-id="4a31b-139">이 코드는 피보나치 알고리즘의 재귀적 구현을 보여 줍니다. 이는 매우 비효율적이며, 큰 숫자를 완성하는 데 기하급수적으로 긴 시간이 소요됩니다.</span><span class="sxs-lookup"><span data-stu-id="4a31b-139">This code demonstrates the recursive implementation of the Fibonacci algorithm, which is notably inefficient, taking exponentially longer time to complete for larger numbers.</span></span> <span data-ttu-id="4a31b-140">여기서는 애플리케이션에서 오랜 지연을 유발할 수 있는 작업을 보여 주기 위해 설명 용도로 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="4a31b-140">It is used here for illustrative purposes, to show an operation that can introduce long delays in your application.</span></span>

     [!code-cpp[System.ComponentModel.BackgroundWorker#10](~/samples/snippets/cpp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/CPP/fibonacciform.cpp#10)]
     [!code-csharp[System.ComponentModel.BackgroundWorker#10](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/CS/fibonacciform.cs#10)]
     [!code-vb[System.ComponentModel.BackgroundWorker#10](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/VB/fibonacciform.vb#10)]

3. <span data-ttu-id="4a31b-141">에 <xref:System.ComponentModel.BackgroundWorker.DoWork> 이벤트 처리기 호출을 추가 합니다 `ComputeFibonacci` 메서드.</span><span class="sxs-lookup"><span data-stu-id="4a31b-141">In the <xref:System.ComponentModel.BackgroundWorker.DoWork> event handler, add a call to the `ComputeFibonacci` method.</span></span> <span data-ttu-id="4a31b-142">에 대 한 첫 번째 매개 변수를 사용 `ComputeFibonacci` 에서 합니다 <xref:System.ComponentModel.DoWorkEventArgs.Argument%2A> 의 속성을 <xref:System.ComponentModel.DoWorkEventArgs>입니다.</span><span class="sxs-lookup"><span data-stu-id="4a31b-142">Take the first parameter for `ComputeFibonacci` from the <xref:System.ComponentModel.DoWorkEventArgs.Argument%2A> property of the <xref:System.ComponentModel.DoWorkEventArgs>.</span></span> <span data-ttu-id="4a31b-143"><xref:System.ComponentModel.BackgroundWorker> 및 <xref:System.ComponentModel.DoWorkEventArgs> 매개 변수는 나중에 사용할 진행률 보고 및 취소를 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="4a31b-143">The <xref:System.ComponentModel.BackgroundWorker> and <xref:System.ComponentModel.DoWorkEventArgs> parameters will be used later for progress reporting and cancellation support.</span></span> <span data-ttu-id="4a31b-144">반환 값을 할당 `ComputeFibonacci` 에 <xref:System.ComponentModel.DoWorkEventArgs.Result%2A> 의 속성을 <xref:System.ComponentModel.DoWorkEventArgs>.</span><span class="sxs-lookup"><span data-stu-id="4a31b-144">Assign the return value from `ComputeFibonacci` to the <xref:System.ComponentModel.DoWorkEventArgs.Result%2A> property of the <xref:System.ComponentModel.DoWorkEventArgs>.</span></span> <span data-ttu-id="4a31b-145">이 결과 사용할 수 있습니다는 <xref:System.ComponentModel.BackgroundWorker.RunWorkerCompleted> 이벤트 처리기입니다.</span><span class="sxs-lookup"><span data-stu-id="4a31b-145">This result will be available to the <xref:System.ComponentModel.BackgroundWorker.RunWorkerCompleted> event handler.</span></span>

    > [!NOTE]
    > <span data-ttu-id="4a31b-146">합니다 <xref:System.ComponentModel.BackgroundWorker.DoWork> 이벤트 처리기를 참조 하지 않습니다 합니다 `backgroundWorker1` 인스턴스 변수를 직접이 이벤트 처리기의 특정 인스턴스에 결합은이 처럼 <xref:System.ComponentModel.BackgroundWorker>합니다.</span><span class="sxs-lookup"><span data-stu-id="4a31b-146">The <xref:System.ComponentModel.BackgroundWorker.DoWork> event handler does not reference the `backgroundWorker1` instance variable directly, as this would couple this event handler to a specific instance of <xref:System.ComponentModel.BackgroundWorker>.</span></span> <span data-ttu-id="4a31b-147">대신에 대 한 참조를 <xref:System.ComponentModel.BackgroundWorker> 이 발생 하는 이벤트에서 복구 되는 `sender` 매개 변수입니다.</span><span class="sxs-lookup"><span data-stu-id="4a31b-147">Instead, a reference to the <xref:System.ComponentModel.BackgroundWorker> that raised this event is recovered from the `sender` parameter.</span></span> <span data-ttu-id="4a31b-148">둘 이상의 폼 호스트 하는 경우이 중요 <xref:System.ComponentModel.BackgroundWorker>합니다.</span><span class="sxs-lookup"><span data-stu-id="4a31b-148">This is important when the form hosts more than one <xref:System.ComponentModel.BackgroundWorker>.</span></span> <span data-ttu-id="4a31b-149">사용자 인터페이스 개체를 조작 하지 않아야 이기도 하 <xref:System.ComponentModel.BackgroundWorker.DoWork> 이벤트 처리기입니다.</span><span class="sxs-lookup"><span data-stu-id="4a31b-149">It is also important not to manipulate any user-interface objects in your <xref:System.ComponentModel.BackgroundWorker.DoWork> event handler.</span></span> <span data-ttu-id="4a31b-150">대신, 사용자 인터페이스를 통해 통신 합니다 <xref:System.ComponentModel.BackgroundWorker> 이벤트입니다.</span><span class="sxs-lookup"><span data-stu-id="4a31b-150">Instead, communicate to the user interface through the <xref:System.ComponentModel.BackgroundWorker> events.</span></span>

     [!code-cpp[System.ComponentModel.BackgroundWorker#5](~/samples/snippets/cpp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/CPP/fibonacciform.cpp#5)]
     [!code-csharp[System.ComponentModel.BackgroundWorker#5](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/CS/fibonacciform.cs#5)]
     [!code-vb[System.ComponentModel.BackgroundWorker#5](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/VB/fibonacciform.vb#5)]

4. <span data-ttu-id="4a31b-151">에 `startAsyncButton` 컨트롤의 <xref:System.Windows.Forms.Control.Click> 이벤트 처리기에서 비동기 작업을 시작 하는 코드를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="4a31b-151">In the `startAsyncButton` control's <xref:System.Windows.Forms.Control.Click> event handler, add the code that starts the asynchronous operation.</span></span>

     [!code-cpp[System.ComponentModel.BackgroundWorker#13](~/samples/snippets/cpp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/CPP/fibonacciform.cpp#13)]
     [!code-csharp[System.ComponentModel.BackgroundWorker#13](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/CS/fibonacciform.cs#13)]
     [!code-vb[System.ComponentModel.BackgroundWorker#13](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/VB/fibonacciform.vb#13)]

5. <span data-ttu-id="4a31b-152">에 <xref:System.ComponentModel.BackgroundWorker.RunWorkerCompleted> 이벤트 처리기를 계산의 결과 할당 합니다 `resultLabel` 컨트롤.</span><span class="sxs-lookup"><span data-stu-id="4a31b-152">In the <xref:System.ComponentModel.BackgroundWorker.RunWorkerCompleted> event handler, assign the result of the calculation to the `resultLabel` control.</span></span>

     [!code-cpp[System.ComponentModel.BackgroundWorker#6](~/samples/snippets/cpp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/CPP/fibonacciform.cpp#6)]
     [!code-csharp[System.ComponentModel.BackgroundWorker#6](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/CS/fibonacciform.cs#6)]
     [!code-vb[System.ComponentModel.BackgroundWorker#6](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/VB/fibonacciform.vb#6)]

## <a name="adding-progress-reporting-and-support-for-cancellation"></a><span data-ttu-id="4a31b-153">진행률 보고 및 취소에 대한 지원 추가</span><span class="sxs-lookup"><span data-stu-id="4a31b-153">Adding Progress Reporting and Support for Cancellation</span></span>

<span data-ttu-id="4a31b-154">시간이 오래 소요되는 비동기 작업의 경우 사용자에게 진행률을 보고하고 사용자가 작업을 취소하도록 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4a31b-154">For asynchronous operations that will take a long time, it is often desirable to report progress to the user and to allow the user to cancel the operation.</span></span> <span data-ttu-id="4a31b-155"><xref:System.ComponentModel.BackgroundWorker> 클래스에 백그라운드 작업이 수행 될 때 진행률을 게시할 수 있는 이벤트를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="4a31b-155">The <xref:System.ComponentModel.BackgroundWorker> class provides an event that allows you to post progress as your background operation proceeds.</span></span> <span data-ttu-id="4a31b-156">또한 작업자 코드에 대 한 호출을 검색할 수 있는 플래그가 제공 <xref:System.ComponentModel.BackgroundWorker.CancelAsync%2A> 자체를 방해 합니다.</span><span class="sxs-lookup"><span data-stu-id="4a31b-156">It also provides a flag that allows your worker code to detect a call to <xref:System.ComponentModel.BackgroundWorker.CancelAsync%2A> and interrupt itself.</span></span>

### <a name="implement-progress-reporting"></a><span data-ttu-id="4a31b-157">진행률 보고를 구현 합니다.</span><span class="sxs-lookup"><span data-stu-id="4a31b-157">Implement progress reporting</span></span>

1. <span data-ttu-id="4a31b-158">**속성** 창에서 `backgroundWorker1`을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="4a31b-158">In the **Properties**, window, select `backgroundWorker1`.</span></span> <span data-ttu-id="4a31b-159">설정 된 <xref:System.ComponentModel.BackgroundWorker.WorkerReportsProgress%2A> 하 고 <xref:System.ComponentModel.BackgroundWorker.WorkerSupportsCancellation%2A> 속성을 `true`입니다.</span><span class="sxs-lookup"><span data-stu-id="4a31b-159">Set the <xref:System.ComponentModel.BackgroundWorker.WorkerReportsProgress%2A> and <xref:System.ComponentModel.BackgroundWorker.WorkerSupportsCancellation%2A> properties to `true`.</span></span>

2. <span data-ttu-id="4a31b-160">`FibonacciCalculator` 폼에서 변수 두 개를 선언합니다.</span><span class="sxs-lookup"><span data-stu-id="4a31b-160">Declare two variables in the `FibonacciCalculator` form.</span></span> <span data-ttu-id="4a31b-161">진행률을 추적하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="4a31b-161">These will be used to track progress.</span></span>

     [!code-cpp[System.ComponentModel.BackgroundWorker#14](~/samples/snippets/cpp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/CPP/fibonacciform.cpp#14)]
     [!code-csharp[System.ComponentModel.BackgroundWorker#14](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/CS/fibonacciform.cs#14)]
     [!code-vb[System.ComponentModel.BackgroundWorker#14](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/VB/fibonacciform.vb#14)]

3. <span data-ttu-id="4a31b-162"><xref:System.ComponentModel.BackgroundWorker.ProgressChanged> 이벤트에 대한 이벤트 처리기를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="4a31b-162">Add an event handler for the <xref:System.ComponentModel.BackgroundWorker.ProgressChanged> event.</span></span> <span data-ttu-id="4a31b-163">에 <xref:System.ComponentModel.BackgroundWorker.ProgressChanged> 이벤트 처리기, 업데이트를 <xref:System.Windows.Forms.ProgressBar> 사용 하 여를 <xref:System.ComponentModel.ProgressChangedEventArgs.ProgressPercentage%2A> 의 속성을 <xref:System.ComponentModel.ProgressChangedEventArgs> 매개 변수입니다.</span><span class="sxs-lookup"><span data-stu-id="4a31b-163">In the <xref:System.ComponentModel.BackgroundWorker.ProgressChanged> event handler, update the <xref:System.Windows.Forms.ProgressBar> with the <xref:System.ComponentModel.ProgressChangedEventArgs.ProgressPercentage%2A> property of the <xref:System.ComponentModel.ProgressChangedEventArgs> parameter.</span></span>

     [!code-cpp[System.ComponentModel.BackgroundWorker#7](~/samples/snippets/cpp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/CPP/fibonacciform.cpp#7)]
     [!code-csharp[System.ComponentModel.BackgroundWorker#7](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/CS/fibonacciform.cs#7)]
     [!code-vb[System.ComponentModel.BackgroundWorker#7](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/VB/fibonacciform.vb#7)]

### <a name="implement-support-for-cancellation"></a><span data-ttu-id="4a31b-164">취소에 대 한 구현 지원</span><span class="sxs-lookup"><span data-stu-id="4a31b-164">Implement support for cancellation</span></span>

1. <span data-ttu-id="4a31b-165">에 `cancelAsyncButton` 컨트롤의 <xref:System.Windows.Forms.Control.Click> 이벤트 처리기에서 비동기 작업을 취소 하는 코드를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="4a31b-165">In the `cancelAsyncButton` control's <xref:System.Windows.Forms.Control.Click> event handler, add the code that cancels the asynchronous operation.</span></span>

     [!code-cpp[System.ComponentModel.BackgroundWorker#4](~/samples/snippets/cpp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/CPP/fibonacciform.cpp#4)]
     [!code-csharp[System.ComponentModel.BackgroundWorker#4](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/CS/fibonacciform.cs#4)]
     [!code-vb[System.ComponentModel.BackgroundWorker#4](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/VB/fibonacciform.vb#4)]

2. <span data-ttu-id="4a31b-166">`ComputeFibonacci` 메서드의 다음 코드 조각은 진행률을 보고하고 취소를 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="4a31b-166">The following code fragments in the `ComputeFibonacci` method report progress and support cancellation.</span></span>

     [!code-cpp[System.ComponentModel.BackgroundWorker#11](~/samples/snippets/cpp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/CPP/fibonacciform.cpp#11)]
     [!code-csharp[System.ComponentModel.BackgroundWorker#11](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/CS/fibonacciform.cs#11)]
     [!code-vb[System.ComponentModel.BackgroundWorker#11](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/VB/fibonacciform.vb#11)]
    [!code-cpp[System.ComponentModel.BackgroundWorker#12](~/samples/snippets/cpp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/CPP/fibonacciform.cpp#12)]
    [!code-csharp[System.ComponentModel.BackgroundWorker#12](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/CS/fibonacciform.cs#12)]
    [!code-vb[System.ComponentModel.BackgroundWorker#12](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/VB/fibonacciform.vb#12)]

## <a name="checkpoint"></a><span data-ttu-id="4a31b-167">검사점</span><span class="sxs-lookup"><span data-stu-id="4a31b-167">Checkpoint</span></span>

<span data-ttu-id="4a31b-168">이 시점에서 피보나치 계산기 애플리케이션을 컴파일하여 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4a31b-168">At this point, you can compile and run the Fibonacci Calculator application.</span></span>

<span data-ttu-id="4a31b-169">키를 눌러 **F5** 를 컴파일하고 응용 프로그램을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="4a31b-169">Press **F5** to compile and run the application.</span></span>

<span data-ttu-id="4a31b-170">계산 백그라운드에서 실행 되는 동안 표시 됩니다는 <xref:System.Windows.Forms.ProgressBar> 완료 될 때까지 계산 진행률이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4a31b-170">While the calculation is running in the background, you will see the <xref:System.Windows.Forms.ProgressBar> displaying the progress of the calculation toward completion.</span></span> <span data-ttu-id="4a31b-171">보류 중인 작업도 취소할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4a31b-171">You can also cancel the pending operation.</span></span>

<span data-ttu-id="4a31b-172">작은 숫자에 대한 계산은 매우 빠르지만 큰 수에 대한 계산은 상당한 지연이 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="4a31b-172">For small numbers, the calculation should be very fast, but for larger numbers, you should see a noticeable delay.</span></span> <span data-ttu-id="4a31b-173">값을 30 이상 입력하면 컴퓨터 속도에 따라 몇 초의 지연이 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="4a31b-173">If you enter a value of 30 or greater, you should see a delay of several seconds, depending on the speed of your computer.</span></span> <span data-ttu-id="4a31b-174">값이 40을 넘으면 계산을 완료하는 데 몇 분 또는 몇 시간이 소요될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4a31b-174">For values greater than 40, it may take minutes or hours to finish the calculation.</span></span> <span data-ttu-id="4a31b-175">계산기가 큰 피보나치 수를 계산하는 동안 폼을 자유롭게 움직이고, 최소화 및 최대화하며, 해제할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4a31b-175">While the calculator is busy computing a large Fibonacci number, notice that you can freely move the form around, minimize, maximize, and even dismiss it.</span></span> <span data-ttu-id="4a31b-176">주 UI 스레드가 계산이 완료되기를 기다리지 않기 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="4a31b-176">This is because the main UI thread is not waiting for the calculation to finish.</span></span>

## <a name="next-steps"></a><span data-ttu-id="4a31b-177">다음 단계</span><span class="sxs-lookup"><span data-stu-id="4a31b-177">Next steps</span></span>

<span data-ttu-id="4a31b-178">사용 하는 폼 구현 했으므로 <xref:System.ComponentModel.BackgroundWorker> 백그라운드에서 계산을 실행 하는 구성 요소가 비동기 작업에 대 한 다른 가능성을 살펴볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4a31b-178">Now that you have implemented a form that uses a <xref:System.ComponentModel.BackgroundWorker> component to execute a computation in the background, you can explore other possibilities for asynchronous operations:</span></span>

- <span data-ttu-id="4a31b-179">사용 하 여 <xref:System.ComponentModel.BackgroundWorker> 여러 동시 작업에 대 한 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="4a31b-179">Use multiple <xref:System.ComponentModel.BackgroundWorker> objects for several simultaneous operations.</span></span>

- <span data-ttu-id="4a31b-180">다중 스레드 응용 프로그램을 디버깅 하려면 참조 [방법: 스레드 창 사용](/visualstudio/debugger/how-to-use-the-threads-window)합니다.</span><span class="sxs-lookup"><span data-stu-id="4a31b-180">To debug your multithreaded application, see [How to: Use the Threads Window](/visualstudio/debugger/how-to-use-the-threads-window).</span></span>

- <span data-ttu-id="4a31b-181">비동기 프로그래밍 모델을 지원하는 사용자 고유의 구성 요소를 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="4a31b-181">Implement your own component that supports the asynchronous programming model.</span></span> <span data-ttu-id="4a31b-182">자세한 내용은 [이벤트 기반 비동기 패턴 개요](../../../standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-overview.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="4a31b-182">For more information, see [Event-based Asynchronous Pattern Overview](../../../standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-overview.md).</span></span>

    > [!CAUTION]
    > <span data-ttu-id="4a31b-183">모든 종류의 다중 스레딩을 사용할 때는 매우 심각하고 복잡한 버그에 잠재적으로 노출됩니다.</span><span class="sxs-lookup"><span data-stu-id="4a31b-183">When using multithreading of any sort, you potentially expose yourself to very serious and complex bugs.</span></span> <span data-ttu-id="4a31b-184">다중 스레딩을 사용하는 솔루션을 구현하기 전에 [관리되는 스레딩을 구현하는 최선의 방법](../../../standard/threading/managed-threading-best-practices.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="4a31b-184">Consult the [Managed Threading Best Practices](../../../standard/threading/managed-threading-best-practices.md) before implementing any solution that uses multithreading.</span></span>

## <a name="see-also"></a><span data-ttu-id="4a31b-185">참고자료</span><span class="sxs-lookup"><span data-stu-id="4a31b-185">See also</span></span>

- <xref:System.ComponentModel.BackgroundWorker?displayProperty=nameWithType>
- [<span data-ttu-id="4a31b-186">관리되는 스레딩</span><span class="sxs-lookup"><span data-stu-id="4a31b-186">Managed Threading</span></span>](../../../standard/threading/index.md)
- [<span data-ttu-id="4a31b-187">관리되는 스레딩을 구현하는 최선의 방법</span><span class="sxs-lookup"><span data-stu-id="4a31b-187">Managed Threading Best Practices</span></span>](../../../standard/threading/managed-threading-best-practices.md)
- [<span data-ttu-id="4a31b-188">이벤트 기반 비동기 패턴 개요</span><span class="sxs-lookup"><span data-stu-id="4a31b-188">Event-based Asynchronous Pattern Overview</span></span>](../../../standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-overview.md)
- [<span data-ttu-id="4a31b-189">방법: 백그라운드 작업을 사용하는 양식 구현</span><span class="sxs-lookup"><span data-stu-id="4a31b-189">How to: Implement a Form That Uses a Background Operation</span></span>](how-to-implement-a-form-that-uses-a-background-operation.md)
- [<span data-ttu-id="4a31b-190">연습: 백그라운드에서 작업 실행</span><span class="sxs-lookup"><span data-stu-id="4a31b-190">Walkthrough: Running an Operation in the Background</span></span>](walkthrough-running-an-operation-in-the-background.md)
- [<span data-ttu-id="4a31b-191">BackgroundWorker 구성 요소</span><span class="sxs-lookup"><span data-stu-id="4a31b-191">BackgroundWorker Component</span></span>](backgroundworker-component.md)
