---
title: <peerTransport>의 <transport>
ms.date: 03/30/2017
ms.assetid: d7116240-845c-4b6f-b203-262de6b597ef
ms.openlocfilehash: 3b2c7716727f58abb81bf4d58b13189ac170cf7c
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/06/2020
ms.locfileid: "70399298"
---
# <a name="transport-of-peertransport"></a><span data-ttu-id="9a891-102">\<peerTransport>의 \<transport></span><span class="sxs-lookup"><span data-stu-id="9a891-102">\<transport> of \<peerTransport></span></span>
<span data-ttu-id="9a891-103">이 바인딩으로 구성된 피어에서 보낸 보안 메시지의 전송 형식을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="9a891-103">Specifies the transport type for secured messages sent by peers configured with this binding.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<customBinding>**](custombinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<peerTransport>**](peertransport.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<security>**](security-of-peertransport.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<transport>**  
  
## <a name="syntax"></a><span data-ttu-id="9a891-104">구문</span><span class="sxs-lookup"><span data-stu-id="9a891-104">Syntax</span></span>  
  
```xml  
<security>
  <transport credentialType="Certificate/Password" />
</security>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="9a891-105">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="9a891-105">Attributes and Elements</span></span>  
 <span data-ttu-id="9a891-106">다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="9a891-106">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="9a891-107">특성</span><span class="sxs-lookup"><span data-stu-id="9a891-107">Attributes</span></span>  
  
|<span data-ttu-id="9a891-108">attribute</span><span class="sxs-lookup"><span data-stu-id="9a891-108">Attribute</span></span>|<span data-ttu-id="9a891-109">Description</span><span class="sxs-lookup"><span data-stu-id="9a891-109">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="9a891-110">credentialType</span><span class="sxs-lookup"><span data-stu-id="9a891-110">credentialType</span></span>|<span data-ttu-id="9a891-111">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="9a891-111">Optional.</span></span> <span data-ttu-id="9a891-112">피어 전송을 통해 보내는 메시지를 확인할 때 사용되는 자격 증명 형식을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="9a891-112">Specifies the type of credentials used to verify messages sent with the peer transport.</span></span> <span data-ttu-id="9a891-113">이 특성은 <xref:System.ServiceModel.PeerTransportCredentialType> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="9a891-113">This attribute is of type <xref:System.ServiceModel.PeerTransportCredentialType>.</span></span>|  
  
## <a name="credentialtype-attribute"></a><span data-ttu-id="9a891-114">credentialType 특성</span><span class="sxs-lookup"><span data-stu-id="9a891-114">credentialType Attribute</span></span>  
  
|<span data-ttu-id="9a891-115">값</span><span class="sxs-lookup"><span data-stu-id="9a891-115">Value</span></span>|<span data-ttu-id="9a891-116">Description</span><span class="sxs-lookup"><span data-stu-id="9a891-116">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="9a891-117">인증서</span><span class="sxs-lookup"><span data-stu-id="9a891-117">Certificate</span></span>|<span data-ttu-id="9a891-118">피어 채널 전송을 인증하려면 X509 인증서가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="9a891-118">Authentication of the peer channel transport requires an X509 certificate.</span></span>|  
|<span data-ttu-id="9a891-119">암호</span><span class="sxs-lookup"><span data-stu-id="9a891-119">Password</span></span>|<span data-ttu-id="9a891-120">피어 채널 전송을 인증하려면 올바른 암호가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="9a891-120">Authentication of the peer channel transport requires a correct password.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="9a891-121">자식 요소</span><span class="sxs-lookup"><span data-stu-id="9a891-121">Child Elements</span></span>  
 <span data-ttu-id="9a891-122">None</span><span class="sxs-lookup"><span data-stu-id="9a891-122">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="9a891-123">부모 요소</span><span class="sxs-lookup"><span data-stu-id="9a891-123">Parent Elements</span></span>  
  
|<span data-ttu-id="9a891-124">요소</span><span class="sxs-lookup"><span data-stu-id="9a891-124">Element</span></span>|<span data-ttu-id="9a891-125">Description</span><span class="sxs-lookup"><span data-stu-id="9a891-125">Description</span></span>|  
|-------------|-----------------|  
|[\<security>](security-of-peertransport.md)|<span data-ttu-id="9a891-126">피어 전송의 보안 설정을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="9a891-126">Defines the security settings for a peer transport.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9a891-127">설명</span><span class="sxs-lookup"><span data-stu-id="9a891-127">Remarks</span></span>  
 <span data-ttu-id="9a891-128">이 요소는의 mode 특성이 또는로 설정 된 경우에만 설정 됩니다 [\<security>](security-of-peertransport.md) `Transport` `TransportWithMessageCredential` .</span><span class="sxs-lookup"><span data-stu-id="9a891-128">This element is set only if the mode attribute of [\<security>](security-of-peertransport.md) is set to `Transport` or `TransportWithMessageCredential`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9a891-129">참고 항목</span><span class="sxs-lookup"><span data-stu-id="9a891-129">See also</span></span>

- <xref:System.ServiceModel.Configuration.PeerTransportSecurityElement>
- <xref:System.ServiceModel.PeerSecuritySettings.Transport%2A>
- <xref:System.ServiceModel.PeerTransportSecuritySettings>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [<span data-ttu-id="9a891-130">전송 보안</span><span class="sxs-lookup"><span data-stu-id="9a891-130">Transport Security</span></span>](../../../wcf/feature-details/transport-security.md)
- [<span data-ttu-id="9a891-131">전송</span><span class="sxs-lookup"><span data-stu-id="9a891-131">Transports</span></span>](../../../wcf/feature-details/transports.md)
- [<span data-ttu-id="9a891-132">전송 선택</span><span class="sxs-lookup"><span data-stu-id="9a891-132">Choosing a Transport</span></span>](../../../wcf/feature-details/choosing-a-transport.md)
- [<span data-ttu-id="9a891-133">바인딩</span><span class="sxs-lookup"><span data-stu-id="9a891-133">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="9a891-134">바인딩 확장명</span><span class="sxs-lookup"><span data-stu-id="9a891-134">Extending Bindings</span></span>](../../../wcf/extending/extending-bindings.md)
- [<span data-ttu-id="9a891-135">사용자 지정 바인딩</span><span class="sxs-lookup"><span data-stu-id="9a891-135">Custom Bindings</span></span>](../../../wcf/extending/custom-bindings.md)
- [\<customBinding>](custombinding.md)
