---
title: <serviceCredential>의 <secureConversationAuthentication>
ms.date: 03/30/2017
ms.assetid: 0bd3fac7-befd-4a45-ba51-c200b33be0fd
ms.openlocfilehash: f35392b91d047c46e65ce433ef544b86cf6c88c6
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61670614"
---
# <a name="secureconversationauthentication-of-servicecredential"></a><span data-ttu-id="f7ae3-102">\<secureConversationAuthentication >의 \<serviceCredential ></span><span class="sxs-lookup"><span data-stu-id="f7ae3-102">\<secureConversationAuthentication> of \<serviceCredential></span></span>
<span data-ttu-id="f7ae3-103">보안 대화 서비스 설정을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="f7ae3-103">Specifies the settings for a secure conversation service.</span></span>  
  
 <span data-ttu-id="f7ae3-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="f7ae3-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="f7ae3-105">\<behaviors></span><span class="sxs-lookup"><span data-stu-id="f7ae3-105">\<behaviors></span></span>  
<span data-ttu-id="f7ae3-106">\<serviceBehaviors></span><span class="sxs-lookup"><span data-stu-id="f7ae3-106">\<serviceBehaviors></span></span>  
<span data-ttu-id="f7ae3-107">\<behavior></span><span class="sxs-lookup"><span data-stu-id="f7ae3-107">\<behavior></span></span>  
<span data-ttu-id="f7ae3-108">\<serviceCredentials></span><span class="sxs-lookup"><span data-stu-id="f7ae3-108">\<serviceCredentials></span></span>  
<span data-ttu-id="f7ae3-109">\<secureConversationAuthentication></span><span class="sxs-lookup"><span data-stu-id="f7ae3-109">\<secureConversationAuthentication></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f7ae3-110">구문</span><span class="sxs-lookup"><span data-stu-id="f7ae3-110">Syntax</span></span>  
  
```xml  
<secureConversationAuthentication securityStateEncoderType="String" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="f7ae3-111">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="f7ae3-111">Attributes and Elements</span></span>  
 <span data-ttu-id="f7ae3-112">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="f7ae3-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="f7ae3-113">특성</span><span class="sxs-lookup"><span data-stu-id="f7ae3-113">Attributes</span></span>  
  
|<span data-ttu-id="f7ae3-114">특성</span><span class="sxs-lookup"><span data-stu-id="f7ae3-114">Attribute</span></span>|<span data-ttu-id="f7ae3-115">설명</span><span class="sxs-lookup"><span data-stu-id="f7ae3-115">Description</span></span>|  
|---------------|-----------------|  
|`securityStateEncoderType`|<span data-ttu-id="f7ae3-116">사용할 <xref:System.ServiceModel.Security.SecurityStateEncoder> 형식을 지정하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="f7ae3-116">A string that specifies the type of <xref:System.ServiceModel.Security.SecurityStateEncoder> to be used.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="f7ae3-117">자식 요소</span><span class="sxs-lookup"><span data-stu-id="f7ae3-117">Child Elements</span></span>  
 <span data-ttu-id="f7ae3-118">없음</span><span class="sxs-lookup"><span data-stu-id="f7ae3-118">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="f7ae3-119">부모 요소</span><span class="sxs-lookup"><span data-stu-id="f7ae3-119">Parent Elements</span></span>  
  
|<span data-ttu-id="f7ae3-120">요소</span><span class="sxs-lookup"><span data-stu-id="f7ae3-120">Element</span></span>|<span data-ttu-id="f7ae3-121">설명</span><span class="sxs-lookup"><span data-stu-id="f7ae3-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="f7ae3-122">\<serviceCredentials></span><span class="sxs-lookup"><span data-stu-id="f7ae3-122">\<serviceCredentials></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/servicecredentials.md)|<span data-ttu-id="f7ae3-123">서비스를 인증하는 데 사용되는 자격 증명 및 클라이언트 자격 증명 유효성 검사 관련 설정을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="f7ae3-123">Specifies the credential to be used in authenticating the service, and the client credential validation-related settings.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f7ae3-124">설명</span><span class="sxs-lookup"><span data-stu-id="f7ae3-124">Remarks</span></span>  
 <span data-ttu-id="f7ae3-125">SCT(보안 컨텍스트 토큰) 쿠키 serialization을 위한 알려진 클레임 형식 목록과 쿠키 정보를 인코딩 및 보안할 인코더를 지정하려면 이 구성 요소를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="f7ae3-125">Use this configuration element to specify a list of known claim types for the Security Context Token (SCT) cookies serialization, as well as an encoder to encode and secure cookies information.</span></span> <span data-ttu-id="f7ae3-126">SCT에 대한 자세한 내용은 <xref:System.ServiceModel.Security.SecureConversationServiceCredential>을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f7ae3-126">For more information on SCT, see <xref:System.ServiceModel.Security.SecureConversationServiceCredential>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f7ae3-127">참고자료</span><span class="sxs-lookup"><span data-stu-id="f7ae3-127">See also</span></span>

- <xref:System.ServiceModel.Configuration.SecureConversationServiceElement>
- <xref:System.ServiceModel.Configuration.ServiceCredentialsElement.SecureConversationAuthentication%2A>
- <xref:System.ServiceModel.Description.ServiceCredentials.SecureConversationAuthentication%2A>
- <xref:System.ServiceModel.Security.SecureConversationServiceCredential>
