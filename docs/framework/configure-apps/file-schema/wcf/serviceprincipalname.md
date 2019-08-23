---
title: <servicePrincipalName>
ms.date: 03/30/2017
ms.assetid: 3f3b85d3-20f2-4cd8-8a6a-ee18befbd165
ms.openlocfilehash: 28ae27481ea9cb86c31b5be1f12b5491f8ca143e
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/22/2019
ms.locfileid: "69936160"
---
# <a name="serviceprincipalname"></a><span data-ttu-id="d44ce-101">\<servicePrincipalName></span><span class="sxs-lookup"><span data-stu-id="d44ce-101">\<servicePrincipalName></span></span>
<span data-ttu-id="d44ce-102">SPN(서비스 사용자 이름)으로 서비스 ID를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="d44ce-102">Specifies the identity of a service by its Service Principal Name (SPN).</span></span>  
  
 <span data-ttu-id="d44ce-103">SPN을 설정 하는 방법에 대 한 자세한 내용은 [서비스 id 및 인증](../../../wcf/feature-details/service-identity-and-authentication.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="d44ce-103">For more information about setting the SPN, see [Service Identity and Authentication](../../../wcf/feature-details/service-identity-and-authentication.md).</span></span>  
  
 <span data-ttu-id="d44ce-104">\<identity></span><span class="sxs-lookup"><span data-stu-id="d44ce-104">\<identity></span></span>  
<span data-ttu-id="d44ce-105">\<servicePrincipalName></span><span class="sxs-lookup"><span data-stu-id="d44ce-105">\<servicePrincipalName></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d44ce-106">구문</span><span class="sxs-lookup"><span data-stu-id="d44ce-106">Syntax</span></span>  
  
```xml  
<servicePrincipalName value="String" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="d44ce-107">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="d44ce-107">Attributes and Elements</span></span>  
 <span data-ttu-id="d44ce-108">다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="d44ce-108">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="d44ce-109">특성</span><span class="sxs-lookup"><span data-stu-id="d44ce-109">Attributes</span></span>  
  
|<span data-ttu-id="d44ce-110">특성</span><span class="sxs-lookup"><span data-stu-id="d44ce-110">Attribute</span></span>|<span data-ttu-id="d44ce-111">설명</span><span class="sxs-lookup"><span data-stu-id="d44ce-111">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="d44ce-112">value</span><span class="sxs-lookup"><span data-stu-id="d44ce-112">value</span></span>|<span data-ttu-id="d44ce-113">클라이언트가 서비스 인스턴스를 고유하게 식별하는 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="d44ce-113">The name by which a client uniquely identifies an instance of a service.</span></span> <span data-ttu-id="d44ce-114">포리스트를 통해 컴퓨터에 여러 서비스 인스턴스를 설치하는 경우 각 인스턴스에 고유한 SPN이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d44ce-114">If you install multiple instances of a service on computers throughout a forest, each instance must have its own SPN.</span></span> <span data-ttu-id="d44ce-115">클라이언트에서 인증에 사용할 수 있는 이름이 여러 개인 경우 지정한 서비스 인스턴스에 여러 개의 SPN이 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d44ce-115">A given service instance can have multiple SPNs if there are multiple names that clients might use for authentication.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="d44ce-116">자식 요소</span><span class="sxs-lookup"><span data-stu-id="d44ce-116">Child Elements</span></span>  
 <span data-ttu-id="d44ce-117">없음</span><span class="sxs-lookup"><span data-stu-id="d44ce-117">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="d44ce-118">부모 요소</span><span class="sxs-lookup"><span data-stu-id="d44ce-118">Parent Elements</span></span>  
  
|<span data-ttu-id="d44ce-119">요소</span><span class="sxs-lookup"><span data-stu-id="d44ce-119">Element</span></span>|<span data-ttu-id="d44ce-120">Description</span><span class="sxs-lookup"><span data-stu-id="d44ce-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="d44ce-121">\<identity></span><span class="sxs-lookup"><span data-stu-id="d44ce-121">\<identity></span></span>](identity.md)|<span data-ttu-id="d44ce-122">클라이언트에서 인증할 서비스의 ID를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="d44ce-122">Specifies the identity of the service to be authenticated by the client.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d44ce-123">설명</span><span class="sxs-lookup"><span data-stu-id="d44ce-123">Remarks</span></span>  
 <span data-ttu-id="d44ce-124">이 id를 사용 하 여 끝점에 연결 하는 WCF (secure Windows Communication Foundation) 클라이언트는 끝점을 사용 하 여 SSPI 인증을 수행할 때 SPN을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="d44ce-124">A secure Windows Communication Foundation (WCF) client that connects to an endpoint with this identity uses the SPN when performing SSPI authentication with the endpoint.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d44ce-125">참고자료</span><span class="sxs-lookup"><span data-stu-id="d44ce-125">See also</span></span>

- <xref:System.ServiceModel.Configuration.IdentityElement>
- <xref:System.ServiceModel.EndpointAddress>
- <xref:System.ServiceModel.EndpointAddress.Identity%2A>
- <xref:System.ServiceModel.SpnEndpointIdentity>
- [<span data-ttu-id="d44ce-126">서비스 ID 및 인증</span><span class="sxs-lookup"><span data-stu-id="d44ce-126">Service Identity and Authentication</span></span>](../../../wcf/feature-details/service-identity-and-authentication.md)
- [<span data-ttu-id="d44ce-127">\<identity></span><span class="sxs-lookup"><span data-stu-id="d44ce-127">\<identity></span></span>](identity.md)
