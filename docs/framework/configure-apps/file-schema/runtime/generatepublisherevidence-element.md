---
title: <generatePublisherEvidence> 요소
ms.date: 03/30/2017
helpviewer_keywords:
- generatePublisherEvidence element
- <generatePublisherEvidence> element
ms.assetid: 7d208f50-e8d5-4a42-bc1a-1cf3590706a8
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 09a12f062b2fe3ad6e5ac90f0d268bbbeab44876
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59198922"
---
# <a name="generatepublisherevidence-element"></a><span data-ttu-id="9b80a-102">\<generatePublisherEvidence > 요소</span><span class="sxs-lookup"><span data-stu-id="9b80a-102">\<generatePublisherEvidence> Element</span></span>
<span data-ttu-id="9b80a-103">런타임을 만드는 지 여부를 지정 <xref:System.Security.Policy.Publisher> 코드 액세스 보안 (CA)에 대 한 증거입니다.</span><span class="sxs-lookup"><span data-stu-id="9b80a-103">Specifies whether the runtime creates <xref:System.Security.Policy.Publisher> evidence for code access security (CAS).</span></span>  
  
 <span data-ttu-id="9b80a-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="9b80a-104">\<configuration></span></span>  
<span data-ttu-id="9b80a-105">\<runtime></span><span class="sxs-lookup"><span data-stu-id="9b80a-105">\<runtime></span></span>  
<span data-ttu-id="9b80a-106">\<generatePublisherEvidence></span><span class="sxs-lookup"><span data-stu-id="9b80a-106">\<generatePublisherEvidence></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9b80a-107">구문</span><span class="sxs-lookup"><span data-stu-id="9b80a-107">Syntax</span></span>  
  
```xml  
<generatePublisherEvidence    
   enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="9b80a-108">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="9b80a-108">Attributes and Elements</span></span>  
 <span data-ttu-id="9b80a-109">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="9b80a-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="9b80a-110">특성</span><span class="sxs-lookup"><span data-stu-id="9b80a-110">Attributes</span></span>  
  
|<span data-ttu-id="9b80a-111">특성</span><span class="sxs-lookup"><span data-stu-id="9b80a-111">Attribute</span></span>|<span data-ttu-id="9b80a-112">설명</span><span class="sxs-lookup"><span data-stu-id="9b80a-112">Description</span></span>|  
|---------------|-----------------|  
|`enabled`|<span data-ttu-id="9b80a-113">필수 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="9b80a-113">Required attribute.</span></span><br /><br /> <span data-ttu-id="9b80a-114">런타임을 만드는 지 여부를 지정 <xref:System.Security.Policy.Publisher> 증명 정보입니다.</span><span class="sxs-lookup"><span data-stu-id="9b80a-114">Specifies whether the runtime creates <xref:System.Security.Policy.Publisher> evidence.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="9b80a-115">enabled 특성</span><span class="sxs-lookup"><span data-stu-id="9b80a-115">enabled Attribute</span></span>  
  
|<span data-ttu-id="9b80a-116">값</span><span class="sxs-lookup"><span data-stu-id="9b80a-116">Value</span></span>|<span data-ttu-id="9b80a-117">설명</span><span class="sxs-lookup"><span data-stu-id="9b80a-117">Description</span></span>|  
|-----------|-----------------|  
|`false`|<span data-ttu-id="9b80a-118">만들어지지는지 않습니다 <xref:System.Security.Policy.Publisher> 증명 정보입니다.</span><span class="sxs-lookup"><span data-stu-id="9b80a-118">Does not create <xref:System.Security.Policy.Publisher> evidence.</span></span>|  
|`true`|<span data-ttu-id="9b80a-119">만듭니다 <xref:System.Security.Policy.Publisher> 증명 정보입니다.</span><span class="sxs-lookup"><span data-stu-id="9b80a-119">Creates <xref:System.Security.Policy.Publisher> evidence.</span></span> <span data-ttu-id="9b80a-120">이 값이 기본값입니다.</span><span class="sxs-lookup"><span data-stu-id="9b80a-120">This is the default.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="9b80a-121">자식 요소</span><span class="sxs-lookup"><span data-stu-id="9b80a-121">Child Elements</span></span>  
 <span data-ttu-id="9b80a-122">없음</span><span class="sxs-lookup"><span data-stu-id="9b80a-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="9b80a-123">부모 요소</span><span class="sxs-lookup"><span data-stu-id="9b80a-123">Parent Elements</span></span>  
  
|<span data-ttu-id="9b80a-124">요소</span><span class="sxs-lookup"><span data-stu-id="9b80a-124">Element</span></span>|<span data-ttu-id="9b80a-125">설명</span><span class="sxs-lookup"><span data-stu-id="9b80a-125">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="9b80a-126">공용 언어 런타임 및 .NET Framework 애플리케이션에서 사용하는 모든 구성 파일의 루트 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="9b80a-126">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="9b80a-127">런타임 초기화 옵션에 대한 정보를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="9b80a-127">Contains information about runtime initialization options.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9b80a-128">설명</span><span class="sxs-lookup"><span data-stu-id="9b80a-128">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="9b80a-129">에 [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)] 및 나중에이 요소에 어셈블리 로드 시간에 영향을 주지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="9b80a-129">In the [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)] and later, this element has no effect on assembly load times.</span></span> <span data-ttu-id="9b80a-130">자세한 내용은의 "보안 정책 단순화" 섹션을 참조 하세요 [보안 변경 내용](../../../../../docs/framework/security/security-changes.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="9b80a-130">For more information, see the "Security Policy Simplification" section in [Security Changes](../../../../../docs/framework/security/security-changes.md).</span></span>  
  
 <span data-ttu-id="9b80a-131">만들려는 로드 시 Authenticode 서명을 확인 하려고 하는 CLR (공용 언어 런타임) <xref:System.Security.Policy.Publisher> 어셈블리 증명 정보입니다.</span><span class="sxs-lookup"><span data-stu-id="9b80a-131">The common language runtime (CLR) tries to verify the Authenticode signature at load time to create <xref:System.Security.Policy.Publisher> evidence for the assembly.</span></span> <span data-ttu-id="9b80a-132">그러나 기본적으로 대부분의 응용 프로그램 않아도 <xref:System.Security.Policy.Publisher> 증명 정보입니다.</span><span class="sxs-lookup"><span data-stu-id="9b80a-132">However, by default, most applications do not need <xref:System.Security.Policy.Publisher> evidence.</span></span> <span data-ttu-id="9b80a-133">표준 CAS 정책을 사용 하지는 <xref:System.Security.Policy.PublisherMembershipCondition>합니다.</span><span class="sxs-lookup"><span data-stu-id="9b80a-133">Standard CAS policy does not rely on the <xref:System.Security.Policy.PublisherMembershipCondition>.</span></span> <span data-ttu-id="9b80a-134">관련 응용 프로그램 사용자 지정 CAS 정책 사용 하 여 컴퓨터에서 실행 하거나에 대 한 요구를 충족 하려는 경우가 아니면 게시자 서명 확인 된 불필요 한 시작 비용은 안 <xref:System.Security.Permissions.PublisherIdentityPermission> 부분 신뢰 환경에서.</span><span class="sxs-lookup"><span data-stu-id="9b80a-134">You should avoid the unnecessary startup cost associated with verifying the publisher signature unless your application executes on a computer with custom CAS policy, or is intending to satisfy demands for <xref:System.Security.Permissions.PublisherIdentityPermission> in a partial-trust environment.</span></span> <span data-ttu-id="9b80a-135">(Id 권한 요청이 항상 완전 신뢰 환경에서 성공 합니다.)</span><span class="sxs-lookup"><span data-stu-id="9b80a-135">(Demands for identity permissions always succeed in a full-trust environment.)</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="9b80a-136">사용 하 여 서비스 하는 것이 좋습니다는 `<generatePublisherEvidence>` 시작 성능을 개선 하는 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="9b80a-136">We recommend that services use the `<generatePublisherEvidence>` element to improve startup performance.</span></span>  <span data-ttu-id="9b80a-137">이 요소를 사용 하는 시간 제한 및 서비스의 시작을 취소 될 수 있는 지연을 방지할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9b80a-137">Using this element can also help avoid delays that can cause a time-out and the cancellation of the service startup.</span></span>  
  
## <a name="configuration-file"></a><span data-ttu-id="9b80a-138">구성 파일</span><span class="sxs-lookup"><span data-stu-id="9b80a-138">Configuration File</span></span>  
 <span data-ttu-id="9b80a-139">이 요소는 응용 프로그램 구성 파일에만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9b80a-139">This element can be used only in the application configuration file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="9b80a-140">예제</span><span class="sxs-lookup"><span data-stu-id="9b80a-140">Example</span></span>  
 <span data-ttu-id="9b80a-141">다음 예제에서는 사용 하는 방법의 `<generatePublisherEvidence>` 요소를 응용 프로그램에 대 한 게시자 정책 CA에 대 한 확인을 사용 하지 않도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="9b80a-141">The following example shows how to use the `<generatePublisherEvidence>` element to disable checking for CAS publisher policy for an application.</span></span>  
  
```xml  
<configuration>  
    <runtime>  
        <generatePublisherEvidence enabled="false"/>  
    </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="9b80a-142">참고자료</span><span class="sxs-lookup"><span data-stu-id="9b80a-142">See also</span></span>

- [<span data-ttu-id="9b80a-143">런타임 설정 스키마</span><span class="sxs-lookup"><span data-stu-id="9b80a-143">Runtime Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)
- [<span data-ttu-id="9b80a-144">구성 파일 스키마</span><span class="sxs-lookup"><span data-stu-id="9b80a-144">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)
