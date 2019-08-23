---
title: <peer>of <clientCredentials> 요소
ms.date: 03/30/2017
ms.assetid: 505bd987-0042-4622-b68e-94f439729d53
ms.openlocfilehash: 2f1cb5689125e2483a74dcac515beb07abbb7c70
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/22/2019
ms.locfileid: "69934043"
---
# <a name="peer-of-clientcredentials-element"></a><span data-ttu-id="c8250-102">\<\<clientCredentials > 요소의 피어 ></span><span class="sxs-lookup"><span data-stu-id="c8250-102">\<peer> of \<clientCredentials> Element</span></span>
<span data-ttu-id="c8250-103">피어 투 피어 클라이언트를 인증할 때 사용하는 자격 증명을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="c8250-103">Specifies credentials used when authenticating peer-to-peer clients.</span></span>  
  
 <span data-ttu-id="c8250-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="c8250-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="c8250-105">\<behaviors></span><span class="sxs-lookup"><span data-stu-id="c8250-105">\<behaviors></span></span>  
<span data-ttu-id="c8250-106">\<endpointBehaviors></span><span class="sxs-lookup"><span data-stu-id="c8250-106">\<endpointBehaviors></span></span>  
<span data-ttu-id="c8250-107">\<behavior></span><span class="sxs-lookup"><span data-stu-id="c8250-107">\<behavior></span></span>  
<span data-ttu-id="c8250-108">\<clientCredentials></span><span class="sxs-lookup"><span data-stu-id="c8250-108">\<clientCredentials></span></span>  
<span data-ttu-id="c8250-109">\<peer></span><span class="sxs-lookup"><span data-stu-id="c8250-109">\<peer></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c8250-110">구문</span><span class="sxs-lookup"><span data-stu-id="c8250-110">Syntax</span></span>  
  
```xml  
<peer>
  <certificate />
  <peerAuthentication />
  <messageSenderAuthentication />
</peer>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="c8250-111">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="c8250-111">Attributes and Elements</span></span>  
 <span data-ttu-id="c8250-112">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="c8250-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="c8250-113">특성</span><span class="sxs-lookup"><span data-stu-id="c8250-113">Attributes</span></span>  
 <span data-ttu-id="c8250-114">없음</span><span class="sxs-lookup"><span data-stu-id="c8250-114">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="c8250-115">자식 요소</span><span class="sxs-lookup"><span data-stu-id="c8250-115">Child Elements</span></span>  
  
|<span data-ttu-id="c8250-116">요소</span><span class="sxs-lookup"><span data-stu-id="c8250-116">Element</span></span>|<span data-ttu-id="c8250-117">설명</span><span class="sxs-lookup"><span data-stu-id="c8250-117">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="c8250-118">\<certificate></span><span class="sxs-lookup"><span data-stu-id="c8250-118">\<certificate></span></span>](certificate-element.md)|<span data-ttu-id="c8250-119">피어 투 피어 클라이언트의 메시지를 서명 및 암호화하는 데 사용하는 X.509 인증서를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="c8250-119">Specifies an X.509 certificate to use for signing and encrypting messages for peer-to-peer clients.</span></span> <span data-ttu-id="c8250-120">을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="c8250-120">.</span></span>|  
|[<span data-ttu-id="c8250-121">\<peerAuthentication></span><span class="sxs-lookup"><span data-stu-id="c8250-121">\<peerAuthentication></span></span>](peerauthentication-element.md)|<span data-ttu-id="c8250-122">피어 클라이언트에 대한 인증 옵션을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="c8250-122">Specifies authentication options for peer clients.</span></span>|  
|[<span data-ttu-id="c8250-123">\<messageSenderAuthentication></span><span class="sxs-lookup"><span data-stu-id="c8250-123">\<messageSenderAuthentication></span></span>](messagesenderauthentication-element.md)|<span data-ttu-id="c8250-124">메시지 발신자에 대한 인증 옵션을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="c8250-124">Specifies authentication options for message senders.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="c8250-125">부모 요소</span><span class="sxs-lookup"><span data-stu-id="c8250-125">Parent Elements</span></span>  
  
|<span data-ttu-id="c8250-126">요소</span><span class="sxs-lookup"><span data-stu-id="c8250-126">Element</span></span>|<span data-ttu-id="c8250-127">Description</span><span class="sxs-lookup"><span data-stu-id="c8250-127">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="c8250-128">\<clientCredentials></span><span class="sxs-lookup"><span data-stu-id="c8250-128">\<clientCredentials></span></span>](clientcredentials.md)|<span data-ttu-id="c8250-129">클라이언트를 서비스에 인증할 때 사용되는 자격 증명을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="c8250-129">Specifies the credentials used to authenticate a client to a service.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c8250-130">설명</span><span class="sxs-lookup"><span data-stu-id="c8250-130">Remarks</span></span>  
 <span data-ttu-id="c8250-131">이 구성 요소는 피어 노드가 메시에서 다른 노드로부터 인증을 얻는 데 사용하는 자격 증명과 피어 노드가 다른 피어 노드를 인증하는 데 사용하는 인증 설정을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="c8250-131">This configuration element specifies the credentials that a peer node uses to authenticate itself to other nodes in the mesh, as well as authentication settings that a peer node uses to authenticate other peer nodes.</span></span> <span data-ttu-id="c8250-132">자세한 내용은 [피어 채널 메시지 인증](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/aa967730(v=vs.90)) 및 [피어 채널 응용 프로그램 보안](../../../wcf/feature-details/securing-peer-channel-applications.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="c8250-132">For more information, see [Peer Channel Message Authentication](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/aa967730(v=vs.90)) and [Securing Peer Channel Applications](../../../wcf/feature-details/securing-peer-channel-applications.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c8250-133">참고자료</span><span class="sxs-lookup"><span data-stu-id="c8250-133">See also</span></span>

- <xref:System.ServiceModel.Configuration.ClientCredentialsElement>
- <xref:System.ServiceModel.Description.ClientCredentials>
- <xref:System.ServiceModel.Configuration.PeerCredentialElement>
- <xref:System.ServiceModel.Configuration.ClientCredentialsElement.Peer%2A>
- <xref:System.ServiceModel.Description.ClientCredentials>
- <xref:System.ServiceModel.Description.ClientCredentials.Peer%2A>
- <xref:System.ServiceModel.Security.PeerCredential>
- [<span data-ttu-id="c8250-134">피어 투 피어 네트워킹</span><span class="sxs-lookup"><span data-stu-id="c8250-134">Peer-to-Peer Networking</span></span>](../../../wcf/feature-details/peer-to-peer-networking.md)
- [<span data-ttu-id="c8250-135">클라이언트에 보안 설정</span><span class="sxs-lookup"><span data-stu-id="c8250-135">Securing Clients</span></span>](../../../wcf/securing-clients.md)
- <span data-ttu-id="c8250-136">[피어 채널 메시지 인증](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/aa967730(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="c8250-136">[Peer Channel Message Authentication](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/aa967730(v=vs.90))</span></span>
- <span data-ttu-id="c8250-137">[피어 채널 사용자 지정 인증](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms751447(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="c8250-137">[Peer Channel Custom Authentication](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms751447(v=vs.90))</span></span>
- [<span data-ttu-id="c8250-138">피어 채널 애플리케이션 보안</span><span class="sxs-lookup"><span data-stu-id="c8250-138">Securing Peer Channel Applications</span></span>](../../../wcf/feature-details/securing-peer-channel-applications.md)
- [<span data-ttu-id="c8250-139">서비스 및 클라이언트에 보안 설정</span><span class="sxs-lookup"><span data-stu-id="c8250-139">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
