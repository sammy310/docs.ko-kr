---
title: <serviceCredential>의 <secureConversationAuthentication>
ms.date: 03/30/2017
ms.assetid: 0bd3fac7-befd-4a45-ba51-c200b33be0fd
ms.openlocfilehash: 336969c654f332ae3d838d8fd6d1c4243838539c
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/06/2019
ms.locfileid: "70399924"
---
# <a name="secureconversationauthentication-of-servicecredential"></a><span data-ttu-id="71882-102">\<serviceCredential의 \<servicecredential > ></span><span class="sxs-lookup"><span data-stu-id="71882-102">\<secureConversationAuthentication> of \<serviceCredential></span></span>
<span data-ttu-id="71882-103">보안 대화 서비스 설정을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="71882-103">Specifies the settings for a secure conversation service.</span></span>  
  
<span data-ttu-id="71882-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="71882-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="71882-105">&nbsp;&nbsp;[ **\<System.servicemodel >** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="71882-105">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="71882-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<동작 >** ](behaviors.md)</span><span class="sxs-lookup"><span data-stu-id="71882-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)</span></span>\
<span data-ttu-id="71882-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<serviceBehaviors >** ](servicebehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="71882-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors.md)</span></span>\
<span data-ttu-id="71882-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<동작 >** ](behavior-of-servicebehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="71882-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-servicebehaviors.md)</span></span>\
<span data-ttu-id="71882-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<serviceCredentials >** ](servicecredentials.md)</span><span class="sxs-lookup"><span data-stu-id="71882-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceCredentials>**](servicecredentials.md)</span></span>\
<span data-ttu-id="71882-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<Servicecredential >**</span><span class="sxs-lookup"><span data-stu-id="71882-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<secureConversationAuthentication>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="71882-111">구문</span><span class="sxs-lookup"><span data-stu-id="71882-111">Syntax</span></span>  
  
```xml  
<secureConversationAuthentication securityStateEncoderType="String" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="71882-112">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="71882-112">Attributes and Elements</span></span>  
 <span data-ttu-id="71882-113">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="71882-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="71882-114">특성</span><span class="sxs-lookup"><span data-stu-id="71882-114">Attributes</span></span>  
  
|<span data-ttu-id="71882-115">특성</span><span class="sxs-lookup"><span data-stu-id="71882-115">Attribute</span></span>|<span data-ttu-id="71882-116">Description</span><span class="sxs-lookup"><span data-stu-id="71882-116">Description</span></span>|  
|---------------|-----------------|  
|`securityStateEncoderType`|<span data-ttu-id="71882-117">사용할 <xref:System.ServiceModel.Security.SecurityStateEncoder> 형식을 지정하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="71882-117">A string that specifies the type of <xref:System.ServiceModel.Security.SecurityStateEncoder> to be used.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="71882-118">자식 요소</span><span class="sxs-lookup"><span data-stu-id="71882-118">Child Elements</span></span>  
 <span data-ttu-id="71882-119">없음</span><span class="sxs-lookup"><span data-stu-id="71882-119">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="71882-120">부모 요소</span><span class="sxs-lookup"><span data-stu-id="71882-120">Parent Elements</span></span>  
  
|<span data-ttu-id="71882-121">요소</span><span class="sxs-lookup"><span data-stu-id="71882-121">Element</span></span>|<span data-ttu-id="71882-122">Description</span><span class="sxs-lookup"><span data-stu-id="71882-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="71882-123">\<serviceCredentials></span><span class="sxs-lookup"><span data-stu-id="71882-123">\<serviceCredentials></span></span>](servicecredentials.md)|<span data-ttu-id="71882-124">서비스를 인증하는 데 사용되는 자격 증명 및 클라이언트 자격 증명 유효성 검사 관련 설정을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="71882-124">Specifies the credential to be used in authenticating the service, and the client credential validation-related settings.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="71882-125">설명</span><span class="sxs-lookup"><span data-stu-id="71882-125">Remarks</span></span>  
 <span data-ttu-id="71882-126">SCT(보안 컨텍스트 토큰) 쿠키 serialization을 위한 알려진 클레임 형식 목록과 쿠키 정보를 인코딩 및 보안할 인코더를 지정하려면 이 구성 요소를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="71882-126">Use this configuration element to specify a list of known claim types for the Security Context Token (SCT) cookies serialization, as well as an encoder to encode and secure cookies information.</span></span> <span data-ttu-id="71882-127">SCT에 대한 자세한 내용은 <xref:System.ServiceModel.Security.SecureConversationServiceCredential>을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="71882-127">For more information on SCT, see <xref:System.ServiceModel.Security.SecureConversationServiceCredential>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="71882-128">참고자료</span><span class="sxs-lookup"><span data-stu-id="71882-128">See also</span></span>

- <xref:System.ServiceModel.Configuration.SecureConversationServiceElement>
- <xref:System.ServiceModel.Configuration.ServiceCredentialsElement.SecureConversationAuthentication%2A>
- <xref:System.ServiceModel.Description.ServiceCredentials.SecureConversationAuthentication%2A>
- <xref:System.ServiceModel.Security.SecureConversationServiceCredential>
