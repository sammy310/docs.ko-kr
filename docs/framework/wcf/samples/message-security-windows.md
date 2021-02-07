---
description: '자세한 정보: 메시지 보안 창'
title: Message Security Windows
ms.date: 03/30/2017
helpviewer_keywords:
- WS Security
ms.assetid: d2221d1c-c9cb-48d1-b044-a3b4445c7f05
ms.openlocfilehash: 6b181e1bb835ea3129e99eb45baa6669bf8c09a1
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99752277"
---
# <a name="message-security-windows"></a>Message Security Windows

이 샘플에서는 Windows 인증과 함께 메시지 수준 보안을 사용하도록 <xref:System.ServiceModel.WSHttpBinding> 바인딩을 구성하는 방법을 보여 줍니다. 이 샘플은 [시작](getting-started-sample.md)을 기반으로 합니다. 이 샘플에서 서비스는 IIS(인터넷 정보 서비스)에서 호스트되고 클라이언트는 콘솔 애플리케이션(.exe)입니다.  
  
> [!NOTE]
> 이 샘플의 설치 절차 및 빌드 지침은 이 항목의 끝부분에 나와 있습니다.  
  
 의 기본 보안은 [\<wsHttpBinding>](../../configure-apps/file-schema/wcf/wshttpbinding.md) Windows 인증을 사용 하는 메시지 보안입니다. 이 샘플의 구성 파일은의 특성을로 명시적으로 설정 하 `mode` [\<security>](../../configure-apps/file-schema/wcf/security-of-wshttpbinding.md) `Message` 고 `clientCredentialType` 특성을로 `Windows` 설정 합니다. 이러한 값은 이 바인딩의 기본값이지만 다음 샘플 구성에서와 같이 실제 사용을 보여 주기 위해 명시적으로 구성되었습니다.  
  
```xml  
<bindings>  
    <wsHttpBinding>  
        <binding>  
            <security mode="Message">  
                <message clientCredentialType="Windows"/>  
            </security>  
        </binding>  
    </wsHttpBinding>  
</bindings>  
```  
  
 클라이언트 엔드포인트 구성은 서비스 엔드포인트의 절대 주소, 바인딩 및 계약으로 구성됩니다. 클라이언트 바인딩은 적절한 `securityMode` 및 `authenticationMode`를 사용하여 구성됩니다.  
  
```xml  
<system.serviceModel>  
  <client>  
    <endpoint address=  
            "http://localhost/servicemodelsamples/service.svc"
            binding="wsHttpBinding"
            bindingConfiguration="Binding1"
            contract="Microsoft.ServiceModel.Samples.ICalculator" />  
  </client>  
  
  <bindings>  
    <wsHttpBinding>  
      <!-- The default security for the WSHttpBinding is -->  
      <!-- Message security using Windows authentication. -->  
      <!-- This configuration explicitly defines the security mode -->  
      <!-- as Message and the clientCredentialType as Windows -->  
      <!-- for demonstration purposes. -->  
      <binding name="Binding1">  
        <security mode="Message">  
          <message clientCredentialType="Windows"/>  
        </security>  
      </binding>  
    </wsHttpBinding>  
  </bindings>  
</system.serviceModel>  
```  
  
 <xref:System.ServiceModel.OperationContext.ServiceSecurityContext%2A>를 사용하여 호출자의 ID에 액세스하는 방법을 보여 주기 위해 서비스 소스 코드가 수정되었습니다.  

```csharp
public string GetCallerIdentity()  
{  
    // The Windows identity of the caller can be accessed on the ServiceSecurityContext.WindowsIdentity.  
    return OperationContext.Current.ServiceSecurityContext.WindowsIdentity.Name;  
}  
```

 샘플을 실행하면 작업 요청 및 응답이 클라이언트 콘솔 창에 표시됩니다. `GetCallerIdentity`라는 첫 번째 메서드는 호출자 ID의 이름을 클라이언트에게 반환합니다. 클라이언트를 종료하려면 콘솔 창에서 Enter 키를 누릅니다.  
  
### <a name="to-set-up-build-and-run-the-sample"></a>샘플을 설치, 빌드 및 실행하려면  
  
1. [Windows Communication Foundation 샘플에 대 한 일회성 설치 절차](one-time-setup-procedure-for-the-wcf-samples.md)를 수행 했는지 확인 합니다.  
  
2. C# 또는 Visual Basic .NET 버전의 솔루션을 빌드하려면 [Building the Windows Communication Foundation Samples](building-the-samples.md)의 지침을 따릅니다.  
  
3. 단일 컴퓨터 또는 다중 컴퓨터 구성에서 샘플을 실행 하려면 [Windows Communication Foundation 샘플 실행](running-the-samples.md)의 지침을 따르세요.  
