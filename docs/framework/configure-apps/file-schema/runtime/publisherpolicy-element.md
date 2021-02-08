---
description: '다음에 대 한 자세한 정보: <publisherPolicy> 요소'
title: <publisherPolicy> 요소
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/runtime/assemblyBinding/publisherPolicy
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/runtime/assemblyBinding/dependentAssembly/publisherPolicy
- http://schemas.microsoft.com/.NetConfiguration/v2.0#publisherPolicy
helpviewer_keywords:
- publisherPolicy element
- container tags, <publisherPolicy> element
- <publisherPolicy> element
ms.assetid: 4613407e-d0a8-4ef2-9f81-a6acb9fdc7d4
ms.openlocfilehash: 35d729d5b195e010a80e7272312f14ac5802001b
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99802439"
---
# <a name="publisherpolicy-element"></a><span data-ttu-id="3a464-103">\<publisherPolicy> 요소</span><span class="sxs-lookup"><span data-stu-id="3a464-103">\<publisherPolicy> Element</span></span>

<span data-ttu-id="3a464-104">런타임이 게시자 정책을 적용할지를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="3a464-104">Specifies whether the runtime applies publisher policy.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<assemblyBinding>**](assemblybinding-element-for-runtime.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<dependentAssembly>**](dependentassembly-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<publisherPolicy>**  
  
## <a name="syntax"></a><span data-ttu-id="3a464-105">구문</span><span class="sxs-lookup"><span data-stu-id="3a464-105">Syntax</span></span>  
  
```xml  
<publisherPolicy apply="yes|no"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="3a464-106">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="3a464-106">Attributes and Elements</span></span>  

 <span data-ttu-id="3a464-107">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="3a464-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="3a464-108">특성</span><span class="sxs-lookup"><span data-stu-id="3a464-108">Attributes</span></span>  
  
|<span data-ttu-id="3a464-109">attribute</span><span class="sxs-lookup"><span data-stu-id="3a464-109">Attribute</span></span>|<span data-ttu-id="3a464-110">설명</span><span class="sxs-lookup"><span data-stu-id="3a464-110">Description</span></span>|  
|---------------|-----------------|  
|`apply`|<span data-ttu-id="3a464-111">게시자 정책을 적용할지 여부를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="3a464-111">Specifies whether to apply publisher policy.</span></span>|  
  
## <a name="apply-attribute"></a><span data-ttu-id="3a464-112">특성 적용</span><span class="sxs-lookup"><span data-stu-id="3a464-112">apply Attribute</span></span>  
  
|<span data-ttu-id="3a464-113">값</span><span class="sxs-lookup"><span data-stu-id="3a464-113">Value</span></span>|<span data-ttu-id="3a464-114">설명</span><span class="sxs-lookup"><span data-stu-id="3a464-114">Description</span></span>|  
|-----------|-----------------|  
|`yes`|<span data-ttu-id="3a464-115">게시자 정책을 적용 합니다.</span><span class="sxs-lookup"><span data-stu-id="3a464-115">Applies publisher policy.</span></span> <span data-ttu-id="3a464-116">이 값은 기본 설정입니다.</span><span class="sxs-lookup"><span data-stu-id="3a464-116">This is the default setting.</span></span>|  
|`no`|<span data-ttu-id="3a464-117">게시자 정책을 적용 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="3a464-117">Does not apply publisher policy.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="3a464-118">자식 요소</span><span class="sxs-lookup"><span data-stu-id="3a464-118">Child Elements</span></span>  

<span data-ttu-id="3a464-119">없음</span><span class="sxs-lookup"><span data-stu-id="3a464-119">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="3a464-120">부모 요소</span><span class="sxs-lookup"><span data-stu-id="3a464-120">Parent Elements</span></span>  
  
|<span data-ttu-id="3a464-121">요소</span><span class="sxs-lookup"><span data-stu-id="3a464-121">Element</span></span>|<span data-ttu-id="3a464-122">설명</span><span class="sxs-lookup"><span data-stu-id="3a464-122">Description</span></span>|  
|-------------|-----------------|  
|`assemblyBinding`|<span data-ttu-id="3a464-123">어셈블리 버전 리디렉션 및 어셈블리 위치에 대한 정보를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="3a464-123">Contains information about assembly version redirection and the locations of assemblies.</span></span>|  
|`configuration`|<span data-ttu-id="3a464-124">공용 언어 런타임 및 .NET Framework 애플리케이션에서 사용하는 모든 구성 파일의 루트 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="3a464-124">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`dependentAssembly`|<span data-ttu-id="3a464-125">각 어셈블리에 대한 바인딩 정책 및 어셈블리 위치를 캡슐화합니다.</span><span class="sxs-lookup"><span data-stu-id="3a464-125">Encapsulates binding policy and assembly location for each assembly.</span></span> <span data-ttu-id="3a464-126">`<dependentAssembly>`각 어셈블리에 대해 하나의 요소를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="3a464-126">Use one `<dependentAssembly>` element for each assembly.</span></span>|  
|`runtime`|<span data-ttu-id="3a464-127">어셈블리 바인딩 및 가비지 컬렉션에 대한 정보를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="3a464-127">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3a464-128">설명</span><span class="sxs-lookup"><span data-stu-id="3a464-128">Remarks</span></span>  

 <span data-ttu-id="3a464-129">구성 요소 공급 업체에서 새 버전의 어셈블리를 출시 하는 경우 이전 버전을 사용 하는 응용 프로그램이 이제 새 버전을 사용 하도록 공급 업체에 게시자 정책을 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3a464-129">When a component vendor releases a new version of an assembly, the vendor can include a publisher policy so applications that use the old version now use the new version.</span></span> <span data-ttu-id="3a464-130">특정 어셈블리에 대해 게시자 정책을 적용할지 여부를 지정 하려면 요소를 **\<publisherPolicy>** 요소에 배치 **\<dependentAssembly>** 합니다.</span><span class="sxs-lookup"><span data-stu-id="3a464-130">To specify whether to apply publisher policy for a particular assembly, put the **\<publisherPolicy>** element in the **\<dependentAssembly>** element.</span></span>  
  
 <span data-ttu-id="3a464-131">**Apply** 특성의 기본 설정은 **예** 입니다.</span><span class="sxs-lookup"><span data-stu-id="3a464-131">The default setting for the **apply** attribute is **yes**.</span></span> <span data-ttu-id="3a464-132">**Apply** 특성을 **no** 로 설정 하면 어셈블리의 모든 이전 **예** 설정이 무시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3a464-132">Setting the **apply** attribute to **no** overrides any previous **yes** settings for an assembly.</span></span>  
  
 <span data-ttu-id="3a464-133">응용 프로그램 구성 파일의 요소를 사용 하 여 응용 프로그램에서 게시자 정책을 명시적으로 무시 하려면 권한이 필요 [\<publisherPolicy apply="no"/>](publisherpolicy-element.md) 합니다.</span><span class="sxs-lookup"><span data-stu-id="3a464-133">Permission is required for an application to explicitly ignore publisher policy using the [\<publisherPolicy apply="no"/>](publisherpolicy-element.md) element in the application configuration file.</span></span> <span data-ttu-id="3a464-134">에 플래그를 설정 하 여 사용 권한을 부여 합니다 <xref:System.Security.Permissions.SecurityPermissionFlag> <xref:System.Security.Permissions.SecurityPermission> .</span><span class="sxs-lookup"><span data-stu-id="3a464-134">The permission is granted by setting the <xref:System.Security.Permissions.SecurityPermissionFlag> flag on the <xref:System.Security.Permissions.SecurityPermission>.</span></span> <span data-ttu-id="3a464-135">자세한 내용은 [어셈블리 바인딩 리디렉션 보안 권한](../../assembly-binding-redirection-security-permission.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="3a464-135">For more information, see [Assembly Binding Redirection Security Permission](../../assembly-binding-redirection-security-permission.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="3a464-136">예제</span><span class="sxs-lookup"><span data-stu-id="3a464-136">Example</span></span>  

 <span data-ttu-id="3a464-137">다음 예에서는 어셈블리에 대 한 게시자 정책을 해제 `myAssembly` 합니다.</span><span class="sxs-lookup"><span data-stu-id="3a464-137">The following example turns off publisher policy for the assembly, `myAssembly`.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1">  
         <dependentAssembly>  
            <assemblyIdentity name="myAssembly"  
                                    publicKeyToken="32ab4ba45e0a69a1"  
                                    culture="neutral" />  
            <publisherPolicy apply="no"/>  
         </dependentAssembly>  
      </assemblyBinding>  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="3a464-138">참고 항목</span><span class="sxs-lookup"><span data-stu-id="3a464-138">See also</span></span>

- [<span data-ttu-id="3a464-139">런타임 설정 스키마</span><span class="sxs-lookup"><span data-stu-id="3a464-139">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="3a464-140">구성 파일 스키마</span><span class="sxs-lookup"><span data-stu-id="3a464-140">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="3a464-141">런타임에서 어셈블리를 찾는 방법</span><span class="sxs-lookup"><span data-stu-id="3a464-141">How the Runtime Locates Assemblies</span></span>](../../../deployment/how-the-runtime-locates-assemblies.md)
- [<span data-ttu-id="3a464-142">어셈블리 버전 리디렉션</span><span class="sxs-lookup"><span data-stu-id="3a464-142">Redirecting Assembly Versions</span></span>](../../redirect-assembly-versions.md)
