---
description: 다음에 대해 자세히 알아보세요. <servicePrincipalName>
title: <servicePrincipalName>
ms.date: 03/30/2017
ms.assetid: 3f3b85d3-20f2-4cd8-8a6a-ee18befbd165
ms.openlocfilehash: 494368f1f47f10aac8009e47a9219966c87e5eda
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99786696"
---
# \<servicePrincipalName>

<span data-ttu-id="9f6f5-102">SPN(서비스 사용자 이름)으로 서비스 ID를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="9f6f5-102">Specifies the identity of a service by its Service Principal Name (SPN).</span></span>  
  
<span data-ttu-id="9f6f5-103">SPN을 설정 하는 방법에 대 한 자세한 내용은 [서비스 id 및 인증](../../../wcf/feature-details/service-identity-and-authentication.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="9f6f5-103">For more information about setting the SPN, see [Service Identity and Authentication](../../../wcf/feature-details/service-identity-and-authentication.md).</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<client>**](client.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpoint>**](endpoint-of-client.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<identity>**](identity.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<servicePrincipalName>**  
  
## <a name="syntax"></a><span data-ttu-id="9f6f5-104">구문</span><span class="sxs-lookup"><span data-stu-id="9f6f5-104">Syntax</span></span>  
  
```xml  
<servicePrincipalName value="String" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="9f6f5-105">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="9f6f5-105">Attributes and Elements</span></span>  

 <span data-ttu-id="9f6f5-106">다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="9f6f5-106">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="9f6f5-107">특성</span><span class="sxs-lookup"><span data-stu-id="9f6f5-107">Attributes</span></span>  
  
|<span data-ttu-id="9f6f5-108">attribute</span><span class="sxs-lookup"><span data-stu-id="9f6f5-108">Attribute</span></span>|<span data-ttu-id="9f6f5-109">Description</span><span class="sxs-lookup"><span data-stu-id="9f6f5-109">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="9f6f5-110">값</span><span class="sxs-lookup"><span data-stu-id="9f6f5-110">value</span></span>|<span data-ttu-id="9f6f5-111">클라이언트가 서비스 인스턴스를 고유하게 식별하는 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="9f6f5-111">The name by which a client uniquely identifies an instance of a service.</span></span> <span data-ttu-id="9f6f5-112">포리스트를 통해 컴퓨터에 여러 서비스 인스턴스를 설치하는 경우 각 인스턴스에 고유한 SPN이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9f6f5-112">If you install multiple instances of a service on computers throughout a forest, each instance must have its own SPN.</span></span> <span data-ttu-id="9f6f5-113">클라이언트에서 인증에 사용할 수 있는 이름이 여러 개인 경우 지정한 서비스 인스턴스에 여러 개의 SPN이 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9f6f5-113">A given service instance can have multiple SPNs if there are multiple names that clients might use for authentication.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="9f6f5-114">자식 요소</span><span class="sxs-lookup"><span data-stu-id="9f6f5-114">Child Elements</span></span>  

 <span data-ttu-id="9f6f5-115">없음</span><span class="sxs-lookup"><span data-stu-id="9f6f5-115">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="9f6f5-116">부모 요소</span><span class="sxs-lookup"><span data-stu-id="9f6f5-116">Parent Elements</span></span>  
  
|<span data-ttu-id="9f6f5-117">요소</span><span class="sxs-lookup"><span data-stu-id="9f6f5-117">Element</span></span>|<span data-ttu-id="9f6f5-118">설명</span><span class="sxs-lookup"><span data-stu-id="9f6f5-118">Description</span></span>|  
|-------------|-----------------|  
|[\<identity>](identity.md)|<span data-ttu-id="9f6f5-119">클라이언트에서 인증할 서비스의 ID를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="9f6f5-119">Specifies the identity of the service to be authenticated by the client.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9f6f5-120">설명</span><span class="sxs-lookup"><span data-stu-id="9f6f5-120">Remarks</span></span>  

 <span data-ttu-id="9f6f5-121">이 id를 사용 하 여 끝점에 연결 하는 WCF (secure Windows Communication Foundation) 클라이언트는 끝점을 사용 하 여 SSPI 인증을 수행할 때 SPN을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="9f6f5-121">A secure Windows Communication Foundation (WCF) client that connects to an endpoint with this identity uses the SPN when performing SSPI authentication with the endpoint.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9f6f5-122">참고 항목</span><span class="sxs-lookup"><span data-stu-id="9f6f5-122">See also</span></span>

- <xref:System.ServiceModel.Configuration.IdentityElement>
- <xref:System.ServiceModel.EndpointAddress>
- <xref:System.ServiceModel.EndpointAddress.Identity%2A>
- <xref:System.ServiceModel.SpnEndpointIdentity>
- [<span data-ttu-id="9f6f5-123">서비스 ID 및 인증</span><span class="sxs-lookup"><span data-stu-id="9f6f5-123">Service Identity and Authentication</span></span>](../../../wcf/feature-details/service-identity-and-authentication.md)
- [\<identity>](identity.md)
