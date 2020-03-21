---
title: '방법: 사용자 지정 인증서 유효성 검사기를 사용하는 서비스 만들기'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WCF, authentication
ms.assetid: bb0190ff-0738-4e54-8d22-c97d343708bf
ms.openlocfilehash: af1bb9b2ff793f6e6854c1b253dd445a35a5076f
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79185572"
---
# <a name="how-to-create-a-service-that-employs-a-custom-certificate-validator"></a>방법: 사용자 지정 인증서 유효성 검사기를 사용하는 서비스 만들기
이 항목에서는 사용자 지정 인증서 유효성 검사기를 구현하는 방법과 클라이언트 또는 서비스 자격 증명을 구성하여 기본 인증서 유효성 검사 논리를 사용자 지정 인증서 유효성 검사기로 바꾸는 방법을 보여 줍니다.  
  
 X.509 인증서가 클라이언트 또는 서비스를 인증하는 데 사용되는 경우 WCF(Windows 통신 재단)는 기본적으로 Windows 인증서 저장소및 암호화 API를 사용하여 인증서의 유효성을 검사하고 신뢰할 수 있는지 확인합니다. 기본 제공 인증서 유효성 검사 기능으로 충분하지 않은 경우에는 변경해야 합니다. WCF는 사용자가 사용자 지정 인증서 유효성 검사기를 추가할 수 있도록 하여 유효성 검사 논리를 쉽게 변경할 수 있는 방법을 제공합니다. 사용자 지정 인증서 유효성 검사자가 지정되면 WCF는 기본 제공 인증서 유효성 검사 논리를 사용하지 않고 대신 사용자 지정 유효성 검사기에서 사용합니다.  
  
## <a name="procedures"></a>프로시저  
  
#### <a name="to-create-a-custom-certificate-validator"></a>사용자 지정 인증서 유효성 검사기를 만들려면  
  
1. <xref:System.IdentityModel.Selectors.X509CertificateValidator>에서 파생된 새 클래스를 정의합니다.  
  
2. 추상 <xref:System.IdentityModel.Selectors.X509CertificateValidator.Validate%2A> 메서드를 구현합니다. 유효성을 검사해야 하는 인증서는 인수로 메서드에 전달됩니다. 전달된 인증서가 유효성 검사 논리에 따라 유효하지 않은 경우 이 메서드는 <xref:System.IdentityModel.Tokens.SecurityTokenValidationException>을 throw합니다. 인증서가 유효하면 메서드가 호출자에게 반환됩니다.  
  
    > [!NOTE]
    > 인증 오류를 다시 클라이언트에 반환하려면 <xref:System.ServiceModel.FaultException> 메서드에서 <xref:System.IdentityModel.Selectors.UserNamePasswordValidator.Validate%2A>을 throw합니다.  
  
 [!code-csharp[c_CustomCertificateValidator#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customcertificatevalidator/cs/source.cs#2)]
 [!code-vb[c_CustomCertificateValidator#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customcertificatevalidator/vb/source.vb#2)]  
  
#### <a name="to-specify-a-custom-certificate-validator-in-service-configuration"></a>서비스 구성에 사용자 지정 인증서 유효성 검사기를 지정하려면  
  
1. 동작>요소 및 [ \<service를 추가합니다.serviceModel](../../configure-apps/file-schema/wcf/servicebehaviors.md)>요소에>행동합니다. [ \<](../../configure-apps/file-schema/wcf/behaviors.md) [ \<](../../configure-apps/file-schema/wcf/system-servicemodel.md)  
  
2. >[ \<동작을](../../configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md) 추가하고 `name` 특성을 적절한 값으로 설정합니다.  
  
3. `<behavior>` 요소에 [ \<서비스 자격 증명>추가합니다.](../../configure-apps/file-schema/wcf/servicecredentials.md)  
  
4. `<clientCertificate>` 요소를 `<serviceCredentials>` 요소에 추가합니다.  
  
5. 요소에 [ \<인증>](../../configure-apps/file-schema/wcf/authentication-of-clientcertificate-element.md) 추가합니다. `<clientCertificate>`  
  
6. `customCertificateValidatorType` 특성을 유효성 검사기 형식으로 설정합니다. 다음 예제에서는 특성을 형식의 네임스페이스 및 이름으로 설정합니다.  
  
7. `certificateValidationMode` 특성을 `Custom`으로 설정합니다.  
  
    ```xml  
    <configuration>  
     <system.serviceModel>  
      <behaviors>  
       <serviceBehaviors>  
        <behavior name="ServiceBehavior">  
         <serviceCredentials>  
          <clientCertificate>  
          <authentication certificateValidationMode="Custom" customCertificateValidatorType="Samples.MyValidator, service" />  
          </clientCertificate>  
         </serviceCredentials>  
        </behavior>  
       </serviceBehaviors>  
      </behaviors>  
    </system.serviceModel>  
    </configuration>  
    ```  
  
#### <a name="to-specify-a-custom-certificate-validator-using-configuration-on-the-client"></a>클라이언트에 구성을 사용하여 사용자 지정 인증서 유효성 검사기를 지정하려면  
  
1. 동작>요소 및 [ \<service를 추가합니다.serviceModel](../../configure-apps/file-schema/wcf/servicebehaviors.md)>요소에>행동합니다. [ \<](../../configure-apps/file-schema/wcf/behaviors.md) [ \<](../../configure-apps/file-schema/wcf/system-servicemodel.md)  
  
2. 끝점>요소를 추가합니다. [ \<](../../configure-apps/file-schema/wcf/endpointbehaviors.md)  
  
3. `<behavior>` 요소를 추가하고 `name` 특성을 적절한 값으로 설정합니다.  
  
4. 클라이언트 [ \<자격 증명>요소를 추가합니다.](../../configure-apps/file-schema/wcf/clientcredentials.md)  
  
5. 서비스 추가인증서>. [ \< ](../../configure-apps/file-schema/wcf/servicecertificate-of-clientcredentials-element.md)  
  
6. 다음 [ \<](../../configure-apps/file-schema/wcf/authentication-of-servicecertificate-element.md) 예제와 같이 인증>추가합니다.  
  
7. `customCertificateValidatorType` 특성을 유효성 검사기 형식으로 설정합니다.  
  
8. `certificateValidationMode` 특성을 `Custom`으로 설정합니다. 다음 예제에서는 특성을 형식의 네임스페이스 및 이름으로 설정합니다.  
  
    ```xml  
    <configuration>  
     <system.serviceModel>  
      <behaviors>  
       <endpointBehaviors>  
        <behavior name="clientBehavior">  
         <clientCredentials>  
          <serviceCertificate>  
           <authentication certificateValidationMode="Custom"
                  customCertificateValidatorType=  
             "Samples.CustomX509CertificateValidator, client"/>  
          </serviceCertificate>  
         </clientCredentials>  
        </behavior>  
       </endpointBehaviors>  
      </behaviors>  
     </system.serviceModel>  
    </configuration>  
    ```  
  
#### <a name="to-specify-a-custom-certificate-validator-using-code-on-the-service"></a>서비스에 코드를 사용하여 사용자 지정 인증서 유효성 검사기를 지정하려면  
  
1. <xref:System.ServiceModel.Description.ServiceCredentials.ClientCertificate%2A> 속성에 사용자 지정 인증서 유효성 검사기를 지정합니다. <xref:System.ServiceModel.ServiceHostBase.Credentials%2A> 속성을 사용하여 서비스 자격 증명에 액세스할 수 있습니다.  
  
2. <xref:System.ServiceModel.Security.X509ClientCertificateAuthentication.CertificateValidationMode%2A> 속성을 <xref:System.ServiceModel.Security.X509CertificateValidationMode.Custom>로 설정합니다.  
  
 [!code-csharp[c_CustomCertificateValidator#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customcertificatevalidator/cs/source.cs#1)]
 [!code-vb[c_CustomCertificateValidator#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customcertificatevalidator/vb/source.vb#1)]  
  
#### <a name="to-specify-a-custom-certificate-validator-using-code-on-the-client"></a>클라이언트에 코드를 사용하여 사용자 지정 인증서 유효성 검사기를 지정하려면  
  
1. <xref:System.ServiceModel.Security.X509ServiceCertificateAuthentication.CustomCertificateValidator%2A> 속성을 사용하여 사용자 지정 인증서 유효성 검사기를 지정합니다. <xref:System.ServiceModel.ServiceHostBase.Credentials%2A> 속성을 사용하여 클라이언트 자격 증명에 액세스할 수 있습니다. 서비스 모델 메타 [데이터 유틸리티 도구 (Svcutil.exe)에](../servicemodel-metadata-utility-tool-svcutil-exe.md) 의해 <xref:System.ServiceModel.ClientBase%601> 생성 된 클라이언트 클래스는 항상 클래스에서 파생 됩니다.)  
  
2. <xref:System.ServiceModel.Security.X509ServiceCertificateAuthentication.CertificateValidationMode%2A> 속성을 <xref:System.ServiceModel.Security.X509CertificateValidationMode.Custom>로 설정합니다.  
  
## <a name="example"></a>예제  
  
### <a name="description"></a>Description  
 다음 샘플에서는 서비스에 사용자 지정 인증서 유효성 검사기를 구현하고 사용하는 방법을 보여 줍니다.  
  
### <a name="code"></a>코드  
 [!code-csharp[c_CustomCertificateValidator#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customcertificatevalidator/cs/source.cs#3)]
 [!code-vb[c_CustomCertificateValidator#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customcertificatevalidator/vb/source.vb#3)]  
  
## <a name="see-also"></a>참고 항목

- <xref:System.IdentityModel.Selectors.X509CertificateValidator>
