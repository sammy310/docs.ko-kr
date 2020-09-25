---
title: <authorizationPolicies>의 <add>
ms.date: 03/30/2017
ms.assetid: 613a03d8-4384-4556-bce2-8c23286c0bb0
ms.openlocfilehash: 39cb89340907743c727a425bb2f140ac34842e3b
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/24/2020
ms.locfileid: "91181676"
---
# <a name="add-of-authorizationpolicies"></a><span data-ttu-id="b7669-102">\<authorizationPolicies>의 \<add></span><span class="sxs-lookup"><span data-stu-id="b7669-102">\<add> of \<authorizationPolicies></span></span>

<span data-ttu-id="b7669-103">클레임 변환에 대한 권한 부여 정책을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="b7669-103">Specifies an authorization policy for claim transformation.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceAuthorization>**](serviceauthorization-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<authorizationPolicies>**](authorizationpolicies.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**  
  
## <a name="syntax"></a><span data-ttu-id="b7669-104">구문</span><span class="sxs-lookup"><span data-stu-id="b7669-104">Syntax</span></span>  
  
```xml  
<authorizationPolicies>
  <add policyType="String" />
</authorizationPolicies>
```  
  
## <a name="type"></a><span data-ttu-id="b7669-105">형식</span><span class="sxs-lookup"><span data-stu-id="b7669-105">Type</span></span>  

 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="b7669-106">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="b7669-106">Attributes and Elements</span></span>  

 <span data-ttu-id="b7669-107">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="b7669-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="b7669-108">특성</span><span class="sxs-lookup"><span data-stu-id="b7669-108">Attributes</span></span>  
  
|<span data-ttu-id="b7669-109">attribute</span><span class="sxs-lookup"><span data-stu-id="b7669-109">Attribute</span></span>|<span data-ttu-id="b7669-110">설명</span><span class="sxs-lookup"><span data-stu-id="b7669-110">Description</span></span>|  
|---------------|-----------------|  
|`policyType`|<span data-ttu-id="b7669-111">필수 String 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="b7669-111">A required String attribute.</span></span><br /><br /> <span data-ttu-id="b7669-112">WCF (Windows Communication Foundation) 액세스 제어 모델은 권한 부여 정책 집합을 형식으로 프로 비전 할 수 있도록 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="b7669-112">The Windows Communication Foundation (WCF) access control model supports provisioning a set of authorization policies as types.</span></span> <span data-ttu-id="b7669-113">이 특성은 한 입력 클레임 집합을 다른 클레임 집합으로 변형할 수 있도록 하는 권한 부여 정책을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="b7669-113">This attribute specifies an authorization policy, which enables transformation of one set of input claims into another set of claims.</span></span> <span data-ttu-id="b7669-114">그에 따라 액세스 제어가 부여되거나 거부됩니다.</span><span class="sxs-lookup"><span data-stu-id="b7669-114">Access control can be granted or denied based on that.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="b7669-115">자식 요소</span><span class="sxs-lookup"><span data-stu-id="b7669-115">Child Elements</span></span>  

 <span data-ttu-id="b7669-116">없음</span><span class="sxs-lookup"><span data-stu-id="b7669-116">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="b7669-117">부모 요소</span><span class="sxs-lookup"><span data-stu-id="b7669-117">Parent Elements</span></span>  
  
|<span data-ttu-id="b7669-118">요소</span><span class="sxs-lookup"><span data-stu-id="b7669-118">Element</span></span>|<span data-ttu-id="b7669-119">설명</span><span class="sxs-lookup"><span data-stu-id="b7669-119">Description</span></span>|  
|-------------|-----------------|  
|[\<authorizationPolicies>](authorizationpolicies.md)|<span data-ttu-id="b7669-120">권한 부여 정책 형식 컬렉션을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="b7669-120">Specifies a collection of authorization policy types.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b7669-121">설명</span><span class="sxs-lookup"><span data-stu-id="b7669-121">Remarks</span></span>  

 <span data-ttu-id="b7669-122">각 인증 정책에는 문자열에 해당하는 단일 필수 `policyType` 특성이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b7669-122">Each authorization policy contains a single required `policyType` attribute that is a string.</span></span> <span data-ttu-id="b7669-123">이 특성은 한 입력 클레임 집합을 다른 클레임 집합으로 변환할 수 있도록 하는 인증 정책을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="b7669-123">The attribute specifies an authorization policy, which enables transformation of one set of input claims into another set of claims.</span></span> <span data-ttu-id="b7669-124">그에 따라 액세스 제어가 부여되거나 거부됩니다.</span><span class="sxs-lookup"><span data-stu-id="b7669-124">Access control can be granted or denied based on that.</span></span> <span data-ttu-id="b7669-125">권한 부여 정책의 작동 방식에 대 한 자세한 내용은 <xref:System.IdentityModel.Policy.IAuthorizationPolicy> 및 [권한 부여 정책](../../../wcf/samples/authorization-policy.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="b7669-125">For more information on how an authorization policy works, see <xref:System.IdentityModel.Policy.IAuthorizationPolicy> and [Authorization Policy](../../../wcf/samples/authorization-policy.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b7669-126">참고 항목</span><span class="sxs-lookup"><span data-stu-id="b7669-126">See also</span></span>

- <xref:System.ServiceModel.Configuration.ServiceAuthorizationElement>
- <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior.ExternalAuthorizationPolicies%2A>
- <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior>
- <xref:System.ServiceModel.Configuration.AuthorizationPolicyTypeElement>
- <xref:System.ServiceModel.Configuration.ServiceAuthorizationElement.AuthorizationPolicies%2A>
- <xref:System.ServiceModel.Configuration.AuthorizationPolicyTypeElementCollection>
- <xref:System.IdentityModel.Policy.IAuthorizationPolicy>
- [<span data-ttu-id="b7669-127">Authorizing Access to Service Operations</span><span class="sxs-lookup"><span data-stu-id="b7669-127">Authorizing Access to Service Operations</span></span>](../../../wcf/samples/authorizing-access-to-service-operations.md)
- [<span data-ttu-id="b7669-128">방법: 서비스에 대한 사용자 지정 권한 부여 관리자 만들기</span><span class="sxs-lookup"><span data-stu-id="b7669-128">How to: Create a Custom Authorization Manager for a Service</span></span>](../../../wcf/extending/how-to-create-a-custom-authorization-manager-for-a-service.md)
- [\<add>](add-of-authorizationpolicies.md)
- [<span data-ttu-id="b7669-129">권한 부여 정책</span><span class="sxs-lookup"><span data-stu-id="b7669-129">Authorization Policy</span></span>](../../../wcf/samples/authorization-policy.md)
