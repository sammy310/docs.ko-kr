---
title: <httpDigest> 요소
ms.date: 03/30/2017
ms.assetid: 3da4f276-dfd9-4247-8c07-01d83618727c
ms.openlocfilehash: f392ebf4eeb6a008952fd4d5ef4e301e57f6eb31
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/06/2019
ms.locfileid: "70397987"
---
# <a name="httpdigest-element"></a><span data-ttu-id="8a59c-102">\<httpDigest > 요소</span><span class="sxs-lookup"><span data-stu-id="8a59c-102">\<httpDigest> Element</span></span>
<span data-ttu-id="8a59c-103">서비스에게 클라이언트를 인증하는 데 사용되는 다이제스트 형식 자격 증명을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="8a59c-103">Specifies a digest type credential used when authenticating the client to a service.</span></span>  
  
<span data-ttu-id="8a59c-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="8a59c-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="8a59c-105">&nbsp;&nbsp;[ **\<System.servicemodel >** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="8a59c-105">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="8a59c-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<동작 >** ](behaviors.md)</span><span class="sxs-lookup"><span data-stu-id="8a59c-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)</span></span>\
<span data-ttu-id="8a59c-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<endpointBehaviors >** ](endpointbehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="8a59c-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpointBehaviors>**](endpointbehaviors.md)</span></span>\
<span data-ttu-id="8a59c-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<동작 >** ](behavior-of-endpointbehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="8a59c-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-endpointbehaviors.md)</span></span>\
<span data-ttu-id="8a59c-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<clientCredentials >** ](clientcredentials.md)</span><span class="sxs-lookup"><span data-stu-id="8a59c-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<clientCredentials>**](clientcredentials.md)</span></span>\
<span data-ttu-id="8a59c-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<httpDigest >**</span><span class="sxs-lookup"><span data-stu-id="8a59c-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<httpDigest>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8a59c-111">구문</span><span class="sxs-lookup"><span data-stu-id="8a59c-111">Syntax</span></span>  
  
```xml  
<digest impersonationLevel="Identification/Impersonation/Delegation/Anonymous/None" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="8a59c-112">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="8a59c-112">Attributes and Elements</span></span>  
 <span data-ttu-id="8a59c-113">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="8a59c-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="8a59c-114">특성</span><span class="sxs-lookup"><span data-stu-id="8a59c-114">Attributes</span></span>  
  
|<span data-ttu-id="8a59c-115">특성</span><span class="sxs-lookup"><span data-stu-id="8a59c-115">Attribute</span></span>|<span data-ttu-id="8a59c-116">Description</span><span class="sxs-lookup"><span data-stu-id="8a59c-116">Description</span></span>|  
|---------------|-----------------|  
|`impersonationLevel`|<span data-ttu-id="8a59c-117">클라이언트가 서버에 전달하는 가장 기본 설정을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="8a59c-117">Sets the impersonation preference that the client communicates to the server.</span></span> <span data-ttu-id="8a59c-118">클라이언트에서 선택하는 가장 모드는 서버에 적용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8a59c-118">The impersonation mode that the client selects is not enforced on the server.</span></span> <span data-ttu-id="8a59c-119">유효한 값은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="8a59c-119">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="8a59c-120">등록 서버는 클라이언트의 id와 권한을 가져올 수 있지만 클라이언트를 가장할 수는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="8a59c-120">-   Identification: The server can get the identity and privileges of the client, but cannot impersonate the client.</span></span><br /><span data-ttu-id="8a59c-121">가장 서버는 로컬 시스템에서 클라이언트의 보안 컨텍스트를 가장할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8a59c-121">-   Impersonation: The server can impersonate the client's security context on the local system.</span></span><br /><span data-ttu-id="8a59c-122">대리인 서버는 원격 시스템에서 클라이언트의 보안 컨텍스트를 가장할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8a59c-122">-   Delegation: The server can impersonate the client's security context on remote systems.</span></span><br /><span data-ttu-id="8a59c-123">익명 서버에서 클라이언트를 가장 하거나 식별할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="8a59c-123">-   Anonymous: The server cannot impersonate or identify the client.</span></span><br /><span data-ttu-id="8a59c-124">없음을 가장 수준이 할당 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8a59c-124">-   None: An impersonation level is not assigned.</span></span><br /><br /> <span data-ttu-id="8a59c-125">기본값은 Identification입니다.</span><span class="sxs-lookup"><span data-stu-id="8a59c-125">The default is Identification.</span></span> <span data-ttu-id="8a59c-126">이 특성은 <xref:System.Security.Principal.TokenImpersonationLevel> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="8a59c-126">This attribute is of type <xref:System.Security.Principal.TokenImpersonationLevel>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="8a59c-127">자식 요소</span><span class="sxs-lookup"><span data-stu-id="8a59c-127">Child Elements</span></span>  
 <span data-ttu-id="8a59c-128">없음</span><span class="sxs-lookup"><span data-stu-id="8a59c-128">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="8a59c-129">부모 요소</span><span class="sxs-lookup"><span data-stu-id="8a59c-129">Parent Elements</span></span>  
  
|<span data-ttu-id="8a59c-130">요소</span><span class="sxs-lookup"><span data-stu-id="8a59c-130">Element</span></span>|<span data-ttu-id="8a59c-131">설명</span><span class="sxs-lookup"><span data-stu-id="8a59c-131">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="8a59c-132">\<clientCredentials></span><span class="sxs-lookup"><span data-stu-id="8a59c-132">\<clientCredentials></span></span>](clientcredentials.md)|<span data-ttu-id="8a59c-133">클라이언트를 서비스에 인증할 때 사용되는 자격 증명을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="8a59c-133">Specifies the credentials used to authenticate a client to a service.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8a59c-134">설명</span><span class="sxs-lookup"><span data-stu-id="8a59c-134">Remarks</span></span>  
 <span data-ttu-id="8a59c-135">다이제스트는 알고리즘과 입력 집합을 통해 확인되는 해시입니다.</span><span class="sxs-lookup"><span data-stu-id="8a59c-135">A digest is a hash determined by using an algorithm and a set of inputs.</span></span> <span data-ttu-id="8a59c-136">인증자 및 인증된 사용자는 알고리즘에 동의하고 입력으로 사용된 데이터를 교환합니다.</span><span class="sxs-lookup"><span data-stu-id="8a59c-136">The authenticator and the authenticated agree upon an algorithm and exchange the data used as inputs.</span></span> <span data-ttu-id="8a59c-137">클라이언트는 해시를 계산하여 서비스로 보냅니다.</span><span class="sxs-lookup"><span data-stu-id="8a59c-137">The client can calculate the hash and send it to the service.</span></span> <span data-ttu-id="8a59c-138">서비스에서도 해시를 계산하여 값을 비교합니다.</span><span class="sxs-lookup"><span data-stu-id="8a59c-138">The service also calculates the hash and compares the values.</span></span> <span data-ttu-id="8a59c-139">값이 일치하면 클라이언트가 확인됩니다.</span><span class="sxs-lookup"><span data-stu-id="8a59c-139">A match validates the client.</span></span>  
  
 <span data-ttu-id="8a59c-140">이 기능은 Windows 및 IIS(인터넷 정보 서비스)의 Active Directory를 통해 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8a59c-140">This feature must be enabled with Active Directory on Windows and Internet Information Services (IIS).</span></span> <span data-ttu-id="8a59c-141">자세한 내용은 [IIS 6.0의 다이제스트 인증](https://go.microsoft.com/fwlink/?LinkId=88443)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="8a59c-141">For more information, see [Digest Authentication in IIS 6.0](https://go.microsoft.com/fwlink/?LinkId=88443).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8a59c-142">참고자료</span><span class="sxs-lookup"><span data-stu-id="8a59c-142">See also</span></span>

- <xref:System.ServiceModel.Configuration.ClientCredentialsElement>
- <xref:System.ServiceModel.Configuration.ClientCredentialsElement.HttpDigest%2A>
- <xref:System.ServiceModel.Description.ClientCredentials>
- <xref:System.ServiceModel.Description.ClientCredentials.HttpDigest%2A>
- <xref:System.ServiceModel.Configuration.HttpDigestClientElement>
- <xref:System.ServiceModel.Security.HttpDigestClientCredential>
- [<span data-ttu-id="8a59c-143">보안 동작</span><span class="sxs-lookup"><span data-stu-id="8a59c-143">Security Behaviors</span></span>](../../../wcf/feature-details/security-behaviors-in-wcf.md)
- [<span data-ttu-id="8a59c-144">클라이언트에 보안 설정</span><span class="sxs-lookup"><span data-stu-id="8a59c-144">Securing Clients</span></span>](../../../wcf/securing-clients.md)
- [<span data-ttu-id="8a59c-145">인증서 작업</span><span class="sxs-lookup"><span data-stu-id="8a59c-145">Working with Certificates</span></span>](../../../wcf/feature-details/working-with-certificates.md)
- [<span data-ttu-id="8a59c-146">서비스 및 클라이언트에 보안 설정</span><span class="sxs-lookup"><span data-stu-id="8a59c-146">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
