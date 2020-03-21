---
title: 성능 카운터 사용
ms.date: 03/30/2017
ms.assetid: 00a787af-1876-473c-a48d-f52b51e28a3f
ms.openlocfilehash: 7ffd9f5de5efb4be22968958246839e804daf23d
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79143579"
---
# <a name="using-performance-counters"></a>성능 카운터 사용
이 샘플에서는 WCF(Windows 통신 Foundation) 성능 카운터에 액세스하는 방법과 사용자 정의 성능 카운터를 만드는 방법을 보여 줍니다. 이 샘플은 [시작하기](../../../../docs/framework/wcf/samples/getting-started-sample.md)를 기반으로 합니다.  
  
> [!NOTE]
> 이 샘플의 설치 절차 및 빌드 지침은 이 항목의 끝부분에 나와 있습니다.  
  
 이 샘플에서 클라이언트는 `ICalculator` 서비스의 메서드 4개를 호출합니다. 클라이언트는 사용자가 중단할 때까지 이 작업을 계속 수행합니다. 서비스는 변경되지 않습니다.  
  
 성능 카운터는 다음 샘플 구성에 표시된 것과 같이 서비스에 대한 Web.config 파일의 진단 섹션에서 사용할 수 있습니다.  
  
```xml  
<configuration>  
  <system.serviceModel>  
    <diagnostics performanceCounters="All" />
  </system.serviceModel>  
</configuration>  
```  
  
 이 작업은 [구성 편집기 도구(SvcConfigEditor.exe)를](../../../../docs/framework/wcf/configuration-editor-tool-svcconfigeditor-exe.md)사용하여 수행할 수도 있습니다.  
  
 성능 카운터를 사용하도록 설정하면 서비스에 대해 전체 WCF 성능 카운터 제품군이 활성화됩니다. .NET Framework는 `ServiceModelService`, `ServiceModelEndpoint` 및 `ServiceModelOperation`의 세 가지 수준에서 성능 데이터를 자동으로 유지 관리합니다. 이러한 각 수준에는 "Calls", "Calls per Second" 및 "Security Calls Not Authorized"와 같은 성능 카운터가 있습니다.  
  
### <a name="to-set-up-build-and-run-the-sample"></a>샘플을 설치, 빌드 및 실행하려면  
  
1. Windows 통신 기초 [샘플에 대한 일회성 설치 절차를](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md)수행했어야 합니다.  
  
2. C# 또는 Visual Basic .NET 버전의 솔루션을 빌드하려면 [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md)의 지침을 따릅니다.  
  
3. 단일 또는 컴퓨터 간 구성에서 샘플을 실행하려면 Windows [통신 기반 샘플 실행의 지침을 따르십시오.](../../../../docs/framework/wcf/samples/running-the-samples.md)  
  
### <a name="to-view-performance-data"></a>성능 데이터를 보려면  
  
1. 시작 **,** **실행,** `perfmon` **입력** 및 확인을 클릭하거나 제어판에서 관리 **도구를** 선택하고 **성능을**두 번 클릭하여 성능 모니터 도구를 시작합니다.  
  
    > [!NOTE]
    > 샘플 코드가 실행될 때까지는 카운터를 추가할 수 없습니다.  
  
2. 나열된 성능 카운터를 선택한 다음 Delete 키를 누르면 성능 카운터를 제거할 수 있습니다.  
  
3. 그래프 창을 마우스 오른쪽 단추로 클릭하고 카운터 추가를 선택하여 WCF **카운터를 추가합니다.** 카운터 **추가** 대화 상자에서 **ServiceModelOperation 3.0.0.0, ServiceModelEndpoint 3.0.0.0 또는 ServiceModelService 3.0.0.0을** 성능 개체 드롭다운 목록 상자에서 선택합니다. 목록에서 보려는 카운터를 선택합니다.  
  
    > [!NOTE]
    > 컴퓨터에서 실행 중인 WCF 서비스가 없는 경우 서비스에 대한 WCF 성능 카운터가 없습니다.  
  
### <a name="to-use-the-configuration-editor-to-enable-counters"></a>Configuration Editor를 사용하여 카운터를 사용하려면  
  
1. SvcConfigEditor.exe의 인스턴스를 엽니다.  
  
2. 파일 메뉴에서 **열기를** 클릭한 다음 **구성 파일을 클릭합니다...**  
  
3. 샘플 애플리케이션의 서비스 폴더로 이동한 다음 Web.config 파일을 엽니다.  
  
4. 구성 트리에서 **진단을 클릭합니다.**  
  
5. 진단 창에서 **성능 카운터를** 전환하여 '모두'를 **표시합니다.**  
  
6. 구성 파일을 저장하고 편집기를 끝냅니다.  
  
> [!IMPORTANT]
> 컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다. 계속하기 전에 다음(기본) 디렉터리를 확인하세요.  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> 이 디렉터리가 없는 경우 [.NET Framework 4에 대한 WCF(Windows 통신 재단) 및 WF(Windows 워크플로우 재단) 샘플로](https://www.microsoft.com/download/details.aspx?id=21459) 이동하여 모든 WCF(Windows 통신 재단) 및 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 샘플을 다운로드합니다. 이 샘플은 다음 디렉터리에 있습니다.  
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Management\PerfCounters`  
  
## <a name="see-also"></a>참고 항목

- [AppFabric 모니터링 샘플](https://docs.microsoft.com/previous-versions/appfabric/ff383407(v=azure.10))
