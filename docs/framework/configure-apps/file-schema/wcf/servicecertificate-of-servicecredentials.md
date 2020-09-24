---
title: <serviceCredentials>의 <serviceCertificate>
ms.date: 03/30/2017
ms.assetid: 597ae6d5-4938-4950-9f5e-b2280e816182
ms.openlocfilehash: 936661595813d7b8f3e894efb7bf6cf3aab7e89e
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/24/2020
ms.locfileid: "91167104"
---
# <a name="servicecertificate-of-servicecredentials"></a><span data-ttu-id="f614a-102">\<serviceCredentials>의 \<serviceCertificate></span><span class="sxs-lookup"><span data-stu-id="f614a-102">\<serviceCertificate> of \<serviceCredentials></span></span>

<span data-ttu-id="f614a-103">메시지 보안 모드를 사용하는 클라이언트에 대한 서비스를 인증하는 데 사용할 X.509 인증서를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="f614a-103">Specify an X.509 certificate that will be used to authenticate the service to clients using Message security mode.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceCredentials>**](servicecredentials.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<serviceCertificate>**  
  
## <a name="syntax"></a><span data-ttu-id="f614a-104">구문</span><span class="sxs-lookup"><span data-stu-id="f614a-104">Syntax</span></span>  
  
```xml  
<serviceCertificate findValue="String"
                    storeLocation="LocalMachine/CurrentUser"
                    storeName="AddressBook/AuthRoot/CertificateAuthority/Disallowed/My/Root/TrustedPeople/TrustedPublisher"
                    x509FindType="FindByThumbprint/FindBySubjectName/FindBySubjectDistinguishedName/FindByIssuerName/FindByIssuerDistinguishedName/FindBySerialNumber/FindByTimeValid/FindByTimeNotYetValid/FindByTemplateName/FindByApplicationPolicy/FindByCertificatePolicy/FindByExtension/FindByKeyUsage/FindBySubjectKeyIdentifier" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="f614a-105">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="f614a-105">Attributes and Elements</span></span>  

 <span data-ttu-id="f614a-106">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="f614a-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="f614a-107">특성</span><span class="sxs-lookup"><span data-stu-id="f614a-107">Attributes</span></span>  
  
|<span data-ttu-id="f614a-108">attribute</span><span class="sxs-lookup"><span data-stu-id="f614a-108">Attribute</span></span>|<span data-ttu-id="f614a-109">설명</span><span class="sxs-lookup"><span data-stu-id="f614a-109">Description</span></span>|  
|---------------|-----------------|  
|`findValue`|<span data-ttu-id="f614a-110">X.509 인증서 저장소에서 검색할 값을 포함하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="f614a-110">A string that contains the value to search for in the X.509 certificate store.</span></span> <span data-ttu-id="f614a-111">이 특성에 포함된 형식은 지정된 X509FindType에 대한 요구 사항을 충족해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f614a-111">The type contained in the attribute must satisfy the requirements of the specified X509FindType.</span></span> <span data-ttu-id="f614a-112">기본값은 빈 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="f614a-112">The default is an empty string.</span></span>|  
|`storeLocation`|<span data-ttu-id="f614a-113">클라이언트가 서버 인증서의 유효성을 검사하는 데 사용하는 X.509 인증서 저장소 위치를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="f614a-113">Specifies the location of the X.509 certificate store that the client uses to validate the server’s certificate against.</span></span> <span data-ttu-id="f614a-114">유효한 값은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="f614a-114">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="f614a-115">-LocalMachine: 로컬 컴퓨터에 할당 된 인증서 저장소입니다.</span><span class="sxs-lookup"><span data-stu-id="f614a-115">-   LocalMachine: the certificate store assigned to the local machine.</span></span><br /><span data-ttu-id="f614a-116">-CurrentUser: 현재 사용자에 게 할당 된 인증서 저장소입니다.</span><span class="sxs-lookup"><span data-stu-id="f614a-116">-   CurrentUser: the certificate store assigned to the current user.</span></span><br /><br /> <span data-ttu-id="f614a-117">기본값은 LocalMachine입니다.</span><span class="sxs-lookup"><span data-stu-id="f614a-117">The default is LocalMachine.</span></span>|  
|`storeName`|<span data-ttu-id="f614a-118">열려는 X.509 인증서 저장소의 이름을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="f614a-118">Specifies the name of the X.509 certificate store to open.</span></span> <span data-ttu-id="f614a-119">유효한 값은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="f614a-119">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="f614a-120">-AddressBook: 다른 사용자에 대 한 인증서 저장소입니다.</span><span class="sxs-lookup"><span data-stu-id="f614a-120">-   AddressBook: Certificate store for other users.</span></span><br /><span data-ttu-id="f614a-121">-AuthRoot: 타사 Ca (인증 기관) 용 인증서 저장소입니다.</span><span class="sxs-lookup"><span data-stu-id="f614a-121">-   AuthRoot: Certificate store for third-party certification authorities (CAs).</span></span><br /><span data-ttu-id="f614a-122">-CertificatAuthority: 중간 Ca (인증 기관) 용 인증서 저장소입니다.</span><span class="sxs-lookup"><span data-stu-id="f614a-122">-   CertificatAuthority: Certificate store for intermediate certification authorities (CAs).</span></span><br /><span data-ttu-id="f614a-123">-허용 안 함: 해지 된 인증서의 인증서 저장소입니다.</span><span class="sxs-lookup"><span data-stu-id="f614a-123">-   Disallowed: Certificate store for revoked certificates.</span></span><br /><span data-ttu-id="f614a-124">-My: 개인 인증서용 인증서 저장소입니다.</span><span class="sxs-lookup"><span data-stu-id="f614a-124">-   My: Certificate store for personal certificates.</span></span><br /><span data-ttu-id="f614a-125">-Root: 신뢰할 수 있는 루트 Ca (인증 기관) 용 인증서 저장소입니다.</span><span class="sxs-lookup"><span data-stu-id="f614a-125">-   Root: Certificate store for trusted root certification authorities (CAs).</span></span><br /><span data-ttu-id="f614a-126">-개인 사용자: 직접 신뢰할 수 있는 사용자 및 리소스에 대 한 인증서 저장소입니다.</span><span class="sxs-lookup"><span data-stu-id="f614a-126">-   TrustedPeople: Certificate store for directly trusted people and resources.</span></span><br /><span data-ttu-id="f614a-127">-신뢰할 수 있는 게시자: 직접 신뢰할 수 있는 게시자 용 인증서 저장소입니다.</span><span class="sxs-lookup"><span data-stu-id="f614a-127">-   TrustedPublisher: Certificate store for directly trusted publishers.</span></span><br /><br /> <span data-ttu-id="f614a-128">기본값은 My입니다.</span><span class="sxs-lookup"><span data-stu-id="f614a-128">The default is My.</span></span>|  
|`x509FindType`|<span data-ttu-id="f614a-129">실행할 X.509 검색의 유형을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="f614a-129">Defines the type of X.509 search to be executed.</span></span> <span data-ttu-id="f614a-130">유효한 값은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="f614a-130">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="f614a-131">-FindByThumbprint</span><span class="sxs-lookup"><span data-stu-id="f614a-131">-   FindByThumbprint</span></span><br /><span data-ttu-id="f614a-132">-FindBySubjectName</span><span class="sxs-lookup"><span data-stu-id="f614a-132">-   FindBySubjectName</span></span><br /><span data-ttu-id="f614a-133">-FindBySubjectDistinguishedName</span><span class="sxs-lookup"><span data-stu-id="f614a-133">-   FindBySubjectDistinguishedName</span></span><br /><span data-ttu-id="f614a-134">- FindByIssuerName</span><span class="sxs-lookup"><span data-stu-id="f614a-134">-   FindByIssuerName</span></span><br /><span data-ttu-id="f614a-135">- FindByIssuerDistinguishedName</span><span class="sxs-lookup"><span data-stu-id="f614a-135">-   FindByIssuerDistinguishedName</span></span><br /><span data-ttu-id="f614a-136">-FindBySerialNumber</span><span class="sxs-lookup"><span data-stu-id="f614a-136">-   FindBySerialNumber</span></span><br /><span data-ttu-id="f614a-137">- FindByTimeValid</span><span class="sxs-lookup"><span data-stu-id="f614a-137">-   FindByTimeValid</span></span><br /><span data-ttu-id="f614a-138">- FindByTimeNotYetValid</span><span class="sxs-lookup"><span data-stu-id="f614a-138">-   FindByTimeNotYetValid</span></span><br /><span data-ttu-id="f614a-139">- FindByTemplateName</span><span class="sxs-lookup"><span data-stu-id="f614a-139">-   FindByTemplateName</span></span><br /><span data-ttu-id="f614a-140">- FindByApplicationPolicy</span><span class="sxs-lookup"><span data-stu-id="f614a-140">-   FindByApplicationPolicy</span></span><br /><span data-ttu-id="f614a-141">- FindByCertificatePolicy</span><span class="sxs-lookup"><span data-stu-id="f614a-141">-   FindByCertificatePolicy</span></span><br /><span data-ttu-id="f614a-142">- FindByExtension</span><span class="sxs-lookup"><span data-stu-id="f614a-142">-   FindByExtension</span></span><br /><span data-ttu-id="f614a-143">- FindByKeyUsage</span><span class="sxs-lookup"><span data-stu-id="f614a-143">-   FindByKeyUsage</span></span><br /><span data-ttu-id="f614a-144">- FindBySubjectKeyIdentifier</span><span class="sxs-lookup"><span data-stu-id="f614a-144">-   FindBySubjectKeyIdentifier</span></span><br /><br /> <span data-ttu-id="f614a-145">`findValue` 특성에 포함된 형식은 지정된 X509FindType에 대한 요구 사항을 충족해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f614a-145">The type contained in the `findValue` attribute must satisfy the requirements of the specified X509FindType.</span></span><br /><br /> <span data-ttu-id="f614a-146">기본값은 FindBySubjectDistinguishedName입니다.</span><span class="sxs-lookup"><span data-stu-id="f614a-146">The default value is FindBySubjectDistinguishedName.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="f614a-147">자식 요소</span><span class="sxs-lookup"><span data-stu-id="f614a-147">Child Elements</span></span>  

 <span data-ttu-id="f614a-148">없음</span><span class="sxs-lookup"><span data-stu-id="f614a-148">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="f614a-149">부모 요소</span><span class="sxs-lookup"><span data-stu-id="f614a-149">Parent Elements</span></span>  
  
|<span data-ttu-id="f614a-150">요소</span><span class="sxs-lookup"><span data-stu-id="f614a-150">Element</span></span>|<span data-ttu-id="f614a-151">설명</span><span class="sxs-lookup"><span data-stu-id="f614a-151">Description</span></span>|  
|-------------|-----------------|  
|[\<serviceCredentials>](servicecredentials.md)|<span data-ttu-id="f614a-152">서비스를 인증하는 데 사용되는 자격 증명 및 클라이언트 자격 증명 확인 관련 설정을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="f614a-152">Specifies the credential to be used in authenticating the service, and the client credential validation related settings.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f614a-153">설명</span><span class="sxs-lookup"><span data-stu-id="f614a-153">Remarks</span></span>  

 <span data-ttu-id="f614a-154">이 요소를 사용하여 메시지 보안 모드를 사용하는 클라이언트에 대한 서비스를 인증하는 데 사용할 X.509 인증서를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="f614a-154">Use this element to specify an X.509 certificate that will be used to authenticate the service to clients using Message security mode.</span></span> <span data-ttu-id="f614a-155">주기적으로 갱신되는 인증서를 사용하는 경우 지문이 변경됩니다.</span><span class="sxs-lookup"><span data-stu-id="f614a-155">If you are using a certificate that will be periodically renewed, then its thumbprint will change.</span></span> <span data-ttu-id="f614a-156">이러한 경우 인증서를 동일한 주체 이름으로 다시 발급할 수 있기 때문에 주체 이름으로 `x509FindType`을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="f614a-156">In that case, use the subject name as the `x509FindType` because the certificate can be reissued with the same subject name.</span></span>  
  
 <span data-ttu-id="f614a-157">요소를 사용 하는 방법에 대 한 자세한 내용은 [방법: 클라이언트 자격 증명 값 지정을](../../../wcf/how-to-specify-client-credential-values.md)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="f614a-157">For more information about using the element, see [How to: Specify Client Credential Values](../../../wcf/how-to-specify-client-credential-values.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f614a-158">참고 항목</span><span class="sxs-lookup"><span data-stu-id="f614a-158">See also</span></span>

- <xref:System.ServiceModel.Configuration.X509RecipientCertificateServiceElement>
- <xref:System.ServiceModel.Configuration.ServiceCredentialsElement.ServiceCertificate%2A>
- <xref:System.ServiceModel.Security.X509CertificateRecipientServiceCredential>
- <xref:System.ServiceModel.Description.ServiceCredentials.ServiceCertificate%2A>
- [<span data-ttu-id="f614a-159">방법: 클라이언트 자격 증명 값 지정</span><span class="sxs-lookup"><span data-stu-id="f614a-159">How to: Specify Client Credential Values</span></span>](../../../wcf/how-to-specify-client-credential-values.md)
- [<span data-ttu-id="f614a-160">보안 동작</span><span class="sxs-lookup"><span data-stu-id="f614a-160">Security Behaviors</span></span>](../../../wcf/feature-details/security-behaviors-in-wcf.md)
