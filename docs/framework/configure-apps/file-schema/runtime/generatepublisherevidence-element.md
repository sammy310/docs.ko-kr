---
title: <generatePublisherEvidence> 요소
ms.date: 03/30/2017
helpviewer_keywords:
- generatePublisherEvidence element
- <generatePublisherEvidence> element
ms.assetid: 7d208f50-e8d5-4a42-bc1a-1cf3590706a8
ms.openlocfilehash: c2ba4a7244b7849e28eac38fb34a2cdd0d1f1048
ms.sourcegitcommit: 62285ec11fa8e8424bab00511a90760c60e63c95
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/20/2020
ms.locfileid: "81645351"
---
# <a name="generatepublisherevidence-element"></a><span data-ttu-id="d1743-102">\<generatePublisherEvidence> 요소</span><span class="sxs-lookup"><span data-stu-id="d1743-102">\<generatePublisherEvidence> Element</span></span>
<span data-ttu-id="d1743-103">런타임이 CAS(코드 <xref:System.Security.Policy.Publisher> 액세스 보안)에 대한 증명 을 만드는지 여부를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="d1743-103">Specifies whether the runtime creates <xref:System.Security.Policy.Publisher> evidence for code access security (CAS).</span></span>  
  
<span data-ttu-id="d1743-104">[**\<구성>**](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="d1743-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="d1743-105">&nbsp;&nbsp;[**\<런타임>**](runtime-element.md)</span><span class="sxs-lookup"><span data-stu-id="d1743-105">&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)</span></span>\
<span data-ttu-id="d1743-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<생성게시자>**</span><span class="sxs-lookup"><span data-stu-id="d1743-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<generatePublisherEvidence>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d1743-107">구문</span><span class="sxs-lookup"><span data-stu-id="d1743-107">Syntax</span></span>  
  
```xml  
<generatePublisherEvidence
   enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="d1743-108">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="d1743-108">Attributes and Elements</span></span>  
 <span data-ttu-id="d1743-109">다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="d1743-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="d1743-110">특성</span><span class="sxs-lookup"><span data-stu-id="d1743-110">Attributes</span></span>  
  
|<span data-ttu-id="d1743-111">attribute</span><span class="sxs-lookup"><span data-stu-id="d1743-111">Attribute</span></span>|<span data-ttu-id="d1743-112">Description</span><span class="sxs-lookup"><span data-stu-id="d1743-112">Description</span></span>|  
|---------------|-----------------|  
|`enabled`|<span data-ttu-id="d1743-113">필수 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="d1743-113">Required attribute.</span></span><br /><br /> <span data-ttu-id="d1743-114">런타임에서 증명 증명 <xref:System.Security.Policy.Publisher> 을 만드는지 여부를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="d1743-114">Specifies whether the runtime creates <xref:System.Security.Policy.Publisher> evidence.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="d1743-115">enabled 특성</span><span class="sxs-lookup"><span data-stu-id="d1743-115">enabled Attribute</span></span>  
  
|<span data-ttu-id="d1743-116">값</span><span class="sxs-lookup"><span data-stu-id="d1743-116">Value</span></span>|<span data-ttu-id="d1743-117">설명</span><span class="sxs-lookup"><span data-stu-id="d1743-117">Description</span></span>|  
|-----------|-----------------|  
|`false`|<span data-ttu-id="d1743-118">증거를 만들지 <xref:System.Security.Policy.Publisher> 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d1743-118">Does not create <xref:System.Security.Policy.Publisher> evidence.</span></span>|  
|`true`|<span data-ttu-id="d1743-119">증거를 <xref:System.Security.Policy.Publisher> 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="d1743-119">Creates <xref:System.Security.Policy.Publisher> evidence.</span></span> <span data-ttu-id="d1743-120">이것이 기본값입니다.</span><span class="sxs-lookup"><span data-stu-id="d1743-120">This is the default.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="d1743-121">자식 요소</span><span class="sxs-lookup"><span data-stu-id="d1743-121">Child Elements</span></span>  
 <span data-ttu-id="d1743-122">없음</span><span class="sxs-lookup"><span data-stu-id="d1743-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="d1743-123">부모 요소</span><span class="sxs-lookup"><span data-stu-id="d1743-123">Parent Elements</span></span>  
  
|<span data-ttu-id="d1743-124">요소</span><span class="sxs-lookup"><span data-stu-id="d1743-124">Element</span></span>|<span data-ttu-id="d1743-125">Description</span><span class="sxs-lookup"><span data-stu-id="d1743-125">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="d1743-126">공용 언어 런타임 및 .NET Framework 애플리케이션에서 사용하는 모든 구성 파일의 루트 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="d1743-126">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="d1743-127">런타임 초기화 옵션에 대한 정보를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="d1743-127">Contains information about runtime initialization options.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d1743-128">설명</span><span class="sxs-lookup"><span data-stu-id="d1743-128">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="d1743-129">.NET Framework 4 이상에서는 이 요소가 어셈블리 로드 시간에 영향을 주지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d1743-129">In the .NET Framework 4 and later, this element has no effect on assembly load times.</span></span> <span data-ttu-id="d1743-130">자세한 내용은 [보안 변경의](https://docs.microsoft.com/previous-versions/dotnet/framework/security/security-changes)"보안 정책 단순화" 섹션을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="d1743-130">For more information, see the "Security Policy Simplification" section in [Security Changes](https://docs.microsoft.com/previous-versions/dotnet/framework/security/security-changes).</span></span>  
  
 <span data-ttu-id="d1743-131">공통 언어 런타임(CLR)은 로드 시 Authenticode 서명을 <xref:System.Security.Policy.Publisher> 확인하여 어셈블리에 대한 증거를 만들려고 합니다.</span><span class="sxs-lookup"><span data-stu-id="d1743-131">The common language runtime (CLR) tries to verify the Authenticode signature at load time to create <xref:System.Security.Policy.Publisher> evidence for the assembly.</span></span> <span data-ttu-id="d1743-132">그러나 기본적으로 대부분의 응용 프로그램에는 <xref:System.Security.Policy.Publisher> 증거가 필요하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d1743-132">However, by default, most applications do not need <xref:System.Security.Policy.Publisher> evidence.</span></span> <span data-ttu-id="d1743-133">표준 CAS 정책은 <xref:System.Security.Policy.PublisherMembershipCondition>에 의존하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d1743-133">Standard CAS policy does not rely on the <xref:System.Security.Policy.PublisherMembershipCondition>.</span></span> <span data-ttu-id="d1743-134">응용 프로그램이 사용자 지정 CAS 정책을 사용하여 컴퓨터에서 실행되거나 부분 신뢰 환경에서 요구 사항을 <xref:System.Security.Permissions.PublisherIdentityPermission> 충족하려는 경우가 아니면 게시자 서명 확인과 관련된 불필요한 시작 비용을 피해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d1743-134">You should avoid the unnecessary startup cost associated with verifying the publisher signature unless your application executes on a computer with custom CAS policy, or is intending to satisfy demands for <xref:System.Security.Permissions.PublisherIdentityPermission> in a partial-trust environment.</span></span> <span data-ttu-id="d1743-135">ID 권한에 대한 요구는 항상 완전 신뢰 환경에서 성공합니다.</span><span class="sxs-lookup"><span data-stu-id="d1743-135">(Demands for identity permissions always succeed in a full-trust environment.)</span></span>  
  
> [!NOTE]
> <span data-ttu-id="d1743-136">서비스는 `<generatePublisherEvidence>` 시작 성능을 향상시키기 위해 요소를 사용하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="d1743-136">We recommend that services use the `<generatePublisherEvidence>` element to improve startup performance.</span></span>  <span data-ttu-id="d1743-137">이 요소를 사용하면 시간 시간 및 서비스 시작 취소를 유발할 수 있는 지연을 방지할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d1743-137">Using this element can also help avoid delays that can cause a time-out and the cancellation of the service startup.</span></span>  
  
## <a name="configuration-file"></a><span data-ttu-id="d1743-138">구성 파일</span><span class="sxs-lookup"><span data-stu-id="d1743-138">Configuration File</span></span>  
 <span data-ttu-id="d1743-139">이 요소는 응용 프로그램 구성 파일에서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d1743-139">This element can be used only in the application configuration file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d1743-140">예제</span><span class="sxs-lookup"><span data-stu-id="d1743-140">Example</span></span>  
 <span data-ttu-id="d1743-141">다음 예제에서는 `<generatePublisherEvidence>` 요소를 사용하여 응용 프로그램에 대한 CAS 게시자 정책 검사를 사용하지 않도록 설정하는 방법을 보여 주습니다.</span><span class="sxs-lookup"><span data-stu-id="d1743-141">The following example shows how to use the `<generatePublisherEvidence>` element to disable checking for CAS publisher policy for an application.</span></span>  
  
```xml  
<configuration>  
    <runtime>  
        <generatePublisherEvidence enabled="false"/>  
    </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="d1743-142">참고 항목</span><span class="sxs-lookup"><span data-stu-id="d1743-142">See also</span></span>

- [<span data-ttu-id="d1743-143">런타임 설정 스키마</span><span class="sxs-lookup"><span data-stu-id="d1743-143">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="d1743-144">구성 파일 스키마</span><span class="sxs-lookup"><span data-stu-id="d1743-144">Configuration File Schema</span></span>](../index.md)
