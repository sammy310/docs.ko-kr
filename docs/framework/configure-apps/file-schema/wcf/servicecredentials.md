---
title: <serviceCredentials>
ms.date: 03/30/2017
ms.assetid: 96db336c-4f7a-4193-81a5-910b8ffd804f
ms.openlocfilehash: d9f8fdf272962916cd08aede484e9bbde55b96a3
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59227082"
---
# <a name="servicecredentials"></a><span data-ttu-id="474be-101">\<serviceCredentials></span><span class="sxs-lookup"><span data-stu-id="474be-101">\<serviceCredentials></span></span>
<span data-ttu-id="474be-102">서비스를 인증하는 데 사용되는 자격 증명 및 클라이언트 자격 증명 유효성 검사 관련 설정을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="474be-102">Specifies the credential to be used in authenticating the service and the client credential validation-related settings.</span></span>  
  
 <span data-ttu-id="474be-103">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="474be-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="474be-104">\<behaviors></span><span class="sxs-lookup"><span data-stu-id="474be-104">\<behaviors></span></span>  
<span data-ttu-id="474be-105">\<serviceBehaviors></span><span class="sxs-lookup"><span data-stu-id="474be-105">\<serviceBehaviors></span></span>  
<span data-ttu-id="474be-106">\<behavior></span><span class="sxs-lookup"><span data-stu-id="474be-106">\<behavior></span></span>  
<span data-ttu-id="474be-107">\<serviceCredentials></span><span class="sxs-lookup"><span data-stu-id="474be-107">\<serviceCredentials></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="474be-108">구문</span><span class="sxs-lookup"><span data-stu-id="474be-108">Syntax</span></span>  
  
```xml  
<serviceCredentials type="String">
  <clientCertificate>
  </clientCertificate>
  <issuedTokenAuthentication>
  </issuedTokenAuthentication>
  <peer>
  </peer>
  <secureConversationAuthentication>
  </secureConversationAuthentication>
  <serviceCertificate>
  </serviceCertificate>
  <userNameAuthentication>
  </userNameAuthentication>
  <windowsAuthentication>
  </windowsAuthentication>
</serviceCredentials>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="474be-109">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="474be-109">Attributes and Elements</span></span>  
 <span data-ttu-id="474be-110">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="474be-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="474be-111">특성</span><span class="sxs-lookup"><span data-stu-id="474be-111">Attributes</span></span>  
  
|<span data-ttu-id="474be-112">특성</span><span class="sxs-lookup"><span data-stu-id="474be-112">Attribute</span></span>|<span data-ttu-id="474be-113">설명</span><span class="sxs-lookup"><span data-stu-id="474be-113">Description</span></span>|  
|---------------|-----------------|  
|`type`|<span data-ttu-id="474be-114">이 구성 요소의 형식을 지정하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="474be-114">A string that specifies the type of this configuration element.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="474be-115">자식 요소</span><span class="sxs-lookup"><span data-stu-id="474be-115">Child Elements</span></span>  
  
|<span data-ttu-id="474be-116">요소</span><span class="sxs-lookup"><span data-stu-id="474be-116">Element</span></span>|<span data-ttu-id="474be-117">설명</span><span class="sxs-lookup"><span data-stu-id="474be-117">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="474be-118">\<clientCertificate></span><span class="sxs-lookup"><span data-stu-id="474be-118">\<clientCertificate></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/clientcertificate-of-servicecredentials.md)|<span data-ttu-id="474be-119">클라이언트 인증서가 out-of-band 방식으로 제공될 때 사용할 인증서를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="474be-119">Specifies the certificate to be used when the client certificate is available out-of-band.</span></span> <span data-ttu-id="474be-120">이 요소는 클라이언트 인증서 유효성 검사 설정도 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="474be-120">This element also specifies client certificate validation settings.</span></span> <span data-ttu-id="474be-121">이 요소는 <xref:System.ServiceModel.Configuration.X509InitiatorCertificateServiceElement> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="474be-121">This element is of type <xref:System.ServiceModel.Configuration.X509InitiatorCertificateServiceElement>.</span></span>|  
|[<span data-ttu-id="474be-122">\<issuedTokenAuthentication></span><span class="sxs-lookup"><span data-stu-id="474be-122">\<issuedTokenAuthentication></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/issuedtokenauthentication-of-servicecredentials.md)|<span data-ttu-id="474be-123">이 서비스에 대해 현재 발급된 토큰을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="474be-123">Specifies the current issued token for this service.</span></span> <span data-ttu-id="474be-124">이 요소는 <xref:System.ServiceModel.Configuration.IssuedTokenServiceElement> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="474be-124">This element is of type <xref:System.ServiceModel.Configuration.IssuedTokenServiceElement>.</span></span>|  
|[<span data-ttu-id="474be-125">\<peer></span><span class="sxs-lookup"><span data-stu-id="474be-125">\<peer></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/peer-of-servicecredentials.md)|<span data-ttu-id="474be-126">피어 노드에 대한 현재 자격 증명을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="474be-126">Specifies the current credentials for a peer node.</span></span> <span data-ttu-id="474be-127">이 요소는 <xref:System.ServiceModel.Configuration.PeerCredentialElement> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="474be-127">This element is of type <xref:System.ServiceModel.Configuration.PeerCredentialElement>.</span></span>|  
|[<span data-ttu-id="474be-128">\<secureConversationAuthentication></span><span class="sxs-lookup"><span data-stu-id="474be-128">\<secureConversationAuthentication></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/secureconversationauthentication-of-servicecredential.md)|<span data-ttu-id="474be-129">보안 대화에 대한 현재 자격 증명을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="474be-129">Specifies the current credentials for a secure conversation.</span></span> <span data-ttu-id="474be-130">이 요소는 <xref:System.ServiceModel.Configuration.SecureConversationServiceElement> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="474be-130">This element is of type <xref:System.ServiceModel.Configuration.SecureConversationServiceElement>.</span></span>|  
|[<span data-ttu-id="474be-131">\<serviceCertificate></span><span class="sxs-lookup"><span data-stu-id="474be-131">\<serviceCertificate></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/servicecertificate-of-servicecredentials.md)|<span data-ttu-id="474be-132">자체 식별을 위해 서비스에서 사용되는 인증서를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="474be-132">Specifies a certificate used by a service to identify itself.</span></span> <span data-ttu-id="474be-133">이 요소는 <xref:System.ServiceModel.Configuration.X509RecipientCertificateServiceElement> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="474be-133">This element is of type <xref:System.ServiceModel.Configuration.X509RecipientCertificateServiceElement>.</span></span>|  
|[<span data-ttu-id="474be-134">\<userNameAuthentication></span><span class="sxs-lookup"><span data-stu-id="474be-134">\<userNameAuthentication></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/usernameauthentication.md)|<span data-ttu-id="474be-135">사용자 이름 암호 유효성 검사의 설정을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="474be-135">Specifies the settings for username password validation.</span></span> <span data-ttu-id="474be-136">이 요소는 <xref:System.ServiceModel.Configuration.UserNameServiceElement> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="474be-136">This element is of type <xref:System.ServiceModel.Configuration.UserNameServiceElement>.</span></span>|  
|[<span data-ttu-id="474be-137">\<windowsAuthentication></span><span class="sxs-lookup"><span data-stu-id="474be-137">\<windowsAuthentication></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/windowsauthentication-of-servicecredentials.md)|<span data-ttu-id="474be-138">Windows 자격 증명 유효성 검사의 설정을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="474be-138">Specifies the settings for Windows credential validation.</span></span> <span data-ttu-id="474be-139">이 요소는 <xref:System.ServiceModel.Configuration.WindowsServiceElement> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="474be-139">This element is of type <xref:System.ServiceModel.Configuration.WindowsServiceElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="474be-140">부모 요소</span><span class="sxs-lookup"><span data-stu-id="474be-140">Parent Elements</span></span>  
  
|<span data-ttu-id="474be-141">요소</span><span class="sxs-lookup"><span data-stu-id="474be-141">Element</span></span>|<span data-ttu-id="474be-142">설명</span><span class="sxs-lookup"><span data-stu-id="474be-142">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="474be-143">\<behavior></span><span class="sxs-lookup"><span data-stu-id="474be-143">\<behavior></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|<span data-ttu-id="474be-144">동작 요소를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="474be-144">Specifies a behavior element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="474be-145">참고자료</span><span class="sxs-lookup"><span data-stu-id="474be-145">See also</span></span>

- <xref:System.ServiceModel.Configuration.ServiceCredentialsElement>
- <xref:System.ServiceModel.Description.ServiceCredentials>
- [<span data-ttu-id="474be-146">보안 동작</span><span class="sxs-lookup"><span data-stu-id="474be-146">Security Behaviors</span></span>](../../../../../docs/framework/wcf/feature-details/security-behaviors-in-wcf.md)
