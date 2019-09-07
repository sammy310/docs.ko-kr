---
title: <clientCredentials>
ms.date: 03/30/2017
ms.assetid: 1e6eef0d-a34e-4d74-b0f7-f65d2181858d
ms.openlocfilehash: f295fe48e194611c80b78c0c23ab3e66ea1c0b64
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/06/2019
ms.locfileid: "70400504"
---
# <a name="clientcredentials"></a><span data-ttu-id="574e3-101">\<clientCredentials></span><span class="sxs-lookup"><span data-stu-id="574e3-101">\<clientCredentials></span></span>
<span data-ttu-id="574e3-102">클라이언트를 서비스에 인증하는 데 사용되는 자격 증명을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="574e3-102">Specifies the credentials used to authenticate the client to a service.</span></span>  
  
<span data-ttu-id="574e3-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="574e3-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="574e3-104">&nbsp;&nbsp;[ **\<System.servicemodel >** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="574e3-104">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="574e3-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<동작 >** ](behaviors.md)</span><span class="sxs-lookup"><span data-stu-id="574e3-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)</span></span>\
<span data-ttu-id="574e3-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<endpointBehaviors >** ](endpointbehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="574e3-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpointBehaviors>**](endpointbehaviors.md)</span></span>\
<span data-ttu-id="574e3-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<동작 >** ](behavior-of-endpointbehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="574e3-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-endpointbehaviors.md)</span></span>\
<span data-ttu-id="574e3-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<clientCredentials >**</span><span class="sxs-lookup"><span data-stu-id="574e3-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<clientCredentials>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="574e3-109">구문</span><span class="sxs-lookup"><span data-stu-id="574e3-109">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="574e3-110">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="574e3-110">Attributes and Elements</span></span>  
 <span data-ttu-id="574e3-111">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="574e3-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="574e3-112">특성</span><span class="sxs-lookup"><span data-stu-id="574e3-112">Attributes</span></span>  
  
|<span data-ttu-id="574e3-113">특성</span><span class="sxs-lookup"><span data-stu-id="574e3-113">Attribute</span></span>|<span data-ttu-id="574e3-114">Description</span><span class="sxs-lookup"><span data-stu-id="574e3-114">Description</span></span>|  
|---------------|-----------------|  
|`supportInteractive`|<span data-ttu-id="574e3-115">런타임에 클라이언트 자격 증명을 선택할 때 대화형 사용자가 포함될 수 있는지 여부를 지정하는 부울 값입니다.</span><span class="sxs-lookup"><span data-stu-id="574e3-115">A Boolean value that specifies whether an interactive user can be involved in selecting a client credential at runtime.</span></span> <span data-ttu-id="574e3-116">기본값은 `true`입니다.</span><span class="sxs-lookup"><span data-stu-id="574e3-116">The default value is `true`.</span></span>|  
|`type`|<span data-ttu-id="574e3-117">이 구성 요소의 형식을 지정하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="574e3-117">A string that specifies the type of this configuration element.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="574e3-118">자식 요소</span><span class="sxs-lookup"><span data-stu-id="574e3-118">Child Elements</span></span>  
  
|<span data-ttu-id="574e3-119">요소</span><span class="sxs-lookup"><span data-stu-id="574e3-119">Element</span></span>|<span data-ttu-id="574e3-120">설명</span><span class="sxs-lookup"><span data-stu-id="574e3-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="574e3-121">\<clientCertificate></span><span class="sxs-lookup"><span data-stu-id="574e3-121">\<clientCertificate></span></span>](clientcertificate-of-clientcredentials-element.md)|<span data-ttu-id="574e3-122">클라이언트를 서비스에 인증하는 데 사용되는 인증서를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="574e3-122">Specifies the certificate used to authenticate the client to the service.</span></span> <span data-ttu-id="574e3-123">이 요소는 <xref:System.ServiceModel.Configuration.X509InitiatorCertificateClientElement> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="574e3-123">This element is of type <xref:System.ServiceModel.Configuration.X509InitiatorCertificateClientElement>.</span></span>|  
|[<span data-ttu-id="574e3-124">\<httpDigest></span><span class="sxs-lookup"><span data-stu-id="574e3-124">\<httpDigest></span></span>](httpdigest-element.md)|<span data-ttu-id="574e3-125">클라이언트를 서비스에 인증하는 데 사용되는 다이제스트를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="574e3-125">Specifies a digest used to authenticate the client to the service.</span></span> <span data-ttu-id="574e3-126">이 요소는 <xref:System.ServiceModel.Configuration.HttpDigestClientElement> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="574e3-126">This element is of type <xref:System.ServiceModel.Configuration.HttpDigestClientElement>.</span></span>|  
|[<span data-ttu-id="574e3-127">\<issuedToken></span><span class="sxs-lookup"><span data-stu-id="574e3-127">\<issuedToken></span></span>](issuedtoken.md)|<span data-ttu-id="574e3-128">클라이언트를 STS(보안 토큰 서비스)에 인증하는 데 사용되는 사용자 지정 토큰 형식을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="574e3-128">Specifies a custom token type used to authenticate the client to a Secure Token Service (STS).</span></span> <span data-ttu-id="574e3-129">이 요소는 <xref:System.ServiceModel.Configuration.IssuedTokenClientElement> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="574e3-129">This element is of type <xref:System.ServiceModel.Configuration.IssuedTokenClientElement>.</span></span>|  
|[<span data-ttu-id="574e3-130">\<peer></span><span class="sxs-lookup"><span data-stu-id="574e3-130">\<peer></span></span>](peer-of-clientcredentials-element.md)|<span data-ttu-id="574e3-131">현재 피어 자격 증명을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="574e3-131">Specifies a current peer credential.</span></span> <span data-ttu-id="574e3-132">이 요소는 <xref:System.ServiceModel.Configuration.PeerCredentialElement> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="574e3-132">This element is of type <xref:System.ServiceModel.Configuration.PeerCredentialElement>.</span></span>|  
|[<span data-ttu-id="574e3-133">\<serviceCertificate></span><span class="sxs-lookup"><span data-stu-id="574e3-133">\<serviceCertificate></span></span>](servicecertificate-of-clientcredentials-element.md)|<span data-ttu-id="574e3-134">서비스를 클라이언트에 인증하는 데 사용되는 인증서를 지정하고 인증서 옵션을 설정하기 위한 구조를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="574e3-134">Specifies the certificate used to authenticate the service to the client and provides a structure for setting certificate options.</span></span> <span data-ttu-id="574e3-135">이 인증서는 서비스로부터 클라이언트에게 out-of-band로 제공되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="574e3-135">This certificate must be supplied out-of-band from the service to the client.</span></span> <span data-ttu-id="574e3-136">이 요소는 <xref:System.ServiceModel.Configuration.X509RecipientCertificateClientElement> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="574e3-136">This element is of type <xref:System.ServiceModel.Configuration.X509RecipientCertificateClientElement>.</span></span>|  
|[<span data-ttu-id="574e3-137">\<windows></span><span class="sxs-lookup"><span data-stu-id="574e3-137">\<windows></span></span>](windows-of-clientcredentials-element.md)|<span data-ttu-id="574e3-138">Windows 자격 증명을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="574e3-138">Specifies a Windows credential.</span></span> <span data-ttu-id="574e3-139">기본값은 현재 스레드의 자격 증명입니다.</span><span class="sxs-lookup"><span data-stu-id="574e3-139">The default is the credential of the current thread.</span></span> <span data-ttu-id="574e3-140">이 요소는 <xref:System.ServiceModel.Configuration.WindowsClientElement> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="574e3-140">This element is of type <xref:System.ServiceModel.Configuration.WindowsClientElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="574e3-141">부모 요소</span><span class="sxs-lookup"><span data-stu-id="574e3-141">Parent Elements</span></span>  
  
|<span data-ttu-id="574e3-142">요소</span><span class="sxs-lookup"><span data-stu-id="574e3-142">Element</span></span>|<span data-ttu-id="574e3-143">설명</span><span class="sxs-lookup"><span data-stu-id="574e3-143">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="574e3-144">\<behavior></span><span class="sxs-lookup"><span data-stu-id="574e3-144">\<behavior></span></span>](behavior-of-endpointbehaviors.md)|<span data-ttu-id="574e3-145">엔드포인트 동작을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="574e3-145">Specifies an endpoint behavior.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="574e3-146">설명</span><span class="sxs-lookup"><span data-stu-id="574e3-146">Remarks</span></span>  
 <span data-ttu-id="574e3-147">클라이언트 자격 증명은 상호 인증이 필요한 경우 서비스에 대해 클라이언트를 인증하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="574e3-147">Client credentials are used to authenticate the client to services in cases where mutual authentication is required.</span></span> <span data-ttu-id="574e3-148">또한 이 구성 섹션은 클라이언트가 서비스 인증서를 사용하여 서비스에 대한 메시지 보안을 유지해야 하는 경우 서비스 인증서를 지정하는 데 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="574e3-148">This configuration section can also be used to specify service certificates for scenarios where the client must secure messages to a service with the service's certificate.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="574e3-149">참고자료</span><span class="sxs-lookup"><span data-stu-id="574e3-149">See also</span></span>

- <xref:System.ServiceModel.Configuration.ClientCredentialsElement>
- <xref:System.ServiceModel.Description.ClientCredentials>
- [<span data-ttu-id="574e3-150">보안 동작</span><span class="sxs-lookup"><span data-stu-id="574e3-150">Security Behaviors</span></span>](../../../wcf/feature-details/security-behaviors-in-wcf.md)
- [<span data-ttu-id="574e3-151">클라이언트에 보안 설정</span><span class="sxs-lookup"><span data-stu-id="574e3-151">Securing Clients</span></span>](../../../wcf/securing-clients.md)
