---
description: '자세한 정보: 연습: My.Application.Log가 정보를 기록하는 위치 확인(Visual Basic)'
title: My.Application.Log가 정보를 기록하는 위치 확인
ms.date: 07/20/2015
helpviewer_keywords:
- My.Log object, output location
- output, application log location
- My.Application.Log object, output location
- event logs, determining output location
- application event logs, output location
- applications [Visual Basic], output location
ms.assetid: 5b70143a-7741-45f2-ae1d-03324a3a4189
ms.openlocfilehash: 4ddb5777bcbdde07069efd2fd3a66f0c220ee135
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99792286"
---
# <a name="walkthrough-determining-where-myapplicationlog-writes-information-visual-basic"></a><span data-ttu-id="9c3d7-103">연습: My.Application.Log가 정보를 기록하는 위치 확인(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="9c3d7-103">Walkthrough: Determining Where My.Application.Log Writes Information (Visual Basic)</span></span>

<span data-ttu-id="9c3d7-104">`My.Application.Log` 개체는 여러 로그 수신기에 정보를 쓸 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9c3d7-104">The `My.Application.Log` object can write information to several log listeners.</span></span> <span data-ttu-id="9c3d7-105">로그 수신기는 컴퓨터의 구성 파일로 구성되며 애플리케이션의 구성 파일로 재정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9c3d7-105">The log listeners are configured by the computer's configuration file and can be overridden by an application's configuration file.</span></span> <span data-ttu-id="9c3d7-106">이 항목에서는 기본 설정과 애플리케이션의 설정을 확인하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="9c3d7-106">This topic describes the default settings and how to determine the settings for your application.</span></span>

<span data-ttu-id="9c3d7-107">기본 출력 위치에 대한 자세한 내용은 [애플리케이션 로그 작업](working-with-application-logs.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="9c3d7-107">For more information about the default output locations, see [Working with Application Logs](working-with-application-logs.md).</span></span>

### <a name="to-determine-the-listeners-for-myapplicationlog"></a><span data-ttu-id="9c3d7-108">My.Application.Log의 수신기를 확인하려면</span><span class="sxs-lookup"><span data-stu-id="9c3d7-108">To determine the listeners for My.Application.Log</span></span>

1. <span data-ttu-id="9c3d7-109">어셈블리의 구성 파일을 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="9c3d7-109">Locate the assembly's configuration file.</span></span> <span data-ttu-id="9c3d7-110">어셈블리를 개발하는 경우 Visual Studio의 **솔루션 탐색기** 에서 app.config에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9c3d7-110">If you are developing the assembly, you can access the app.config in Visual Studio from the **Solution Explorer**.</span></span> <span data-ttu-id="9c3d7-111">그렇지 않은 경우 구성 파일 이름은 어셈블리의 이름에 ".config"가 붙은 형태이며 어셈블리와 같은 디렉터리에 위치합니다.</span><span class="sxs-lookup"><span data-stu-id="9c3d7-111">Otherwise, the configuration file name is the assembly's name appended with ".config", and it is located in the same directory as the assembly.</span></span>

    > [!NOTE]
    > <span data-ttu-id="9c3d7-112">구성 파일에 없는 어셈블리도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9c3d7-112">Not every assembly has a configuration file.</span></span>

    <span data-ttu-id="9c3d7-113">구성 파일은 XML 파일입니다.</span><span class="sxs-lookup"><span data-stu-id="9c3d7-113">The configuration file is an XML file.</span></span>

2. <span data-ttu-id="9c3d7-114">`<listeners>` 특성이 "DefaultSource"인 `<source>` 섹션에서 `name` 섹션에 있는 `<sources>` 섹션을 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="9c3d7-114">Locate the `<listeners>` section, in the `<source>` section with the `name` attribute "DefaultSource", located in the `<sources>` section.</span></span> <span data-ttu-id="9c3d7-115">`<sources>` 섹션은 최상위 `<system.diagnostics>` 섹션의 `<configuration>` 섹션에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9c3d7-115">The `<sources>` section is located in the `<system.diagnostics>` section, in the top-level `<configuration>` section.</span></span>

    <span data-ttu-id="9c3d7-116">이들 섹션이 없으면 컴퓨터의 구성 파일이 `My.Application.Log` 로그 수신기를 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="9c3d7-116">If these sections do not exist, then the computer's configuration file may configure the `My.Application.Log` log listeners.</span></span> <span data-ttu-id="9c3d7-117">다음 단계에서는 컴퓨터 구성 파일에 정의된 내용을 확인하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="9c3d7-117">The following steps describe how to determine what the computer configuration file defines:</span></span>

    1. <span data-ttu-id="9c3d7-118">컴퓨터의 machine.config 파일을 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="9c3d7-118">Locate the computer's machine.config file.</span></span> <span data-ttu-id="9c3d7-119">이 파일은 일반적으로 *SystemRoot\Microsoft.NET\Framework\frameworkVersion\CONFIG* 디렉터리에 있으며, 여기서 `SystemRoot` 는 운영 체제 디렉터리이고 `frameworkVersion`은 .NET Framework의 버전입니다.</span><span class="sxs-lookup"><span data-stu-id="9c3d7-119">Typically, it is located in the *SystemRoot\Microsoft.NET\Framework\frameworkVersion\CONFIG* directory, where `SystemRoot` is the operating system directory, and `frameworkVersion` is the version of the .NET Framework.</span></span>

        <span data-ttu-id="9c3d7-120">machine.config의 설정은 애플리케이션의 구성 파일로 재정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9c3d7-120">The settings in machine.config can be overridden by an application's configuration file.</span></span>

        <span data-ttu-id="9c3d7-121">아래 나열된 선택적 요소가 없을 경우 새로 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9c3d7-121">If the optional elements listed below do not exist, you can create them.</span></span>

    2. <span data-ttu-id="9c3d7-122">최상위 `<listeners>` 섹션의 `<source>` 섹션에 있는 `name` 섹션에서 `<sources>` 특성이 "DefaultSource"인 `<system.diagnostics>` 섹션에 있는 `<configuration>` 섹션을 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="9c3d7-122">Locate the `<listeners>` section, in the `<source>` section with the `name` attribute "DefaultSource", in the `<sources>` section, in the `<system.diagnostics>` section, in the top-level `<configuration>` section.</span></span>

        <span data-ttu-id="9c3d7-123">이들 섹션이 없으면 `My.Application.Log` 에 기본 로그 수신기만 있는 경우입니다.</span><span class="sxs-lookup"><span data-stu-id="9c3d7-123">If these sections do not exist, then the `My.Application.Log` has only the default log listeners.</span></span>

3. <span data-ttu-id="9c3d7-124"><`listeners>` 섹션에서 <`add>` 요소를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="9c3d7-124">Locate the <`add>` elements in the <`listeners>` section.</span></span>

     <span data-ttu-id="9c3d7-125">이들 요소는 명명된 로그 수신기를 `My.Application.Log` 소스에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="9c3d7-125">These elements add the named log listeners to `My.Application.Log` source.</span></span>

4. <span data-ttu-id="9c3d7-126">최상위 `<add>` 섹션에 있는 `<sharedListeners>` 섹션의 `<system.diagnostics>` 섹션에서 로그 수신기의 이름이 지정된 `<configuration>` 요소를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="9c3d7-126">Locate the `<add>` elements with the names of the log listeners in the `<sharedListeners>` section, in the `<system.diagnostics>` section, in the top-level `<configuration>` section.</span></span>

5. <span data-ttu-id="9c3d7-127">여러 형식의 공유 수신기의 경우, 수신기의 초기화 데이터에는 수신기가 데이터를 보낼 위치에 대한 설명이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9c3d7-127">For many types of shared listeners, the listener's initialization data includes a description of where the listener directs the data:</span></span>

    - <span data-ttu-id="9c3d7-128">소개에서 설명한 것처럼 <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener?displayProperty=nameWithType> 수신기는 파일 로그에 씁니다.</span><span class="sxs-lookup"><span data-stu-id="9c3d7-128">A <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener?displayProperty=nameWithType> listener writes to a file log, as described in the introduction.</span></span>

    - <span data-ttu-id="9c3d7-129"><xref:System.Diagnostics.EventLogTraceListener?displayProperty=nameWithType> 수신기는 `initializeData` 매개 변수로 지정된 컴퓨터 이벤트 로그에 정보를 씁니다.</span><span class="sxs-lookup"><span data-stu-id="9c3d7-129">A <xref:System.Diagnostics.EventLogTraceListener?displayProperty=nameWithType> listener writes information to the computer event log specified by the `initializeData` parameter.</span></span> <span data-ttu-id="9c3d7-130">이벤트 로그를 보려면 **서버 탐색기** 또는 **Windows 이벤트 뷰어** 를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="9c3d7-130">To view an event log, you can use **Server Explorer** or **Windows Event Viewer**.</span></span> <span data-ttu-id="9c3d7-131">자세한 내용은 [ETW Events in the .NET Framework](../../../../framework/performance/etw-events.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="9c3d7-131">For more information, see [ETW Events in the .NET Framework](../../../../framework/performance/etw-events.md).</span></span>

    - <span data-ttu-id="9c3d7-132"><xref:System.Diagnostics.DelimitedListTraceListener?displayProperty=nameWithType> 및 <xref:System.Diagnostics.XmlWriterTraceListener?displayProperty=nameWithType> 수신기는 `initializeData` 매개 변수에 지정된 파일에 씁니다.</span><span class="sxs-lookup"><span data-stu-id="9c3d7-132">The <xref:System.Diagnostics.DelimitedListTraceListener?displayProperty=nameWithType> and <xref:System.Diagnostics.XmlWriterTraceListener?displayProperty=nameWithType> listeners write to the file specified in the `initializeData` parameter.</span></span>

    - <span data-ttu-id="9c3d7-133"><xref:System.Diagnostics.ConsoleTraceListener?displayProperty=nameWithType> 수신기는 명령줄 콘솔에 씁니다.</span><span class="sxs-lookup"><span data-stu-id="9c3d7-133">A <xref:System.Diagnostics.ConsoleTraceListener?displayProperty=nameWithType> listener writes to the command-line console.</span></span>

    - <span data-ttu-id="9c3d7-134">다른 형식의 로그 수신기가 정보를 쓰는 위치에 대한 자세한 내용은 해당 형식의 설명서를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="9c3d7-134">For information about where other types of log listeners write information, consult that type's documentation.</span></span>

## <a name="see-also"></a><span data-ttu-id="9c3d7-135">참조</span><span class="sxs-lookup"><span data-stu-id="9c3d7-135">See also</span></span>

- <xref:Microsoft.VisualBasic.Logging.Log?displayProperty=nameWithType>
- <xref:System.Diagnostics.DefaultTraceListener>
- <xref:System.Diagnostics.EventLogTraceListener>
- <xref:System.Diagnostics.DelimitedListTraceListener>
- <xref:System.Diagnostics.XmlWriterTraceListener>
- <xref:System.Diagnostics.ConsoleTraceListener>
- <xref:System.Diagnostics>
- [<span data-ttu-id="9c3d7-136">애플리케이션 로그 작업</span><span class="sxs-lookup"><span data-stu-id="9c3d7-136">Working with Application Logs</span></span>](working-with-application-logs.md)
- [<span data-ttu-id="9c3d7-137">방법: 로그 예외</span><span class="sxs-lookup"><span data-stu-id="9c3d7-137">How to: Log Exceptions</span></span>](how-to-log-exceptions.md)
- [<span data-ttu-id="9c3d7-138">방법: 로그 메시지 쓰기</span><span class="sxs-lookup"><span data-stu-id="9c3d7-138">How to: Write Log Messages</span></span>](how-to-write-log-messages.md)
- [<span data-ttu-id="9c3d7-139">연습: My.Application.Log가 정보를 기록하는 위치 변경</span><span class="sxs-lookup"><span data-stu-id="9c3d7-139">Walkthrough: Changing Where My.Application.Log Writes Information</span></span>](walkthrough-changing-where-my-application-log-writes-information.md)
- [<span data-ttu-id="9c3d7-140">ETW Events in the .NET Framework</span><span class="sxs-lookup"><span data-stu-id="9c3d7-140">ETW Events in the .NET Framework</span></span>](../../../../framework/performance/etw-events.md)
- [<span data-ttu-id="9c3d7-141">문제 해결: 로그 수신기</span><span class="sxs-lookup"><span data-stu-id="9c3d7-141">Troubleshooting: Log Listeners</span></span>](troubleshooting-log-listeners.md)
