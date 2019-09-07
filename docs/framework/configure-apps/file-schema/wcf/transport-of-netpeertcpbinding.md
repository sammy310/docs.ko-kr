---
title: <netPeerTcpBinding>의 <transport>
ms.date: 03/30/2017
ms.assetid: c44d86d2-1160-44d7-9c7a-297b12eccc7f
ms.openlocfilehash: 08be5d752f8422ebe6442b295195f21b16a274c0
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/06/2019
ms.locfileid: "70399303"
---
# <a name="transport-of-netpeertcpbinding"></a><span data-ttu-id="87ed4-102">\<netpeertcpbinding의 \<전송 > ></span><span class="sxs-lookup"><span data-stu-id="87ed4-102">\<transport> of \<netPeerTcpBinding></span></span>
<span data-ttu-id="87ed4-103">[ \<Netpeertcpbinding >](netpeertcpbinding.md)를 사용할 때 전송 수준 보안에 대 한 설정을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="87ed4-103">Specifies settings for transport level security when using the [\<netPeerTcpBinding>](netpeertcpbinding.md).</span></span>  
  
<span data-ttu-id="87ed4-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="87ed4-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="87ed4-105">&nbsp;&nbsp;[ **\<System.servicemodel >** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="87ed4-105">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="87ed4-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<바인딩 >** ](bindings.md)</span><span class="sxs-lookup"><span data-stu-id="87ed4-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)</span></span>\
<span data-ttu-id="87ed4-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<netPeerTcpBinding >** ](netpeertcpbinding.md)</span><span class="sxs-lookup"><span data-stu-id="87ed4-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<netPeerTcpBinding>**](netpeertcpbinding.md)</span></span>\
<span data-ttu-id="87ed4-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<바인딩 >** </span><span class="sxs-lookup"><span data-stu-id="87ed4-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**</span></span>\
<span data-ttu-id="87ed4-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<보안 >** ](security-of-netpeerbinding.md)</span><span class="sxs-lookup"><span data-stu-id="87ed4-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<security>**](security-of-netpeerbinding.md)</span></span>\
<span data-ttu-id="87ed4-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<전송 >**</span><span class="sxs-lookup"><span data-stu-id="87ed4-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<transport>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="87ed4-111">구문</span><span class="sxs-lookup"><span data-stu-id="87ed4-111">Syntax</span></span>  
  
```xml  
<netPeerTcpBinding>
  <binding>
    <security>
      <transport credentialType="Certificate/Password" />
    </security>
  </binding>
</netPeerTcpBinding>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="87ed4-112">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="87ed4-112">Attributes and Elements</span></span>  
 <span data-ttu-id="87ed4-113">다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="87ed4-113">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="87ed4-114">특성</span><span class="sxs-lookup"><span data-stu-id="87ed4-114">Attributes</span></span>  
  
|<span data-ttu-id="87ed4-115">특성</span><span class="sxs-lookup"><span data-stu-id="87ed4-115">Attribute</span></span>|<span data-ttu-id="87ed4-116">설명</span><span class="sxs-lookup"><span data-stu-id="87ed4-116">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="87ed4-117">credentialType</span><span class="sxs-lookup"><span data-stu-id="87ed4-117">credentialType</span></span>|<span data-ttu-id="87ed4-118">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="87ed4-118">Optional.</span></span> <span data-ttu-id="87ed4-119">피어 전송을 통해 보내는 메시지를 확인할 때 사용되는 자격 증명 형식을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="87ed4-119">Specifies the type of credentials used to verify messages sent with the peer transport.</span></span> <span data-ttu-id="87ed4-120">이 특성은 <xref:System.ServiceModel.PeerTransportCredentialType> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="87ed4-120">This attribute is of type <xref:System.ServiceModel.PeerTransportCredentialType>.</span></span>|  
  
## <a name="credentialtype-attribute"></a><span data-ttu-id="87ed4-121">credentialType 특성</span><span class="sxs-lookup"><span data-stu-id="87ed4-121">credentialType Attribute</span></span>  
  
|<span data-ttu-id="87ed4-122">값</span><span class="sxs-lookup"><span data-stu-id="87ed4-122">Value</span></span>|<span data-ttu-id="87ed4-123">Description</span><span class="sxs-lookup"><span data-stu-id="87ed4-123">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="87ed4-124">Certificate</span><span class="sxs-lookup"><span data-stu-id="87ed4-124">Certificate</span></span>|<span data-ttu-id="87ed4-125">피어 채널 전송을 인증하려면 X509 인증서가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="87ed4-125">Authentication of the peer channel transport requires an X509 certificate.</span></span>|  
|<span data-ttu-id="87ed4-126">암호</span><span class="sxs-lookup"><span data-stu-id="87ed4-126">Password</span></span>|<span data-ttu-id="87ed4-127">피어 채널 전송을 인증하려면 올바른 암호가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="87ed4-127">Authentication of the peer channel transport requires a correct password.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="87ed4-128">자식 요소</span><span class="sxs-lookup"><span data-stu-id="87ed4-128">Child Elements</span></span>  
 <span data-ttu-id="87ed4-129">없음</span><span class="sxs-lookup"><span data-stu-id="87ed4-129">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="87ed4-130">부모 요소</span><span class="sxs-lookup"><span data-stu-id="87ed4-130">Parent Elements</span></span>  
  
|<span data-ttu-id="87ed4-131">요소</span><span class="sxs-lookup"><span data-stu-id="87ed4-131">Element</span></span>|<span data-ttu-id="87ed4-132">설명</span><span class="sxs-lookup"><span data-stu-id="87ed4-132">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="87ed4-133">\<security></span><span class="sxs-lookup"><span data-stu-id="87ed4-133">\<security></span></span>](security-of-netpeerbinding.md)|<span data-ttu-id="87ed4-134">Netpeertcpbinding >에 대 한 [ \<](netpeertcpbinding.md)보안 설정을 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="87ed4-134">Defines the security settings for the [\<netPeerTcpBinding>](netpeertcpbinding.md).</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="87ed4-135">참고자료</span><span class="sxs-lookup"><span data-stu-id="87ed4-135">See also</span></span>

- <xref:System.ServiceModel.Configuration.PeerTransportSecurityElement>
- <xref:System.ServiceModel.PeerSecuritySettings.Transport%2A>
- <xref:System.ServiceModel.Configuration.PeerSecurityElement.Transport%2A>
- <xref:System.ServiceModel.PeerTransportSecuritySettings>
- [<span data-ttu-id="87ed4-136">서비스 및 클라이언트에 보안 설정</span><span class="sxs-lookup"><span data-stu-id="87ed4-136">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="87ed4-137">바인딩</span><span class="sxs-lookup"><span data-stu-id="87ed4-137">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="87ed4-138">시스템 제공 바인딩 구성</span><span class="sxs-lookup"><span data-stu-id="87ed4-138">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="87ed4-139">바인딩을 사용하여 서비스 및 클라이언트 구성</span><span class="sxs-lookup"><span data-stu-id="87ed4-139">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="87ed4-140">\<binding></span><span class="sxs-lookup"><span data-stu-id="87ed4-140">\<binding></span></span>](../../../misc/binding.md)
