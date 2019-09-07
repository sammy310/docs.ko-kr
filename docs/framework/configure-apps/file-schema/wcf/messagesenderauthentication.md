---
title: <messageSenderAuthentication>
ms.date: 03/30/2017
ms.assetid: ea62fc06-55fb-42e0-aa2b-8867bdf4b415
ms.openlocfilehash: c6183a8d27d56c7199b815ccb31b06f983a51b33
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/06/2019
ms.locfileid: "70398397"
---
# <a name="messagesenderauthentication"></a><span data-ttu-id="1b19c-101">\<messageSenderAuthentication></span><span class="sxs-lookup"><span data-stu-id="1b19c-101">\<messageSenderAuthentication></span></span>
<span data-ttu-id="1b19c-102">메시지 발신자가 사용하는 피어 인증서에 대한 인증 설정을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="1b19c-102">Specifies authentication settings for peer certificate used by a message sender.</span></span>  
  
<span data-ttu-id="1b19c-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="1b19c-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="1b19c-104">&nbsp;&nbsp;[ **\<System.servicemodel >** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="1b19c-104">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="1b19c-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<동작 >** ](behaviors.md)</span><span class="sxs-lookup"><span data-stu-id="1b19c-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)</span></span>\
<span data-ttu-id="1b19c-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<serviceBehaviors >** ](servicebehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="1b19c-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors.md)</span></span>\
<span data-ttu-id="1b19c-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<동작 >** ](behavior-of-servicebehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="1b19c-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-servicebehaviors.md)</span></span>\
<span data-ttu-id="1b19c-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<serviceCredentials >** ](servicecredentials.md)</span><span class="sxs-lookup"><span data-stu-id="1b19c-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceCredentials>**](servicecredentials.md)</span></span>\
<span data-ttu-id="1b19c-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<피어 >** ](peer-of-servicecredentials.md)</span><span class="sxs-lookup"><span data-stu-id="1b19c-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<peer>**](peer-of-servicecredentials.md)</span></span>\
<span data-ttu-id="1b19c-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<h >**</span><span class="sxs-lookup"><span data-stu-id="1b19c-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<messageSenderAuthentication>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1b19c-111">구문</span><span class="sxs-lookup"><span data-stu-id="1b19c-111">Syntax</span></span>  
  
```xml  
<messageSenderAuthentication customCertificateValidatorType="namespace.typeName, [,AssemblyName] [,Version=version number] [,Culture=culture] [,PublicKeyToken=token]"
                             certificateValidationMode="ChainTrust/None/PeerTrust/PeerOrChainTrust/Custom"
                             revocationMode="NoCheck/Online/Offline"
                             trustedStoreLocation="CurrentUser/LocalMachine" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="1b19c-112">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="1b19c-112">Attributes and Elements</span></span>  
 <span data-ttu-id="1b19c-113">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="1b19c-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="1b19c-114">특성</span><span class="sxs-lookup"><span data-stu-id="1b19c-114">Attributes</span></span>  
  
|<span data-ttu-id="1b19c-115">특성</span><span class="sxs-lookup"><span data-stu-id="1b19c-115">Attribute</span></span>|<span data-ttu-id="1b19c-116">Description</span><span class="sxs-lookup"><span data-stu-id="1b19c-116">Description</span></span>|  
|---------------|-----------------|  
|`certificateValidationMode`|<span data-ttu-id="1b19c-117">선택적 열거형입니다.</span><span class="sxs-lookup"><span data-stu-id="1b19c-117">Optional enumeration.</span></span> <span data-ttu-id="1b19c-118">자격 증명의 유효성을 검사하는 데 사용되는 5개 모드 중 하나를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="1b19c-118">Specifies one of five modes used to validate credentials.</span></span> <span data-ttu-id="1b19c-119">이 특성은 <xref:System.ServiceModel.Security.X509CertificateValidationMode> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="1b19c-119">This attribute is of type <xref:System.ServiceModel.Security.X509CertificateValidationMode>.</span></span> <span data-ttu-id="1b19c-120">`Custom`으로 설정되면 `customCertificateValidator`도 지정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1b19c-120">If set to `Custom`, then a `customCertificateValidator` must also be supplied.</span></span>|  
|`customCertificateValidatorType`|<span data-ttu-id="1b19c-121">선택적 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="1b19c-121">Optional string.</span></span> <span data-ttu-id="1b19c-122">사용자 지정 형식의 유효성을 검사하는 데 사용되는 형식 및 어셈블리를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="1b19c-122">Specifies a type and assembly used to validate a custom type.</span></span> <span data-ttu-id="1b19c-123">이 특성은 `certificateValidationMode`가 `Custom`으로 설정되어 있을 때 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1b19c-123">This attribute must be set when `certificateValidationMode` is set to `Custom`.</span></span> <span data-ttu-id="1b19c-124">이 특성은 <xref:System.IdentityModel.Selectors.X509CertificateValidator> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="1b19c-124">This attribute is of type <xref:System.IdentityModel.Selectors.X509CertificateValidator>.</span></span> <span data-ttu-id="1b19c-125">Windows Communication Foundation (WCF) 기본 피어 신뢰할 수 있는 사용자 저장소를 대상으로 피어 인증서를 확인 하는 인증서 유효성 검사기를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="1b19c-125">Windows Communication Foundation (WCF) provides a default peer certificate validator that verifies the peer certificate against the trusted people store.</span></span> <span data-ttu-id="1b19c-126">이 검사기는 또한 인증서가 유효한 루트에 연결되었는지도 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="1b19c-126">It also verifies that the certificate chains up to a valid root.</span></span> <span data-ttu-id="1b19c-127">사용자 지정 유효성 검사기를 사용하여 다른 동작을 지정하고, 이 특성을 사용하여 사용자 지정 유효성 검사기의 위치를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1b19c-127">You can implement a custom validator to specify a different behavior and use this attribute to point to the custom validator.</span></span>|  
|`revocationMode`|<span data-ttu-id="1b19c-128">선택적 열거형입니다.</span><span class="sxs-lookup"><span data-stu-id="1b19c-128">Optional enumeration.</span></span> <span data-ttu-id="1b19c-129">인증서 해지 모드를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="1b19c-129">Specifies the certificate revocation mode.</span></span> <span data-ttu-id="1b19c-130">이 특성은 <xref:System.Security.Cryptography.X509Certificates.X509RevocationMode> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="1b19c-130">This attribute is of type <xref:System.Security.Cryptography.X509Certificates.X509RevocationMode>.</span></span> <span data-ttu-id="1b19c-131">시스템에서는 해지된 인증서 목록에서 피어 인증서를 검색하여 해당 피어 인증서가 해지되지 않았는지를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="1b19c-131">The system verifies that the peer certificate has not been revoked by looking it up in the revoked certificate list.</span></span> <span data-ttu-id="1b19c-132">이러한 확인은 온라인으로 확인하거나 캐시된 해지 목록을 확인하여 이루어집니다.</span><span class="sxs-lookup"><span data-stu-id="1b19c-132">This check can be performed either by checking online or against a cached revocation list.</span></span> <span data-ttu-id="1b19c-133">이 특성을 NoCheck로 설정하면 해지 확인을 해제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1b19c-133">Revocation checking can be turned off by setting this attribute to NoCheck.</span></span>|  
|`trustedStoreLocation`|<span data-ttu-id="1b19c-134">선택적 열거형입니다.</span><span class="sxs-lookup"><span data-stu-id="1b19c-134">Optional enumeration.</span></span> <span data-ttu-id="1b19c-135">WCF 보안 시스템에서 피어 인증서의 유효성을 검사 하는 신뢰할 수 있는 저장소 위치를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="1b19c-135">Specifies the trusted store location where the peer certificate is validated by the WCF security system.</span></span> <span data-ttu-id="1b19c-136">이 특성은 <xref:System.Security.Cryptography.X509Certificates.StoreLocation> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="1b19c-136">This attribute is of type <xref:System.Security.Cryptography.X509Certificates.StoreLocation>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="1b19c-137">자식 요소</span><span class="sxs-lookup"><span data-stu-id="1b19c-137">Child Elements</span></span>  
 <span data-ttu-id="1b19c-138">없음</span><span class="sxs-lookup"><span data-stu-id="1b19c-138">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="1b19c-139">부모 요소</span><span class="sxs-lookup"><span data-stu-id="1b19c-139">Parent Elements</span></span>  
  
|<span data-ttu-id="1b19c-140">요소</span><span class="sxs-lookup"><span data-stu-id="1b19c-140">Element</span></span>|<span data-ttu-id="1b19c-141">설명</span><span class="sxs-lookup"><span data-stu-id="1b19c-141">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="1b19c-142">\<peer></span><span class="sxs-lookup"><span data-stu-id="1b19c-142">\<peer></span></span>](peer-of-servicecredentials.md)|<span data-ttu-id="1b19c-143">피어 노드에 대한 현재 자격 증명을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="1b19c-143">Specifies the current credentials for a peer node.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1b19c-144">설명</span><span class="sxs-lookup"><span data-stu-id="1b19c-144">Remarks</span></span>  
 <span data-ttu-id="1b19c-145">메시지 인증을 선택하면 이 요소를 구성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1b19c-145">This element must be configured if message authentication is chosen.</span></span> <span data-ttu-id="1b19c-146">출력 채널의 경우 각 메시지는 [ \<인증서 >](certificate-element.md)에서 제공 하는 인증서를 사용 하 여 서명 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1b19c-146">For output channels, each message is signed using the certificate provided by [\<certificate>](certificate-element.md).</span></span> <span data-ttu-id="1b19c-147">모든 메시지는 애플리케이션에 배달되기 전에 이 요소의 `customCertificateValidatorType` 특성에 지정된 유효성 검사기를 사용하여 메시지 자격 증명과 비교하여 검사됩니다.</span><span class="sxs-lookup"><span data-stu-id="1b19c-147">All messages, before delivered to the application, are checked against the message credential using the validator specified by the `customCertificateValidatorType` attribute of this element.</span></span> <span data-ttu-id="1b19c-148">유효성 검사기는 자격 증명을 수락하거나 거부할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1b19c-148">The validator can either accept or reject the credential.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1b19c-149">참고자료</span><span class="sxs-lookup"><span data-stu-id="1b19c-149">See also</span></span>

- <xref:System.ServiceModel.Configuration.X509PeerCertificateAuthenticationElement>
- <xref:System.ServiceModel.Security.X509PeerCertificateAuthentication>
- <xref:System.ServiceModel.Security.PeerCredential.MessageSenderAuthentication%2A>
- <xref:System.ServiceModel.Configuration.PeerCredentialElement.MessageSenderAuthentication%2A>
- [<span data-ttu-id="1b19c-150">인증서 작업</span><span class="sxs-lookup"><span data-stu-id="1b19c-150">Working with Certificates</span></span>](../../../wcf/feature-details/working-with-certificates.md)
- [<span data-ttu-id="1b19c-151">피어 투 피어 네트워킹</span><span class="sxs-lookup"><span data-stu-id="1b19c-151">Peer-to-Peer Networking</span></span>](../../../wcf/feature-details/peer-to-peer-networking.md)
- <span data-ttu-id="1b19c-152">[피어 채널 메시지 인증](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/aa967730(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="1b19c-152">[Peer Channel Message Authentication](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/aa967730(v=vs.90))</span></span>
- <span data-ttu-id="1b19c-153">[피어 채널 사용자 지정 인증](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms751447(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="1b19c-153">[Peer Channel Custom Authentication](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms751447(v=vs.90))</span></span>
- [<span data-ttu-id="1b19c-154">피어 채널 애플리케이션 보안</span><span class="sxs-lookup"><span data-stu-id="1b19c-154">Securing Peer Channel Applications</span></span>](../../../wcf/feature-details/securing-peer-channel-applications.md)
