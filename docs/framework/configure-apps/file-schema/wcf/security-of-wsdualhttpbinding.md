---
description: '다음에 대 한 자세한 정보:: <security><wsDualHttpBinding>'
title: <wsDualHttpBinding>의 <security>
ms.date: 03/30/2017
ms.assetid: 869c05e7-4ebe-467d-95ab-c8f8de4e6b9e
ms.openlocfilehash: 6d2e87912aef6114d7dcb99b82e4a7804317b28a
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99683036"
---
# <a name="security-of-wsdualhttpbinding"></a><span data-ttu-id="a0acf-103">\<wsDualHttpBinding>의 \<security></span><span class="sxs-lookup"><span data-stu-id="a0acf-103">\<security> of \<wsDualHttpBinding></span></span>

<span data-ttu-id="a0acf-104">의 보안 기능을 정의 합니다 [\<wsDualHttpBinding>](wsdualhttpbinding.md) .</span><span class="sxs-lookup"><span data-stu-id="a0acf-104">Defines the security capabilities of the [\<wsDualHttpBinding>](wsdualhttpbinding.md).</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<wsDualHttpBinding>**](wsdualhttpbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<security>**  
  
## <a name="syntax"></a><span data-ttu-id="a0acf-105">구문</span><span class="sxs-lookup"><span data-stu-id="a0acf-105">Syntax</span></span>  
  
```xml  
<security mode="Message/None">
  <message algorithmSuite="Basic128/Basic192/Basic256/Basic128Rsa15/Basic256Rsa15/TripleDes/TripleDesRsa15/Basic128Sha256/Basic192Sha256/TripleDesSha256/Basic128Sha256Rsa15/Basic192Sha256Rsa15/Basic256Sha256Rsa15/TripleDesSha256Rsa15"
           clientCredentialType="Certificate/IssuedToken/None/UserName/Windows"
           negotiateServiceCredential="Boolean"/>
</security>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="a0acf-106">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="a0acf-106">Attributes and Elements</span></span>  

 <span data-ttu-id="a0acf-107">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="a0acf-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="a0acf-108">특성</span><span class="sxs-lookup"><span data-stu-id="a0acf-108">Attributes</span></span>  
  
|<span data-ttu-id="a0acf-109">attribute</span><span class="sxs-lookup"><span data-stu-id="a0acf-109">Attribute</span></span>|<span data-ttu-id="a0acf-110">설명</span><span class="sxs-lookup"><span data-stu-id="a0acf-110">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="a0acf-111">mode</span><span class="sxs-lookup"><span data-stu-id="a0acf-111">mode</span></span>|<span data-ttu-id="a0acf-112">필드.</span><span class="sxs-lookup"><span data-stu-id="a0acf-112">-   Optional.</span></span> <span data-ttu-id="a0acf-113">적용되는 보안 형식을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="a0acf-113">Specifies the type of security that is applied.</span></span> <span data-ttu-id="a0acf-114">기본값은 `Message`입니다.</span><span class="sxs-lookup"><span data-stu-id="a0acf-114">The default value is `Message`.</span></span> <span data-ttu-id="a0acf-115">이 특성은 <xref:System.ServiceModel.WSDualHttpSecurityMode> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="a0acf-115">This attribute is of type <xref:System.ServiceModel.WSDualHttpSecurityMode>.</span></span>|  
  
## <a name="mode-attribute"></a><span data-ttu-id="a0acf-116">Mode 특성</span><span class="sxs-lookup"><span data-stu-id="a0acf-116">Mode Attribute</span></span>  
  
|<span data-ttu-id="a0acf-117">값</span><span class="sxs-lookup"><span data-stu-id="a0acf-117">Value</span></span>|<span data-ttu-id="a0acf-118">설명</span><span class="sxs-lookup"><span data-stu-id="a0acf-118">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="a0acf-119">없음</span><span class="sxs-lookup"><span data-stu-id="a0acf-119">None</span></span>|<span data-ttu-id="a0acf-120">보안이 해제되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a0acf-120">Security is disabled.</span></span>|  
|<span data-ttu-id="a0acf-121">메시지</span><span class="sxs-lookup"><span data-stu-id="a0acf-121">Message</span></span>|<span data-ttu-id="a0acf-122">SOAP 메시지 보안을 사용하여 보안이 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="a0acf-122">Security is provided using SOAP message security.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="a0acf-123">자식 요소</span><span class="sxs-lookup"><span data-stu-id="a0acf-123">Child Elements</span></span>  
  
|<span data-ttu-id="a0acf-124">요소</span><span class="sxs-lookup"><span data-stu-id="a0acf-124">Element</span></span>|<span data-ttu-id="a0acf-125">설명</span><span class="sxs-lookup"><span data-stu-id="a0acf-125">Description</span></span>|  
|-------------|-----------------|  
|[\<message>](message-of-wsdualhttpbinding.md)|<span data-ttu-id="a0acf-126">메시지 수준 보안 설정을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="a0acf-126">Defines the settings for the message-level security.</span></span> <span data-ttu-id="a0acf-127">이 요소는 <xref:System.ServiceModel.MessageSecurityOverHttp> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="a0acf-127">This element is of type <xref:System.ServiceModel.MessageSecurityOverHttp>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="a0acf-128">부모 요소</span><span class="sxs-lookup"><span data-stu-id="a0acf-128">Parent Elements</span></span>  
  
|<span data-ttu-id="a0acf-129">요소</span><span class="sxs-lookup"><span data-stu-id="a0acf-129">Element</span></span>|<span data-ttu-id="a0acf-130">설명</span><span class="sxs-lookup"><span data-stu-id="a0acf-130">Description</span></span>|  
|-------------|-----------------|  
|[\<binding>](bindings.md)|<span data-ttu-id="a0acf-131">의 모든 바인딩 기능을 정의 [\<wsDualHttpBinding>](wsdualhttpbinding.md) 합니다.</span><span class="sxs-lookup"><span data-stu-id="a0acf-131">Defines all binding capabilities of the [\<wsDualHttpBinding>](wsdualhttpbinding.md).</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a0acf-132">설명</span><span class="sxs-lookup"><span data-stu-id="a0acf-132">Remarks</span></span>  

 <span data-ttu-id="a0acf-133">이중 바인딩은 클라이언트의 IP 주소를 서비스에 노출합니다.</span><span class="sxs-lookup"><span data-stu-id="a0acf-133">A dual binding exposes the IP address of the client to the service.</span></span> <span data-ttu-id="a0acf-134">클라이언트는 보안을 사용하여 신뢰하는 서비스에만 연결해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a0acf-134">The client should use security to ensure that it only connects to services it trusts.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a0acf-135">참고 항목</span><span class="sxs-lookup"><span data-stu-id="a0acf-135">See also</span></span>

- <xref:System.ServiceModel.WSDualHttpSecurity>
- <xref:System.ServiceModel.BasicHttpSecurity>
- [<span data-ttu-id="a0acf-136">서비스 및 클라이언트에 보안 설정</span><span class="sxs-lookup"><span data-stu-id="a0acf-136">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="a0acf-137">바인딩</span><span class="sxs-lookup"><span data-stu-id="a0acf-137">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="a0acf-138">시스템 제공 바인딩 구성</span><span class="sxs-lookup"><span data-stu-id="a0acf-138">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="a0acf-139">바인딩을 사용하여 서비스 및 클라이언트 구성</span><span class="sxs-lookup"><span data-stu-id="a0acf-139">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [\<binding>](bindings.md)
