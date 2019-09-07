---
title: <netNamedPipeBinding>의 <security>
ms.date: 03/30/2017
ms.assetid: bb3cb022-637e-49fd-92e8-6766038affa7
ms.openlocfilehash: cd3ff5d3983283f9b4783912b4b9525c5000df61
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/06/2019
ms.locfileid: "70399822"
---
# <a name="security-of-netnamedpipebinding"></a><span data-ttu-id="a9a39-102">\<netNamedPipeBinding >의 \<보안 ></span><span class="sxs-lookup"><span data-stu-id="a9a39-102">\<security> of \<netNamedPipeBinding></span></span>
<span data-ttu-id="a9a39-103">바인딩에 대한 보안 설정을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="a9a39-103">Defines the security settings for a binding.</span></span>  
  
<span data-ttu-id="a9a39-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="a9a39-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="a9a39-105">&nbsp;&nbsp;[ **\<System.servicemodel >** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="a9a39-105">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="a9a39-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<바인딩 >** ](bindings.md)</span><span class="sxs-lookup"><span data-stu-id="a9a39-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)</span></span>\
<span data-ttu-id="a9a39-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<netNamedPipeBinding >** ](netnamedpipebinding.md)</span><span class="sxs-lookup"><span data-stu-id="a9a39-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<netNamedPipeBinding>**](netnamedpipebinding.md)</span></span>\
<span data-ttu-id="a9a39-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<바인딩 >** </span><span class="sxs-lookup"><span data-stu-id="a9a39-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**</span></span>\
<span data-ttu-id="a9a39-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<보안 >**</span><span class="sxs-lookup"><span data-stu-id="a9a39-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<security>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a9a39-110">구문</span><span class="sxs-lookup"><span data-stu-id="a9a39-110">Syntax</span></span>  
  
```xml  
<netNamedPipeBinding>
  <binding>
    <security mode="None/Transport">
      <transport protectionLevel="None/Sign/EncryptAndSign" />
    </security>
  </binding>
</netNamedPipeBinding>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="a9a39-111">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="a9a39-111">Attributes and Elements</span></span>  
 <span data-ttu-id="a9a39-112">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="a9a39-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="a9a39-113">특성</span><span class="sxs-lookup"><span data-stu-id="a9a39-113">Attributes</span></span>  
  
|<span data-ttu-id="a9a39-114">특성</span><span class="sxs-lookup"><span data-stu-id="a9a39-114">Attribute</span></span>|<span data-ttu-id="a9a39-115">Description</span><span class="sxs-lookup"><span data-stu-id="a9a39-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="a9a39-116">모드</span><span class="sxs-lookup"><span data-stu-id="a9a39-116">mode</span></span>|<span data-ttu-id="a9a39-117">이 바인딩에 적용되는 보안 형식을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="a9a39-117">Specifies the type of security that is applied to this binding.</span></span> <span data-ttu-id="a9a39-118">유효한 값은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="a9a39-118">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="a9a39-119">없음을 이렇게 하면 보안이 해제 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a9a39-119">-   None: This disables security.</span></span><br /><span data-ttu-id="a9a39-120">트랜스포트가 보안은 기본 전송 기반 보안을 사용 하 여 제공 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a9a39-120">-   Transport: Security is provided using underlying transport based security.</span></span> <span data-ttu-id="a9a39-121">이 모드에서는 보호 수준을 제어할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a9a39-121">It is possible to control the protection level with this mode.</span></span><br /><span data-ttu-id="a9a39-122">-기본값은 Transport입니다.</span><span class="sxs-lookup"><span data-stu-id="a9a39-122">-   The default value is Transport.</span></span> <span data-ttu-id="a9a39-123">이 특성은 <xref:System.ServiceModel.NetNamedPipeSecurityMode> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="a9a39-123">This attribute is of type <xref:System.ServiceModel.NetNamedPipeSecurityMode>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="a9a39-124">자식 요소</span><span class="sxs-lookup"><span data-stu-id="a9a39-124">Child Elements</span></span>  
  
|<span data-ttu-id="a9a39-125">요소</span><span class="sxs-lookup"><span data-stu-id="a9a39-125">Element</span></span>|<span data-ttu-id="a9a39-126">Description</span><span class="sxs-lookup"><span data-stu-id="a9a39-126">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="a9a39-127">transport</span><span class="sxs-lookup"><span data-stu-id="a9a39-127">transport</span></span>|<span data-ttu-id="a9a39-128">전송의 보안 설정을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="a9a39-128">Defines the security settings for the transport.</span></span> <span data-ttu-id="a9a39-129">이 요소는 <xref:System.ServiceModel.Configuration.NamedPipeTransportSecurityElement> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="a9a39-129">This element is of type <xref:System.ServiceModel.Configuration.NamedPipeTransportSecurityElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="a9a39-130">부모 요소</span><span class="sxs-lookup"><span data-stu-id="a9a39-130">Parent Elements</span></span>  
  
|<span data-ttu-id="a9a39-131">요소</span><span class="sxs-lookup"><span data-stu-id="a9a39-131">Element</span></span>|<span data-ttu-id="a9a39-132">Description</span><span class="sxs-lookup"><span data-stu-id="a9a39-132">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="a9a39-133">바인딩(binding)</span><span class="sxs-lookup"><span data-stu-id="a9a39-133">binding</span></span>|<span data-ttu-id="a9a39-134">[ \<NetNamedPipeBinding >](netnamedpipebinding.md)의 바인딩 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="a9a39-134">The binding element of the [\<netNamedPipeBinding>](netnamedpipebinding.md).</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="a9a39-135">참고자료</span><span class="sxs-lookup"><span data-stu-id="a9a39-135">See also</span></span>

- <xref:System.ServiceModel.NetNamedPipeSecurity>
- <xref:System.ServiceModel.NetNamedPipeBinding.Security%2A>
- <xref:System.ServiceModel.Configuration.NetNamedPipeBindingElement.Security%2A>
- <xref:System.ServiceModel.Configuration.NetNamedPipeSecurityElement>
- [<span data-ttu-id="a9a39-136">서비스 및 클라이언트에 보안 설정</span><span class="sxs-lookup"><span data-stu-id="a9a39-136">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="a9a39-137">자격 증명 형식 선택</span><span class="sxs-lookup"><span data-stu-id="a9a39-137">Selecting a Credential Type</span></span>](../../../wcf/feature-details/selecting-a-credential-type.md)
- [<span data-ttu-id="a9a39-138">바인딩</span><span class="sxs-lookup"><span data-stu-id="a9a39-138">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="a9a39-139">시스템 제공 바인딩 구성</span><span class="sxs-lookup"><span data-stu-id="a9a39-139">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="a9a39-140">바인딩을 사용하여 서비스 및 클라이언트 구성</span><span class="sxs-lookup"><span data-stu-id="a9a39-140">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="a9a39-141">\<binding></span><span class="sxs-lookup"><span data-stu-id="a9a39-141">\<binding></span></span>](../../../misc/binding.md)
