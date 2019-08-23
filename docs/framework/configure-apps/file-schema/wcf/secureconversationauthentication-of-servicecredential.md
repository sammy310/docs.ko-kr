---
title: <serviceCredential>의 <secureConversationAuthentication>
ms.date: 03/30/2017
ms.assetid: 0bd3fac7-befd-4a45-ba51-c200b33be0fd
ms.openlocfilehash: 61034c2c66a6d8e27a87ec5380aa7297247eb31e
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/22/2019
ms.locfileid: "69935828"
---
# <a name="secureconversationauthentication-of-servicecredential"></a><span data-ttu-id="99296-102">\<serviceCredential의 \<servicecredential > ></span><span class="sxs-lookup"><span data-stu-id="99296-102">\<secureConversationAuthentication> of \<serviceCredential></span></span>
<span data-ttu-id="99296-103">보안 대화 서비스 설정을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="99296-103">Specifies the settings for a secure conversation service.</span></span>  
  
 <span data-ttu-id="99296-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="99296-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="99296-105">\<behaviors></span><span class="sxs-lookup"><span data-stu-id="99296-105">\<behaviors></span></span>  
<span data-ttu-id="99296-106">\<serviceBehaviors></span><span class="sxs-lookup"><span data-stu-id="99296-106">\<serviceBehaviors></span></span>  
<span data-ttu-id="99296-107">\<behavior></span><span class="sxs-lookup"><span data-stu-id="99296-107">\<behavior></span></span>  
<span data-ttu-id="99296-108">\<serviceCredentials></span><span class="sxs-lookup"><span data-stu-id="99296-108">\<serviceCredentials></span></span>  
<span data-ttu-id="99296-109">\<secureConversationAuthentication></span><span class="sxs-lookup"><span data-stu-id="99296-109">\<secureConversationAuthentication></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="99296-110">구문</span><span class="sxs-lookup"><span data-stu-id="99296-110">Syntax</span></span>  
  
```xml  
<secureConversationAuthentication securityStateEncoderType="String" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="99296-111">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="99296-111">Attributes and Elements</span></span>  
 <span data-ttu-id="99296-112">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="99296-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="99296-113">특성</span><span class="sxs-lookup"><span data-stu-id="99296-113">Attributes</span></span>  
  
|<span data-ttu-id="99296-114">특성</span><span class="sxs-lookup"><span data-stu-id="99296-114">Attribute</span></span>|<span data-ttu-id="99296-115">Description</span><span class="sxs-lookup"><span data-stu-id="99296-115">Description</span></span>|  
|---------------|-----------------|  
|`securityStateEncoderType`|<span data-ttu-id="99296-116">사용할 <xref:System.ServiceModel.Security.SecurityStateEncoder> 형식을 지정하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="99296-116">A string that specifies the type of <xref:System.ServiceModel.Security.SecurityStateEncoder> to be used.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="99296-117">자식 요소</span><span class="sxs-lookup"><span data-stu-id="99296-117">Child Elements</span></span>  
 <span data-ttu-id="99296-118">없음</span><span class="sxs-lookup"><span data-stu-id="99296-118">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="99296-119">부모 요소</span><span class="sxs-lookup"><span data-stu-id="99296-119">Parent Elements</span></span>  
  
|<span data-ttu-id="99296-120">요소</span><span class="sxs-lookup"><span data-stu-id="99296-120">Element</span></span>|<span data-ttu-id="99296-121">Description</span><span class="sxs-lookup"><span data-stu-id="99296-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="99296-122">\<serviceCredentials></span><span class="sxs-lookup"><span data-stu-id="99296-122">\<serviceCredentials></span></span>](servicecredentials.md)|<span data-ttu-id="99296-123">서비스를 인증하는 데 사용되는 자격 증명 및 클라이언트 자격 증명 유효성 검사 관련 설정을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="99296-123">Specifies the credential to be used in authenticating the service, and the client credential validation-related settings.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="99296-124">설명</span><span class="sxs-lookup"><span data-stu-id="99296-124">Remarks</span></span>  
 <span data-ttu-id="99296-125">SCT(보안 컨텍스트 토큰) 쿠키 serialization을 위한 알려진 클레임 형식 목록과 쿠키 정보를 인코딩 및 보안할 인코더를 지정하려면 이 구성 요소를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="99296-125">Use this configuration element to specify a list of known claim types for the Security Context Token (SCT) cookies serialization, as well as an encoder to encode and secure cookies information.</span></span> <span data-ttu-id="99296-126">SCT에 대한 자세한 내용은 <xref:System.ServiceModel.Security.SecureConversationServiceCredential>을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="99296-126">For more information on SCT, see <xref:System.ServiceModel.Security.SecureConversationServiceCredential>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="99296-127">참고자료</span><span class="sxs-lookup"><span data-stu-id="99296-127">See also</span></span>

- <xref:System.ServiceModel.Configuration.SecureConversationServiceElement>
- <xref:System.ServiceModel.Configuration.ServiceCredentialsElement.SecureConversationAuthentication%2A>
- <xref:System.ServiceModel.Description.ServiceCredentials.SecureConversationAuthentication%2A>
- <xref:System.ServiceModel.Security.SecureConversationServiceCredential>
