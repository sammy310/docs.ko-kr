---
title: <netNamedPipeBinding>의 <security>
ms.date: 03/30/2017
ms.assetid: bb3cb022-637e-49fd-92e8-6766038affa7
ms.openlocfilehash: 31ea31ce6880a770c966350cd931e487396c4d63
ms.sourcegitcommit: 22be09204266253d45ece46f51cc6f080f2b3fd6
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/07/2019
ms.locfileid: "73736444"
---
# <a name="security-of-netnamedpipebinding"></a><span data-ttu-id="c071c-102">\<보안 > \<netNamedPipeBinding ></span><span class="sxs-lookup"><span data-stu-id="c071c-102">\<security> of \<netNamedPipeBinding></span></span>
<span data-ttu-id="c071c-103">바인딩에 대한 보안 설정을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="c071c-103">Defines the security settings for a binding.</span></span>  
  
<span data-ttu-id="c071c-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="c071c-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="c071c-105">[ **\<system serviceModel >** ](system-servicemodel.md) &nbsp; &nbsp; </span><span class="sxs-lookup"><span data-stu-id="c071c-105">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="c071c-106">&nbsp;&nbsp;&nbsp;&nbsp;\<[**바인딩**](bindings.md) ></span><span class="sxs-lookup"><span data-stu-id="c071c-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\</span></span>
<span data-ttu-id="c071c-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<netNamedPipeBinding >** ](netnamedpipebinding.md)</span><span class="sxs-lookup"><span data-stu-id="c071c-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<netNamedPipeBinding>**](netnamedpipebinding.md)</span></span>\
<span data-ttu-id="c071c-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<바인딩 >** </span><span class="sxs-lookup"><span data-stu-id="c071c-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**</span></span>\
<span data-ttu-id="c071c-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<**보안 >**</span><span class="sxs-lookup"><span data-stu-id="c071c-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<security>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c071c-110">구문</span><span class="sxs-lookup"><span data-stu-id="c071c-110">Syntax</span></span>  
  
```xml  
<netNamedPipeBinding>
  <binding>
    <security mode="None/Transport">
      <transport protectionLevel="None/Sign/EncryptAndSign" />
    </security>
  </binding>
</netNamedPipeBinding>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="c071c-111">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="c071c-111">Attributes and Elements</span></span>  
 <span data-ttu-id="c071c-112">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="c071c-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="c071c-113">특성</span><span class="sxs-lookup"><span data-stu-id="c071c-113">Attributes</span></span>  
  
|<span data-ttu-id="c071c-114">특성</span><span class="sxs-lookup"><span data-stu-id="c071c-114">Attribute</span></span>|<span data-ttu-id="c071c-115">설명</span><span class="sxs-lookup"><span data-stu-id="c071c-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="c071c-116">모드</span><span class="sxs-lookup"><span data-stu-id="c071c-116">mode</span></span>|<span data-ttu-id="c071c-117">이 바인딩에 적용되는 보안 형식을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="c071c-117">Specifies the type of security that is applied to this binding.</span></span> <span data-ttu-id="c071c-118">유효한 값은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="c071c-118">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="c071c-119">-없음: 보안을 사용 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c071c-119">-   None: This disables security.</span></span><br /><span data-ttu-id="c071c-120">-전송: 보안은 기본 전송 기반 보안을 사용 하 여 제공 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c071c-120">-   Transport: Security is provided using underlying transport based security.</span></span> <span data-ttu-id="c071c-121">이 모드에서는 보호 수준을 제어할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c071c-121">It is possible to control the protection level with this mode.</span></span><br /><span data-ttu-id="c071c-122">-기본값은 Transport입니다.</span><span class="sxs-lookup"><span data-stu-id="c071c-122">-   The default value is Transport.</span></span> <span data-ttu-id="c071c-123">이 특성은 <xref:System.ServiceModel.NetNamedPipeSecurityMode> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="c071c-123">This attribute is of type <xref:System.ServiceModel.NetNamedPipeSecurityMode>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="c071c-124">자식 요소</span><span class="sxs-lookup"><span data-stu-id="c071c-124">Child Elements</span></span>  
  
|<span data-ttu-id="c071c-125">요소</span><span class="sxs-lookup"><span data-stu-id="c071c-125">Element</span></span>|<span data-ttu-id="c071c-126">설명</span><span class="sxs-lookup"><span data-stu-id="c071c-126">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="c071c-127">transport</span><span class="sxs-lookup"><span data-stu-id="c071c-127">transport</span></span>|<span data-ttu-id="c071c-128">전송의 보안 설정을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="c071c-128">Defines the security settings for the transport.</span></span> <span data-ttu-id="c071c-129">이 요소는 <xref:System.ServiceModel.Configuration.NamedPipeTransportSecurityElement> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="c071c-129">This element is of type <xref:System.ServiceModel.Configuration.NamedPipeTransportSecurityElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="c071c-130">부모 요소</span><span class="sxs-lookup"><span data-stu-id="c071c-130">Parent Elements</span></span>  
  
|<span data-ttu-id="c071c-131">요소</span><span class="sxs-lookup"><span data-stu-id="c071c-131">Element</span></span>|<span data-ttu-id="c071c-132">설명</span><span class="sxs-lookup"><span data-stu-id="c071c-132">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="c071c-133">바인딩</span><span class="sxs-lookup"><span data-stu-id="c071c-133">binding</span></span>|<span data-ttu-id="c071c-134">[\<netNamedPipeBinding >](netnamedpipebinding.md)의 바인딩 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="c071c-134">The binding element of the [\<netNamedPipeBinding>](netnamedpipebinding.md).</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="c071c-135">참조</span><span class="sxs-lookup"><span data-stu-id="c071c-135">See also</span></span>

- <xref:System.ServiceModel.NetNamedPipeSecurity>
- <xref:System.ServiceModel.NetNamedPipeBinding.Security%2A>
- <xref:System.ServiceModel.Configuration.NetNamedPipeBindingElement.Security%2A>
- <xref:System.ServiceModel.Configuration.NetNamedPipeSecurityElement>
- [<span data-ttu-id="c071c-136">서비스 및 클라이언트에 보안 설정</span><span class="sxs-lookup"><span data-stu-id="c071c-136">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="c071c-137">자격 증명 형식 선택</span><span class="sxs-lookup"><span data-stu-id="c071c-137">Selecting a Credential Type</span></span>](../../../wcf/feature-details/selecting-a-credential-type.md)
- [<span data-ttu-id="c071c-138">바인딩</span><span class="sxs-lookup"><span data-stu-id="c071c-138">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="c071c-139">시스템 제공 바인딩 구성</span><span class="sxs-lookup"><span data-stu-id="c071c-139">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="c071c-140">바인딩을 사용하여 서비스 및 클라이언트 구성</span><span class="sxs-lookup"><span data-stu-id="c071c-140">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="c071c-141">\<binding ></span><span class="sxs-lookup"><span data-stu-id="c071c-141">\<binding></span></span>](bindings.md)
