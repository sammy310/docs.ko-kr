---
title: <clientCredentials>
ms.date: 03/30/2017
ms.assetid: 1e6eef0d-a34e-4d74-b0f7-f65d2181858d
ms.openlocfilehash: c3e756f49b7054d6553eb6c3f1850f0fbce14943
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/22/2019
ms.locfileid: "69926124"
---
# <a name="clientcredentials"></a><span data-ttu-id="31611-101">\<clientCredentials></span><span class="sxs-lookup"><span data-stu-id="31611-101">\<clientCredentials></span></span>
<span data-ttu-id="31611-102">클라이언트를 서비스에 인증하는 데 사용되는 자격 증명을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="31611-102">Specifies the credentials used to authenticate the client to a service.</span></span>  
  
 <span data-ttu-id="31611-103">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="31611-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="31611-104">\<behaviors></span><span class="sxs-lookup"><span data-stu-id="31611-104">\<behaviors></span></span>  
<span data-ttu-id="31611-105">\<endpointBehaviors></span><span class="sxs-lookup"><span data-stu-id="31611-105">\<endpointBehaviors></span></span>  
<span data-ttu-id="31611-106">\<behavior></span><span class="sxs-lookup"><span data-stu-id="31611-106">\<behavior></span></span>  
<span data-ttu-id="31611-107">\<clientCredentials></span><span class="sxs-lookup"><span data-stu-id="31611-107">\<clientCredentials></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="31611-108">구문</span><span class="sxs-lookup"><span data-stu-id="31611-108">Syntax</span></span>  
  
```xml  
<clientCredentials type="String"
                   supportInteractive="Boolean" >
  <clientCertificate>
  </clientCertificate>
  <digest>
  </digest>
  <isuedToken>
  </isuedToken>
  <peer>
  </peer>
  <serviceCertificate>
  </serviceCertificate>
  <windowsAuthentication>
  </windowsAuthentication>
</clientCredentials>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="31611-109">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="31611-109">Attributes and Elements</span></span>  
 <span data-ttu-id="31611-110">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="31611-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="31611-111">특성</span><span class="sxs-lookup"><span data-stu-id="31611-111">Attributes</span></span>  
  
|<span data-ttu-id="31611-112">특성</span><span class="sxs-lookup"><span data-stu-id="31611-112">Attribute</span></span>|<span data-ttu-id="31611-113">Description</span><span class="sxs-lookup"><span data-stu-id="31611-113">Description</span></span>|  
|---------------|-----------------|  
|`supportInteractive`|<span data-ttu-id="31611-114">런타임에 클라이언트 자격 증명을 선택할 때 대화형 사용자가 포함될 수 있는지 여부를 지정하는 부울 값입니다.</span><span class="sxs-lookup"><span data-stu-id="31611-114">A Boolean value that specifies whether an interactive user can be involved in selecting a client credential at runtime.</span></span> <span data-ttu-id="31611-115">기본값은 `true`입니다.</span><span class="sxs-lookup"><span data-stu-id="31611-115">The default value is `true`.</span></span>|  
|`type`|<span data-ttu-id="31611-116">이 구성 요소의 형식을 지정하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="31611-116">A string that specifies the type of this configuration element.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="31611-117">자식 요소</span><span class="sxs-lookup"><span data-stu-id="31611-117">Child Elements</span></span>  
  
|<span data-ttu-id="31611-118">요소</span><span class="sxs-lookup"><span data-stu-id="31611-118">Element</span></span>|<span data-ttu-id="31611-119">설명</span><span class="sxs-lookup"><span data-stu-id="31611-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="31611-120">\<clientCertificate></span><span class="sxs-lookup"><span data-stu-id="31611-120">\<clientCertificate></span></span>](clientcertificate-of-clientcredentials-element.md)|<span data-ttu-id="31611-121">클라이언트를 서비스에 인증하는 데 사용되는 인증서를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="31611-121">Specifies the certificate used to authenticate the client to the service.</span></span> <span data-ttu-id="31611-122">이 요소는 <xref:System.ServiceModel.Configuration.X509InitiatorCertificateClientElement> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="31611-122">This element is of type <xref:System.ServiceModel.Configuration.X509InitiatorCertificateClientElement>.</span></span>|  
|[<span data-ttu-id="31611-123">\<httpDigest></span><span class="sxs-lookup"><span data-stu-id="31611-123">\<httpDigest></span></span>](httpdigest-element.md)|<span data-ttu-id="31611-124">클라이언트를 서비스에 인증하는 데 사용되는 다이제스트를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="31611-124">Specifies a digest used to authenticate the client to the service.</span></span> <span data-ttu-id="31611-125">이 요소는 <xref:System.ServiceModel.Configuration.HttpDigestClientElement> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="31611-125">This element is of type <xref:System.ServiceModel.Configuration.HttpDigestClientElement>.</span></span>|  
|[<span data-ttu-id="31611-126">\<issuedToken></span><span class="sxs-lookup"><span data-stu-id="31611-126">\<issuedToken></span></span>](issuedtoken.md)|<span data-ttu-id="31611-127">클라이언트를 STS(보안 토큰 서비스)에 인증하는 데 사용되는 사용자 지정 토큰 형식을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="31611-127">Specifies a custom token type used to authenticate the client to a Secure Token Service (STS).</span></span> <span data-ttu-id="31611-128">이 요소는 <xref:System.ServiceModel.Configuration.IssuedTokenClientElement> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="31611-128">This element is of type <xref:System.ServiceModel.Configuration.IssuedTokenClientElement>.</span></span>|  
|[<span data-ttu-id="31611-129">\<peer></span><span class="sxs-lookup"><span data-stu-id="31611-129">\<peer></span></span>](peer-of-clientcredentials-element.md)|<span data-ttu-id="31611-130">현재 피어 자격 증명을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="31611-130">Specifies a current peer credential.</span></span> <span data-ttu-id="31611-131">이 요소는 <xref:System.ServiceModel.Configuration.PeerCredentialElement> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="31611-131">This element is of type <xref:System.ServiceModel.Configuration.PeerCredentialElement>.</span></span>|  
|[<span data-ttu-id="31611-132">\<serviceCertificate></span><span class="sxs-lookup"><span data-stu-id="31611-132">\<serviceCertificate></span></span>](servicecertificate-of-clientcredentials-element.md)|<span data-ttu-id="31611-133">서비스를 클라이언트에 인증하는 데 사용되는 인증서를 지정하고 인증서 옵션을 설정하기 위한 구조를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="31611-133">Specifies the certificate used to authenticate the service to the client and provides a structure for setting certificate options.</span></span> <span data-ttu-id="31611-134">이 인증서는 서비스로부터 클라이언트에게 out-of-band로 제공되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="31611-134">This certificate must be supplied out-of-band from the service to the client.</span></span> <span data-ttu-id="31611-135">이 요소는 <xref:System.ServiceModel.Configuration.X509RecipientCertificateClientElement> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="31611-135">This element is of type <xref:System.ServiceModel.Configuration.X509RecipientCertificateClientElement>.</span></span>|  
|[<span data-ttu-id="31611-136">\<windows></span><span class="sxs-lookup"><span data-stu-id="31611-136">\<windows></span></span>](windows-of-clientcredentials-element.md)|<span data-ttu-id="31611-137">Windows 자격 증명을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="31611-137">Specifies a Windows credential.</span></span> <span data-ttu-id="31611-138">기본값은 현재 스레드의 자격 증명입니다.</span><span class="sxs-lookup"><span data-stu-id="31611-138">The default is the credential of the current thread.</span></span> <span data-ttu-id="31611-139">이 요소는 <xref:System.ServiceModel.Configuration.WindowsClientElement> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="31611-139">This element is of type <xref:System.ServiceModel.Configuration.WindowsClientElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="31611-140">부모 요소</span><span class="sxs-lookup"><span data-stu-id="31611-140">Parent Elements</span></span>  
  
|<span data-ttu-id="31611-141">요소</span><span class="sxs-lookup"><span data-stu-id="31611-141">Element</span></span>|<span data-ttu-id="31611-142">설명</span><span class="sxs-lookup"><span data-stu-id="31611-142">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="31611-143">\<behavior></span><span class="sxs-lookup"><span data-stu-id="31611-143">\<behavior></span></span>](behavior-of-endpointbehaviors.md)|<span data-ttu-id="31611-144">엔드포인트 동작을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="31611-144">Specifies an endpoint behavior.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="31611-145">설명</span><span class="sxs-lookup"><span data-stu-id="31611-145">Remarks</span></span>  
 <span data-ttu-id="31611-146">클라이언트 자격 증명은 상호 인증이 필요한 경우 서비스에 대해 클라이언트를 인증하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="31611-146">Client credentials are used to authenticate the client to services in cases where mutual authentication is required.</span></span> <span data-ttu-id="31611-147">또한 이 구성 섹션은 클라이언트가 서비스 인증서를 사용하여 서비스에 대한 메시지 보안을 유지해야 하는 경우 서비스 인증서를 지정하는 데 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="31611-147">This configuration section can also be used to specify service certificates for scenarios where the client must secure messages to a service with the service's certificate.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="31611-148">참고자료</span><span class="sxs-lookup"><span data-stu-id="31611-148">See also</span></span>

- <xref:System.ServiceModel.Configuration.ClientCredentialsElement>
- <xref:System.ServiceModel.Description.ClientCredentials>
- [<span data-ttu-id="31611-149">보안 동작</span><span class="sxs-lookup"><span data-stu-id="31611-149">Security Behaviors</span></span>](../../../wcf/feature-details/security-behaviors-in-wcf.md)
- [<span data-ttu-id="31611-150">클라이언트에 보안 설정</span><span class="sxs-lookup"><span data-stu-id="31611-150">Securing Clients</span></span>](../../../wcf/securing-clients.md)
