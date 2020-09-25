---
title: <netPeerTcpBinding>의 <transport>
ms.date: 03/30/2017
ms.assetid: c44d86d2-1160-44d7-9c7a-297b12eccc7f
ms.openlocfilehash: 5df47b1bfc149b524fc9b90eacffa832817f653c
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/24/2020
ms.locfileid: "91172868"
---
# <a name="transport-of-netpeertcpbinding"></a><span data-ttu-id="42d9c-102">\<netPeerTcpBinding>의 \<transport></span><span class="sxs-lookup"><span data-stu-id="42d9c-102">\<transport> of \<netPeerTcpBinding></span></span>

<span data-ttu-id="42d9c-103">를 사용할 때 전송 수준 보안 설정을 지정 합니다 [\<netPeerTcpBinding>](netpeertcpbinding.md) .</span><span class="sxs-lookup"><span data-stu-id="42d9c-103">Specifies settings for transport level security when using the [\<netPeerTcpBinding>](netpeertcpbinding.md).</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<netPeerTcpBinding>**](netpeertcpbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<security>**](security-of-netpeerbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<transport>**  
  
## <a name="syntax"></a><span data-ttu-id="42d9c-104">구문</span><span class="sxs-lookup"><span data-stu-id="42d9c-104">Syntax</span></span>  
  
```xml  
<netPeerTcpBinding>
  <binding>
    <security>
      <transport credentialType="Certificate/Password" />
    </security>
  </binding>
</netPeerTcpBinding>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="42d9c-105">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="42d9c-105">Attributes and Elements</span></span>  

 <span data-ttu-id="42d9c-106">다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="42d9c-106">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="42d9c-107">특성</span><span class="sxs-lookup"><span data-stu-id="42d9c-107">Attributes</span></span>  
  
|<span data-ttu-id="42d9c-108">attribute</span><span class="sxs-lookup"><span data-stu-id="42d9c-108">Attribute</span></span>|<span data-ttu-id="42d9c-109">설명</span><span class="sxs-lookup"><span data-stu-id="42d9c-109">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="42d9c-110">credentialType</span><span class="sxs-lookup"><span data-stu-id="42d9c-110">credentialType</span></span>|<span data-ttu-id="42d9c-111">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="42d9c-111">Optional.</span></span> <span data-ttu-id="42d9c-112">피어 전송을 통해 보내는 메시지를 확인할 때 사용되는 자격 증명 형식을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="42d9c-112">Specifies the type of credentials used to verify messages sent with the peer transport.</span></span> <span data-ttu-id="42d9c-113">이 특성은 <xref:System.ServiceModel.PeerTransportCredentialType> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="42d9c-113">This attribute is of type <xref:System.ServiceModel.PeerTransportCredentialType>.</span></span>|  
  
## <a name="credentialtype-attribute"></a><span data-ttu-id="42d9c-114">credentialType 특성</span><span class="sxs-lookup"><span data-stu-id="42d9c-114">credentialType Attribute</span></span>  
  
|<span data-ttu-id="42d9c-115">Value</span><span class="sxs-lookup"><span data-stu-id="42d9c-115">Value</span></span>|<span data-ttu-id="42d9c-116">설명</span><span class="sxs-lookup"><span data-stu-id="42d9c-116">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="42d9c-117">인증서</span><span class="sxs-lookup"><span data-stu-id="42d9c-117">Certificate</span></span>|<span data-ttu-id="42d9c-118">피어 채널 전송을 인증하려면 X509 인증서가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="42d9c-118">Authentication of the peer channel transport requires an X509 certificate.</span></span>|  
|<span data-ttu-id="42d9c-119">암호</span><span class="sxs-lookup"><span data-stu-id="42d9c-119">Password</span></span>|<span data-ttu-id="42d9c-120">피어 채널 전송을 인증하려면 올바른 암호가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="42d9c-120">Authentication of the peer channel transport requires a correct password.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="42d9c-121">자식 요소</span><span class="sxs-lookup"><span data-stu-id="42d9c-121">Child Elements</span></span>  

 <span data-ttu-id="42d9c-122">없음</span><span class="sxs-lookup"><span data-stu-id="42d9c-122">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="42d9c-123">부모 요소</span><span class="sxs-lookup"><span data-stu-id="42d9c-123">Parent Elements</span></span>  
  
|<span data-ttu-id="42d9c-124">요소</span><span class="sxs-lookup"><span data-stu-id="42d9c-124">Element</span></span>|<span data-ttu-id="42d9c-125">설명</span><span class="sxs-lookup"><span data-stu-id="42d9c-125">Description</span></span>|  
|-------------|-----------------|  
|[\<security>](security-of-netpeerbinding.md)|<span data-ttu-id="42d9c-126">에 대 한 보안 설정을 정의 합니다 [\<netPeerTcpBinding>](netpeertcpbinding.md) .</span><span class="sxs-lookup"><span data-stu-id="42d9c-126">Defines the security settings for the [\<netPeerTcpBinding>](netpeertcpbinding.md).</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="42d9c-127">참고 항목</span><span class="sxs-lookup"><span data-stu-id="42d9c-127">See also</span></span>

- <xref:System.ServiceModel.Configuration.PeerTransportSecurityElement>
- <xref:System.ServiceModel.PeerSecuritySettings.Transport%2A>
- <xref:System.ServiceModel.Configuration.PeerSecurityElement.Transport%2A>
- <xref:System.ServiceModel.PeerTransportSecuritySettings>
- [<span data-ttu-id="42d9c-128">서비스 및 클라이언트에 보안 설정</span><span class="sxs-lookup"><span data-stu-id="42d9c-128">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="42d9c-129">바인딩하</span><span class="sxs-lookup"><span data-stu-id="42d9c-129">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="42d9c-130">시스템 제공 바인딩 구성</span><span class="sxs-lookup"><span data-stu-id="42d9c-130">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="42d9c-131">바인딩을 사용하여 서비스 및 클라이언트 구성</span><span class="sxs-lookup"><span data-stu-id="42d9c-131">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [\<binding>](bindings.md)
