---
title: '방법: 응용 프로그램 이벤트 로그에 쓰기'
ms.date: 07/20/2015
helpviewer_keywords:
- Computer.EventLog element
- WriteEntry method [Visual Basic]
- My.Computer.EventLog element
- event logs, writing to
ms.assetid: cadbc8c1-87af-4746-934e-55b79a4f6e2b
ms.openlocfilehash: 511bb8fb16851872c1a16ae7627ed0fc6594337c
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/15/2020
ms.locfileid: "74352043"
---
# <a name="how-to-write-to-an-application-event-log-visual-basic"></a><span data-ttu-id="157ca-102">방법: 애플리케이션 이벤트 로그에 쓰기(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="157ca-102">How to: Write to an Application Event Log (Visual Basic)</span></span>

<span data-ttu-id="157ca-103">`My.Application.Log` 및 `My.Log` 개체를 사용하여 애플리케이션에서 발생하는 이벤트에 대한 정보를 쓸 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="157ca-103">You can use the `My.Application.Log` and `My.Log` objects to write information about events that occur in your application.</span></span> <span data-ttu-id="157ca-104">이 예제에서는 `My.Application.Log` 가 애플리케이션 이벤트 로그에 추적 정보를 쓰도록 이벤트 로그 수신기를 구성하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="157ca-104">This example shows how to configure an event log listener so `My.Application.Log` writes tracing information to the Application event log.</span></span>

<span data-ttu-id="157ca-105">보안 로그에는 쓸 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="157ca-105">You cannot write to the Security log.</span></span> <span data-ttu-id="157ca-106">시스템 로그에 쓰려면 LocalSystem 또는 Administrator 계정의 멤버여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="157ca-106">In order to write to the System log, you must be a member of the LocalSystem or Administrator account.</span></span>

<span data-ttu-id="157ca-107">이벤트 로그를 보려면 **서버 탐색기** 또는 **Windows 이벤트 뷰어**를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="157ca-107">To view an event log, you can use **Server Explorer** or **Windows Event Viewer**.</span></span> <span data-ttu-id="157ca-108">자세한 내용은 [ETW Events in the .NET Framework](../../../../framework/performance/etw-events.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="157ca-108">For more information, see [ETW Events in the .NET Framework](../../../../framework/performance/etw-events.md).</span></span>

## <a name="to-add-and-configure-the-event-log-listener"></a><span data-ttu-id="157ca-109">이벤트 로그 수신기를 추가하고 구성하려면</span><span class="sxs-lookup"><span data-stu-id="157ca-109">To add and configure the event log listener</span></span>

1. <span data-ttu-id="157ca-110">**솔루션 탐색기** 에서 app.config를 마우스 오른쪽 단추로 클릭하고 **열기**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="157ca-110">Right-click app.config in **Solution Explorer** and choose **Open**.</span></span>

    <span data-ttu-id="157ca-111">\- 또는 -</span><span class="sxs-lookup"><span data-stu-id="157ca-111">\- or -</span></span>

    <span data-ttu-id="157ca-112">app.config 파일이 없는 경우</span><span class="sxs-lookup"><span data-stu-id="157ca-112">If there is no app.config file,</span></span>

    1. <span data-ttu-id="157ca-113">**프로젝트** 메뉴에서 **새 항목 추가**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="157ca-113">On the **Project** menu, choose **Add New Item**.</span></span>

    2. <span data-ttu-id="157ca-114">**새 항목 추가** 대화 상자에서 **애플리케이션 구성 파일**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="157ca-114">From the **Add New Item** dialog box, choose **Application Configuration File**.</span></span>

    3. <span data-ttu-id="157ca-115">**추가**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="157ca-115">Click **Add**.</span></span>

2. <span data-ttu-id="157ca-116">애플리케이션 구성 파일에서 `<listeners>` 섹션을 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="157ca-116">Locate the `<listeners>` section in the application configuration file.</span></span>

    <span data-ttu-id="157ca-117">최상위 `<listeners>` 섹션 아래의 `<source>` 섹션 아래에서 이름 특성이 "DefaultSource"인 `<system.diagnostics>` 섹션에 `<configuration>` 섹션이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="157ca-117">You will find the `<listeners>` section in the `<source>` section with the name attribute "DefaultSource", which is nested under the `<system.diagnostics>` section, which is nested under the top-level `<configuration>` section.</span></span>

3. <span data-ttu-id="157ca-118">다음 요소를 `<listeners>` 섹션에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="157ca-118">Add this element to that `<listeners>` section:</span></span>

    ```xml
    <add name="EventLog"/>
    ```

4. <span data-ttu-id="157ca-119">최상위 `<sharedListeners>` 섹션의 `<system.diagnostics>` 섹션에서 `<configuration>` 섹션을 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="157ca-119">Locate the `<sharedListeners>` section, in the `<system.diagnostics>` section, in the top-level `<configuration>` section.</span></span>

5. <span data-ttu-id="157ca-120">다음 요소를 `<sharedListeners>` 섹션에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="157ca-120">Add this element to that `<sharedListeners>` section:</span></span>

    ```xml
    <add name="EventLog"
        type="System.Diagnostics.EventLogTraceListener, System, Version=2.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089"
         initializeData="APPLICATION_NAME"/>
    ```

    <span data-ttu-id="157ca-121">`APPLICATION_NAME` 을 애플리케이션의 이름으로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="157ca-121">Replace `APPLICATION_NAME` with the name of your application.</span></span>

    > [!NOTE]
    > <span data-ttu-id="157ca-122">일반적으로 애플리케이션에서는 이벤트 로그에 오류만 씁니다.</span><span class="sxs-lookup"><span data-stu-id="157ca-122">Typically, an application writes only errors to the event log.</span></span> <span data-ttu-id="157ca-123">로그 출력 필터링에 대한 자세한 내용은 [Walkthrough: Filtering My.Application.Log Output](../../../../visual-basic/developing-apps/programming/log-info/walkthrough-filtering-my-application-log-output.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="157ca-123">For information on filtering log output, see [Walkthrough: Filtering My.Application.Log Output](../../../../visual-basic/developing-apps/programming/log-info/walkthrough-filtering-my-application-log-output.md).</span></span>

## <a name="to-write-event-information-to-the-event-log"></a><span data-ttu-id="157ca-124">이벤트 정보를 이벤트 로그에 쓰려면</span><span class="sxs-lookup"><span data-stu-id="157ca-124">To write event information to the event log</span></span>

<span data-ttu-id="157ca-125">`My.Application.Log.WriteEntry` 또는 `My.Application.Log.WriteException` 메서드를 사용하여 이벤트 로그에 정보를 씁니다.</span><span class="sxs-lookup"><span data-stu-id="157ca-125">Use the `My.Application.Log.WriteEntry` or `My.Application.Log.WriteException` method to write information to the event log.</span></span> <span data-ttu-id="157ca-126">자세한 내용은 [방법: 로그 메시지 쓰기](../../../../visual-basic/developing-apps/programming/log-info/how-to-write-log-messages.md) 및 [방법: 예외 기록](../../../../visual-basic/developing-apps/programming/log-info/how-to-log-exceptions.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="157ca-126">For more information, see [How to: Write Log Messages](../../../../visual-basic/developing-apps/programming/log-info/how-to-write-log-messages.md) and [How to: Log Exceptions](../../../../visual-basic/developing-apps/programming/log-info/how-to-log-exceptions.md).</span></span>

<span data-ttu-id="157ca-127">어셈블리에 대한 이벤트 로그 수신기를 구성하면 수신기는 `My.Application.Log` 가 해당 어셈블리에서 쓰는 모든 메시지를 수신합니다.</span><span class="sxs-lookup"><span data-stu-id="157ca-127">After you configure the event log listener for an assembly, it receives all messages that `My.Application.Log` writes from that assembly.</span></span>

## <a name="see-also"></a><span data-ttu-id="157ca-128">참고 항목</span><span class="sxs-lookup"><span data-stu-id="157ca-128">See also</span></span>

- <xref:Microsoft.VisualBasic.Logging.Log?displayProperty=nameWithType>
- <xref:Microsoft.VisualBasic.Logging.Log.WriteEntry%2A>
- <xref:Microsoft.VisualBasic.Logging.Log.WriteException%2A>
- [<span data-ttu-id="157ca-129">애플리케이션 로그 작업</span><span class="sxs-lookup"><span data-stu-id="157ca-129">Working with Application Logs</span></span>](../../../../visual-basic/developing-apps/programming/log-info/working-with-application-logs.md)
- [<span data-ttu-id="157ca-130">방법: 예외 기록</span><span class="sxs-lookup"><span data-stu-id="157ca-130">How to: Log Exceptions</span></span>](../../../../visual-basic/developing-apps/programming/log-info/how-to-log-exceptions.md)
- [<span data-ttu-id="157ca-131">연습: My.Application.Log가 정보를 기록하는 위치 확인</span><span class="sxs-lookup"><span data-stu-id="157ca-131">Walkthrough: Determining Where My.Application.Log Writes Information</span></span>](../../../../visual-basic/developing-apps/programming/log-info/walkthrough-determining-where-my-application-log-writes-information.md)
