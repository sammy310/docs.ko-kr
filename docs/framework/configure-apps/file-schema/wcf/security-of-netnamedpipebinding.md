---
title: <netNamedPipeBinding>의 <security>
ms.date: 03/30/2017
ms.assetid: bb3cb022-637e-49fd-92e8-6766038affa7
ms.openlocfilehash: 0996a98438dc344d96d640abced52ac99709adbf
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/22/2019
ms.locfileid: "69936683"
---
# <a name="security-of-netnamedpipebinding"></a><span data-ttu-id="596fb-102">\<netNamedPipeBinding >의 \<보안 ></span><span class="sxs-lookup"><span data-stu-id="596fb-102">\<security> of \<netNamedPipeBinding></span></span>
<span data-ttu-id="596fb-103">바인딩에 대한 보안 설정을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="596fb-103">Defines the security settings for a binding.</span></span>  
  
 <span data-ttu-id="596fb-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="596fb-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="596fb-105">\<bindings></span><span class="sxs-lookup"><span data-stu-id="596fb-105">\<bindings></span></span>  
<span data-ttu-id="596fb-106">\<netNamedPipeBinding></span><span class="sxs-lookup"><span data-stu-id="596fb-106">\<netNamedPipeBinding></span></span>  
<span data-ttu-id="596fb-107">\<binding></span><span class="sxs-lookup"><span data-stu-id="596fb-107">\<binding></span></span>  
<span data-ttu-id="596fb-108">\<security></span><span class="sxs-lookup"><span data-stu-id="596fb-108">\<security></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="596fb-109">구문</span><span class="sxs-lookup"><span data-stu-id="596fb-109">Syntax</span></span>  
  
```xml  
<netNamedPipeBinding>
  <binding>
    <security mode="None/Transport">
      <transport protectionLevel="None/Sign/EncryptAndSign" />
    </security>
  </binding>
</netNamedPipeBinding>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="596fb-110">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="596fb-110">Attributes and Elements</span></span>  
 <span data-ttu-id="596fb-111">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="596fb-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="596fb-112">특성</span><span class="sxs-lookup"><span data-stu-id="596fb-112">Attributes</span></span>  
  
|<span data-ttu-id="596fb-113">특성</span><span class="sxs-lookup"><span data-stu-id="596fb-113">Attribute</span></span>|<span data-ttu-id="596fb-114">Description</span><span class="sxs-lookup"><span data-stu-id="596fb-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="596fb-115">모드</span><span class="sxs-lookup"><span data-stu-id="596fb-115">mode</span></span>|<span data-ttu-id="596fb-116">이 바인딩에 적용되는 보안 형식을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="596fb-116">Specifies the type of security that is applied to this binding.</span></span> <span data-ttu-id="596fb-117">유효한 값은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="596fb-117">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="596fb-118">없음을 이렇게 하면 보안이 해제 됩니다.</span><span class="sxs-lookup"><span data-stu-id="596fb-118">-   None: This disables security.</span></span><br /><span data-ttu-id="596fb-119">트랜스포트가 보안은 기본 전송 기반 보안을 사용 하 여 제공 됩니다.</span><span class="sxs-lookup"><span data-stu-id="596fb-119">-   Transport: Security is provided using underlying transport based security.</span></span> <span data-ttu-id="596fb-120">이 모드에서는 보호 수준을 제어할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="596fb-120">It is possible to control the protection level with this mode.</span></span><br /><span data-ttu-id="596fb-121">-기본값은 Transport입니다.</span><span class="sxs-lookup"><span data-stu-id="596fb-121">-   The default value is Transport.</span></span> <span data-ttu-id="596fb-122">이 특성은 <xref:System.ServiceModel.NetNamedPipeSecurityMode> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="596fb-122">This attribute is of type <xref:System.ServiceModel.NetNamedPipeSecurityMode>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="596fb-123">자식 요소</span><span class="sxs-lookup"><span data-stu-id="596fb-123">Child Elements</span></span>  
  
|<span data-ttu-id="596fb-124">요소</span><span class="sxs-lookup"><span data-stu-id="596fb-124">Element</span></span>|<span data-ttu-id="596fb-125">설명</span><span class="sxs-lookup"><span data-stu-id="596fb-125">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="596fb-126">transport</span><span class="sxs-lookup"><span data-stu-id="596fb-126">transport</span></span>|<span data-ttu-id="596fb-127">전송의 보안 설정을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="596fb-127">Defines the security settings for the transport.</span></span> <span data-ttu-id="596fb-128">이 요소는 <xref:System.ServiceModel.Configuration.NamedPipeTransportSecurityElement> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="596fb-128">This element is of type <xref:System.ServiceModel.Configuration.NamedPipeTransportSecurityElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="596fb-129">부모 요소</span><span class="sxs-lookup"><span data-stu-id="596fb-129">Parent Elements</span></span>  
  
|<span data-ttu-id="596fb-130">요소</span><span class="sxs-lookup"><span data-stu-id="596fb-130">Element</span></span>|<span data-ttu-id="596fb-131">Description</span><span class="sxs-lookup"><span data-stu-id="596fb-131">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="596fb-132">바인딩(binding)</span><span class="sxs-lookup"><span data-stu-id="596fb-132">binding</span></span>|<span data-ttu-id="596fb-133">[ \<NetNamedPipeBinding >](netnamedpipebinding.md)의 바인딩 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="596fb-133">The binding element of the [\<netNamedPipeBinding>](netnamedpipebinding.md).</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="596fb-134">참고자료</span><span class="sxs-lookup"><span data-stu-id="596fb-134">See also</span></span>

- <xref:System.ServiceModel.NetNamedPipeSecurity>
- <xref:System.ServiceModel.NetNamedPipeBinding.Security%2A>
- <xref:System.ServiceModel.Configuration.NetNamedPipeBindingElement.Security%2A>
- <xref:System.ServiceModel.Configuration.NetNamedPipeSecurityElement>
- [<span data-ttu-id="596fb-135">서비스 및 클라이언트에 보안 설정</span><span class="sxs-lookup"><span data-stu-id="596fb-135">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="596fb-136">자격 증명 형식 선택</span><span class="sxs-lookup"><span data-stu-id="596fb-136">Selecting a Credential Type</span></span>](../../../wcf/feature-details/selecting-a-credential-type.md)
- [<span data-ttu-id="596fb-137">바인딩</span><span class="sxs-lookup"><span data-stu-id="596fb-137">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="596fb-138">시스템 제공 바인딩 구성</span><span class="sxs-lookup"><span data-stu-id="596fb-138">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="596fb-139">바인딩을 사용하여 서비스 및 클라이언트 구성</span><span class="sxs-lookup"><span data-stu-id="596fb-139">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="596fb-140">\<binding></span><span class="sxs-lookup"><span data-stu-id="596fb-140">\<binding></span></span>](../../../misc/binding.md)
