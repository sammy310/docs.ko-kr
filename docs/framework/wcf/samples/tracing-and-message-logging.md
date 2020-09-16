---
title: 추적 및 메시지 로깅
description: 서비스 추적 뷰어 도구 (SvcTraceViewer.exe)를 사용 하 여이 WFC 샘플을 통해 추적 및 메시지 로그를 보는 방법에 대해 알아봅니다.
ms.date: 03/30/2017
helpviewer_keywords:
- Tracing and logging
ms.assetid: a4f39bfc-3c5e-4d51-a312-71c5c3ce0afd
ms.openlocfilehash: 9c3d83f0055a1700c675017216a7419fdba674fd
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/15/2020
ms.locfileid: "90547462"
---
# <a name="tracing-and-message-logging"></a><span data-ttu-id="f1ba0-103">추적 및 메시지 로깅</span><span class="sxs-lookup"><span data-stu-id="f1ba0-103">Tracing and Message Logging</span></span>
<span data-ttu-id="f1ba0-104">이 샘플에서는 추적 및 메시지 로깅을 사용하도록 설정하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="f1ba0-104">This sample demonstrates how to enable tracing and message logging.</span></span> <span data-ttu-id="f1ba0-105">결과 추적 및 메시지 로그는 [서비스 추적 뷰어 도구 (SvcTraceViewer.exe)](../service-trace-viewer-tool-svctraceviewer-exe.md)를 사용 하 여 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f1ba0-105">The resulting traces and message logs are viewed using the [Service Trace Viewer Tool (SvcTraceViewer.exe)](../service-trace-viewer-tool-svctraceviewer-exe.md).</span></span> <span data-ttu-id="f1ba0-106">이 샘플은 [시작](getting-started-sample.md)을 기반으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="f1ba0-106">This sample is based on the [Getting Started](getting-started-sample.md).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="f1ba0-107">이 샘플의 설치 절차 및 빌드 지침은 이 항목의 끝부분에 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f1ba0-107">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span>  
  
## <a name="tracing"></a><span data-ttu-id="f1ba0-108">추적</span><span class="sxs-lookup"><span data-stu-id="f1ba0-108">Tracing</span></span>  
 <span data-ttu-id="f1ba0-109">WCF (Windows Communication Foundation)는 네임 스페이스에 정의 된 추적 메커니즘을 사용 합니다 <xref:System.Diagnostics> .</span><span class="sxs-lookup"><span data-stu-id="f1ba0-109">Windows Communication Foundation (WCF) uses the tracing mechanism defined in the <xref:System.Diagnostics> namespace.</span></span> <span data-ttu-id="f1ba0-110">이 추적 모델에서 추적 데이터는 애플리케이션이 구현하는 추적 소스에 의해 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="f1ba0-110">In this tracing model, trace data is produced by trace sources that applications implement.</span></span> <span data-ttu-id="f1ba0-111">각 소스는 이름으로 식별됩니다.</span><span class="sxs-lookup"><span data-stu-id="f1ba0-111">Each source is identified by a name.</span></span> <span data-ttu-id="f1ba0-112">추적 소비자는 정보를 검색하려는 추적 소스에 대한 추적 수신기를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="f1ba0-112">Trace consumers create trace listeners for the trace sources for which they want to retrieve information.</span></span> <span data-ttu-id="f1ba0-113">추적 데이터를 수신하려면 추적 소스에 대한 수신기를 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f1ba0-113">To receive trace data, you must create a listener for the trace source.</span></span> <span data-ttu-id="f1ba0-114">WCF에서는 서비스 모델 추적 소스를 설정 하 여 서비스 또는 클라이언트의 구성 파일에 다음 코드를 추가 하 여이 작업을 수행할 수 있습니다 `switchValue` .</span><span class="sxs-lookup"><span data-stu-id="f1ba0-114">In WCF, this can be done by adding the following code to either the service’s or client’s configuration file by setting the Service Model trace source `switchValue`:</span></span>  
  
```xml  
<system.diagnostics>  
    <sources>  
      <source name="System.ServiceModel" switchValue="Information,ActivityTracing"  
        propagateActivity="true">  
        <listeners>  
          <add name="xml" />  
        </listeners>  
      </source>  
      <source name="System.ServiceModel.MessageLogging">  
        <listeners>  
          <add name="xml" />  
        </listeners>  
      </source>  
    </sources>  
    <sharedListeners>  
      <add initializeData="C:\logs\TracingAndLogging-service.svclog" type="System.Diagnostics.XmlWriterTraceListener"  
        name="xml" />  
    </sharedListeners>  
    <trace autoflush="true" />  
</system.diagnostics>  
```  
  
 <span data-ttu-id="f1ba0-115">추적 소스에 대 한 자세한 내용은 추적 [구성](../diagnostics/tracing/configuring-tracing.md) 항목에서 추적 원본 섹션을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="f1ba0-115">For more information about trace sources, see the Trace Source section in the [Configuring Tracing](../diagnostics/tracing/configuring-tracing.md) topic.</span></span>  
  
## <a name="activity-tracing-and-propagation"></a><span data-ttu-id="f1ba0-116">동작 추적 및 전파</span><span class="sxs-lookup"><span data-stu-id="f1ba0-116">Activity Tracing and Propagation</span></span>  
 <span data-ttu-id="f1ba0-117">`ActivityTracing` `propagateActivity` 클라이언트와 서비스 모두에 대해 추적 소스에서를 사용 하도록 설정 하 고를로 설정 하면 `true` `system.ServiceModel` 논리 처리 단위 (작업) 내에서, 끝점 내의 작업 (작업 전송 통해) 및 여러 끝점에 걸친 작업 (작업 ID 전파를 통해) 간에 추적의 상관 관계를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="f1ba0-117">Having `ActivityTracing` enabled and `propagateActivity` set to `true` in the `system.ServiceModel` trace sources for both the client and service provide correlation of traces within logical units of processing (activities), across activities within endpoints (through activity transfers), and across activities spanning multiple endpoints (through activity ID propagation).</span></span>  
  
 <span data-ttu-id="f1ba0-118">이러한 세 가지 메커니즘(동작, 전송 및 전파)은 Service Trace Viewer 도구를 사용하여 오류의 근본 원인을 더 신속하게 찾을 수 있도록 도와줍니다.</span><span class="sxs-lookup"><span data-stu-id="f1ba0-118">These three mechanisms (activities, transfers, and propagation) can help you locate the root cause of an error more quickly using the Service Trace Viewer tool.</span></span> <span data-ttu-id="f1ba0-119">자세한 내용은 [서비스 추적 뷰어를 사용 하 여 상호 관련 된 추적 보기 및 문제 해결](../diagnostics/tracing/using-service-trace-viewer-for-viewing-correlated-traces-and-troubleshooting.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="f1ba0-119">For more information, see [Using Service Trace Viewer for Viewing Correlated Traces and Troubleshooting](../diagnostics/tracing/using-service-trace-viewer-for-viewing-correlated-traces-and-troubleshooting.md).</span></span>  
  
 <span data-ttu-id="f1ba0-120">사용자 정의 동작 추적을 만들어 ServiceModel이 제공되는 추적을 확장할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f1ba0-120">It is possible to extend the tracing that is provided by the ServiceModel by creating user-defined activity traces.</span></span> <span data-ttu-id="f1ba0-121">사용자 정의 동작 추적을 통해 사용자는 추적 동작을 만들어 다음을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f1ba0-121">User-defined activity tracing allows the user to create trace activities to:</span></span>  
  
- <span data-ttu-id="f1ba0-122">추적을 작업의 논리 단위로 그룹화합니다.</span><span class="sxs-lookup"><span data-stu-id="f1ba0-122">Group traces into logical units of work.</span></span>  
  
- <span data-ttu-id="f1ba0-123">전송과 전파를 통해 동작을 상호 연결합니다.</span><span class="sxs-lookup"><span data-stu-id="f1ba0-123">Correlate activities through transfers and propagation.</span></span>  
  
- <span data-ttu-id="f1ba0-124">WCF 추적의 성능 비용 (예: 로그 파일의 디스크 공간 비용)을 줄입니다.</span><span class="sxs-lookup"><span data-stu-id="f1ba0-124">Lessen the performance cost of WCF tracing (for example, the disk space cost of a log file).</span></span>  
  
 <span data-ttu-id="f1ba0-125">사용자 정의 작업 추적에 대 한 자세한 내용은 [추적 확장](extending-tracing.md) 샘플을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="f1ba0-125">For more information about user-defined activity trace, please see the [Extending Tracing](extending-tracing.md) sample.</span></span>  
  
## <a name="message-logging"></a><span data-ttu-id="f1ba0-126">메시지 로깅</span><span class="sxs-lookup"><span data-stu-id="f1ba0-126">Message Logging</span></span>  
 <span data-ttu-id="f1ba0-127">메시지 로깅은 WCF 응용 프로그램의 클라이언트 및 서비스 모두에서 사용 하도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f1ba0-127">Message logging can be enabled both on the client and service of any WCF application.</span></span> <span data-ttu-id="f1ba0-128">메시지 로깅을 사용하도록 설정하려면 클라이언트나 서비스에 다음 코드를 추가해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f1ba0-128">To enable message logging, you must add the following code to either the client or service:</span></span>  
  
```xml  
<configuration>  
  <system.serviceModel>  
    <diagnostics>  
      <!-- Enable Message Logging here. -->  
      <!-- log all messages received or sent at the transport or service model levels -->  
      <messageLogging logEntireMessage="true"  
                      maxMessagesToLog="300"  
                      logMessagesAtServiceLevel="true"  
                      logMalformedMessages="true"  
                      logMessagesAtTransportLevel="true" />  
    </diagnostics>  
  </system.serviceModel>  
</configuration>  
```  
  
 <span data-ttu-id="f1ba0-129">메시지가 기록될 때 클라이언트에서 추적되는지 아니면 서버에서 추적되는지 여부에 따라 추적 유형이 달라집니다.</span><span class="sxs-lookup"><span data-stu-id="f1ba0-129">When a message is recorded, the trace type depends on whether it is being traced at the client or the server.</span></span> <span data-ttu-id="f1ba0-130">예를 들어, 클라이언트에 보내지는 "추가" 메시지는 클라이언트에서는 "TransportWrite" 범주 아래에 추적되지만 서비스에서는 "TransportRead" 범주 아래에 추적됩니다.</span><span class="sxs-lookup"><span data-stu-id="f1ba0-130">For example, an "Add" message that is sent to a client is traced under the "TransportWrite" category at the client, whereas the same message is traced under the "TransportRead" category at the service.</span></span>  
  
 <span data-ttu-id="f1ba0-131">클라이언트의 App.config 파일이나 서비스의 Web.config 파일의 <xref:System.Diagnostics> 섹션에 다음 코드를 추가하여 추적 수신기를 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="f1ba0-131">Configure the trace listener by adding the following code to the <xref:System.Diagnostics> section of the client's App.config file or the service's Web.config file:</span></span>  
  
```xml  
<system.diagnostics>  
    <sources>  
      <source name="System.ServiceModel" switchValue="Information,ActivityTracing"  
        propagateActivity="true">  
        <listeners>  
          <add name="xml" />  
        </listeners>  
      </source>  
      <source name="System.ServiceModel.MessageLogging">  
        <listeners>  
          <add name="xml" />  
        </listeners>  
      </source>  
    </sources>  
    <sharedListeners>  
      <add initializeData="C:\logs\TracingAndLogging-client.svclog" type="System.Diagnostics.XmlWriterTraceListener"  
        name="xml" />  
    </sharedListeners>  
    <trace autoflush="true" />  
  </system.diagnostics>  
```  
  
 <span data-ttu-id="f1ba0-132">메시지는 구성 파일에 지정된 대상 디렉터리에 XML 형식으로 기록됩니다.</span><span class="sxs-lookup"><span data-stu-id="f1ba0-132">Messages are logged in XML format in the target directory specified in the configuration file.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="f1ba0-133">처음에 로그 디렉터리를 만들어야 추적 파일이 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="f1ba0-133">Trace files are not created without initially creating the log directory.</span></span> <span data-ttu-id="f1ba0-134">C:\logs\ 디렉터리가 있는지 확인하거나 수신기 구성에서 대체 로깅 디렉터리를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="f1ba0-134">Make sure that the directory C:\logs\ exists, or specify an alternate logging directory in the listener configuration.</span></span> <span data-ttu-id="f1ba0-135">자세한 내용은 이 문서의 끝에 있는 초기 설정 지침을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="f1ba0-135">See the initial setup instructions at the end of this document for more information.</span></span>  
  
 <span data-ttu-id="f1ba0-136">메시지 로깅에 대 한 자세한 내용은 [메시지 로깅 구성](../diagnostics/configuring-message-logging.md) 항목을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="f1ba0-136">For more information about message logging, see the [Configuring Message Logging](../diagnostics/configuring-message-logging.md) topic.</span></span>  
  
#### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="f1ba0-137">샘플을 설치, 빌드 및 실행하려면</span><span class="sxs-lookup"><span data-stu-id="f1ba0-137">To set up, build, and run the sample</span></span>  
  
1. <span data-ttu-id="f1ba0-138">[Windows Communication Foundation 샘플에 대 한 일회성 설치 절차](one-time-setup-procedure-for-the-wcf-samples.md)를 수행 했는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="f1ba0-138">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
2. <span data-ttu-id="f1ba0-139">Tracing and Message Logging 샘플을 실행하기 전에 .svclog 파일을 서비스에서 기록할 수 있도록 C:\logs\ 디렉터리를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="f1ba0-139">Before running the Tracing and Message Logging sample, create the directory C:\logs\ for the service to write the .svclog files to.</span></span> <span data-ttu-id="f1ba0-140">이 디렉터리의 이름은 추적 및 메시지를 기록하기 위한 경로로 구성 파일에 정의되며 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f1ba0-140">The name of this directory is defined in the configuration file as the path for the traces and messages to be logged and can be changed.</span></span> <span data-ttu-id="f1ba0-141">로그 디렉터리에 대한 Network Service 쓰기 권한을 사용자에게 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="f1ba0-141">Give the user Network Service write access to the logs directory.</span></span>  
  
3. <span data-ttu-id="f1ba0-142">C #, c + + 또는 Visual Basic .NET 버전의 솔루션을 빌드하려면 [Windows Communication Foundation 샘플 빌드](building-the-samples.md)의 지침을 따르세요.</span><span class="sxs-lookup"><span data-stu-id="f1ba0-142">To build the C#, C++, or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](building-the-samples.md).</span></span>  
  
4. <span data-ttu-id="f1ba0-143">단일 컴퓨터 또는 다중 컴퓨터 구성에서 샘플을 실행 하려면 [Windows Communication Foundation 샘플 실행](running-the-samples.md)의 지침을 따르세요.</span><span class="sxs-lookup"><span data-stu-id="f1ba0-143">To run the sample in a single- or cross-computer configuration, follow the instructions in [Running the Windows Communication Foundation Samples](running-the-samples.md).</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="f1ba0-144">컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f1ba0-144">The samples may already be installed on your computer.</span></span> <span data-ttu-id="f1ba0-145">계속하기 전에 다음(기본) 디렉터리를 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="f1ba0-145">Check for the following (default) directory before continuing.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> <span data-ttu-id="f1ba0-146">이 디렉터리가 없는 경우 [.NET Framework 4에 대 한 Windows Communication Foundation (wcf) 및 Windows Workflow Foundation (WF) 샘플](https://www.microsoft.com/download/details.aspx?id=21459) 로 이동 하 여 모든 WINDOWS COMMUNICATION FOUNDATION (wcf) 및 샘플을 다운로드 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 합니다.</span><span class="sxs-lookup"><span data-stu-id="f1ba0-146">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="f1ba0-147">이 샘플은 다음 디렉터리에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f1ba0-147">This sample is located in the following directory.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Management\TracingAndLogging`  
  
## <a name="see-also"></a><span data-ttu-id="f1ba0-148">참조</span><span class="sxs-lookup"><span data-stu-id="f1ba0-148">See also</span></span>

- [<span data-ttu-id="f1ba0-149">추적</span><span class="sxs-lookup"><span data-stu-id="f1ba0-149">Tracing</span></span>](../diagnostics/tracing/index.md)
- <span data-ttu-id="f1ba0-150">[AppFabric 모니터링 샘플](/previous-versions/appfabric/ff383407(v=azure.10))</span><span class="sxs-lookup"><span data-stu-id="f1ba0-150">[AppFabric Monitoring Samples](/previous-versions/appfabric/ff383407(v=azure.10))</span></span>
