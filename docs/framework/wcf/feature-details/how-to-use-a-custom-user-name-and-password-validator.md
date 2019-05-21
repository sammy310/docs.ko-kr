---
title: '방법: 사용자 지정 사용자 이름 및 암호에 대한 유효성 검사기 사용'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WCF, username and password
ms.assetid: 8e08b74b-fa44-4018-b63d-0d0805f85e3f
ms.openlocfilehash: 593e3e97ad7e5ae65447d8618caacf22f762f9b4
ms.sourcegitcommit: ffd7dd79468a81bbb0d6449f6d65513e050c04c4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/21/2019
ms.locfileid: "65960065"
---
# <a name="how-to-use-a-custom-user-name-and-password-validator"></a>방법: 사용자 지정 사용자 이름 및 암호에 대한 유효성 검사기 사용
기본적으로 사용자 이름 및 암호 인증을 위해 사용 되는 경우 Windows Communication Foundation (WCF)를 사용 하 여 Windows 사용자 이름 및 암호의 유효성을 검사 합니다. 그러나 WCF에서는 사용자 지정 사용자 이름 및 암호 인증 체계에 대 한 라고도 *유효성 검사기*합니다. 사용자 지정 사용자 이름 및 암호 유효성 검사기를 통합하려면 <xref:System.IdentityModel.Selectors.UserNamePasswordValidator>에서 파생되는 클래스를 만들어 구성합니다.  
  
 샘플 응용 프로그램을 참조 하세요 [사용자 이름 암호 유효성 검사기](../../../../docs/framework/wcf/samples/user-name-password-validator.md)합니다.  
  
### <a name="to-create-a-custom-user-name-and-password-validator"></a>사용자 지정 사용자 이름 및 암호 유효성 검사기를 만들려면  
  
1. <xref:System.IdentityModel.Selectors.UserNamePasswordValidator>에서 파생되는 클래스를 만듭니다.  
  
     [!code-csharp[C_CustomUsernameAndPasswordValidator#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customusernameandpasswordvalidator/cs/service.cs#3)]
     [!code-vb[C_CustomUsernameAndPasswordValidator#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customusernameandpasswordvalidator/vb/service.vb#3)]  
  
2. <xref:System.IdentityModel.Selectors.UserNamePasswordValidator.Validate%2A> 메서드를 재정의하여 사용자 지정 인증 스키마를 구현합니다.  
  
     다음 예제에서는 프로덕션 환경에서 <xref:System.IdentityModel.Selectors.UserNamePasswordValidator.Validate%2A> 메서드를 재정의하는 코드를 사용하지 않습니다. 코드를 사용자 지정 사용자 이름 및 암호 유효성 검사 스키마로 바꿉니다. 이 스키마는 데이터베이스에서 사용자 이름과 암호 쌍을 검색합니다.  
  
     인증 오류를 다시 클라이언트에 반환하려면 <xref:System.ServiceModel.FaultException> 메서드에서 <xref:System.IdentityModel.Selectors.UserNamePasswordValidator.Validate%2A>을 throw합니다.  
  
     [!code-csharp[C_CustomUsernameAndPasswordValidator#4](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customusernameandpasswordvalidator/cs/service.cs#4)]
     [!code-vb[C_CustomUsernameAndPasswordValidator#4](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customusernameandpasswordvalidator/vb/service.vb#4)]  
  
### <a name="to-configure-a-service-to-use-a-custom-user-name-and-password-validator"></a>사용자 지정 사용자 이름 및 암호 유효성 검사기를 사용하도록 서비스를 구성하려면  
  
1. HTTP(S)를 통해 전송 또는 전송 수준 보안에서 메시지 보안을 사용하는 바인딩을 구성합니다.  
  
     메시지 보안을 사용 하는 경우 시스템 제공 바인딩 중 하나 같은 추가 된 [ \<wsHttpBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md), 또는 [ \<customBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md) 지원 하는 메시지 보안 및 `UserName` 자격 증명 유형입니다.  
  
     전송 수준 보안 HTTP (S)를 통해 사용 하는 경우 추가 합니다 [ \<wsHttpBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md) 하거나 [ \<basicHttpBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/basichttpbinding.md), [ \< netTcpBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/nettcpbinding.md) 또는 [ \<customBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md) HTTP (S)를 사용 하 고 `Basic` 인증 체계입니다.  
  
    > [!NOTE]
    >  [!INCLUDE[netfx35_long](../../../../includes/netfx35-long-md.md)] 이상을 사용하는 경우 메시지 및 전송 보안과 함께 사용자 지정 사용자 이름 및 암호 유효성 검사기를 사용할 수 있습니다. WinFX를 사용 하 여 메시지 보안을 사용 하 여 사용자 지정 사용자 이름 및 암호 유효성 검사기만 사용할 수 있습니다.  
  
    > [!TIP]
    >  사용 하 여 대 한 자세한 내용은 \<netTcpBinding >이 컨텍스트에서 참조 [ \<보안 >](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-nettcpbinding.md)  
  
    1. 구성 파일에 아래 합니다 [ \<system.serviceModel >](../../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel.md) 요소를 추가 [ \<바인딩 >](../../../../docs/framework/configure-apps/file-schema/wcf/bindings.md) 요소.  
  
    2. 추가 된 [ \<wsHttpBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md) 하거나 [ \<basicHttpBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/basichttpbinding.md) 요소를 바인딩 섹션. WCF 바인딩 요소를 만드는 방법에 대 한 자세한 내용은 참조 하세요. [방법: 구성에서 서비스 바인딩 지정](../../../../docs/framework/wcf/how-to-specify-a-service-binding-in-configuration.md)합니다.  
  
    3. 설정 합니다 `mode` 특성을 [ \<보안 >](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-wshttpbinding.md) 또는 [ \<보안 >](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-basichttpbinding.md) 를 `Message`, `Transport`, 또는 `TransportWithMessageCredential`.  
  
    4. 설정 합니다 `clientCredentialType` 특성을 [ \<메시지 >](../../../../docs/framework/configure-apps/file-schema/wcf/message-of-wshttpbinding.md) 또는 [ \<전송 >](../../../../docs/framework/configure-apps/file-schema/wcf/transport-of-wshttpbinding.md)합니다.  
  
         메시지 보안을 사용할 때 설정 합니다 `clientCredentialType` 특성을 [ \<메시지 >](../../../../docs/framework/configure-apps/file-schema/wcf/message-of-wshttpbinding.md) 를 `UserName`.  
  
         HTTP (S)를 통해 전송 수준 보안 사용 하 여 설정 합니다 `clientCredentialType` 특성을 [ \<전송 >](../../../../docs/framework/configure-apps/file-schema/wcf/transport-of-wshttpbinding.md) 또는 [ \<전송 >](../../../../docs/framework/configure-apps/file-schema/wcf/transport-of-basichttpbinding.md) 에 `Basic`입니다.  
  
        > [!NOTE]
        >  WCF 서비스에서 인터넷 정보 서비스 (IIS) 전송 수준 보안을 사용 하 여 호스팅된 경우 및 <xref:System.ServiceModel.Security.UserNamePasswordServiceCredential.UserNamePasswordValidationMode%2A> 속성이 <xref:System.ServiceModel.Security.UserNamePasswordValidationMode.Custom>, 사용자 지정 인증 체계는 Windows 인증의 하위 집합을 사용 합니다. 이것은 IIS이이 시나리오에서는 WCF 사용자 지정 인증자를 호출 하기 전에 Windows 인증을 수행 합니다.  
  
     WCF 바인딩 요소를 만드는 방법에 대 한 자세한 내용은 참조 하세요. [방법: 구성에서 서비스 바인딩 지정](../../../../docs/framework/wcf/how-to-specify-a-service-binding-in-configuration.md)합니다.  
  
     다음 예제에서는 바인딩에 대한 구성 코드를 보여 줍니다.  
  
    ```xml  
    <system.serviceModel>   
      <bindings>  
      <wsHttpBinding>  
          <binding name="Binding1">  
            <security mode="Message">  
              <message clientCredentialType="UserName" />  
            </security>  
          </binding>          
        </wsHttpBinding>  
      </bindings>  
    </system.serviceModel>  
    ```  
  
2. 사용자 지정 사용자 이름 및 암호 유효성 검사기를 사용하여 들어오는 <xref:System.IdentityModel.Tokens.UserNameSecurityToken> 보안 토큰에 대한 사용자 이름과 암호 쌍의 유효성을 검사하도록 지정하는 동작을 구성합니다.  
  
    1. 에 자식 항목으로 [ \<system.serviceModel >](../../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel.md) 요소에 추가 [ \<동작 >](../../../../docs/framework/configure-apps/file-schema/wcf/behaviors.md) 요소입니다.  
  
    2. 추가 된 [ \<serviceBehaviors >](../../../../docs/framework/configure-apps/file-schema/wcf/servicebehaviors.md) 에 [ \<동작 >](../../../../docs/framework/configure-apps/file-schema/wcf/behaviors.md) 요소.  
  
    3. 추가 [ \<동작 >](../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-servicebehaviors.md) 요소를 `name` 특성을 적절 한 값으로.  
  
    4. 추가 된 [ \<serviceCredentials >](../../../../docs/framework/configure-apps/file-schema/wcf/servicecredentials.md) 에 [ \<동작 >](../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-servicebehaviors.md) 요소.  
  
    5. 추가 된 [ \<userNameAuthentication >](../../../../docs/framework/configure-apps/file-schema/wcf/usernameauthentication.md) 에 [ \<serviceCredentials >](../../../../docs/framework/configure-apps/file-schema/wcf/servicecredentials.md)합니다.  
  
    6. `userNamePasswordValidationMode`를 `Custom`으로 설정합니다.  
  
        > [!IMPORTANT]
        >  경우는 `userNamePasswordValidationMode` 값 설정 하지 않으면, WCF 사용자 지정 사용자 이름 및 암호 유효성 검사기 대신 Windows 인증을 사용 합니다.  
  
    7. `customUserNamePasswordValidatorType`을 사용자 지정 사용자 이름 및 암호 유효성 검사기를 나타내는 형식으로 설정합니다.  
  
     다음 예제에서는 이 지점에 대한 `<serviceCredentials>` 단편을 보여 줍니다.  
  
    ```xml  
    <serviceCredentials>  
      <userNameAuthentication userNamePasswordValidationMode="Custom" customUserNamePasswordValidatorType="Microsoft.ServiceModel.Samples.CalculatorService.CustomUserNameValidator, service" />  
    </serviceCredentials>  
    ```  
  
## <a name="example"></a>예제  
 다음 코드 예제에서는 사용자 지정 사용자 이름 및 암호 유효성 검사기를 만드는 방법을 보여 줍니다. 프로덕션 환경에서는 <xref:System.IdentityModel.Selectors.UserNamePasswordValidator.Validate%2A> 메서드를 재정의하는 코드를 사용하지 않습니다. 코드를 사용자 지정 사용자 이름 및 암호 유효성 검사 스키마로 바꿉니다. 이 스키마는 데이터베이스에서 사용자 이름과 암호 쌍을 검색합니다.  
  
 [!code-csharp[C_CustomUsernameAndPasswordValidator#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customusernameandpasswordvalidator/cs/service.cs#1)]
 [!code-vb[C_CustomUsernameAndPasswordValidator#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customusernameandpasswordvalidator/vb/service.vb#1)]  
[!code-csharp[C_CustomUsernameAndPasswordValidator#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customusernameandpasswordvalidator/cs/service.cs#2)]
[!code-vb[C_CustomUsernameAndPasswordValidator#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customusernameandpasswordvalidator/vb/service.vb#2)]  
  
## <a name="see-also"></a>참고자료

- <xref:System.IdentityModel.Selectors.UserNamePasswordValidator>
- [방법: ASP.NET 멤버 자격 공급자 사용](../../../../docs/framework/wcf/feature-details/how-to-use-the-aspnet-membership-provider.md)
- [인증](../../../../docs/framework/wcf/feature-details/authentication-in-wcf.md)
