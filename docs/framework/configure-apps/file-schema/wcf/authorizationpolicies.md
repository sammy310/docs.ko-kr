---
title: <authorizationPolicies>
ms.date: 03/30/2017
ms.assetid: 5b367489-54d7-408b-8f56-cb157dd68eaf
ms.openlocfilehash: 38d123a53b344ff1e4d781115093d0d1de5ae679
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/22/2019
ms.locfileid: "69926455"
---
# <a name="authorizationpolicies"></a><span data-ttu-id="9c2bf-101">\<authorizationPolicies></span><span class="sxs-lookup"><span data-stu-id="9c2bf-101">\<authorizationPolicies></span></span>
<span data-ttu-id="9c2bf-102">이 구성 섹션에는 `add` 키워드를 사용하여 추가할 수 있는 인증 정책 형식 컬렉션이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9c2bf-102">This configuration section contains a collection of authorization policy types, which can be added using the `add` keyword.</span></span> <span data-ttu-id="9c2bf-103">각 인증 정책에는 문자열에 해당하는 단일 필수 `policyType` 특성이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9c2bf-103">Each authorization policy contains a single required `policyType` attribute that is a string.</span></span> <span data-ttu-id="9c2bf-104">이 특성은 한 입력 클레임 집합을 다른 클레임 집합으로 변환할 수 있도록 하는 인증 정책을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="9c2bf-104">The attribute specifies an authorization policy, which enables transformation of one set of input claims into another set of claims.</span></span> <span data-ttu-id="9c2bf-105">그에 따라 액세스 제어가 부여되거나 거부됩니다.</span><span class="sxs-lookup"><span data-stu-id="9c2bf-105">Access control can be granted or denied based on that.</span></span> <span data-ttu-id="9c2bf-106">권한 부여 정책의 작동 방식에 대 한 자세한 내용은 및 <xref:System.IdentityModel.Policy.IAuthorizationPolicy> [권한 부여 정책](../../../wcf/samples/authorization-policy.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="9c2bf-106">For more information on how an authorization policy works, see <xref:System.IdentityModel.Policy.IAuthorizationPolicy> and [Authorization Policy](../../../wcf/samples/authorization-policy.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9c2bf-107">참고자료</span><span class="sxs-lookup"><span data-stu-id="9c2bf-107">See also</span></span>

- <xref:System.ServiceModel.Configuration.ServiceAuthorizationElement>
- <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior.ExternalAuthorizationPolicies%2A>
- <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior>
- <xref:System.ServiceModel.Configuration.AuthorizationPolicyTypeElement>
- <xref:System.ServiceModel.Configuration.ServiceAuthorizationElement.AuthorizationPolicies%2A>
- <xref:System.ServiceModel.Configuration.AuthorizationPolicyTypeElementCollection>
- <xref:System.IdentityModel.Policy.IAuthorizationPolicy>
- [<span data-ttu-id="9c2bf-108">서비스 작업에 대한 액세스 승인</span><span class="sxs-lookup"><span data-stu-id="9c2bf-108">Authorizing Access to Service Operations</span></span>](../../../wcf/samples/authorizing-access-to-service-operations.md)
- [<span data-ttu-id="9c2bf-109">방법: 서비스에 대 한 사용자 지정 권한 부여 관리자 만들기</span><span class="sxs-lookup"><span data-stu-id="9c2bf-109">How to: Create a Custom Authorization Manager for a Service</span></span>](../../../wcf/extending/how-to-create-a-custom-authorization-manager-for-a-service.md)
- [<span data-ttu-id="9c2bf-110">\<add></span><span class="sxs-lookup"><span data-stu-id="9c2bf-110">\<add></span></span>](add-of-authorizationpolicies.md)
- [<span data-ttu-id="9c2bf-111">권한 부여 정책</span><span class="sxs-lookup"><span data-stu-id="9c2bf-111">Authorization Policy</span></span>](../../../wcf/samples/authorization-policy.md)
