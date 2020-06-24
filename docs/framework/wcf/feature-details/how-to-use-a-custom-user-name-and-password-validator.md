---
title: '방법: 사용자 지정 사용자 이름 및 암호에 대한 유효성 검사기 사용'
description: 기본 Windows 사용자 이름 및 암호 유효성 검사 대신 WFC 응용 프로그램에 대 한 사용자 지정 암호 유효성 검사기를 통합 하는 방법에 대해 알아봅니다.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WCF, username and password
ms.assetid: 8e08b74b-fa44-4018-b63d-0d0805f85e3f
ms.openlocfilehash: 7f69db7bf8248593b64cdae4378983c2460de597
ms.sourcegitcommit: 358a28048f36a8dca39a9fe6e6ac1f1913acadd5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/23/2020
ms.locfileid: "85246794"
---
# <a name="how-to-use-a-custom-user-name-and-password-validator"></a>방법: 사용자 지정 사용자 이름 및 암호에 대한 유효성 검사기 사용

기본적으로 인증에 사용자 이름과 암호를 사용 하는 경우 WCF (Windows Communication Foundation)는 Windows를 사용 하 여 사용자 이름과 암호의 유효성을 검사 합니다. 그러나 WCF는 사용자 지정 사용자 이름 및 암호 인증 스키마 ( *유효성 검사기*라고도 함)를 허용 합니다. 사용자 지정 사용자 이름 및 암호 유효성 검사기를 통합하려면 <xref:System.IdentityModel.Selectors.UserNamePasswordValidator>에서 파생되는 클래스를 만들어 구성합니다.

응용 프로그램 예제는 [사용자 이름 암호 유효성 검사기](../samples/user-name-password-validator.md)를 참조 하세요.

### <a name="to-create-a-custom-user-name-and-password-validator"></a>사용자 지정 사용자 이름 및 암호 유효성 검사기를 만들려면

1. <xref:System.IdentityModel.Selectors.UserNamePasswordValidator>에서 파생되는 클래스를 만듭니다.

    [!code-csharp[C_CustomUsernameAndPasswordValidator#3](~/samples/snippets/csharp/VS_Snippets_CFX/c_customusernameandpasswordvalidator/cs/service.cs#3)]
    [!code-vb[C_CustomUsernameAndPasswordValidator#3](~/samples/snippets/visualbasic/VS_Snippets_CFX/c_customusernameandpasswordvalidator/vb/service.vb#3)]

2. <xref:System.IdentityModel.Selectors.UserNamePasswordValidator.Validate%2A> 메서드를 재정의하여 사용자 지정 인증 스키마를 구현합니다.

    다음 예제에서는 프로덕션 환경에서 <xref:System.IdentityModel.Selectors.UserNamePasswordValidator.Validate%2A> 메서드를 재정의하는 코드를 사용하지 않습니다. 코드를 사용자 지정 사용자 이름 및 암호 유효성 검사 스키마로 바꿉니다. 이 스키마는 데이터베이스에서 사용자 이름과 암호 쌍을 검색합니다.

    인증 오류를 다시 클라이언트에 반환하려면 <xref:System.ServiceModel.FaultException> 메서드에서 <xref:System.IdentityModel.Selectors.UserNamePasswordValidator.Validate%2A>을 throw합니다.

    [!code-csharp[C_CustomUsernameAndPasswordValidator#4](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customusernameandpasswordvalidator/cs/service.cs#4)]
    [!code-vb[C_CustomUsernameAndPasswordValidator#4](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customusernameandpasswordvalidator/vb/service.vb#4)]

### <a name="to-configure-a-service-to-use-a-custom-user-name-and-password-validator"></a>사용자 지정 사용자 이름 및 암호 유효성 검사기를 사용하도록 서비스를 구성하려면

1. HTTP(S)를 통해 전송 또는 전송 수준 보안에서 메시지 보안을 사용하는 바인딩을 구성합니다.

    메시지 보안을 사용 하는 경우 [\<wsHttpBinding>](../../configure-apps/file-schema/wcf/wshttpbinding.md) [\<customBinding>](../../configure-apps/file-schema/wcf/custombinding.md) 메시지 보안 및 `UserName` 자격 증명 형식을 지 원하는 또는와 같은 시스템 제공 바인딩 중 하나를 추가 합니다.

    HTTP (S)를 통해 전송 수준 보안을 사용 하 [\<wsHttpBinding>](../../configure-apps/file-schema/wcf/wshttpbinding.md) [\<basicHttpBinding>](../../configure-apps/file-schema/wcf/basichttpbinding.md) 는 경우 [\<netTcpBinding>](../../configure-apps/file-schema/wcf/nettcpbinding.md) [\<customBinding>](../../configure-apps/file-schema/wcf/custombinding.md) http (s) 및 인증 체계를 사용 하는 또는, 또는를 추가 합니다 `Basic` .

    > [!NOTE]
    > .NET Framework 3.5 이상 버전을 사용 하는 경우 메시지 및 전송 보안과 함께 사용자 지정 사용자 이름 및 암호 유효성 검사기를 사용할 수 있습니다. WinFX를 사용 하면 사용자 지정 사용자 이름 및 암호 유효성 검사기를 메시지 보안과 함께 사용할 수 있습니다.

    > [!TIP]
    > 이 컨텍스트에서를 사용 하는 방법에 대 한 자세한 내용은 \<netTcpBinding> 을 참조 하십시오 [\<security>](../../configure-apps/file-schema/wcf/security-of-nettcpbinding.md) .

    1. 구성 파일의 요소 아래에 [\<system.serviceModel>](../../configure-apps/file-schema/wcf/system-servicemodel.md) 요소를 추가 [\<bindings>](../../configure-apps/file-schema/wcf/bindings.md) 합니다.

    2. [\<wsHttpBinding>](../../configure-apps/file-schema/wcf/wshttpbinding.md)또는 요소를 [\<basicHttpBinding>](../../configure-apps/file-schema/wcf/basichttpbinding.md) 바인딩 섹션에 추가 합니다. WCF 바인딩 요소를 만드는 방법에 대 한 자세한 내용은 [방법: 구성에서 서비스 바인딩 지정](../how-to-specify-a-service-binding-in-configuration.md)을 참조 하세요.

    3. `mode`또는의 특성을 [\<security>](../../configure-apps/file-schema/wcf/security-of-wshttpbinding.md) [\<security>](../../configure-apps/file-schema/wcf/security-of-basichttpbinding.md) `Message` , `Transport` 또는로 `TransportWithMessageCredential` 설정 합니다.

    4. `clientCredentialType`또는의 특성을 설정 [\<message>](../../configure-apps/file-schema/wcf/message-of-wshttpbinding.md) 합니다 [\<transport>](../../configure-apps/file-schema/wcf/transport-of-wshttpbinding.md) .

        메시지 보안을 사용 하는 경우 `clientCredentialType` 의 특성을 [\<message>](../../configure-apps/file-schema/wcf/message-of-wshttpbinding.md) 로 설정 `UserName` 합니다.

        HTTP (S)를 통해 전송 수준 보안을 사용 하는 경우 `clientCredentialType` 또는의 특성 [\<transport>](../../configure-apps/file-schema/wcf/transport-of-wshttpbinding.md) 을 [\<transport>](../../configure-apps/file-schema/wcf/transport-of-basichttpbinding.md) 로 설정 `Basic` 합니다.

        > [!NOTE]
        > WCF 서비스에서 인터넷 정보 서비스 (IIS) 전송 수준 보안을 사용 하 여 호스팅된 경우 및 <xref:System.ServiceModel.Security.UserNamePasswordServiceCredential.UserNamePasswordValidationMode%2A> 속성이 <xref:System.ServiceModel.Security.UserNamePasswordValidationMode.Custom>, 사용자 지정 인증 체계는 Windows 인증의 하위 집합을 사용 합니다. 이것은 IIS이이 시나리오에서는 WCF 사용자 지정 인증자를 호출 하기 전에 Windows 인증을 수행 합니다.

    WCF 바인딩 요소를 만드는 방법에 대 한 자세한 내용은 [방법: 구성에서 서비스 바인딩 지정](../how-to-specify-a-service-binding-in-configuration.md)을 참조 하세요.

    다음 예제는 바인딩에 대 한 구성 코드를 보여 줍니다.

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

    1. 요소에 대 한 자식으로 [\<system.serviceModel>](../../configure-apps/file-schema/wcf/system-servicemodel.md) 요소를 추가 [\<behaviors>](../../configure-apps/file-schema/wcf/behaviors.md) 합니다.

    2. [\<serviceBehaviors>](../../configure-apps/file-schema/wcf/servicebehaviors.md)요소에를 추가 [\<behaviors>](../../configure-apps/file-schema/wcf/behaviors.md) 합니다.

    3. 요소를 추가 [\<behavior>](../../configure-apps/file-schema/wcf/behavior-of-servicebehaviors.md) 하 고 `name` 특성을 적절 한 값으로 설정 합니다.

    4. [\<serviceCredentials>](../../configure-apps/file-schema/wcf/servicecredentials.md)요소에를 추가 [\<behavior>](../../configure-apps/file-schema/wcf/behavior-of-servicebehaviors.md) 합니다.

    5. 에를 추가 [\<userNameAuthentication>](../../configure-apps/file-schema/wcf/usernameauthentication.md) [\<serviceCredentials>](../../configure-apps/file-schema/wcf/servicecredentials.md) 합니다.

    6. `userNamePasswordValidationMode`을 `Custom`으로 설정합니다.

        > [!IMPORTANT]
        > 값을 `userNamePasswordValidationMode` 설정 하지 않으면 WCF는 사용자 지정 사용자 이름 및 암호 유효성 검사기 대신 Windows 인증을 사용 합니다.

    7. `customUserNamePasswordValidatorType`을 사용자 지정 사용자 이름 및 암호 유효성 검사기를 나타내는 형식으로 설정합니다.

    다음 예제에서는 `<serviceCredentials>` 이 지점의 조각을 보여 줍니다.

    ```xml
    <serviceCredentials>
      <userNameAuthentication userNamePasswordValidationMode="Custom" customUserNamePasswordValidatorType="Microsoft.ServiceModel.Samples.CalculatorService.CustomUserNameValidator, service" />
    </serviceCredentials>
    ```

## <a name="example"></a>예제

다음 코드 예제에서는 사용자 지정 사용자 이름 및 암호 유효성 검사기를 만드는 방법을 보여 줍니다. 프로덕션 환경에서는 <xref:System.IdentityModel.Selectors.UserNamePasswordValidator.Validate%2A> 메서드를 재정의하는 코드를 사용하지 않습니다. 코드를 사용자 지정 사용자 이름 및 암호 유효성 검사 스키마로 바꿉니다. 이 스키마는 데이터베이스에서 사용자 이름과 암호 쌍을 검색합니다.

[!code-csharp[C_CustomUsernameAndPasswordValidator#1](~/samples/snippets/csharp/VS_Snippets_CFX/c_customusernameandpasswordvalidator/cs/service.cs#1)]
[!code-vb[C_CustomUsernameAndPasswordValidator#1](~/samples/snippets/visualbasic/VS_Snippets_CFX/c_customusernameandpasswordvalidator/vb/service.vb#1)]
[!code-csharp[C_CustomUsernameAndPasswordValidator#2](~/samples/snippets/csharp/VS_Snippets_CFX/c_customusernameandpasswordvalidator/cs/service.cs#2)]
[!code-vb[C_CustomUsernameAndPasswordValidator#2](~/samples/snippets/visualbasic/VS_Snippets_CFX/c_customusernameandpasswordvalidator/vb/service.vb#2)]

## <a name="see-also"></a>참고 항목

- <xref:System.IdentityModel.Selectors.UserNamePasswordValidator>
- [방법: ASP.NET 멤버 자격 공급자 사용](how-to-use-the-aspnet-membership-provider.md)
- [인증](authentication-in-wcf.md)
