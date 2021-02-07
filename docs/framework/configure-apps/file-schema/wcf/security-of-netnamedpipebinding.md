---
description: '다음에 대 한 자세한 정보:: <security><netNamedPipeBinding>'
title: <netNamedPipeBinding>의 <security>
ms.date: 03/30/2017
ms.assetid: bb3cb022-637e-49fd-92e8-6766038affa7
ms.openlocfilehash: d64917c53390cade00d9e104c8581ce45355ac34
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99683101"
---
# <a name="security-of-netnamedpipebinding"></a><span data-ttu-id="201a2-103">\<netNamedPipeBinding>의 \<security></span><span class="sxs-lookup"><span data-stu-id="201a2-103">\<security> of \<netNamedPipeBinding></span></span>

<span data-ttu-id="201a2-104">바인딩에 대한 보안 설정을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="201a2-104">Defines the security settings for a binding.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<netNamedPipeBinding>**](netnamedpipebinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<security>**  
  
## <a name="syntax"></a><span data-ttu-id="201a2-105">구문</span><span class="sxs-lookup"><span data-stu-id="201a2-105">Syntax</span></span>  
  
```xml  
<netNamedPipeBinding>
  <binding>
    <security mode="None/Transport">
      <transport protectionLevel="None/Sign/EncryptAndSign" />
    </security>
  </binding>
</netNamedPipeBinding>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="201a2-106">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="201a2-106">Attributes and Elements</span></span>  

 <span data-ttu-id="201a2-107">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="201a2-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="201a2-108">특성</span><span class="sxs-lookup"><span data-stu-id="201a2-108">Attributes</span></span>  
  
|<span data-ttu-id="201a2-109">attribute</span><span class="sxs-lookup"><span data-stu-id="201a2-109">Attribute</span></span>|<span data-ttu-id="201a2-110">설명</span><span class="sxs-lookup"><span data-stu-id="201a2-110">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="201a2-111">mode</span><span class="sxs-lookup"><span data-stu-id="201a2-111">mode</span></span>|<span data-ttu-id="201a2-112">이 바인딩에 적용되는 보안 형식을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="201a2-112">Specifies the type of security that is applied to this binding.</span></span> <span data-ttu-id="201a2-113">유효한 값은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="201a2-113">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="201a2-114">-없음: 보안을 사용 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="201a2-114">-   None: This disables security.</span></span><br /><span data-ttu-id="201a2-115">-전송: 보안은 기본 전송 기반 보안을 사용 하 여 제공 됩니다.</span><span class="sxs-lookup"><span data-stu-id="201a2-115">-   Transport: Security is provided using underlying transport based security.</span></span> <span data-ttu-id="201a2-116">이 모드에서는 보호 수준을 제어할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="201a2-116">It is possible to control the protection level with this mode.</span></span><br /><span data-ttu-id="201a2-117">-기본값은 Transport입니다.</span><span class="sxs-lookup"><span data-stu-id="201a2-117">-   The default value is Transport.</span></span> <span data-ttu-id="201a2-118">이 특성은 <xref:System.ServiceModel.NetNamedPipeSecurityMode> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="201a2-118">This attribute is of type <xref:System.ServiceModel.NetNamedPipeSecurityMode>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="201a2-119">자식 요소</span><span class="sxs-lookup"><span data-stu-id="201a2-119">Child Elements</span></span>  
  
|<span data-ttu-id="201a2-120">요소</span><span class="sxs-lookup"><span data-stu-id="201a2-120">Element</span></span>|<span data-ttu-id="201a2-121">설명</span><span class="sxs-lookup"><span data-stu-id="201a2-121">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="201a2-122">교통</span><span class="sxs-lookup"><span data-stu-id="201a2-122">transport</span></span>|<span data-ttu-id="201a2-123">전송의 보안 설정을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="201a2-123">Defines the security settings for the transport.</span></span> <span data-ttu-id="201a2-124">이 요소는 <xref:System.ServiceModel.Configuration.NamedPipeTransportSecurityElement> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="201a2-124">This element is of type <xref:System.ServiceModel.Configuration.NamedPipeTransportSecurityElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="201a2-125">부모 요소</span><span class="sxs-lookup"><span data-stu-id="201a2-125">Parent Elements</span></span>  
  
|<span data-ttu-id="201a2-126">요소</span><span class="sxs-lookup"><span data-stu-id="201a2-126">Element</span></span>|<span data-ttu-id="201a2-127">설명</span><span class="sxs-lookup"><span data-stu-id="201a2-127">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="201a2-128">바인딩</span><span class="sxs-lookup"><span data-stu-id="201a2-128">binding</span></span>|<span data-ttu-id="201a2-129">의 바인딩 요소 [\<netNamedPipeBinding>](netnamedpipebinding.md) 입니다.</span><span class="sxs-lookup"><span data-stu-id="201a2-129">The binding element of the [\<netNamedPipeBinding>](netnamedpipebinding.md).</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="201a2-130">참고 항목</span><span class="sxs-lookup"><span data-stu-id="201a2-130">See also</span></span>

- <xref:System.ServiceModel.NetNamedPipeSecurity>
- <xref:System.ServiceModel.NetNamedPipeBinding.Security%2A>
- <xref:System.ServiceModel.Configuration.NetNamedPipeBindingElement.Security%2A>
- <xref:System.ServiceModel.Configuration.NetNamedPipeSecurityElement>
- [<span data-ttu-id="201a2-131">서비스 및 클라이언트에 보안 설정</span><span class="sxs-lookup"><span data-stu-id="201a2-131">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="201a2-132">자격 증명 형식 선택</span><span class="sxs-lookup"><span data-stu-id="201a2-132">Selecting a Credential Type</span></span>](../../../wcf/feature-details/selecting-a-credential-type.md)
- [<span data-ttu-id="201a2-133">바인딩</span><span class="sxs-lookup"><span data-stu-id="201a2-133">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="201a2-134">시스템 제공 바인딩 구성</span><span class="sxs-lookup"><span data-stu-id="201a2-134">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="201a2-135">바인딩을 사용하여 서비스 및 클라이언트 구성</span><span class="sxs-lookup"><span data-stu-id="201a2-135">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [\<binding>](bindings.md)
