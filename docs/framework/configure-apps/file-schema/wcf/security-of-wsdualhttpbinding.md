---
title: <wsDualHttpBinding>의 <security>
ms.date: 03/30/2017
ms.assetid: 869c05e7-4ebe-467d-95ab-c8f8de4e6b9e
ms.openlocfilehash: bed7f4ce325e0d5e387e310ca15a3b72ac93f18e
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/22/2019
ms.locfileid: "69936551"
---
# <a name="security-of-wsdualhttpbinding"></a><span data-ttu-id="1e856-102">\<wsDualHttpBinding >의 \<보안 ></span><span class="sxs-lookup"><span data-stu-id="1e856-102">\<security> of \<wsDualHttpBinding></span></span>
<span data-ttu-id="1e856-103">[ \<WsDualHttpBinding >](wsdualhttpbinding.md)의 보안 기능을 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="1e856-103">Defines the security capabilities of the [\<wsDualHttpBinding>](wsdualhttpbinding.md).</span></span>  
  
 <span data-ttu-id="1e856-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="1e856-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="1e856-105">\<bindings></span><span class="sxs-lookup"><span data-stu-id="1e856-105">\<bindings></span></span>  
<span data-ttu-id="1e856-106">\<wsDualHttpBinding></span><span class="sxs-lookup"><span data-stu-id="1e856-106">\<wsDualHttpBinding></span></span>  
<span data-ttu-id="1e856-107">\<binding></span><span class="sxs-lookup"><span data-stu-id="1e856-107">\<binding></span></span>  
<span data-ttu-id="1e856-108">\<security></span><span class="sxs-lookup"><span data-stu-id="1e856-108">\<security></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1e856-109">구문</span><span class="sxs-lookup"><span data-stu-id="1e856-109">Syntax</span></span>  
  
```xml  
<security mode="Message/None">
  <message algorithmSuite="Basic128/Basic192/Basic256/Basic128Rsa15/Basic256Rsa15/TripleDes/TripleDesRsa15/Basic128Sha256/Basic192Sha256/TripleDesSha256/Basic128Sha256Rsa15/Basic192Sha256Rsa15/Basic256Sha256Rsa15/TripleDesSha256Rsa15"
           clientCredentialType="Certificate/IssuedToken/None/UserName/Windows"
           negotiateServiceCredential="Boolean"/>
</security>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="1e856-110">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="1e856-110">Attributes and Elements</span></span>  
 <span data-ttu-id="1e856-111">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="1e856-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="1e856-112">특성</span><span class="sxs-lookup"><span data-stu-id="1e856-112">Attributes</span></span>  
  
|<span data-ttu-id="1e856-113">특성</span><span class="sxs-lookup"><span data-stu-id="1e856-113">Attribute</span></span>|<span data-ttu-id="1e856-114">Description</span><span class="sxs-lookup"><span data-stu-id="1e856-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="1e856-115">모드</span><span class="sxs-lookup"><span data-stu-id="1e856-115">mode</span></span>|<span data-ttu-id="1e856-116">필드.</span><span class="sxs-lookup"><span data-stu-id="1e856-116">-   Optional.</span></span> <span data-ttu-id="1e856-117">적용되는 보안 형식을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="1e856-117">Specifies the type of security that is applied.</span></span> <span data-ttu-id="1e856-118">기본값은 `Message`입니다.</span><span class="sxs-lookup"><span data-stu-id="1e856-118">The default value is `Message`.</span></span> <span data-ttu-id="1e856-119">이 특성은 <xref:System.ServiceModel.WSDualHttpSecurityMode> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="1e856-119">This attribute is of type <xref:System.ServiceModel.WSDualHttpSecurityMode>.</span></span>|  
  
## <a name="mode-attribute"></a><span data-ttu-id="1e856-120">Mode 특성</span><span class="sxs-lookup"><span data-stu-id="1e856-120">Mode Attribute</span></span>  
  
|<span data-ttu-id="1e856-121">값</span><span class="sxs-lookup"><span data-stu-id="1e856-121">Value</span></span>|<span data-ttu-id="1e856-122">설명</span><span class="sxs-lookup"><span data-stu-id="1e856-122">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="1e856-123">없음</span><span class="sxs-lookup"><span data-stu-id="1e856-123">None</span></span>|<span data-ttu-id="1e856-124">보안이 해제되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1e856-124">Security is disabled.</span></span>|  
|<span data-ttu-id="1e856-125">메시지</span><span class="sxs-lookup"><span data-stu-id="1e856-125">Message</span></span>|<span data-ttu-id="1e856-126">SOAP 메시지 보안을 사용하여 보안이 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="1e856-126">Security is provided using SOAP message security.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="1e856-127">자식 요소</span><span class="sxs-lookup"><span data-stu-id="1e856-127">Child Elements</span></span>  
  
|<span data-ttu-id="1e856-128">요소</span><span class="sxs-lookup"><span data-stu-id="1e856-128">Element</span></span>|<span data-ttu-id="1e856-129">Description</span><span class="sxs-lookup"><span data-stu-id="1e856-129">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="1e856-130">\<message></span><span class="sxs-lookup"><span data-stu-id="1e856-130">\<message></span></span>](message-of-wsdualhttpbinding.md)|<span data-ttu-id="1e856-131">메시지 수준 보안 설정을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="1e856-131">Defines the settings for the message-level security.</span></span> <span data-ttu-id="1e856-132">이 요소는 <xref:System.ServiceModel.MessageSecurityOverHttp> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="1e856-132">This element is of type <xref:System.ServiceModel.MessageSecurityOverHttp>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="1e856-133">부모 요소</span><span class="sxs-lookup"><span data-stu-id="1e856-133">Parent Elements</span></span>  
  
|<span data-ttu-id="1e856-134">요소</span><span class="sxs-lookup"><span data-stu-id="1e856-134">Element</span></span>|<span data-ttu-id="1e856-135">설명</span><span class="sxs-lookup"><span data-stu-id="1e856-135">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="1e856-136">\<binding></span><span class="sxs-lookup"><span data-stu-id="1e856-136">\<binding></span></span>](../../../misc/binding.md)|<span data-ttu-id="1e856-137">WsDualHttpBinding >의 모든 바인딩 기능을 [ \<](wsdualhttpbinding.md)정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="1e856-137">Defines all binding capabilities of the [\<wsDualHttpBinding>](wsdualhttpbinding.md).</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1e856-138">설명</span><span class="sxs-lookup"><span data-stu-id="1e856-138">Remarks</span></span>  
 <span data-ttu-id="1e856-139">이중 바인딩은 클라이언트의 IP 주소를 서비스에 노출합니다.</span><span class="sxs-lookup"><span data-stu-id="1e856-139">A dual binding exposes the IP address of the client to the service.</span></span> <span data-ttu-id="1e856-140">클라이언트는 보안을 사용하여 신뢰하는 서비스에만 연결해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1e856-140">The client should use security to ensure that it only connects to services it trusts.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1e856-141">참고자료</span><span class="sxs-lookup"><span data-stu-id="1e856-141">See also</span></span>

- <xref:System.ServiceModel.WSDualHttpSecurity>
- <xref:System.ServiceModel.BasicHttpSecurity>
- [<span data-ttu-id="1e856-142">서비스 및 클라이언트에 보안 설정</span><span class="sxs-lookup"><span data-stu-id="1e856-142">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="1e856-143">바인딩</span><span class="sxs-lookup"><span data-stu-id="1e856-143">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="1e856-144">시스템 제공 바인딩 구성</span><span class="sxs-lookup"><span data-stu-id="1e856-144">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="1e856-145">바인딩을 사용하여 서비스 및 클라이언트 구성</span><span class="sxs-lookup"><span data-stu-id="1e856-145">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="1e856-146">\<binding></span><span class="sxs-lookup"><span data-stu-id="1e856-146">\<binding></span></span>](../../../misc/binding.md)
