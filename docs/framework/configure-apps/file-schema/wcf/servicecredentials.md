---
description: 다음에 대해 자세히 알아보세요. <serviceCredentials>
title: <serviceCredentials>
ms.date: 03/30/2017
ms.assetid: 96db336c-4f7a-4193-81a5-910b8ffd804f
ms.openlocfilehash: c6fd39226ca2235d8f8253a7d2f2e363522870e5
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99682867"
---
# \<serviceCredentials>

<span data-ttu-id="7f502-102">서비스를 인증하는 데 사용되는 자격 증명 및 클라이언트 자격 증명 유효성 검사 관련 설정을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="7f502-102">Specifies the credential to be used in authenticating the service and the client credential validation-related settings.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<serviceCredentials>**  
  
## <a name="syntax"></a><span data-ttu-id="7f502-103">구문</span><span class="sxs-lookup"><span data-stu-id="7f502-103">Syntax</span></span>  
  
```xml  
<serviceCredentials type="String">
  <clientCertificate>
  </clientCertificate>
  <issuedTokenAuthentication>
  </issuedTokenAuthentication>
  <peer>
  </peer>
  <secureConversationAuthentication>
  </secureConversationAuthentication>
  <serviceCertificate>
  </serviceCertificate>
  <userNameAuthentication>
  </userNameAuthentication>
  <windowsAuthentication>
  </windowsAuthentication>
</serviceCredentials>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="7f502-104">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="7f502-104">Attributes and Elements</span></span>  

 <span data-ttu-id="7f502-105">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="7f502-105">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="7f502-106">특성</span><span class="sxs-lookup"><span data-stu-id="7f502-106">Attributes</span></span>  
  
|<span data-ttu-id="7f502-107">attribute</span><span class="sxs-lookup"><span data-stu-id="7f502-107">Attribute</span></span>|<span data-ttu-id="7f502-108">설명</span><span class="sxs-lookup"><span data-stu-id="7f502-108">Description</span></span>|  
|---------------|-----------------|  
|`type`|<span data-ttu-id="7f502-109">이 구성 요소의 형식을 지정하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="7f502-109">A string that specifies the type of this configuration element.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="7f502-110">자식 요소</span><span class="sxs-lookup"><span data-stu-id="7f502-110">Child Elements</span></span>  
  
|<span data-ttu-id="7f502-111">요소</span><span class="sxs-lookup"><span data-stu-id="7f502-111">Element</span></span>|<span data-ttu-id="7f502-112">설명</span><span class="sxs-lookup"><span data-stu-id="7f502-112">Description</span></span>|  
|-------------|-----------------|  
|[\<clientCertificate>](clientcertificate-of-servicecredentials.md)|<span data-ttu-id="7f502-113">클라이언트 인증서가 out-of-band 방식으로 제공될 때 사용할 인증서를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="7f502-113">Specifies the certificate to be used when the client certificate is available out-of-band.</span></span> <span data-ttu-id="7f502-114">이 요소는 클라이언트 인증서 유효성 검사 설정도 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="7f502-114">This element also specifies client certificate validation settings.</span></span> <span data-ttu-id="7f502-115">이 요소는 <xref:System.ServiceModel.Configuration.X509InitiatorCertificateServiceElement> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="7f502-115">This element is of type <xref:System.ServiceModel.Configuration.X509InitiatorCertificateServiceElement>.</span></span>|  
|[\<issuedTokenAuthentication>](issuedtokenauthentication-of-servicecredentials.md)|<span data-ttu-id="7f502-116">이 서비스에 대해 현재 발급된 토큰을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="7f502-116">Specifies the current issued token for this service.</span></span> <span data-ttu-id="7f502-117">이 요소는 <xref:System.ServiceModel.Configuration.IssuedTokenServiceElement> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="7f502-117">This element is of type <xref:System.ServiceModel.Configuration.IssuedTokenServiceElement>.</span></span>|  
|[\<peer>](peer-of-servicecredentials.md)|<span data-ttu-id="7f502-118">피어 노드에 대한 현재 자격 증명을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="7f502-118">Specifies the current credentials for a peer node.</span></span> <span data-ttu-id="7f502-119">이 요소는 <xref:System.ServiceModel.Configuration.PeerCredentialElement> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="7f502-119">This element is of type <xref:System.ServiceModel.Configuration.PeerCredentialElement>.</span></span>|  
|[\<secureConversationAuthentication>](secureconversationauthentication-of-servicecredential.md)|<span data-ttu-id="7f502-120">보안 대화에 대한 현재 자격 증명을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="7f502-120">Specifies the current credentials for a secure conversation.</span></span> <span data-ttu-id="7f502-121">이 요소는 <xref:System.ServiceModel.Configuration.SecureConversationServiceElement> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="7f502-121">This element is of type <xref:System.ServiceModel.Configuration.SecureConversationServiceElement>.</span></span>|  
|[\<serviceCertificate>](servicecertificate-of-servicecredentials.md)|<span data-ttu-id="7f502-122">자체 식별을 위해 서비스에서 사용되는 인증서를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="7f502-122">Specifies a certificate used by a service to identify itself.</span></span> <span data-ttu-id="7f502-123">이 요소는 <xref:System.ServiceModel.Configuration.X509RecipientCertificateServiceElement> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="7f502-123">This element is of type <xref:System.ServiceModel.Configuration.X509RecipientCertificateServiceElement>.</span></span>|  
|[\<userNameAuthentication>](usernameauthentication.md)|<span data-ttu-id="7f502-124">사용자 이름 암호 유효성 검사의 설정을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="7f502-124">Specifies the settings for username password validation.</span></span> <span data-ttu-id="7f502-125">이 요소는 <xref:System.ServiceModel.Configuration.UserNameServiceElement> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="7f502-125">This element is of type <xref:System.ServiceModel.Configuration.UserNameServiceElement>.</span></span>|  
|[\<windowsAuthentication>](windowsauthentication-of-servicecredentials.md)|<span data-ttu-id="7f502-126">Windows 자격 증명 유효성 검사의 설정을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="7f502-126">Specifies the settings for Windows credential validation.</span></span> <span data-ttu-id="7f502-127">이 요소는 <xref:System.ServiceModel.Configuration.WindowsServiceElement> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="7f502-127">This element is of type <xref:System.ServiceModel.Configuration.WindowsServiceElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="7f502-128">부모 요소</span><span class="sxs-lookup"><span data-stu-id="7f502-128">Parent Elements</span></span>  
  
|<span data-ttu-id="7f502-129">요소</span><span class="sxs-lookup"><span data-stu-id="7f502-129">Element</span></span>|<span data-ttu-id="7f502-130">설명</span><span class="sxs-lookup"><span data-stu-id="7f502-130">Description</span></span>|  
|-------------|-----------------|  
|[\<behavior>](behavior-of-endpointbehaviors.md)|<span data-ttu-id="7f502-131">동작 요소를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="7f502-131">Specifies a behavior element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="7f502-132">참고 항목</span><span class="sxs-lookup"><span data-stu-id="7f502-132">See also</span></span>

- <xref:System.ServiceModel.Configuration.ServiceCredentialsElement>
- <xref:System.ServiceModel.Description.ServiceCredentials>
- [<span data-ttu-id="7f502-133">보안 동작</span><span class="sxs-lookup"><span data-stu-id="7f502-133">Security Behaviors</span></span>](../../../wcf/feature-details/security-behaviors-in-wcf.md)
