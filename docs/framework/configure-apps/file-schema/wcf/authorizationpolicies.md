---
title: <authorizationPolicies>
ms.date: 03/30/2017
ms.assetid: 5b367489-54d7-408b-8f56-cb157dd68eaf
ms.openlocfilehash: 2910f47b85ee67694cae0c3a725c3c7c7b3803c0
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59122827"
---
# <a name="authorizationpolicies"></a><span data-ttu-id="23d01-101">\<authorizationPolicies></span><span class="sxs-lookup"><span data-stu-id="23d01-101">\<authorizationPolicies></span></span>
<span data-ttu-id="23d01-102">이 구성 섹션에는 `add` 키워드를 사용하여 추가할 수 있는 인증 정책 형식 컬렉션이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="23d01-102">This configuration section contains a collection of authorization policy types, which can be added using the `add` keyword.</span></span> <span data-ttu-id="23d01-103">각 인증 정책에는 문자열에 해당하는 단일 필수 `policyType` 특성이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="23d01-103">Each authorization policy contains a single required `policyType` attribute that is a string.</span></span> <span data-ttu-id="23d01-104">이 특성은 한 입력 클레임 집합을 다른 클레임 집합으로 변환할 수 있도록 하는 인증 정책을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="23d01-104">The attribute specifies an authorization policy, which enables transformation of one set of input claims into another set of claims.</span></span> <span data-ttu-id="23d01-105">그에 따라 액세스 제어가 부여되거나 거부됩니다.</span><span class="sxs-lookup"><span data-stu-id="23d01-105">Access control can be granted or denied based on that.</span></span> <span data-ttu-id="23d01-106">권한 부여 정책이 작동 하는 방법에 대 한 자세한 내용은 참조 하세요. <xref:System.IdentityModel.Policy.IAuthorizationPolicy> 하 고 [권한 부여 정책](../../../../../docs/framework/wcf/samples/authorization-policy.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="23d01-106">For more information on how an authorization policy works, see <xref:System.IdentityModel.Policy.IAuthorizationPolicy> and [Authorization Policy](../../../../../docs/framework/wcf/samples/authorization-policy.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="23d01-107">참고자료</span><span class="sxs-lookup"><span data-stu-id="23d01-107">See also</span></span>

- <xref:System.ServiceModel.Configuration.ServiceAuthorizationElement>
- <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior.ExternalAuthorizationPolicies%2A>
- <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior>
- <xref:System.ServiceModel.Configuration.AuthorizationPolicyTypeElement>
- <xref:System.ServiceModel.Configuration.ServiceAuthorizationElement.AuthorizationPolicies%2A>
- <xref:System.ServiceModel.Configuration.AuthorizationPolicyTypeElementCollection>
- <xref:System.IdentityModel.Policy.IAuthorizationPolicy>
- [<span data-ttu-id="23d01-108">서비스 작업에 대한 액세스 승인</span><span class="sxs-lookup"><span data-stu-id="23d01-108">Authorizing Access to Service Operations</span></span>](../../../../../docs/framework/wcf/samples/authorizing-access-to-service-operations.md)
- [<span data-ttu-id="23d01-109">방법: 서비스에 대 한 사용자 지정 권한 부여 관리자 만들기</span><span class="sxs-lookup"><span data-stu-id="23d01-109">How to: Create a Custom Authorization Manager for a Service</span></span>](../../../../../docs/framework/wcf/extending/how-to-create-a-custom-authorization-manager-for-a-service.md)
- [<span data-ttu-id="23d01-110">\<add></span><span class="sxs-lookup"><span data-stu-id="23d01-110">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-authorizationpolicies.md)
- [<span data-ttu-id="23d01-111">권한 부여 정책</span><span class="sxs-lookup"><span data-stu-id="23d01-111">Authorization Policy</span></span>](../../../../../docs/framework/wcf/samples/authorization-policy.md)
