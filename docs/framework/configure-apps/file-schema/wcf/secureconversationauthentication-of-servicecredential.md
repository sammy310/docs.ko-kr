---
description: '다음에 대 한 자세한 정보:: <secureConversationAuthentication><serviceCredential>'
title: <serviceCredential>의 <secureConversationAuthentication>
ms.date: 03/30/2017
ms.assetid: 0bd3fac7-befd-4a45-ba51-c200b33be0fd
ms.openlocfilehash: 8f95b4009111996d2a5c1133c9ef762375b4e3e2
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99683322"
---
# <a name="secureconversationauthentication-of-servicecredential"></a><span data-ttu-id="31f52-103">\<serviceCredential>의 \<secureConversationAuthentication></span><span class="sxs-lookup"><span data-stu-id="31f52-103">\<secureConversationAuthentication> of \<serviceCredential></span></span>

<span data-ttu-id="31f52-104">보안 대화 서비스 설정을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="31f52-104">Specifies the settings for a secure conversation service.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceCredentials>**](servicecredentials.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<secureConversationAuthentication>**  
  
## <a name="syntax"></a><span data-ttu-id="31f52-105">구문</span><span class="sxs-lookup"><span data-stu-id="31f52-105">Syntax</span></span>  
  
```xml  
<secureConversationAuthentication securityStateEncoderType="String" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="31f52-106">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="31f52-106">Attributes and Elements</span></span>  

 <span data-ttu-id="31f52-107">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="31f52-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="31f52-108">특성</span><span class="sxs-lookup"><span data-stu-id="31f52-108">Attributes</span></span>  
  
|<span data-ttu-id="31f52-109">attribute</span><span class="sxs-lookup"><span data-stu-id="31f52-109">Attribute</span></span>|<span data-ttu-id="31f52-110">설명</span><span class="sxs-lookup"><span data-stu-id="31f52-110">Description</span></span>|  
|---------------|-----------------|  
|`securityStateEncoderType`|<span data-ttu-id="31f52-111">사용할 <xref:System.ServiceModel.Security.SecurityStateEncoder> 형식을 지정하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="31f52-111">A string that specifies the type of <xref:System.ServiceModel.Security.SecurityStateEncoder> to be used.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="31f52-112">자식 요소</span><span class="sxs-lookup"><span data-stu-id="31f52-112">Child Elements</span></span>  

 <span data-ttu-id="31f52-113">없음</span><span class="sxs-lookup"><span data-stu-id="31f52-113">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="31f52-114">부모 요소</span><span class="sxs-lookup"><span data-stu-id="31f52-114">Parent Elements</span></span>  
  
|<span data-ttu-id="31f52-115">요소</span><span class="sxs-lookup"><span data-stu-id="31f52-115">Element</span></span>|<span data-ttu-id="31f52-116">설명</span><span class="sxs-lookup"><span data-stu-id="31f52-116">Description</span></span>|  
|-------------|-----------------|  
|[\<serviceCredentials>](servicecredentials.md)|<span data-ttu-id="31f52-117">서비스를 인증하는 데 사용되는 자격 증명 및 클라이언트 자격 증명 유효성 검사 관련 설정을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="31f52-117">Specifies the credential to be used in authenticating the service, and the client credential validation-related settings.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="31f52-118">설명</span><span class="sxs-lookup"><span data-stu-id="31f52-118">Remarks</span></span>  

 <span data-ttu-id="31f52-119">SCT(보안 컨텍스트 토큰) 쿠키 serialization을 위한 알려진 클레임 형식 목록과 쿠키 정보를 인코딩 및 보안할 인코더를 지정하려면 이 구성 요소를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="31f52-119">Use this configuration element to specify a list of known claim types for the Security Context Token (SCT) cookies serialization, as well as an encoder to encode and secure cookies information.</span></span> <span data-ttu-id="31f52-120">SCT에 대한 자세한 내용은 <xref:System.ServiceModel.Security.SecureConversationServiceCredential>을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="31f52-120">For more information on SCT, see <xref:System.ServiceModel.Security.SecureConversationServiceCredential>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="31f52-121">참고 항목</span><span class="sxs-lookup"><span data-stu-id="31f52-121">See also</span></span>

- <xref:System.ServiceModel.Configuration.SecureConversationServiceElement>
- <xref:System.ServiceModel.Configuration.ServiceCredentialsElement.SecureConversationAuthentication%2A>
- <xref:System.ServiceModel.Description.ServiceCredentials.SecureConversationAuthentication%2A>
- <xref:System.ServiceModel.Security.SecureConversationServiceCredential>
