---
title: <generatePublisherEvidence> 요소
ms.date: 03/30/2017
helpviewer_keywords:
- generatePublisherEvidence element
- <generatePublisherEvidence> element
ms.assetid: 7d208f50-e8d5-4a42-bc1a-1cf3590706a8
ms.openlocfilehash: c2ba4a7244b7849e28eac38fb34a2cdd0d1f1048
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/06/2020
ms.locfileid: "81645351"
---
# <a name="generatepublisherevidence-element"></a><span data-ttu-id="3cd44-102">\<generatePublisherEvidence> 요소</span><span class="sxs-lookup"><span data-stu-id="3cd44-102">\<generatePublisherEvidence> Element</span></span>
<span data-ttu-id="3cd44-103">런타임에서 <xref:System.Security.Policy.Publisher> CAS (코드 액세스 보안)에 대 한 증명 정보를 만들지 여부를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="3cd44-103">Specifies whether the runtime creates <xref:System.Security.Policy.Publisher> evidence for code access security (CAS).</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<generatePublisherEvidence>**  
  
## <a name="syntax"></a><span data-ttu-id="3cd44-104">구문</span><span class="sxs-lookup"><span data-stu-id="3cd44-104">Syntax</span></span>  
  
```xml  
<generatePublisherEvidence
   enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="3cd44-105">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="3cd44-105">Attributes and Elements</span></span>  
 <span data-ttu-id="3cd44-106">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="3cd44-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="3cd44-107">특성</span><span class="sxs-lookup"><span data-stu-id="3cd44-107">Attributes</span></span>  
  
|<span data-ttu-id="3cd44-108">attribute</span><span class="sxs-lookup"><span data-stu-id="3cd44-108">Attribute</span></span>|<span data-ttu-id="3cd44-109">Description</span><span class="sxs-lookup"><span data-stu-id="3cd44-109">Description</span></span>|  
|---------------|-----------------|  
|`enabled`|<span data-ttu-id="3cd44-110">필수 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="3cd44-110">Required attribute.</span></span><br /><br /> <span data-ttu-id="3cd44-111">런타임에서 증명 정보를 만들지 여부를 지정 합니다 <xref:System.Security.Policy.Publisher> .</span><span class="sxs-lookup"><span data-stu-id="3cd44-111">Specifies whether the runtime creates <xref:System.Security.Policy.Publisher> evidence.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="3cd44-112">enabled 특성</span><span class="sxs-lookup"><span data-stu-id="3cd44-112">enabled Attribute</span></span>  
  
|<span data-ttu-id="3cd44-113">값</span><span class="sxs-lookup"><span data-stu-id="3cd44-113">Value</span></span>|<span data-ttu-id="3cd44-114">Description</span><span class="sxs-lookup"><span data-stu-id="3cd44-114">Description</span></span>|  
|-----------|-----------------|  
|`false`|<span data-ttu-id="3cd44-115"><xref:System.Security.Policy.Publisher>증명 정보를 만들지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="3cd44-115">Does not create <xref:System.Security.Policy.Publisher> evidence.</span></span>|  
|`true`|<span data-ttu-id="3cd44-116"><xref:System.Security.Policy.Publisher>증명 정보를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="3cd44-116">Creates <xref:System.Security.Policy.Publisher> evidence.</span></span> <span data-ttu-id="3cd44-117">기본값입니다.</span><span class="sxs-lookup"><span data-stu-id="3cd44-117">This is the default.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="3cd44-118">자식 요소</span><span class="sxs-lookup"><span data-stu-id="3cd44-118">Child Elements</span></span>  
 <span data-ttu-id="3cd44-119">없음</span><span class="sxs-lookup"><span data-stu-id="3cd44-119">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="3cd44-120">부모 요소</span><span class="sxs-lookup"><span data-stu-id="3cd44-120">Parent Elements</span></span>  
  
|<span data-ttu-id="3cd44-121">요소</span><span class="sxs-lookup"><span data-stu-id="3cd44-121">Element</span></span>|<span data-ttu-id="3cd44-122">Description</span><span class="sxs-lookup"><span data-stu-id="3cd44-122">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="3cd44-123">공용 언어 런타임 및 .NET Framework 애플리케이션에서 사용하는 모든 구성 파일의 루트 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="3cd44-123">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="3cd44-124">런타임 초기화 옵션에 대한 정보를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="3cd44-124">Contains information about runtime initialization options.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3cd44-125">설명</span><span class="sxs-lookup"><span data-stu-id="3cd44-125">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="3cd44-126">.NET Framework 4 이상에서이 요소는 어셈블리 로드 시간에 영향을 주지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="3cd44-126">In the .NET Framework 4 and later, this element has no effect on assembly load times.</span></span> <span data-ttu-id="3cd44-127">자세한 내용은 [보안 변경 내용](https://docs.microsoft.com/previous-versions/dotnet/framework/security/security-changes)의 "보안 정책 단순화" 섹션을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="3cd44-127">For more information, see the "Security Policy Simplification" section in [Security Changes](https://docs.microsoft.com/previous-versions/dotnet/framework/security/security-changes).</span></span>  
  
 <span data-ttu-id="3cd44-128">CLR (공용 언어 런타임)은 로드할 때 Authenticode 서명을 확인 하 여 <xref:System.Security.Policy.Publisher> 어셈블리에 대 한 증명 정보를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="3cd44-128">The common language runtime (CLR) tries to verify the Authenticode signature at load time to create <xref:System.Security.Policy.Publisher> evidence for the assembly.</span></span> <span data-ttu-id="3cd44-129">그러나 대부분의 응용 프로그램에는 기본적으로 증명 정보가 필요 하지 않습니다 <xref:System.Security.Policy.Publisher> .</span><span class="sxs-lookup"><span data-stu-id="3cd44-129">However, by default, most applications do not need <xref:System.Security.Policy.Publisher> evidence.</span></span> <span data-ttu-id="3cd44-130">표준 CAS 정책은를 사용 하지 않습니다 <xref:System.Security.Policy.PublisherMembershipCondition> .</span><span class="sxs-lookup"><span data-stu-id="3cd44-130">Standard CAS policy does not rely on the <xref:System.Security.Policy.PublisherMembershipCondition>.</span></span> <span data-ttu-id="3cd44-131">응용 프로그램이 사용자 지정 CAS 정책을 사용 하는 컴퓨터에서 실행 되지 않거나 <xref:System.Security.Permissions.PublisherIdentityPermission> 부분 신뢰 환경에서에 대 한 요구를 충족 하는 경우에만 게시자 서명 확인에 관련 된 불필요 한 시작 비용을 피해 야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3cd44-131">You should avoid the unnecessary startup cost associated with verifying the publisher signature unless your application executes on a computer with custom CAS policy, or is intending to satisfy demands for <xref:System.Security.Permissions.PublisherIdentityPermission> in a partial-trust environment.</span></span> <span data-ttu-id="3cd44-132">(Id 권한 요구는 항상 완전 신뢰 환경에서 성공 합니다.)</span><span class="sxs-lookup"><span data-stu-id="3cd44-132">(Demands for identity permissions always succeed in a full-trust environment.)</span></span>  
  
> [!NOTE]
> <span data-ttu-id="3cd44-133">서비스에서 요소를 사용 하 여 `<generatePublisherEvidence>` 시작 성능을 향상 시키는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="3cd44-133">We recommend that services use the `<generatePublisherEvidence>` element to improve startup performance.</span></span>  <span data-ttu-id="3cd44-134">이 요소를 사용 하면 시간 초과 및 서비스 시작 취소가 발생할 수 있는 지연을 방지할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3cd44-134">Using this element can also help avoid delays that can cause a time-out and the cancellation of the service startup.</span></span>  
  
## <a name="configuration-file"></a><span data-ttu-id="3cd44-135">구성 파일</span><span class="sxs-lookup"><span data-stu-id="3cd44-135">Configuration File</span></span>  
 <span data-ttu-id="3cd44-136">이 요소는 응용 프로그램 구성 파일에만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3cd44-136">This element can be used only in the application configuration file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="3cd44-137">예제</span><span class="sxs-lookup"><span data-stu-id="3cd44-137">Example</span></span>  
 <span data-ttu-id="3cd44-138">다음 예제에서는 요소를 사용 하 여 `<generatePublisherEvidence>` 응용 프로그램에 대 한 CAS 게시자 정책 검사를 사용 하지 않도록 설정 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="3cd44-138">The following example shows how to use the `<generatePublisherEvidence>` element to disable checking for CAS publisher policy for an application.</span></span>  
  
```xml  
<configuration>  
    <runtime>  
        <generatePublisherEvidence enabled="false"/>  
    </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="3cd44-139">참고 항목</span><span class="sxs-lookup"><span data-stu-id="3cd44-139">See also</span></span>

- [<span data-ttu-id="3cd44-140">런타임 설정 스키마</span><span class="sxs-lookup"><span data-stu-id="3cd44-140">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="3cd44-141">구성 파일 스키마</span><span class="sxs-lookup"><span data-stu-id="3cd44-141">Configuration File Schema</span></span>](../index.md)
