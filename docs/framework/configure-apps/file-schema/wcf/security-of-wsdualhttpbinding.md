---
title: <wsDualHttpBinding>의 <security>
ms.date: 03/30/2017
ms.assetid: 869c05e7-4ebe-467d-95ab-c8f8de4e6b9e
ms.openlocfilehash: 4969c041678bbf3490975bc0ec53507b6cf762bb
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/06/2020
ms.locfileid: "73738612"
---
# <a name="security-of-wsdualhttpbinding"></a><span data-ttu-id="ca7b2-102">\<wsDualHttpBinding>의 \<security></span><span class="sxs-lookup"><span data-stu-id="ca7b2-102">\<security> of \<wsDualHttpBinding></span></span>
<span data-ttu-id="ca7b2-103">의 보안 기능을 정의 합니다 [\<wsDualHttpBinding>](wsdualhttpbinding.md) .</span><span class="sxs-lookup"><span data-stu-id="ca7b2-103">Defines the security capabilities of the [\<wsDualHttpBinding>](wsdualhttpbinding.md).</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<wsDualHttpBinding>**](wsdualhttpbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<security>**  
  
## <a name="syntax"></a><span data-ttu-id="ca7b2-104">구문</span><span class="sxs-lookup"><span data-stu-id="ca7b2-104">Syntax</span></span>  
  
```xml  
<security mode="Message/None">
  <message algorithmSuite="Basic128/Basic192/Basic256/Basic128Rsa15/Basic256Rsa15/TripleDes/TripleDesRsa15/Basic128Sha256/Basic192Sha256/TripleDesSha256/Basic128Sha256Rsa15/Basic192Sha256Rsa15/Basic256Sha256Rsa15/TripleDesSha256Rsa15"
           clientCredentialType="Certificate/IssuedToken/None/UserName/Windows"
           negotiateServiceCredential="Boolean"/>
</security>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="ca7b2-105">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="ca7b2-105">Attributes and Elements</span></span>  
 <span data-ttu-id="ca7b2-106">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="ca7b2-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="ca7b2-107">특성</span><span class="sxs-lookup"><span data-stu-id="ca7b2-107">Attributes</span></span>  
  
|<span data-ttu-id="ca7b2-108">attribute</span><span class="sxs-lookup"><span data-stu-id="ca7b2-108">Attribute</span></span>|<span data-ttu-id="ca7b2-109">Description</span><span class="sxs-lookup"><span data-stu-id="ca7b2-109">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="ca7b2-110">mode</span><span class="sxs-lookup"><span data-stu-id="ca7b2-110">mode</span></span>|<span data-ttu-id="ca7b2-111">필드.</span><span class="sxs-lookup"><span data-stu-id="ca7b2-111">-   Optional.</span></span> <span data-ttu-id="ca7b2-112">적용되는 보안 형식을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="ca7b2-112">Specifies the type of security that is applied.</span></span> <span data-ttu-id="ca7b2-113">기본값은 `Message`입니다.</span><span class="sxs-lookup"><span data-stu-id="ca7b2-113">The default value is `Message`.</span></span> <span data-ttu-id="ca7b2-114">이 특성은 <xref:System.ServiceModel.WSDualHttpSecurityMode> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="ca7b2-114">This attribute is of type <xref:System.ServiceModel.WSDualHttpSecurityMode>.</span></span>|  
  
## <a name="mode-attribute"></a><span data-ttu-id="ca7b2-115">Mode 특성</span><span class="sxs-lookup"><span data-stu-id="ca7b2-115">Mode Attribute</span></span>  
  
|<span data-ttu-id="ca7b2-116">값</span><span class="sxs-lookup"><span data-stu-id="ca7b2-116">Value</span></span>|<span data-ttu-id="ca7b2-117">Description</span><span class="sxs-lookup"><span data-stu-id="ca7b2-117">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="ca7b2-118">None</span><span class="sxs-lookup"><span data-stu-id="ca7b2-118">None</span></span>|<span data-ttu-id="ca7b2-119">보안이 해제되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ca7b2-119">Security is disabled.</span></span>|  
|<span data-ttu-id="ca7b2-120">메시지</span><span class="sxs-lookup"><span data-stu-id="ca7b2-120">Message</span></span>|<span data-ttu-id="ca7b2-121">SOAP 메시지 보안을 사용하여 보안이 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="ca7b2-121">Security is provided using SOAP message security.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="ca7b2-122">자식 요소</span><span class="sxs-lookup"><span data-stu-id="ca7b2-122">Child Elements</span></span>  
  
|<span data-ttu-id="ca7b2-123">요소</span><span class="sxs-lookup"><span data-stu-id="ca7b2-123">Element</span></span>|<span data-ttu-id="ca7b2-124">Description</span><span class="sxs-lookup"><span data-stu-id="ca7b2-124">Description</span></span>|  
|-------------|-----------------|  
|[\<message>](message-of-wsdualhttpbinding.md)|<span data-ttu-id="ca7b2-125">메시지 수준 보안 설정을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="ca7b2-125">Defines the settings for the message-level security.</span></span> <span data-ttu-id="ca7b2-126">이 요소는 <xref:System.ServiceModel.MessageSecurityOverHttp> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="ca7b2-126">This element is of type <xref:System.ServiceModel.MessageSecurityOverHttp>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="ca7b2-127">부모 요소</span><span class="sxs-lookup"><span data-stu-id="ca7b2-127">Parent Elements</span></span>  
  
|<span data-ttu-id="ca7b2-128">요소</span><span class="sxs-lookup"><span data-stu-id="ca7b2-128">Element</span></span>|<span data-ttu-id="ca7b2-129">Description</span><span class="sxs-lookup"><span data-stu-id="ca7b2-129">Description</span></span>|  
|-------------|-----------------|  
|[\<binding>](bindings.md)|<span data-ttu-id="ca7b2-130">의 모든 바인딩 기능을 정의 [\<wsDualHttpBinding>](wsdualhttpbinding.md) 합니다.</span><span class="sxs-lookup"><span data-stu-id="ca7b2-130">Defines all binding capabilities of the [\<wsDualHttpBinding>](wsdualhttpbinding.md).</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ca7b2-131">설명</span><span class="sxs-lookup"><span data-stu-id="ca7b2-131">Remarks</span></span>  
 <span data-ttu-id="ca7b2-132">이중 바인딩은 클라이언트의 IP 주소를 서비스에 노출합니다.</span><span class="sxs-lookup"><span data-stu-id="ca7b2-132">A dual binding exposes the IP address of the client to the service.</span></span> <span data-ttu-id="ca7b2-133">클라이언트는 보안을 사용하여 신뢰하는 서비스에만 연결해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ca7b2-133">The client should use security to ensure that it only connects to services it trusts.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ca7b2-134">참고 항목</span><span class="sxs-lookup"><span data-stu-id="ca7b2-134">See also</span></span>

- <xref:System.ServiceModel.WSDualHttpSecurity>
- <xref:System.ServiceModel.BasicHttpSecurity>
- [<span data-ttu-id="ca7b2-135">서비스 및 클라이언트에 보안 설정</span><span class="sxs-lookup"><span data-stu-id="ca7b2-135">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="ca7b2-136">바인딩</span><span class="sxs-lookup"><span data-stu-id="ca7b2-136">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="ca7b2-137">시스템 제공 바인딩 구성</span><span class="sxs-lookup"><span data-stu-id="ca7b2-137">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="ca7b2-138">바인딩을 사용하여 서비스 및 클라이언트 구성</span><span class="sxs-lookup"><span data-stu-id="ca7b2-138">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [\<binding>](bindings.md)
