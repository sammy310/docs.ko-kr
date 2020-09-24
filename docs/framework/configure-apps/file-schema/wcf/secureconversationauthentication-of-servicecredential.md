---
title: <serviceCredential>의 <secureConversationAuthentication>
ms.date: 03/30/2017
ms.assetid: 0bd3fac7-befd-4a45-ba51-c200b33be0fd
ms.openlocfilehash: be2a9298a78de1503271f41076b9f5bb63c73f74
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/24/2020
ms.locfileid: "91162243"
---
# <a name="secureconversationauthentication-of-servicecredential"></a><span data-ttu-id="56f48-102">\<serviceCredential>의 \<secureConversationAuthentication></span><span class="sxs-lookup"><span data-stu-id="56f48-102">\<secureConversationAuthentication> of \<serviceCredential></span></span>

<span data-ttu-id="56f48-103">보안 대화 서비스 설정을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="56f48-103">Specifies the settings for a secure conversation service.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceCredentials>**](servicecredentials.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<secureConversationAuthentication>**  
  
## <a name="syntax"></a><span data-ttu-id="56f48-104">구문</span><span class="sxs-lookup"><span data-stu-id="56f48-104">Syntax</span></span>  
  
```xml  
<secureConversationAuthentication securityStateEncoderType="String" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="56f48-105">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="56f48-105">Attributes and Elements</span></span>  

 <span data-ttu-id="56f48-106">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="56f48-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="56f48-107">특성</span><span class="sxs-lookup"><span data-stu-id="56f48-107">Attributes</span></span>  
  
|<span data-ttu-id="56f48-108">attribute</span><span class="sxs-lookup"><span data-stu-id="56f48-108">Attribute</span></span>|<span data-ttu-id="56f48-109">설명</span><span class="sxs-lookup"><span data-stu-id="56f48-109">Description</span></span>|  
|---------------|-----------------|  
|`securityStateEncoderType`|<span data-ttu-id="56f48-110">사용할 <xref:System.ServiceModel.Security.SecurityStateEncoder> 형식을 지정하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="56f48-110">A string that specifies the type of <xref:System.ServiceModel.Security.SecurityStateEncoder> to be used.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="56f48-111">자식 요소</span><span class="sxs-lookup"><span data-stu-id="56f48-111">Child Elements</span></span>  

 <span data-ttu-id="56f48-112">없음</span><span class="sxs-lookup"><span data-stu-id="56f48-112">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="56f48-113">부모 요소</span><span class="sxs-lookup"><span data-stu-id="56f48-113">Parent Elements</span></span>  
  
|<span data-ttu-id="56f48-114">요소</span><span class="sxs-lookup"><span data-stu-id="56f48-114">Element</span></span>|<span data-ttu-id="56f48-115">설명</span><span class="sxs-lookup"><span data-stu-id="56f48-115">Description</span></span>|  
|-------------|-----------------|  
|[\<serviceCredentials>](servicecredentials.md)|<span data-ttu-id="56f48-116">서비스를 인증하는 데 사용되는 자격 증명 및 클라이언트 자격 증명 유효성 검사 관련 설정을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="56f48-116">Specifies the credential to be used in authenticating the service, and the client credential validation-related settings.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="56f48-117">설명</span><span class="sxs-lookup"><span data-stu-id="56f48-117">Remarks</span></span>  

 <span data-ttu-id="56f48-118">SCT(보안 컨텍스트 토큰) 쿠키 serialization을 위한 알려진 클레임 형식 목록과 쿠키 정보를 인코딩 및 보안할 인코더를 지정하려면 이 구성 요소를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="56f48-118">Use this configuration element to specify a list of known claim types for the Security Context Token (SCT) cookies serialization, as well as an encoder to encode and secure cookies information.</span></span> <span data-ttu-id="56f48-119">SCT에 대한 자세한 내용은 <xref:System.ServiceModel.Security.SecureConversationServiceCredential>을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="56f48-119">For more information on SCT, see <xref:System.ServiceModel.Security.SecureConversationServiceCredential>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="56f48-120">참고 항목</span><span class="sxs-lookup"><span data-stu-id="56f48-120">See also</span></span>

- <xref:System.ServiceModel.Configuration.SecureConversationServiceElement>
- <xref:System.ServiceModel.Configuration.ServiceCredentialsElement.SecureConversationAuthentication%2A>
- <xref:System.ServiceModel.Description.ServiceCredentials.SecureConversationAuthentication%2A>
- <xref:System.ServiceModel.Security.SecureConversationServiceCredential>
