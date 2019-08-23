---
title: <serviceCredentials>의 <peer>
ms.date: 03/30/2017
ms.assetid: b134e21d-e5b5-458e-9309-626dbf8db4ed
ms.openlocfilehash: 50415cb9b35d2a2053efa3313a415de518b7e36e
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/22/2019
ms.locfileid: "69933783"
---
# <a name="peer-of-servicecredentials"></a><span data-ttu-id="8e8bb-102">\<serviceCredentials >의 \<피어 ></span><span class="sxs-lookup"><span data-stu-id="8e8bb-102">\<peer> of \<serviceCredentials></span></span>
<span data-ttu-id="8e8bb-103">피어 노드에 대한 현재 자격 증명을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="8e8bb-103">Specifies the current credentials for a peer node.</span></span>  
  
 <span data-ttu-id="8e8bb-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="8e8bb-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="8e8bb-105">\<behaviors></span><span class="sxs-lookup"><span data-stu-id="8e8bb-105">\<behaviors></span></span>  
<span data-ttu-id="8e8bb-106">\<serviceBehaviors></span><span class="sxs-lookup"><span data-stu-id="8e8bb-106">\<serviceBehaviors></span></span>  
<span data-ttu-id="8e8bb-107">\<behavior></span><span class="sxs-lookup"><span data-stu-id="8e8bb-107">\<behavior></span></span>  
<span data-ttu-id="8e8bb-108">\<serviceCredentials></span><span class="sxs-lookup"><span data-stu-id="8e8bb-108">\<serviceCredentials></span></span>  
<span data-ttu-id="8e8bb-109">\<peer></span><span class="sxs-lookup"><span data-stu-id="8e8bb-109">\<peer></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8e8bb-110">구문</span><span class="sxs-lookup"><span data-stu-id="8e8bb-110">Syntax</span></span>  
  
```xml  
<peer>
  <certificate />
  <peerAuthentication />
  <messageSenderAuthentication />
</peer>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="8e8bb-111">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="8e8bb-111">Attributes and Elements</span></span>  
 <span data-ttu-id="8e8bb-112">다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="8e8bb-112">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="8e8bb-113">특성</span><span class="sxs-lookup"><span data-stu-id="8e8bb-113">Attributes</span></span>  
 <span data-ttu-id="8e8bb-114">없음</span><span class="sxs-lookup"><span data-stu-id="8e8bb-114">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="8e8bb-115">자식 요소</span><span class="sxs-lookup"><span data-stu-id="8e8bb-115">Child Elements</span></span>  
  
|<span data-ttu-id="8e8bb-116">요소</span><span class="sxs-lookup"><span data-stu-id="8e8bb-116">Element</span></span>|<span data-ttu-id="8e8bb-117">Description</span><span class="sxs-lookup"><span data-stu-id="8e8bb-117">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="8e8bb-118">\<certificate></span><span class="sxs-lookup"><span data-stu-id="8e8bb-118">\<certificate></span></span>](certificate-of-peer.md)|<span data-ttu-id="8e8bb-119">피어 투 피어 서비스의 메시지를 서명 및 암호화하는 데 사용하는 X.509 인증서를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="8e8bb-119">Specifies an X.509 certificate to use for signing and encrypting messages for peer-to-peer services.</span></span> <span data-ttu-id="8e8bb-120">을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="8e8bb-120">.</span></span>|  
|[<span data-ttu-id="8e8bb-121">\<messageSenderAuthentication></span><span class="sxs-lookup"><span data-stu-id="8e8bb-121">\<messageSenderAuthentication></span></span>](messagesenderauthentication.md)|<span data-ttu-id="8e8bb-122">메시지 발신자에 대한 인증 옵션을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="8e8bb-122">Specifies authentication options for message senders.</span></span>|  
|[<span data-ttu-id="8e8bb-123">\<peerAuthentication></span><span class="sxs-lookup"><span data-stu-id="8e8bb-123">\<peerAuthentication></span></span>](peerauthentication.md)|<span data-ttu-id="8e8bb-124">피어 서비스의 인증 옵션을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="8e8bb-124">Specifies authentication options for peer services.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="8e8bb-125">부모 요소</span><span class="sxs-lookup"><span data-stu-id="8e8bb-125">Parent Elements</span></span>  
  
|<span data-ttu-id="8e8bb-126">요소</span><span class="sxs-lookup"><span data-stu-id="8e8bb-126">Element</span></span>|<span data-ttu-id="8e8bb-127">설명</span><span class="sxs-lookup"><span data-stu-id="8e8bb-127">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="8e8bb-128">\<serviceCredentials></span><span class="sxs-lookup"><span data-stu-id="8e8bb-128">\<serviceCredentials></span></span>](servicecredentials.md)|<span data-ttu-id="8e8bb-129">서비스를 인증하는 데 사용되는 자격 증명 및 클라이언트 자격 증명 유효성 검사 관련 설정을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="8e8bb-129">Specifies the credential to be used in authenticating the service, and the client credential validation-related settings.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="8e8bb-130">참고자료</span><span class="sxs-lookup"><span data-stu-id="8e8bb-130">See also</span></span>

- <xref:System.ServiceModel.Configuration.PeerCredentialElement>
- <xref:System.ServiceModel.Configuration.ServiceCredentialsElement.Peer%2A>
- <xref:System.ServiceModel.Description.ServiceCredentials.Peer%2A>
- <xref:System.ServiceModel.Security.PeerCredential>
- [<span data-ttu-id="8e8bb-131">피어 투 피어 네트워킹</span><span class="sxs-lookup"><span data-stu-id="8e8bb-131">Peer-to-Peer Networking</span></span>](../../../wcf/feature-details/peer-to-peer-networking.md)
- <span data-ttu-id="8e8bb-132">[피어 채널 메시지 인증](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/aa967730(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="8e8bb-132">[Peer Channel Message Authentication](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/aa967730(v=vs.90))</span></span>
- <span data-ttu-id="8e8bb-133">[피어 채널 사용자 지정 인증](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms751447(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="8e8bb-133">[Peer Channel Custom Authentication](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms751447(v=vs.90))</span></span>
- [<span data-ttu-id="8e8bb-134">피어 채널 애플리케이션 보안</span><span class="sxs-lookup"><span data-stu-id="8e8bb-134">Securing Peer Channel Applications</span></span>](../../../wcf/feature-details/securing-peer-channel-applications.md)
- [<span data-ttu-id="8e8bb-135">서비스 및 클라이언트에 보안 설정</span><span class="sxs-lookup"><span data-stu-id="8e8bb-135">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
