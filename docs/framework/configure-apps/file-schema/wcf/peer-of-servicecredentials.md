---
title: <serviceCredentials>의 <peer>
ms.date: 03/30/2017
ms.assetid: b134e21d-e5b5-458e-9309-626dbf8db4ed
ms.openlocfilehash: ca97be7b1ab562382895fea4f1d1fc716151b70b
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/06/2019
ms.locfileid: "70397637"
---
# <a name="peer-of-servicecredentials"></a><span data-ttu-id="9d4a4-102">\<serviceCredentials >의 \<피어 ></span><span class="sxs-lookup"><span data-stu-id="9d4a4-102">\<peer> of \<serviceCredentials></span></span>
<span data-ttu-id="9d4a4-103">피어 노드에 대한 현재 자격 증명을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="9d4a4-103">Specifies the current credentials for a peer node.</span></span>  
  
<span data-ttu-id="9d4a4-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="9d4a4-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="9d4a4-105">&nbsp;&nbsp;[ **\<System.servicemodel >** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="9d4a4-105">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="9d4a4-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<동작 >** ](behaviors.md)</span><span class="sxs-lookup"><span data-stu-id="9d4a4-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)</span></span>\
<span data-ttu-id="9d4a4-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<serviceBehaviors >** ](servicebehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="9d4a4-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors.md)</span></span>\
<span data-ttu-id="9d4a4-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<동작 >** ](behavior-of-servicebehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="9d4a4-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-servicebehaviors.md)</span></span>\
<span data-ttu-id="9d4a4-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<serviceCredentials >** ](servicecredentials.md)</span><span class="sxs-lookup"><span data-stu-id="9d4a4-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceCredentials>**](servicecredentials.md)</span></span>\
<span data-ttu-id="9d4a4-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<피어 >**</span><span class="sxs-lookup"><span data-stu-id="9d4a4-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<peer>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9d4a4-111">구문</span><span class="sxs-lookup"><span data-stu-id="9d4a4-111">Syntax</span></span>  
  
```xml  
<peer>
  <certificate />
  <peerAuthentication />
  <messageSenderAuthentication />
</peer>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="9d4a4-112">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="9d4a4-112">Attributes and Elements</span></span>  
 <span data-ttu-id="9d4a4-113">다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="9d4a4-113">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="9d4a4-114">특성</span><span class="sxs-lookup"><span data-stu-id="9d4a4-114">Attributes</span></span>  
 <span data-ttu-id="9d4a4-115">없음</span><span class="sxs-lookup"><span data-stu-id="9d4a4-115">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="9d4a4-116">자식 요소</span><span class="sxs-lookup"><span data-stu-id="9d4a4-116">Child Elements</span></span>  
  
|<span data-ttu-id="9d4a4-117">요소</span><span class="sxs-lookup"><span data-stu-id="9d4a4-117">Element</span></span>|<span data-ttu-id="9d4a4-118">Description</span><span class="sxs-lookup"><span data-stu-id="9d4a4-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="9d4a4-119">\<certificate></span><span class="sxs-lookup"><span data-stu-id="9d4a4-119">\<certificate></span></span>](certificate-of-peer.md)|<span data-ttu-id="9d4a4-120">피어 투 피어 서비스의 메시지를 서명 및 암호화하는 데 사용하는 X.509 인증서를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="9d4a4-120">Specifies an X.509 certificate to use for signing and encrypting messages for peer-to-peer services.</span></span> <span data-ttu-id="9d4a4-121">을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="9d4a4-121">.</span></span>|  
|[<span data-ttu-id="9d4a4-122">\<messageSenderAuthentication></span><span class="sxs-lookup"><span data-stu-id="9d4a4-122">\<messageSenderAuthentication></span></span>](messagesenderauthentication.md)|<span data-ttu-id="9d4a4-123">메시지 발신자에 대한 인증 옵션을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="9d4a4-123">Specifies authentication options for message senders.</span></span>|  
|[<span data-ttu-id="9d4a4-124">\<peerAuthentication></span><span class="sxs-lookup"><span data-stu-id="9d4a4-124">\<peerAuthentication></span></span>](peerauthentication.md)|<span data-ttu-id="9d4a4-125">피어 서비스의 인증 옵션을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="9d4a4-125">Specifies authentication options for peer services.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="9d4a4-126">부모 요소</span><span class="sxs-lookup"><span data-stu-id="9d4a4-126">Parent Elements</span></span>  
  
|<span data-ttu-id="9d4a4-127">요소</span><span class="sxs-lookup"><span data-stu-id="9d4a4-127">Element</span></span>|<span data-ttu-id="9d4a4-128">Description</span><span class="sxs-lookup"><span data-stu-id="9d4a4-128">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="9d4a4-129">\<serviceCredentials></span><span class="sxs-lookup"><span data-stu-id="9d4a4-129">\<serviceCredentials></span></span>](servicecredentials.md)|<span data-ttu-id="9d4a4-130">서비스를 인증하는 데 사용되는 자격 증명 및 클라이언트 자격 증명 유효성 검사 관련 설정을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="9d4a4-130">Specifies the credential to be used in authenticating the service, and the client credential validation-related settings.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="9d4a4-131">참고자료</span><span class="sxs-lookup"><span data-stu-id="9d4a4-131">See also</span></span>

- <xref:System.ServiceModel.Configuration.PeerCredentialElement>
- <xref:System.ServiceModel.Configuration.ServiceCredentialsElement.Peer%2A>
- <xref:System.ServiceModel.Description.ServiceCredentials.Peer%2A>
- <xref:System.ServiceModel.Security.PeerCredential>
- [<span data-ttu-id="9d4a4-132">피어 투 피어 네트워킹</span><span class="sxs-lookup"><span data-stu-id="9d4a4-132">Peer-to-Peer Networking</span></span>](../../../wcf/feature-details/peer-to-peer-networking.md)
- <span data-ttu-id="9d4a4-133">[피어 채널 메시지 인증](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/aa967730(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="9d4a4-133">[Peer Channel Message Authentication](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/aa967730(v=vs.90))</span></span>
- <span data-ttu-id="9d4a4-134">[피어 채널 사용자 지정 인증](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms751447(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="9d4a4-134">[Peer Channel Custom Authentication](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms751447(v=vs.90))</span></span>
- [<span data-ttu-id="9d4a4-135">피어 채널 애플리케이션 보안</span><span class="sxs-lookup"><span data-stu-id="9d4a4-135">Securing Peer Channel Applications</span></span>](../../../wcf/feature-details/securing-peer-channel-applications.md)
- [<span data-ttu-id="9d4a4-136">서비스 및 클라이언트에 보안 설정</span><span class="sxs-lookup"><span data-stu-id="9d4a4-136">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
