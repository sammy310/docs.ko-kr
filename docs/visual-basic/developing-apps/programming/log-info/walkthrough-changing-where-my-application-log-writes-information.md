---
description: '자세한 정보: 연습: My.Application.Log가 정보를 기록하는 위치 변경(Visual Basic)'
title: My.Application.Log가 정보를 기록하는 위치 변경
ms.date: 07/20/2015
helpviewer_keywords:
- My.Application.Log object, walkthroughs
- event logs, changing output location
ms.assetid: ecc74f95-743c-450d-93f6-09a30db0fe4a
ms.openlocfilehash: aa4e1b8ce33e2afd8dd51c68340feb3e85eb8966
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99731424"
---
# <a name="walkthrough-changing-where-myapplicationlog-writes-information-visual-basic"></a><span data-ttu-id="e0f13-103">연습: My.Application.Log가 정보를 기록하는 위치 변경(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="e0f13-103">Walkthrough: Changing Where My.Application.Log Writes Information (Visual Basic)</span></span>

<span data-ttu-id="e0f13-104">`My.Application.Log` 및 `My.Log` 개체를 사용하여 애플리케이션에서 발생하는 이벤트에 대한 정보를 기록할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e0f13-104">You can use the `My.Application.Log` and `My.Log` objects to log information about events that occur in your application.</span></span> <span data-ttu-id="e0f13-105">이 연습에서는 기본 설정을 재정의하고 `Log` 개체가 다른 로그 수신기에 쓰도록 만드는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="e0f13-105">This walkthrough shows how to override the default settings and cause the `Log` object to write to other log listeners.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="e0f13-106">사전 준비 사항</span><span class="sxs-lookup"><span data-stu-id="e0f13-106">Prerequisites</span></span>

<span data-ttu-id="e0f13-107">`Log` 개체는 여러 로그 수신기에 정보를 쓸 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e0f13-107">The `Log` object can write information to several log listeners.</span></span> <span data-ttu-id="e0f13-108">구성을 변경하기 전에 로그 수신기의 현재 구성을 확인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e0f13-108">You need to determine the current configuration of the log listeners before changing the configurations.</span></span> <span data-ttu-id="e0f13-109">자세한 내용은 [연습: My.Application.Log가 정보를 기록하는 위치 확인](walkthrough-determining-where-my-application-log-writes-information.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="e0f13-109">For more information, see [Walkthrough: Determining Where My.Application.Log Writes Information](walkthrough-determining-where-my-application-log-writes-information.md).</span></span>

<span data-ttu-id="e0f13-110">[방법: 텍스트 파일에 이벤트 정보 쓰기](how-to-write-event-information-to-a-text-file.md) 또는 [방법: 애플리케이션 이벤트 로그에 쓰기](how-to-write-to-an-application-event-log.md)도 검토할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e0f13-110">You may want to review [How to: Write Event Information to a Text File](how-to-write-event-information-to-a-text-file.md) or [How to: Write to an Application Event Log](how-to-write-to-an-application-event-log.md).</span></span>

### <a name="to-add-listeners"></a><span data-ttu-id="e0f13-111">수신기를 추가하려면</span><span class="sxs-lookup"><span data-stu-id="e0f13-111">To add listeners</span></span>

1. <span data-ttu-id="e0f13-112">**솔루션 탐색기** 에서 app.config를 마우스 오른쪽 단추로 클릭하고 **열기** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="e0f13-112">Right-click app.config in **Solution Explorer** and choose **Open**.</span></span>

     <span data-ttu-id="e0f13-113">\- 또는 -</span><span class="sxs-lookup"><span data-stu-id="e0f13-113">\- or -</span></span>

     <span data-ttu-id="e0f13-114">app.config 파일이 없는 경우</span><span class="sxs-lookup"><span data-stu-id="e0f13-114">If there is no app.config file:</span></span>

    1. <span data-ttu-id="e0f13-115">**프로젝트** 메뉴에서 **새 항목 추가** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="e0f13-115">On the **Project** menu, choose **Add New Item**.</span></span>

    2. <span data-ttu-id="e0f13-116">**새 항목 추가** 대화 상자에서 **애플리케이션 구성 파일** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="e0f13-116">From the **Add New Item** dialog box, select **Application Configuration File**.</span></span>

    3. <span data-ttu-id="e0f13-117">**추가** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="e0f13-117">Click **Add**.</span></span>

2. <span data-ttu-id="e0f13-118">`<listeners>` 섹션에서 `<source>` 특성이 "DefaultSource"인 `name` 섹션 아래에 있는 `<sources>` 섹션을 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="e0f13-118">Locate the `<listeners>` section, under the `<source>` section with the `name` attribute "DefaultSource", in the `<sources>` section.</span></span> <span data-ttu-id="e0f13-119">`<sources>` 섹션은 최상위 `<system.diagnostics>` 섹션의 `<configuration>` 섹션에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e0f13-119">The `<sources>` section is in the `<system.diagnostics>` section, in the top-level `<configuration>` section.</span></span>

3. <span data-ttu-id="e0f13-120">다음 요소를 `<listeners>` 섹션에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="e0f13-120">Add these elements to that `<listeners>` section.</span></span>

    ```xml
    <!-- Uncomment to connect the application file log. -->
    <!-- <add name="FileLog" /> -->
    <!-- Uncomment to connect the event log. -->
    <!-- <add name="EventLog" /> -->
    <!-- Uncomment to connect the event log. -->
    <!-- <add name="Delimited" /> -->
    <!-- Uncomment to connect the XML log. -->
    <!-- <add name="XmlWriter" /> -->
    <!-- Uncomment to connect the console log. -->
    <!-- <add name="Console" /> -->
    ```

4. <span data-ttu-id="e0f13-121">`Log` 메시지를 받을 로그 수신기의 주석을 해제합니다.</span><span class="sxs-lookup"><span data-stu-id="e0f13-121">Uncomment the log listeners that you want to receive `Log` messages.</span></span>

5. <span data-ttu-id="e0f13-122">최상위 `<sharedListeners>` 섹션의 `<system.diagnostics>` 섹션에서 `<configuration>` 섹션을 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="e0f13-122">Locate the `<sharedListeners>` section, in the `<system.diagnostics>` section, in the top-level `<configuration>` section.</span></span>

6. <span data-ttu-id="e0f13-123">다음 요소를 `<sharedListeners>` 섹션에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="e0f13-123">Add these elements to that `<sharedListeners>` section.</span></span>

    ```xml
    <add name="FileLog"
         type="Microsoft.VisualBasic.Logging.FileLogTraceListener,
               Microsoft.VisualBasic, Version=8.0.0.0,
               Culture=neutral, PublicKeyToken=b03f5f7f11d50a3a"
         initializeData="FileLogWriter" />
    <add name="EventLog"
         type="System.Diagnostics.EventLogTraceListener,
               System, Version=2.0.0.0,
               Culture=neutral, PublicKeyToken=b77a5c561934e089"
         initializeData="sample application"/>
    <add name="Delimited"
         type="System.Diagnostics.DelimitedListTraceListener,
               System, Version=2.0.0.0,
               Culture=neutral, PublicKeyToken=b77a5c561934e089"
         initializeData="c:\temp\sampleDelimitedFile.txt"
         traceOutputOptions="DateTime" />
    <add name="XmlWriter"
         type="System.Diagnostics.XmlWriterTraceListener,
               System, Version=2.0.0.0,
               Culture=neutral, PublicKeyToken=b77a5c561934e089"
         initializeData="c:\temp\sampleLogFile.xml" />
    <add name="Console"
         type="System.Diagnostics.ConsoleTraceListener,
               System, Version=2.0.0.0,
               Culture=neutral, PublicKeyToken=b77a5c561934e089"
         initializeData="true" />
    ```

7. <span data-ttu-id="e0f13-124">app.config 파일의 내용은 다음 XML과 비슷합니다.</span><span class="sxs-lookup"><span data-stu-id="e0f13-124">The content of the app.config file should be similar to the following XML:</span></span>

    ```xml
    <?xml version="1.0" encoding="utf-8" ?>
    <configuration>
      <system.diagnostics>
        <sources>
          <!-- This section configures My.Application.Log -->
          <source name="DefaultSource" switchName="DefaultSwitch">
            <listeners>
              <add name="FileLog"/>
              <!-- Uncomment to connect the application file log. -->
              <!-- <add name="FileLog" /> -->
              <!-- Uncomment to connect the event log. -->
              <!-- <add name="EventLog" /> -->
              <!-- Uncomment to connect the event log. -->
              <!-- <add name="Delimited" /> -->
              <!-- Uncomment to connect the XML log. -->
              <!-- <add name="XmlWriter" /> -->
              <!-- Uncomment to connect the console log. -->
              <!-- <add name="Console" /> -->
            </listeners>
          </source>
        </sources>
        <switches>
          <add name="DefaultSwitch" value="Information" />
        </switches>
        <sharedListeners>
          <add name="FileLog"
               type="Microsoft.VisualBasic.Logging.FileLogTraceListener,
                     Microsoft.VisualBasic, Version=8.0.0.0,
                     Culture=neutral, PublicKeyToken=b03f5f7f11d50a3a"
               initializeData="FileLogWriter" />
          <add name="EventLog"
               type="System.Diagnostics.EventLogTraceListener,
                     System, Version=2.0.0.0,
                     Culture=neutral, PublicKeyToken=b77a5c561934e089"
               initializeData="sample application"/>
          <add name="Delimited"
               type="System.Diagnostics.DelimitedListTraceListener,
                     System, Version=2.0.0.0,
                     Culture=neutral, PublicKeyToken=b77a5c561934e089"
               initializeData="c:\temp\sampleDelimitedFile.txt"
               traceOutputOptions="DateTime" />
          <add name="XmlWriter"
               type="System.Diagnostics.XmlWriterTraceListener,
                     System, Version=2.0.0.0,
                     Culture=neutral, PublicKeyToken=b77a5c561934e089"
               initializeData="c:\temp\sampleLogFile.xml" />
          <add name="Console"
               type="System.Diagnostics.ConsoleTraceListener,
                     System, Version=2.0.0.0,
                     Culture=neutral, PublicKeyToken=b77a5c561934e089"
               initializeData="true" />
        </sharedListeners>
      </system.diagnostics>
    </configuration>
    ```

### <a name="to-reconfigure-a-listener"></a><span data-ttu-id="e0f13-125">수신기를 다시 구성하려면</span><span class="sxs-lookup"><span data-stu-id="e0f13-125">To reconfigure a listener</span></span>

1. <span data-ttu-id="e0f13-126">`<add>` 섹션에서 수신기의 `<sharedListeners>` 요소를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="e0f13-126">Locate the listener's `<add>` element from the `<sharedListeners>` section.</span></span>

2. <span data-ttu-id="e0f13-127">`type` 특성이 수신기 형식의 이름을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="e0f13-127">The `type` attribute gives the name of the listener type.</span></span> <span data-ttu-id="e0f13-128">이 형식은 <xref:System.Diagnostics.TraceListener> 클래스에서 상속해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e0f13-128">This type must inherit from the <xref:System.Diagnostics.TraceListener> class.</span></span> <span data-ttu-id="e0f13-129">올바른 형식이 사용되도록 강력한 이름의 형식 이름을 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="e0f13-129">Use the strongly named type name to ensure that the right type is used.</span></span> <span data-ttu-id="e0f13-130">자세한 내용은 아래의 "강력한 이름의 형식을 참조하려면"을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="e0f13-130">For more information, see the "To reference a strongly named type" section below.</span></span>

     <span data-ttu-id="e0f13-131">다음 형식을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e0f13-131">Some types that you can use are:</span></span>

    - <span data-ttu-id="e0f13-132">파일 로그에 쓰는 <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener?displayProperty=nameWithType> 수신기</span><span class="sxs-lookup"><span data-stu-id="e0f13-132">A <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener?displayProperty=nameWithType> listener, which writes to a file log.</span></span>

    - <span data-ttu-id="e0f13-133"><xref:System.Diagnostics.EventLogTraceListener?displayProperty=nameWithType> 매개 변수로 지정된 컴퓨터 이벤트 로그에 정보를 쓰는 `initializeData` 수신기</span><span class="sxs-lookup"><span data-stu-id="e0f13-133">A <xref:System.Diagnostics.EventLogTraceListener?displayProperty=nameWithType> listener, which writes information to the computer event log specified by the `initializeData` parameter.</span></span>

    - <span data-ttu-id="e0f13-134"><xref:System.Diagnostics.DelimitedListTraceListener?displayProperty=nameWithType> 매개 변수에 지정된 파일에 쓰는 <xref:System.Diagnostics.XmlWriterTraceListener?displayProperty=nameWithType> 및 `initializeData` 수신기</span><span class="sxs-lookup"><span data-stu-id="e0f13-134">The <xref:System.Diagnostics.DelimitedListTraceListener?displayProperty=nameWithType> and <xref:System.Diagnostics.XmlWriterTraceListener?displayProperty=nameWithType> listeners, which write to the file specified in the `initializeData` parameter.</span></span>

    - <span data-ttu-id="e0f13-135">명령줄 콘솔에 쓰는 <xref:System.Diagnostics.ConsoleTraceListener?displayProperty=nameWithType> 수신기</span><span class="sxs-lookup"><span data-stu-id="e0f13-135">A <xref:System.Diagnostics.ConsoleTraceListener?displayProperty=nameWithType> listener, which writes to the command-line console.</span></span>

     <span data-ttu-id="e0f13-136">다른 형식의 로그 수신기가 정보를 쓰는 위치에 대한 자세한 내용은 해당 형식의 설명서를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="e0f13-136">For information about where other types of log listeners write information, consult that type's documentation.</span></span>

3. <span data-ttu-id="e0f13-137">애플리케이션에서는 로그 수신기 개체를 만들 때 `initializeData` 특성을 생성자 매개 변수로 전달합니다.</span><span class="sxs-lookup"><span data-stu-id="e0f13-137">When the application creates the log-listener object, it passes the `initializeData` attribute as the constructor parameter.</span></span> <span data-ttu-id="e0f13-138">`initializeData` 특성의 의미는 추적 수신기에 따라 달라집니다.</span><span class="sxs-lookup"><span data-stu-id="e0f13-138">The meaning of the `initializeData` attribute depends on the trace listener.</span></span>

4. <span data-ttu-id="e0f13-139">로그 수신기를 만든 후 애플리케이션에서는 수신기의 속성을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="e0f13-139">After creating the log listener, the application sets the listener's properties.</span></span> <span data-ttu-id="e0f13-140">이들 속성은 `<add>` 요소의 다른 특성에 의해 정의됩니다.</span><span class="sxs-lookup"><span data-stu-id="e0f13-140">These properties are defined by the other attributes in the `<add>` element.</span></span> <span data-ttu-id="e0f13-141">특정 수신기의 속성에 대한 자세한 내용은 해당 수신기 형식의 설명서를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="e0f13-141">For more information on the properties for a particular listener, see the documentation for that listener's type.</span></span>

### <a name="to-reference-a-strongly-named-type"></a><span data-ttu-id="e0f13-142">강력한 이름의 형식을 참조하려면</span><span class="sxs-lookup"><span data-stu-id="e0f13-142">To reference a strongly named type</span></span>

1. <span data-ttu-id="e0f13-143">로그 수신기에 올바른 형식이 사용되도록 하려면 정규화된 형식 이름과 강력한 이름의 어셈블리 이름을 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="e0f13-143">To ensure that the right type is used for your log listener, make sure to use the fully qualified type name and the strongly named assembly name.</span></span> <span data-ttu-id="e0f13-144">강력한 이름의 형식은 다음과 같은 구문을 갖습니다.</span><span class="sxs-lookup"><span data-stu-id="e0f13-144">The syntax of a strongly named type is as follows:</span></span>

     <span data-ttu-id="e0f13-145">\<*type name*>, \<*assembly name*>, \<*version number*>, \<*culture*>, \<*strong name*></span><span class="sxs-lookup"><span data-stu-id="e0f13-145">\<*type name*>, \<*assembly name*>, \<*version number*>, \<*culture*>, \<*strong name*></span></span>

2. <span data-ttu-id="e0f13-146">이 코드 예제에서는 정규화된 형식(이 경우 "System.Diagnostics.FileLogTraceListener")에 대한 강력한 이름이 지정된 형식 이름을 확인하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="e0f13-146">This code example shows how to determine the strongly named type name for a fully qualified type—"System.Diagnostics.FileLogTraceListener" in this case.</span></span>

     [!code-vb[VbVbalrMyApplicationLog#15](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyApplicationLog/VB/Form1.vb#15)]

     <span data-ttu-id="e0f13-147">출력은 다음과 같으며, 위의 "수신기를 추가하려면" 절차에서처럼 이 출력을 사용하여 강력한 이름의 형식을 고유하게 참조할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e0f13-147">This is the output, and it can be used to uniquely reference a strongly named type, as in the "To add listeners" procedure above.</span></span>

     `Microsoft.VisualBasic.Logging.FileLogTraceListener, Microsoft.VisualBasic, Version=8.0.0.0, Culture=neutral, PublicKeyToken=b03f5f7f11d50a3a`

## <a name="see-also"></a><span data-ttu-id="e0f13-148">참고 항목</span><span class="sxs-lookup"><span data-stu-id="e0f13-148">See also</span></span>

- <xref:Microsoft.VisualBasic.Logging.Log?displayProperty=nameWithType>
- <xref:System.Diagnostics.TraceListener>
- <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener?displayProperty=nameWithType>
- <xref:System.Diagnostics.EventLogTraceListener?displayProperty=nameWithType>
- [<span data-ttu-id="e0f13-149">방법: 텍스트 파일에 이벤트 정보 쓰기</span><span class="sxs-lookup"><span data-stu-id="e0f13-149">How to: Write Event Information to a Text File</span></span>](how-to-write-event-information-to-a-text-file.md)
- [<span data-ttu-id="e0f13-150">방법: 애플리케이션 이벤트 로그에 쓰기</span><span class="sxs-lookup"><span data-stu-id="e0f13-150">How to: Write to an Application Event Log</span></span>](how-to-write-to-an-application-event-log.md)
