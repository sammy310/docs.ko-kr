---
description: 다음에 대해 자세히 알아보세요. <userNameAuthentication>
title: <userNameAuthentication>
ms.date: 03/30/2017
ms.assetid: 24d8b398-770f-418f-ba23-c4325419cfa6
ms.openlocfilehash: 0edd92ba343ec38207d60c99616058d0b28f045b
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99664446"
---
# \<userNameAuthentication>

<span data-ttu-id="fbf39-102">사용자 이름 및 암호에 따라 서비스의 자격 증명을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="fbf39-102">Specifies a service's credentials based on user name and password.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceCredentials>**](servicecredentials.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<userNameAuthentication>**  
  
## <a name="syntax"></a><span data-ttu-id="fbf39-103">구문</span><span class="sxs-lookup"><span data-stu-id="fbf39-103">Syntax</span></span>  
  
```xml  
<userNameAuthentication cacheLogonTokenLifetime="TimeSpan"
                        cacheLogonTokens="Boolean"
                        customUserNamePasswordValidatorType="String"
                        includeWindowsGroups="Boolean"
                        maxCacheLogonTokens="Integer"
                        membershipProviderName="String"
                        userNamePasswordValidationMode="Windows/MembershipProvider/Custom" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="fbf39-104">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="fbf39-104">Attributes and Elements</span></span>  

 <span data-ttu-id="fbf39-105">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="fbf39-105">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="fbf39-106">특성</span><span class="sxs-lookup"><span data-stu-id="fbf39-106">Attributes</span></span>  
  
|<span data-ttu-id="fbf39-107">attribute</span><span class="sxs-lookup"><span data-stu-id="fbf39-107">Attribute</span></span>|<span data-ttu-id="fbf39-108">설명</span><span class="sxs-lookup"><span data-stu-id="fbf39-108">Description</span></span>|  
|---------------|-----------------|  
|`cacheLogonTokenLifetime`|<span data-ttu-id="fbf39-109">토큰이 캐시되는 최대 시간 길이를 지정하는 <xref:System.TimeSpan>입니다.</span><span class="sxs-lookup"><span data-stu-id="fbf39-109">A <xref:System.TimeSpan> that specifies the maximum length of time a token is cached.</span></span> <span data-ttu-id="fbf39-110">기본값은 00:15:00입니다.</span><span class="sxs-lookup"><span data-stu-id="fbf39-110">The default is 00:15:00.</span></span>|  
|`cacheLogonTokens`|<span data-ttu-id="fbf39-111">로그온 토큰 캐시 여부를 지정하는 부울 값입니다.</span><span class="sxs-lookup"><span data-stu-id="fbf39-111">A Boolean value that specifies whether logon tokens are cached.</span></span> <span data-ttu-id="fbf39-112">기본값은 `false`입니다.</span><span class="sxs-lookup"><span data-stu-id="fbf39-112">The default is `false`.</span></span>|  
|`customUserNamePasswordValidatorType`|<span data-ttu-id="fbf39-113">사용되는 사용자 지정 사용자 이름 암호 유효성 검사기 형식을 지정하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="fbf39-113">A string that specifies the type of custom username password validator to be used.</span></span> <span data-ttu-id="fbf39-114">기본값은 빈 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="fbf39-114">The default is an empty string.</span></span>|  
|`includeWindowsGroups`|<span data-ttu-id="fbf39-115">Windows 그룹이 보안 컨텍스트에 포함되는지 여부를 지정하는 부울 값입니다.</span><span class="sxs-lookup"><span data-stu-id="fbf39-115">A Boolean value that specifies whether Windows groups are included in the security context.</span></span> <span data-ttu-id="fbf39-116">기본값은 `true`입니다.</span><span class="sxs-lookup"><span data-stu-id="fbf39-116">The default is `true`.</span></span><br /><br /> <span data-ttu-id="fbf39-117">이 특성을 `true`로 설정하면 전체 그룹이 확장되므로 성능에 영향을 줍니다.</span><span class="sxs-lookup"><span data-stu-id="fbf39-117">Setting this attribute to `true` has a performance impact as it results in a full-group expansion.</span></span> <span data-ttu-id="fbf39-118">사용자가 속한 그룹의 목록을 설정할 필요가 없으면 이 속성을 `false`로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="fbf39-118">Set this property to `false` if you do not need to establish the list of groups a user belongs to.</span></span>|  
|`maxCacheLogonTokens`|<span data-ttu-id="fbf39-119">캐시할 로그온 토큰의 최대 수를 지정하는 정수입니다.</span><span class="sxs-lookup"><span data-stu-id="fbf39-119">An integer that specifies the maximum number of logon tokens to cache.</span></span> <span data-ttu-id="fbf39-120">이 값은 0보다 커야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fbf39-120">This value should be larger than zero.</span></span> <span data-ttu-id="fbf39-121">기본값은 128입니다.</span><span class="sxs-lookup"><span data-stu-id="fbf39-121">The default is 128.</span></span>|  
|`membershipProviderName`|<span data-ttu-id="fbf39-122">바인딩의 `clientCredentialType` 특성이 `username`으로 설정되면 사용자 이름이 Windows 계정에 매핑됩니다.</span><span class="sxs-lookup"><span data-stu-id="fbf39-122">When the `clientCredentialType` attribute of a binding is set to `username`, the username is mapped to Windows accounts.</span></span> <span data-ttu-id="fbf39-123">이 특성을 사용하여 이 동작을 재정의할 수 있습니다. 해당 특성은 관련 암호 유효성 검사 메커니즘을 제공하는 <xref:System.Web.Security.MembershipProvider> 값의 이름을 포함하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="fbf39-123">You can override this behavior using this attribute, which is a string that contains the name of the <xref:System.Web.Security.MembershipProvider> value that provides the relevant password validation mechanism.</span></span>|  
|`userNamePasswordValidationMode`|<span data-ttu-id="fbf39-124">사용자 이름 암호의 유효성 검사 방식을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="fbf39-124">Specifies the manner in which username password is validated.</span></span> <span data-ttu-id="fbf39-125">유효한 값은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="fbf39-125">Valid values are:</span></span><br /><br /> <span data-ttu-id="fbf39-126">-Windows</span><span class="sxs-lookup"><span data-stu-id="fbf39-126">-   Windows</span></span><br /><span data-ttu-id="fbf39-127">-MembershipProvider</span><span class="sxs-lookup"><span data-stu-id="fbf39-127">-   MembershipProvider</span></span><br /><span data-ttu-id="fbf39-128">-Custom</span><span class="sxs-lookup"><span data-stu-id="fbf39-128">-   Custom</span></span><br /><br /> <span data-ttu-id="fbf39-129">기본값은 Windows입니다.</span><span class="sxs-lookup"><span data-stu-id="fbf39-129">The default is Windows.</span></span> <span data-ttu-id="fbf39-130">이 특성은 <xref:System.ServiceModel.Security.UserNamePasswordValidationMode> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="fbf39-130">This attribute is of type <xref:System.ServiceModel.Security.UserNamePasswordValidationMode>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="fbf39-131">자식 요소</span><span class="sxs-lookup"><span data-stu-id="fbf39-131">Child Elements</span></span>  

 <span data-ttu-id="fbf39-132">없음</span><span class="sxs-lookup"><span data-stu-id="fbf39-132">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="fbf39-133">부모 요소</span><span class="sxs-lookup"><span data-stu-id="fbf39-133">Parent Elements</span></span>  
  
|<span data-ttu-id="fbf39-134">요소</span><span class="sxs-lookup"><span data-stu-id="fbf39-134">Element</span></span>|<span data-ttu-id="fbf39-135">설명</span><span class="sxs-lookup"><span data-stu-id="fbf39-135">Description</span></span>|  
|-------------|-----------------|  
|[\<serviceCredentials>](servicecredentials.md)|<span data-ttu-id="fbf39-136">서비스를 인증하는 데 사용되는 자격 증명 및 클라이언트 자격 증명 확인 관련 설정을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="fbf39-136">Specifies the credential to be used in authenticating the service, and the client credential validation related settings.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="fbf39-137">설명</span><span class="sxs-lookup"><span data-stu-id="fbf39-137">Remarks</span></span>  

 <span data-ttu-id="fbf39-138">사용자 이름/암호 기반 인증을 위해 구성된 서비스에서 사용하는 바인딩이 없으면 이 요소의 특성이 무시됩니다.</span><span class="sxs-lookup"><span data-stu-id="fbf39-138">If none of the bindings used by a service is configured for user name/password-based authentication, the attributes for this element are ignored.</span></span> <span data-ttu-id="fbf39-139">여기에는,, `customUserNamePasswordValidatorType` 및가 포함 됩니다 `includeWindowsGroups` `membershipProviderName` `userNamePasswordValidationMode` .</span><span class="sxs-lookup"><span data-stu-id="fbf39-139">These include `customUserNamePasswordValidatorType`, `includeWindowsGroups`, `membershipProviderName`, and `userNamePasswordValidationMode`.</span></span>  
  
 <span data-ttu-id="fbf39-140">사용자 이름/암호에 대한 Windows 인증을 사용하기 위해 구성된 서비스에서 사용하는 바인딩이 없으면 로그온 토큰의 캐싱과 관련된 설정이 무시됩니다.</span><span class="sxs-lookup"><span data-stu-id="fbf39-140">If none of the bindings used by a service is configured to use Windows authentication for user name/password, the settings related to caching of logon tokens are ignored.</span></span> <span data-ttu-id="fbf39-141">이것에는 `cacheLogonTokenLifetime`, `cacheLogonTokens` 및 `maxCacheLogonTokens`가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fbf39-141">These include the `cacheLogonTokenLifetime`, `cacheLogonTokens`, and `maxCacheLogonTokens`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fbf39-142">참고 항목</span><span class="sxs-lookup"><span data-stu-id="fbf39-142">See also</span></span>

- <xref:System.ServiceModel.Configuration.UserNameServiceElement>
- <xref:System.ServiceModel.Description.ServiceCredentials.UserNameAuthentication%2A>
- <xref:System.ServiceModel.Security.UserNamePasswordServiceCredential>
- <xref:System.ServiceModel.Configuration.ServiceCredentialsElement.UserNameAuthentication%2A>
