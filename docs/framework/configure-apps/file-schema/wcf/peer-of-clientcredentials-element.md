---
description: '다음에 대 한 자세한 정보: <peer> <clientCredentials> 요소'
title: <peer> of <clientCredentials> 요소
ms.date: 03/30/2017
ms.assetid: 505bd987-0042-4622-b68e-94f439729d53
ms.openlocfilehash: 1ff9386ba51dcf6bab6df71bd345cdaa59f18e3a
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99683790"
---
# <a name="peer-of-clientcredentials-element"></a><span data-ttu-id="939ea-103">\<peer> of \<clientCredentials> 요소</span><span class="sxs-lookup"><span data-stu-id="939ea-103">\<peer> of \<clientCredentials> Element</span></span>

<span data-ttu-id="939ea-104">피어 투 피어 클라이언트를 인증할 때 사용하는 자격 증명을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="939ea-104">Specifies credentials used when authenticating peer-to-peer clients.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpointBehaviors>**](endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<clientCredentials>**](clientcredentials.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<peer>**  
  
## <a name="syntax"></a><span data-ttu-id="939ea-105">구문</span><span class="sxs-lookup"><span data-stu-id="939ea-105">Syntax</span></span>  
  
```xml  
<peer>
  <certificate />
  <peerAuthentication />
  <messageSenderAuthentication />
</peer>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="939ea-106">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="939ea-106">Attributes and Elements</span></span>  

 <span data-ttu-id="939ea-107">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="939ea-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="939ea-108">특성</span><span class="sxs-lookup"><span data-stu-id="939ea-108">Attributes</span></span>  

 <span data-ttu-id="939ea-109">없음</span><span class="sxs-lookup"><span data-stu-id="939ea-109">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="939ea-110">자식 요소</span><span class="sxs-lookup"><span data-stu-id="939ea-110">Child Elements</span></span>  
  
|<span data-ttu-id="939ea-111">요소</span><span class="sxs-lookup"><span data-stu-id="939ea-111">Element</span></span>|<span data-ttu-id="939ea-112">설명</span><span class="sxs-lookup"><span data-stu-id="939ea-112">Description</span></span>|  
|-------------|-----------------|  
|[\<certificate>](certificate-element.md)|<span data-ttu-id="939ea-113">피어 투 피어 클라이언트의 메시지를 서명 및 암호화하는 데 사용하는 X.509 인증서를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="939ea-113">Specifies an X.509 certificate to use for signing and encrypting messages for peer-to-peer clients.</span></span> <span data-ttu-id="939ea-114">.</span><span class="sxs-lookup"><span data-stu-id="939ea-114">.</span></span>|  
|[\<peerAuthentication>](peerauthentication-element.md)|<span data-ttu-id="939ea-115">피어 클라이언트에 대한 인증 옵션을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="939ea-115">Specifies authentication options for peer clients.</span></span>|  
|[\<messageSenderAuthentication>](messagesenderauthentication-element.md)|<span data-ttu-id="939ea-116">메시지 발신자에 대한 인증 옵션을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="939ea-116">Specifies authentication options for message senders.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="939ea-117">부모 요소</span><span class="sxs-lookup"><span data-stu-id="939ea-117">Parent Elements</span></span>  
  
|<span data-ttu-id="939ea-118">요소</span><span class="sxs-lookup"><span data-stu-id="939ea-118">Element</span></span>|<span data-ttu-id="939ea-119">설명</span><span class="sxs-lookup"><span data-stu-id="939ea-119">Description</span></span>|  
|-------------|-----------------|  
|[\<clientCredentials>](clientcredentials.md)|<span data-ttu-id="939ea-120">클라이언트를 서비스에 인증할 때 사용되는 자격 증명을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="939ea-120">Specifies the credentials used to authenticate a client to a service.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="939ea-121">설명</span><span class="sxs-lookup"><span data-stu-id="939ea-121">Remarks</span></span>  

 <span data-ttu-id="939ea-122">이 구성 요소는 피어 노드가 메시에서 다른 노드로부터 인증을 얻는 데 사용하는 자격 증명과 피어 노드가 다른 피어 노드를 인증하는 데 사용하는 인증 설정을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="939ea-122">This configuration element specifies the credentials that a peer node uses to authenticate itself to other nodes in the mesh, as well as authentication settings that a peer node uses to authenticate other peer nodes.</span></span> <span data-ttu-id="939ea-123">자세한 내용은 [피어 채널 메시지 인증](/previous-versions/dotnet/netframework-3.5/aa967730(v=vs.90)) 및 [피어 채널 응용 프로그램 보안](../../../wcf/feature-details/securing-peer-channel-applications.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="939ea-123">For more information, see [Peer Channel Message Authentication](/previous-versions/dotnet/netframework-3.5/aa967730(v=vs.90)) and [Securing Peer Channel Applications](../../../wcf/feature-details/securing-peer-channel-applications.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="939ea-124">참고 항목</span><span class="sxs-lookup"><span data-stu-id="939ea-124">See also</span></span>

- <xref:System.ServiceModel.Configuration.ClientCredentialsElement>
- <xref:System.ServiceModel.Description.ClientCredentials>
- <xref:System.ServiceModel.Configuration.PeerCredentialElement>
- <xref:System.ServiceModel.Configuration.ClientCredentialsElement.Peer%2A>
- <xref:System.ServiceModel.Description.ClientCredentials>
- <xref:System.ServiceModel.Description.ClientCredentials.Peer%2A>
- <xref:System.ServiceModel.Security.PeerCredential>
- [<span data-ttu-id="939ea-125">피어 투 피어 네트워킹</span><span class="sxs-lookup"><span data-stu-id="939ea-125">Peer-to-Peer Networking</span></span>](../../../wcf/feature-details/peer-to-peer-networking.md)
- [<span data-ttu-id="939ea-126">클라이언트에 보안 설정</span><span class="sxs-lookup"><span data-stu-id="939ea-126">Securing Clients</span></span>](../../../wcf/securing-clients.md)
- <span data-ttu-id="939ea-127">[Peer Channel Message Authentication](/previous-versions/dotnet/netframework-3.5/aa967730(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="939ea-127">[Peer Channel Message Authentication](/previous-versions/dotnet/netframework-3.5/aa967730(v=vs.90))</span></span>
- <span data-ttu-id="939ea-128">[Peer Channel Custom Authentication](/previous-versions/dotnet/netframework-3.5/ms751447(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="939ea-128">[Peer Channel Custom Authentication](/previous-versions/dotnet/netframework-3.5/ms751447(v=vs.90))</span></span>
- [<span data-ttu-id="939ea-129">피어 채널 애플리케이션 보안</span><span class="sxs-lookup"><span data-stu-id="939ea-129">Securing Peer Channel Applications</span></span>](../../../wcf/feature-details/securing-peer-channel-applications.md)
- [<span data-ttu-id="939ea-130">서비스 및 클라이언트에 보안 설정</span><span class="sxs-lookup"><span data-stu-id="939ea-130">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
