---
title: <secureConversationAuthentication> / <serviceCredential>
ms.date: 03/30/2017
ms.assetid: 0bd3fac7-befd-4a45-ba51-c200b33be0fd
ms.openlocfilehash: f35392b91d047c46e65ce433ef544b86cf6c88c6
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59083701"
---
# <a name="secureconversationauthentication-of-servicecredential"></a><span data-ttu-id="d5a19-102">\<secureConversationAuthentication >의 \<serviceCredential ></span><span class="sxs-lookup"><span data-stu-id="d5a19-102">\<secureConversationAuthentication> of \<serviceCredential></span></span>
<span data-ttu-id="d5a19-103">보안 대화 서비스 설정을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="d5a19-103">Specifies the settings for a secure conversation service.</span></span>  
  
 <span data-ttu-id="d5a19-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="d5a19-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="d5a19-105">\<behaviors></span><span class="sxs-lookup"><span data-stu-id="d5a19-105">\<behaviors></span></span>  
<span data-ttu-id="d5a19-106">\<serviceBehaviors></span><span class="sxs-lookup"><span data-stu-id="d5a19-106">\<serviceBehaviors></span></span>  
<span data-ttu-id="d5a19-107">\<behavior></span><span class="sxs-lookup"><span data-stu-id="d5a19-107">\<behavior></span></span>  
<span data-ttu-id="d5a19-108">\<serviceCredentials></span><span class="sxs-lookup"><span data-stu-id="d5a19-108">\<serviceCredentials></span></span>  
<span data-ttu-id="d5a19-109">\<secureConversationAuthentication></span><span class="sxs-lookup"><span data-stu-id="d5a19-109">\<secureConversationAuthentication></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d5a19-110">구문</span><span class="sxs-lookup"><span data-stu-id="d5a19-110">Syntax</span></span>  
  
```xml  
<secureConversationAuthentication securityStateEncoderType="String" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="d5a19-111">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="d5a19-111">Attributes and Elements</span></span>  
 <span data-ttu-id="d5a19-112">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="d5a19-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="d5a19-113">특성</span><span class="sxs-lookup"><span data-stu-id="d5a19-113">Attributes</span></span>  
  
|<span data-ttu-id="d5a19-114">특성</span><span class="sxs-lookup"><span data-stu-id="d5a19-114">Attribute</span></span>|<span data-ttu-id="d5a19-115">설명</span><span class="sxs-lookup"><span data-stu-id="d5a19-115">Description</span></span>|  
|---------------|-----------------|  
|`securityStateEncoderType`|<span data-ttu-id="d5a19-116">사용할 <xref:System.ServiceModel.Security.SecurityStateEncoder> 형식을 지정하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="d5a19-116">A string that specifies the type of <xref:System.ServiceModel.Security.SecurityStateEncoder> to be used.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="d5a19-117">자식 요소</span><span class="sxs-lookup"><span data-stu-id="d5a19-117">Child Elements</span></span>  
 <span data-ttu-id="d5a19-118">없음</span><span class="sxs-lookup"><span data-stu-id="d5a19-118">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="d5a19-119">부모 요소</span><span class="sxs-lookup"><span data-stu-id="d5a19-119">Parent Elements</span></span>  
  
|<span data-ttu-id="d5a19-120">요소</span><span class="sxs-lookup"><span data-stu-id="d5a19-120">Element</span></span>|<span data-ttu-id="d5a19-121">설명</span><span class="sxs-lookup"><span data-stu-id="d5a19-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="d5a19-122">\<serviceCredentials></span><span class="sxs-lookup"><span data-stu-id="d5a19-122">\<serviceCredentials></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/servicecredentials.md)|<span data-ttu-id="d5a19-123">서비스를 인증하는 데 사용되는 자격 증명 및 클라이언트 자격 증명 유효성 검사 관련 설정을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="d5a19-123">Specifies the credential to be used in authenticating the service, and the client credential validation-related settings.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d5a19-124">설명</span><span class="sxs-lookup"><span data-stu-id="d5a19-124">Remarks</span></span>  
 <span data-ttu-id="d5a19-125">SCT(보안 컨텍스트 토큰) 쿠키 serialization을 위한 알려진 클레임 형식 목록과 쿠키 정보를 인코딩 및 보안할 인코더를 지정하려면 이 구성 요소를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="d5a19-125">Use this configuration element to specify a list of known claim types for the Security Context Token (SCT) cookies serialization, as well as an encoder to encode and secure cookies information.</span></span> <span data-ttu-id="d5a19-126">SCT에 대한 자세한 내용은 <xref:System.ServiceModel.Security.SecureConversationServiceCredential>을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d5a19-126">For more information on SCT, see <xref:System.ServiceModel.Security.SecureConversationServiceCredential>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d5a19-127">참고자료</span><span class="sxs-lookup"><span data-stu-id="d5a19-127">See also</span></span>

- <xref:System.ServiceModel.Configuration.SecureConversationServiceElement>
- <xref:System.ServiceModel.Configuration.ServiceCredentialsElement.SecureConversationAuthentication%2A>
- <xref:System.ServiceModel.Description.ServiceCredentials.SecureConversationAuthentication%2A>
- <xref:System.ServiceModel.Security.SecureConversationServiceCredential>
