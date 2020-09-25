---
title: <serviceCredentials>
ms.date: 03/30/2017
ms.assetid: 96db336c-4f7a-4193-81a5-910b8ffd804f
ms.openlocfilehash: 63368355027856118546bc70183b41864eddb0e6
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/24/2020
ms.locfileid: "91172881"
---
# \<serviceCredentials>

<span data-ttu-id="d100b-101">서비스를 인증하는 데 사용되는 자격 증명 및 클라이언트 자격 증명 유효성 검사 관련 설정을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="d100b-101">Specifies the credential to be used in authenticating the service and the client credential validation-related settings.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<serviceCredentials>**  
  
## <a name="syntax"></a><span data-ttu-id="d100b-102">구문</span><span class="sxs-lookup"><span data-stu-id="d100b-102">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="d100b-103">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="d100b-103">Attributes and Elements</span></span>  

 <span data-ttu-id="d100b-104">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="d100b-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="d100b-105">특성</span><span class="sxs-lookup"><span data-stu-id="d100b-105">Attributes</span></span>  
  
|<span data-ttu-id="d100b-106">attribute</span><span class="sxs-lookup"><span data-stu-id="d100b-106">Attribute</span></span>|<span data-ttu-id="d100b-107">설명</span><span class="sxs-lookup"><span data-stu-id="d100b-107">Description</span></span>|  
|---------------|-----------------|  
|`type`|<span data-ttu-id="d100b-108">이 구성 요소의 형식을 지정하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="d100b-108">A string that specifies the type of this configuration element.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="d100b-109">자식 요소</span><span class="sxs-lookup"><span data-stu-id="d100b-109">Child Elements</span></span>  
  
|<span data-ttu-id="d100b-110">요소</span><span class="sxs-lookup"><span data-stu-id="d100b-110">Element</span></span>|<span data-ttu-id="d100b-111">설명</span><span class="sxs-lookup"><span data-stu-id="d100b-111">Description</span></span>|  
|-------------|-----------------|  
|[\<clientCertificate>](clientcertificate-of-servicecredentials.md)|<span data-ttu-id="d100b-112">클라이언트 인증서가 out-of-band 방식으로 제공될 때 사용할 인증서를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="d100b-112">Specifies the certificate to be used when the client certificate is available out-of-band.</span></span> <span data-ttu-id="d100b-113">이 요소는 클라이언트 인증서 유효성 검사 설정도 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="d100b-113">This element also specifies client certificate validation settings.</span></span> <span data-ttu-id="d100b-114">이 요소는 <xref:System.ServiceModel.Configuration.X509InitiatorCertificateServiceElement> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="d100b-114">This element is of type <xref:System.ServiceModel.Configuration.X509InitiatorCertificateServiceElement>.</span></span>|  
|[\<issuedTokenAuthentication>](issuedtokenauthentication-of-servicecredentials.md)|<span data-ttu-id="d100b-115">이 서비스에 대해 현재 발급된 토큰을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="d100b-115">Specifies the current issued token for this service.</span></span> <span data-ttu-id="d100b-116">이 요소는 <xref:System.ServiceModel.Configuration.IssuedTokenServiceElement> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="d100b-116">This element is of type <xref:System.ServiceModel.Configuration.IssuedTokenServiceElement>.</span></span>|  
|[\<peer>](peer-of-servicecredentials.md)|<span data-ttu-id="d100b-117">피어 노드에 대한 현재 자격 증명을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="d100b-117">Specifies the current credentials for a peer node.</span></span> <span data-ttu-id="d100b-118">이 요소는 <xref:System.ServiceModel.Configuration.PeerCredentialElement> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="d100b-118">This element is of type <xref:System.ServiceModel.Configuration.PeerCredentialElement>.</span></span>|  
|[\<secureConversationAuthentication>](secureconversationauthentication-of-servicecredential.md)|<span data-ttu-id="d100b-119">보안 대화에 대한 현재 자격 증명을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="d100b-119">Specifies the current credentials for a secure conversation.</span></span> <span data-ttu-id="d100b-120">이 요소는 <xref:System.ServiceModel.Configuration.SecureConversationServiceElement> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="d100b-120">This element is of type <xref:System.ServiceModel.Configuration.SecureConversationServiceElement>.</span></span>|  
|[\<serviceCertificate>](servicecertificate-of-servicecredentials.md)|<span data-ttu-id="d100b-121">자체 식별을 위해 서비스에서 사용되는 인증서를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="d100b-121">Specifies a certificate used by a service to identify itself.</span></span> <span data-ttu-id="d100b-122">이 요소는 <xref:System.ServiceModel.Configuration.X509RecipientCertificateServiceElement> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="d100b-122">This element is of type <xref:System.ServiceModel.Configuration.X509RecipientCertificateServiceElement>.</span></span>|  
|[\<userNameAuthentication>](usernameauthentication.md)|<span data-ttu-id="d100b-123">사용자 이름 암호 유효성 검사의 설정을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="d100b-123">Specifies the settings for username password validation.</span></span> <span data-ttu-id="d100b-124">이 요소는 <xref:System.ServiceModel.Configuration.UserNameServiceElement> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="d100b-124">This element is of type <xref:System.ServiceModel.Configuration.UserNameServiceElement>.</span></span>|  
|[\<windowsAuthentication>](windowsauthentication-of-servicecredentials.md)|<span data-ttu-id="d100b-125">Windows 자격 증명 유효성 검사의 설정을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="d100b-125">Specifies the settings for Windows credential validation.</span></span> <span data-ttu-id="d100b-126">이 요소는 <xref:System.ServiceModel.Configuration.WindowsServiceElement> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="d100b-126">This element is of type <xref:System.ServiceModel.Configuration.WindowsServiceElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="d100b-127">부모 요소</span><span class="sxs-lookup"><span data-stu-id="d100b-127">Parent Elements</span></span>  
  
|<span data-ttu-id="d100b-128">요소</span><span class="sxs-lookup"><span data-stu-id="d100b-128">Element</span></span>|<span data-ttu-id="d100b-129">설명</span><span class="sxs-lookup"><span data-stu-id="d100b-129">Description</span></span>|  
|-------------|-----------------|  
|[\<behavior>](behavior-of-endpointbehaviors.md)|<span data-ttu-id="d100b-130">동작 요소를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="d100b-130">Specifies a behavior element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="d100b-131">참고 항목</span><span class="sxs-lookup"><span data-stu-id="d100b-131">See also</span></span>

- <xref:System.ServiceModel.Configuration.ServiceCredentialsElement>
- <xref:System.ServiceModel.Description.ServiceCredentials>
- [<span data-ttu-id="d100b-132">보안 동작</span><span class="sxs-lookup"><span data-stu-id="d100b-132">Security Behaviors</span></span>](../../../wcf/feature-details/security-behaviors-in-wcf.md)
