---
description: '다음에 대 한 자세한 정보:: <serviceCertificate><serviceCredentials>'
title: <serviceCredentials>의 <serviceCertificate>
ms.date: 03/30/2017
ms.assetid: 597ae6d5-4938-4950-9f5e-b2280e816182
ms.openlocfilehash: ab52f27949168562ec0cab0433c95843a7c312d0
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99786735"
---
# <a name="servicecertificate-of-servicecredentials"></a><span data-ttu-id="155bd-103">\<serviceCredentials>의 \<serviceCertificate></span><span class="sxs-lookup"><span data-stu-id="155bd-103">\<serviceCertificate> of \<serviceCredentials></span></span>

<span data-ttu-id="155bd-104">메시지 보안 모드를 사용하는 클라이언트에 대한 서비스를 인증하는 데 사용할 X.509 인증서를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="155bd-104">Specify an X.509 certificate that will be used to authenticate the service to clients using Message security mode.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceCredentials>**](servicecredentials.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<serviceCertificate>**  
  
## <a name="syntax"></a><span data-ttu-id="155bd-105">구문</span><span class="sxs-lookup"><span data-stu-id="155bd-105">Syntax</span></span>  
  
```xml  
<serviceCertificate findValue="String"
                    storeLocation="LocalMachine/CurrentUser"
                    storeName="AddressBook/AuthRoot/CertificateAuthority/Disallowed/My/Root/TrustedPeople/TrustedPublisher"
                    x509FindType="FindByThumbprint/FindBySubjectName/FindBySubjectDistinguishedName/FindByIssuerName/FindByIssuerDistinguishedName/FindBySerialNumber/FindByTimeValid/FindByTimeNotYetValid/FindByTemplateName/FindByApplicationPolicy/FindByCertificatePolicy/FindByExtension/FindByKeyUsage/FindBySubjectKeyIdentifier" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="155bd-106">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="155bd-106">Attributes and Elements</span></span>  

 <span data-ttu-id="155bd-107">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="155bd-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="155bd-108">특성</span><span class="sxs-lookup"><span data-stu-id="155bd-108">Attributes</span></span>  
  
|<span data-ttu-id="155bd-109">attribute</span><span class="sxs-lookup"><span data-stu-id="155bd-109">Attribute</span></span>|<span data-ttu-id="155bd-110">설명</span><span class="sxs-lookup"><span data-stu-id="155bd-110">Description</span></span>|  
|---------------|-----------------|  
|`findValue`|<span data-ttu-id="155bd-111">X.509 인증서 저장소에서 검색할 값을 포함하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="155bd-111">A string that contains the value to search for in the X.509 certificate store.</span></span> <span data-ttu-id="155bd-112">이 특성에 포함된 형식은 지정된 X509FindType에 대한 요구 사항을 충족해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="155bd-112">The type contained in the attribute must satisfy the requirements of the specified X509FindType.</span></span> <span data-ttu-id="155bd-113">기본값은 빈 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="155bd-113">The default is an empty string.</span></span>|  
|`storeLocation`|<span data-ttu-id="155bd-114">클라이언트가 서버 인증서의 유효성을 검사하는 데 사용하는 X.509 인증서 저장소 위치를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="155bd-114">Specifies the location of the X.509 certificate store that the client uses to validate the server’s certificate against.</span></span> <span data-ttu-id="155bd-115">유효한 값은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="155bd-115">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="155bd-116">-LocalMachine: 로컬 컴퓨터에 할당 된 인증서 저장소입니다.</span><span class="sxs-lookup"><span data-stu-id="155bd-116">-   LocalMachine: the certificate store assigned to the local machine.</span></span><br /><span data-ttu-id="155bd-117">-CurrentUser: 현재 사용자에 게 할당 된 인증서 저장소입니다.</span><span class="sxs-lookup"><span data-stu-id="155bd-117">-   CurrentUser: the certificate store assigned to the current user.</span></span><br /><br /> <span data-ttu-id="155bd-118">기본값은 LocalMachine입니다.</span><span class="sxs-lookup"><span data-stu-id="155bd-118">The default is LocalMachine.</span></span>|  
|`storeName`|<span data-ttu-id="155bd-119">열려는 X.509 인증서 저장소의 이름을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="155bd-119">Specifies the name of the X.509 certificate store to open.</span></span> <span data-ttu-id="155bd-120">유효한 값은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="155bd-120">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="155bd-121">-AddressBook: 다른 사용자에 대 한 인증서 저장소입니다.</span><span class="sxs-lookup"><span data-stu-id="155bd-121">-   AddressBook: Certificate store for other users.</span></span><br /><span data-ttu-id="155bd-122">-AuthRoot: 타사 Ca (인증 기관) 용 인증서 저장소입니다.</span><span class="sxs-lookup"><span data-stu-id="155bd-122">-   AuthRoot: Certificate store for third-party certification authorities (CAs).</span></span><br /><span data-ttu-id="155bd-123">-CertificatAuthority: 중간 Ca (인증 기관) 용 인증서 저장소입니다.</span><span class="sxs-lookup"><span data-stu-id="155bd-123">-   CertificatAuthority: Certificate store for intermediate certification authorities (CAs).</span></span><br /><span data-ttu-id="155bd-124">-허용 안 함: 해지 된 인증서의 인증서 저장소입니다.</span><span class="sxs-lookup"><span data-stu-id="155bd-124">-   Disallowed: Certificate store for revoked certificates.</span></span><br /><span data-ttu-id="155bd-125">-My: 개인 인증서용 인증서 저장소입니다.</span><span class="sxs-lookup"><span data-stu-id="155bd-125">-   My: Certificate store for personal certificates.</span></span><br /><span data-ttu-id="155bd-126">-Root: 신뢰할 수 있는 루트 Ca (인증 기관) 용 인증서 저장소입니다.</span><span class="sxs-lookup"><span data-stu-id="155bd-126">-   Root: Certificate store for trusted root certification authorities (CAs).</span></span><br /><span data-ttu-id="155bd-127">-개인 사용자: 직접 신뢰할 수 있는 사용자 및 리소스에 대 한 인증서 저장소입니다.</span><span class="sxs-lookup"><span data-stu-id="155bd-127">-   TrustedPeople: Certificate store for directly trusted people and resources.</span></span><br /><span data-ttu-id="155bd-128">-신뢰할 수 있는 게시자: 직접 신뢰할 수 있는 게시자 용 인증서 저장소입니다.</span><span class="sxs-lookup"><span data-stu-id="155bd-128">-   TrustedPublisher: Certificate store for directly trusted publishers.</span></span><br /><br /> <span data-ttu-id="155bd-129">기본값은 My입니다.</span><span class="sxs-lookup"><span data-stu-id="155bd-129">The default is My.</span></span>|  
|`x509FindType`|<span data-ttu-id="155bd-130">실행할 X.509 검색의 유형을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="155bd-130">Defines the type of X.509 search to be executed.</span></span> <span data-ttu-id="155bd-131">유효한 값은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="155bd-131">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="155bd-132">-FindByThumbprint</span><span class="sxs-lookup"><span data-stu-id="155bd-132">-   FindByThumbprint</span></span><br /><span data-ttu-id="155bd-133">-FindBySubjectName</span><span class="sxs-lookup"><span data-stu-id="155bd-133">-   FindBySubjectName</span></span><br /><span data-ttu-id="155bd-134">-FindBySubjectDistinguishedName</span><span class="sxs-lookup"><span data-stu-id="155bd-134">-   FindBySubjectDistinguishedName</span></span><br /><span data-ttu-id="155bd-135">- FindByIssuerName</span><span class="sxs-lookup"><span data-stu-id="155bd-135">-   FindByIssuerName</span></span><br /><span data-ttu-id="155bd-136">- FindByIssuerDistinguishedName</span><span class="sxs-lookup"><span data-stu-id="155bd-136">-   FindByIssuerDistinguishedName</span></span><br /><span data-ttu-id="155bd-137">-FindBySerialNumber</span><span class="sxs-lookup"><span data-stu-id="155bd-137">-   FindBySerialNumber</span></span><br /><span data-ttu-id="155bd-138">- FindByTimeValid</span><span class="sxs-lookup"><span data-stu-id="155bd-138">-   FindByTimeValid</span></span><br /><span data-ttu-id="155bd-139">- FindByTimeNotYetValid</span><span class="sxs-lookup"><span data-stu-id="155bd-139">-   FindByTimeNotYetValid</span></span><br /><span data-ttu-id="155bd-140">- FindByTemplateName</span><span class="sxs-lookup"><span data-stu-id="155bd-140">-   FindByTemplateName</span></span><br /><span data-ttu-id="155bd-141">- FindByApplicationPolicy</span><span class="sxs-lookup"><span data-stu-id="155bd-141">-   FindByApplicationPolicy</span></span><br /><span data-ttu-id="155bd-142">- FindByCertificatePolicy</span><span class="sxs-lookup"><span data-stu-id="155bd-142">-   FindByCertificatePolicy</span></span><br /><span data-ttu-id="155bd-143">- FindByExtension</span><span class="sxs-lookup"><span data-stu-id="155bd-143">-   FindByExtension</span></span><br /><span data-ttu-id="155bd-144">- FindByKeyUsage</span><span class="sxs-lookup"><span data-stu-id="155bd-144">-   FindByKeyUsage</span></span><br /><span data-ttu-id="155bd-145">- FindBySubjectKeyIdentifier</span><span class="sxs-lookup"><span data-stu-id="155bd-145">-   FindBySubjectKeyIdentifier</span></span><br /><br /> <span data-ttu-id="155bd-146">`findValue` 특성에 포함된 형식은 지정된 X509FindType에 대한 요구 사항을 충족해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="155bd-146">The type contained in the `findValue` attribute must satisfy the requirements of the specified X509FindType.</span></span><br /><br /> <span data-ttu-id="155bd-147">기본값은 FindBySubjectDistinguishedName입니다.</span><span class="sxs-lookup"><span data-stu-id="155bd-147">The default value is FindBySubjectDistinguishedName.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="155bd-148">자식 요소</span><span class="sxs-lookup"><span data-stu-id="155bd-148">Child Elements</span></span>  

 <span data-ttu-id="155bd-149">없음</span><span class="sxs-lookup"><span data-stu-id="155bd-149">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="155bd-150">부모 요소</span><span class="sxs-lookup"><span data-stu-id="155bd-150">Parent Elements</span></span>  
  
|<span data-ttu-id="155bd-151">요소</span><span class="sxs-lookup"><span data-stu-id="155bd-151">Element</span></span>|<span data-ttu-id="155bd-152">설명</span><span class="sxs-lookup"><span data-stu-id="155bd-152">Description</span></span>|  
|-------------|-----------------|  
|[\<serviceCredentials>](servicecredentials.md)|<span data-ttu-id="155bd-153">서비스를 인증하는 데 사용되는 자격 증명 및 클라이언트 자격 증명 확인 관련 설정을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="155bd-153">Specifies the credential to be used in authenticating the service, and the client credential validation related settings.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="155bd-154">설명</span><span class="sxs-lookup"><span data-stu-id="155bd-154">Remarks</span></span>  

 <span data-ttu-id="155bd-155">이 요소를 사용하여 메시지 보안 모드를 사용하는 클라이언트에 대한 서비스를 인증하는 데 사용할 X.509 인증서를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="155bd-155">Use this element to specify an X.509 certificate that will be used to authenticate the service to clients using Message security mode.</span></span> <span data-ttu-id="155bd-156">주기적으로 갱신되는 인증서를 사용하는 경우 지문이 변경됩니다.</span><span class="sxs-lookup"><span data-stu-id="155bd-156">If you are using a certificate that will be periodically renewed, then its thumbprint will change.</span></span> <span data-ttu-id="155bd-157">이러한 경우 인증서를 동일한 주체 이름으로 다시 발급할 수 있기 때문에 주체 이름으로 `x509FindType`을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="155bd-157">In that case, use the subject name as the `x509FindType` because the certificate can be reissued with the same subject name.</span></span>  
  
 <span data-ttu-id="155bd-158">요소를 사용 하는 방법에 대 한 자세한 내용은 [방법: 클라이언트 자격 증명 값 지정을](../../../wcf/how-to-specify-client-credential-values.md)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="155bd-158">For more information about using the element, see [How to: Specify Client Credential Values](../../../wcf/how-to-specify-client-credential-values.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="155bd-159">참고 항목</span><span class="sxs-lookup"><span data-stu-id="155bd-159">See also</span></span>

- <xref:System.ServiceModel.Configuration.X509RecipientCertificateServiceElement>
- <xref:System.ServiceModel.Configuration.ServiceCredentialsElement.ServiceCertificate%2A>
- <xref:System.ServiceModel.Security.X509CertificateRecipientServiceCredential>
- <xref:System.ServiceModel.Description.ServiceCredentials.ServiceCertificate%2A>
- [<span data-ttu-id="155bd-160">방법: 클라이언트 자격 증명 값 지정</span><span class="sxs-lookup"><span data-stu-id="155bd-160">How to: Specify Client Credential Values</span></span>](../../../wcf/how-to-specify-client-credential-values.md)
- [<span data-ttu-id="155bd-161">보안 동작</span><span class="sxs-lookup"><span data-stu-id="155bd-161">Security Behaviors</span></span>](../../../wcf/feature-details/security-behaviors-in-wcf.md)
