---
title: 추적 및 메시지 로깅에 권장되는 설정
ms.date: 03/30/2017
ms.assetid: c6aca6e8-704e-4779-a9ef-50c46850249e
ms.openlocfilehash: 604aae2c0a0c5390428e7f1a2c99e17e90ee76a9
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79185726"
---
# <a name="recommended-settings-for-tracing-and-message-logging"></a><span data-ttu-id="ba424-102">추적 및 메시지 로깅에 권장되는 설정</span><span class="sxs-lookup"><span data-stu-id="ba424-102">Recommended Settings for Tracing and Message Logging</span></span>
<span data-ttu-id="ba424-103">이 항목에서는 다른 운영 환경에 권장되는 추적 및 메시지 로깅 설정에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="ba424-103">This topic describes recommended tracing and message logging settings for different operating environments.</span></span>  
  
## <a name="recommended-settings-for-a-production-environment"></a><span data-ttu-id="ba424-104">프로덕션 환경에 대한 권장 설정</span><span class="sxs-lookup"><span data-stu-id="ba424-104">Recommended Settings for a Production Environment</span></span>  
 <span data-ttu-id="ba424-105">WCF 추적 소스를 사용하는 경우 프로덕션 환경에 대해 `switchValue`를 Warning으로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="ba424-105">For a production environment, if you are using WCF trace sources, set the `switchValue` to Warning.</span></span> <span data-ttu-id="ba424-106">WCF `System.ServiceModel` 추적 소스를 사용하는 경우 `switchValue` 특성을 `Warning`, `propagateActivity` 특성을 `true`로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="ba424-106">If you are using the WCF `System.ServiceModel` trace source, set the `switchValue` attribute to `Warning` and the `propagateActivity` attribute to `true`.</span></span> <span data-ttu-id="ba424-107">사용자 정의 추적 소스를 사용하는 경우 `switchValue` 특성을 `Warning, ActivityTracing`으로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="ba424-107">If you are using a user-defined trace source, set the `switchValue` attribute to `Warning, ActivityTracing`.</span></span> <span data-ttu-id="ba424-108">이 작업은 [구성 편집기 도구(SvcConfigEditor.exe)를](../../../../../docs/framework/wcf/configuration-editor-tool-svcconfigeditor-exe.md)사용하여 수동으로 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ba424-108">This can be done manually using the [Configuration Editor Tool (SvcConfigEditor.exe)](../../../../../docs/framework/wcf/configuration-editor-tool-svcconfigeditor-exe.md).</span></span> <span data-ttu-id="ba424-109">성능 향상을 기대하지 않는 경우 앞에서 설명한 모든 경우에서 `switchValue` 특성을 `Information`으로 설정할 수 있습니다. 이렇게 하면 상당히 많은 추적 데이터가 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="ba424-109">If you do not anticipate a hit in performance, you can set the `switchValue` attribute to `Information` in all the previously mentioned cases, which generates a fairly large amount of trace data.</span></span> <span data-ttu-id="ba424-110">다음 예제에서는 이러한 권장 설정을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="ba424-110">The following example demonstrates these recommended settings.</span></span>  
  
```xml  
<configuration>  
 <system.diagnostics>  
  <sources>  
    <source name="System.ServiceModel"  
            switchValue="Warning"  
            propagateActivity="true" >  
      <listeners>  
        <add name="xml"/>  
      </listeners>  
    </source>  
    <source name="myUserTraceSource"  
            switchValue="Warning, ActivityTracing">  
      <listeners>  
        <add name="xml"/>  
      </listeners>  
    </source>  
  </sources>  
  <sharedListeners>  
    <add name="xml"  
         type="System.Diagnostics.XmlWriterTraceListener"  
               initializeData="C:\logs\Traces.svclog" />  
  </sharedListeners>  
 </system.diagnostics>  
  
<system.serviceModel>  
  <diagnostics wmiProviderEnabled="true">  
  </diagnostics>  
 </system.serviceModel>  
</configuration>  
```  
  
## <a name="recommended-settings-for-deployment-or-debugging"></a><span data-ttu-id="ba424-111">배포 또는 디버깅에 대한 권장 설정</span><span class="sxs-lookup"><span data-stu-id="ba424-111">Recommended Settings for Deployment or Debugging</span></span>  
 <span data-ttu-id="ba424-112">배포 또는 디버깅 환경의 경우 `Information` 또는 `Verbose`를 선택하고 사용자 정의 또는 `ActivityTracing` 추적 소스에 대해 `System.ServiceModel`을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="ba424-112">For deployment or debugging environment, choose `Information` or `Verbose`, along with `ActivityTracing` for either a user-defined or `System.ServiceModel` trace source.</span></span> <span data-ttu-id="ba424-113">디버깅을 향상시키려면 다른 추적 소스(`System.ServiceModel.MessageLogging`)를 구성에 추가하여 메시지 로깅을 활성화해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ba424-113">To enhance debugging, you should also add an additional trace source (`System.ServiceModel.MessageLogging`) to the configuration to enable message logging.</span></span> <span data-ttu-id="ba424-114">`switchValue` 특성은 이 추적 소스에 영향을 주지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ba424-114">Notice that the `switchValue` attribute has no impact on this trace source.</span></span>  
  
 <span data-ttu-id="ba424-115">다음 예제에서는 `XmlWriterTraceListener`를 이용하는 공유 수신기를 사용한 권장 설정을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="ba424-115">The following example demonstrates the recommended settings, using a shared listener that utilizes the `XmlWriterTraceListener`.</span></span>  
  
```xml  
<configuration>  
 <system.diagnostics>  
  <sources>  
    <source name="System.ServiceModel"  
            switchValue="Information, ActivityTracing"  
            propagateActivity="true" >  
      <listeners>  
        <add name="xml"/>  
      </listeners>  
    </source>  
    <source name="System.ServiceModel.MessageLogging">  
      <listeners>  
        <add name="xml"/>  
      </listeners>  
    </source>  
    <source name="myUserTraceSource"  
            switchValue="Information, ActivityTracing">  
      <listeners>  
        <add name="xml"/>  
      </listeners>  
    </source>  
  </sources>  
  <sharedListeners>  
    <add name="xml"  
         type="System.Diagnostics.XmlWriterTraceListener"  
               initializeData="C:\logs\Traces.svclog" />  
  </sharedListeners>  
 </system.diagnostics>  
  
 <system.serviceModel>  
  <diagnostics wmiProviderEnabled="true">  
      <messageLogging
           logEntireMessage="true"
           logMalformedMessages="true"  
           logMessagesAtServiceLevel="true"
           logMessagesAtTransportLevel="true"  
           maxMessagesToLog="3000"
       />  
  </diagnostics>  
 </system.serviceModel>  
</configuration>  
```  
  
## <a name="using-wmi-to-modify-settings"></a><span data-ttu-id="ba424-116">WMI를 사용하여 설정 수정</span><span class="sxs-lookup"><span data-stu-id="ba424-116">Using WMI to Modify Settings</span></span>  
 <span data-ttu-id="ba424-117">앞의 구성 예제와 같이 구성에서 `wmiProviderEnabled` 특성을 활성화하면 WMI를 사용하여 런타임에 구성 설정을 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ba424-117">You can use WMI to change configuration settings at runtime (by enabling the `wmiProviderEnabled` attribute in the configuration, as demonstrated in the previously configuration example).</span></span> <span data-ttu-id="ba424-118">예를 들어 CIM Studio 내에서 WMI를 사용하여 런타임에 추적 소스 수준을 Warning에서 Information으로 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ba424-118">For example, you can use WMI within the CIM Studio to change the trace source levels from Warning to Information at runtime.</span></span> <span data-ttu-id="ba424-119">이런 방식으로 라이브 디버깅을 사용하면 성능에 큰 영향을 줄 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ba424-119">You should be aware that the performance cost of live debugging in this way can be very high.</span></span> <span data-ttu-id="ba424-120">WMI 사용에 대한 자세한 내용은 [진단에 Windows 관리 계측 사용](../../../../../docs/framework/wcf/diagnostics/wmi/index.md) 항목을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="ba424-120">For more information about using WMI, see the [Using Windows Management Instrumentation for Diagnostics](../../../../../docs/framework/wcf/diagnostics/wmi/index.md) topic.</span></span>  
  
## <a name="enable-correlated-events-in-aspnet-tracing"></a><span data-ttu-id="ba424-121">ASP.NET 추적에서 상호 관련된 이벤트 사용</span><span class="sxs-lookup"><span data-stu-id="ba424-121">Enable Correlated Events in ASP.NET Tracing</span></span>  
 <span data-ttu-id="ba424-122">ASP.NET 이벤트 추적이 켜져 있지 않은 경우 ASP.NET 이벤트는 상관 관계 ID(ActivityID)를 설정하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ba424-122">ASP.NET events do not set the correlation ID (ActivityID) unless ASP.NET event tracing is turned on.</span></span> <span data-ttu-id="ba424-123">상호 관련된 이벤트를 제대로 보려면 명령 콘솔에서 다음 명령을 사용하여 추적하는 ASP.NET 이벤트를 켜야 하며, 이 명령은 **시작**, **실행** 및 **cmd**입력으로 이동하여 호출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ba424-123">To see correlated events properly, you have to turn on ASP.NET events tracing using the following command in the command console, which can be invoked by going to **Start**, **Run** and type **cmd**,</span></span>  
  
```console  
logman start mytrace -pf logman.providers -o test.etl –ets  
```  
  
 <span data-ttu-id="ba424-124">ASP.NET 이벤트 추적을 끄려면 다음 명령을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="ba424-124">To turn off tracing of ASP.NET events, use the following command,</span></span>  
  
```console
logman stop mytrace -ets  
```  
  
## <a name="see-also"></a><span data-ttu-id="ba424-125">참고 항목</span><span class="sxs-lookup"><span data-stu-id="ba424-125">See also</span></span>

- [<span data-ttu-id="ba424-126">진단에 Windows Management Instrumentation 사용</span><span class="sxs-lookup"><span data-stu-id="ba424-126">Using Windows Management Instrumentation for Diagnostics</span></span>](../../../../../docs/framework/wcf/diagnostics/wmi/index.md)
