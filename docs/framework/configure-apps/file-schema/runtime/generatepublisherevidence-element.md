---
title: <generatePublisherEvidence> 요소
ms.date: 03/30/2017
helpviewer_keywords:
- generatePublisherEvidence element
- <generatePublisherEvidence> element
ms.assetid: 7d208f50-e8d5-4a42-bc1a-1cf3590706a8
ms.openlocfilehash: b04ef53d6e9c3d954b0925ea8634b3d220b36af7
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73116579"
---
# <a name="generatepublisherevidence-element"></a><span data-ttu-id="fe6a7-102">\<generatePublisherEvidence > 요소</span><span class="sxs-lookup"><span data-stu-id="fe6a7-102">\<generatePublisherEvidence> Element</span></span>
<span data-ttu-id="fe6a7-103">런타임이 CAS (코드 액세스 보안)에 대 한 <xref:System.Security.Policy.Publisher> 증명 정보를 만들지 여부를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="fe6a7-103">Specifies whether the runtime creates <xref:System.Security.Policy.Publisher> evidence for code access security (CAS).</span></span>  
  
<span data-ttu-id="fe6a7-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="fe6a7-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="fe6a7-105">&nbsp; &nbsp;[ **\<runtime >** ](runtime-element.md) </span><span class="sxs-lookup"><span data-stu-id="fe6a7-105">&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)</span></span>\
<span data-ttu-id="fe6a7-106">&nbsp;&nbsp;&nbsp;&nbsp; **\<generatePublisherEvidence >**</span><span class="sxs-lookup"><span data-stu-id="fe6a7-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<generatePublisherEvidence>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fe6a7-107">구문</span><span class="sxs-lookup"><span data-stu-id="fe6a7-107">Syntax</span></span>  
  
```xml  
<generatePublisherEvidence    
   enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="fe6a7-108">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="fe6a7-108">Attributes and Elements</span></span>  
 <span data-ttu-id="fe6a7-109">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="fe6a7-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="fe6a7-110">특성</span><span class="sxs-lookup"><span data-stu-id="fe6a7-110">Attributes</span></span>  
  
|<span data-ttu-id="fe6a7-111">특성</span><span class="sxs-lookup"><span data-stu-id="fe6a7-111">Attribute</span></span>|<span data-ttu-id="fe6a7-112">설명</span><span class="sxs-lookup"><span data-stu-id="fe6a7-112">Description</span></span>|  
|---------------|-----------------|  
|`enabled`|<span data-ttu-id="fe6a7-113">필수 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="fe6a7-113">Required attribute.</span></span><br /><br /> <span data-ttu-id="fe6a7-114">런타임이 <xref:System.Security.Policy.Publisher> 증명 정보를 만들지 여부를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="fe6a7-114">Specifies whether the runtime creates <xref:System.Security.Policy.Publisher> evidence.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="fe6a7-115">enabled 특성</span><span class="sxs-lookup"><span data-stu-id="fe6a7-115">enabled Attribute</span></span>  
  
|<span data-ttu-id="fe6a7-116">값</span><span class="sxs-lookup"><span data-stu-id="fe6a7-116">Value</span></span>|<span data-ttu-id="fe6a7-117">설명</span><span class="sxs-lookup"><span data-stu-id="fe6a7-117">Description</span></span>|  
|-----------|-----------------|  
|`false`|<span data-ttu-id="fe6a7-118"><xref:System.Security.Policy.Publisher> 증명 정보를 만들지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="fe6a7-118">Does not create <xref:System.Security.Policy.Publisher> evidence.</span></span>|  
|`true`|<span data-ttu-id="fe6a7-119"><xref:System.Security.Policy.Publisher> 증명 정보를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="fe6a7-119">Creates <xref:System.Security.Policy.Publisher> evidence.</span></span> <span data-ttu-id="fe6a7-120">기본값입니다.</span><span class="sxs-lookup"><span data-stu-id="fe6a7-120">This is the default.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="fe6a7-121">자식 요소</span><span class="sxs-lookup"><span data-stu-id="fe6a7-121">Child Elements</span></span>  
 <span data-ttu-id="fe6a7-122">없음.</span><span class="sxs-lookup"><span data-stu-id="fe6a7-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="fe6a7-123">부모 요소</span><span class="sxs-lookup"><span data-stu-id="fe6a7-123">Parent Elements</span></span>  
  
|<span data-ttu-id="fe6a7-124">요소</span><span class="sxs-lookup"><span data-stu-id="fe6a7-124">Element</span></span>|<span data-ttu-id="fe6a7-125">설명</span><span class="sxs-lookup"><span data-stu-id="fe6a7-125">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="fe6a7-126">공용 언어 런타임 및 .NET Framework 애플리케이션에서 사용하는 모든 구성 파일의 루트 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="fe6a7-126">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="fe6a7-127">런타임 초기화 옵션에 대한 정보를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="fe6a7-127">Contains information about runtime initialization options.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="fe6a7-128">주의</span><span class="sxs-lookup"><span data-stu-id="fe6a7-128">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="fe6a7-129">.NET Framework 4 이상에서이 요소는 어셈블리 로드 시간에 영향을 주지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="fe6a7-129">In the .NET Framework 4 and later, this element has no effect on assembly load times.</span></span> <span data-ttu-id="fe6a7-130">자세한 내용은 [보안 변경 내용](../../../security/security-changes.md)의 "보안 정책 단순화" 섹션을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="fe6a7-130">For more information, see the "Security Policy Simplification" section in [Security Changes](../../../security/security-changes.md).</span></span>  
  
 <span data-ttu-id="fe6a7-131">CLR (공용 언어 런타임)은 로드할 때 Authenticode 서명을 확인 하 여 어셈블리에 대 한 <xref:System.Security.Policy.Publisher> 증명 정보를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="fe6a7-131">The common language runtime (CLR) tries to verify the Authenticode signature at load time to create <xref:System.Security.Policy.Publisher> evidence for the assembly.</span></span> <span data-ttu-id="fe6a7-132">그러나 기본적으로 대부분의 응용 프로그램에는 <xref:System.Security.Policy.Publisher> 증명 정보가 필요 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="fe6a7-132">However, by default, most applications do not need <xref:System.Security.Policy.Publisher> evidence.</span></span> <span data-ttu-id="fe6a7-133">표준 CAS 정책은 <xref:System.Security.Policy.PublisherMembershipCondition>를 사용 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="fe6a7-133">Standard CAS policy does not rely on the <xref:System.Security.Policy.PublisherMembershipCondition>.</span></span> <span data-ttu-id="fe6a7-134">응용 프로그램이 사용자 지정 CAS 정책을 사용 하는 컴퓨터에서 실행 되지 않거나 부분 신뢰 환경에서 <xref:System.Security.Permissions.PublisherIdentityPermission>에 대 한 요구를 충족 하는 경우에만 게시자 서명을 확인 하는 데 관련 된 불필요 한 시작 비용을 피해 야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fe6a7-134">You should avoid the unnecessary startup cost associated with verifying the publisher signature unless your application executes on a computer with custom CAS policy, or is intending to satisfy demands for <xref:System.Security.Permissions.PublisherIdentityPermission> in a partial-trust environment.</span></span> <span data-ttu-id="fe6a7-135">(Id 권한 요구는 항상 완전 신뢰 환경에서 성공 합니다.)</span><span class="sxs-lookup"><span data-stu-id="fe6a7-135">(Demands for identity permissions always succeed in a full-trust environment.)</span></span>  
  
> [!NOTE]
> <span data-ttu-id="fe6a7-136">서비스에서 `<generatePublisherEvidence>` 요소를 사용 하 여 시작 성능을 향상 시키는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="fe6a7-136">We recommend that services use the `<generatePublisherEvidence>` element to improve startup performance.</span></span>  <span data-ttu-id="fe6a7-137">이 요소를 사용 하면 시간 초과 및 서비스 시작 취소가 발생할 수 있는 지연을 방지할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fe6a7-137">Using this element can also help avoid delays that can cause a time-out and the cancellation of the service startup.</span></span>  
  
## <a name="configuration-file"></a><span data-ttu-id="fe6a7-138">구성 파일</span><span class="sxs-lookup"><span data-stu-id="fe6a7-138">Configuration File</span></span>  
 <span data-ttu-id="fe6a7-139">이 요소는 응용 프로그램 구성 파일에만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fe6a7-139">This element can be used only in the application configuration file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="fe6a7-140">예제</span><span class="sxs-lookup"><span data-stu-id="fe6a7-140">Example</span></span>  
 <span data-ttu-id="fe6a7-141">다음 예제에서는 `<generatePublisherEvidence>` 요소를 사용 하 여 응용 프로그램에 대 한 CAS 게시자 정책 검사를 사용 하지 않도록 설정 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="fe6a7-141">The following example shows how to use the `<generatePublisherEvidence>` element to disable checking for CAS publisher policy for an application.</span></span>  
  
```xml  
<configuration>  
    <runtime>  
        <generatePublisherEvidence enabled="false"/>  
    </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="fe6a7-142">참조</span><span class="sxs-lookup"><span data-stu-id="fe6a7-142">See also</span></span>

- [<span data-ttu-id="fe6a7-143">런타임 설정 스키마</span><span class="sxs-lookup"><span data-stu-id="fe6a7-143">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="fe6a7-144">구성 파일 스키마</span><span class="sxs-lookup"><span data-stu-id="fe6a7-144">Configuration File Schema</span></span>](../index.md)
