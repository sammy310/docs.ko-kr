---
description: '다음에 대 한 자세한 정보: <windows> <clientCredentials> 요소'
title: <windows> of <clientCredentials> 요소
ms.date: 03/30/2017
ms.assetid: 793e41c2-31ea-4159-abbc-2123bf097233
ms.openlocfilehash: d693ad914dfa02ef12a7c8520ca84be3a9595e73
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99682425"
---
# <a name="windows-of-clientcredentials-element"></a><span data-ttu-id="fe3c5-103">\<windows> of \<clientCredentials> 요소</span><span class="sxs-lookup"><span data-stu-id="fe3c5-103">\<windows> of \<clientCredentials> Element</span></span>

<span data-ttu-id="fe3c5-104">클라이언트를 나타내는 데 사용되는 Windows 자격 증명의 설정을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="fe3c5-104">Specifies the settings for a Windows credential to be used to represent the client.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpointBehaviors>**](endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<clientCredentials>**](clientcredentials.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<windows>**  
  
## <a name="syntax"></a><span data-ttu-id="fe3c5-105">구문</span><span class="sxs-lookup"><span data-stu-id="fe3c5-105">Syntax</span></span>  
  
```xml  
<windows allowedImpersonationLevel="Identification/Impersonation/Delegation/Anonymous/None"
         allowNtlm="Boolean" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="fe3c5-106">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="fe3c5-106">Attributes and Elements</span></span>  

 <span data-ttu-id="fe3c5-107">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="fe3c5-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="fe3c5-108">특성</span><span class="sxs-lookup"><span data-stu-id="fe3c5-108">Attributes</span></span>  
  
|<span data-ttu-id="fe3c5-109">attribute</span><span class="sxs-lookup"><span data-stu-id="fe3c5-109">Attribute</span></span>|<span data-ttu-id="fe3c5-110">설명</span><span class="sxs-lookup"><span data-stu-id="fe3c5-110">Description</span></span>|  
|---------------|-----------------|  
|`allowedImpersonationLevel`|<span data-ttu-id="fe3c5-111">클라이언트가 서버에 전달하는 가장 기본 설정을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="fe3c5-111">Sets the impersonation preference that the client communicates to the server.</span></span> <span data-ttu-id="fe3c5-112">클라이언트에서 선택하는 가장 모드는 서버에 적용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="fe3c5-112">The impersonation mode that the client selects is not enforced on the server.</span></span> <span data-ttu-id="fe3c5-113">유효한 값은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="fe3c5-113">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="fe3c5-114">-식별: 서버는 클라이언트의 id와 권한을 가져올 수 있지만 클라이언트를 가장할 수는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="fe3c5-114">-   Identification: The server can get the identity and privileges of the client, but cannot impersonate the client.</span></span><br /><span data-ttu-id="fe3c5-115">-가장: 서버는 로컬 시스템에서 클라이언트의 보안 컨텍스트를 가장할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fe3c5-115">-   Impersonation: The server can impersonate the client's security context on the local system.</span></span><br /><span data-ttu-id="fe3c5-116">-위임: 서버는 원격 시스템에서 클라이언트의 보안 컨텍스트를 가장할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fe3c5-116">-   Delegation: The server can impersonate the client's security context on remote systems.</span></span><br /><span data-ttu-id="fe3c5-117">-Anonymous: 서버에서 클라이언트를 가장 하거나 식별할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="fe3c5-117">-   Anonymous: The server cannot impersonate or identify the client.</span></span><br /><span data-ttu-id="fe3c5-118">-None: 가장 수준이 할당 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="fe3c5-118">-   None: An impersonation level is not assigned.</span></span><br /><br /> <span data-ttu-id="fe3c5-119">기본값은 Identification입니다.</span><span class="sxs-lookup"><span data-stu-id="fe3c5-119">The default is Identification.</span></span> <span data-ttu-id="fe3c5-120">이 특성은 <xref:System.Security.Principal.TokenImpersonationLevel> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="fe3c5-120">This attribute is of type <xref:System.Security.Principal.TokenImpersonationLevel>.</span></span>|  
|`allowNtlm`|<span data-ttu-id="fe3c5-121">이 속성을 `true`로 설정하면 Kerberos를 사용할 수 없는 경우 NTLM으로 인증을 다운그레이드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fe3c5-121">Setting this property to `true` allows authentication to downgrade to NTLM if Kerberos is not available.</span></span><br /><br /> <span data-ttu-id="fe3c5-122">이 속성을 설정 `false` 하면 NTLM이 사용 하는 경우 예외를 throw 하는 최상의 노력을 하도록 Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="fe3c5-122">Setting this property to `false` causes Windows Communication Foundation (WCF) to make a best-effort to throw an exception if NTLM is used.</span></span> <span data-ttu-id="fe3c5-123">이 속성을 `false`로 설정하면 유선을 통해 NTLM 자격 증명을 보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fe3c5-123">Note that setting this property to `false` may not prevent NTLM credentials from being sent over the wire.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="fe3c5-124">자식 요소</span><span class="sxs-lookup"><span data-stu-id="fe3c5-124">Child Elements</span></span>  

 <span data-ttu-id="fe3c5-125">없음</span><span class="sxs-lookup"><span data-stu-id="fe3c5-125">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="fe3c5-126">부모 요소</span><span class="sxs-lookup"><span data-stu-id="fe3c5-126">Parent Elements</span></span>  
  
|<span data-ttu-id="fe3c5-127">요소</span><span class="sxs-lookup"><span data-stu-id="fe3c5-127">Element</span></span>|<span data-ttu-id="fe3c5-128">설명</span><span class="sxs-lookup"><span data-stu-id="fe3c5-128">Description</span></span>|  
|-------------|-----------------|  
|[\<clientCredentials>](clientcredentials.md)|<span data-ttu-id="fe3c5-129">클라이언트를 서비스에 인증할 때 사용되는 자격 증명을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="fe3c5-129">Specifies the credentials used to authenticate the client to the service.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="fe3c5-130">참고 항목</span><span class="sxs-lookup"><span data-stu-id="fe3c5-130">See also</span></span>

- <xref:System.ServiceModel.Configuration.WindowsClientElement>
- <xref:System.ServiceModel.Configuration.ClientCredentialsElement>
- <xref:System.ServiceModel.Description.ClientCredentials>
- <xref:System.ServiceModel.Configuration.ClientCredentialsElement.Windows%2A>
- <xref:System.ServiceModel.Description.ClientCredentials>
- <xref:System.ServiceModel.Description.ClientCredentials.Windows%2A>
- <xref:System.ServiceModel.Security.WindowsClientCredential>
- [<span data-ttu-id="fe3c5-131">클라이언트에 보안 설정</span><span class="sxs-lookup"><span data-stu-id="fe3c5-131">Securing Clients</span></span>](../../../wcf/securing-clients.md)
- [<span data-ttu-id="fe3c5-132">인증서 사용</span><span class="sxs-lookup"><span data-stu-id="fe3c5-132">Working with Certificates</span></span>](../../../wcf/feature-details/working-with-certificates.md)
- [<span data-ttu-id="fe3c5-133">서비스 및 클라이언트에 보안 설정</span><span class="sxs-lookup"><span data-stu-id="fe3c5-133">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
