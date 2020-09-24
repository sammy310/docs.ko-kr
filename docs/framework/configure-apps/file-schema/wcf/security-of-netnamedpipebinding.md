---
title: <netNamedPipeBinding>의 <security>
ms.date: 03/30/2017
ms.assetid: bb3cb022-637e-49fd-92e8-6766038affa7
ms.openlocfilehash: 1a231a60d29cc6a4460de69a98753c23c0386027
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/24/2020
ms.locfileid: "91170040"
---
# <a name="security-of-netnamedpipebinding"></a><span data-ttu-id="7aea3-102">\<netNamedPipeBinding>의 \<security></span><span class="sxs-lookup"><span data-stu-id="7aea3-102">\<security> of \<netNamedPipeBinding></span></span>

<span data-ttu-id="7aea3-103">바인딩에 대한 보안 설정을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="7aea3-103">Defines the security settings for a binding.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<netNamedPipeBinding>**](netnamedpipebinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<security>**  
  
## <a name="syntax"></a><span data-ttu-id="7aea3-104">구문</span><span class="sxs-lookup"><span data-stu-id="7aea3-104">Syntax</span></span>  
  
```xml  
<netNamedPipeBinding>
  <binding>
    <security mode="None/Transport">
      <transport protectionLevel="None/Sign/EncryptAndSign" />
    </security>
  </binding>
</netNamedPipeBinding>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="7aea3-105">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="7aea3-105">Attributes and Elements</span></span>  

 <span data-ttu-id="7aea3-106">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="7aea3-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="7aea3-107">특성</span><span class="sxs-lookup"><span data-stu-id="7aea3-107">Attributes</span></span>  
  
|<span data-ttu-id="7aea3-108">attribute</span><span class="sxs-lookup"><span data-stu-id="7aea3-108">Attribute</span></span>|<span data-ttu-id="7aea3-109">설명</span><span class="sxs-lookup"><span data-stu-id="7aea3-109">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="7aea3-110">mode</span><span class="sxs-lookup"><span data-stu-id="7aea3-110">mode</span></span>|<span data-ttu-id="7aea3-111">이 바인딩에 적용되는 보안 형식을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="7aea3-111">Specifies the type of security that is applied to this binding.</span></span> <span data-ttu-id="7aea3-112">유효한 값은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="7aea3-112">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="7aea3-113">-없음: 보안을 사용 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7aea3-113">-   None: This disables security.</span></span><br /><span data-ttu-id="7aea3-114">-전송: 보안은 기본 전송 기반 보안을 사용 하 여 제공 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7aea3-114">-   Transport: Security is provided using underlying transport based security.</span></span> <span data-ttu-id="7aea3-115">이 모드에서는 보호 수준을 제어할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7aea3-115">It is possible to control the protection level with this mode.</span></span><br /><span data-ttu-id="7aea3-116">-기본값은 Transport입니다.</span><span class="sxs-lookup"><span data-stu-id="7aea3-116">-   The default value is Transport.</span></span> <span data-ttu-id="7aea3-117">이 특성은 <xref:System.ServiceModel.NetNamedPipeSecurityMode> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="7aea3-117">This attribute is of type <xref:System.ServiceModel.NetNamedPipeSecurityMode>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="7aea3-118">자식 요소</span><span class="sxs-lookup"><span data-stu-id="7aea3-118">Child Elements</span></span>  
  
|<span data-ttu-id="7aea3-119">요소</span><span class="sxs-lookup"><span data-stu-id="7aea3-119">Element</span></span>|<span data-ttu-id="7aea3-120">설명</span><span class="sxs-lookup"><span data-stu-id="7aea3-120">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="7aea3-121">교통</span><span class="sxs-lookup"><span data-stu-id="7aea3-121">transport</span></span>|<span data-ttu-id="7aea3-122">전송의 보안 설정을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="7aea3-122">Defines the security settings for the transport.</span></span> <span data-ttu-id="7aea3-123">이 요소는 <xref:System.ServiceModel.Configuration.NamedPipeTransportSecurityElement> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="7aea3-123">This element is of type <xref:System.ServiceModel.Configuration.NamedPipeTransportSecurityElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="7aea3-124">부모 요소</span><span class="sxs-lookup"><span data-stu-id="7aea3-124">Parent Elements</span></span>  
  
|<span data-ttu-id="7aea3-125">요소</span><span class="sxs-lookup"><span data-stu-id="7aea3-125">Element</span></span>|<span data-ttu-id="7aea3-126">설명</span><span class="sxs-lookup"><span data-stu-id="7aea3-126">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="7aea3-127">바인딩</span><span class="sxs-lookup"><span data-stu-id="7aea3-127">binding</span></span>|<span data-ttu-id="7aea3-128">의 바인딩 요소 [\<netNamedPipeBinding>](netnamedpipebinding.md) 입니다.</span><span class="sxs-lookup"><span data-stu-id="7aea3-128">The binding element of the [\<netNamedPipeBinding>](netnamedpipebinding.md).</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="7aea3-129">참고 항목</span><span class="sxs-lookup"><span data-stu-id="7aea3-129">See also</span></span>

- <xref:System.ServiceModel.NetNamedPipeSecurity>
- <xref:System.ServiceModel.NetNamedPipeBinding.Security%2A>
- <xref:System.ServiceModel.Configuration.NetNamedPipeBindingElement.Security%2A>
- <xref:System.ServiceModel.Configuration.NetNamedPipeSecurityElement>
- [<span data-ttu-id="7aea3-130">서비스 및 클라이언트에 보안 설정</span><span class="sxs-lookup"><span data-stu-id="7aea3-130">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="7aea3-131">자격 증명 형식 선택</span><span class="sxs-lookup"><span data-stu-id="7aea3-131">Selecting a Credential Type</span></span>](../../../wcf/feature-details/selecting-a-credential-type.md)
- [<span data-ttu-id="7aea3-132">바인딩하</span><span class="sxs-lookup"><span data-stu-id="7aea3-132">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="7aea3-133">시스템 제공 바인딩 구성</span><span class="sxs-lookup"><span data-stu-id="7aea3-133">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="7aea3-134">바인딩을 사용하여 서비스 및 클라이언트 구성</span><span class="sxs-lookup"><span data-stu-id="7aea3-134">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [\<binding>](bindings.md)
