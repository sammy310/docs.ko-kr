---
description: 다음에 대해 자세히 알아보세요. <rsa>
title: <rsa>
ms.date: 03/30/2017
ms.assetid: ae1f2267-e40d-42ff-8abf-06ab7067bdb9
ms.openlocfilehash: 5e558e608ec1196081166d01415e12fb2c3083b0
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99786878"
---
# \<rsa>

<span data-ttu-id="60463-102">이 id를 사용 하 여 끝점에 연결 하는 보안 WCF 클라이언트는 서버에서 제공 하는 클레임이이 id를 생성 하는 데 사용 된 RSA 공개 키를 포함 하는 클레임을 포함 하는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="60463-102">A secure WCF client that connects to an endpoint with this identity verifies that the claims presented by the server contain a claim that contains the RSA public key used to construct this identity.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<client>**](client.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpoint>**](endpoint-of-client.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<identity>**](identity.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<rsa>**  
  
## <a name="syntax"></a><span data-ttu-id="60463-103">구문</span><span class="sxs-lookup"><span data-stu-id="60463-103">Syntax</span></span>  
  
```xml  
<rsa value="String" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="60463-104">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="60463-104">Attributes and Elements</span></span>  

 <span data-ttu-id="60463-105">다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="60463-105">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="60463-106">특성</span><span class="sxs-lookup"><span data-stu-id="60463-106">Attributes</span></span>  
  
|<span data-ttu-id="60463-107">attribute</span><span class="sxs-lookup"><span data-stu-id="60463-107">Attribute</span></span>|<span data-ttu-id="60463-108">Description</span><span class="sxs-lookup"><span data-stu-id="60463-108">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="60463-109">값</span><span class="sxs-lookup"><span data-stu-id="60463-109">value</span></span>|<span data-ttu-id="60463-110">선택적 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="60463-110">Optional String.</span></span> <span data-ttu-id="60463-111">클라이언트에서 비교할 RSA 공개 키 값입니다.</span><span class="sxs-lookup"><span data-stu-id="60463-111">The RSA public key value to be compared with on the client.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="60463-112">자식 요소</span><span class="sxs-lookup"><span data-stu-id="60463-112">Child Elements</span></span>  

 <span data-ttu-id="60463-113">없음</span><span class="sxs-lookup"><span data-stu-id="60463-113">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="60463-114">부모 요소</span><span class="sxs-lookup"><span data-stu-id="60463-114">Parent Elements</span></span>  
  
|<span data-ttu-id="60463-115">요소</span><span class="sxs-lookup"><span data-stu-id="60463-115">Element</span></span>|<span data-ttu-id="60463-116">설명</span><span class="sxs-lookup"><span data-stu-id="60463-116">Description</span></span>|  
|-------------|-----------------|  
|[\<identity>](identity.md)|<span data-ttu-id="60463-117">클라이언트에서 인증할 서비스의 ID를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="60463-117">Specifies the identity of the service to be authenticated by the client.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="60463-118">설명</span><span class="sxs-lookup"><span data-stu-id="60463-118">Remarks</span></span>  

 <span data-ttu-id="60463-119">RSA 검사를 사용하면 RSA 키 또는 생성된 고유 RSA 키 값에 따라 하나의 인증서만 사용하도록 제한할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="60463-119">A RSA check enables you to specifically restrict authentication to a single certificate based upon its RSA key or generated your own RSA key value.</span></span> <span data-ttu-id="60463-120">이렇게 하면 RSA 키 값이 변경된 경우 기존 클라이언트와 작동하지 않는 서비스 대신 특정 RSA 키에 대한 인증을 강화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="60463-120">This enables stricter authentication of a specific RSA key at the expense of the service no longer working with existing clients if the RSA key value is changed.</span></span>  
  
 <span data-ttu-id="60463-121">Id를 사용 하 여 클라이언트에 대 한 서비스의 유효성을 검사 하는 방법에 대 한 자세한 내용은 [서비스 id 및 인증](../../../wcf/feature-details/service-identity-and-authentication.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="60463-121">For more information about using identity to validate a service to a client, see [Service Identity and Authentication](../../../wcf/feature-details/service-identity-and-authentication.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="60463-122">예제</span><span class="sxs-lookup"><span data-stu-id="60463-122">Example</span></span>  

 <span data-ttu-id="60463-123">다음 구성 코드에서는 서버를 인증하는 데 사용되는 X.509 인증서의 공개 키 값을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="60463-123">The following configuration code specifies the public key value of an X.509 certificate that is used to authenticate a server.</span></span>  
  
```xml  
<identity>
  <rsa value="0000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000" />
</identity>
```  
  
## <a name="see-also"></a><span data-ttu-id="60463-124">참고 항목</span><span class="sxs-lookup"><span data-stu-id="60463-124">See also</span></span>

- <xref:System.ServiceModel.Configuration.IdentityElement>
- <xref:System.ServiceModel.EndpointAddress>
- <xref:System.ServiceModel.EndpointAddress.Identity%2A>
- <xref:System.ServiceModel.RsaEndpointIdentity>
- [<span data-ttu-id="60463-125">서비스 ID 및 인증</span><span class="sxs-lookup"><span data-stu-id="60463-125">Service Identity and Authentication</span></span>](../../../wcf/feature-details/service-identity-and-authentication.md)
- [\<identity>](identity.md)
