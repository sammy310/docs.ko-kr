---
title: '방법: 추적 소스 만들기 및 초기화'
description: .NET에서 TraceSource 클래스를 사용 하 여 추적 소스를 만들고 초기화 합니다. 이 클래스는 이벤트와 데이터를 추적 하 고 정보 추적을 실행 하는 메서드를 제공 합니다.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- trace sources
- initializing trace sources
- configuration files [.NET Framework], trace sources
ms.assetid: f88dda6f-5fda-45be-9b3c-745a9b708c4d
ms.openlocfilehash: 55d7854bff991ba185d3f5d6e4c6e7222c9e3039
ms.sourcegitcommit: 0edbeb66d71b8df10fcb374cfca4d731b58ccdb2
ms.contentlocale: ko-KR
ms.lasthandoff: 07/07/2020
ms.locfileid: "86051274"
---
# <a name="how-to-create-and-initialize-trace-sources"></a><span data-ttu-id="77b74-104">방법: 추적 소스 만들기 및 초기화</span><span class="sxs-lookup"><span data-stu-id="77b74-104">How to: Create and Initialize Trace Sources</span></span>
<span data-ttu-id="77b74-105"><xref:System.Diagnostics.TraceSource> 클래스는 애플리케이션과 연결될 수 있는 추적을 만들기 위해 애플리케이션에서 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="77b74-105">The <xref:System.Diagnostics.TraceSource> class is used by applications to produce traces that can be associated with the application.</span></span> <span data-ttu-id="77b74-106"><xref:System.Diagnostics.TraceSource>는 이벤트, 추적 데이터 및 문제 정보 추적을 쉽게 추적할 수 있는 추적 메서드를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="77b74-106"><xref:System.Diagnostics.TraceSource> provides tracing methods that allow you to easily trace events, trace data, and issue informational traces.</span></span> <span data-ttu-id="77b74-107">구성 파일을 사용하거나 사용하지 않고 <xref:System.Diagnostics.TraceSource>에서 추적 출력을 만들고 초기화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="77b74-107">Trace output from <xref:System.Diagnostics.TraceSource> can be created and initialized with or without the use of configuration files.</span></span> <span data-ttu-id="77b74-108">이 항목에서는 두 가지 옵션 모두에 대한 지침을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="77b74-108">This topic provides instructions for both options.</span></span> <span data-ttu-id="77b74-109">하지만 구성 파일을 사용하여 런타임에 추적 소스에 의해 생성되는 추적을 쉽게 재구성하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="77b74-109">However, we recommend that you use configuration files to facilitate the reconfiguration of the traces produced by trace sources at run time.</span></span>  
  
### <a name="to-create-and-initialize-a-trace-source-using-a-configuration-file"></a><span data-ttu-id="77b74-110">구성 파일을 사용하여 추적 소스를 만들고 초기화하려면</span><span class="sxs-lookup"><span data-stu-id="77b74-110">To create and initialize a trace source using a configuration file</span></span>  
  
1. <span data-ttu-id="77b74-111">Visual Studio 콘솔 응용 프로그램 프로젝트 (.NET Framework)를 만들고 제공 된 코드를 다음 코드로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="77b74-111">Create a Visual Studio console application project (.NET Framework) and replace the supplied code with the following code.</span></span> <span data-ttu-id="77b74-112">이 코드는 오류 및 경고를 기록하며 그 중 일부는 콘솔에 출력하고 일부는 구성 파일의 항목에 의해 만들어진 myListener 파일에 출력합니다.</span><span class="sxs-lookup"><span data-stu-id="77b74-112">This code logs errors and warnings and outputs some of them to the console, and some of them to the myListener file that is created by the entries in the configuration file.</span></span>  
  
     [!code-csharp[TraceSourceExample1#1](../../../samples/snippets/csharp/VS_Snippets_CLR/tracesourceexample1/cs/program.cs#1)]
     [!code-vb[TraceSourceExample1#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/tracesourceexample1/vb/program.vb#1)]  
  
2. <span data-ttu-id="77b74-113">애플리케이션 구성 파일이 없다면 1단계의 코드 예제에서 `TraceSourceApp`이라는 추적 소스를 초기화하기 위해 프로젝트에 애플리케이션 구성 파일을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="77b74-113">Add an application configuration file, if one is not present, to the project to initialize the trace source named `TraceSourceApp` in the code example in step 1.</span></span>  
  
3. <span data-ttu-id="77b74-114">기본 구성 파일 콘텐츠를 다음 설정으로 바꿔서 1단계에서 만든 추적 소스에 대해 콘솔 추적 수신기와 텍스트 기록기 추적 수신기를 초기화합니다.</span><span class="sxs-lookup"><span data-stu-id="77b74-114">Replace the default configuration file content with the following settings to initialize a console trace listener and a text writer trace listener for the trace source that was created in step 1.</span></span>  
  
    ```xml  
    <configuration>  
      <system.diagnostics>  
        <sources>  
          <source name="TraceSourceApp"
            switchName="sourceSwitch"
            switchType="System.Diagnostics.SourceSwitch">  
            <listeners>  
              <add name="console"
                type="System.Diagnostics.ConsoleTraceListener">  
                <filter type="System.Diagnostics.EventTypeFilter"
                  initializeData="Error"/>  
              </add>  
              <add name="myListener"/>  
              <remove name="Default"/>  
            </listeners>  
          </source>  
        </sources>  
        <switches>  
          <add name="sourceSwitch" value="Error"/>  
        </switches>  
        <sharedListeners>  
          <add name="myListener"
            type="System.Diagnostics.TextWriterTraceListener"
            initializeData="myListener.log">  
            <filter type="System.Diagnostics.EventTypeFilter"
              initializeData="Error"/>  
          </add>  
        </sharedListeners>  
      </system.diagnostics>  
    </configuration>  
    ```  
  
     <span data-ttu-id="77b74-115">추적 수신기의 구성 이외에도 구성 파일은 두 수신기에 대한 필터를 만들고 추적 소스에 대한 소스 스위치를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="77b74-115">In addition to configuring the trace listeners, the configuration file creates filters for both listeners and creates a source switch for the trace source.</span></span> <span data-ttu-id="77b74-116">추적 수신기를 추가하는 데는 두 가지 방법이 사용됩니다. 즉 수신기를 추적 소스에 직접 추가하는 방법과 수신기를 공유 컬렉션에 추가한 다음 이를 이름별로 추적 소스에 추가하는 방법이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="77b74-116">Two techniques are shown for adding trace listeners: adding the listener directly to the trace source and adding a listener to the shared listeners collection and then adding it by name to the trace source.</span></span> <span data-ttu-id="77b74-117">두 수신기에 대해 식별된 필터는 서로 다른 소스 수준으로 초기화됩니다.</span><span class="sxs-lookup"><span data-stu-id="77b74-117">The filters identified for the two listeners are initialized with different source levels.</span></span> <span data-ttu-id="77b74-118">이로 인해 일부 메시지가 두 수신기 중 하나에 의해서만 기록됩니다.</span><span class="sxs-lookup"><span data-stu-id="77b74-118">This results in some messages being written by only one of the two listeners.</span></span>  
  
     <span data-ttu-id="77b74-119">구성 파일은 애플리케이션이 초기화될 때 추적 소스에 대한 설정을 초기화합니다.</span><span class="sxs-lookup"><span data-stu-id="77b74-119">The configuration file initializes the settings for the trace source at the time the application is initialized.</span></span> <span data-ttu-id="77b74-120">애플리케이션은 구성 파일에서 설정되는 속성을 동적으로 변경하여 사용자가 지정한 설정을 재정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="77b74-120">The application can dynamically change the properties set by the configuration file to override any settings specified by the user.</span></span> <span data-ttu-id="77b74-121">예를 들어, 현재의 구성 설정과 관계없이 중대 오류 메시지를 항상 텍스트 파일로 보내도록 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="77b74-121">For example, you might want to ensure that critical messages are always sent to a text file, regardless of the current configuration settings.</span></span> <span data-ttu-id="77b74-122">예제 코드에서는 구성 파일 설정을 재정의하여 중대 오류 메시지가 추적 수신기에 출력되도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="77b74-122">The example code demonstrates how to override configuration file settings to ensure that critical messages are output to the trace listeners.</span></span>  
  
     <span data-ttu-id="77b74-123">애플리케이션이 실행되는 동안 구성 파일 설정을 변경해도 초기 설정이 변경되지는 않습니다.</span><span class="sxs-lookup"><span data-stu-id="77b74-123">Changing the configuration file settings while the application is executing does not change the initial settings.</span></span> <span data-ttu-id="77b74-124">설정을 변경하려면 애플리케이션을 다시 시작하거나 <xref:System.Diagnostics.Trace.Refresh%2A?displayProperty=nameWithType> 메서드를 사용하여 애플리케이션을 프로그래밍 방식으로 새로 고쳐야 합니다.</span><span class="sxs-lookup"><span data-stu-id="77b74-124">To change the settings, you must either restart the application or programmatically refresh the application by using the <xref:System.Diagnostics.Trace.Refresh%2A?displayProperty=nameWithType> method.</span></span>  
  
### <a name="to-initialize-trace-sources-listeners-and-filters-without-a-configuration-file"></a><span data-ttu-id="77b74-125">구성 파일 없이 추적 소스, 수신기 및 필터를 초기화하려면</span><span class="sxs-lookup"><span data-stu-id="77b74-125">To initialize trace sources, listeners, and filters without a configuration file</span></span>  
  
- <span data-ttu-id="77b74-126">다음 예제 코드를 사용하여 구성 파일을 사용하지 않고도 추적 소스를 통해 추적할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="77b74-126">Use the following example code to enable tracing through a trace source without using a configuration file.</span></span> <span data-ttu-id="77b74-127">이 방법은 권장되는 구현 방법은 아니지만, 상황에 따라 구성 파일에 의존하지 않고 추적하려는 경우가 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="77b74-127">This is not a recommended practice, but there may be circumstances in which you do not want to depend on configuration files to ensure tracing.</span></span>  
  
     [!code-csharp[TraceSourceExample2#1](../../../samples/snippets/csharp/VS_Snippets_CLR/tracesourceexample2/cs/program.cs#1)]
     [!code-vb[TraceSourceExample2#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/tracesourceexample2/vb/program.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="77b74-128">참조</span><span class="sxs-lookup"><span data-stu-id="77b74-128">See also</span></span>

- <xref:System.Diagnostics.TraceSource>
- <xref:System.Diagnostics.TextWriterTraceListener>
- <xref:System.Diagnostics.ConsoleTraceListener>
- <xref:System.Diagnostics.EventTypeFilter>
- [<span data-ttu-id="77b74-129">애플리케이션 추적 및 조율</span><span class="sxs-lookup"><span data-stu-id="77b74-129">Tracing and Instrumenting Applications</span></span>](tracing-and-instrumenting-applications.md)
