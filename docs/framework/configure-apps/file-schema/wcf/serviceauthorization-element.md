---
title: <serviceAuthorization> 요소
ms.date: 03/30/2017
ms.assetid: 18cddad5-ddcb-4839-a0ac-1d6f6ab783ca
ms.openlocfilehash: f476f754a340f52859be2986e42754cba0ef3771
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/06/2020
ms.locfileid: "71834018"
---
# <a name="serviceauthorization-element"></a><span data-ttu-id="d7636-102">\<serviceAuthorization> 요소</span><span class="sxs-lookup"><span data-stu-id="d7636-102">\<serviceAuthorization> element</span></span>

<span data-ttu-id="d7636-103">서비스 작업에 대한 액세스 권한을 부여하는 설정을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="d7636-103">Specifies settings that authorize access to service operations</span></span>

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<serviceAuthorization>**  

## <a name="syntax"></a><span data-ttu-id="d7636-104">구문</span><span class="sxs-lookup"><span data-stu-id="d7636-104">Syntax</span></span>

```xml
<serviceAuthorization impersonateCallerForAllOperations="Boolean"
                      principalPermissionMode="None/UseWindowsGroups/UseAspNetRoles/Custom"
                      roleProviderName="String"
                      serviceAuthorizationManagerType="String">
  <authorizationPolicies>
    <add policyType="String" />
  </authorizationPolicies>
</serviceAuthorization>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="d7636-105">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="d7636-105">Attributes and elements</span></span>

<span data-ttu-id="d7636-106">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="d7636-106">The following sections describe attributes, child elements, and parent elements:</span></span>

### <a name="attributes"></a><span data-ttu-id="d7636-107">특성</span><span class="sxs-lookup"><span data-stu-id="d7636-107">Attributes</span></span>

|<span data-ttu-id="d7636-108">attribute</span><span class="sxs-lookup"><span data-stu-id="d7636-108">Attribute</span></span>|<span data-ttu-id="d7636-109">Description</span><span class="sxs-lookup"><span data-stu-id="d7636-109">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="d7636-110">impersonateCallerForAllOperations</span><span class="sxs-lookup"><span data-stu-id="d7636-110">impersonateCallerForAllOperations</span></span>|<span data-ttu-id="d7636-111">서비스의 모든 작업이 호출자를 가장하는지 여부를 지정하는 부울 값입니다.</span><span class="sxs-lookup"><span data-stu-id="d7636-111">A Boolean value that specifies if all the operations in the service impersonate the caller.</span></span> <span data-ttu-id="d7636-112">기본값은 `false`입니다.</span><span class="sxs-lookup"><span data-stu-id="d7636-112">The default is `false`.</span></span><br /><br /> <span data-ttu-id="d7636-113">특정 서비스 작업이 호출자를 가장하면 지정된 서비스를 실행하기 전에 스레드 컨텍스트가 호출자 컨텍스트로 전환됩니다.</span><span class="sxs-lookup"><span data-stu-id="d7636-113">When a specific service operation impersonates the caller, the thread context is switched to the caller context before executing the specified service.</span></span>|  
|<span data-ttu-id="d7636-114">principalPermissionMode</span><span class="sxs-lookup"><span data-stu-id="d7636-114">principalPermissionMode</span></span>|<span data-ttu-id="d7636-115">서버에서 작업을 수행할 때 사용되는 사용자를 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="d7636-115">Sets the principal used to carry out operations on the server.</span></span> <span data-ttu-id="d7636-116">여기에는 다음 값이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="d7636-116">Values include the following:</span></span><br /><br /> <span data-ttu-id="d7636-117">-없음</span><span class="sxs-lookup"><span data-stu-id="d7636-117">-   None</span></span><br /><span data-ttu-id="d7636-118">-UseWindowsGroups</span><span class="sxs-lookup"><span data-stu-id="d7636-118">-   UseWindowsGroups</span></span><br /><span data-ttu-id="d7636-119">-Usa Pnetroles</span><span class="sxs-lookup"><span data-stu-id="d7636-119">-   UseAspNetRoles</span></span><br /><span data-ttu-id="d7636-120">-Custom</span><span class="sxs-lookup"><span data-stu-id="d7636-120">-   Custom</span></span><br /><br /> <span data-ttu-id="d7636-121">기본값은 UseWindowsGroups입니다.</span><span class="sxs-lookup"><span data-stu-id="d7636-121">The default value is UseWindowsGroups.</span></span> <span data-ttu-id="d7636-122">값은 <xref:System.ServiceModel.Description.PrincipalPermissionMode> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="d7636-122">The value is of type <xref:System.ServiceModel.Description.PrincipalPermissionMode>.</span></span> <span data-ttu-id="d7636-123">이 특성을 사용 하는 방법에 대 한 자세한 내용은 [방법: PrincipalPermissionAttribute 클래스를 사용 하 여 액세스 제한](../../../wcf/how-to-restrict-access-with-the-principalpermissionattribute-class.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="d7636-123">For more information on using this attribute, see [How to: Restrict Access with the PrincipalPermissionAttribute Class](../../../wcf/how-to-restrict-access-with-the-principalpermissionattribute-class.md).</span></span>|  
|<span data-ttu-id="d7636-124">roleProviderName</span><span class="sxs-lookup"><span data-stu-id="d7636-124">roleProviderName</span></span>|<span data-ttu-id="d7636-125">역할 공급자의 이름을 지정하는 문자열로, WCF(Windows Communication Foundation) 애플리케이션에 대한 역할 정보를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="d7636-125">A string that specifies the name of the role provider, which provides role information for a Windows Communication Foundation (WCF) application.</span></span> <span data-ttu-id="d7636-126">기본값은 빈 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="d7636-126">The default is an empty string.</span></span>|  
|<span data-ttu-id="d7636-127">ServiceAuthorizationManagerType</span><span class="sxs-lookup"><span data-stu-id="d7636-127">ServiceAuthorizationManagerType</span></span>|<span data-ttu-id="d7636-128">서비스 인증 관리자의 형식을 포함하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="d7636-128">A string containing the type of the service authorization manager.</span></span> <span data-ttu-id="d7636-129">자세한 내용은 <xref:System.ServiceModel.ServiceAuthorizationManager>를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d7636-129">For more information, see <xref:System.ServiceModel.ServiceAuthorizationManager>.</span></span>|  

### <a name="child-elements"></a><span data-ttu-id="d7636-130">자식 요소</span><span class="sxs-lookup"><span data-stu-id="d7636-130">Child elements</span></span>

|<span data-ttu-id="d7636-131">요소</span><span class="sxs-lookup"><span data-stu-id="d7636-131">Element</span></span>|<span data-ttu-id="d7636-132">Description</span><span class="sxs-lookup"><span data-stu-id="d7636-132">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="d7636-133">authorizationPolicies</span><span class="sxs-lookup"><span data-stu-id="d7636-133">authorizationPolicies</span></span>|<span data-ttu-id="d7636-134">`add` 키워드를 사용하여 추가할 수 있는 인증 정책 형식 컬렉션이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d7636-134">Contains a collection of authorization policy types, which can be added using the `add` keyword.</span></span> <span data-ttu-id="d7636-135">각 인증 정책에는 문자열에 해당하는 단일 필수 `policyType` 특성이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d7636-135">Each authorization policy contains a single required `policyType` attribute that is a string.</span></span> <span data-ttu-id="d7636-136">이 특성은 한 입력 클레임 집합을 다른 클레임 집합으로 변환할 수 있도록 하는 인증 정책을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="d7636-136">The attribute specifies an authorization policy, which enables transformation of one set of input claims into another set of claims.</span></span> <span data-ttu-id="d7636-137">그에 따라 액세스 제어가 부여되거나 거부됩니다.</span><span class="sxs-lookup"><span data-stu-id="d7636-137">Access control can be granted or denied based on that.</span></span> <span data-ttu-id="d7636-138">자세한 내용은 <xref:System.ServiceModel.Configuration.AuthorizationPolicyTypeElement>를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d7636-138">For more information, see <xref:System.ServiceModel.Configuration.AuthorizationPolicyTypeElement>.</span></span>|  

### <a name="parent-elements"></a><span data-ttu-id="d7636-139">부모 요소</span><span class="sxs-lookup"><span data-stu-id="d7636-139">Parent elements</span></span>

|<span data-ttu-id="d7636-140">요소</span><span class="sxs-lookup"><span data-stu-id="d7636-140">Element</span></span>|<span data-ttu-id="d7636-141">Description</span><span class="sxs-lookup"><span data-stu-id="d7636-141">Description</span></span>|  
|-------------|-----------------|  
|[\<behavior>](behavior-of-endpointbehaviors.md)|<span data-ttu-id="d7636-142">서비스의 동작에 대한 설정 컬렉션을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="d7636-142">Contains a collection of settings for the behavior of a service.</span></span>|  

## <a name="remarks"></a><span data-ttu-id="d7636-143">설명</span><span class="sxs-lookup"><span data-stu-id="d7636-143">Remarks</span></span>

<span data-ttu-id="d7636-144">이 섹션에는 권한 부여, 사용자 지정 역할 공급자 및 가장에 영향을 주는 요소가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d7636-144">This section contains elements affecting authorization, custom role providers, and impersonation.</span></span>  
  
<span data-ttu-id="d7636-145">`principalPermissionMode` 특성은 보호된 메서드의 사용 권한을 부여할 때 사용할 사용자 그룹을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="d7636-145">The `principalPermissionMode` attribute specifies the groups of users to use when authorizing use of a protected method.</span></span> <span data-ttu-id="d7636-146">기본값은 `UseWindowsGroups`이며 리소스에 액세스하려는 ID에 대해 "Administrators" 또는 "Users"와 같은 Windows 그룹을 검색하도록 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="d7636-146">The default value is `UseWindowsGroups` and specifies that Windows groups, such as "Administrators" or "Users," are searched for an identity trying to access a resource.</span></span> <span data-ttu-id="d7636-147">`UseAspNetRoles`다음 코드와 같이 요소 아래에서 구성 된 사용자 지정 역할 공급자를 사용 하도록 지정할 수도 있습니다 \<system.web> .</span><span class="sxs-lookup"><span data-stu-id="d7636-147">You can also specify `UseAspNetRoles` to use a custom role provider that is configured under the \<system.web> element, as shown in the following code:</span></span>

```xml
<system.web>
  <membership defaultProvider="SqlProvider"
              userIsOnlineTimeWindow="15">
    <providers>
      <clear />
      <add name="SqlProvider"
           type="System.Web.Security.SqlMembershipProvider"
           connectionStringName="SqlConn"
           applicationName="MembershipProvider"
           enablePasswordRetrieval="false"
           enablePasswordReset="false"
           requiresQuestionAndAnswer="false"
           requiresUniqueEmail="true"
           passwordFormat="Hashed" />
    </providers>
  </membership>
  <!-- Other configuration code not shown. -->
</system.web>
```
  
<span data-ttu-id="d7636-148">다음 코드에서는 `roleProviderName` 특성과 함께 사용 되는을 보여 줍니다 `principalPermissionMode` .</span><span class="sxs-lookup"><span data-stu-id="d7636-148">The following code shows the `roleProviderName` used with the `principalPermissionMode` attribute:</span></span>
  
```xml
<behaviors>
  <behavior name="ServiceBehaviour">
    <serviceAuthorization principalPermissionMode ="UseAspNetRoles"
                          roleProviderName ="SqlProvider" />
  </behavior>
  <!-- Other configuration code not shown. -->
</behaviors>
```

<span data-ttu-id="d7636-149">이 구성 요소 사용에 대 한 자세한 예제는 서비스 작업 및 [권한 부여 정책](../../../wcf/samples/authorization-policy.md)에 대 한 [액세스 권한 부여](../../../wcf/samples/authorizing-access-to-service-operations.md) 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="d7636-149">For a detailed example of using this configuration element, see [Authorizing Access to Service Operations](../../../wcf/samples/authorizing-access-to-service-operations.md) and [Authorization Policy](../../../wcf/samples/authorization-policy.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="d7636-150">참고 항목</span><span class="sxs-lookup"><span data-stu-id="d7636-150">See also</span></span>

- <xref:System.ServiceModel.Configuration.ServiceAuthorizationElement>
- <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior>
- [<span data-ttu-id="d7636-151">보안 동작</span><span class="sxs-lookup"><span data-stu-id="d7636-151">Security Behaviors</span></span>](../../../wcf/feature-details/security-behaviors-in-wcf.md)
- [<span data-ttu-id="d7636-152">Authorizing Access to Service Operations</span><span class="sxs-lookup"><span data-stu-id="d7636-152">Authorizing Access to Service Operations</span></span>](../../../wcf/samples/authorizing-access-to-service-operations.md)
- [<span data-ttu-id="d7636-153">방법: 서비스에 대한 사용자 지정 권한 부여 관리자 만들기</span><span class="sxs-lookup"><span data-stu-id="d7636-153">How to: Create a Custom Authorization Manager for a Service</span></span>](../../../wcf/extending/how-to-create-a-custom-authorization-manager-for-a-service.md)
- [<span data-ttu-id="d7636-154">방법: PrincipalPermissionAttribute 클래스를 사용하여 액세스 제한</span><span class="sxs-lookup"><span data-stu-id="d7636-154">How to: Restrict Access with the PrincipalPermissionAttribute Class</span></span>](../../../wcf/how-to-restrict-access-with-the-principalpermissionattribute-class.md)
- [<span data-ttu-id="d7636-155">권한 부여 정책</span><span class="sxs-lookup"><span data-stu-id="d7636-155">Authorization Policy</span></span>](../../../wcf/samples/authorization-policy.md)
