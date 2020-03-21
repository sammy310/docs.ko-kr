---
title: WMI 공급자
ms.date: 03/30/2017
ms.assetid: 462f0db3-f4a4-4a4b-ac26-41fc25c670a4
ms.openlocfilehash: 04fdbb7efcae6fdbb78f467352e6106ac5218799
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79183198"
---
# <a name="wmi-provider"></a>WMI 공급자
이 샘플에서는 WCF에 기본 제공된 WMI(Windows 관리 계측) 공급자를 사용하여 런타임에 WCF(Windows 통신 Foundation) 서비스에서 데이터를 수집하는 방법을 보여 줍니다. 또한 사용자 정의 WMI 개체를 서비스에 추가하는 방법도 보여 줍니다. 이 샘플은 [시작하기에](../../../../docs/framework/wcf/samples/getting-started-sample.md) 대한 WMI 공급자를 활성화하고 런타임시 `ICalculator` 서비스에서 데이터를 수집하는 방법을 보여 줍니다.  
  
 WMI는 Microsoft에서 구현한 WBEM(Web-Based Enterprise Management) 표준입니다. WMI SDK에 대한 자세한 내용은 [Windows 관리 계측](/windows/desktop/WmiSdk/wmi-start-page)을 참조하십시오. WBEM은 애플리케이션에서 외부 관리 도구에 관리 계측을 노출하는 방법을 지정하는 산업 표준입니다.  
  
 WCF는 WBEM 호환 인터페이스를 통해 런타임시 계측을 노출하는 구성 요소인 WMI 공급자를 구현합니다. 관리 도구는 런타임에 인터페이스를 통해 서비스에 연결될 수 있습니다. WCF는 주소, 바인딩, 동작 및 리스너와 같은 서비스의 특성을 노출합니다.  
  
 기본 제공 WMI 공급자는 애플리케이션의 구성 파일에서 활성화합니다. 이 작업은 다음 `wmiProviderEnabled` 샘플 구성과 같이 [ \<system.serviceModel>](../../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel.md) 섹션에 [ \<>진단](../../../../docs/framework/configure-apps/file-schema/wcf/diagnostics.md) 특성을 통해 수행됩니다.  
  
```xml  
<system.serviceModel>  
    ...  
    <diagnostics wmiProviderEnabled="true" />  
    ...  
</system.serviceModel>  
```  
  
 이 구성 항목은 WMI 인터페이스를 노출합니다. 관리 애플리케이션이 이 인터페이스를 통해 연결하여 애플리케이션의 관리 계측에 액세스할 수 있습니다.  
  
## <a name="custom-wmi-object"></a>사용자 지정 WMI 개체  
 서비스에 WMI 개체를 추가하면 기본 제공 WMI 공급자 정보와 함께 사용자 정의 정보를 표시할 수 있습니다. 그러려면 Installutil.exe 애플리케이션을 사용하여 WMI에 서비스의 스키마를 게시합니다. 이 작업을 수행하기 위한 지침과 자세한 설명은 항목 끝 부분에 있는 설치 지침을 참조하십시오.  
  
## <a name="accessing-wmi-information"></a>WMI 정보 액세스  

다양한 방식으로 WMI 데이터에 액세스할 수 있습니다. Microsoft는 스크립트, 시각적 기본 응용 프로그램, C++ 응용 프로그램 및 .NET 프레임워크에 대해 WMI API를 제공합니다. 자세한 내용은 [WMI 사용](/windows/desktop/wmisdk/using-wmi)을 참조하십시오.
  
 이 샘플에서는 두 개의 Java 스크립트를 사용합니다. 하나는 컴퓨터에서 실행 중인 서비스를 속성과 함께 나열하고, 다른 하나는 사용자 정의 WMI 데이터를 표시합니다. 스크립트에서는 WMI 공급자에 대한 연결을 열고, 데이터를 구문 분석하고, 수집된 데이터를 표시합니다.  
  
 샘플을 시작하여 WCF 서비스의 실행 중인 인스턴스를 만듭니다. 서비스가 실행 중인 동안 명령 프롬프트에서 다음 명령을 사용하여 각 Java 스크립트를 실행합니다.  
  
```console  
cscript EnumerateServices.js  
```  
  
 스크립트에서는 서비스에 포함된 계측에 액세스하여 다음 출력을 생성합니다.  
  
```console  
Microsoft (R) Windows Script Host Version 5.6  
Copyright © Microsoft Corporation 1996-2001. All rights reserved.  
  
1 service(s) found.  
|-PID:           5776  
|-DistinguishedName:  CalculatorService@http://localhost/ServiceModelSamples/service.svc  
|-Endpoints:     1 endpoints  
  |-CalculatorService.ICalculator@http://localhost/ServiceModelSamples/service.svc  
    |-Address:                        http://localhost/ServiceModelSamples/service.svc  
    |-CounterInstanceName:  
    |-AddressHeaders:                 0  
    |-ContractType:                   Contract.Name='ICalculator'  
    |-BindingElements:                4 bindings  
      |-BindingElements[0]  
        |-Type:                       TransactionFlowBindingElement  
      |-BindingElements[1]  
        |-Type:                       SymmetricSecurityBindingElement  
      |-BindingElements[2]  
        |-Type:                       TextMessageEncodingBindingElement  
        |-MaxReadPoolSize:            64  
        |-MaxWritePoolSize:           16  
      |-BindingElements[3]  
        |-Type:                       HttpTransportBindingElement  
        |-ManualAddressing:           false  
        |-MaxBufferSize:              65536  
        |-AllowCookies:               false  
        |-AuthenticationScheme:       Anonymous  
        |-BypassProxyOnLocal:         false  
        |-HostNameComparisonMode:     StrongWildcard  
        |-ProxyAddress:               null  
        |-ProxyAuthenticationScheme:  Anonymous  
        |-Realm:  
        |-TransferMode:               Buffered  
        |-UseDefaultWebProxy:         true  
|-Behaviors:     5 behaviors  
      |-Behavior[0]  
      |-Type:                       ServiceBehaviorAttribute  
        |-AddressFilterMode:               Exact  
        |-AutomaticSessionShutdown:        true  
        |-ConcurrencyMode:                 Single  
        |-IncludeExceptionDetailInFaults:  false  
        |-InstanceContextMode:             PerSession  
        |-TransactionIsolationLevel:       Unspecified  
        |-TransactionTimeout:              null  
        |-ValidateMustUnderstand:          true  
      |-Behavior[1]  
      |-Type:                       AspNetCompatibilityRequirementsAttribute  
      |-Behavior[2]  
      |-Type:                       ServiceDebugBehavior  
      |-Behavior[3]  
      |-Type:                       ServiceAuthorizationBehavior  
      |-Behavior[4]  
      |-Type:                       Behavior  
```  
  
 다음으로 두 번째 Java Script를 실행하여 사용자 정의 WMI 데이터를 표시합니다.  
  
```console  
cscript EnumerateCustomObjects.js  
```  
  
 스크립트에서는 서비스에 포함된 사용자 정의 계측에 액세스하여 다음 출력을 생성합니다.  
  
```console
1 WMIObject(s) found.  
|-PID:           30285bfd-9d66-4c4e-9be2-310499c5cef5  
|-InstanceId:    3839  
|-WMIInfo:       User Defined WMI Information.  
```  
  
 컴퓨터에서 단일 서비스가 실행되고 있다는 것이 출력에 표시됩니다. 서비스에서는 `ICalculator` 계약을 구현하는 엔드포인트 하나를 노출합니다. 엔드포인트에서 구현하는 동작 및 바인딩 설정은 메시징 스택에 있는 개별 요소의 합으로 나열됩니다.  
  
 WMI는 WCF 인프라의 관리 계측을 노출하는 데 만 국한되지 않습니다. 같은 메커니즘을 통해 자체 도메인별 데이터 항목을 노출할 수 있습니다. WMI는 웹 서비스의 검사 및 제어를 위한 통합 메커니즘입니다.  
  
#### <a name="to-set-up-build-and-run-the-sample"></a>샘플을 설치, 빌드 및 실행하려면  
  
1. [Windows 통신 기초 샘플에 대한 일회성 설치 절차를](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md)수행했어야 합니다.  
  
2. C# 또는 Visual Basic .NET 버전의 솔루션을 빌드하려면 [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md)의 지침을 따릅니다.  
  
3. 호스팅 디렉터리에 있는 service.dll 파일에서 InstallUtil.exe(기본 위치는 "%WINDIR%\Microsoft.NET\Framework\v4.0.30319")를 실행하여 WMI에 서비스 스키마를 게시합니다. 이 단계는 service.dll 파일이 수정된 경우에만 수행되어야 합니다.
  
4. 단일 또는 컴퓨터 간 구성에서 샘플을 실행하려면 Windows [통신 기반 샘플 실행의 지침을 따르십시오.](../../../../docs/framework/wcf/samples/running-the-samples.md)  
  
    > [!NOTE]
    > ASP.NET 설치한 후 WCF를 설치한 경우 "%WINDIR%\"를 실행해야 할 수 있습니다. 마이크로소프트.Net\프레임 워크\v3.0\윈도우 통신 재단\servicemodelreg.exe " -r-x ASPNET 계정 WMI 개체를 게시 할 수있는 권한을 부여합니다.  
  
5. `cscript EnumerateServices.js` 또는 `cscript EnumerateCustomObjects.js` 명령을 사용하여 WMI를 통해 표시된 샘플의 데이터를 봅니다.  
  
> [!IMPORTANT]
> 컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다. 계속하기 전에 다음(기본) 디렉터리를 확인하세요.  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> 이 디렉터리가 없는 경우 [.NET Framework 4에 대한 WCF(Windows 통신 재단) 및 WF(Windows 워크플로우 재단) 샘플로](https://www.microsoft.com/download/details.aspx?id=21459) 이동하여 모든 WCF(Windows 통신 재단) 및 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 샘플을 다운로드합니다. 이 샘플은 다음 디렉터리에 있습니다.  
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Management\WMIProvider`  
  
## <a name="see-also"></a>참고 항목

- [AppFabric 모니터링 샘플](https://docs.microsoft.com/previous-versions/appfabric/ff383407(v=azure.10))
