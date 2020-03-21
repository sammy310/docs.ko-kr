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
# <a name="how-to-create-a-service-that-employs-a-custom-certificate-validator"></a><span data-ttu-id="897d8-102">방법: 사용자 지정 인증서 유효성 검사기를 사용하는 서비스 만들기</span><span class="sxs-lookup"><span data-stu-id="897d8-102">How to: Create a Service that Employs a Custom Certificate Validator</span></span>
<span data-ttu-id="897d8-103">이 항목에서는 사용자 지정 인증서 유효성 검사기를 구현하는 방법과 클라이언트 또는 서비스 자격 증명을 구성하여 기본 인증서 유효성 검사 논리를 사용자 지정 인증서 유효성 검사기로 바꾸는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="897d8-103">This topic shows how to implement a custom certificate validator and how to configure client or service credentials to replace the default certificate validation logic with the custom certificate validator.</span></span>  
  
 <span data-ttu-id="897d8-104">X.509 인증서가 클라이언트 또는 서비스를 인증하는 데 사용되는 경우 WCF(Windows 통신 재단)는 기본적으로 Windows 인증서 저장소및 암호화 API를 사용하여 인증서의 유효성을 검사하고 신뢰할 수 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="897d8-104">If the X.509 certificate is used to authenticate a client or service, Windows Communication Foundation (WCF) by default uses the Windows certificate store and Crypto API to validate the certificate and to ensure that it is trusted.</span></span> <span data-ttu-id="897d8-105">기본 제공 인증서 유효성 검사 기능으로 충분하지 않은 경우에는 변경해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="897d8-105">Sometimes the built-in certificate validation functionality is not enough and must be changed.</span></span> <span data-ttu-id="897d8-106">WCF는 사용자가 사용자 지정 인증서 유효성 검사기를 추가할 수 있도록 하여 유효성 검사 논리를 쉽게 변경할 수 있는 방법을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="897d8-106">WCF provides an easy way to change the validation logic by allowing users to add a custom certificate validator.</span></span> <span data-ttu-id="897d8-107">사용자 지정 인증서 유효성 검사자가 지정되면 WCF는 기본 제공 인증서 유효성 검사 논리를 사용하지 않고 대신 사용자 지정 유효성 검사기에서 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="897d8-107">If a custom certificate validator is specified, WCF does not use the built-in certificate validation logic but relies on the custom validator instead.</span></span>  
  
## <a name="procedures"></a><span data-ttu-id="897d8-108">프로시저</span><span class="sxs-lookup"><span data-stu-id="897d8-108">Procedures</span></span>  
  
#### <a name="to-create-a-custom-certificate-validator"></a><span data-ttu-id="897d8-109">사용자 지정 인증서 유효성 검사기를 만들려면</span><span class="sxs-lookup"><span data-stu-id="897d8-109">To create a custom certificate validator</span></span>  
  
1. <span data-ttu-id="897d8-110"><xref:System.IdentityModel.Selectors.X509CertificateValidator>에서 파생된 새 클래스를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="897d8-110">Define a new class derived from <xref:System.IdentityModel.Selectors.X509CertificateValidator>.</span></span>  
  
2. <span data-ttu-id="897d8-111">추상 <xref:System.IdentityModel.Selectors.X509CertificateValidator.Validate%2A> 메서드를 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="897d8-111">Implement the abstract <xref:System.IdentityModel.Selectors.X509CertificateValidator.Validate%2A> method.</span></span> <span data-ttu-id="897d8-112">유효성을 검사해야 하는 인증서는 인수로 메서드에 전달됩니다.</span><span class="sxs-lookup"><span data-stu-id="897d8-112">The certificate that must be validated is passed as an argument to the method.</span></span> <span data-ttu-id="897d8-113">전달된 인증서가 유효성 검사 논리에 따라 유효하지 않은 경우 이 메서드는 <xref:System.IdentityModel.Tokens.SecurityTokenValidationException>을 throw합니다.</span><span class="sxs-lookup"><span data-stu-id="897d8-113">If the passed certificate is not valid according to the validation logic, this method throws a <xref:System.IdentityModel.Tokens.SecurityTokenValidationException>.</span></span> <span data-ttu-id="897d8-114">인증서가 유효하면 메서드가 호출자에게 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="897d8-114">If the certificate is valid, the method returns to the caller.</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="897d8-115">인증 오류를 다시 클라이언트에 반환하려면 <xref:System.ServiceModel.FaultException> 메서드에서 <xref:System.IdentityModel.Selectors.UserNamePasswordValidator.Validate%2A>을 throw합니다.</span><span class="sxs-lookup"><span data-stu-id="897d8-115">To return authentication errors back to the client, throw a <xref:System.ServiceModel.FaultException> in the <xref:System.IdentityModel.Selectors.UserNamePasswordValidator.Validate%2A> method.</span></span>  
  
 [!code-csharp[c_CustomCertificateValidator#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customcertificatevalidator/cs/source.cs#2)]
 [!code-vb[c_CustomCertificateValidator#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customcertificatevalidator/vb/source.vb#2)]  
  
#### <a name="to-specify-a-custom-certificate-validator-in-service-configuration"></a><span data-ttu-id="897d8-116">서비스 구성에 사용자 지정 인증서 유효성 검사기를 지정하려면</span><span class="sxs-lookup"><span data-stu-id="897d8-116">To specify a custom certificate validator in service configuration</span></span>  
  
1. <span data-ttu-id="897d8-117">동작>요소 및 [ \<service를 추가합니다.serviceModel](../../configure-apps/file-schema/wcf/servicebehaviors.md)>요소에>행동합니다. [ \<](../../configure-apps/file-schema/wcf/behaviors.md) [ \<](../../configure-apps/file-schema/wcf/system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="897d8-117">Add a [\<behaviors>](../../configure-apps/file-schema/wcf/behaviors.md) element and a [\<serviceBehaviors>](../../configure-apps/file-schema/wcf/servicebehaviors.md) to the [\<system.serviceModel>](../../configure-apps/file-schema/wcf/system-servicemodel.md) element.</span></span>  
  
2. <span data-ttu-id="897d8-118">>[ \<동작을](../../configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md) 추가하고 `name` 특성을 적절한 값으로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="897d8-118">Add a [\<behavior>](../../configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md) and set the `name` attribute to an appropriate value.</span></span>  
  
3. <span data-ttu-id="897d8-119">`<behavior>` 요소에 [ \<서비스 자격 증명>추가합니다.](../../configure-apps/file-schema/wcf/servicecredentials.md)</span><span class="sxs-lookup"><span data-stu-id="897d8-119">Add a [\<serviceCredentials>](../../configure-apps/file-schema/wcf/servicecredentials.md) to the `<behavior>` element.</span></span>  
  
4. <span data-ttu-id="897d8-120">`<clientCertificate>` 요소를 `<serviceCredentials>` 요소에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="897d8-120">Add a `<clientCertificate>` element to the `<serviceCredentials>` element.</span></span>  
  
5. <span data-ttu-id="897d8-121">요소에 [ \<인증>](../../configure-apps/file-schema/wcf/authentication-of-clientcertificate-element.md) 추가합니다. `<clientCertificate>`</span><span class="sxs-lookup"><span data-stu-id="897d8-121">Add an [\<authentication>](../../configure-apps/file-schema/wcf/authentication-of-clientcertificate-element.md) to the `<clientCertificate>` element.</span></span>  
  
6. <span data-ttu-id="897d8-122">`customCertificateValidatorType` 특성을 유효성 검사기 형식으로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="897d8-122">Set the `customCertificateValidatorType` attribute to the validator type.</span></span> <span data-ttu-id="897d8-123">다음 예제에서는 특성을 형식의 네임스페이스 및 이름으로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="897d8-123">The following example sets the attribute to the namespace and name of the type.</span></span>  
  
7. <span data-ttu-id="897d8-124">`certificateValidationMode` 특성을 `Custom`으로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="897d8-124">Set the `certificateValidationMode` attribute to `Custom`.</span></span>  
  
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
  
#### <a name="to-specify-a-custom-certificate-validator-using-configuration-on-the-client"></a><span data-ttu-id="897d8-125">클라이언트에 구성을 사용하여 사용자 지정 인증서 유효성 검사기를 지정하려면</span><span class="sxs-lookup"><span data-stu-id="897d8-125">To specify a custom certificate validator using configuration on the client</span></span>  
  
1. <span data-ttu-id="897d8-126">동작>요소 및 [ \<service를 추가합니다.serviceModel](../../configure-apps/file-schema/wcf/servicebehaviors.md)>요소에>행동합니다. [ \<](../../configure-apps/file-schema/wcf/behaviors.md) [ \<](../../configure-apps/file-schema/wcf/system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="897d8-126">Add a [\<behaviors>](../../configure-apps/file-schema/wcf/behaviors.md) element and a [\<serviceBehaviors>](../../configure-apps/file-schema/wcf/servicebehaviors.md) to the [\<system.serviceModel>](../../configure-apps/file-schema/wcf/system-servicemodel.md) element.</span></span>  
  
2. <span data-ttu-id="897d8-127">끝점>요소를 추가합니다. [ \<](../../configure-apps/file-schema/wcf/endpointbehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="897d8-127">Add an [\<endpointBehaviors>](../../configure-apps/file-schema/wcf/endpointbehaviors.md) element.</span></span>  
  
3. <span data-ttu-id="897d8-128">`<behavior>` 요소를 추가하고 `name` 특성을 적절한 값으로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="897d8-128">Add a `<behavior>` element and set the `name` attribute to an appropriate value.</span></span>  
  
4. <span data-ttu-id="897d8-129">클라이언트 [ \<자격 증명>요소를 추가합니다.](../../configure-apps/file-schema/wcf/clientcredentials.md)</span><span class="sxs-lookup"><span data-stu-id="897d8-129">Add a [\<clientCredentials>](../../configure-apps/file-schema/wcf/clientcredentials.md) element.</span></span>  
  
5. <span data-ttu-id="897d8-130">서비스 추가인증서>. [ \< ](../../configure-apps/file-schema/wcf/servicecertificate-of-clientcredentials-element.md)</span><span class="sxs-lookup"><span data-stu-id="897d8-130">Add a [\<serviceCertificate>](../../configure-apps/file-schema/wcf/servicecertificate-of-clientcredentials-element.md).</span></span>  
  
6. <span data-ttu-id="897d8-131">다음 [ \<](../../configure-apps/file-schema/wcf/authentication-of-servicecertificate-element.md) 예제와 같이 인증>추가합니다.</span><span class="sxs-lookup"><span data-stu-id="897d8-131">Add an [\<authentication>](../../configure-apps/file-schema/wcf/authentication-of-servicecertificate-element.md) as shown on the following example.</span></span>  
  
7. <span data-ttu-id="897d8-132">`customCertificateValidatorType` 특성을 유효성 검사기 형식으로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="897d8-132">Set the `customCertificateValidatorType` attribute to the validator type.</span></span>  
  
8. <span data-ttu-id="897d8-133">`certificateValidationMode` 특성을 `Custom`으로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="897d8-133">Set the `certificateValidationMode` attribute to `Custom`.</span></span> <span data-ttu-id="897d8-134">다음 예제에서는 특성을 형식의 네임스페이스 및 이름으로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="897d8-134">The following example sets the attribute to the namespace and name of the type.</span></span>  
  
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
  
#### <a name="to-specify-a-custom-certificate-validator-using-code-on-the-service"></a><span data-ttu-id="897d8-135">서비스에 코드를 사용하여 사용자 지정 인증서 유효성 검사기를 지정하려면</span><span class="sxs-lookup"><span data-stu-id="897d8-135">To specify a custom certificate validator using code on the service</span></span>  
  
1. <span data-ttu-id="897d8-136"><xref:System.ServiceModel.Description.ServiceCredentials.ClientCertificate%2A> 속성에 사용자 지정 인증서 유효성 검사기를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="897d8-136">Specify the custom certificate validator on the <xref:System.ServiceModel.Description.ServiceCredentials.ClientCertificate%2A> property.</span></span> <span data-ttu-id="897d8-137"><xref:System.ServiceModel.ServiceHostBase.Credentials%2A> 속성을 사용하여 서비스 자격 증명에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="897d8-137">You can access the service credentials using the <xref:System.ServiceModel.ServiceHostBase.Credentials%2A> property.</span></span>  
  
2. <span data-ttu-id="897d8-138"><xref:System.ServiceModel.Security.X509ClientCertificateAuthentication.CertificateValidationMode%2A> 속성을 <xref:System.ServiceModel.Security.X509CertificateValidationMode.Custom>로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="897d8-138">Set the <xref:System.ServiceModel.Security.X509ClientCertificateAuthentication.CertificateValidationMode%2A> property to <xref:System.ServiceModel.Security.X509CertificateValidationMode.Custom>.</span></span>  
  
 [!code-csharp[c_CustomCertificateValidator#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customcertificatevalidator/cs/source.cs#1)]
 [!code-vb[c_CustomCertificateValidator#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customcertificatevalidator/vb/source.vb#1)]  
  
#### <a name="to-specify-a-custom-certificate-validator-using-code-on-the-client"></a><span data-ttu-id="897d8-139">클라이언트에 코드를 사용하여 사용자 지정 인증서 유효성 검사기를 지정하려면</span><span class="sxs-lookup"><span data-stu-id="897d8-139">To specify a custom certificate validator using code on the client</span></span>  
  
1. <span data-ttu-id="897d8-140"><xref:System.ServiceModel.Security.X509ServiceCertificateAuthentication.CustomCertificateValidator%2A> 속성을 사용하여 사용자 지정 인증서 유효성 검사기를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="897d8-140">Specify the custom certificate validator using the <xref:System.ServiceModel.Security.X509ServiceCertificateAuthentication.CustomCertificateValidator%2A> property.</span></span> <span data-ttu-id="897d8-141"><xref:System.ServiceModel.ServiceHostBase.Credentials%2A> 속성을 사용하여 클라이언트 자격 증명에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="897d8-141">You can access the client credentials using the <xref:System.ServiceModel.ServiceHostBase.Credentials%2A> property.</span></span> <span data-ttu-id="897d8-142">서비스 모델 메타 [데이터 유틸리티 도구 (Svcutil.exe)에](../servicemodel-metadata-utility-tool-svcutil-exe.md) 의해 <xref:System.ServiceModel.ClientBase%601> 생성 된 클라이언트 클래스는 항상 클래스에서 파생 됩니다.)</span><span class="sxs-lookup"><span data-stu-id="897d8-142">(The client class generated by [ServiceModel Metadata Utility Tool (Svcutil.exe)](../servicemodel-metadata-utility-tool-svcutil-exe.md) always derives from the <xref:System.ServiceModel.ClientBase%601> class.)</span></span>  
  
2. <span data-ttu-id="897d8-143"><xref:System.ServiceModel.Security.X509ServiceCertificateAuthentication.CertificateValidationMode%2A> 속성을 <xref:System.ServiceModel.Security.X509CertificateValidationMode.Custom>로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="897d8-143">Set the <xref:System.ServiceModel.Security.X509ServiceCertificateAuthentication.CertificateValidationMode%2A> property to <xref:System.ServiceModel.Security.X509CertificateValidationMode.Custom>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="897d8-144">예제</span><span class="sxs-lookup"><span data-stu-id="897d8-144">Example</span></span>  
  
### <a name="description"></a><span data-ttu-id="897d8-145">Description</span><span class="sxs-lookup"><span data-stu-id="897d8-145">Description</span></span>  
 <span data-ttu-id="897d8-146">다음 샘플에서는 서비스에 사용자 지정 인증서 유효성 검사기를 구현하고 사용하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="897d8-146">The following sample shows an implementation of a custom certificate validator and its usage on the service.</span></span>  
  
### <a name="code"></a><span data-ttu-id="897d8-147">코드</span><span class="sxs-lookup"><span data-stu-id="897d8-147">Code</span></span>  
 [!code-csharp[c_CustomCertificateValidator#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customcertificatevalidator/cs/source.cs#3)]
 [!code-vb[c_CustomCertificateValidator#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customcertificatevalidator/vb/source.vb#3)]  
  
## <a name="see-also"></a><span data-ttu-id="897d8-148">참고 항목</span><span class="sxs-lookup"><span data-stu-id="897d8-148">See also</span></span>

- <xref:System.IdentityModel.Selectors.X509CertificateValidator>
