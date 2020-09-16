---
title: <serviceCredentials>의 <peer>
ms.date: 03/30/2017
ms.assetid: b134e21d-e5b5-458e-9309-626dbf8db4ed
ms.openlocfilehash: 50db8eb381249c3b880c4b1dd96ec3813d51ce67
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/15/2020
ms.locfileid: "90556117"
---
# <a name="peer-of-servicecredentials"></a><span data-ttu-id="a2a86-102">\<serviceCredentials>의 \<peer></span><span class="sxs-lookup"><span data-stu-id="a2a86-102">\<peer> of \<serviceCredentials></span></span>
<span data-ttu-id="a2a86-103">피어 노드에 대한 현재 자격 증명을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="a2a86-103">Specifies the current credentials for a peer node.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceCredentials>**](servicecredentials.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<peer>**  
  
## <a name="syntax"></a><span data-ttu-id="a2a86-104">구문</span><span class="sxs-lookup"><span data-stu-id="a2a86-104">Syntax</span></span>  
  
```xml  
<peer>
  <certificate />
  <peerAuthentication />
  <messageSenderAuthentication />
</peer>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="a2a86-105">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="a2a86-105">Attributes and Elements</span></span>  
 <span data-ttu-id="a2a86-106">다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="a2a86-106">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="a2a86-107">특성</span><span class="sxs-lookup"><span data-stu-id="a2a86-107">Attributes</span></span>  
 <span data-ttu-id="a2a86-108">없음</span><span class="sxs-lookup"><span data-stu-id="a2a86-108">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="a2a86-109">자식 요소</span><span class="sxs-lookup"><span data-stu-id="a2a86-109">Child Elements</span></span>  
  
|<span data-ttu-id="a2a86-110">요소</span><span class="sxs-lookup"><span data-stu-id="a2a86-110">Element</span></span>|<span data-ttu-id="a2a86-111">Description</span><span class="sxs-lookup"><span data-stu-id="a2a86-111">Description</span></span>|  
|-------------|-----------------|  
|[\<certificate>](certificate-of-peer.md)|<span data-ttu-id="a2a86-112">피어 투 피어 서비스의 메시지를 서명 및 암호화하는 데 사용하는 X.509 인증서를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="a2a86-112">Specifies an X.509 certificate to use for signing and encrypting messages for peer-to-peer services.</span></span> <span data-ttu-id="a2a86-113">.</span><span class="sxs-lookup"><span data-stu-id="a2a86-113">.</span></span>|  
|[\<messageSenderAuthentication>](messagesenderauthentication.md)|<span data-ttu-id="a2a86-114">메시지 발신자에 대한 인증 옵션을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="a2a86-114">Specifies authentication options for message senders.</span></span>|  
|[\<peerAuthentication>](peerauthentication.md)|<span data-ttu-id="a2a86-115">피어 서비스의 인증 옵션을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="a2a86-115">Specifies authentication options for peer services.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="a2a86-116">부모 요소</span><span class="sxs-lookup"><span data-stu-id="a2a86-116">Parent Elements</span></span>  
  
|<span data-ttu-id="a2a86-117">요소</span><span class="sxs-lookup"><span data-stu-id="a2a86-117">Element</span></span>|<span data-ttu-id="a2a86-118">Description</span><span class="sxs-lookup"><span data-stu-id="a2a86-118">Description</span></span>|  
|-------------|-----------------|  
|[\<serviceCredentials>](servicecredentials.md)|<span data-ttu-id="a2a86-119">서비스를 인증하는 데 사용되는 자격 증명 및 클라이언트 자격 증명 유효성 검사 관련 설정을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="a2a86-119">Specifies the credential to be used in authenticating the service, and the client credential validation-related settings.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="a2a86-120">참조</span><span class="sxs-lookup"><span data-stu-id="a2a86-120">See also</span></span>

- <xref:System.ServiceModel.Configuration.PeerCredentialElement>
- <xref:System.ServiceModel.Configuration.ServiceCredentialsElement.Peer%2A>
- <xref:System.ServiceModel.Description.ServiceCredentials.Peer%2A>
- <xref:System.ServiceModel.Security.PeerCredential>
- [<span data-ttu-id="a2a86-121">피어 투 피어 네트워킹</span><span class="sxs-lookup"><span data-stu-id="a2a86-121">Peer-to-Peer Networking</span></span>](../../../wcf/feature-details/peer-to-peer-networking.md)
- <span data-ttu-id="a2a86-122">[Peer Channel Message Authentication](/previous-versions/dotnet/netframework-3.5/aa967730(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="a2a86-122">[Peer Channel Message Authentication](/previous-versions/dotnet/netframework-3.5/aa967730(v=vs.90))</span></span>
- <span data-ttu-id="a2a86-123">[Peer Channel Custom Authentication](/previous-versions/dotnet/netframework-3.5/ms751447(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="a2a86-123">[Peer Channel Custom Authentication](/previous-versions/dotnet/netframework-3.5/ms751447(v=vs.90))</span></span>
- [<span data-ttu-id="a2a86-124">피어 채널 애플리케이션 보안</span><span class="sxs-lookup"><span data-stu-id="a2a86-124">Securing Peer Channel Applications</span></span>](../../../wcf/feature-details/securing-peer-channel-applications.md)
- [<span data-ttu-id="a2a86-125">서비스 및 클라이언트에 보안 설정</span><span class="sxs-lookup"><span data-stu-id="a2a86-125">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
