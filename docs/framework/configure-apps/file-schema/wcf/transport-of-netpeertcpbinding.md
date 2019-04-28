---
title: <netPeerTcpBinding>의 <transport>
ms.date: 03/30/2017
ms.assetid: c44d86d2-1160-44d7-9c7a-297b12eccc7f
ms.openlocfilehash: 157637615abafbd5913e4d90b702bb0224d5f121
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61788325"
---
# <a name="transport-of-netpeertcpbinding"></a><span data-ttu-id="06251-102">\<전송 >의 \<netPeerTcpBinding ></span><span class="sxs-lookup"><span data-stu-id="06251-102">\<transport> of \<netPeerTcpBinding></span></span>
<span data-ttu-id="06251-103">전송 수준 보안에 대 한 설정을 사용 하는 경우 지정 된 [ \<netPeerTcpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/netpeertcpbinding.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="06251-103">Specifies settings for transport level security when using the [\<netPeerTcpBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/netpeertcpbinding.md).</span></span>  
  
 <span data-ttu-id="06251-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="06251-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="06251-105">\<bindings></span><span class="sxs-lookup"><span data-stu-id="06251-105">\<bindings></span></span>  
<span data-ttu-id="06251-106">\<netPeerTcpBinding></span><span class="sxs-lookup"><span data-stu-id="06251-106">\<netPeerTcpBinding></span></span>  
<span data-ttu-id="06251-107">\<binding></span><span class="sxs-lookup"><span data-stu-id="06251-107">\<binding></span></span>  
<span data-ttu-id="06251-108">\<security></span><span class="sxs-lookup"><span data-stu-id="06251-108">\<security></span></span>  
<span data-ttu-id="06251-109">\<transport></span><span class="sxs-lookup"><span data-stu-id="06251-109">\<transport></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="06251-110">구문</span><span class="sxs-lookup"><span data-stu-id="06251-110">Syntax</span></span>  
  
```xml  
<netPeerTcpBinding>
  <binding>
    <security>
      <transport credentialType="Certificate/Password" />
    </security>
  </binding>
</netPeerTcpBinding>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="06251-111">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="06251-111">Attributes and Elements</span></span>  
 <span data-ttu-id="06251-112">다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="06251-112">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="06251-113">특성</span><span class="sxs-lookup"><span data-stu-id="06251-113">Attributes</span></span>  
  
|<span data-ttu-id="06251-114">특성</span><span class="sxs-lookup"><span data-stu-id="06251-114">Attribute</span></span>|<span data-ttu-id="06251-115">설명</span><span class="sxs-lookup"><span data-stu-id="06251-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="06251-116">credentialType</span><span class="sxs-lookup"><span data-stu-id="06251-116">credentialType</span></span>|<span data-ttu-id="06251-117">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="06251-117">Optional.</span></span> <span data-ttu-id="06251-118">피어 전송을 통해 보내는 메시지를 확인할 때 사용되는 자격 증명 형식을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="06251-118">Specifies the type of credentials used to verify messages sent with the peer transport.</span></span> <span data-ttu-id="06251-119">이 특성은 <xref:System.ServiceModel.PeerTransportCredentialType> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="06251-119">This attribute is of type <xref:System.ServiceModel.PeerTransportCredentialType>.</span></span>|  
  
## <a name="credentialtype-attribute"></a><span data-ttu-id="06251-120">credentialType 특성</span><span class="sxs-lookup"><span data-stu-id="06251-120">credentialType Attribute</span></span>  
  
|<span data-ttu-id="06251-121">값</span><span class="sxs-lookup"><span data-stu-id="06251-121">Value</span></span>|<span data-ttu-id="06251-122">설명</span><span class="sxs-lookup"><span data-stu-id="06251-122">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="06251-123">인증서</span><span class="sxs-lookup"><span data-stu-id="06251-123">Certificate</span></span>|<span data-ttu-id="06251-124">피어 채널 전송을 인증하려면 X509 인증서가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="06251-124">Authentication of the peer channel transport requires an X509 certificate.</span></span>|  
|<span data-ttu-id="06251-125">암호</span><span class="sxs-lookup"><span data-stu-id="06251-125">Password</span></span>|<span data-ttu-id="06251-126">피어 채널 전송을 인증하려면 올바른 암호가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="06251-126">Authentication of the peer channel transport requires a correct password.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="06251-127">자식 요소</span><span class="sxs-lookup"><span data-stu-id="06251-127">Child Elements</span></span>  
 <span data-ttu-id="06251-128">없음</span><span class="sxs-lookup"><span data-stu-id="06251-128">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="06251-129">부모 요소</span><span class="sxs-lookup"><span data-stu-id="06251-129">Parent Elements</span></span>  
  
|<span data-ttu-id="06251-130">요소</span><span class="sxs-lookup"><span data-stu-id="06251-130">Element</span></span>|<span data-ttu-id="06251-131">설명</span><span class="sxs-lookup"><span data-stu-id="06251-131">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="06251-132">\<security></span><span class="sxs-lookup"><span data-stu-id="06251-132">\<security></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/security-of-netpeerbinding.md)|<span data-ttu-id="06251-133">에 대 한 보안 설정을 정의 합니다 [ \<netPeerTcpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/netpeertcpbinding.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="06251-133">Defines the security settings for the [\<netPeerTcpBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/netpeertcpbinding.md).</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="06251-134">참고자료</span><span class="sxs-lookup"><span data-stu-id="06251-134">See also</span></span>

- <xref:System.ServiceModel.Configuration.PeerTransportSecurityElement>
- <xref:System.ServiceModel.PeerSecuritySettings.Transport%2A>
- <xref:System.ServiceModel.Configuration.PeerSecurityElement.Transport%2A>
- <xref:System.ServiceModel.PeerTransportSecuritySettings>
- [<span data-ttu-id="06251-135">서비스 및 클라이언트에 보안 설정</span><span class="sxs-lookup"><span data-stu-id="06251-135">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="06251-136">바인딩</span><span class="sxs-lookup"><span data-stu-id="06251-136">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)
- [<span data-ttu-id="06251-137">시스템 제공 바인딩 구성</span><span class="sxs-lookup"><span data-stu-id="06251-137">Configuring System-Provided Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="06251-138">바인딩을 사용하여 서비스 및 클라이언트 구성</span><span class="sxs-lookup"><span data-stu-id="06251-138">Using Bindings to Configure Services and Clients</span></span>](../../../../../docs/framework/wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="06251-139">\<binding></span><span class="sxs-lookup"><span data-stu-id="06251-139">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)
