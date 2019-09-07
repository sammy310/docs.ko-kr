---
title: <wsDualHttpBinding>의 <security>
ms.date: 03/30/2017
ms.assetid: 869c05e7-4ebe-467d-95ab-c8f8de4e6b9e
ms.openlocfilehash: b6a1c952b1ae65c8fb6f17237b5c15f3a8d4844a
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/06/2019
ms.locfileid: "70399742"
---
# <a name="security-of-wsdualhttpbinding"></a><span data-ttu-id="3fcac-102">\<wsDualHttpBinding >의 \<보안 ></span><span class="sxs-lookup"><span data-stu-id="3fcac-102">\<security> of \<wsDualHttpBinding></span></span>
<span data-ttu-id="3fcac-103">[ \<WsDualHttpBinding >](wsdualhttpbinding.md)의 보안 기능을 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="3fcac-103">Defines the security capabilities of the [\<wsDualHttpBinding>](wsdualhttpbinding.md).</span></span>  
  
<span data-ttu-id="3fcac-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="3fcac-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="3fcac-105">&nbsp;&nbsp;[ **\<System.servicemodel >** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="3fcac-105">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="3fcac-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<바인딩 >** ](bindings.md)</span><span class="sxs-lookup"><span data-stu-id="3fcac-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)</span></span>\
<span data-ttu-id="3fcac-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<wsDualHttpBinding >** ](wsdualhttpbinding.md)</span><span class="sxs-lookup"><span data-stu-id="3fcac-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<wsDualHttpBinding>**](wsdualhttpbinding.md)</span></span>\
<span data-ttu-id="3fcac-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<바인딩 >** </span><span class="sxs-lookup"><span data-stu-id="3fcac-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**</span></span>\
<span data-ttu-id="3fcac-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<보안 >**</span><span class="sxs-lookup"><span data-stu-id="3fcac-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<security>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3fcac-110">구문</span><span class="sxs-lookup"><span data-stu-id="3fcac-110">Syntax</span></span>  
  
```xml  
<security mode="Message/None">
  <message algorithmSuite="Basic128/Basic192/Basic256/Basic128Rsa15/Basic256Rsa15/TripleDes/TripleDesRsa15/Basic128Sha256/Basic192Sha256/TripleDesSha256/Basic128Sha256Rsa15/Basic192Sha256Rsa15/Basic256Sha256Rsa15/TripleDesSha256Rsa15"
           clientCredentialType="Certificate/IssuedToken/None/UserName/Windows"
           negotiateServiceCredential="Boolean"/>
</security>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="3fcac-111">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="3fcac-111">Attributes and Elements</span></span>  
 <span data-ttu-id="3fcac-112">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="3fcac-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="3fcac-113">특성</span><span class="sxs-lookup"><span data-stu-id="3fcac-113">Attributes</span></span>  
  
|<span data-ttu-id="3fcac-114">특성</span><span class="sxs-lookup"><span data-stu-id="3fcac-114">Attribute</span></span>|<span data-ttu-id="3fcac-115">Description</span><span class="sxs-lookup"><span data-stu-id="3fcac-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="3fcac-116">모드</span><span class="sxs-lookup"><span data-stu-id="3fcac-116">mode</span></span>|<span data-ttu-id="3fcac-117">필드.</span><span class="sxs-lookup"><span data-stu-id="3fcac-117">-   Optional.</span></span> <span data-ttu-id="3fcac-118">적용되는 보안 형식을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="3fcac-118">Specifies the type of security that is applied.</span></span> <span data-ttu-id="3fcac-119">기본값은 `Message`입니다.</span><span class="sxs-lookup"><span data-stu-id="3fcac-119">The default value is `Message`.</span></span> <span data-ttu-id="3fcac-120">이 특성은 <xref:System.ServiceModel.WSDualHttpSecurityMode> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="3fcac-120">This attribute is of type <xref:System.ServiceModel.WSDualHttpSecurityMode>.</span></span>|  
  
## <a name="mode-attribute"></a><span data-ttu-id="3fcac-121">Mode 특성</span><span class="sxs-lookup"><span data-stu-id="3fcac-121">Mode Attribute</span></span>  
  
|<span data-ttu-id="3fcac-122">값</span><span class="sxs-lookup"><span data-stu-id="3fcac-122">Value</span></span>|<span data-ttu-id="3fcac-123">설명</span><span class="sxs-lookup"><span data-stu-id="3fcac-123">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="3fcac-124">없음</span><span class="sxs-lookup"><span data-stu-id="3fcac-124">None</span></span>|<span data-ttu-id="3fcac-125">보안이 해제되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3fcac-125">Security is disabled.</span></span>|  
|<span data-ttu-id="3fcac-126">메시지</span><span class="sxs-lookup"><span data-stu-id="3fcac-126">Message</span></span>|<span data-ttu-id="3fcac-127">SOAP 메시지 보안을 사용하여 보안이 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="3fcac-127">Security is provided using SOAP message security.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="3fcac-128">자식 요소</span><span class="sxs-lookup"><span data-stu-id="3fcac-128">Child Elements</span></span>  
  
|<span data-ttu-id="3fcac-129">요소</span><span class="sxs-lookup"><span data-stu-id="3fcac-129">Element</span></span>|<span data-ttu-id="3fcac-130">설명</span><span class="sxs-lookup"><span data-stu-id="3fcac-130">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="3fcac-131">\<message></span><span class="sxs-lookup"><span data-stu-id="3fcac-131">\<message></span></span>](message-of-wsdualhttpbinding.md)|<span data-ttu-id="3fcac-132">메시지 수준 보안 설정을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="3fcac-132">Defines the settings for the message-level security.</span></span> <span data-ttu-id="3fcac-133">이 요소는 <xref:System.ServiceModel.MessageSecurityOverHttp> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="3fcac-133">This element is of type <xref:System.ServiceModel.MessageSecurityOverHttp>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="3fcac-134">부모 요소</span><span class="sxs-lookup"><span data-stu-id="3fcac-134">Parent Elements</span></span>  
  
|<span data-ttu-id="3fcac-135">요소</span><span class="sxs-lookup"><span data-stu-id="3fcac-135">Element</span></span>|<span data-ttu-id="3fcac-136">설명</span><span class="sxs-lookup"><span data-stu-id="3fcac-136">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="3fcac-137">\<binding></span><span class="sxs-lookup"><span data-stu-id="3fcac-137">\<binding></span></span>](../../../misc/binding.md)|<span data-ttu-id="3fcac-138">WsDualHttpBinding >의 모든 바인딩 기능을 [ \<](wsdualhttpbinding.md)정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="3fcac-138">Defines all binding capabilities of the [\<wsDualHttpBinding>](wsdualhttpbinding.md).</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3fcac-139">설명</span><span class="sxs-lookup"><span data-stu-id="3fcac-139">Remarks</span></span>  
 <span data-ttu-id="3fcac-140">이중 바인딩은 클라이언트의 IP 주소를 서비스에 노출합니다.</span><span class="sxs-lookup"><span data-stu-id="3fcac-140">A dual binding exposes the IP address of the client to the service.</span></span> <span data-ttu-id="3fcac-141">클라이언트는 보안을 사용하여 신뢰하는 서비스에만 연결해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3fcac-141">The client should use security to ensure that it only connects to services it trusts.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3fcac-142">참고자료</span><span class="sxs-lookup"><span data-stu-id="3fcac-142">See also</span></span>

- <xref:System.ServiceModel.WSDualHttpSecurity>
- <xref:System.ServiceModel.BasicHttpSecurity>
- [<span data-ttu-id="3fcac-143">서비스 및 클라이언트에 보안 설정</span><span class="sxs-lookup"><span data-stu-id="3fcac-143">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="3fcac-144">바인딩</span><span class="sxs-lookup"><span data-stu-id="3fcac-144">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="3fcac-145">시스템 제공 바인딩 구성</span><span class="sxs-lookup"><span data-stu-id="3fcac-145">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="3fcac-146">바인딩을 사용하여 서비스 및 클라이언트 구성</span><span class="sxs-lookup"><span data-stu-id="3fcac-146">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="3fcac-147">\<binding></span><span class="sxs-lookup"><span data-stu-id="3fcac-147">\<binding></span></span>](../../../misc/binding.md)
