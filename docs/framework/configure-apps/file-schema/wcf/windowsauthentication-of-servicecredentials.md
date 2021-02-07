---
description: '다음에 대 한 자세한 정보:: <windowsAuthentication><serviceCredentials>'
title: <serviceCredentials>의 <windowsAuthentication>
ms.date: 03/30/2017
ms.assetid: e0709473-0997-4de3-8f49-783527309a48
ms.openlocfilehash: 94f5804ac22a8c3ee1b8fc646ece8521ff639aec
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99682412"
---
# <a name="windowsauthentication-of-servicecredentials"></a><span data-ttu-id="feda0-103">\<serviceCredentials>의 \<windowsAuthentication></span><span class="sxs-lookup"><span data-stu-id="feda0-103">\<windowsAuthentication> of \<serviceCredentials></span></span>

<span data-ttu-id="feda0-104">Windows 서비스 자격 증명의 설정을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="feda0-104">Specifies the settings of a Windows service credential.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceCredentials>**](servicecredentials.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<windowsAuthentication>**  
  
## <a name="syntax"></a><span data-ttu-id="feda0-105">구문</span><span class="sxs-lookup"><span data-stu-id="feda0-105">Syntax</span></span>  
  
```xml  
<windowsAuthentication allowAnonymousLogons="Boolean"
                       includeWindowsGroups="Boolean" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="feda0-106">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="feda0-106">Attributes and Elements</span></span>  

 <span data-ttu-id="feda0-107">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="feda0-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="feda0-108">특성</span><span class="sxs-lookup"><span data-stu-id="feda0-108">Attributes</span></span>  
  
|<span data-ttu-id="feda0-109">attribute</span><span class="sxs-lookup"><span data-stu-id="feda0-109">Attribute</span></span>|<span data-ttu-id="feda0-110">설명</span><span class="sxs-lookup"><span data-stu-id="feda0-110">Description</span></span>|  
|---------------|-----------------|  
|`includeWindowsGroups`|<span data-ttu-id="feda0-111">시스템의 보안 컨텍스트에 Windows 그룹이 포함되어 있는지 여부를 지정하는 선택적 부울 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="feda0-111">An optional Boolean attribute that specifies whether the system includes Windows groups in the security context.</span></span> <span data-ttu-id="feda0-112">기본값은 `true`입니다.</span><span class="sxs-lookup"><span data-stu-id="feda0-112">The default is `true`.</span></span><br /><br /> <span data-ttu-id="feda0-113">이 특성을 `true`로 설정하면 전체 그룹이 확장되므로 성능에 영향을 줍니다.</span><span class="sxs-lookup"><span data-stu-id="feda0-113">Setting this attribute to `true` has a performance impact as it results in a full-group expansion.</span></span> <span data-ttu-id="feda0-114">사용자가 속한 그룹의 목록을 설정할 필요가 없으면 이 특성을 `false`로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="feda0-114">Set this attribute to `false` if you do not need to establish the list of groups a user belongs to.</span></span>|  
|`allowAnonymousLogons`|<span data-ttu-id="feda0-115">익명의 인증되지 않은 호출자가 허용되는지 여부를 지정하는 선택적 부울 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="feda0-115">An optional Boolean attribute that specifies whether anonymous, unauthenticated callers are allowed.</span></span> <span data-ttu-id="feda0-116">기본값은 `false`입니다.</span><span class="sxs-lookup"><span data-stu-id="feda0-116">The default is `false`.</span></span><br /><br /> <span data-ttu-id="feda0-117">바인딩의 `clientCredentialType` 특성을 `Windows`로 설정하면 익명 호출자가 허용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="feda0-117">When the `clientCredentialType` attribute of a binding is set to `Windows`, the system does not allow anonymous callers.</span></span> <span data-ttu-id="feda0-118">즉, 도메인 또는 작업 그룹 인증 호출자가 시스템에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="feda0-118">This means that only domain or workgroup authenticated callers are allowed to access the system.</span></span> <span data-ttu-id="feda0-119">이 특성을 사용하여 이 동작을 재정의할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="feda0-119">You can override this behavior by using this attribute.</span></span><br /><br /> <span data-ttu-id="feda0-120">따라서 이 설정을 사용할 때는 특히 주의해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="feda0-120">Use this setting with extreme caution.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="feda0-121">자식 요소</span><span class="sxs-lookup"><span data-stu-id="feda0-121">Child Elements</span></span>  

 <span data-ttu-id="feda0-122">없음</span><span class="sxs-lookup"><span data-stu-id="feda0-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="feda0-123">부모 요소</span><span class="sxs-lookup"><span data-stu-id="feda0-123">Parent Elements</span></span>  
  
|<span data-ttu-id="feda0-124">요소</span><span class="sxs-lookup"><span data-stu-id="feda0-124">Element</span></span>|<span data-ttu-id="feda0-125">설명</span><span class="sxs-lookup"><span data-stu-id="feda0-125">Description</span></span>|  
|-------------|-----------------|  
|[\<serviceCredentials>](servicecredentials.md)|<span data-ttu-id="feda0-126">서비스를 인증하는 데 사용되는 자격 증명 및 클라이언트 자격 증명 유효성 검사 관련 설정을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="feda0-126">Specifies the credential to be used in authenticating the service, and the client credential validation-related settings.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="feda0-127">설명</span><span class="sxs-lookup"><span data-stu-id="feda0-127">Remarks</span></span>  

 <span data-ttu-id="feda0-128">`allowAnonymousLogons` 특성을 설정하여 익명 Windows 사용자 액세스를 허용할지 여부를 지정하려면 이 요소를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="feda0-128">Use this element to specify whether to allow anonymous Windows users access by setting the `allowAnonymousLogons` attribute.</span></span> <span data-ttu-id="feda0-129">또한 `includeWindowsGroups` 특성을 설정하여 사용자가 속한 그룹 정보를 AuthorizationContext에 포함시킬지 여부를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="feda0-129">You can also specify whether to include group information to which users belong in the AuthorizationContext by setting the `includeWindowsGroups` attribute.</span></span> <span data-ttu-id="feda0-130">`true`(기본 설정)로 설정되면 서비스에서 클라이언트가 속해 있는 Windows 그룹을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="feda0-130">If it is set to `true` (the default setting), the service can determine the Windows groups to which the client belongs.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="feda0-131">참고 항목</span><span class="sxs-lookup"><span data-stu-id="feda0-131">See also</span></span>

- <xref:System.ServiceModel.Configuration.WindowsServiceElement>
- <xref:System.ServiceModel.Configuration.ServiceCredentialsElement.WindowsAuthentication%2A>
- <xref:System.ServiceModel.Description.ServiceCredentials.WindowsAuthentication%2A>
- <xref:System.ServiceModel.Security.WindowsServiceCredential>
