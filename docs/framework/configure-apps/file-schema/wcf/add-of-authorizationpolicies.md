---
title: <authorizationPolicies>의 <add>
ms.date: 03/30/2017
ms.assetid: 613a03d8-4384-4556-bce2-8c23286c0bb0
ms.openlocfilehash: e2597bc51e788c919bfe3ce3422ae2911cc6b33b
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/06/2019
ms.locfileid: "70400695"
---
# <a name="add-of-authorizationpolicies"></a><span data-ttu-id="9acb1-102">\<\<authorizationpolicies > 추가 ></span><span class="sxs-lookup"><span data-stu-id="9acb1-102">\<add> of \<authorizationPolicies></span></span>
<span data-ttu-id="9acb1-103">클레임 변환에 대한 권한 부여 정책을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="9acb1-103">Specifies an authorization policy for claim transformation.</span></span>  
  
<span data-ttu-id="9acb1-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="9acb1-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="9acb1-105">&nbsp;&nbsp;[ **\<System.servicemodel >** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="9acb1-105">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="9acb1-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<동작 >** ](behaviors.md)</span><span class="sxs-lookup"><span data-stu-id="9acb1-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)</span></span>\
<span data-ttu-id="9acb1-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<serviceBehaviors >** ](servicebehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="9acb1-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors.md)</span></span>\
<span data-ttu-id="9acb1-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<동작 >** ](behavior-of-servicebehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="9acb1-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-servicebehaviors.md)</span></span>\
<span data-ttu-id="9acb1-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<serviceAuthorization >** ](serviceauthorization-element.md)</span><span class="sxs-lookup"><span data-stu-id="9acb1-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceAuthorization>**](serviceauthorization-element.md)</span></span>\
<span data-ttu-id="9acb1-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<authorizationPolicies >** ](authorizationpolicies.md)</span><span class="sxs-lookup"><span data-stu-id="9acb1-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<authorizationPolicies>**](authorizationpolicies.md)</span></span>\
<span data-ttu-id="9acb1-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<> 추가**</span><span class="sxs-lookup"><span data-stu-id="9acb1-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9acb1-112">구문</span><span class="sxs-lookup"><span data-stu-id="9acb1-112">Syntax</span></span>  
  
```xml  
<authorizationPolicies>
  <add policyType="String" />
</authorizationPolicies>
```  
  
## <a name="type"></a><span data-ttu-id="9acb1-113">형식</span><span class="sxs-lookup"><span data-stu-id="9acb1-113">Type</span></span>  
 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="9acb1-114">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="9acb1-114">Attributes and Elements</span></span>  
 <span data-ttu-id="9acb1-115">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="9acb1-115">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="9acb1-116">특성</span><span class="sxs-lookup"><span data-stu-id="9acb1-116">Attributes</span></span>  
  
|<span data-ttu-id="9acb1-117">특성</span><span class="sxs-lookup"><span data-stu-id="9acb1-117">Attribute</span></span>|<span data-ttu-id="9acb1-118">Description</span><span class="sxs-lookup"><span data-stu-id="9acb1-118">Description</span></span>|  
|---------------|-----------------|  
|`policyType`|<span data-ttu-id="9acb1-119">필수 String 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="9acb1-119">A required String attribute.</span></span><br /><br /> <span data-ttu-id="9acb1-120">WCF (Windows Communication Foundation) 액세스 제어 모델은 권한 부여 정책 집합을 형식으로 프로 비전 할 수 있도록 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="9acb1-120">The Windows Communication Foundation (WCF) access control model supports provisioning a set of authorization policies as types.</span></span> <span data-ttu-id="9acb1-121">이 특성은 한 입력 클레임 집합을 다른 클레임 집합으로 변형할 수 있도록 하는 권한 부여 정책을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="9acb1-121">This attribute specifies an authorization policy, which enables transformation of one set of input claims into another set of claims.</span></span> <span data-ttu-id="9acb1-122">그에 따라 액세스 제어가 부여되거나 거부됩니다.</span><span class="sxs-lookup"><span data-stu-id="9acb1-122">Access control can be granted or denied based on that.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="9acb1-123">자식 요소</span><span class="sxs-lookup"><span data-stu-id="9acb1-123">Child Elements</span></span>  
 <span data-ttu-id="9acb1-124">없음</span><span class="sxs-lookup"><span data-stu-id="9acb1-124">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="9acb1-125">부모 요소</span><span class="sxs-lookup"><span data-stu-id="9acb1-125">Parent Elements</span></span>  
  
|<span data-ttu-id="9acb1-126">요소</span><span class="sxs-lookup"><span data-stu-id="9acb1-126">Element</span></span>|<span data-ttu-id="9acb1-127">설명</span><span class="sxs-lookup"><span data-stu-id="9acb1-127">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="9acb1-128">\<authorizationPolicies></span><span class="sxs-lookup"><span data-stu-id="9acb1-128">\<authorizationPolicies></span></span>](authorizationpolicies.md)|<span data-ttu-id="9acb1-129">권한 부여 정책 형식 컬렉션을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="9acb1-129">Specifies a collection of authorization policy types.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9acb1-130">설명</span><span class="sxs-lookup"><span data-stu-id="9acb1-130">Remarks</span></span>  
 <span data-ttu-id="9acb1-131">각 인증 정책에는 문자열에 해당하는 단일 필수 `policyType` 특성이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9acb1-131">Each authorization policy contains a single required `policyType` attribute that is a string.</span></span> <span data-ttu-id="9acb1-132">이 특성은 한 입력 클레임 집합을 다른 클레임 집합으로 변환할 수 있도록 하는 인증 정책을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="9acb1-132">The attribute specifies an authorization policy, which enables transformation of one set of input claims into another set of claims.</span></span> <span data-ttu-id="9acb1-133">그에 따라 액세스 제어가 부여되거나 거부됩니다.</span><span class="sxs-lookup"><span data-stu-id="9acb1-133">Access control can be granted or denied based on that.</span></span> <span data-ttu-id="9acb1-134">권한 부여 정책의 작동 방식에 대 한 자세한 내용은 및 <xref:System.IdentityModel.Policy.IAuthorizationPolicy> [권한 부여 정책](../../../wcf/samples/authorization-policy.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="9acb1-134">For more information on how an authorization policy works, see <xref:System.IdentityModel.Policy.IAuthorizationPolicy> and [Authorization Policy](../../../wcf/samples/authorization-policy.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9acb1-135">참고자료</span><span class="sxs-lookup"><span data-stu-id="9acb1-135">See also</span></span>

- <xref:System.ServiceModel.Configuration.ServiceAuthorizationElement>
- <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior.ExternalAuthorizationPolicies%2A>
- <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior>
- <xref:System.ServiceModel.Configuration.AuthorizationPolicyTypeElement>
- <xref:System.ServiceModel.Configuration.ServiceAuthorizationElement.AuthorizationPolicies%2A>
- <xref:System.ServiceModel.Configuration.AuthorizationPolicyTypeElementCollection>
- <xref:System.IdentityModel.Policy.IAuthorizationPolicy>
- [<span data-ttu-id="9acb1-136">서비스 작업에 대한 액세스 승인</span><span class="sxs-lookup"><span data-stu-id="9acb1-136">Authorizing Access to Service Operations</span></span>](../../../wcf/samples/authorizing-access-to-service-operations.md)
- [<span data-ttu-id="9acb1-137">방법: 서비스에 대 한 사용자 지정 권한 부여 관리자 만들기</span><span class="sxs-lookup"><span data-stu-id="9acb1-137">How to: Create a Custom Authorization Manager for a Service</span></span>](../../../wcf/extending/how-to-create-a-custom-authorization-manager-for-a-service.md)
- [<span data-ttu-id="9acb1-138">\<add></span><span class="sxs-lookup"><span data-stu-id="9acb1-138">\<add></span></span>](add-of-authorizationpolicies.md)
- [<span data-ttu-id="9acb1-139">권한 부여 정책</span><span class="sxs-lookup"><span data-stu-id="9acb1-139">Authorization Policy</span></span>](../../../wcf/samples/authorization-policy.md)
