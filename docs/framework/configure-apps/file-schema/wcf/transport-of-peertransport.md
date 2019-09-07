---
title: <peerTransport>의 <transport>
ms.date: 03/30/2017
ms.assetid: d7116240-845c-4b6f-b203-262de6b597ef
ms.openlocfilehash: 3b2c7716727f58abb81bf4d58b13189ac170cf7c
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/06/2019
ms.locfileid: "70399298"
---
# <a name="transport-of-peertransport"></a><span data-ttu-id="75fea-102">\<peertransport > \<의 전송 ></span><span class="sxs-lookup"><span data-stu-id="75fea-102">\<transport> of \<peerTransport></span></span>
<span data-ttu-id="75fea-103">이 바인딩으로 구성된 피어에서 보낸 보안 메시지의 전송 형식을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="75fea-103">Specifies the transport type for secured messages sent by peers configured with this binding.</span></span>  
  
<span data-ttu-id="75fea-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="75fea-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="75fea-105">&nbsp;&nbsp;[ **\<System.servicemodel >** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="75fea-105">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="75fea-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<바인딩 >** ](bindings.md)</span><span class="sxs-lookup"><span data-stu-id="75fea-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)</span></span>\
<span data-ttu-id="75fea-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<customBinding >** ](custombinding.md)</span><span class="sxs-lookup"><span data-stu-id="75fea-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<customBinding>**](custombinding.md)</span></span>\
<span data-ttu-id="75fea-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<바인딩 >** </span><span class="sxs-lookup"><span data-stu-id="75fea-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**</span></span>\
<span data-ttu-id="75fea-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<peerTransport >** ](peertransport.md)</span><span class="sxs-lookup"><span data-stu-id="75fea-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<peerTransport>**](peertransport.md)</span></span>\
<span data-ttu-id="75fea-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<보안 >** ](security-of-peertransport.md)</span><span class="sxs-lookup"><span data-stu-id="75fea-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<security>**](security-of-peertransport.md)</span></span>\
<span data-ttu-id="75fea-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<전송 >**</span><span class="sxs-lookup"><span data-stu-id="75fea-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<transport>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="75fea-112">구문</span><span class="sxs-lookup"><span data-stu-id="75fea-112">Syntax</span></span>  
  
```xml  
<security>
  <transport credentialType="Certificate/Password" />
</security>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="75fea-113">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="75fea-113">Attributes and Elements</span></span>  
 <span data-ttu-id="75fea-114">다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="75fea-114">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="75fea-115">특성</span><span class="sxs-lookup"><span data-stu-id="75fea-115">Attributes</span></span>  
  
|<span data-ttu-id="75fea-116">특성</span><span class="sxs-lookup"><span data-stu-id="75fea-116">Attribute</span></span>|<span data-ttu-id="75fea-117">Description</span><span class="sxs-lookup"><span data-stu-id="75fea-117">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="75fea-118">credentialType</span><span class="sxs-lookup"><span data-stu-id="75fea-118">credentialType</span></span>|<span data-ttu-id="75fea-119">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="75fea-119">Optional.</span></span> <span data-ttu-id="75fea-120">피어 전송을 통해 보내는 메시지를 확인할 때 사용되는 자격 증명 형식을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="75fea-120">Specifies the type of credentials used to verify messages sent with the peer transport.</span></span> <span data-ttu-id="75fea-121">이 특성은 <xref:System.ServiceModel.PeerTransportCredentialType> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="75fea-121">This attribute is of type <xref:System.ServiceModel.PeerTransportCredentialType>.</span></span>|  
  
## <a name="credentialtype-attribute"></a><span data-ttu-id="75fea-122">credentialType 특성</span><span class="sxs-lookup"><span data-stu-id="75fea-122">credentialType Attribute</span></span>  
  
|<span data-ttu-id="75fea-123">값</span><span class="sxs-lookup"><span data-stu-id="75fea-123">Value</span></span>|<span data-ttu-id="75fea-124">설명</span><span class="sxs-lookup"><span data-stu-id="75fea-124">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="75fea-125">Certificate</span><span class="sxs-lookup"><span data-stu-id="75fea-125">Certificate</span></span>|<span data-ttu-id="75fea-126">피어 채널 전송을 인증하려면 X509 인증서가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="75fea-126">Authentication of the peer channel transport requires an X509 certificate.</span></span>|  
|<span data-ttu-id="75fea-127">암호</span><span class="sxs-lookup"><span data-stu-id="75fea-127">Password</span></span>|<span data-ttu-id="75fea-128">피어 채널 전송을 인증하려면 올바른 암호가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="75fea-128">Authentication of the peer channel transport requires a correct password.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="75fea-129">자식 요소</span><span class="sxs-lookup"><span data-stu-id="75fea-129">Child Elements</span></span>  
 <span data-ttu-id="75fea-130">없음</span><span class="sxs-lookup"><span data-stu-id="75fea-130">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="75fea-131">부모 요소</span><span class="sxs-lookup"><span data-stu-id="75fea-131">Parent Elements</span></span>  
  
|<span data-ttu-id="75fea-132">요소</span><span class="sxs-lookup"><span data-stu-id="75fea-132">Element</span></span>|<span data-ttu-id="75fea-133">설명</span><span class="sxs-lookup"><span data-stu-id="75fea-133">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="75fea-134">\<security></span><span class="sxs-lookup"><span data-stu-id="75fea-134">\<security></span></span>](security-of-peertransport.md)|<span data-ttu-id="75fea-135">피어 전송의 보안 설정을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="75fea-135">Defines the security settings for a peer transport.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="75fea-136">설명</span><span class="sxs-lookup"><span data-stu-id="75fea-136">Remarks</span></span>  
 <span data-ttu-id="75fea-137">이 요소는 [ \<security >](security-of-peertransport.md) 의 mode 특성이 또는 `TransportWithMessageCredential`로 설정 된 경우에 `Transport` 만 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="75fea-137">This element is set only if the mode attribute of [\<security>](security-of-peertransport.md) is set to `Transport` or `TransportWithMessageCredential`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="75fea-138">참고자료</span><span class="sxs-lookup"><span data-stu-id="75fea-138">See also</span></span>

- <xref:System.ServiceModel.Configuration.PeerTransportSecurityElement>
- <xref:System.ServiceModel.PeerSecuritySettings.Transport%2A>
- <xref:System.ServiceModel.PeerTransportSecuritySettings>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [<span data-ttu-id="75fea-139">전송 보안</span><span class="sxs-lookup"><span data-stu-id="75fea-139">Transport Security</span></span>](../../../wcf/feature-details/transport-security.md)
- [<span data-ttu-id="75fea-140">전송</span><span class="sxs-lookup"><span data-stu-id="75fea-140">Transports</span></span>](../../../wcf/feature-details/transports.md)
- [<span data-ttu-id="75fea-141">전송 선택</span><span class="sxs-lookup"><span data-stu-id="75fea-141">Choosing a Transport</span></span>](../../../wcf/feature-details/choosing-a-transport.md)
- [<span data-ttu-id="75fea-142">바인딩</span><span class="sxs-lookup"><span data-stu-id="75fea-142">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="75fea-143">바인딩 확장</span><span class="sxs-lookup"><span data-stu-id="75fea-143">Extending Bindings</span></span>](../../../wcf/extending/extending-bindings.md)
- [<span data-ttu-id="75fea-144">사용자 지정 바인딩</span><span class="sxs-lookup"><span data-stu-id="75fea-144">Custom Bindings</span></span>](../../../wcf/extending/custom-bindings.md)
- [<span data-ttu-id="75fea-145">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="75fea-145">\<customBinding></span></span>](custombinding.md)
