---
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
ms.openlocfilehash: 89fa8a991cc7d0352eb0a13cdfd3a6063ea468e7
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73115853"
---
# <a name="publisherpolicy-element"></a><span data-ttu-id="3cd48-102">\<Y apply > 요소</span><span class="sxs-lookup"><span data-stu-id="3cd48-102">\<publisherPolicy> Element</span></span>
<span data-ttu-id="3cd48-103">런타임이 게시자 정책을 적용할지를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="3cd48-103">Specifies whether the runtime applies publisher policy.</span></span>  
  
<span data-ttu-id="3cd48-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="3cd48-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="3cd48-105">&nbsp; &nbsp;[ **\<runtime >** ](runtime-element.md) </span><span class="sxs-lookup"><span data-stu-id="3cd48-105">&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)</span></span>\
<span data-ttu-id="3cd48-106">&nbsp; &nbsp; &nbsp; &nbsp;[ **\<assemblyBinding >** ](assemblybinding-element-for-runtime.md) </span><span class="sxs-lookup"><span data-stu-id="3cd48-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<assemblyBinding>**](assemblybinding-element-for-runtime.md)</span></span>\
<span data-ttu-id="3cd48-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<dependentAssembly >** ](dependentassembly-element.md)</span><span class="sxs-lookup"><span data-stu-id="3cd48-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<dependentAssembly>**](dependentassembly-element.md)</span></span>\
<span data-ttu-id="3cd48-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<y apply >**</span><span class="sxs-lookup"><span data-stu-id="3cd48-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<publisherPolicy>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3cd48-109">구문</span><span class="sxs-lookup"><span data-stu-id="3cd48-109">Syntax</span></span>  
  
```xml  
<publisherPolicy apply="yes|no"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="3cd48-110">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="3cd48-110">Attributes and Elements</span></span>  
 <span data-ttu-id="3cd48-111">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="3cd48-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="3cd48-112">특성</span><span class="sxs-lookup"><span data-stu-id="3cd48-112">Attributes</span></span>  
  
|<span data-ttu-id="3cd48-113">특성</span><span class="sxs-lookup"><span data-stu-id="3cd48-113">Attribute</span></span>|<span data-ttu-id="3cd48-114">설명</span><span class="sxs-lookup"><span data-stu-id="3cd48-114">Description</span></span>|  
|---------------|-----------------|  
|`apply`|<span data-ttu-id="3cd48-115">게시자 정책을 적용할지 여부를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="3cd48-115">Specifies whether to apply publisher policy.</span></span>|  
  
## <a name="apply-attribute"></a><span data-ttu-id="3cd48-116">특성 적용</span><span class="sxs-lookup"><span data-stu-id="3cd48-116">apply Attribute</span></span>  
  
|<span data-ttu-id="3cd48-117">값</span><span class="sxs-lookup"><span data-stu-id="3cd48-117">Value</span></span>|<span data-ttu-id="3cd48-118">설명</span><span class="sxs-lookup"><span data-stu-id="3cd48-118">Description</span></span>|  
|-----------|-----------------|  
|`yes`|<span data-ttu-id="3cd48-119">게시자 정책을 적용 합니다.</span><span class="sxs-lookup"><span data-stu-id="3cd48-119">Applies publisher policy.</span></span> <span data-ttu-id="3cd48-120">이것이 기본 설정입니다.</span><span class="sxs-lookup"><span data-stu-id="3cd48-120">This is the default setting.</span></span>|  
|`no`|<span data-ttu-id="3cd48-121">게시자 정책을 적용 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="3cd48-121">Does not apply publisher policy.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="3cd48-122">자식 요소</span><span class="sxs-lookup"><span data-stu-id="3cd48-122">Child Elements</span></span>  

<span data-ttu-id="3cd48-123">없음.</span><span class="sxs-lookup"><span data-stu-id="3cd48-123">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="3cd48-124">부모 요소</span><span class="sxs-lookup"><span data-stu-id="3cd48-124">Parent Elements</span></span>  
  
|<span data-ttu-id="3cd48-125">요소</span><span class="sxs-lookup"><span data-stu-id="3cd48-125">Element</span></span>|<span data-ttu-id="3cd48-126">설명</span><span class="sxs-lookup"><span data-stu-id="3cd48-126">Description</span></span>|  
|-------------|-----------------|  
|`assemblyBinding`|<span data-ttu-id="3cd48-127">어셈블리 버전 리디렉션 및 어셈블리 위치에 대한 정보를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="3cd48-127">Contains information about assembly version redirection and the locations of assemblies.</span></span>|  
|`configuration`|<span data-ttu-id="3cd48-128">공용 언어 런타임 및 .NET Framework 애플리케이션에서 사용하는 모든 구성 파일의 루트 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="3cd48-128">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`dependentAssembly`|<span data-ttu-id="3cd48-129">각 어셈블리에 대한 바인딩 정책 및 어셈블리 위치를 캡슐화합니다.</span><span class="sxs-lookup"><span data-stu-id="3cd48-129">Encapsulates binding policy and assembly location for each assembly.</span></span> <span data-ttu-id="3cd48-130">각 어셈블리에 대해 하나의 `<dependentAssembly>` 요소를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="3cd48-130">Use one `<dependentAssembly>` element for each assembly.</span></span>|  
|`runtime`|<span data-ttu-id="3cd48-131">어셈블리 바인딩 및 가비지 컬렉션에 대한 정보를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="3cd48-131">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3cd48-132">주의</span><span class="sxs-lookup"><span data-stu-id="3cd48-132">Remarks</span></span>  
 <span data-ttu-id="3cd48-133">구성 요소 공급 업체에서 새 버전의 어셈블리를 출시 하는 경우 이전 버전을 사용 하는 응용 프로그램이 이제 새 버전을 사용 하도록 공급 업체에 게시자 정책을 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3cd48-133">When a component vendor releases a new version of an assembly, the vendor can include a publisher policy so applications that use the old version now use the new version.</span></span> <span data-ttu-id="3cd48-134">특정 어셈블리에 대해 게시자 정책을 적용할지 여부를 지정 하려면 **\<dependentAssembly >** 요소에 **\<y apply >** 요소를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="3cd48-134">To specify whether to apply publisher policy for a particular assembly, put the **\<publisherPolicy>** element in the **\<dependentAssembly>** element.</span></span>  
  
 <span data-ttu-id="3cd48-135">**Apply** 특성의 기본 설정은 **예**입니다.</span><span class="sxs-lookup"><span data-stu-id="3cd48-135">The default setting for the **apply** attribute is **yes**.</span></span> <span data-ttu-id="3cd48-136">**Apply** 특성을 **no** 로 설정 하면 어셈블리의 모든 이전 **예** 설정이 무시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3cd48-136">Setting the **apply** attribute to **no** overrides any previous **yes** settings for an assembly.</span></span>  
  
 <span data-ttu-id="3cd48-137">응용 프로그램에서 응용 프로그램 구성 파일의 [\<y apply apply = "no"/>](publisherpolicy-element.md) 요소를 사용 하 여 게시자 정책을 명시적으로 무시 하려면 응용 프로그램에 대 한 권한이 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="3cd48-137">Permission is required for an application to explicitly ignore publisher policy using the [\<publisherPolicy apply="no"/>](publisherpolicy-element.md) element in the application configuration file.</span></span> <span data-ttu-id="3cd48-138"><xref:System.Security.Permissions.SecurityPermission>에서 <xref:System.Security.Permissions.SecurityPermissionFlag> 플래그를 설정 하 여 사용 권한을 부여 합니다.</span><span class="sxs-lookup"><span data-stu-id="3cd48-138">The permission is granted by setting the <xref:System.Security.Permissions.SecurityPermissionFlag> flag on the <xref:System.Security.Permissions.SecurityPermission>.</span></span> <span data-ttu-id="3cd48-139">자세한 내용은 [어셈블리 바인딩 리디렉션 보안 권한](../../assembly-binding-redirection-security-permission.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="3cd48-139">For more information, see [Assembly Binding Redirection Security Permission](../../assembly-binding-redirection-security-permission.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="3cd48-140">예제</span><span class="sxs-lookup"><span data-stu-id="3cd48-140">Example</span></span>  
 <span data-ttu-id="3cd48-141">다음 예에서는 어셈블리에 대 한 게시자 정책을 해제 `myAssembly`합니다.</span><span class="sxs-lookup"><span data-stu-id="3cd48-141">The following example turns off publisher policy for the assembly, `myAssembly`.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="3cd48-142">참조</span><span class="sxs-lookup"><span data-stu-id="3cd48-142">See also</span></span>

- [<span data-ttu-id="3cd48-143">런타임 설정 스키마</span><span class="sxs-lookup"><span data-stu-id="3cd48-143">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="3cd48-144">구성 파일 스키마</span><span class="sxs-lookup"><span data-stu-id="3cd48-144">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="3cd48-145">런타임에서 어셈블리를 찾는 방법</span><span class="sxs-lookup"><span data-stu-id="3cd48-145">How the Runtime Locates Assemblies</span></span>](../../../deployment/how-the-runtime-locates-assemblies.md)
- [<span data-ttu-id="3cd48-146">어셈블리 버전 리디렉션</span><span class="sxs-lookup"><span data-stu-id="3cd48-146">Redirecting Assembly Versions</span></span>](../../redirect-assembly-versions.md)
