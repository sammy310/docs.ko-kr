---
title: <servicePrincipalName>
ms.date: 03/30/2017
ms.assetid: 3f3b85d3-20f2-4cd8-8a6a-ee18befbd165
ms.openlocfilehash: da865a19a91d4af6221a13b53a174637d5fb8139
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/06/2020
ms.locfileid: "70854997"
---
# \<servicePrincipalName>
<span data-ttu-id="7b261-101">SPN(서비스 사용자 이름)으로 서비스 ID를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="7b261-101">Specifies the identity of a service by its Service Principal Name (SPN).</span></span>  
  
<span data-ttu-id="7b261-102">SPN을 설정 하는 방법에 대 한 자세한 내용은 [서비스 id 및 인증](../../../wcf/feature-details/service-identity-and-authentication.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="7b261-102">For more information about setting the SPN, see [Service Identity and Authentication](../../../wcf/feature-details/service-identity-and-authentication.md).</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<client>**](client.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpoint>**](endpoint-of-client.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<identity>**](identity.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<servicePrincipalName>**  
  
## <a name="syntax"></a><span data-ttu-id="7b261-103">구문</span><span class="sxs-lookup"><span data-stu-id="7b261-103">Syntax</span></span>  
  
```xml  
<servicePrincipalName value="String" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="7b261-104">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="7b261-104">Attributes and Elements</span></span>  
 <span data-ttu-id="7b261-105">다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="7b261-105">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="7b261-106">특성</span><span class="sxs-lookup"><span data-stu-id="7b261-106">Attributes</span></span>  
  
|<span data-ttu-id="7b261-107">attribute</span><span class="sxs-lookup"><span data-stu-id="7b261-107">Attribute</span></span>|<span data-ttu-id="7b261-108">Description</span><span class="sxs-lookup"><span data-stu-id="7b261-108">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="7b261-109">값</span><span class="sxs-lookup"><span data-stu-id="7b261-109">value</span></span>|<span data-ttu-id="7b261-110">클라이언트가 서비스 인스턴스를 고유하게 식별하는 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="7b261-110">The name by which a client uniquely identifies an instance of a service.</span></span> <span data-ttu-id="7b261-111">포리스트를 통해 컴퓨터에 여러 서비스 인스턴스를 설치하는 경우 각 인스턴스에 고유한 SPN이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7b261-111">If you install multiple instances of a service on computers throughout a forest, each instance must have its own SPN.</span></span> <span data-ttu-id="7b261-112">클라이언트에서 인증에 사용할 수 있는 이름이 여러 개인 경우 지정한 서비스 인스턴스에 여러 개의 SPN이 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7b261-112">A given service instance can have multiple SPNs if there are multiple names that clients might use for authentication.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="7b261-113">자식 요소</span><span class="sxs-lookup"><span data-stu-id="7b261-113">Child Elements</span></span>  
 <span data-ttu-id="7b261-114">없음</span><span class="sxs-lookup"><span data-stu-id="7b261-114">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="7b261-115">부모 요소</span><span class="sxs-lookup"><span data-stu-id="7b261-115">Parent Elements</span></span>  
  
|<span data-ttu-id="7b261-116">요소</span><span class="sxs-lookup"><span data-stu-id="7b261-116">Element</span></span>|<span data-ttu-id="7b261-117">Description</span><span class="sxs-lookup"><span data-stu-id="7b261-117">Description</span></span>|  
|-------------|-----------------|  
|[\<identity>](identity.md)|<span data-ttu-id="7b261-118">클라이언트에서 인증할 서비스의 ID를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="7b261-118">Specifies the identity of the service to be authenticated by the client.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7b261-119">설명</span><span class="sxs-lookup"><span data-stu-id="7b261-119">Remarks</span></span>  
 <span data-ttu-id="7b261-120">이 id를 사용 하 여 끝점에 연결 하는 WCF (secure Windows Communication Foundation) 클라이언트는 끝점을 사용 하 여 SSPI 인증을 수행할 때 SPN을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="7b261-120">A secure Windows Communication Foundation (WCF) client that connects to an endpoint with this identity uses the SPN when performing SSPI authentication with the endpoint.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7b261-121">참고 항목</span><span class="sxs-lookup"><span data-stu-id="7b261-121">See also</span></span>

- <xref:System.ServiceModel.Configuration.IdentityElement>
- <xref:System.ServiceModel.EndpointAddress>
- <xref:System.ServiceModel.EndpointAddress.Identity%2A>
- <xref:System.ServiceModel.SpnEndpointIdentity>
- [<span data-ttu-id="7b261-122">서비스 ID 및 인증</span><span class="sxs-lookup"><span data-stu-id="7b261-122">Service Identity and Authentication</span></span>](../../../wcf/feature-details/service-identity-and-authentication.md)
- [\<identity>](identity.md)
