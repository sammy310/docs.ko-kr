---
title: '자습서: Windows 서비스 앱 만들기'
description: 이 자습서에서는 이벤트 로그에 메시지를 쓰는 Windows 서비스 앱을 Visual Studio에서 만듭니다. 기능을 추가하고, 상태를 설정하고, 설치 관리자를 추가합니다.
ms.date: 03/27/2019
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Windows service applications, walkthroughs
- Windows service applications, creating
ms.assetid: e24d8a3d-edc6-485c-b6e0-5672d91fb607
ms.openlocfilehash: bbf9ab7d06c952aa2e076fc36c71f37f1bb10884
ms.sourcegitcommit: 97405ed212f69b0a32faa66a5d5fae7e76628b68
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/01/2020
ms.locfileid: "91608389"
---
# <a name="tutorial-create-a-windows-service-app"></a><span data-ttu-id="3a603-104">자습서: Windows 서비스 앱 만들기</span><span class="sxs-lookup"><span data-stu-id="3a603-104">Tutorial: Create a Windows service app</span></span>

<span data-ttu-id="3a603-105">이 문서에서는 이벤트 로그에 메시지를 쓰는 Windows 서비스 앱을 Visual Studio에서 만드는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="3a603-105">This article demonstrates how to create a Windows service app in Visual Studio that writes messages to an event log.</span></span>

## <a name="create-a-service"></a><span data-ttu-id="3a603-106">서비스 만들기</span><span class="sxs-lookup"><span data-stu-id="3a603-106">Create a service</span></span>

<span data-ttu-id="3a603-107">우선 프로젝트를 만들고 서비스가 제대로 작동하는 데 필요한 값을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="3a603-107">To begin, create the project and set the values that are required for the service to function correctly.</span></span>

1. <span data-ttu-id="3a603-108">Visual Studio **파일** 메뉴에서 **새로 만들기** > **프로젝트**를 선택하거나 **Ctrl**+**Shift**+**N**을 눌러 **새 프로젝트** 창을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="3a603-108">From the Visual Studio **File** menu, select **New** > **Project** (or press **Ctrl**+**Shift**+**N**) to open the **New Project** window.</span></span>

2. <span data-ttu-id="3a603-109">**Windows 서비스(.NET Framework)** 프로젝트 템플릿을 검색하여 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="3a603-109">Navigate to and select the **Windows Service (.NET Framework)** project template.</span></span> <span data-ttu-id="3a603-110">템플릿을 찾으려면 **설치됨**과 **Visual C#** 또는 **Visual Basic**을 차례로 확장한 후 **Windows 데스크톱**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="3a603-110">To find it, expand **Installed** and **Visual C#** or **Visual Basic**, then select **Windows Desktop**.</span></span> <span data-ttu-id="3a603-111">또는 오른쪽 상단의 검색 상자에서 *Windows 서비스*를 입력하고 **Enter** 키를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="3a603-111">Or, enter *Windows Service* in the search box on the upper right and press **Enter**.</span></span>

   ![Visual Studio의 새 프로젝트 대화 상자에 있는 Windows 서비스 템플릿](./media/new-project-dialog.png)

   > [!NOTE]
   > <span data-ttu-id="3a603-113">**Windows 서비스** 템플릿이 표시되지 않는 경우 **.NET 데스크톱 개발** 워크로드를 설치해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3a603-113">If you don't see the **Windows Service** template, you may need to install the **.NET desktop development** workload:</span></span>
   >
   > <span data-ttu-id="3a603-114">**새 프로젝트** 대화 상자의 왼쪽 하단에서 **Visual Studio 설치 관리자 열기**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="3a603-114">In the **New Project** dialog, select **Open Visual Studio Installer** on the lower left.</span></span> <span data-ttu-id="3a603-115">**.NET 데스크톱 개발** 워크로드를 선택한 다음, **수정**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="3a603-115">Select the **.NET desktop development** workload, and then select **Modify**.</span></span>

3. <span data-ttu-id="3a603-116">**이름**에서 *MyNewService*를 입력한 다음, **확인**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="3a603-116">For **Name**, enter *MyNewService*, and then select **OK**.</span></span>

   <span data-ttu-id="3a603-117">**디자인** 탭이 표시됩니다(**Service1.cs [디자인]** 또는 **Service1.vb [디자인]** ).</span><span class="sxs-lookup"><span data-stu-id="3a603-117">The **Design** tab appears (**Service1.cs [Design]** or **Service1.vb [Design]**).</span></span>

   <span data-ttu-id="3a603-118">프로젝트 템플릿은 <xref:System.ServiceProcess.ServiceBase?displayProperty=nameWithType>에서 상속된 `Service1`이라는 구성 요소 클래스를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="3a603-118">The project template includes a component class named `Service1` that inherits from <xref:System.ServiceProcess.ServiceBase?displayProperty=nameWithType>.</span></span> <span data-ttu-id="3a603-119">여기에는 서비스를 시작하는 코드 등의 많은 기본 서비스 코드가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="3a603-119">It includes much of the basic service code, such as the code to start the service.</span></span>

## <a name="rename-the-service"></a><span data-ttu-id="3a603-120">서비스 이름 바꾸기</span><span class="sxs-lookup"><span data-stu-id="3a603-120">Rename the service</span></span>

<span data-ttu-id="3a603-121">서비스 이름을 **Service1**에서 **MyNewService**로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="3a603-121">Rename the service from **Service1** to **MyNewService**.</span></span>

1. <span data-ttu-id="3a603-122">**솔루션 탐색기**에서 **Service1.cs** 또는 **Service1.vb**를 선택하고 바로 가기 메뉴에서 **이름 바꾸기**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="3a603-122">In **Solution Explorer**, select **Service1.cs**, or **Service1.vb**, and choose **Rename** from the shortcut menu.</span></span> <span data-ttu-id="3a603-123">파일 이름을 **MyNewService.cs** 또는 **MyNewService.vb**로 바꾼 다음, **Enter** 키를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="3a603-123">Rename the file to **MyNewService.cs**, or **MyNewService.vb**, and then press **Enter**</span></span>

    <span data-ttu-id="3a603-124">코드 요소 *Service1*에 대한 모든 참조 이름을 변경할지 여부를 묻는 팝업 창이 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="3a603-124">A pop-up window appears asking whether you would like to rename all references to the code element *Service1*.</span></span>

2. <span data-ttu-id="3a603-125">팝업 창에서 **예**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="3a603-125">In the pop-up window, select **Yes**.</span></span>

    <span data-ttu-id="3a603-126">![프롬프트 이름 바꾸기](./media/windows-service-rename.png "Windows 서비스 이름 바꾸기 프롬프트")</span><span class="sxs-lookup"><span data-stu-id="3a603-126">![Rename prompt](./media/windows-service-rename.png "Windows service rename prompt")</span></span>

3. <span data-ttu-id="3a603-127">**디자인** 탭의 바로 가기 메뉴에서 **속성**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="3a603-127">In the **Design** tab, select **Properties** from the shortcut menu.</span></span> <span data-ttu-id="3a603-128">**속성** 창에서 **ServiceName** 값을 *MyNewService*로 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="3a603-128">From the **Properties** window, change the **ServiceName** value to *MyNewService*.</span></span>

    <span data-ttu-id="3a603-129">![서비스 속성](./media/windows-service-properties.png "Windows 서비스 속성")</span><span class="sxs-lookup"><span data-stu-id="3a603-129">![Service properties](./media/windows-service-properties.png "Windows service properties")</span></span>

4. <span data-ttu-id="3a603-130">**파일** 메뉴에서 **모두 저장**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="3a603-130">Select **Save All** from the **File** menu.</span></span>

## <a name="add-features-to-the-service"></a><span data-ttu-id="3a603-131">서비스에 기능 추가</span><span class="sxs-lookup"><span data-stu-id="3a603-131">Add features to the service</span></span>

<span data-ttu-id="3a603-132">다음 섹션에서는 Windows 서비스에 사용자 지정 이벤트 로그를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="3a603-132">In this section, you add a custom event log to the Windows service.</span></span> <span data-ttu-id="3a603-133">Windows 서비스에 추가할 수 있는 구성 요소 종류의 한 예로 <xref:System.Diagnostics.EventLog> 구성 요소를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="3a603-133">The <xref:System.Diagnostics.EventLog> component is an example of the type of component you can add to a Windows service.</span></span>

### <a name="add-custom-event-log-functionality"></a><span data-ttu-id="3a603-134">사용자 지정 이벤트 로그 기능 추가</span><span class="sxs-lookup"><span data-stu-id="3a603-134">Add custom event log functionality</span></span>

1. <span data-ttu-id="3a603-135">**솔루션 탐색기**에서 **MyNewService.cs** 또는 **MyNewService.vb**의 바로 가기 메뉴에 있는 **뷰 디자이너**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="3a603-135">In **Solution Explorer**, from the shortcut menu for **MyNewService.cs**, or **MyNewService.vb**, choose **View Designer**.</span></span>

2. <span data-ttu-id="3a603-136">**도구 상자**에서 **구성 요소**를 확장한 다음, **EventLog** 구성 요소를 **Service1.cs [디자인]** 또는 **Service1.vb [디자인]** 탭으로 끕니다.</span><span class="sxs-lookup"><span data-stu-id="3a603-136">In **Toolbox**, expand **Components**, and then drag the **EventLog** component to the **Service1.cs [Design]**, or **Service1.vb [Design]** tab.</span></span>

3. <span data-ttu-id="3a603-137">**솔루션 탐색기**에서 **MyNewService.cs** 또는 **MyNewService.vb**의 바로 가기 메뉴에 있는 **코드 보기**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="3a603-137">In **Solution Explorer**, from the shortcut menu for **MyNewService.cs**, or **MyNewService.vb**, choose **View Code**.</span></span>

4. <span data-ttu-id="3a603-138">사용자 지정 이벤트 로그를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="3a603-138">Define a custom event log.</span></span> <span data-ttu-id="3a603-139">C#에서는 기존 `MyNewService()` 생성자를 편집하고 Visual Basic에서는 `New()` 생성자를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="3a603-139">For C#, edit the existing `MyNewService()` constructor; for Visual Basic, add the `New()` constructor:</span></span>

   [!code-csharp[VbRadconService#2](../../../samples/snippets/csharp/VS_Snippets_VBCSharp/VbRadconService/CS/MyNewService.cs#2)]
   [!code-vb[VbRadconService#2](../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbRadconService/VB/MyNewService.vb#2)]

5. <span data-ttu-id="3a603-140">`using` 문을 **MyNewService.cs**에 추가하거나(없는 경우) <xref:System.Diagnostics?displayProperty=nameWithType> 네임스페이스에 대해서는 `Imports` 문을 **MyNewService.vb**에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="3a603-140">Add a `using` statement to **MyNewService.cs** (if it doesn't already exist), or an `Imports` statement **MyNewService.vb**, for the <xref:System.Diagnostics?displayProperty=nameWithType> namespace:</span></span>

    ```csharp
    using System.Diagnostics;
    ```

    ```vb
    Imports System.Diagnostics
    ```

6. <span data-ttu-id="3a603-141">**파일** 메뉴에서 **모두 저장**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="3a603-141">Select **Save All** from the **File** menu.</span></span>

### <a name="define-what-occurs-when-the-service-starts"></a><span data-ttu-id="3a603-142">서비스가 시작될 때 수행되는 동작 정의</span><span class="sxs-lookup"><span data-stu-id="3a603-142">Define what occurs when the service starts</span></span>

<span data-ttu-id="3a603-143">**MyNewService.cs** 또는 **MyNewService.vb**의 코드 편집기에서 <xref:System.ServiceProcess.ServiceBase.OnStart%2A> 메서드를 찾습니다. Visual Studio는 프로젝트를 만들 때 자동으로 빈 메서드 정의를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="3a603-143">In the code editor for **MyNewService.cs** or **MyNewService.vb**, locate the <xref:System.ServiceProcess.ServiceBase.OnStart%2A> method; Visual Studio automatically created an empty method definition when you created the project.</span></span> <span data-ttu-id="3a603-144">서비스가 시작될 때 이벤트 로그에 항목을 기록하는 코드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="3a603-144">Add code that writes an entry to the event log when the service starts:</span></span>

[!code-csharp[VbRadconService#3](../../../samples/snippets/csharp/VS_Snippets_VBCSharp/VbRadconService/CS/MyNewService.cs#3)]
[!code-vb[VbRadconService#3](../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbRadconService/VB/MyNewService.vb#3)]

#### <a name="polling"></a><span data-ttu-id="3a603-145">폴링</span><span class="sxs-lookup"><span data-stu-id="3a603-145">Polling</span></span>

<span data-ttu-id="3a603-146">서비스 애플리케이션은 오랫동안 실행되도록 설계되므로 대개 <xref:System.ServiceProcess.ServiceBase.OnStart%2A> 메서드에서 설정한 시스템을 폴링하거나 모니터링합니다.</span><span class="sxs-lookup"><span data-stu-id="3a603-146">Because a service application is designed to be long-running, it usually polls or monitors the system, which you set up in the <xref:System.ServiceProcess.ServiceBase.OnStart%2A> method.</span></span> <span data-ttu-id="3a603-147">서비스의 작업이 시작되고 나면 `OnStart` 메서드가 운영 체제에 반환되어야 시스템이 차단되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="3a603-147">The `OnStart` method must return to the operating system after the service's operation has begun so that the system isn't blocked.</span></span>

<span data-ttu-id="3a603-148">간단한 폴링 메커니즘을 설정하려면 <xref:System.Timers.Timer?displayProperty=nameWithType> 구성 요소를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="3a603-148">To set up a simple polling mechanism, use the <xref:System.Timers.Timer?displayProperty=nameWithType> component.</span></span> <span data-ttu-id="3a603-149">타이머가 일정 간격으로 <xref:System.Timers.Timer.Elapsed> 이벤트를 발생시키며 서비스는 이벤트가 발생했을 때 모니터링을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3a603-149">The timer raises an <xref:System.Timers.Timer.Elapsed> event at regular intervals, at which time your service can do its monitoring.</span></span> <span data-ttu-id="3a603-150"><xref:System.Timers.Timer> 구성 요소는 다음과 같이 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="3a603-150">You use the <xref:System.Timers.Timer> component as follows:</span></span>

- <span data-ttu-id="3a603-151">`MyNewService.OnStart` 메서드에서 <xref:System.Timers.Timer> 구성 요소의 속성을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="3a603-151">Set the properties of the <xref:System.Timers.Timer> component in the `MyNewService.OnStart` method.</span></span>
- <span data-ttu-id="3a603-152"><xref:System.Timers.Timer.Start%2A> 메서드를 호출하여 타이머를 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="3a603-152">Start the timer by calling the <xref:System.Timers.Timer.Start%2A> method.</span></span>

##### <a name="set-up-the-polling-mechanism"></a><span data-ttu-id="3a603-153">폴링 메커니즘을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="3a603-153">Set up the polling mechanism.</span></span>

1. <span data-ttu-id="3a603-154">`MyNewService.OnStart` 이벤트에 다음 코드를 추가하여 폴링 메커니즘을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="3a603-154">Add the following code in the `MyNewService.OnStart` event to set up the polling mechanism:</span></span>

   ```csharp
   // Set up a timer that triggers every minute.
   Timer timer = new Timer();
   timer.Interval = 60000; // 60 seconds
   timer.Elapsed += new ElapsedEventHandler(this.OnTimer);
   timer.Start();
   ```

   ```vb
   ' Set up a timer that triggers every minute.
   Dim timer As Timer = New Timer()
   timer.Interval = 60000 ' 60 seconds
   AddHandler timer.Elapsed, AddressOf Me.OnTimer
   timer.Start()
   ```

2. <span data-ttu-id="3a603-155">`using` 문을 **MyNewService.cs**에 추가하거나 <xref:System.Timers?displayProperty=nameWithType> 네임스페이스에 대해서는 `Imports` 문을 **MyNewService.vb**에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="3a603-155">Add a `using` statement to **MyNewService.cs**, or an `Imports` statement to **MyNewService.vb**, for the <xref:System.Timers?displayProperty=nameWithType> namespace:</span></span>

   ```csharp
   using System.Timers;
   ```

   ```vb
   Imports System.Timers
   ```

3. <span data-ttu-id="3a603-156">`MyNewService` 클래스에서 `OnTimer` 메서드를 추가하여 <xref:System.Timers.Timer.Elapsed?displayProperty=nameWithType> 이벤트를 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="3a603-156">In the `MyNewService` class, add the `OnTimer` method to handle the <xref:System.Timers.Timer.Elapsed?displayProperty=nameWithType> event:</span></span>

   ```csharp
   public void OnTimer(object sender, ElapsedEventArgs args)
   {
       // TODO: Insert monitoring activities here.
       eventLog1.WriteEntry("Monitoring the System", EventLogEntryType.Information, eventId++);
   }
   ```

   ```vb
   Private Sub OnTimer(sender As Object, e As Timers.ElapsedEventArgs)
      ' TODO: Insert monitoring activities here.
      eventLog1.WriteEntry("Monitoring the System", EventLogEntryType.Information, eventId)
      eventId = eventId + 1
   End Sub
   ```

4. <span data-ttu-id="3a603-157">`MyNewService` 클래스에서 멤버 변수를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="3a603-157">In the `MyNewService` class, add a member variable.</span></span> <span data-ttu-id="3a603-158">여기에는 이벤트 로그에 기록할 다음 이벤트의 식별자가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="3a603-158">It contains the identifier of the next event to write into the event log:</span></span>

   ```csharp
   private int eventId = 1;
   ```

   ```vb
   Private eventId As Integer = 1
   ```

<span data-ttu-id="3a603-159">주 스레드에서 모든 작업을 실행하는 대신 백그라운드 작업자 스레드를 사용하여 작업을 실행할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3a603-159">Instead of running all your work on the main thread, you can run tasks by using background worker threads.</span></span> <span data-ttu-id="3a603-160">자세한 내용은 <xref:System.ComponentModel.BackgroundWorker?displayProperty=fullName>를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="3a603-160">For more information, see <xref:System.ComponentModel.BackgroundWorker?displayProperty=fullName>.</span></span>

### <a name="define-what-occurs-when-the-service-is-stopped"></a><span data-ttu-id="3a603-161">서비스가 중지될 때 수행되는 동작 정의</span><span class="sxs-lookup"><span data-stu-id="3a603-161">Define what occurs when the service is stopped</span></span>

<span data-ttu-id="3a603-162">서비스가 중지될 때 이벤트 로그에 항목을 추가하는 코드 줄을 <xref:System.ServiceProcess.ServiceBase.OnStop%2A> 메서드에 삽입합니다.</span><span class="sxs-lookup"><span data-stu-id="3a603-162">Insert a line of code in the <xref:System.ServiceProcess.ServiceBase.OnStop%2A> method that adds an entry to the event log when the service is stopped:</span></span>

[!code-csharp[VbRadconService#2](../../../samples/snippets/csharp/VS_Snippets_VBCSharp/VbRadconService/CS/MyNewService.cs#4)]
[!code-vb[VbRadconService#4](../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbRadconService/VB/MyNewService.vb#4)]

### <a name="define-other-actions-for-the-service"></a><span data-ttu-id="3a603-163">서비스의 다른 동작 정의</span><span class="sxs-lookup"><span data-stu-id="3a603-163">Define other actions for the service</span></span>

<span data-ttu-id="3a603-164"><xref:System.ServiceProcess.ServiceBase.OnPause%2A>, <xref:System.ServiceProcess.ServiceBase.OnContinue%2A> 및 <xref:System.ServiceProcess.ServiceBase.OnShutdown%2A> 메서드를 재정의하여 구성 요소에 대한 처리 작업을 추가로 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3a603-164">You can override the <xref:System.ServiceProcess.ServiceBase.OnPause%2A>, <xref:System.ServiceProcess.ServiceBase.OnContinue%2A>, and <xref:System.ServiceProcess.ServiceBase.OnShutdown%2A> methods to define additional processing for your component.</span></span>

<span data-ttu-id="3a603-165">다음 코드에서는 `MyNewService` 클래스에서 <xref:System.ServiceProcess.ServiceBase.OnContinue%2A> 메서드를 재정의하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="3a603-165">The following code shows how you to override the <xref:System.ServiceProcess.ServiceBase.OnContinue%2A> method in the `MyNewService` class:</span></span>

[!code-csharp[VbRadconService#5](../../../samples/snippets/csharp/VS_Snippets_VBCSharp/VbRadconService/CS/MyNewService.cs#5)]
[!code-vb[VbRadconService#5](../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbRadconService/VB/MyNewService.vb#5)]

## <a name="set-service-status"></a><span data-ttu-id="3a603-166">서비스 상태 설정</span><span class="sxs-lookup"><span data-stu-id="3a603-166">Set service status</span></span>

<span data-ttu-id="3a603-167">서비스는 [서비스 제어 관리자](/windows/desktop/Services/service-control-manager)에 상태를 보고합니다. 따라서 사용자는 서비스가 정상적으로 작동 중인지를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3a603-167">Services report their status to the [Service Control Manager](/windows/desktop/Services/service-control-manager) so that a user can tell whether a service is functioning correctly.</span></span> <span data-ttu-id="3a603-168">기본적으로 <xref:System.ServiceProcess.ServiceBase>에서 상속되는 서비스는 SERVICE_STOPPED, SERVICE_PAUSED 및 SERVICE_RUNNING을 포함하여 제한된 상태 설정 세트를 보고합니다.</span><span class="sxs-lookup"><span data-stu-id="3a603-168">By default, a service that inherits from <xref:System.ServiceProcess.ServiceBase> reports a limited set of status settings, which include SERVICE_STOPPED, SERVICE_PAUSED, and SERVICE_RUNNING.</span></span> <span data-ttu-id="3a603-169">서비스를 시작하는 데 시간이 걸리는 경우에는 SERVICE_START_PENDING 상태를 보고하면 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3a603-169">If a service takes a while to start up, it's useful to report a SERVICE_START_PENDING status.</span></span>

<span data-ttu-id="3a603-170">또한 Windows [SetServiceStatus](/windows/desktop/api/winsvc/nf-winsvc-setservicestatus) 함수를 호출하는 코드를 추가하여 SERVICE_START_PENDING 및 SERVICE_STOP_PENDING 상태 설정을 구현할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3a603-170">You can implement the SERVICE_START_PENDING and SERVICE_STOP_PENDING status settings by adding code that calls the Windows [SetServiceStatus](/windows/desktop/api/winsvc/nf-winsvc-setservicestatus) function.</span></span>

### <a name="implement-service-pending-status"></a><span data-ttu-id="3a603-171">서비스 보류 중 상태 구현</span><span class="sxs-lookup"><span data-stu-id="3a603-171">Implement service pending status</span></span>

1. <span data-ttu-id="3a603-172">`using` 문을 **MyNewService.cs**에 추가하거나 <xref:System.Runtime.InteropServices?displayProperty=nameWithType> 네임스페이스에 대해서는 `Imports` 문을 **MyNewService.vb**에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="3a603-172">Add a `using` statement to **MyNewService.cs**, or an `Imports` statement to **MyNewService.vb**, for the <xref:System.Runtime.InteropServices?displayProperty=nameWithType> namespace:</span></span>

    ```csharp
    using System.Runtime.InteropServices;
    ```

    ```vb
    Imports System.Runtime.InteropServices
    ```

2. <span data-ttu-id="3a603-173">`ServiceState` 값을 선언하고 상태에 대한 구조(플랫폼 호출에서 사용함)를 추가하려면 **MyNewService.cs** 또는 **MyNewService.vb**에 다음 코드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="3a603-173">Add the following code to **MyNewService.cs**, or **MyNewService.vb**, to declare the `ServiceState` values and to add a structure for the status, which you'll use in a platform invoke call:</span></span>

    ```csharp
    public enum ServiceState
    {
        SERVICE_STOPPED = 0x00000001,
        SERVICE_START_PENDING = 0x00000002,
        SERVICE_STOP_PENDING = 0x00000003,
        SERVICE_RUNNING = 0x00000004,
        SERVICE_CONTINUE_PENDING = 0x00000005,
        SERVICE_PAUSE_PENDING = 0x00000006,
        SERVICE_PAUSED = 0x00000007,
    }

    [StructLayout(LayoutKind.Sequential)]
    public struct ServiceStatus
    {
        public int dwServiceType;
        public ServiceState dwCurrentState;
        public int dwControlsAccepted;
        public int dwWin32ExitCode;
        public int dwServiceSpecificExitCode;
        public int dwCheckPoint;
        public int dwWaitHint;
    };
    ```

    ```vb
    Public Enum ServiceState
        SERVICE_STOPPED = 1
        SERVICE_START_PENDING = 2
        SERVICE_STOP_PENDING = 3
        SERVICE_RUNNING = 4
        SERVICE_CONTINUE_PENDING = 5
        SERVICE_PAUSE_PENDING = 6
        SERVICE_PAUSED = 7
    End Enum

    <StructLayout(LayoutKind.Sequential)>
    Public Structure ServiceStatus
        Public dwServiceType As Long
        Public dwCurrentState As ServiceState
        Public dwControlsAccepted As Long
        Public dwWin32ExitCode As Long
        Public dwServiceSpecificExitCode As Long
        Public dwCheckPoint As Long
        Public dwWaitHint As Long
    End Structure
    ```

    > [!NOTE]
    > <span data-ttu-id="3a603-174">서비스 제어 관리자는 [SERVICE_STATUS 구조체](/windows/win32/api/winsvc/ns-winsvc-service_status)의 `dwWaitHint` 및 `dwCheckpoint` 멤버를 사용하여 Windows 서비스가 시작 또는 종료될 때까지 기다릴 시간을 결정합니다.</span><span class="sxs-lookup"><span data-stu-id="3a603-174">The Service Control Manager uses the `dwWaitHint` and `dwCheckpoint` members of the [SERVICE_STATUS structure](/windows/win32/api/winsvc/ns-winsvc-service_status) to determine how much time to wait for a Windows service to start or shut down.</span></span> <span data-ttu-id="3a603-175">`OnStart` 및 `OnStop` 메서드가 오랫동안 실행되는 경우 서비스는 증분된 `dwCheckPoint` 값을 포함하여 `SetServiceStatus`을(를) 다시 호출하여 시간을 더 요청할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3a603-175">If your `OnStart` and `OnStop` methods run long, your service can request more time by calling `SetServiceStatus` again with an incremented `dwCheckPoint` value.</span></span>

3. <span data-ttu-id="3a603-176">`MyNewService` 클래스에서 [플랫폼 호출](../interop/consuming-unmanaged-dll-functions.md)을 사용하여 [SetServiceStatus](/windows/desktop/api/winsvc/nf-winsvc-setservicestatus) 함수를 선언합니다.</span><span class="sxs-lookup"><span data-stu-id="3a603-176">In the `MyNewService` class, declare the [SetServiceStatus](/windows/desktop/api/winsvc/nf-winsvc-setservicestatus) function by using [platform invoke](../interop/consuming-unmanaged-dll-functions.md):</span></span>

    ```csharp
    [DllImport("advapi32.dll", SetLastError = true)]
    private static extern bool SetServiceStatus(System.IntPtr handle, ref ServiceStatus serviceStatus);
    ```

    ```vb
    Declare Auto Function SetServiceStatus Lib "advapi32.dll" (ByVal handle As IntPtr, ByRef serviceStatus As ServiceStatus) As Boolean
    ```

4. <span data-ttu-id="3a603-177">SERVICE_START_PENDING 상태를 구현하려면 <xref:System.ServiceProcess.ServiceBase.OnStart%2A> 메서드 시작 부분에 다음 코드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="3a603-177">To implement the SERVICE_START_PENDING status, add the following code to the beginning of the <xref:System.ServiceProcess.ServiceBase.OnStart%2A> method:</span></span>

    ```csharp
    // Update the service state to Start Pending.
    ServiceStatus serviceStatus = new ServiceStatus();
    serviceStatus.dwCurrentState = ServiceState.SERVICE_START_PENDING;
    serviceStatus.dwWaitHint = 100000;
    SetServiceStatus(this.ServiceHandle, ref serviceStatus);
    ```

    ```vb
    ' Update the service state to Start Pending.
    Dim serviceStatus As ServiceStatus = New ServiceStatus()
    serviceStatus.dwCurrentState = ServiceState.SERVICE_START_PENDING
    serviceStatus.dwWaitHint = 100000
    SetServiceStatus(Me.ServiceHandle, serviceStatus)
    ```

5. <span data-ttu-id="3a603-178">상태를 SERVICE_RUNNING으로 설정하려면 `OnStart` 메서드 끝에 코드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="3a603-178">Add code to the end of the `OnStart` method to set the status to SERVICE_RUNNING:</span></span>

    ```csharp
    // Update the service state to Running.
    serviceStatus.dwCurrentState = ServiceState.SERVICE_RUNNING;
    SetServiceStatus(this.ServiceHandle, ref serviceStatus);
    ```

    ```vb
    ' Update the service state to Running.
    serviceStatus.dwCurrentState = ServiceState.SERVICE_RUNNING
    SetServiceStatus(Me.ServiceHandle, serviceStatus)
    ```

6. <span data-ttu-id="3a603-179">(선택 사항) <xref:System.ServiceProcess.ServiceBase.OnStop%2A> 메서드가 장기 실행 메서드인 경우 `OnStop` 메서드에서 이 절차를 반복합니다.</span><span class="sxs-lookup"><span data-stu-id="3a603-179">(Optional) If <xref:System.ServiceProcess.ServiceBase.OnStop%2A> is a long-running method, repeat this procedure in the `OnStop` method.</span></span> <span data-ttu-id="3a603-180">SERVICE_STOP_PENDING 상태를 구현하고 `OnStop` 메서드가 끝나기 전에 SERVICE_STOPPED 상태를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="3a603-180">Implement the SERVICE_STOP_PENDING status and return the SERVICE_STOPPED status before the `OnStop` method exits.</span></span>

   <span data-ttu-id="3a603-181">예를 들어:</span><span class="sxs-lookup"><span data-stu-id="3a603-181">For example:</span></span>

    ```csharp
    // Update the service state to Stop Pending.
    ServiceStatus serviceStatus = new ServiceStatus();
    serviceStatus.dwCurrentState = ServiceState.SERVICE_STOP_PENDING;
    serviceStatus.dwWaitHint = 100000;
    SetServiceStatus(this.ServiceHandle, ref serviceStatus);

    // Update the service state to Stopped.
    serviceStatus.dwCurrentState = ServiceState.SERVICE_STOPPED;
    SetServiceStatus(this.ServiceHandle, ref serviceStatus);
    ```

    ```vb
    ' Update the service state to Stop Pending.
    Dim serviceStatus As ServiceStatus = New ServiceStatus()
    serviceStatus.dwCurrentState = ServiceState.SERVICE_STOP_PENDING
    serviceStatus.dwWaitHint = 100000
    SetServiceStatus(Me.ServiceHandle, serviceStatus)

    ' Update the service state to Stopped.
    serviceStatus.dwCurrentState = ServiceState.SERVICE_STOPPED
    SetServiceStatus(Me.ServiceHandle, serviceStatus)
    ```

## <a name="add-installers-to-the-service"></a><span data-ttu-id="3a603-182">서비스에 설치 관리자 추가</span><span class="sxs-lookup"><span data-stu-id="3a603-182">Add installers to the service</span></span>

<span data-ttu-id="3a603-183">Windows 서비스를 실행하려면 해당 서비스를 설치해야 합니다. 그러면 서비스 제어 관리자에 서비스가 등록됩니다.</span><span class="sxs-lookup"><span data-stu-id="3a603-183">Before you run a Windows service, you need to install it, which registers it with the Service Control Manager.</span></span> <span data-ttu-id="3a603-184">등록 정보를 처리하는 설치 관리자를 프로젝트에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="3a603-184">Add installers to your project to handle the registration details.</span></span>

1. <span data-ttu-id="3a603-185">**솔루션 탐색기**에서 **MyNewService.cs** 또는 **MyNewService.vb**의 바로 가기 메뉴에 있는 **뷰 디자이너**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="3a603-185">In **Solution Explorer**, from the shortcut menu for **MyNewService.cs**, or **MyNewService.vb**, choose **View Designer**.</span></span>

2. <span data-ttu-id="3a603-186">**디자인** 뷰에서 백그라운드 영역을 선택한 다음, 바로 가기 메뉴에서 **설치 관리자 추가**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="3a603-186">In the **Design** view, select the background area, then choose **Add Installer** from the shortcut menu.</span></span>

     <span data-ttu-id="3a603-187">기본적으로 Visual Studio는 이름이 `ProjectInstaller`인 구성 요소 클래스를 추가하고 여기에는 프로젝트에 대한 두 개의 설치 관리자가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3a603-187">By default, Visual Studio adds a component class named `ProjectInstaller`, which contains two installers, to your project.</span></span> <span data-ttu-id="3a603-188">이러한 설치 관리자는 서비스 및 서비스에 연결된 프로세스에 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="3a603-188">These installers are for your service and for the service's associated process.</span></span>

3. <span data-ttu-id="3a603-189">**ProjectInstaller**의 **디자인**뷰에서 Visual C# 프로젝트의 경우 **serviceInstaller1**을 선택하고 Visual Basic 프로젝트의 경우 **ServiceInstaller1**을 선택한 다음, 바로 가기 메뉴에서 **속성**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="3a603-189">In the **Design** view for **ProjectInstaller**, select **serviceInstaller1** for a Visual C# project, or **ServiceInstaller1** for a Visual Basic project, then choose **Properties** from the shortcut menu.</span></span>

4. <span data-ttu-id="3a603-190">**속성** 창에서 <xref:System.ServiceProcess.ServiceInstaller.ServiceName%2A> 속성이 **MyNewService**로 설정되어 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="3a603-190">In the **Properties** window, verify the <xref:System.ServiceProcess.ServiceInstaller.ServiceName%2A> property is set to **MyNewService**.</span></span>

5. <span data-ttu-id="3a603-191"><xref:System.ServiceProcess.ServiceInstaller.Description%2A> 속성에 *샘플 서비스*와 같은 텍스트를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="3a603-191">Add text to the <xref:System.ServiceProcess.ServiceInstaller.Description%2A> property, such as *A sample service*.</span></span>

     <span data-ttu-id="3a603-192">이 텍스트는 **서비스** 창의 **설명** 열에 표시되어 사용자에게 서비스를 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="3a603-192">This text appears in the **Description** column of the **Services** window and describes the service to the user.</span></span>

    <span data-ttu-id="3a603-193">![서비스 창의 서비스 설명입니다.](./media/windows-service-description.png "서비스 설명")</span><span class="sxs-lookup"><span data-stu-id="3a603-193">![Service description in the Services window.](./media/windows-service-description.png "Service description")</span></span>

6. <span data-ttu-id="3a603-194"><xref:System.ServiceProcess.ServiceInstaller.DisplayName%2A> 속성에 텍스트를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="3a603-194">Add text to the <xref:System.ServiceProcess.ServiceInstaller.DisplayName%2A> property.</span></span> <span data-ttu-id="3a603-195">예를 들어 *MyNewService 표시 이름*을 입력할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3a603-195">For example, *MyNewService Display Name*.</span></span>

     <span data-ttu-id="3a603-196">이 텍스트는 **서비스** 창의 **표시 이름** 열에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="3a603-196">This text appears in the **Display Name** column of the **Services** window.</span></span> <span data-ttu-id="3a603-197">이 이름은 시스템에서 사용하는 이름인 <xref:System.ServiceProcess.ServiceInstaller.ServiceName%2A> 속성과 다를 수 있습니다(예: 시스템을 시작하는 `net start` 명령에 사용하는 이름).</span><span class="sxs-lookup"><span data-stu-id="3a603-197">This name can be different from the <xref:System.ServiceProcess.ServiceInstaller.ServiceName%2A> property, which is the name the system uses (for example, the name you use for the `net start` command to start your service).</span></span>

7. <span data-ttu-id="3a603-198">드롭 다운 목록에서 <xref:System.ServiceProcess.ServiceInstaller.StartType%2A> 속성을 <xref:System.ServiceProcess.ServiceStartMode.Automatic>(으)로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="3a603-198">Set the <xref:System.ServiceProcess.ServiceInstaller.StartType%2A> property to <xref:System.ServiceProcess.ServiceStartMode.Automatic> from the drop-down list.</span></span>

8. <span data-ttu-id="3a603-199">완료되면 **속성** 창이 다름 그림과 같아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3a603-199">When you're finished, the **Properties** windows should look like the following figure:</span></span>

     <span data-ttu-id="3a603-200">![Windows 서비스의 설치 관리자 속성](./media/windows-service-installer-properties.png "Windows 서비스 설치 관리자 속성")</span><span class="sxs-lookup"><span data-stu-id="3a603-200">![Installer Properties for a Windows service](./media/windows-service-installer-properties.png "Windows service installer properties")</span></span>

9. <span data-ttu-id="3a603-201">**ProjectInstaller**의 **디자인**뷰에서 Visual C# 프로젝트의 경우 **serviceProcessInstaller1**을 선택하고 Visual Basic 프로젝트의 경우 **ServiceProcessInstaller1**을 선택한 다음, 바로 가기 메뉴에서 **속성**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="3a603-201">In the **Design** view for **ProjectInstaller**, choose **serviceProcessInstaller1** for a Visual C# project, or **ServiceProcessInstaller1** for a Visual Basic project, then choose **Properties** from the shortcut menu.</span></span> <span data-ttu-id="3a603-202">드롭 다운 목록에서 <xref:System.ServiceProcess.ServiceProcessInstaller.Account%2A> 속성을 <xref:System.ServiceProcess.ServiceAccount.LocalSystem>(으)로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="3a603-202">Set the <xref:System.ServiceProcess.ServiceProcessInstaller.Account%2A> property to <xref:System.ServiceProcess.ServiceAccount.LocalSystem> from the drop-down list.</span></span>

     <span data-ttu-id="3a603-203">이 설정은 서비스를 설치하고 로컬 시스템 계정을 사용하여 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="3a603-203">This setting installs the service and runs it by using the local system account.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="3a603-204"><xref:System.ServiceProcess.ServiceAccount.LocalSystem> 계정에는 광범위한 권한이 있습니다. 예를 들어, 이 계정은 이벤트 로그에 쓸 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3a603-204">The <xref:System.ServiceProcess.ServiceAccount.LocalSystem> account has broad permissions, including the ability to write to the event log.</span></span> <span data-ttu-id="3a603-205">이 계정을 사용할 때는 악성 소프트웨어의 공격을 받을 가능성이 커지므로 주의해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3a603-205">Use this account with caution, because it might increase your risk of attacks from malicious software.</span></span> <span data-ttu-id="3a603-206">다른 작업에는 <xref:System.ServiceProcess.ServiceAccount.LocalService> 계정을 사용하는 것이 좋습니다. 이 계정은 로컬 컴퓨터에서 권한 없는 사용자의 역할을 하며 원격 서버에 익명 자격 증명을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="3a603-206">For other tasks, consider using the <xref:System.ServiceProcess.ServiceAccount.LocalService> account, which acts as a non-privileged user on the local computer and presents anonymous credentials to any remote server.</span></span> <span data-ttu-id="3a603-207"><xref:System.ServiceProcess.ServiceAccount.LocalService> 계정을 사용하는 경우 이 예제는 실패합니다. 이벤트 로그에 대한 쓰기 권한이 필요하기 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="3a603-207">This example fails if you try to use the <xref:System.ServiceProcess.ServiceAccount.LocalService> account, because it needs permission to write to the event log.</span></span>

<span data-ttu-id="3a603-208">설치 관리자에 대한 자세한 내용은 [방법: 서비스 애플리케이션에 설치 관리자 추가](how-to-add-installers-to-your-service-application.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="3a603-208">For more information about installers, see [How to: Add installers to your service application](how-to-add-installers-to-your-service-application.md).</span></span>

## <a name="optional-set-startup-parameters"></a><span data-ttu-id="3a603-209">(선택 사항) 시작 매개 변수 설정</span><span class="sxs-lookup"><span data-stu-id="3a603-209">(Optional) Set startup parameters</span></span>

> [!NOTE]
> <span data-ttu-id="3a603-210">시작 매개 변수 추가를 결정하기 전에 시작 매개 변수가 서비스로 정보를 전달하는 가장 효율적인 방법인지를 고려합니다.</span><span class="sxs-lookup"><span data-stu-id="3a603-210">Before you decide to add startup parameters, consider whether it's the best way to pass information to your service.</span></span> <span data-ttu-id="3a603-211">시작 매개 변수는 쉽게 사용하고 구문 분석할 수 있으며 사용자가 쉽게 재정의할 수 있지만 설명서가 없으면 사용자가 검색하고 사용하기가 어려울 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3a603-211">Although they're easy to use and parse, and a user can easily override them, they might be harder for a user to discover and use without documentation.</span></span> <span data-ttu-id="3a603-212">일반적으로 서비스에 많은 시작 매개 변수가 필요한 경우에는 레지스트리나 구성 파일을 대신 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3a603-212">Generally, if your service requires more than just a few startup parameters, you should use the registry or a configuration file instead.</span></span>

<span data-ttu-id="3a603-213">Windows 서비스에는 명령줄 인수나 시작 매개 변수를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3a603-213">A Windows service can accept command-line arguments, or startup parameters.</span></span> <span data-ttu-id="3a603-214">프로세스 시작 매개 변수에 코드를 추가하면 사용자가 서비스 속성 창에서 고유한 사용자 지정 시작 매개 변수로 서비스를 시작할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3a603-214">When you add code to process startup parameters, a user can start your service with their own custom startup parameters in the service properties window.</span></span> <span data-ttu-id="3a603-215">그러나 이러한 시작 매개 변수는 다음 번에 서비스를 시작할 때 유지되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="3a603-215">However, these startup parameters aren't persisted the next time the service starts.</span></span> <span data-ttu-id="3a603-216">시작 매개 변수를 영구적으로 설정하려면 레지스트리에서 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="3a603-216">To set startup parameters permanently, set them in the registry.</span></span>

<span data-ttu-id="3a603-217">각 Windows 서비스에는 **HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Services** 하위 키에 레지스트리 항목이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3a603-217">Each Windows service has a registry entry under the **HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Services** subkey.</span></span> <span data-ttu-id="3a603-218">각 서비스의 하위 키 아래에서 **매개 변수** 하위 키를 사용하여 서비스가 액세스할 수 있는 정보를 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="3a603-218">Under each service's subkey, use the **Parameters** subkey to store information that your service can access.</span></span> <span data-ttu-id="3a603-219">Windows 서비스의 애플리케이션 구성 파일은 다른 프로그램 형식에서와 같은 방식으로 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3a603-219">You can use application configuration files for a Windows service the same way you do for other types of programs.</span></span> <span data-ttu-id="3a603-220">샘플 코드는 <xref:System.Configuration.ConfigurationManager.AppSettings?displayProperty=nameWithType>을(를) 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="3a603-220">For sample code, see <xref:System.Configuration.ConfigurationManager.AppSettings?displayProperty=nameWithType>.</span></span>

### <a name="to-add-startup-parameters"></a><span data-ttu-id="3a603-221">시작 매개 변수를 추가하려면</span><span class="sxs-lookup"><span data-stu-id="3a603-221">To add startup parameters</span></span>

1. <span data-ttu-id="3a603-222">**Program.cs** 또는 **MyNewService.Designer.vb**를 선택한 다음, 바로 가기 메뉴에서 **코드 보기**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="3a603-222">Select **Program.cs**, or **MyNewService.Designer.vb**, then choose **View Code** from the shortcut menu.</span></span> <span data-ttu-id="3a603-223">`Main` 메서드에서 코드를 변경해 입력 매개 변수를 추가하고 서비스 생성자에게 전달합니다.</span><span class="sxs-lookup"><span data-stu-id="3a603-223">In the `Main` method, change the code to add an input parameter and pass it to the service constructor:</span></span>

   [!code-csharp[VbRadconService](../../../samples/snippets/csharp/VS_Snippets_VBCSharp/VbRadconService/CS/Program-add-parameter.cs?highlight=1,6)]
   [!code-vb[VbRadconService](../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbRadconService/VB/MyNewService.Designer-add-parameter.vb?highlight=1-2)]

2. <span data-ttu-id="3a603-224">**MyNewService.cs** 또는 **MyNewService.vb**에서 `MyNewService` 생성자를 변경하여 입력 매개 변수를 다름과 같이 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="3a603-224">In **MyNewService.cs**, or **MyNewService.vb**, change the `MyNewService` constructor to process the input parameter as follows:</span></span>

   ```csharp
   using System.Diagnostics;

   public MyNewService(string[] args)
   {
       InitializeComponent();

       string eventSourceName = "MySource";
       string logName = "MyNewLog";

       if (args.Length > 0)
       {
          eventSourceName = args[0];
       }

       if (args.Length > 1)
       {
           logName = args[1];
       }

       eventLog1 = new EventLog();

       if (!EventLog.SourceExists(eventSourceName))
       {
           EventLog.CreateEventSource(eventSourceName, logName);
       }

       eventLog1.Source = eventSourceName;
       eventLog1.Log = logName;
   }
   ```

   ```vb
   Imports System.Diagnostics

   Public Sub New(ByVal cmdArgs() As String)
       InitializeComponent()
       Dim eventSourceName As String = "MySource"
       Dim logName As String = "MyNewLog"
       If (cmdArgs.Count() > 0) Then
           eventSourceName = cmdArgs(0)
       End If
       If (cmdArgs.Count() > 1) Then
           logName = cmdArgs(1)
       End If
       eventLog1 = New EventLog()
       If (Not EventLog.SourceExists(eventSourceName)) Then
           EventLog.CreateEventSource(eventSourceName, logName)
       End If
       eventLog1.Source = eventSourceName
       eventLog1.Log = logName
   End Sub
   ```

   <span data-ttu-id="3a603-225">이 코드는 사용자가 제공하는 시작 매개 변수에 따라 이벤트 소스와 로그 이름을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="3a603-225">This code sets the event source and log name according to the startup parameters that the user supplies.</span></span> <span data-ttu-id="3a603-226">인수가 제공되지 않으면 기본값이 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="3a603-226">If no arguments are supplied, it uses default values.</span></span>

3. <span data-ttu-id="3a603-227">명령줄 인수를 지정하려면 **ProjectInstaller.cs** 또는 **ProjectInstaller.vb**의 `ProjectInstaller` 클래스에 다음 코드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="3a603-227">To specify the command-line arguments, add the following code to the `ProjectInstaller` class in **ProjectInstaller.cs**, or **ProjectInstaller.vb**:</span></span>

   ```csharp
   protected override void OnBeforeInstall(IDictionary savedState)
   {
       string parameter = "MySource1\" \"MyLogFile1";
       Context.Parameters["assemblypath"] = "\"" + Context.Parameters["assemblypath"] + "\" \"" + parameter + "\"";
       base.OnBeforeInstall(savedState);
   }
   ```

   ```vb
   Protected Overrides Sub OnBeforeInstall(ByVal savedState As IDictionary)
       Dim parameter As String = "MySource1"" ""MyLogFile1"
       Context.Parameters("assemblypath") = """" + Context.Parameters("assemblypath") + """ """ + parameter + """"
       MyBase.OnBeforeInstall(savedState)
   End Sub
   ```

   <span data-ttu-id="3a603-228">일반적으로 이 값에는 Windows 서비스에 대한 실행 파일의 전체 경로가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="3a603-228">Typically, this value contains the full path to the executable for the Windows service.</span></span> <span data-ttu-id="3a603-229">서비스를 올바르게 시작하려면 사용자는 경로와 개별 매개 변수에 따옴표를 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3a603-229">For the service to start up correctly, the user must supply quotation marks for the path and each individual parameter.</span></span> <span data-ttu-id="3a603-230">사용자는 **ImagePath** 레지스트리 항목에서 매개 변수를 변경하여 Windows 서비스에 대한 시작 매개 변수를 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3a603-230">A user can change the parameters in the **ImagePath** registry entry to change the startup parameters for the Windows service.</span></span> <span data-ttu-id="3a603-231">그러나 프로그래밍 방식으로 값을 변경하고 관리 또는 구성 유틸리티를 사용하는 것과 같이 사용자에게 익숙한 방식으로 기능을 노출시키는 것이 더 나은 방식입니다.</span><span class="sxs-lookup"><span data-stu-id="3a603-231">However, a better way is to change the value programmatically and expose the functionality in a user-friendly way, such as by using a management or configuration utility.</span></span>

## <a name="build-the-service"></a><span data-ttu-id="3a603-232">서비스 빌드</span><span class="sxs-lookup"><span data-stu-id="3a603-232">Build the service</span></span>

1. <span data-ttu-id="3a603-233">**솔루션 탐색기**에 있는 **MyNewService** 프로젝트의 바로 가기 메뉴에서 **속성**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="3a603-233">In **Solution Explorer**, choose **Properties** from the shortcut menu for the **MyNewService** project.</span></span>

   <span data-ttu-id="3a603-234">프로젝트의 속성 페이지가 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="3a603-234">The property pages for your project appear.</span></span>

2. <span data-ttu-id="3a603-235">**애플리케이션** 탭의 **시작 개체** 목록에서 **MyNewService.Program**을 선택하거나 Visual Basic 프로젝트의 **Sub Main**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="3a603-235">On the **Application** tab, in the **Startup object** list, choose **MyNewService.Program**, or **Sub Main** for Visual Basic projects.</span></span>

3. <span data-ttu-id="3a603-236">프로젝트를 빌드하려면 **솔루션 탐색기**를 열고 프로젝트의 바로 가기 메뉴에 있는 **빌드**를 선택합니다(또는 **Ctrl**+**Shift**+**B**를 누름).</span><span class="sxs-lookup"><span data-stu-id="3a603-236">To build the project, in **Solution Explorer**, choose **Build** from the shortcut menu for your project (or press **Ctrl**+**Shift**+**B**).</span></span>

## <a name="install-the-service"></a><span data-ttu-id="3a603-237">서비스 설치</span><span class="sxs-lookup"><span data-stu-id="3a603-237">Install the service</span></span>

<span data-ttu-id="3a603-238">이제 Windows 서비스를 빌드했으므로 이를 설치할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3a603-238">Now that you've built the Windows service, you can install it.</span></span> <span data-ttu-id="3a603-239">Windows 서비스를 설치하려면 설치할 컴퓨터에서 관리자 자격 증명이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3a603-239">To install a Windows service, you must have administrator credentials on the computer where it's installed.</span></span>

1. <span data-ttu-id="3a603-240">관리자 자격 증명을 사용하여 [Visual Studio에 대한 개발자 명령 프롬프트](../tools/developer-command-prompt-for-vs.md)를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="3a603-240">Open [Developer Command Prompt for Visual Studio](../tools/developer-command-prompt-for-vs.md) with administrative credentials.</span></span> <span data-ttu-id="3a603-241">Windows **시작** 메뉴에서 Visual Studio 폴더에 있는 **VS 2017에 대한 개발자 명령 프롬프트**를 선택한 다음, 바로 가기 메뉴에서 **자세히** > **관리자로 실행**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="3a603-241">From the Windows **Start** menu, select **Developer Command Prompt for VS 2017** in the Visual Studio folder, then select **More** > **Run as Administrator** from the shortcut menu.</span></span>

2. <span data-ttu-id="3a603-242">**Visual Studio에 대한 개발자 명령 프롬프트** 창에서 프로젝트의 출력이 포함된 폴더(기본적으로 프로젝트의 *\bin\Debug* 하위 디렉터리)로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="3a603-242">In the **Developer Command Prompt for Visual Studio** window, navigate to the folder that contains your project's output (by default, the *\bin\Debug* subdirectory of your project).</span></span>

3. <span data-ttu-id="3a603-243">다음 명령을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="3a603-243">Enter the following command:</span></span>

    ```shell
    installutil MyNewService.exe
    ```

    <span data-ttu-id="3a603-244">서비스를 성공적으로 설치한 경우 명령이 설치에 성공했음을 보고합니다.</span><span class="sxs-lookup"><span data-stu-id="3a603-244">If the service installs successfully, the command reports success.</span></span>

    <span data-ttu-id="3a603-245">시스템에서 *installutil.exe*를 찾을 수 없는 경우 해당 파일이 컴퓨터에 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="3a603-245">If the system can't find *installutil.exe*, make sure that it exists on your computer.</span></span> <span data-ttu-id="3a603-246">이 도구는 *%windir%\Microsoft.NET\Framework[64]\\&lt;프레임워크 버전&gt;* 폴더에 .NET Framework와 함께 설치됩니다.</span><span class="sxs-lookup"><span data-stu-id="3a603-246">This tool is installed with the .NET Framework to the folder *%windir%\Microsoft.NET\Framework[64]\\&lt;framework version&gt;*.</span></span> <span data-ttu-id="3a603-247">예를 들어 64비트 버전의 기본 경로는 *%windir%\Microsoft.NET\Framework64\v4.0.30319\InstallUtil.exe*입니다.</span><span class="sxs-lookup"><span data-stu-id="3a603-247">For example, the default path for the 64-bit version is *%windir%\Microsoft.NET\Framework64\v4.0.30319\InstallUtil.exe*.</span></span>

    <span data-ttu-id="3a603-248">**installutil.exe** 프로세스가 실패한 경우 설치 로그를 확인하여 이유를 찾아보세요.</span><span class="sxs-lookup"><span data-stu-id="3a603-248">If the **installutil.exe** process fails, check the install log to find out why.</span></span> <span data-ttu-id="3a603-249">기본적으로 로그는 서비스 실행 파일과 동일한 폴더에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3a603-249">By default, the log is in the same folder as the service executable.</span></span> <span data-ttu-id="3a603-250">다음과 같은 경우 설치에 실패할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3a603-250">The installation can fail if:</span></span>
    - <span data-ttu-id="3a603-251"><xref:System.ComponentModel.RunInstallerAttribute> 클래스가 `ProjectInstaller` 클래스에 없습니다.</span><span class="sxs-lookup"><span data-stu-id="3a603-251">The <xref:System.ComponentModel.RunInstallerAttribute> class isn't present on the `ProjectInstaller` class.</span></span>
    - <span data-ttu-id="3a603-252">특성이 `true`(으)로 설정되지 않았습니다.</span><span class="sxs-lookup"><span data-stu-id="3a603-252">The attribute isn't set to `true`.</span></span>
    - <span data-ttu-id="3a603-253">`ProjectInstaller` 클래스가 `public`(으)로 정의되지 않았습니다.</span><span class="sxs-lookup"><span data-stu-id="3a603-253">The `ProjectInstaller` class isn't defined as `public`.</span></span>

<span data-ttu-id="3a603-254">자세한 내용은 [방법: 서비스 설치 및 제거](how-to-install-and-uninstall-services.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="3a603-254">For more information, see [How to: Install and uninstall services](how-to-install-and-uninstall-services.md).</span></span>

## <a name="start-and-run-the-service"></a><span data-ttu-id="3a603-255">서비스 시작 및 실행</span><span class="sxs-lookup"><span data-stu-id="3a603-255">Start and run the service</span></span>

1. <span data-ttu-id="3a603-256">Windows에서 **서비스** 데스크톱 앱을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="3a603-256">In Windows, open the **Services** desktop app.</span></span> <span data-ttu-id="3a603-257">**Windows**+**R**을 눌러 **실행** 상자를 열고 *services.msc*를 입력한 다음, **Enter** 키를 누르거나 **확인**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="3a603-257">Press **Windows**+**R** to open the **Run** box, enter *services.msc*, and then press **Enter** or select **OK**.</span></span>

     <span data-ttu-id="3a603-258">해당 서비스가 설정된 표시 이름의 사전순으로 **서비스**에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="3a603-258">You should see your service listed in **Services**, displayed alphabetically by the display name that you set for it.</span></span>

     ![서비스 창의 MyNewService입니다.](./media/windowsservices-serviceswindow.PNG)

2. <span data-ttu-id="3a603-260">서비스를 시작하려면 서비스의 바로 가기 메뉴에서 **시작**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="3a603-260">To start the service, choose **Start** from the service's shortcut menu.</span></span>

3. <span data-ttu-id="3a603-261">서비스를 중지하려면 서비스의 바로 가기 메뉴에서 **중지**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="3a603-261">To stop the service, choose **Stop** from the service's shortcut menu.</span></span>

4. <span data-ttu-id="3a603-262">(선택 사항) 명령줄에서 **net start &lt;서비스 이름&gt;** 및 **net stop &lt;서비스 이름&gt;** 명령을 사용하여 서비스를 시작하고 중지할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3a603-262">(Optional) From the command line, use the commands **net start &lt;service name&gt;** and **net stop &lt;service name&gt;** to start and stop your service.</span></span>

### <a name="verify-the-event-log-output-of-your-service"></a><span data-ttu-id="3a603-263">서비스의 이벤트 로그 출력 확인</span><span class="sxs-lookup"><span data-stu-id="3a603-263">Verify the event log output of your service</span></span>

1. <span data-ttu-id="3a603-264">Windows에서 **이벤트 뷰어** 데스크톱 앱을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="3a603-264">In Windows, open the **Event Viewer** desktop app.</span></span> <span data-ttu-id="3a603-265">Windows 검색 창에서 *이벤트 뷰어*를 입력한 다음, 검색 결과에서 **이벤트 뷰어**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="3a603-265">Enter *Event Viewer* in the Windows search bar, and then select **Event Viewer** from the search results.</span></span>

   > [!TIP]
   > <span data-ttu-id="3a603-266">Visual Studio의 **보기** 메뉴에서 **서버 탐색기**를 열고(또는 **Ctrl**+**Alt**+**S**를 누름) 로컬 컴퓨터의 **이벤트 로그** 노드를 확장하면 이벤트 로그에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3a603-266">In Visual Studio, you can access event logs by opening **Server Explorer** from the **View** menu (or press **Ctrl**+**Alt**+**S**) and expanding the **Event Logs** node for the local computer.</span></span>

2. <span data-ttu-id="3a603-267">**이벤트 뷰어**에서 **애플리케이션 및 서비스 로그**를 확장합니다.</span><span class="sxs-lookup"><span data-stu-id="3a603-267">In **Event Viewer**, expand **Applications and Services Logs**.</span></span>

3. <span data-ttu-id="3a603-268">**MyNewLog**(또는 절차에 따라 명령줄 인수를 추가한 경우 **MyLogFile1**)의 목록을 찾아서 확장합니다.</span><span class="sxs-lookup"><span data-stu-id="3a603-268">Locate the listing for **MyNewLog** (or **MyLogFile1** if you followed the procedure to add command-line arguments) and expand it.</span></span> <span data-ttu-id="3a603-269">서비스에서 수행한 두 작업(시작 및 중지)의 항목이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="3a603-269">You should see the entries for the two actions (start and stop) that your service performed.</span></span>

     ![이벤트 뷰어를 사용하여 이벤트 로그 항목 확인](./media/windows-service-event-viewer.png)

## <a name="clean-up-resources"></a><span data-ttu-id="3a603-271">리소스 정리</span><span class="sxs-lookup"><span data-stu-id="3a603-271">Clean up resources</span></span>

<span data-ttu-id="3a603-272">Windows 서비스 앱이 더 이상 필요 없는 경우 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3a603-272">If you no longer need the Windows service app, you can remove it.</span></span>

1. <span data-ttu-id="3a603-273">관리자 자격 증명을 사용하여 **Visual Studio에 대한 개발자 명령 프롬프트**를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="3a603-273">Open **Developer Command Prompt for Visual Studio** with administrative credentials.</span></span>

2. <span data-ttu-id="3a603-274">**Visual Studio에 대한 개발자 명령 프롬프트** 창에서 프로젝트의 출력이 포함된 폴더로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="3a603-274">In the **Developer Command Prompt for Visual Studio** window, navigate to the folder that contains your project's output.</span></span>

3. <span data-ttu-id="3a603-275">다음 명령을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="3a603-275">Enter the following command:</span></span>

    ```shell
    installutil.exe /u MyNewService.exe
    ```

   <span data-ttu-id="3a603-276">서비스를 성공적으로 제거한 경우 명령은 서비스가 성공적으로 제거되었음을 보고합니다.</span><span class="sxs-lookup"><span data-stu-id="3a603-276">If the service uninstalls successfully, the command reports that your service was successfully removed.</span></span> <span data-ttu-id="3a603-277">자세한 내용은 [방법: 서비스 설치 및 제거](how-to-install-and-uninstall-services.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="3a603-277">For more information, see [How to: Install and uninstall services](how-to-install-and-uninstall-services.md).</span></span>

## <a name="next-steps"></a><span data-ttu-id="3a603-278">다음 단계</span><span class="sxs-lookup"><span data-stu-id="3a603-278">Next steps</span></span>

<span data-ttu-id="3a603-279">이제 서비스를 만들었으므로 다음을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3a603-279">Now that you've created the service, you can:</span></span>

- <span data-ttu-id="3a603-280">다른 사용자가 Windows 서비스를 설치하는 데 사용하는 독립 실행형 설치 프로그램을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="3a603-280">Create a standalone setup program for others to use to install your Windows service.</span></span> <span data-ttu-id="3a603-281">[WiX 도구 집합](https://wixtoolset.org/)를 사용하여 Windows 서비스의 설치 관리자를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3a603-281">Use the [WiX Toolset](https://wixtoolset.org/) to create an installer for a Windows service.</span></span> <span data-ttu-id="3a603-282">다른 아이디어를 보려면 [설치 관리자 패키지 만들기](/visualstudio/deployment/deploying-applications-services-and-components#create-an-installer-package-windows-desktop)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="3a603-282">For other ideas, see [Create an installer package](/visualstudio/deployment/deploying-applications-services-and-components#create-an-installer-package-windows-desktop).</span></span>

- <span data-ttu-id="3a603-283">설치한 서비스에 명령을 보낼 수 있는 <xref:System.ServiceProcess.ServiceController> 구성 요소를 살펴보세요.</span><span class="sxs-lookup"><span data-stu-id="3a603-283">Explore the <xref:System.ServiceProcess.ServiceController> component, which enables you to send commands to the service you've installed.</span></span>

- <span data-ttu-id="3a603-284">애플리케이션이 실행될 때 이벤트 로그를 만드는 것보다는 애플리케이션이 설치될 때 설치 관리자를 사용하여 이벤트 로그를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="3a603-284">Instead of creating the event log when the application runs, use an installer to create an event log when you install the application.</span></span> <span data-ttu-id="3a603-285">애플리케이션을 제거하면 설치 관리자가 이벤트 로그를 삭제합니다.</span><span class="sxs-lookup"><span data-stu-id="3a603-285">The event log is deleted by the installer when you uninstall the application.</span></span> <span data-ttu-id="3a603-286">자세한 내용은 <xref:System.Diagnostics.EventLogInstaller>를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="3a603-286">For more information, see <xref:System.Diagnostics.EventLogInstaller>.</span></span>

## <a name="see-also"></a><span data-ttu-id="3a603-287">참조</span><span class="sxs-lookup"><span data-stu-id="3a603-287">See also</span></span>

- [<span data-ttu-id="3a603-288">Windows 서비스 애플리케이션</span><span class="sxs-lookup"><span data-stu-id="3a603-288">Windows service applications</span></span>](index.md)
- [<span data-ttu-id="3a603-289">Windows 서비스 애플리케이션 소개</span><span class="sxs-lookup"><span data-stu-id="3a603-289">Introduction to Windows service applications</span></span>](introduction-to-windows-service-applications.md)
- [<span data-ttu-id="3a603-290">방법: Windows 서비스 애플리케이션 디버그</span><span class="sxs-lookup"><span data-stu-id="3a603-290">How to: Debug Windows service applications</span></span>](how-to-debug-windows-service-applications.md)
- <span data-ttu-id="3a603-291">[Services (Windows)](/windows/desktop/Services/services)(서비스(Windows))</span><span class="sxs-lookup"><span data-stu-id="3a603-291">[Services (Windows)](/windows/desktop/Services/services)</span></span>
