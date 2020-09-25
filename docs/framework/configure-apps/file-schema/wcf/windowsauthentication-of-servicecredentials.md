---
title: <serviceCredentials>의 <windowsAuthentication>
ms.date: 03/30/2017
ms.assetid: e0709473-0997-4de3-8f49-783527309a48
ms.openlocfilehash: bda375959b535ce5f2996d594f719893164b0bd4
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/24/2020
ms.locfileid: "91195001"
---
# <a name="windowsauthentication-of-servicecredentials"></a><span data-ttu-id="dcc92-102">\<serviceCredentials>의 \<windowsAuthentication></span><span class="sxs-lookup"><span data-stu-id="dcc92-102">\<windowsAuthentication> of \<serviceCredentials></span></span>

<span data-ttu-id="dcc92-103">Windows 서비스 자격 증명의 설정을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="dcc92-103">Specifies the settings of a Windows service credential.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceCredentials>**](servicecredentials.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<windowsAuthentication>**  
  
## <a name="syntax"></a><span data-ttu-id="dcc92-104">구문</span><span class="sxs-lookup"><span data-stu-id="dcc92-104">Syntax</span></span>  
  
```xml  
<windowsAuthentication allowAnonymousLogons="Boolean"
                       includeWindowsGroups="Boolean" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="dcc92-105">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="dcc92-105">Attributes and Elements</span></span>  

 <span data-ttu-id="dcc92-106">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="dcc92-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="dcc92-107">특성</span><span class="sxs-lookup"><span data-stu-id="dcc92-107">Attributes</span></span>  
  
|<span data-ttu-id="dcc92-108">attribute</span><span class="sxs-lookup"><span data-stu-id="dcc92-108">Attribute</span></span>|<span data-ttu-id="dcc92-109">설명</span><span class="sxs-lookup"><span data-stu-id="dcc92-109">Description</span></span>|  
|---------------|-----------------|  
|`includeWindowsGroups`|<span data-ttu-id="dcc92-110">시스템의 보안 컨텍스트에 Windows 그룹이 포함되어 있는지 여부를 지정하는 선택적 부울 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="dcc92-110">An optional Boolean attribute that specifies whether the system includes Windows groups in the security context.</span></span> <span data-ttu-id="dcc92-111">기본값은 `true`입니다.</span><span class="sxs-lookup"><span data-stu-id="dcc92-111">The default is `true`.</span></span><br /><br /> <span data-ttu-id="dcc92-112">이 특성을 `true`로 설정하면 전체 그룹이 확장되므로 성능에 영향을 줍니다.</span><span class="sxs-lookup"><span data-stu-id="dcc92-112">Setting this attribute to `true` has a performance impact as it results in a full-group expansion.</span></span> <span data-ttu-id="dcc92-113">사용자가 속한 그룹의 목록을 설정할 필요가 없으면 이 특성을 `false`로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="dcc92-113">Set this attribute to `false` if you do not need to establish the list of groups a user belongs to.</span></span>|  
|`allowAnonymousLogons`|<span data-ttu-id="dcc92-114">익명의 인증되지 않은 호출자가 허용되는지 여부를 지정하는 선택적 부울 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="dcc92-114">An optional Boolean attribute that specifies whether anonymous, unauthenticated callers are allowed.</span></span> <span data-ttu-id="dcc92-115">기본값은 `false`입니다.</span><span class="sxs-lookup"><span data-stu-id="dcc92-115">The default is `false`.</span></span><br /><br /> <span data-ttu-id="dcc92-116">바인딩의 `clientCredentialType` 특성을 `Windows`로 설정하면 익명 호출자가 허용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="dcc92-116">When the `clientCredentialType` attribute of a binding is set to `Windows`, the system does not allow anonymous callers.</span></span> <span data-ttu-id="dcc92-117">즉, 도메인 또는 작업 그룹 인증 호출자가 시스템에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dcc92-117">This means that only domain or workgroup authenticated callers are allowed to access the system.</span></span> <span data-ttu-id="dcc92-118">이 특성을 사용하여 이 동작을 재정의할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dcc92-118">You can override this behavior by using this attribute.</span></span><br /><br /> <span data-ttu-id="dcc92-119">따라서 이 설정을 사용할 때는 특히 주의해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="dcc92-119">Use this setting with extreme caution.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="dcc92-120">자식 요소</span><span class="sxs-lookup"><span data-stu-id="dcc92-120">Child Elements</span></span>  

 <span data-ttu-id="dcc92-121">없음</span><span class="sxs-lookup"><span data-stu-id="dcc92-121">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="dcc92-122">부모 요소</span><span class="sxs-lookup"><span data-stu-id="dcc92-122">Parent Elements</span></span>  
  
|<span data-ttu-id="dcc92-123">요소</span><span class="sxs-lookup"><span data-stu-id="dcc92-123">Element</span></span>|<span data-ttu-id="dcc92-124">설명</span><span class="sxs-lookup"><span data-stu-id="dcc92-124">Description</span></span>|  
|-------------|-----------------|  
|[\<serviceCredentials>](servicecredentials.md)|<span data-ttu-id="dcc92-125">서비스를 인증하는 데 사용되는 자격 증명 및 클라이언트 자격 증명 유효성 검사 관련 설정을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="dcc92-125">Specifies the credential to be used in authenticating the service, and the client credential validation-related settings.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="dcc92-126">설명</span><span class="sxs-lookup"><span data-stu-id="dcc92-126">Remarks</span></span>  

 <span data-ttu-id="dcc92-127">`allowAnonymousLogons` 특성을 설정하여 익명 Windows 사용자 액세스를 허용할지 여부를 지정하려면 이 요소를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="dcc92-127">Use this element to specify whether to allow anonymous Windows users access by setting the `allowAnonymousLogons` attribute.</span></span> <span data-ttu-id="dcc92-128">또한 `includeWindowsGroups` 특성을 설정하여 사용자가 속한 그룹 정보를 AuthorizationContext에 포함시킬지 여부를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dcc92-128">You can also specify whether to include group information to which users belong in the AuthorizationContext by setting the `includeWindowsGroups` attribute.</span></span> <span data-ttu-id="dcc92-129">`true`(기본 설정)로 설정되면 서비스에서 클라이언트가 속해 있는 Windows 그룹을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dcc92-129">If it is set to `true` (the default setting), the service can determine the Windows groups to which the client belongs.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dcc92-130">참고 항목</span><span class="sxs-lookup"><span data-stu-id="dcc92-130">See also</span></span>

- <xref:System.ServiceModel.Configuration.WindowsServiceElement>
- <xref:System.ServiceModel.Configuration.ServiceCredentialsElement.WindowsAuthentication%2A>
- <xref:System.ServiceModel.Description.ServiceCredentials.WindowsAuthentication%2A>
- <xref:System.ServiceModel.Security.WindowsServiceCredential>
