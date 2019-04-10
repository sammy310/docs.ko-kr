---
title: Windows Service 호스트
ms.date: 03/30/2017
helpviewer_keywords:
- NT Service
- NT Service Host Sample [Windows Communication Foundation]
ms.assetid: 1b2f45c5-2bed-4979-b0ee-8f9efcfec028
ms.openlocfilehash: 85d089813a455784fde679e9200a9b29b956af8e
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/09/2019
ms.locfileid: "59338698"
---
# <a name="windows-service-host"></a>Windows Service 호스트
이 샘플에서는 관리 되는 Windows 서비스에서 호스팅되는 Windows Communication Foundation (WCF) 서비스를 보여 줍니다. Windows 서비스의 서비스 애플릿을 사용 하 여 제어 됩니다 **제어판** 시스템 다시 부팅 후 자동으로 시작 되도록 구성할 수 있습니다. 이 샘플은 클라이언트 프로그램과 Windows 서비스 프로그램으로 구성됩니다. 서비스는 .exe 프로그램으로 구현되고 자체 호스팅 코드가 포함됩니다. WAS(Windows Process Activation Services) 또는 IIS(인터넷 정보 서비스) 등의 다른 호스팅 환경에서는 직접 호스팅 코드를 작성할 필요가 없습니다.

> [!NOTE]
>  이 샘플의 설치 절차 및 빌드 지침은 이 항목의 끝부분에 나와 있습니다.

> [!IMPORTANT]
>  컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다. 계속하기 전에 다음(기본) 디렉터리를 확인하세요.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  이 디렉터리가 없으면로 이동 [Windows Communication Foundation (WCF) 및.NET Framework 4 용 Windows WF (Workflow Foundation) 샘플](https://go.microsoft.com/fwlink/?LinkId=150780) 모든 Windows Communication Foundation (WCF)를 다운로드 하 고 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 샘플. 이 샘플은 다음 디렉터리에 있습니다.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Services\Hosting\WindowsService`  
  
 이 서비스를 빌드한 후에는 다른 Windows 서비스와 마찬가지로 Installutil.exe 유틸리티로 설치해야 합니다. 서비스를 변경하려는 경우에는 먼저 `installutil /u`를 사용하여 제거해야 합니다. 이 샘플에 포함된 Setup.bat 및 Cleanup.bat 파일은 Windows 서비스를 설치 및 시작하기 위한 명령과 Windows 서비스를 종료 및 제거하기 위한 명령입니다. Windows 서비스가 실행 되 고 WCF 서비스 클라이언트에 응답만 수 있습니다. 서비스 애플릿을 사용 하 여 Windows 서비스를 중지 하는 경우 **Control Panel** 클라이언트를 실행 하 고는 <xref:System.ServiceModel.EndpointNotFoundException> 클라이언트 서비스에 액세스 하려고 하면 예외가 발생 합니다. Windows 서비스를 다시 시작하고 클라이언트를 다시 실행하면 통신이 성공합니다.  
  
 서비스 코드에는 설치 관리자 클래스, ICalculator 계약을 구현 하는 WCF 서비스 구현 클래스 및 런타임 호스트로 사용 되는 Windows 서비스 클래스를 포함 합니다. <xref:System.Configuration.Install.Installer>에서 상속되는 설치 관리자 클래스를 사용하면 프로그램을 Installutil.exe 도구를 통해 NT 서비스로 설치할 수 있습니다. 서비스 구현 클래스 `WcfCalculatorService`, 기본 서비스 계약을 구현 하는 WCF 서비스입니다. 이 WCF 서비스 라는 Windows 서비스 클래스 내에서 호스팅되는 `WindowsCalculatorService`합니다. Windows 서비스로 정규화하기 위해 클래스가 <xref:System.ServiceProcess.ServiceBase>에서 상속되고 <xref:System.ServiceProcess.ServiceBase.OnStart%28System.String%5B%5D%29> 및 <xref:System.ServiceProcess.ServiceBase.OnStop> 메서드를 구현합니다. <xref:System.ServiceProcess.ServiceBase.OnStart%28System.String%5B%5D%29>에서 <xref:System.ServiceModel.ServiceHost> 개체가 `WcfCalculatorService` 형식에 대해 만들어지고 열립니다. <xref:System.ServiceProcess.ServiceBase.OnStop>에서 ServiceHost는 <xref:System.ServiceModel.Channels.CommunicationObject.Close%28System.TimeSpan%29> 개체의 <xref:System.ServiceModel.ServiceHost> 메서드를 호출하여 닫습니다. 호스트의 기본 주소를 사용 하 여 구성 된 합니다 [ \<추가 >](../../../../docs/framework/configure-apps/file-schema/wcf/add-of-baseaddresses.md) 자식 요소의 [ \<baseAddresses >](../../../../docs/framework/configure-apps/file-schema/wcf/baseaddresses.md)의 자식인는 [ \<호스트 >](../../../../docs/framework/configure-apps/file-schema/wcf/host.md) 자식 요소의 합니다 [ \<서비스 >](../../../../docs/framework/configure-apps/file-schema/wcf/service.md) 요소입니다.  
  
 정의 된 끝점에서는 기본 주소와 [ \<wsHttpBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md)합니다. 다음 샘플에서는 CalculatorService를 노출시키는 엔드포인트와 기본 주소의 구성을 보여 줍니다.  
  
```xml  
<services>  
  <service name="Microsoft.ServiceModel.Samples.WcfCalculatorService"  
           behaviorConfiguration="CalculatorServiceBehavior">  
    <host>  
      <baseAddresses>  
        <add baseAddress="http://localhost:8000/ServiceModelSamples/service"/>  
      </baseAddresses>  
    </host>  
    <!-- This endpoint is exposed at the base address provided by host: http://localhost:8000/ServiceModelSamples/service.  -->  
    <endpoint address=""  
              binding="wsHttpBinding"  
              contract="Microsoft.ServiceModel.Samples.ICalculator" />  
    ...  
  </service>  
</services>  
```  
  
 샘플을 실행하면 작업 요청 및 응답이 서비스와 클라이언트 콘솔 창 모두에 표시됩니다. 서비스와 클라이언트를 종료하려면 각 콘솔 창에서 Enter 키를 누릅니다.  
  
### <a name="to-set-up-build-and-run-the-sample"></a>샘플을 설치, 빌드 및 실행하려면  
  
1. 수행 했는지 확인 합니다 [Windows Communication Foundation 샘플에 대 한 일회성 설치 절차](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md)합니다.  
  
2. C# 또는 Visual Basic .NET 버전의 솔루션을 빌드하려면 [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md)의 지침을 따릅니다.  
  
3. 후 솔루션을 빌드한 Installutil.exe 도구를 사용 하 여 Windows 서비스를 설치 하려면 상승된 된 Visual Studio 2012 명령 프롬프트에서 Setup.bat를 실행 합니다. 서비스가 서비스에 표시됩니다.  
  
4. 단일 컴퓨터 또는 다중 컴퓨터 구성에서 샘플을 실행 하려면의 지침을 따릅니다 [Windows Communication Foundation 샘플 실행](../../../../docs/framework/wcf/samples/running-the-samples.md)합니다.  
  
## <a name="see-also"></a>참고자료

- [AppFabric 호스팅 및 지속성 샘플](https://go.microsoft.com/fwlink/?LinkId=193961)
