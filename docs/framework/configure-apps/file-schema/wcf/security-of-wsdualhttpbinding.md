---
title: <wsDualHttpBinding>의 <security>
ms.date: 03/30/2017
ms.assetid: 869c05e7-4ebe-467d-95ab-c8f8de4e6b9e
ms.openlocfilehash: 4969c041678bbf3490975bc0ec53507b6cf762bb
ms.sourcegitcommit: 22be09204266253d45ece46f51cc6f080f2b3fd6
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/07/2019
ms.locfileid: "73738612"
---
# <a name="security-of-wsdualhttpbinding"></a><span data-ttu-id="86ec8-102">\<보안 > \<wsDualHttpBinding ></span><span class="sxs-lookup"><span data-stu-id="86ec8-102">\<security> of \<wsDualHttpBinding></span></span>
<span data-ttu-id="86ec8-103">[\<wsDualHttpBinding >](wsdualhttpbinding.md)의 보안 기능을 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="86ec8-103">Defines the security capabilities of the [\<wsDualHttpBinding>](wsdualhttpbinding.md).</span></span>  
  
<span data-ttu-id="86ec8-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="86ec8-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="86ec8-105">[ **\<system serviceModel >** ](system-servicemodel.md) &nbsp; &nbsp; </span><span class="sxs-lookup"><span data-stu-id="86ec8-105">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="86ec8-106">&nbsp;&nbsp;&nbsp;&nbsp;\<[**바인딩**](bindings.md) ></span><span class="sxs-lookup"><span data-stu-id="86ec8-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\</span></span>
<span data-ttu-id="86ec8-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<wsDualHttpBinding >** ](wsdualhttpbinding.md)</span><span class="sxs-lookup"><span data-stu-id="86ec8-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<wsDualHttpBinding>**](wsdualhttpbinding.md)</span></span>\
<span data-ttu-id="86ec8-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<바인딩 >** </span><span class="sxs-lookup"><span data-stu-id="86ec8-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**</span></span>\
<span data-ttu-id="86ec8-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<**보안 >**</span><span class="sxs-lookup"><span data-stu-id="86ec8-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<security>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="86ec8-110">구문</span><span class="sxs-lookup"><span data-stu-id="86ec8-110">Syntax</span></span>  
  
```xml  
<security mode="Message/None">
  <message algorithmSuite="Basic128/Basic192/Basic256/Basic128Rsa15/Basic256Rsa15/TripleDes/TripleDesRsa15/Basic128Sha256/Basic192Sha256/TripleDesSha256/Basic128Sha256Rsa15/Basic192Sha256Rsa15/Basic256Sha256Rsa15/TripleDesSha256Rsa15"
           clientCredentialType="Certificate/IssuedToken/None/UserName/Windows"
           negotiateServiceCredential="Boolean"/>
</security>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="86ec8-111">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="86ec8-111">Attributes and Elements</span></span>  
 <span data-ttu-id="86ec8-112">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="86ec8-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="86ec8-113">특성</span><span class="sxs-lookup"><span data-stu-id="86ec8-113">Attributes</span></span>  
  
|<span data-ttu-id="86ec8-114">특성</span><span class="sxs-lookup"><span data-stu-id="86ec8-114">Attribute</span></span>|<span data-ttu-id="86ec8-115">설명</span><span class="sxs-lookup"><span data-stu-id="86ec8-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="86ec8-116">모드</span><span class="sxs-lookup"><span data-stu-id="86ec8-116">mode</span></span>|<span data-ttu-id="86ec8-117">필드.</span><span class="sxs-lookup"><span data-stu-id="86ec8-117">-   Optional.</span></span> <span data-ttu-id="86ec8-118">적용 되는 보안 유형을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="86ec8-118">Specifies the type of security that is applied.</span></span> <span data-ttu-id="86ec8-119">기본값은 `Message`여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="86ec8-119">The default value is `Message`.</span></span> <span data-ttu-id="86ec8-120">이 특성은 <xref:System.ServiceModel.WSDualHttpSecurityMode> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="86ec8-120">This attribute is of type <xref:System.ServiceModel.WSDualHttpSecurityMode>.</span></span>|  
  
## <a name="mode-attribute"></a><span data-ttu-id="86ec8-121">Mode 특성</span><span class="sxs-lookup"><span data-stu-id="86ec8-121">Mode Attribute</span></span>  
  
|<span data-ttu-id="86ec8-122">값</span><span class="sxs-lookup"><span data-stu-id="86ec8-122">Value</span></span>|<span data-ttu-id="86ec8-123">설명</span><span class="sxs-lookup"><span data-stu-id="86ec8-123">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="86ec8-124">없음</span><span class="sxs-lookup"><span data-stu-id="86ec8-124">None</span></span>|<span data-ttu-id="86ec8-125">보안이 사용 하지 않도록 설정 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="86ec8-125">Security is disabled.</span></span>|  
|<span data-ttu-id="86ec8-126">메시지</span><span class="sxs-lookup"><span data-stu-id="86ec8-126">Message</span></span>|<span data-ttu-id="86ec8-127">SOAP 메시지 보안을 사용하여 보안이 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="86ec8-127">Security is provided using SOAP message security.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="86ec8-128">자식 요소</span><span class="sxs-lookup"><span data-stu-id="86ec8-128">Child Elements</span></span>  
  
|<span data-ttu-id="86ec8-129">요소</span><span class="sxs-lookup"><span data-stu-id="86ec8-129">Element</span></span>|<span data-ttu-id="86ec8-130">설명</span><span class="sxs-lookup"><span data-stu-id="86ec8-130">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="86ec8-131">\<message ></span><span class="sxs-lookup"><span data-stu-id="86ec8-131">\<message></span></span>](message-of-wsdualhttpbinding.md)|<span data-ttu-id="86ec8-132">메시지 수준 보안 설정을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="86ec8-132">Defines the settings for the message-level security.</span></span> <span data-ttu-id="86ec8-133">이 요소는 <xref:System.ServiceModel.MessageSecurityOverHttp> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="86ec8-133">This element is of type <xref:System.ServiceModel.MessageSecurityOverHttp>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="86ec8-134">부모 요소</span><span class="sxs-lookup"><span data-stu-id="86ec8-134">Parent Elements</span></span>  
  
|<span data-ttu-id="86ec8-135">요소</span><span class="sxs-lookup"><span data-stu-id="86ec8-135">Element</span></span>|<span data-ttu-id="86ec8-136">설명</span><span class="sxs-lookup"><span data-stu-id="86ec8-136">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="86ec8-137">\<binding ></span><span class="sxs-lookup"><span data-stu-id="86ec8-137">\<binding></span></span>](bindings.md)|<span data-ttu-id="86ec8-138">[\<wsDualHttpBinding >](wsdualhttpbinding.md)의 모든 바인딩 기능을 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="86ec8-138">Defines all binding capabilities of the [\<wsDualHttpBinding>](wsdualhttpbinding.md).</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="86ec8-139">주의</span><span class="sxs-lookup"><span data-stu-id="86ec8-139">Remarks</span></span>  
 <span data-ttu-id="86ec8-140">이중 바인딩은 클라이언트의 IP 주소를 서비스에 노출 합니다.</span><span class="sxs-lookup"><span data-stu-id="86ec8-140">A dual binding exposes the IP address of the client to the service.</span></span> <span data-ttu-id="86ec8-141">클라이언트는 보안을 사용 하 여 신뢰 하는 서비스에만 연결 되도록 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="86ec8-141">The client should use security to ensure that it only connects to services it trusts.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="86ec8-142">참조</span><span class="sxs-lookup"><span data-stu-id="86ec8-142">See also</span></span>

- <xref:System.ServiceModel.WSDualHttpSecurity>
- <xref:System.ServiceModel.BasicHttpSecurity>
- [<span data-ttu-id="86ec8-143">서비스 및 클라이언트에 보안 설정</span><span class="sxs-lookup"><span data-stu-id="86ec8-143">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="86ec8-144">바인딩</span><span class="sxs-lookup"><span data-stu-id="86ec8-144">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="86ec8-145">시스템 제공 바인딩 구성</span><span class="sxs-lookup"><span data-stu-id="86ec8-145">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="86ec8-146">바인딩을 사용하여 서비스 및 클라이언트 구성</span><span class="sxs-lookup"><span data-stu-id="86ec8-146">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="86ec8-147">\<binding ></span><span class="sxs-lookup"><span data-stu-id="86ec8-147">\<binding></span></span>](bindings.md)
