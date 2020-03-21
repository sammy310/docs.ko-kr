---
title: 구성 채널 팩터리
ms.date: 03/30/2017
ms.assetid: 3b749493-bd8a-4ccb-893e-5948901a1486
ms.openlocfilehash: 0f00ba5e217420fe416100071d380e413c3df118
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79183944"
---
# <a name="configuration-channel-factory"></a>구성 채널 팩터리
이 샘플에서는 <xref:System.ServiceModel.Configuration.ConfigurationChannelFactory%601>의 사용법에 대해 설명합니다. WCF <xref:System.ServiceModel.Configuration.ConfigurationChannelFactory%601> 클라이언트 구성을 중앙으로 관리할 수 있습니다. 애플리케이션 도메인의 로드 이후 구성이 선택되었거나 변경된 경우에도 유용합니다.

## <a name="demonstrates"></a>데모
 <xref:System.ServiceModel.Configuration.ConfigurationChannelFactory%601>

## <a name="discussion"></a>토론
 이 샘플에서는 기본 애플리케이션 구성 파일을 사용할 필요 없이 <xref:System.ServiceModel.Configuration.ConfigurationChannelFactory%601>를 사용하여 클라이언트 애플리케이션에 특정 구성 파일을 추가하는 방법을 보여 줍니다.

 이 샘플은 두 프로젝트로 구성되어 있습니다. 첫 번째 프로젝트는 클라이언트가 보내는 메시지에 회신하기 위해 실행되는 간단한 서비스입니다. 두 번째 프로젝트는 Test.config 구성 파일에 대해 <xref:System.ServiceModel.Configuration.ConfigurationChannelFactory%601>을 사용하여 두 개의 <xref:System.Configuration.ExeConfigurationFileMap> 개체를 빌드하고 이 개체를 사용하여 서비스와 통신하는 클라이언트 애플리케이션입니다. 두 클라이언트 모두 Test.config에 지정된 구성을 사용하여 서비스와 통신합니다.

 다음 코드에서는 클라이언트 애플리케이션에 사용자 지정 구성 파일을 추가합니다.

```csharp
ExeConfigurationFileMap fileMap = new ExeConfigurationFileMap();
fileMap.ExeConfigFilename = "Test.config";
Configuration newConfiguration = ConfigurationManager.OpenMappedExeConfiguration(fileMap, ConfigurationUserLevel.None);

ConfigurationChannelFactory<ICalculatorChannel> factory1 = new ConfigurationChannelFactory<ICalculatorChannel>("endpoint1", newConfiguration, new EndpointAddress("http://localhost:8000/servicemodelsamples/service"));
ICalculatorChannel client1 = factory1.CreateChannel();
```

#### <a name="to-set-up-build-and-run-the-sample"></a>샘플을 설치, 빌드 및 실행하려면

1. 관리자 권한이 있는 Visual Studio 2012를 엽니다.

2. 구성채널팩토리 솔루션(2개 프로젝트)을 마우스 오른쪽 단추로 클릭한 다음 **속성을**선택합니다.

3. **공통 속성에서** **시작 프로젝트를**선택한 다음 여러 시작 **프로젝트를**클릭합니다.

4. **작업 '시작'을**사용하여 **서비스** 프로젝트를 목록의 시작 부분으로 이동한 다음 **서비스** 프로젝트 다음에 **클라이언트** 프로젝트를 이동한 다음 **'Start'를**사용하여 클라이언트 프로젝트를 실행하므로 **클라이언트** 프로젝트가 **서비스** 프로젝트 후에 실행됩니다.

5. **확인을**클릭한 다음 F5(또는 CTRL+F5)를 눌러 샘플을 실행합니다.

> [!IMPORTANT]
> 컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다. 계속하기 전에 다음(기본) 디렉터리를 확인하세요.  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> 이 디렉터리가 없는 경우 [.NET Framework 4에 대한 WCF(Windows 통신 재단) 및 WF(Windows 워크플로우 재단) 샘플로](https://www.microsoft.com/download/details.aspx?id=21459) 이동하여 모든 WCF(Windows 통신 재단) 및 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 샘플을 다운로드합니다. 이 샘플은 다음 디렉터리에 있습니다.  
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Services\ConfigurationChannelFactory`
