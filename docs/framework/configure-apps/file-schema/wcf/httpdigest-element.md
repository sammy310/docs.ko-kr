---
title: <httpDigest> 요소
ms.date: 03/30/2017
ms.assetid: 3da4f276-dfd9-4247-8c07-01d83618727c
ms.openlocfilehash: 0ffaba218d31a77407c598f8b7fa0260daa4e39c
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/15/2020
ms.locfileid: "90556904"
---
# <a name="httpdigest-element"></a><span data-ttu-id="46c00-102">\<httpDigest> 요소</span><span class="sxs-lookup"><span data-stu-id="46c00-102">\<httpDigest> Element</span></span>
<span data-ttu-id="46c00-103">서비스에게 클라이언트를 인증하는 데 사용되는 다이제스트 형식 자격 증명을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="46c00-103">Specifies a digest type credential used when authenticating the client to a service.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpointBehaviors>**](endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<clientCredentials>**](clientcredentials.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<httpDigest>**  
  
## <a name="syntax"></a><span data-ttu-id="46c00-104">구문</span><span class="sxs-lookup"><span data-stu-id="46c00-104">Syntax</span></span>  
  
```xml  
<httpDigest impersonationLevel="Identification/Impersonation/Delegation/Anonymous/None" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="46c00-105">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="46c00-105">Attributes and Elements</span></span>  
 <span data-ttu-id="46c00-106">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="46c00-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="46c00-107">특성</span><span class="sxs-lookup"><span data-stu-id="46c00-107">Attributes</span></span>  
  
|<span data-ttu-id="46c00-108">attribute</span><span class="sxs-lookup"><span data-stu-id="46c00-108">Attribute</span></span>|<span data-ttu-id="46c00-109">Description</span><span class="sxs-lookup"><span data-stu-id="46c00-109">Description</span></span>|  
|---------------|-----------------|  
|`impersonationLevel`|<span data-ttu-id="46c00-110">클라이언트가 서버에 전달하는 가장 기본 설정을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="46c00-110">Sets the impersonation preference that the client communicates to the server.</span></span> <span data-ttu-id="46c00-111">클라이언트에서 선택하는 가장 모드는 서버에 적용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="46c00-111">The impersonation mode that the client selects is not enforced on the server.</span></span> <span data-ttu-id="46c00-112">유효한 값은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="46c00-112">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="46c00-113">-식별: 서버는 클라이언트의 id와 권한을 가져올 수 있지만 클라이언트를 가장할 수는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="46c00-113">-   Identification: The server can get the identity and privileges of the client, but cannot impersonate the client.</span></span><br /><span data-ttu-id="46c00-114">-가장: 서버는 로컬 시스템에서 클라이언트의 보안 컨텍스트를 가장할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="46c00-114">-   Impersonation: The server can impersonate the client's security context on the local system.</span></span><br /><span data-ttu-id="46c00-115">-위임: 서버는 원격 시스템에서 클라이언트의 보안 컨텍스트를 가장할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="46c00-115">-   Delegation: The server can impersonate the client's security context on remote systems.</span></span><br /><span data-ttu-id="46c00-116">-Anonymous: 서버에서 클라이언트를 가장 하거나 식별할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="46c00-116">-   Anonymous: The server cannot impersonate or identify the client.</span></span><br /><span data-ttu-id="46c00-117">-None: 가장 수준이 할당 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="46c00-117">-   None: An impersonation level is not assigned.</span></span><br /><br /> <span data-ttu-id="46c00-118">기본값은 Identification입니다.</span><span class="sxs-lookup"><span data-stu-id="46c00-118">The default is Identification.</span></span> <span data-ttu-id="46c00-119">이 특성은 <xref:System.Security.Principal.TokenImpersonationLevel> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="46c00-119">This attribute is of type <xref:System.Security.Principal.TokenImpersonationLevel>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="46c00-120">자식 요소</span><span class="sxs-lookup"><span data-stu-id="46c00-120">Child Elements</span></span>  
 <span data-ttu-id="46c00-121">None</span><span class="sxs-lookup"><span data-stu-id="46c00-121">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="46c00-122">부모 요소</span><span class="sxs-lookup"><span data-stu-id="46c00-122">Parent Elements</span></span>  
  
|<span data-ttu-id="46c00-123">요소</span><span class="sxs-lookup"><span data-stu-id="46c00-123">Element</span></span>|<span data-ttu-id="46c00-124">Description</span><span class="sxs-lookup"><span data-stu-id="46c00-124">Description</span></span>|  
|-------------|-----------------|  
|[\<clientCredentials>](clientcredentials.md)|<span data-ttu-id="46c00-125">클라이언트를 서비스에 인증할 때 사용되는 자격 증명을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="46c00-125">Specifies the credentials used to authenticate a client to a service.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="46c00-126">설명</span><span class="sxs-lookup"><span data-stu-id="46c00-126">Remarks</span></span>  
 <span data-ttu-id="46c00-127">다이제스트는 알고리즘과 입력 집합을 통해 확인되는 해시입니다.</span><span class="sxs-lookup"><span data-stu-id="46c00-127">A digest is a hash determined by using an algorithm and a set of inputs.</span></span> <span data-ttu-id="46c00-128">인증자 및 인증된 사용자는 알고리즘에 동의하고 입력으로 사용된 데이터를 교환합니다.</span><span class="sxs-lookup"><span data-stu-id="46c00-128">The authenticator and the authenticated agree upon an algorithm and exchange the data used as inputs.</span></span> <span data-ttu-id="46c00-129">클라이언트는 해시를 계산하여 서비스로 보냅니다.</span><span class="sxs-lookup"><span data-stu-id="46c00-129">The client can calculate the hash and send it to the service.</span></span> <span data-ttu-id="46c00-130">서비스에서도 해시를 계산하여 값을 비교합니다.</span><span class="sxs-lookup"><span data-stu-id="46c00-130">The service also calculates the hash and compares the values.</span></span> <span data-ttu-id="46c00-131">값이 일치하면 클라이언트가 확인됩니다.</span><span class="sxs-lookup"><span data-stu-id="46c00-131">A match validates the client.</span></span>  
  
 <span data-ttu-id="46c00-132">이 기능은 Windows 및 IIS(인터넷 정보 서비스)의 Active Directory를 통해 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="46c00-132">This feature must be enabled with Active Directory on Windows and Internet Information Services (IIS).</span></span> <span data-ttu-id="46c00-133">자세한 내용은 [IIS 6.0의 다이제스트 인증](/previous-versions/windows/it-pro/windows-server-2003/cc782661(v=ws.10))을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="46c00-133">For more information, see [Digest Authentication in IIS 6.0](/previous-versions/windows/it-pro/windows-server-2003/cc782661(v=ws.10)).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="46c00-134">추가 정보</span><span class="sxs-lookup"><span data-stu-id="46c00-134">See also</span></span>

- <xref:System.ServiceModel.Configuration.ClientCredentialsElement>
- <xref:System.ServiceModel.Configuration.ClientCredentialsElement.HttpDigest%2A>
- <xref:System.ServiceModel.Description.ClientCredentials>
- <xref:System.ServiceModel.Description.ClientCredentials.HttpDigest%2A>
- <xref:System.ServiceModel.Configuration.HttpDigestClientElement>
- <xref:System.ServiceModel.Security.HttpDigestClientCredential>
- [<span data-ttu-id="46c00-135">보안 동작</span><span class="sxs-lookup"><span data-stu-id="46c00-135">Security Behaviors</span></span>](../../../wcf/feature-details/security-behaviors-in-wcf.md)
- [<span data-ttu-id="46c00-136">클라이언트에 보안 설정</span><span class="sxs-lookup"><span data-stu-id="46c00-136">Securing Clients</span></span>](../../../wcf/securing-clients.md)
- [<span data-ttu-id="46c00-137">인증서 사용</span><span class="sxs-lookup"><span data-stu-id="46c00-137">Working with Certificates</span></span>](../../../wcf/feature-details/working-with-certificates.md)
- [<span data-ttu-id="46c00-138">서비스 및 클라이언트에 보안 설정</span><span class="sxs-lookup"><span data-stu-id="46c00-138">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
