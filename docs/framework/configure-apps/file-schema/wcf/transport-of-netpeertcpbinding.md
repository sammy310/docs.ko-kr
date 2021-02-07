---
description: '다음에 대 한 자세한 정보:: <transport><netPeerTcpBinding>'
title: <netPeerTcpBinding>의 <transport>
ms.date: 03/30/2017
ms.assetid: c44d86d2-1160-44d7-9c7a-297b12eccc7f
ms.openlocfilehash: e93885234577e4f3c7a99be66e4798d33ffb5893
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99664576"
---
# <a name="transport-of-netpeertcpbinding"></a><span data-ttu-id="515d6-103">\<netPeerTcpBinding>의 \<transport></span><span class="sxs-lookup"><span data-stu-id="515d6-103">\<transport> of \<netPeerTcpBinding></span></span>

<span data-ttu-id="515d6-104">를 사용할 때 전송 수준 보안 설정을 지정 합니다 [\<netPeerTcpBinding>](netpeertcpbinding.md) .</span><span class="sxs-lookup"><span data-stu-id="515d6-104">Specifies settings for transport level security when using the [\<netPeerTcpBinding>](netpeertcpbinding.md).</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<netPeerTcpBinding>**](netpeertcpbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<security>**](security-of-netpeerbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<transport>**  
  
## <a name="syntax"></a><span data-ttu-id="515d6-105">구문</span><span class="sxs-lookup"><span data-stu-id="515d6-105">Syntax</span></span>  
  
```xml  
<netPeerTcpBinding>
  <binding>
    <security>
      <transport credentialType="Certificate/Password" />
    </security>
  </binding>
</netPeerTcpBinding>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="515d6-106">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="515d6-106">Attributes and Elements</span></span>  

 <span data-ttu-id="515d6-107">다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="515d6-107">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="515d6-108">특성</span><span class="sxs-lookup"><span data-stu-id="515d6-108">Attributes</span></span>  
  
|<span data-ttu-id="515d6-109">attribute</span><span class="sxs-lookup"><span data-stu-id="515d6-109">Attribute</span></span>|<span data-ttu-id="515d6-110">설명</span><span class="sxs-lookup"><span data-stu-id="515d6-110">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="515d6-111">credentialType</span><span class="sxs-lookup"><span data-stu-id="515d6-111">credentialType</span></span>|<span data-ttu-id="515d6-112">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="515d6-112">Optional.</span></span> <span data-ttu-id="515d6-113">피어 전송을 통해 보내는 메시지를 확인할 때 사용되는 자격 증명 형식을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="515d6-113">Specifies the type of credentials used to verify messages sent with the peer transport.</span></span> <span data-ttu-id="515d6-114">이 특성은 <xref:System.ServiceModel.PeerTransportCredentialType> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="515d6-114">This attribute is of type <xref:System.ServiceModel.PeerTransportCredentialType>.</span></span>|  
  
## <a name="credentialtype-attribute"></a><span data-ttu-id="515d6-115">credentialType 특성</span><span class="sxs-lookup"><span data-stu-id="515d6-115">credentialType Attribute</span></span>  
  
|<span data-ttu-id="515d6-116">값</span><span class="sxs-lookup"><span data-stu-id="515d6-116">Value</span></span>|<span data-ttu-id="515d6-117">설명</span><span class="sxs-lookup"><span data-stu-id="515d6-117">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="515d6-118">인증서</span><span class="sxs-lookup"><span data-stu-id="515d6-118">Certificate</span></span>|<span data-ttu-id="515d6-119">피어 채널 전송을 인증하려면 X509 인증서가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="515d6-119">Authentication of the peer channel transport requires an X509 certificate.</span></span>|  
|<span data-ttu-id="515d6-120">암호</span><span class="sxs-lookup"><span data-stu-id="515d6-120">Password</span></span>|<span data-ttu-id="515d6-121">피어 채널 전송을 인증하려면 올바른 암호가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="515d6-121">Authentication of the peer channel transport requires a correct password.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="515d6-122">자식 요소</span><span class="sxs-lookup"><span data-stu-id="515d6-122">Child Elements</span></span>  

 <span data-ttu-id="515d6-123">없음</span><span class="sxs-lookup"><span data-stu-id="515d6-123">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="515d6-124">부모 요소</span><span class="sxs-lookup"><span data-stu-id="515d6-124">Parent Elements</span></span>  
  
|<span data-ttu-id="515d6-125">요소</span><span class="sxs-lookup"><span data-stu-id="515d6-125">Element</span></span>|<span data-ttu-id="515d6-126">설명</span><span class="sxs-lookup"><span data-stu-id="515d6-126">Description</span></span>|  
|-------------|-----------------|  
|[\<security>](security-of-netpeerbinding.md)|<span data-ttu-id="515d6-127">에 대 한 보안 설정을 정의 합니다 [\<netPeerTcpBinding>](netpeertcpbinding.md) .</span><span class="sxs-lookup"><span data-stu-id="515d6-127">Defines the security settings for the [\<netPeerTcpBinding>](netpeertcpbinding.md).</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="515d6-128">참고 항목</span><span class="sxs-lookup"><span data-stu-id="515d6-128">See also</span></span>

- <xref:System.ServiceModel.Configuration.PeerTransportSecurityElement>
- <xref:System.ServiceModel.PeerSecuritySettings.Transport%2A>
- <xref:System.ServiceModel.Configuration.PeerSecurityElement.Transport%2A>
- <xref:System.ServiceModel.PeerTransportSecuritySettings>
- [<span data-ttu-id="515d6-129">서비스 및 클라이언트에 보안 설정</span><span class="sxs-lookup"><span data-stu-id="515d6-129">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="515d6-130">바인딩</span><span class="sxs-lookup"><span data-stu-id="515d6-130">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="515d6-131">시스템 제공 바인딩 구성</span><span class="sxs-lookup"><span data-stu-id="515d6-131">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="515d6-132">바인딩을 사용하여 서비스 및 클라이언트 구성</span><span class="sxs-lookup"><span data-stu-id="515d6-132">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [\<binding>](bindings.md)
