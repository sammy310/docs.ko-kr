---
title: <netNamedPipeBinding>의 <security>
ms.date: 03/30/2017
ms.assetid: bb3cb022-637e-49fd-92e8-6766038affa7
ms.openlocfilehash: fa31dda3274c9768694bdf5232f31554899e1d82
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61670523"
---
# <a name="security-of-netnamedpipebinding"></a><span data-ttu-id="11d87-102">\<보안 >의 \<netNamedPipeBinding ></span><span class="sxs-lookup"><span data-stu-id="11d87-102">\<security> of \<netNamedPipeBinding></span></span>
<span data-ttu-id="11d87-103">바인딩에 대한 보안 설정을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="11d87-103">Defines the security settings for a binding.</span></span>  
  
 <span data-ttu-id="11d87-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="11d87-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="11d87-105">\<bindings></span><span class="sxs-lookup"><span data-stu-id="11d87-105">\<bindings></span></span>  
<span data-ttu-id="11d87-106">\<netNamedPipeBinding></span><span class="sxs-lookup"><span data-stu-id="11d87-106">\<netNamedPipeBinding></span></span>  
<span data-ttu-id="11d87-107">\<binding></span><span class="sxs-lookup"><span data-stu-id="11d87-107">\<binding></span></span>  
<span data-ttu-id="11d87-108">\<security></span><span class="sxs-lookup"><span data-stu-id="11d87-108">\<security></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="11d87-109">구문</span><span class="sxs-lookup"><span data-stu-id="11d87-109">Syntax</span></span>  
  
```xml  
<netNamedPipeBinding>
  <binding>
    <security mode="None/Transport">
      <transport protectionLevel="None/Sign/EncryptAndSign" />
    </security>
  </binding>
</netNamedPipeBinding>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="11d87-110">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="11d87-110">Attributes and Elements</span></span>  
 <span data-ttu-id="11d87-111">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="11d87-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="11d87-112">특성</span><span class="sxs-lookup"><span data-stu-id="11d87-112">Attributes</span></span>  
  
|<span data-ttu-id="11d87-113">특성</span><span class="sxs-lookup"><span data-stu-id="11d87-113">Attribute</span></span>|<span data-ttu-id="11d87-114">설명</span><span class="sxs-lookup"><span data-stu-id="11d87-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="11d87-115">모드</span><span class="sxs-lookup"><span data-stu-id="11d87-115">mode</span></span>|<span data-ttu-id="11d87-116">이 바인딩에 적용되는 보안 형식을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="11d87-116">Specifies the type of security that is applied to this binding.</span></span> <span data-ttu-id="11d87-117">유효한 값은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="11d87-117">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="11d87-118">-None. 이렇게 하면 보안이 해제 합니다.</span><span class="sxs-lookup"><span data-stu-id="11d87-118">-   None: This disables security.</span></span><br /><span data-ttu-id="11d87-119">-전송 합니다. 기본 전송 기반 보안을 사용 하 여 보안이 유지 됩니다.</span><span class="sxs-lookup"><span data-stu-id="11d87-119">-   Transport: Security is provided using underlying transport based security.</span></span> <span data-ttu-id="11d87-120">이 모드에서는 보호 수준을 제어할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="11d87-120">It is possible to control the protection level with this mode.</span></span><br /><span data-ttu-id="11d87-121">-기본값은 Transport입니다.</span><span class="sxs-lookup"><span data-stu-id="11d87-121">-   The default value is Transport.</span></span> <span data-ttu-id="11d87-122">이 특성은 <xref:System.ServiceModel.NetNamedPipeSecurityMode> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="11d87-122">This attribute is of type <xref:System.ServiceModel.NetNamedPipeSecurityMode>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="11d87-123">자식 요소</span><span class="sxs-lookup"><span data-stu-id="11d87-123">Child Elements</span></span>  
  
|<span data-ttu-id="11d87-124">요소</span><span class="sxs-lookup"><span data-stu-id="11d87-124">Element</span></span>|<span data-ttu-id="11d87-125">설명</span><span class="sxs-lookup"><span data-stu-id="11d87-125">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="11d87-126">transport</span><span class="sxs-lookup"><span data-stu-id="11d87-126">transport</span></span>|<span data-ttu-id="11d87-127">전송의 보안 설정을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="11d87-127">Defines the security settings for the transport.</span></span> <span data-ttu-id="11d87-128">이 요소는 <xref:System.ServiceModel.Configuration.NamedPipeTransportSecurityElement> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="11d87-128">This element is of type <xref:System.ServiceModel.Configuration.NamedPipeTransportSecurityElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="11d87-129">부모 요소</span><span class="sxs-lookup"><span data-stu-id="11d87-129">Parent Elements</span></span>  
  
|<span data-ttu-id="11d87-130">요소</span><span class="sxs-lookup"><span data-stu-id="11d87-130">Element</span></span>|<span data-ttu-id="11d87-131">설명</span><span class="sxs-lookup"><span data-stu-id="11d87-131">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="11d87-132">바인딩</span><span class="sxs-lookup"><span data-stu-id="11d87-132">binding</span></span>|<span data-ttu-id="11d87-133">바인딩 요소를 [ \<netNamedPipeBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/netnamedpipebinding.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="11d87-133">The binding element of the [\<netNamedPipeBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/netnamedpipebinding.md).</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="11d87-134">참고자료</span><span class="sxs-lookup"><span data-stu-id="11d87-134">See also</span></span>

- <xref:System.ServiceModel.NetNamedPipeSecurity>
- <xref:System.ServiceModel.NetNamedPipeBinding.Security%2A>
- <xref:System.ServiceModel.Configuration.NetNamedPipeBindingElement.Security%2A>
- <xref:System.ServiceModel.Configuration.NetNamedPipeSecurityElement>
- [<span data-ttu-id="11d87-135">서비스 및 클라이언트에 보안 설정</span><span class="sxs-lookup"><span data-stu-id="11d87-135">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="11d87-136">자격 증명 형식 선택</span><span class="sxs-lookup"><span data-stu-id="11d87-136">Selecting a Credential Type</span></span>](../../../../../docs/framework/wcf/feature-details/selecting-a-credential-type.md)
- [<span data-ttu-id="11d87-137">바인딩</span><span class="sxs-lookup"><span data-stu-id="11d87-137">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)
- [<span data-ttu-id="11d87-138">시스템 제공 바인딩 구성</span><span class="sxs-lookup"><span data-stu-id="11d87-138">Configuring System-Provided Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="11d87-139">바인딩을 사용하여 서비스 및 클라이언트 구성</span><span class="sxs-lookup"><span data-stu-id="11d87-139">Using Bindings to Configure Services and Clients</span></span>](../../../../../docs/framework/wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="11d87-140">\<binding></span><span class="sxs-lookup"><span data-stu-id="11d87-140">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)
