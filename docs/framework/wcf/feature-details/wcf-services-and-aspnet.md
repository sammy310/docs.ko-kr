---
title: WCF 서비스 및 ASP.NET
description: ASP.NET와 함께 WCF 서비스를 함께 호스팅하고 ASP.NET 호환성 모드에서 호스트 하는 방법에 대해 알아봅니다.
ms.date: 03/30/2017
ms.assetid: b980496a-f0b0-4319-8e55-a0f0fa32da70
ms.openlocfilehash: 1d7401f6a326bc50923123acf803e26ce8238415
ms.sourcegitcommit: 358a28048f36a8dca39a9fe6e6ac1f1913acadd5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/23/2020
ms.locfileid: "85246417"
---
# <a name="wcf-services-and-aspnet"></a>WCF 서비스 및 ASP.NET

이 항목에서는 ASP.NET를 사용 하 여 WCF (Windows Communication Foundation) 서비스를 함께 호스팅하고 ASP.NET 호환 모드로 호스트 하는 방법에 대해 설명 합니다.

## <a name="hosting-wcf-side-by-side-with-aspnet"></a>ASP.NET와 함께 WCF 호스팅

인터넷 정보 서비스 (IIS)에서 호스트 되는 WCF 서비스는를 사용 하 여 찾을 수 있습니다. 단일 공통 응용 프로그램 도메인 내에 있는 ASPX 페이지 및 ASMX 웹 서비스입니다. ASP.NET는 WCF 및 ASP.NET HTTP 런타임에 대해 AppDomain 관리 및 동적 컴파일과 같은 일반적인 인프라 서비스를 제공 합니다. WCF에 대 한 기본 구성은 ASP.NET와 나란히 있습니다.

![WCF 서비스 및 ASP .NET: 공유 상태를 보여 주는 스크린샷](./media/wcf-services-and-aspnet/windows-communication-foundation-services-asp-dotnet-configuration.gif)

ASP.NET HTTP 런타임은 ASP.NET 요청을 처리 하지만 WCF 서비스로 향하는 요청 처리에는 참여 하지 않습니다. 이러한 서비스는 ASP.NET 콘텐츠와 동일한 AppDomain에서 호스팅됩니다. 대신 wcf 서비스 모델은 wcf 서비스로 주소가 지정 된 메시지를 가로채서 WCF 전송/채널 스택을 통해 라우팅합니다.

동시 모델의 결과는 다음과 같습니다.

- ASP.NET 및 WCF 서비스는 AppDomain 상태를 공유할 수 있습니다. 두 프레임 워크는 동일한 AppDomain에 공존할 수 있으므로 WCF는 ASP.NET (정적 변수, 이벤트 등 포함)를 사용 하 여 AppDomain 상태를 공유할 수도 있습니다.

- WCF 서비스는 호스팅 환경 및 전송과 독립적으로 일관 되 게 동작 합니다. ASP.NET HTTP 런타임은 IIS/ASP.NET 호스팅 환경 및 HTTP 통신에 의도적으로 연결됩니다. 반대로, WCF는 호스팅 환경에서 일관 되 게 동작 하도록 설계 되었습니다. (WCF는 IIS 내부 및 외부 모두에서 일관성 있게 동작) 및 전송 간에 일관 되 게 동작 하도록 설계 되었습니다. (IIS 7.0 이상에서 호스트 되는 서비스는 HTTP 이외의 프로토콜을 사용 하는 경우에도 노출 하는 모든 끝점에서 일관 된 동작을 가집니다.

- AppDomain 내에서 HTTP 런타임이 구현 하는 기능은 ASP.NET 콘텐츠에는 적용 되지만 WCF에는 적용 되지 않습니다. ASP.NET 응용 프로그램 플랫폼의 다양 한 HTTP 관련 기능은 ASP.NET 콘텐츠를 포함 하는 AppDomain 내에서 호스팅되는 WCF 서비스에 적용 되지 않습니다. 이러한 기능의 예는 다음과 같습니다.

  - HttpContext: <xref:System.Web.HttpContext.Current%2A> 은 `null` WCF 서비스 내에서 항상 액세스할 수 있습니다. 대신 <xref:System.ServiceModel.Channels.RequestContext>를 사용하세요.

  - 파일 기반 권한 부여: WCF 보안 모델에서는 서비스 요청이 인증 되었는지 결정할 때 서비스의 .svc 파일에 적용 되는 ACL (액세스 제어 목록)을 허용 하지 않습니다.

  - 구성 기반 URL 권한 부여: 마찬가지로, WCF 보안 모델은 System.web의 구성 요소에 지정 된 URL 기반 권한 부여 규칙을 준수 하지 않습니다 \<authorization> . 서비스가 ASP로 보호 되는 URL 공간에 있는 경우 WCF 요청에 대해 이러한 설정이 무시 됩니다. NET의 URL 권한 부여 규칙.

  - HttpModule 확장성: WCF 호스팅 인프라는 <xref:System.Web.HttpApplication.PostAuthenticateRequest> 이벤트가 발생 하 고 ASP.NET HTTP 파이프라인에 대 한 처리를 반환 하지 않는 경우 wcf 요청을 가로챕니다. 파이프라인의 이후 단계에서 요청을 가로채기 위해 코딩 된 모듈은 WCF 요청을 차단 하지 않습니다.

  - ASP.NET 가장: 기본적으로 WCF 요청은 ASP.NET이 System.web의 구성 옵션을 사용 하 여 가장을 사용 하도록 설정 된 경우에도 항상 IIS 프로세스 id로 실행 됩니다. \<identity impersonate="true" />

이러한 제한은 IIS 응용 프로그램에서 호스트 되는 WCF 서비스에만 적용 됩니다. ASP.NET 콘텐츠의 동작은 WCF의 존재에 영향을 받지 않습니다.

일반적으로 HTTP 파이프라인에서 제공 하는 기능을 필요로 하는 WCF 응용 프로그램은 호스트 및 전송에 독립적인 WCF와 동등한 기능을 사용 하는 것이 좋습니다.

- <xref:System.ServiceModel.OperationContext> 대신 <xref:System.Web.HttpContext> 사용

- ASP.NET의 File/URL 권한 부여 대신 <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior> 사용

- HTTP 모듈 대신 <xref:System.ServiceModel.Dispatcher.IDispatchMessageInspector> 또는 사용자 지정 계층화된 채널 사용

- System.web 가장 대신 WCF를 사용 하는 각 작업에 대 한 가장입니다.

또는 WCF의 ASP.NET compatibility 모드에서 서비스를 실행 하는 것을 고려할 수 있습니다.

## <a name="hosting-wcf-services-in-aspnet-compatibility-mode"></a>ASP.NET 호환 모드에서 WCF 서비스 호스팅

WCF 모델은 호스팅 환경 및 전송에서 일관성 있게 동작 하도록 설계 되었지만 응용 프로그램에 이러한 수준의 유연성이 필요 하지 않는 경우가 많습니다. WCF의 ASP.NET 호환 모드는 IIS 외부에서 호스트 하는 기능이 필요 하지 않은 시나리오 또는 HTTP 이외의 프로토콜을 통해 통신 하는 기능이 필요 하지 않지만 ASP.NET 웹 응용 프로그램 플랫폼의 모든 기능을 사용 하는 시나리오에 적합 합니다.

Wcf 호스팅 인프라가 WCF 메시지를 가로채 고 HTTP 파이프라인에서 라우팅하는 기본 side-by-side 구성과 달리 ASP.NET Compatibility 모드에서 실행 되는 WCF 서비스는 ASP.NET HTTP 요청 수명 주기에 완전히 참여 합니다. 호환 모드에서 WCF 서비스는 <xref:System.Web.IHttpHandler> ASPX 페이지 및 ASMX 웹 서비스에 대 한 요청이 처리 되는 방식과 비슷하게 구현을 통해 HTTP 파이프라인을 사용 합니다. 따라서 WCF는 다음 ASP.NET 기능에 대해 ASMX와 동일 하 게 작동 합니다.

- <xref:System.Web.HttpContext>: ASP.NET 호환 모드에서 실행 되는 WCF 서비스는 <xref:System.Web.HttpContext.Current%2A> 및 연결 된 상태에 액세스할 수 있습니다.

- 파일 기반 권한 부여: ASP.NET 호환 모드에서 실행 되는 WCF 서비스는 서비스의 .svc 파일에 파일 시스템 Acl (액세스 제어 목록)을 연결 하 여 보안을 유지할 수 있습니다.

- 구성 가능한 URL 권한 부여: ASP. WCF 서비스를 ASP.NET Compatibility 모드로 실행 하는 경우 .NET의 URL 권한 부여 규칙이 WCF 요청에 적용 됩니다.

- <xref:System.Web.HttpModuleCollection>확장성: ASP.NET 호환 모드에서 실행 되는 WCF 서비스는 ASP.NET HTTP 요청 수명 주기에 완전히 참여 하므로 HTTP 파이프라인에 구성 된 모든 HTTP 모듈은 서비스 호출 전후에 WCF 요청에서 작동할 수 있습니다.

- ASP.NET 가장: WCF 서비스는 응용 프로그램에 대 한 ASP.NET 가장이 사용 하도록 설정 된 경우 IIS 프로세스 id와 다를 수 있는 ASP.NET 가장 스레드의 현재 id를 사용 하 여 실행 됩니다. 특정 서비스 작업에 ASP.NET 가장 및 WCF 가장을 모두 사용 하는 경우 서비스 구현은 궁극적으로 WCF에서 가져온 id를 사용 하 여 실행 됩니다.

WCF의 ASP.NET compatibility mode는 응용 프로그램의 Web.config 파일에 있는 다음 구성을 통해 응용 프로그램 수준에서 사용 하도록 설정 됩니다.

```xml
<system.serviceModel>
    <serviceHostingEnvironment aspNetCompatibilityEnabled="true" />
</system.serviceModel>
```

지정 하지 않으면이 값은 기본적으로로 설정 `false` 됩니다. 값은 `false` 응용 프로그램에서 실행 되는 모든 WCF 서비스가 ASP.NET 호환 모드에서 실행 되지 않음을 나타냅니다.

ASP.NET 호환 모드는 기본적으로 WCF 기본값과 다른 요청 처리 의미 체계를 의미 하기 때문에 개별 서비스 구현에는 ASP.NET 호환성 모드가 사용 하도록 설정 된 응용 프로그램 내에서 실행 되는지 여부를 제어할 수 있는 기능이 있습니다. 서비스는 <xref:System.ServiceModel.Activation.AspNetCompatibilityRequirementsAttribute>를 사용하여 ASP.NET 호환 모드를 지원할지 여부를 나타낼 수 있습니다. 이 특성의 기본값은 <xref:System.ServiceModel.Activation.AspNetCompatibilityRequirementsMode.Allowed>입니다.

```csharp
[AspNetCompatibilityRequirements(RequirementsMode = AspNetCompatibilityRequirementsMode.Allowed)]
public class CalculatorService : ICalculatorSession
{//Implement calculator service methods.}
```

다음 표에서는 애플리케이션 수준의 호환 모드 설정이 개별 서비스에 명시된 지원 수준과 상호 작용하는 방법을 보여 줍니다.

|애플리케이션 수준의 호환 모드 설정|[AspNetCompatibilityRequirementsMode]<br /><br /> 설정|확인된 결과|
|--------------------------------------------------|---------------------------------------------------------|---------------------|
|aspNetCompatibilityEnabled = " `true` "|<xref:System.ServiceModel.Activation.AspNetCompatibilityRequirementsMode.Required>|서비스가 활성화됩니다.|
|aspNetCompatibilityEnabled = " `true` "|<xref:System.ServiceModel.Activation.AspNetCompatibilityRequirementsMode.Allowed>|서비스가 활성화됩니다.|
|aspNetCompatibilityEnabled = " `true` "|<xref:System.ServiceModel.Activation.AspNetCompatibilityRequirementsMode.NotAllowed>|서비스가 메시지를 수신할 때 활성화 오류가 발생합니다.|
|aspNetCompatibilityEnabled = " `false` "|<xref:System.ServiceModel.Activation.AspNetCompatibilityRequirementsMode.Required>|서비스가 메시지를 수신할 때 활성화 오류가 발생합니다.|
|aspNetCompatibilityEnabled = " `false` "|<xref:System.ServiceModel.Activation.AspNetCompatibilityRequirementsMode.Allowed>|서비스가 활성화됩니다.|
|aspNetCompatibilityEnabled = " `false` "|<xref:System.ServiceModel.Activation.AspNetCompatibilityRequirementsMode.NotAllowed>|서비스가 활성화됩니다.|

> [!NOTE]
> IIS 7.0 및 WAS를 사용 하면 WCF 서비스에서 HTTP 이외의 프로토콜을 통해 통신할 수 있습니다. 그러나 ASP.NET 호환 모드가 활성화 된 응용 프로그램에서 실행 되는 WCF 서비스는 HTTP가 아닌 끝점을 노출 하도록 허용 되지 않습니다. 이러한 구성은 서비스에서 첫 번째 메시지를 수신할 때 활성화 예외를 생성합니다.

WCF 서비스에 ASP.NET 호환 모드를 사용 하도록 설정 하는 방법에 대 한 자세한 내용은 <xref:System.ServiceModel.Activation.AspNetCompatibilityRequirementsMode> 및 [ASP.NET compatibility](../samples/aspnet-compatibility.md) 샘플을 참조 하세요.

## <a name="see-also"></a>참고 항목

- <xref:System.ServiceModel.Activation.AspNetCompatibilityRequirementsAttribute>
- [Windows Server App Fabric 호스팅 기능](https://docs.microsoft.com/previous-versions/appfabric/ee677189(v=azure.10))
