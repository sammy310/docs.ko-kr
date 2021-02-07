---
description: '다음에 대 한 자세한 정보:: <transport><peerTransport>'
title: <peerTransport>의 <transport>
ms.date: 03/30/2017
ms.assetid: d7116240-845c-4b6f-b203-262de6b597ef
ms.openlocfilehash: ba3405c5dfadb513f92ebd537409a3f7b12fa291
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99664511"
---
# <a name="transport-of-peertransport"></a><span data-ttu-id="c8469-103">\<peerTransport>의 \<transport></span><span class="sxs-lookup"><span data-stu-id="c8469-103">\<transport> of \<peerTransport></span></span>

<span data-ttu-id="c8469-104">이 바인딩으로 구성된 피어에서 보낸 보안 메시지의 전송 형식을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="c8469-104">Specifies the transport type for secured messages sent by peers configured with this binding.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<customBinding>**](custombinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<peerTransport>**](peertransport.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<security>**](security-of-peertransport.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<transport>**  
  
## <a name="syntax"></a><span data-ttu-id="c8469-105">구문</span><span class="sxs-lookup"><span data-stu-id="c8469-105">Syntax</span></span>  
  
```xml  
<security>
  <transport credentialType="Certificate/Password" />
</security>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="c8469-106">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="c8469-106">Attributes and Elements</span></span>  

 <span data-ttu-id="c8469-107">다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="c8469-107">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="c8469-108">특성</span><span class="sxs-lookup"><span data-stu-id="c8469-108">Attributes</span></span>  
  
|<span data-ttu-id="c8469-109">attribute</span><span class="sxs-lookup"><span data-stu-id="c8469-109">Attribute</span></span>|<span data-ttu-id="c8469-110">설명</span><span class="sxs-lookup"><span data-stu-id="c8469-110">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="c8469-111">credentialType</span><span class="sxs-lookup"><span data-stu-id="c8469-111">credentialType</span></span>|<span data-ttu-id="c8469-112">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="c8469-112">Optional.</span></span> <span data-ttu-id="c8469-113">피어 전송을 통해 보내는 메시지를 확인할 때 사용되는 자격 증명 형식을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="c8469-113">Specifies the type of credentials used to verify messages sent with the peer transport.</span></span> <span data-ttu-id="c8469-114">이 특성은 <xref:System.ServiceModel.PeerTransportCredentialType> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="c8469-114">This attribute is of type <xref:System.ServiceModel.PeerTransportCredentialType>.</span></span>|  
  
## <a name="credentialtype-attribute"></a><span data-ttu-id="c8469-115">credentialType 특성</span><span class="sxs-lookup"><span data-stu-id="c8469-115">credentialType Attribute</span></span>  
  
|<span data-ttu-id="c8469-116">값</span><span class="sxs-lookup"><span data-stu-id="c8469-116">Value</span></span>|<span data-ttu-id="c8469-117">설명</span><span class="sxs-lookup"><span data-stu-id="c8469-117">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="c8469-118">인증서</span><span class="sxs-lookup"><span data-stu-id="c8469-118">Certificate</span></span>|<span data-ttu-id="c8469-119">피어 채널 전송을 인증하려면 X509 인증서가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="c8469-119">Authentication of the peer channel transport requires an X509 certificate.</span></span>|  
|<span data-ttu-id="c8469-120">암호</span><span class="sxs-lookup"><span data-stu-id="c8469-120">Password</span></span>|<span data-ttu-id="c8469-121">피어 채널 전송을 인증하려면 올바른 암호가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="c8469-121">Authentication of the peer channel transport requires a correct password.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="c8469-122">자식 요소</span><span class="sxs-lookup"><span data-stu-id="c8469-122">Child Elements</span></span>  

 <span data-ttu-id="c8469-123">없음</span><span class="sxs-lookup"><span data-stu-id="c8469-123">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="c8469-124">부모 요소</span><span class="sxs-lookup"><span data-stu-id="c8469-124">Parent Elements</span></span>  
  
|<span data-ttu-id="c8469-125">요소</span><span class="sxs-lookup"><span data-stu-id="c8469-125">Element</span></span>|<span data-ttu-id="c8469-126">설명</span><span class="sxs-lookup"><span data-stu-id="c8469-126">Description</span></span>|  
|-------------|-----------------|  
|[\<security>](security-of-peertransport.md)|<span data-ttu-id="c8469-127">피어 전송의 보안 설정을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="c8469-127">Defines the security settings for a peer transport.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c8469-128">설명</span><span class="sxs-lookup"><span data-stu-id="c8469-128">Remarks</span></span>  

 <span data-ttu-id="c8469-129">이 요소는의 mode 특성이 또는로 설정 된 경우에만 설정 됩니다 [\<security>](security-of-peertransport.md) `Transport` `TransportWithMessageCredential` .</span><span class="sxs-lookup"><span data-stu-id="c8469-129">This element is set only if the mode attribute of [\<security>](security-of-peertransport.md) is set to `Transport` or `TransportWithMessageCredential`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c8469-130">참고 항목</span><span class="sxs-lookup"><span data-stu-id="c8469-130">See also</span></span>

- <xref:System.ServiceModel.Configuration.PeerTransportSecurityElement>
- <xref:System.ServiceModel.PeerSecuritySettings.Transport%2A>
- <xref:System.ServiceModel.PeerTransportSecuritySettings>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [<span data-ttu-id="c8469-131">전송 보안</span><span class="sxs-lookup"><span data-stu-id="c8469-131">Transport Security</span></span>](../../../wcf/feature-details/transport-security.md)
- [<span data-ttu-id="c8469-132">전송</span><span class="sxs-lookup"><span data-stu-id="c8469-132">Transports</span></span>](../../../wcf/feature-details/transports.md)
- [<span data-ttu-id="c8469-133">전송 선택</span><span class="sxs-lookup"><span data-stu-id="c8469-133">Choosing a Transport</span></span>](../../../wcf/feature-details/choosing-a-transport.md)
- [<span data-ttu-id="c8469-134">바인딩</span><span class="sxs-lookup"><span data-stu-id="c8469-134">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="c8469-135">바인딩 확장명</span><span class="sxs-lookup"><span data-stu-id="c8469-135">Extending Bindings</span></span>](../../../wcf/extending/extending-bindings.md)
- [<span data-ttu-id="c8469-136">사용자 지정 바인딩</span><span class="sxs-lookup"><span data-stu-id="c8469-136">Custom Bindings</span></span>](../../../wcf/extending/custom-bindings.md)
- [\<customBinding>](custombinding.md)
