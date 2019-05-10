---
title: 추적 구성
ms.date: 03/30/2017
helpviewer_keywords:
- tracing [WCF]
ms.assetid: 82922010-e8b3-40eb-98c4-10fc05c6d65d
ms.openlocfilehash: 8c8d4e45035a49a35c32f334895eeae27a1f02a1
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/28/2019
ms.locfileid: "64656196"
---
# <a name="configuring-tracing"></a>추적 구성
이 항목에서는 추적을 사용하고, 추적을 내보내도록 추적 소스를 구성하고, 추적 수준을 설정하고, 종단 간 추적 상관 관계를 지원하도록 동작 추적 및 전파를 설정하고, 추적에 액세스하도록 추적 수신기를 설정하는 방법에 대해 설명합니다.  
  
 프로덕션 또는 디버깅 환경에서 추적 설정 권장 사항에 대 한 참조 [추적 및 메시지 로깅에 대 한 권장 설정](../../../../../docs/framework/wcf/diagnostics/tracing/recommended-settings-for-tracing-and-message-logging.md)합니다.  
  
> [!IMPORTANT]
>  Windows 8에서 응용 프로그램이 추적 로그를 생성할 수 있도록 하려면 응용 프로그램을 승격된 상태(관리자 권한으로 실행)로 실행해야 합니다.  
  
## <a name="enabling-tracing"></a>추적 사용  
 Windows Communication Foundation (WCF) 진단 추적에 대 한 다음 데이터를 출력합니다.  
  
- 작업 호출, 코드 예외, 경고 및 기타 중요 처리 이벤트 등과 같이 응용 프로그램의 모든 구성 요소에서 프로세스 중요 시점에 대한 추적  
  
- 추적 기능 오작동 시 Windows 오류 이벤트. 참조 [이벤트 로깅](../../../../../docs/framework/wcf/diagnostics/event-logging/index.md)합니다.  
  
 WCF 추적의 맨 위에 빌드되 <xref:System.Diagnostics>합니다. 추적을 사용하려면 구성 파일 또는 코드에 추적 소스를 정의해야 합니다. WCF는 각 WCF 어셈블리에 대 한 추적 소스를 정의 합니다. `System.ServiceModel` 추적 소스는 가장 일반적인 WCF 추적 소스 이며 WCF 통신 스택, 사용자 코드 시작/종료를 시작/종료에서 전송에서 처리 중요 시점을 기록 합니다. `System.ServiceModel.MessageLogging` 추적 소스는 시스템을 통해 이동하는 모든 메시지를 기록합니다.  
  
 추적은 기본적으로 사용되지 않습니다. 추적을 활성화 하려면 추적 수신기 만들기 및 구성;에서 "꺼짐" 선택한 추적 소스에 이외의 추적 수준을 설정 해야 합니다. 그렇지 않은 경우 WCF는 모든 추적을 생성 하지 않습니다. 수신기를 지정하지 않으면 추적이 자동으로 사용되지 않습니다. 수신기는 정의되었지만 수준이 지정되지 않은 경우 수준이 기본적으로 "Off"로 설정됩니다. 이 설정은 추적이 내보내지지 않음을 의미합니다.  
  
 사용자 지정 작업 호출자와 같은 WCF 확장성 지점을 사용 하는 경우에 추적을 직접 내보내야 합니다. 즉, WCF 확장성 지점을 구현 하는 경우 기본 경로에서 표준 추적을 내보낼 더 이상 수 없습니다. 추적을 내보내 수동 추적 지원을 구현하지 않으면 예상하는 추적이 표시되지 않을 수 있습니다.  
  
 응용 프로그램의 구성 파일(웹에 호스팅된 응용 프로그램의 경우 Web.config, 자체 호스팅 응용 프로그램의 경우 Appname.exe.config)을 편집하여 추적을 구성할 수 있습니다. 다음은 이러한 편집의 예제입니다. 이러한 설정에 대 한 자세한 내용은 "구성 추적 수신기에 추적을 사용" 섹션을 참조 하세요.  
  
```xml  
<configuration>  
   <system.diagnostics>  
      <sources>  
            <source name="System.ServiceModel"   
                    switchValue="Information, ActivityTracing"  
                    propagateActivity="true">  
            <listeners>  
               <add name="traceListener"   
                   type="System.Diagnostics.XmlWriterTraceListener"   
                   initializeData= "c:\log\Traces.svclog" />  
            </listeners>  
         </source>  
      </sources>  
   </system.diagnostics>  
</configuration>  
```  
  
> [!NOTE]
>  Visual Studio에서 WCF 서비스 프로젝트의 구성 파일을 편집 하려면 응용 프로그램의 구성 파일을 클릭 마우스 오른쪽 단추로-자체 호스팅된 응용 프로그램의 경우 appname.exe.config 웹 호스팅 응용 프로그램의 경우 Web.config **솔루션 탐색기** . 선택 합니다 **WCF 구성 편집** 상황에 맞는 메뉴 항목입니다. 그러면 합니다 [Configuration Editor 도구 (SvcConfigEditor.exe)](../../../../../docs/framework/wcf/configuration-editor-tool-svcconfigeditor-exe.md), 그래픽 사용자 인터페이스를 사용 하 여 WCF 서비스에 대 한 구성 설정을 수정할 수 있습니다.  
  
## <a name="configuring-trace-sources-to-emit-traces"></a>추적을 내보내도록 추적 소스 구성  
 WCF는 각 어셈블리에 대 한 추적 소스를 정의 합니다. 어셈블리 내에 생성된 추적은 해당 소스에 대해 정의된 수신기를 통해 액세스합니다. 다음 추적 소스가 정의됩니다.  
  
- System.ServiceModel: WCF 때마다 처리 하는 모든 단계의 로그 구성을 읽을, 전송에서 된 메시지를 처리 하는 사용자 코드에서 보안 처리 메시지를 디스패치 됩니다.  
  
- System.ServiceModel.MessageLogging: 시스템을 통해 이동 하는 모든 메시지를 기록 합니다.  
  
- System.IdentityModel  
  
- System.ServiceModel.Activation  
  
- System.IO.Log: .NET Framework 인터페이스에는 로그 파일 시스템 CLFS (Common)에 대 한 로깅입니다.  
  
- System.Runtime.Serialization: 개체는 읽거나 쓸 때 기록 합니다.  
  
- CardSpace  
  
 다음 구성 예제에 표시된 대로 같은(공유) 수신기를 사용하도록 각 추적 소스를 구성할 수 있습니다.  
  
```xml  
<configuration>  
    <system.diagnostics>  
        <sources>  
            <source name="System.ServiceModel"   
                    switchValue="Information, ActivityTracing"  
                    propagateActivity="true">  
                <listeners>  
                    <add name="xml" />  
                </listeners>  
            </source>  
            <source name="CardSpace">  
                <listeners>  
                    <add name="xml" />  
                </listeners>  
            </source>  
            <source name="System.IO.Log">  
                <listeners>  
                    <add name="xml" />  
                </listeners>  
            </source>  
            <source name="System.Runtime.Serialization">  
                <listeners>  
                    <add name="xml" />  
                </listeners>  
            </source>  
            <source name="System.IdentityModel">  
                <listeners>  
                    <add name="xml" />  
                </listeners>  
            </source>  
        </sources>  
  
        <sharedListeners>  
            <add name="xml"  
                 type="System.Diagnostics.XmlWriterTraceListener"  
                 initializeData="c:\log\Traces.svclog" />  
        </sharedListeners>  
    </system.diagnostics>  
</configuration>  
```  
  
 또한, 다음 예제처럼 사용자 정의 추적 소스를 추가하여 사용자 코드 추적을 내보낼 수 있습니다.  
  
```xml  
<system.diagnostics>  
   <sources>  
       <source name="UserTraceSource" switchValue="Warning, ActivityTracing" >  
          <listeners>  
              <add name="xml"  
                 type="System.Diagnostics.XmlWriterTraceListener"  
                 initializeData="C:\logs\UserTraces.svclog" />  
          </listeners>  
       </source>  
   </sources>  
   <trace autoflush="true" />   
</system.diagnostics>  
```  
  
 사용자 정의 추적 소스를 만드는 방법에 대 한 자세한 내용은 참조 하세요. [추적 확장](../../../../../docs/framework/wcf/samples/extending-tracing.md)합니다.  
  
## <a name="configuring-trace-listeners-to-consume-traces"></a>추적을 사용하도록 추적 수신기 구성  
 런타임에 WCF는 데이터를 처리 하는 수신기에 추적 데이터를 피드 합니다. 에 대 한 몇 가지 미리 정의 된 수신기를 제공 하는 WCF <xref:System.Diagnostics>, 출력에 대 한 사용 하는 형식은에서 다를 수 있음. 사용자 지정 수신기 형식을 추가할 수도 있습니다.  
  
 `add`를 사용하여 사용할 추적 수신기의 이름과 형식을 지정할 수 있습니다. 예제 구성에서는 수신기 이름을 `traceListener`로 지정하고 표준 .NET Framework 추적 수신기(`System.Diagnostics.XmlWriterTraceListener`)를 사용할 형식으로 추가했습니다. 각 소스에 대한 추적 수신기를 여러 개 추가할 수 있습니다. 추적 수신기가 파일로 추적을 내보내는 경우에는 구성 파일에 출력 파일 위치와 이름을 지정해야 합니다. 이 작업을 수행하려면 `initializeData`를 해당 수신기의 파일 이름으로 설정합니다. 파일 이름을 지정하지 않으면 사용된 수신기 형식에 따라 임의 파일 이름이 생성됩니다. <xref:System.Diagnostics.XmlWriterTraceListener>가 사용되면 확장명이 없는 파일 이름이 생성됩니다. 사용자 지정 수신기를 구현하는 경우 이 특성을 사용하여 파일 이름 이외의 초기화 데이터를 받을 수도 있습니다. 예를 들면 이 특성에 대한 데이터베이스 식별자를 지정할 수 있습니다.  
  
 원격 데이터베이스와 같은 연결을 통해 추적을 보내도록 사용자 지정 추적 수신기를 구성할 수 있습니다. 응용 프로그램 배포자인 경우 원격 컴퓨터의 추적 로그에 적절한 액세스 제어를 적용해야 합니다.  
  
 추적 수신기를 프로그래밍 방식으로 구성할 수도 있습니다. 자세한 내용은 [방법: 추적 수신기 만들기 및 초기화](https://go.microsoft.com/fwlink/?LinkId=94648) 하 고 [사용자 지정 TraceListener 만들기](https://go.microsoft.com/fwlink/?LinkId=96239)합니다.  
  
> [!CAUTION]
>  `System.Diagnostics.XmlWriterTraceListener`는 스레드로부터 안전하지 않으므로 추적을 출력할 때 추적 소스가 리소스를 단독으로 잠글 수도 있습니다. 여러 스레드에서 이 수신기를 사용하도록 구성된 추적 소스로 추적을 출력하면 리소스 경합이 발생할 수 있으며, 이로 인해 성능이 크게 저하될 수 있습니다. 이 문제를 해결하려면 스레드로부터 안전한 사용자 지정 수신기를 구현해야 합니다.  
  
## <a name="trace-level"></a>추적 수준  
 추적 수준은 추적 소스의 `switchValue` 설정에 의해 제어됩니다. 다음 표에서는 사용할 수 있는 추적 수준에 대해 설명합니다.  
  
|추적 수준|추적 이벤트의 특성|추적 이벤트의 내용|추적 이벤트|사용자 대상|  
|-----------------|----------------------------------|-----------------------------------|--------------------|-----------------|  
|끄기|N/A|N/A|내보낸 추적이 없습니다.|N/A|  
|중요|"Negative" 이벤트: 예기치 않은 처리 또는 오류 조건을 나타내는 이벤트입니다.||다음을 포함하여 처리되지 않은 예외를 기록합니다.<br /><br /> -   OutOfMemoryException<br />-ThreadAbortException (CLR이 threadabortexceptionhandler)<br />-StackOverflowException (낼 수 없습니다)<br />-   ConfigurationErrorsException<br />-   SEHException<br />-응용 프로그램 시작 오류<br />-Failfast 이벤트<br />시스템 중지<br />포이즌 메시지: 응용 프로그램 오류가 발생 하는 추적 메시지입니다.|관리자<br /><br /> 응용 프로그램 개발자|  
|Error|"Negative" 이벤트: 예기치 않은 처리 또는 오류 조건을 나타내는 이벤트입니다.|예기치 않은 처리가 발생했습니다. 응용 프로그램이 예상한 대로 작업을 수행하지 못했습니다. 그러나 응용 프로그램이 여전히 실행 중입니다.|모든 예외가 기록됩니다.|관리자<br /><br /> 응용 프로그램 개발자|  
|경고|"Negative" 이벤트: 예기치 않은 처리 또는 오류 조건을 나타내는 이벤트입니다.|문제가 발생했거나 발생할 수도 있지만 응용 프로그램이 여전히 올바르게 작동합니다. 그러나 계속 올바르게 작동하지 않을 수도 있습니다.|-응용 프로그램이 해당 스로틀 설정이 허용 하는 것 보다 많은 요청 받고 있습니다.<br />-구성된 된 최대 용량 거의 수신 큐가 있습니다.<br />제한 시간을 초과 했습니다.<br />자격 증명 거부 됩니다.|관리자<br /><br /> 응용 프로그램 개발자|  
|정보|"Positive" 이벤트: 성공적인 중요 시점을 표시 하는 이벤트|응용 프로그램이 올바르게 작동하는지 여부에 관계 없이 응용 프로그램 실행의 중요한 중요 시점과 성공적인 중요 시점입니다.|일반적으로 시스템 상태 모니터링 및 진단, 성능 측정 또는 프로파일링에 유용한 메시지가 생성됩니다. 용량 계획 및 성능 관리에 이러한 정보를 사용할 수 있습니다.<br /><br /> -채널 생성 됩니다.<br />끝점 수신기가 생성 됩니다.<br />메시지 전송 시작/종료 합니다.<br />보안 토큰이 검색 됩니다.<br />구성 설정을 읽습니다.|관리자<br /><br /> 응용 프로그램 개발자<br /><br /> 제품 개발자|  
|자세히|"Positive" 이벤트: 성공적인 중요 시점을 표시 하는 이벤트입니다.|사용자 코드와 서비스에 대한 하위 수준 이벤트를 내보냅니다.|일반적으로 디버깅 또는 응용 프로그램 최적화에 이 수준을 사용할 수 있습니다.<br /><br /> -메시지 헤더를 확인 합니다.|관리자<br /><br /> 응용 프로그램 개발자<br /><br /> 제품 개발자|  
|ActivityTracing||처리 동작과 구성 요소 간의 흐름 이벤트입니다.|이 수준에서 관리자와 개발자가 같은 응용 프로그램 도메인의 응용 프로그램을 서로 연결할 수 있습니다.<br /><br /> -시작/중지와 같은 동작 경계 추적 합니다.<br />-전송에 대 한 추적 합니다.|모두|  
|모두||응용 프로그램이 올바르게 작동할 수 있습니다. 모든 이벤트를 내보냅니다.|앞의 이벤트 모두|모두|  
  
 Verbose에서 Critical까지의 수준은 서로 위에 쌓입니다. 즉, 각 추적 수준에 Off 수준을 제외한 위의 모든 수준이 포함됩니다. 예를 들어, Warning 수준에서 수신 대기하는 수신기는 Critical, Error 및 Warning 추적을 수신합니다. 모두 수준에는 Verbose에서 Critical까지의 이벤트와 동작 추적 이벤트가 포함됩니다.  
  
> [!CAUTION]
>  Information, Verbose 및 ActivityTracing 수준은 컴퓨터에서 사용 가능한 모든 리소스를 모두 사용한 경우 메시지 처리량을 줄일 수도 있는 여러 가지 추적을 생성합니다.  
  
## <a name="configuring-activity-tracing-and-propagation-for-correlation"></a>상관 관계를 위한 동작 추적 및 전파 구성  
 `activityTracing` 특성에 대한 지정된 `switchValue` 값은 엔드포인트 내에서 동작 경계와 전송에 대한 추적을 내보내는 동작 추적을 활성화하는 데 사용됩니다.  
  
> [!NOTE]
>  WCF의 특정 확장성 기능을 사용 하면 발생할 수 있습니다는 <xref:System.NullReferenceException> 동작 추적을 활성화 한 경우. 이 문제를 해결하려면 응용 프로그램의 구성 파일을 확인하고 추적 소스의 `switchValue` 특성이 `activityTracing`으로 설정되지 않았는지 확인합니다.  
  
 `propagateActivity` 특성은 동작을 메시지 교환에 참여하는 다른 엔드포인트에 전파해야 하는지 여부를 나타냅니다. 이 값을 `true`로 설정하여 두 엔드포인트에서 생성된 추적 파일을 가져오고 한 엔드포인트의 추적 집합이 다른 엔드포인트의 추적 집합으로 이동한 방법을 확인할 수 있습니다.  
  
 동작 추적 및 전파 하는 방법에 대 한 자세한 내용은 참조 하세요. [전파](../../../../../docs/framework/wcf/diagnostics/tracing/propagation.md)합니다.  
  
 둘 다 `propagateActivity` 고 `ActivityTracing` System.ServiceModel TraceSource에 적용 된 부울 값입니다. `ActivityTracing` 값 WCF 또는 사용자 정의 헤더를 포함 하 여 모든 추적 소스에도 적용 됩니다.  
  
 `propagateActivity` 특성은 사용자 정의 추적 소스에 사용할 수 없습니다. 사용자 코드 동작 ID 전파를 위해 ServiceModel `ActivityTracing`은 설정하지 않고 ServiceModel `propagateActivity` 특성은 `true`로 설정해야 합니다.  
  
## <a name="see-also"></a>참고자료

- [추적](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)
- [관리 및 진단](../../../../../docs/framework/wcf/diagnostics/index.md)
- [방법: 추적 수신기 만들기 및 초기화](https://go.microsoft.com/fwlink/?LinkId=94648)
- [사용자 지정 TraceListener 만들기](https://go.microsoft.com/fwlink/?LinkId=96239)
