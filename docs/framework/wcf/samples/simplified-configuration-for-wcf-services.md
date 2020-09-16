---
title: WCF 서비스를 위한 단순화된 구성
description: WCF를 사용 하 여 일반적인 서비스 및 클라이언트를 구현 하 고 구성 하는 방법에 대해 알아봅니다. 서비스는 구성 파일에 지정 된 끝점을 사용 하 여 통신 합니다.
ms.date: 03/30/2017
ms.assetid: 1e39ec25-18a3-4fdc-b6a3-9dfafbd60112
ms.openlocfilehash: dd05754dcfe36cb2e9c28ce20a5927585f85478f
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/15/2020
ms.locfileid: "90554269"
---
# <a name="simplified-configuration-for-wcf-services"></a>WCF 서비스를 위한 단순화된 구성
이 샘플에서는 WCF (Windows Communication Foundation)를 사용 하 여 일반적인 서비스 및 클라이언트를 구현 하 고 구성 하는 방법을 보여 줍니다. 이 샘플은 다른 모든 기본 기술 샘플의 기준이 됩니다.  
  
 서비스와 통신 하기 위한 끝점을 노출 하는이 서비스는 .NET Framework 4에서 간소화 된 구성을 사용 합니다. .NET Framework 4 이전에는 다음 예제 구성 코드에 표시 된 것 처럼 끝점이 일반적으로 구성 파일 (Web.config)에서 정의 됩니다.  
  
```xml  
<?xml version="1.0" encoding="utf-8" ?>  
<!-- Copyright ©) Microsoft Corporation.  All Rights Reserved. -->  
<configuration>  
  <system.serviceModel>  
    <behaviors>  
      <serviceBehaviors>  
        <behavior name="CalculatorServiceBehavior">  
          <serviceMetadata httpGetEnabled="True"/>  
        </behavior>  
      </serviceBehaviors>  
    </behaviors>  
    <services>  
      <service name="Microsoft.Samples.GettingStarted.CalculatorService"  
               behaviorConfiguration="CalculatorServiceBehavior">  
        <endpoint address="" binding="basicHttpBinding" contract="ICalculator"/>  
        <endpoint address="mex" binding="mexHttpBinding" contract="IMetadataExchange"/>  
      </service>  
    </services>  
  </system.serviceModel>  
</configuration>  
```  
  
 .NET Framework 4에서 요소는 `<service>` 선택 사항입니다. 서비스에서 엔드포인트를 정의하지 않을 경우 각 기본 주소의 엔드포인트와 구현된 계약이 서비스에 추가됩니다. 기본 주소가 계약 이름에 추가되어 엔드포인트가 결정되고 바인딩은 주소 스키마에 의해 결정됩니다. 다음 코드 예제에서는 단순화된 구성 파일을 보여 줍니다. 구성 된 대로 `http://localhost/servicemodelsamples/service.svc` 동일한 컴퓨터의 클라이언트에서 서비스에 액세스할 수 있습니다. 원격 컴퓨터의 클라이언트가 서비스에 액세스하려면 localhost 대신 정규화된 도메인 이름을 지정해야 합니다. 기본적으로 서비스에서는 메타데이터를 노출하지 않습니다. 따라서 서비스에서는 <xref:System.ServiceModel.Description.ServiceMetadataBehavior> 동작을 설정합니다.  
  
```xml  
<?xml version="1.0" encoding="utf-8" ?>  
<!-- Copyright © Microsoft Corporation.  All Rights Reserved. -->  
<configuration>  
  <system.serviceModel>  
    <behaviors>  
      <serviceBehaviors>  
        <behavior name="">  
          <serviceMetadata httpGetEnabled="True"/>  
        </behavior>  
      </serviceBehaviors>  
    </behaviors>  
  </system.serviceModel>  
</configuration>  
```  
  
### <a name="to-use-this-sample"></a>이 샘플을 사용하려면  
  
1. [Windows Communication Foundation 샘플에 대 한 일회성 설치 절차](one-time-setup-procedure-for-the-wcf-samples.md)를 수행 했는지 확인 합니다.  
  
2. 솔루션을 빌드하려면 [Windows Communication Foundation 샘플 빌드](building-the-samples.md)의 지침을 따르세요.  
  
3. 다음 단계에 따라 샘플을 실행합니다.  
  
    1. **서비스** 프로젝트를 마우스 오른쪽 단추로 클릭 하 고 **시작 프로젝트로 설정**을 선택한 다음 **ctrl + F5**를 누릅니다.  
  
    2. 서비스가 실행 중이라는 콘솔 출력이 나타날 때까지 기다립니다.  
  
    3. **클라이언트** 프로젝트를 마우스 오른쪽 단추로 클릭 하 고 **시작 프로젝트로 설정**을 선택한 다음 **ctrl + F5**를 누릅니다.  
  
> [!IMPORTANT]
> 컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다. 계속하기 전에 다음(기본) 디렉터리를 확인하세요.  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> 이 디렉터리가 없는 경우 [.NET Framework 4에 대 한 Windows Communication Foundation (wcf) 및 Windows Workflow Foundation (WF) 샘플](https://www.microsoft.com/download/details.aspx?id=21459) 로 이동 하 여 모든 WINDOWS COMMUNICATION FOUNDATION (wcf) 및 샘플을 다운로드 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 합니다. 이 샘플은 다음 디렉터리에 있습니다.  
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Services\ConfigSimplificationIn40`  
  
## <a name="see-also"></a>참조

- [AppFabric 관리 샘플](/previous-versions/appfabric/ff383405(v=azure.10))
- [단순화된 구성](../simplified-configuration.md)
