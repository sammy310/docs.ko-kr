---
description: 다음에 대해 자세히 알아보세요. <clientCredentials>
title: <clientCredentials>
ms.date: 03/30/2017
ms.assetid: 1e6eef0d-a34e-4d74-b0f7-f65d2181858d
ms.openlocfilehash: b10e046f8e4994e367db69d5863e54a0bfa07db5
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99638810"
---
# \<clientCredentials>

<span data-ttu-id="1b1d0-102">클라이언트를 서비스에 인증하는 데 사용되는 자격 증명을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="1b1d0-102">Specifies the credentials used to authenticate the client to a service.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpointBehaviors>**](endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<clientCredentials>**  
  
## <a name="syntax"></a><span data-ttu-id="1b1d0-103">구문</span><span class="sxs-lookup"><span data-stu-id="1b1d0-103">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="1b1d0-104">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="1b1d0-104">Attributes and Elements</span></span>  

 <span data-ttu-id="1b1d0-105">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="1b1d0-105">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="1b1d0-106">특성</span><span class="sxs-lookup"><span data-stu-id="1b1d0-106">Attributes</span></span>  
  
|<span data-ttu-id="1b1d0-107">attribute</span><span class="sxs-lookup"><span data-stu-id="1b1d0-107">Attribute</span></span>|<span data-ttu-id="1b1d0-108">설명</span><span class="sxs-lookup"><span data-stu-id="1b1d0-108">Description</span></span>|  
|---------------|-----------------|  
|`supportInteractive`|<span data-ttu-id="1b1d0-109">런타임에 클라이언트 자격 증명을 선택할 때 대화형 사용자가 포함될 수 있는지 여부를 지정하는 부울 값입니다.</span><span class="sxs-lookup"><span data-stu-id="1b1d0-109">A Boolean value that specifies whether an interactive user can be involved in selecting a client credential at runtime.</span></span> <span data-ttu-id="1b1d0-110">기본값은 `true`입니다.</span><span class="sxs-lookup"><span data-stu-id="1b1d0-110">The default value is `true`.</span></span>|  
|`type`|<span data-ttu-id="1b1d0-111">이 구성 요소의 형식을 지정하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="1b1d0-111">A string that specifies the type of this configuration element.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="1b1d0-112">자식 요소</span><span class="sxs-lookup"><span data-stu-id="1b1d0-112">Child Elements</span></span>  
  
|<span data-ttu-id="1b1d0-113">요소</span><span class="sxs-lookup"><span data-stu-id="1b1d0-113">Element</span></span>|<span data-ttu-id="1b1d0-114">설명</span><span class="sxs-lookup"><span data-stu-id="1b1d0-114">Description</span></span>|  
|-------------|-----------------|  
|[\<clientCertificate>](clientcertificate-of-clientcredentials-element.md)|<span data-ttu-id="1b1d0-115">클라이언트를 서비스에 인증하는 데 사용되는 인증서를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="1b1d0-115">Specifies the certificate used to authenticate the client to the service.</span></span> <span data-ttu-id="1b1d0-116">이 요소는 <xref:System.ServiceModel.Configuration.X509InitiatorCertificateClientElement> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="1b1d0-116">This element is of type <xref:System.ServiceModel.Configuration.X509InitiatorCertificateClientElement>.</span></span>|  
|[\<httpDigest>](httpdigest-element.md)|<span data-ttu-id="1b1d0-117">클라이언트를 서비스에 인증하는 데 사용되는 다이제스트를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="1b1d0-117">Specifies a digest used to authenticate the client to the service.</span></span> <span data-ttu-id="1b1d0-118">이 요소는 <xref:System.ServiceModel.Configuration.HttpDigestClientElement> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="1b1d0-118">This element is of type <xref:System.ServiceModel.Configuration.HttpDigestClientElement>.</span></span>|  
|[\<issuedToken>](issuedtoken.md)|<span data-ttu-id="1b1d0-119">클라이언트를 STS(보안 토큰 서비스)에 인증하는 데 사용되는 사용자 지정 토큰 형식을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="1b1d0-119">Specifies a custom token type used to authenticate the client to a Secure Token Service (STS).</span></span> <span data-ttu-id="1b1d0-120">이 요소는 <xref:System.ServiceModel.Configuration.IssuedTokenClientElement> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="1b1d0-120">This element is of type <xref:System.ServiceModel.Configuration.IssuedTokenClientElement>.</span></span>|  
|[\<peer>](peer-of-clientcredentials-element.md)|<span data-ttu-id="1b1d0-121">현재 피어 자격 증명을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="1b1d0-121">Specifies a current peer credential.</span></span> <span data-ttu-id="1b1d0-122">이 요소는 <xref:System.ServiceModel.Configuration.PeerCredentialElement> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="1b1d0-122">This element is of type <xref:System.ServiceModel.Configuration.PeerCredentialElement>.</span></span>|  
|[\<serviceCertificate>](servicecertificate-of-clientcredentials-element.md)|<span data-ttu-id="1b1d0-123">서비스를 클라이언트에 인증하는 데 사용되는 인증서를 지정하고 인증서 옵션을 설정하기 위한 구조를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="1b1d0-123">Specifies the certificate used to authenticate the service to the client and provides a structure for setting certificate options.</span></span> <span data-ttu-id="1b1d0-124">이 인증서는 서비스로부터 클라이언트에게 out-of-band로 제공되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1b1d0-124">This certificate must be supplied out-of-band from the service to the client.</span></span> <span data-ttu-id="1b1d0-125">이 요소는 <xref:System.ServiceModel.Configuration.X509RecipientCertificateClientElement> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="1b1d0-125">This element is of type <xref:System.ServiceModel.Configuration.X509RecipientCertificateClientElement>.</span></span>|  
|[\<windows>](windows-of-clientcredentials-element.md)|<span data-ttu-id="1b1d0-126">Windows 자격 증명을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="1b1d0-126">Specifies a Windows credential.</span></span> <span data-ttu-id="1b1d0-127">기본값은 현재 스레드의 자격 증명입니다.</span><span class="sxs-lookup"><span data-stu-id="1b1d0-127">The default is the credential of the current thread.</span></span> <span data-ttu-id="1b1d0-128">이 요소는 <xref:System.ServiceModel.Configuration.WindowsClientElement> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="1b1d0-128">This element is of type <xref:System.ServiceModel.Configuration.WindowsClientElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="1b1d0-129">부모 요소</span><span class="sxs-lookup"><span data-stu-id="1b1d0-129">Parent Elements</span></span>  
  
|<span data-ttu-id="1b1d0-130">요소</span><span class="sxs-lookup"><span data-stu-id="1b1d0-130">Element</span></span>|<span data-ttu-id="1b1d0-131">설명</span><span class="sxs-lookup"><span data-stu-id="1b1d0-131">Description</span></span>|  
|-------------|-----------------|  
|[\<behavior>](behavior-of-endpointbehaviors.md)|<span data-ttu-id="1b1d0-132">엔드포인트 동작을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="1b1d0-132">Specifies an endpoint behavior.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1b1d0-133">설명</span><span class="sxs-lookup"><span data-stu-id="1b1d0-133">Remarks</span></span>  

 <span data-ttu-id="1b1d0-134">클라이언트 자격 증명은 상호 인증이 필요한 경우 서비스에 대해 클라이언트를 인증하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="1b1d0-134">Client credentials are used to authenticate the client to services in cases where mutual authentication is required.</span></span> <span data-ttu-id="1b1d0-135">또한 이 구성 섹션은 클라이언트가 서비스 인증서를 사용하여 서비스에 대한 메시지 보안을 유지해야 하는 경우 서비스 인증서를 지정하는 데 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1b1d0-135">This configuration section can also be used to specify service certificates for scenarios where the client must secure messages to a service with the service's certificate.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1b1d0-136">참고 항목</span><span class="sxs-lookup"><span data-stu-id="1b1d0-136">See also</span></span>

- <xref:System.ServiceModel.Configuration.ClientCredentialsElement>
- <xref:System.ServiceModel.Description.ClientCredentials>
- [<span data-ttu-id="1b1d0-137">보안 동작</span><span class="sxs-lookup"><span data-stu-id="1b1d0-137">Security Behaviors</span></span>](../../../wcf/feature-details/security-behaviors-in-wcf.md)
- [<span data-ttu-id="1b1d0-138">클라이언트에 보안 설정</span><span class="sxs-lookup"><span data-stu-id="1b1d0-138">Securing Clients</span></span>](../../../wcf/securing-clients.md)
