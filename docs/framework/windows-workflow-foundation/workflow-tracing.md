---
title: 워크플로 추적
ms.date: 03/30/2017
ms.assetid: 18737989-0502-4367-b5f6-617ebfb77c96
ms.openlocfilehash: 92497768e7e8d720cdcc7c8f2c7c04b4dfcc47b4
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59224938"
---
# <a name="workflow-tracing"></a>워크플로 추적
워크플로 추적을 사용하면 .NET Framework 추적 수신기를 통해 진단 정보를 캡처할 수 있습니다. 추적은 응용 프로그램에서 문제가 발견되면 사용하도록 설정했다가 문제가 해결되면 다시 사용하지 않도록 설정할 수 있습니다. 워크플로에 대한 디버그 추적을 두 가지 방법으로 활성화할 수 있습니다. 이벤트 추적 뷰어를 사용하여 구성하거나 <xref:System.Diagnostics>를 사용하여 추적 이벤트를 파일로 보낼 수 있습니다.  
  
## <a name="enabling-debug-tracing-in-etw"></a>ETW에서 디버그 추적 사용  
 ETW를 사용하여 추적을 활성화하려면 이벤트 뷰어에서 디버그 채널을 사용하도록 설정합니다.  
  
1.  이벤트 뷰어에서 분석 및 디버그 로그 노드로 이동합니다.  
  
2.  이동할 이벤트 뷰어의 트리 뷰에서 **이벤트 뷰어-> 응용 프로그램 및 서비스 로그-> Microsoft-> Windows 응용 프로그램 서버-응용 프로그램->** 합니다. 마우스 오른쪽 단추로 클릭 **응용 프로그램 서버-응용 프로그램** 선택한 **분석 및 디버그 로그 표시 보기->** 합니다. 마우스 오른쪽 단추로 클릭 **디버깅할** 선택한 **로그 사용**합니다.  
  
3.  워크플로에서 디버그를 실행하고 추적을 ETW 디버그 채널로 내보낸 후 이벤트 뷰어에서 추적 내용을 볼 수 있습니다. 이동할 **이벤트 뷰어-> 응용 프로그램 및 서비스 로그-> Microsoft-> Windows 응용 프로그램 서버-응용 프로그램->** 합니다. 마우스 오른쪽 단추로 클릭 **디버깅할** 선택한 **새로 고침**합니다.  
  
4.  기본 분석 추적 버퍼 크기는 겨우 4KB이므로 이 크기를 32KB로 늘리는 것이 좋습니다. 이렇게 하려면 다음 단계를 수행합니다.  
  
    1.  현재 프레임 워크 디렉터리 (예를 들어 C:\Windows\Microsoft.NET\Framework\v4.0.21203)에서 다음 명령을 실행 합니다. `wevtutil um Microsoft.Windows.ApplicationServer.Applications.man`  
  
    2.  변경 된 \<bufferSize > 32 Windows.ApplicationServer.Applications.man 파일의 값입니다.  
  
        ```xml  
        <channel name="Microsoft-Windows-Application Server-Applications/Analytic" chid="ANALYTIC_CHANNEL" symbol="ANALYTIC_CHANNEL" type="Analytic" enabled="false" isolation="Application" message="$(string.MICROSOFT_WINDOWS_APPLICATIONSERVER_APPLICATIONS.channel.ANALYTIC_CHANNEL.message)" >  
                    <publishing>  
                      <bufferSize>32</bufferSize>  
                    </publishing>  
                  </channel>  
        ```  
  
    3.  현재 프레임 워크 디렉터리 (예를 들어 C:\Windows\Microsoft.NET\Framework\v4.0.21203)에서 다음 명령을 실행 합니다. `wevtutil im Microsoft.Windows.ApplicationServer.Applications.man`  
  
> [!NOTE]
>  .NET Framework 4 Client Profile을 사용 하는 경우.NET Framework 4 디렉터리에서 다음 명령을 실행 하 여 ETW 매니페스트를 먼저 등록 해야 합니다. `ServiceModelReg.exe –i –c:etw`  
  
## <a name="enabling-debug-tracing-using-systemdiagnostics"></a>System.Diagnostics를 사용하여 디버그 추적 활성화  
 이러한 수신기는 워크플로 응용 프로그램의 App.config 파일 또는 워크플로 서비스의 Web.config에서 구성할 수 있습니다. 이 예제는 [TextWriterTraceListener](https://go.microsoft.com/fwlink/?LinkId=165424) 현재 디렉터리의 MyTraceLog.txt 파일에 추적 정보를 저장 하도록 구성 됩니다.  
  
```xml  
<configuration>  
  <system.diagnostics>  
    <sources>  
      <source name="System.Activities" switchValue="Information">  
        <listeners>  
          <add name="textListener" />  
          <remove name="Default" />  
        </listeners>  
      </source>  
    </sources>  
    <sharedListeners>  
      <add name="textListener"  
           type="System.Diagnostics.TextWriterTraceListener"  
           initializeData="MyTraceLog.txt"  
           traceOutputOptions="ProcessId, DateTime" />  
    </sharedListeners>  
    <trace autoflush="true" indentsize="4">  
      <listeners>  
        <add name="textListener" />  
      </listeners>  
    </trace>  
  </system.diagnostics>  
</configuration>  
```  
  
## <a name="see-also"></a>참고자료

- [Windows Server App Fabric 모니터링](https://go.microsoft.com/fwlink/?LinkId=201273)
- [App Fabric을 사용 하 여 응용 프로그램 모니터링](https://go.microsoft.com/fwlink/?LinkId=201275)
