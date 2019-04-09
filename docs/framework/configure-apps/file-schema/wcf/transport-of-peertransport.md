---
title: <transport> / <peerTransport>
ms.date: 03/30/2017
ms.assetid: d7116240-845c-4b6f-b203-262de6b597ef
ms.openlocfilehash: 9b6f548515afbba5068659bd5c6f7f2b33f80cda
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59076005"
---
# <a name="transport-of-peertransport"></a><span data-ttu-id="4ad4c-102">\<전송 >의 \<peerTransport ></span><span class="sxs-lookup"><span data-stu-id="4ad4c-102">\<transport> of \<peerTransport></span></span>
<span data-ttu-id="4ad4c-103">이 바인딩으로 구성된 피어에서 보낸 보안 메시지의 전송 형식을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="4ad4c-103">Specifies the transport type for secured messages sent by peers configured with this binding.</span></span>  
  
 <span data-ttu-id="4ad4c-104">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="4ad4c-104">\<system.serviceModel></span></span>  
<span data-ttu-id="4ad4c-105">\<bindings></span><span class="sxs-lookup"><span data-stu-id="4ad4c-105">\<bindings></span></span>  
<span data-ttu-id="4ad4c-106">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="4ad4c-106">\<customBinding></span></span>  
<span data-ttu-id="4ad4c-107">\<binding></span><span class="sxs-lookup"><span data-stu-id="4ad4c-107">\<binding></span></span>  
<span data-ttu-id="4ad4c-108">\<peerTransport></span><span class="sxs-lookup"><span data-stu-id="4ad4c-108">\<peerTransport></span></span>  
<span data-ttu-id="4ad4c-109">\<security></span><span class="sxs-lookup"><span data-stu-id="4ad4c-109">\<security></span></span>  
<span data-ttu-id="4ad4c-110">\<transport></span><span class="sxs-lookup"><span data-stu-id="4ad4c-110">\<transport></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4ad4c-111">구문</span><span class="sxs-lookup"><span data-stu-id="4ad4c-111">Syntax</span></span>  
  
```xml  
<security>
  <transport credentialType="Certificate/Password" />
</security>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="4ad4c-112">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="4ad4c-112">Attributes and Elements</span></span>  
 <span data-ttu-id="4ad4c-113">다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="4ad4c-113">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="4ad4c-114">특성</span><span class="sxs-lookup"><span data-stu-id="4ad4c-114">Attributes</span></span>  
  
|<span data-ttu-id="4ad4c-115">특성</span><span class="sxs-lookup"><span data-stu-id="4ad4c-115">Attribute</span></span>|<span data-ttu-id="4ad4c-116">설명</span><span class="sxs-lookup"><span data-stu-id="4ad4c-116">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="4ad4c-117">credentialType</span><span class="sxs-lookup"><span data-stu-id="4ad4c-117">credentialType</span></span>|<span data-ttu-id="4ad4c-118">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="4ad4c-118">Optional.</span></span> <span data-ttu-id="4ad4c-119">피어 전송을 통해 보내는 메시지를 확인할 때 사용되는 자격 증명 형식을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="4ad4c-119">Specifies the type of credentials used to verify messages sent with the peer transport.</span></span> <span data-ttu-id="4ad4c-120">이 특성은 <xref:System.ServiceModel.PeerTransportCredentialType> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="4ad4c-120">This attribute is of type <xref:System.ServiceModel.PeerTransportCredentialType>.</span></span>|  
  
## <a name="credentialtype-attribute"></a><span data-ttu-id="4ad4c-121">credentialType 특성</span><span class="sxs-lookup"><span data-stu-id="4ad4c-121">credentialType Attribute</span></span>  
  
|<span data-ttu-id="4ad4c-122">값</span><span class="sxs-lookup"><span data-stu-id="4ad4c-122">Value</span></span>|<span data-ttu-id="4ad4c-123">설명</span><span class="sxs-lookup"><span data-stu-id="4ad4c-123">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="4ad4c-124">인증서</span><span class="sxs-lookup"><span data-stu-id="4ad4c-124">Certificate</span></span>|<span data-ttu-id="4ad4c-125">피어 채널 전송을 인증하려면 X509 인증서가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="4ad4c-125">Authentication of the peer channel transport requires an X509 certificate.</span></span>|  
|<span data-ttu-id="4ad4c-126">암호</span><span class="sxs-lookup"><span data-stu-id="4ad4c-126">Password</span></span>|<span data-ttu-id="4ad4c-127">피어 채널 전송을 인증하려면 올바른 암호가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="4ad4c-127">Authentication of the peer channel transport requires a correct password.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="4ad4c-128">자식 요소</span><span class="sxs-lookup"><span data-stu-id="4ad4c-128">Child Elements</span></span>  
 <span data-ttu-id="4ad4c-129">없음</span><span class="sxs-lookup"><span data-stu-id="4ad4c-129">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="4ad4c-130">부모 요소</span><span class="sxs-lookup"><span data-stu-id="4ad4c-130">Parent Elements</span></span>  
  
|<span data-ttu-id="4ad4c-131">요소</span><span class="sxs-lookup"><span data-stu-id="4ad4c-131">Element</span></span>|<span data-ttu-id="4ad4c-132">설명</span><span class="sxs-lookup"><span data-stu-id="4ad4c-132">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="4ad4c-133">\<security></span><span class="sxs-lookup"><span data-stu-id="4ad4c-133">\<security></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/security-of-peertransport.md)|<span data-ttu-id="4ad4c-134">피어 전송의 보안 설정을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="4ad4c-134">Defines the security settings for a peer transport.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4ad4c-135">설명</span><span class="sxs-lookup"><span data-stu-id="4ad4c-135">Remarks</span></span>  
 <span data-ttu-id="4ad4c-136">경우에이 요소는 설정의 mode 특성이 [ \<보안 >](../../../../../docs/framework/configure-apps/file-schema/wcf/security-of-peertransport.md) 로 설정 되어 `Transport` 또는 `TransportWithMessageCredential`합니다.</span><span class="sxs-lookup"><span data-stu-id="4ad4c-136">This element is set only if the mode attribute of [\<security>](../../../../../docs/framework/configure-apps/file-schema/wcf/security-of-peertransport.md) is set to `Transport` or `TransportWithMessageCredential`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4ad4c-137">참고자료</span><span class="sxs-lookup"><span data-stu-id="4ad4c-137">See also</span></span>

- <xref:System.ServiceModel.Configuration.PeerTransportSecurityElement>
- <xref:System.ServiceModel.PeerSecuritySettings.Transport%2A>
- <xref:System.ServiceModel.PeerTransportSecuritySettings>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [<span data-ttu-id="4ad4c-138">전송 보안</span><span class="sxs-lookup"><span data-stu-id="4ad4c-138">Transport Security</span></span>](../../../../../docs/framework/wcf/feature-details/transport-security.md)
- [<span data-ttu-id="4ad4c-139">전송</span><span class="sxs-lookup"><span data-stu-id="4ad4c-139">Transports</span></span>](../../../../../docs/framework/wcf/feature-details/transports.md)
- [<span data-ttu-id="4ad4c-140">전송 선택</span><span class="sxs-lookup"><span data-stu-id="4ad4c-140">Choosing a Transport</span></span>](../../../../../docs/framework/wcf/feature-details/choosing-a-transport.md)
- [<span data-ttu-id="4ad4c-141">바인딩</span><span class="sxs-lookup"><span data-stu-id="4ad4c-141">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)
- [<span data-ttu-id="4ad4c-142">바인딩 확장명</span><span class="sxs-lookup"><span data-stu-id="4ad4c-142">Extending Bindings</span></span>](../../../../../docs/framework/wcf/extending/extending-bindings.md)
- [<span data-ttu-id="4ad4c-143">사용자 지정 바인딩</span><span class="sxs-lookup"><span data-stu-id="4ad4c-143">Custom Bindings</span></span>](../../../../../docs/framework/wcf/extending/custom-bindings.md)
- [<span data-ttu-id="4ad4c-144">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="4ad4c-144">\<customBinding></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)
