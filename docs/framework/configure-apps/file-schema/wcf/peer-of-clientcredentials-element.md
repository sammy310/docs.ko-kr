---
title: <peer>of <clientCredentials> 요소
ms.date: 03/30/2017
ms.assetid: 505bd987-0042-4622-b68e-94f439729d53
ms.openlocfilehash: dce7ef64de1e3eb248e3553c97cbce8e9b205b4c
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/06/2019
ms.locfileid: "70400094"
---
# <a name="peer-of-clientcredentials-element"></a><span data-ttu-id="9dc91-102">\<\<clientCredentials > 요소의 피어 ></span><span class="sxs-lookup"><span data-stu-id="9dc91-102">\<peer> of \<clientCredentials> Element</span></span>
<span data-ttu-id="9dc91-103">피어 투 피어 클라이언트를 인증할 때 사용하는 자격 증명을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="9dc91-103">Specifies credentials used when authenticating peer-to-peer clients.</span></span>  
  
<span data-ttu-id="9dc91-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="9dc91-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="9dc91-105">&nbsp;&nbsp;[ **\<System.servicemodel >** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="9dc91-105">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="9dc91-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<동작 >** ](behaviors.md)</span><span class="sxs-lookup"><span data-stu-id="9dc91-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)</span></span>\
<span data-ttu-id="9dc91-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<endpointBehaviors >** ](endpointbehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="9dc91-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpointBehaviors>**](endpointbehaviors.md)</span></span>\
<span data-ttu-id="9dc91-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<동작 >** ](behavior-of-endpointbehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="9dc91-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-endpointbehaviors.md)</span></span>\
<span data-ttu-id="9dc91-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<clientCredentials >** ](clientcredentials.md)</span><span class="sxs-lookup"><span data-stu-id="9dc91-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<clientCredentials>**](clientcredentials.md)</span></span>\
<span data-ttu-id="9dc91-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<피어 >**</span><span class="sxs-lookup"><span data-stu-id="9dc91-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<peer>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9dc91-111">구문</span><span class="sxs-lookup"><span data-stu-id="9dc91-111">Syntax</span></span>  
  
```xml  
<peer>
  <certificate />
  <peerAuthentication />
  <messageSenderAuthentication />
</peer>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="9dc91-112">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="9dc91-112">Attributes and Elements</span></span>  
 <span data-ttu-id="9dc91-113">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="9dc91-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="9dc91-114">특성</span><span class="sxs-lookup"><span data-stu-id="9dc91-114">Attributes</span></span>  
 <span data-ttu-id="9dc91-115">없음</span><span class="sxs-lookup"><span data-stu-id="9dc91-115">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="9dc91-116">자식 요소</span><span class="sxs-lookup"><span data-stu-id="9dc91-116">Child Elements</span></span>  
  
|<span data-ttu-id="9dc91-117">요소</span><span class="sxs-lookup"><span data-stu-id="9dc91-117">Element</span></span>|<span data-ttu-id="9dc91-118">설명</span><span class="sxs-lookup"><span data-stu-id="9dc91-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="9dc91-119">\<certificate></span><span class="sxs-lookup"><span data-stu-id="9dc91-119">\<certificate></span></span>](certificate-element.md)|<span data-ttu-id="9dc91-120">피어 투 피어 클라이언트의 메시지를 서명 및 암호화하는 데 사용하는 X.509 인증서를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="9dc91-120">Specifies an X.509 certificate to use for signing and encrypting messages for peer-to-peer clients.</span></span> <span data-ttu-id="9dc91-121">을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="9dc91-121">.</span></span>|  
|[<span data-ttu-id="9dc91-122">\<peerAuthentication></span><span class="sxs-lookup"><span data-stu-id="9dc91-122">\<peerAuthentication></span></span>](peerauthentication-element.md)|<span data-ttu-id="9dc91-123">피어 클라이언트에 대한 인증 옵션을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="9dc91-123">Specifies authentication options for peer clients.</span></span>|  
|[<span data-ttu-id="9dc91-124">\<messageSenderAuthentication></span><span class="sxs-lookup"><span data-stu-id="9dc91-124">\<messageSenderAuthentication></span></span>](messagesenderauthentication-element.md)|<span data-ttu-id="9dc91-125">메시지 발신자에 대한 인증 옵션을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="9dc91-125">Specifies authentication options for message senders.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="9dc91-126">부모 요소</span><span class="sxs-lookup"><span data-stu-id="9dc91-126">Parent Elements</span></span>  
  
|<span data-ttu-id="9dc91-127">요소</span><span class="sxs-lookup"><span data-stu-id="9dc91-127">Element</span></span>|<span data-ttu-id="9dc91-128">Description</span><span class="sxs-lookup"><span data-stu-id="9dc91-128">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="9dc91-129">\<clientCredentials></span><span class="sxs-lookup"><span data-stu-id="9dc91-129">\<clientCredentials></span></span>](clientcredentials.md)|<span data-ttu-id="9dc91-130">클라이언트를 서비스에 인증할 때 사용되는 자격 증명을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="9dc91-130">Specifies the credentials used to authenticate a client to a service.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9dc91-131">설명</span><span class="sxs-lookup"><span data-stu-id="9dc91-131">Remarks</span></span>  
 <span data-ttu-id="9dc91-132">이 구성 요소는 피어 노드가 메시에서 다른 노드로부터 인증을 얻는 데 사용하는 자격 증명과 피어 노드가 다른 피어 노드를 인증하는 데 사용하는 인증 설정을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="9dc91-132">This configuration element specifies the credentials that a peer node uses to authenticate itself to other nodes in the mesh, as well as authentication settings that a peer node uses to authenticate other peer nodes.</span></span> <span data-ttu-id="9dc91-133">자세한 내용은 [피어 채널 메시지 인증](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/aa967730(v=vs.90)) 및 [피어 채널 응용 프로그램 보안](../../../wcf/feature-details/securing-peer-channel-applications.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="9dc91-133">For more information, see [Peer Channel Message Authentication](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/aa967730(v=vs.90)) and [Securing Peer Channel Applications](../../../wcf/feature-details/securing-peer-channel-applications.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9dc91-134">참고자료</span><span class="sxs-lookup"><span data-stu-id="9dc91-134">See also</span></span>

- <xref:System.ServiceModel.Configuration.ClientCredentialsElement>
- <xref:System.ServiceModel.Description.ClientCredentials>
- <xref:System.ServiceModel.Configuration.PeerCredentialElement>
- <xref:System.ServiceModel.Configuration.ClientCredentialsElement.Peer%2A>
- <xref:System.ServiceModel.Description.ClientCredentials>
- <xref:System.ServiceModel.Description.ClientCredentials.Peer%2A>
- <xref:System.ServiceModel.Security.PeerCredential>
- [<span data-ttu-id="9dc91-135">피어 투 피어 네트워킹</span><span class="sxs-lookup"><span data-stu-id="9dc91-135">Peer-to-Peer Networking</span></span>](../../../wcf/feature-details/peer-to-peer-networking.md)
- [<span data-ttu-id="9dc91-136">클라이언트에 보안 설정</span><span class="sxs-lookup"><span data-stu-id="9dc91-136">Securing Clients</span></span>](../../../wcf/securing-clients.md)
- <span data-ttu-id="9dc91-137">[피어 채널 메시지 인증](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/aa967730(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="9dc91-137">[Peer Channel Message Authentication](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/aa967730(v=vs.90))</span></span>
- <span data-ttu-id="9dc91-138">[피어 채널 사용자 지정 인증](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms751447(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="9dc91-138">[Peer Channel Custom Authentication](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms751447(v=vs.90))</span></span>
- [<span data-ttu-id="9dc91-139">피어 채널 애플리케이션 보안</span><span class="sxs-lookup"><span data-stu-id="9dc91-139">Securing Peer Channel Applications</span></span>](../../../wcf/feature-details/securing-peer-channel-applications.md)
- [<span data-ttu-id="9dc91-140">서비스 및 클라이언트에 보안 설정</span><span class="sxs-lookup"><span data-stu-id="9dc91-140">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
