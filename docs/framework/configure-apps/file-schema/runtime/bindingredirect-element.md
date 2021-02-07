---
description: '다음에 대 한 자세한 정보: <bindingRedirect> 요소'
title: <bindingRedirect> 요소
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/runtime/assemblyBinding/dependentAssembly/bindingRedirect
- http://schemas.microsoft.com/.NetConfiguration/v2.0#bindingRedirect
helpviewer_keywords:
- <bindingRedirect> element
- container tags, <bindingRedirect> element
- bindingRedirect element
ms.assetid: 67784ecd-9663-434e-bd6a-26975e447ac0
ms.openlocfilehash: 833ee73fa11d179ac855f3ac4d2bca8d7a2226ac
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99719177"
---
# <a name="bindingredirect-element"></a><span data-ttu-id="658d3-103">\<bindingRedirect> 요소</span><span class="sxs-lookup"><span data-stu-id="658d3-103">\<bindingRedirect> Element</span></span>

<span data-ttu-id="658d3-104">어셈블리 버전을 다른 버전으로 리디렉션합니다.</span><span class="sxs-lookup"><span data-stu-id="658d3-104">Redirects one assembly version to another.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<assemblyBinding>**](assemblybinding-element-for-runtime.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<dependentAssembly>**](dependentassembly-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<bindingRedirect>**  
  
## <a name="syntax"></a><span data-ttu-id="658d3-105">구문</span><span class="sxs-lookup"><span data-stu-id="658d3-105">Syntax</span></span>  
  
```xml  
   <bindingRedirect
oldVersion="existing assembly version"  
newVersion="new assembly version"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="658d3-106">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="658d3-106">Attributes and Elements</span></span>  

 <span data-ttu-id="658d3-107">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="658d3-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="658d3-108">특성</span><span class="sxs-lookup"><span data-stu-id="658d3-108">Attributes</span></span>  
  
|<span data-ttu-id="658d3-109">attribute</span><span class="sxs-lookup"><span data-stu-id="658d3-109">Attribute</span></span>|<span data-ttu-id="658d3-110">설명</span><span class="sxs-lookup"><span data-stu-id="658d3-110">Description</span></span>|  
|---------------|-----------------|  
|`oldVersion`|<span data-ttu-id="658d3-111">필수 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="658d3-111">Required attribute.</span></span><br /><br /> <span data-ttu-id="658d3-112">원래 요청된 어셈블리 버전을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="658d3-112">Specifies the version of the assembly that was originally requested.</span></span> <span data-ttu-id="658d3-113">어셈블리 버전 번호의 형식은 주 버전. *부 버전. 빌드. 수정 버전* 입니다.</span><span class="sxs-lookup"><span data-stu-id="658d3-113">The format of an assembly version number is *major.minor.build.revision*.</span></span> <span data-ttu-id="658d3-114">이 버전 번호의 각 부분에 사용할 수 있는 값은 0부터 65535까지입니다.</span><span class="sxs-lookup"><span data-stu-id="658d3-114">Valid values for each part of this version number are 0 to 65535.</span></span><br /><br /> <span data-ttu-id="658d3-115">다음 형식으로 다양한 버전을 지정할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="658d3-115">You can also specify a range of versions in the following format:</span></span><br /><br /> <span data-ttu-id="658d3-116">*n.n.n.n. n. n. n. n. n. n. n*</span><span class="sxs-lookup"><span data-stu-id="658d3-116">*n.n.n.n - n.n.n.n*</span></span>|  
|`newVersion`|<span data-ttu-id="658d3-117">필수 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="658d3-117">Required attribute.</span></span><br /><br /> <span data-ttu-id="658d3-118">원래 요청 된 버전 대신 다음 형식으로 사용할 어셈블리의 버전을 지정 *합니다. n* . n. n</span><span class="sxs-lookup"><span data-stu-id="658d3-118">Specifies the version of the assembly to use instead of the originally requested version in the format: *n.n.n.n*</span></span><br /><br /> <span data-ttu-id="658d3-119">이 값은 `oldVersion`보다 이전 버전을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="658d3-119">This value can specify an earlier version than `oldVersion`.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="658d3-120">자식 요소</span><span class="sxs-lookup"><span data-stu-id="658d3-120">Child Elements</span></span>  
  
|<span data-ttu-id="658d3-121">요소</span><span class="sxs-lookup"><span data-stu-id="658d3-121">Element</span></span>|<span data-ttu-id="658d3-122">설명</span><span class="sxs-lookup"><span data-stu-id="658d3-122">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="658d3-123">없음</span><span class="sxs-lookup"><span data-stu-id="658d3-123">None</span></span>||  
  
### <a name="parent-elements"></a><span data-ttu-id="658d3-124">부모 요소</span><span class="sxs-lookup"><span data-stu-id="658d3-124">Parent Elements</span></span>  
  
|<span data-ttu-id="658d3-125">요소</span><span class="sxs-lookup"><span data-stu-id="658d3-125">Element</span></span>|<span data-ttu-id="658d3-126">설명</span><span class="sxs-lookup"><span data-stu-id="658d3-126">Description</span></span>|  
|-------------|-----------------|  
|`assemblyBinding`|<span data-ttu-id="658d3-127">어셈블리 버전 리디렉션 및 어셈블리 위치에 대한 정보를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="658d3-127">Contains information about assembly version redirection and the locations of assemblies.</span></span>|  
|`configuration`|<span data-ttu-id="658d3-128">공용 언어 런타임 및 .NET Framework 애플리케이션에서 사용하는 모든 구성 파일의 루트 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="658d3-128">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`dependentAssembly`|<span data-ttu-id="658d3-129">각 어셈블리에 대한 바인딩 정책 및 어셈블리 위치를 캡슐화합니다.</span><span class="sxs-lookup"><span data-stu-id="658d3-129">Encapsulates binding policy and assembly location for each assembly.</span></span> <span data-ttu-id="658d3-130">각 어셈블리에 dependentAssembly 요소를 하나만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="658d3-130">Use one dependentAssembly element for each assembly.</span></span>|  
|`runtime`|<span data-ttu-id="658d3-131">어셈블리 바인딩 및 가비지 컬렉션에 대한 정보를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="658d3-131">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="658d3-132">설명</span><span class="sxs-lookup"><span data-stu-id="658d3-132">Remarks</span></span>  

 <span data-ttu-id="658d3-133">강력한 이름의 어셈블리에 대해 .NET Framework 애플리케이션을 빌드하면, 애플리케이션은 새 버전이 있는 경우에도 런타임에 기본적으로 어셈블리의 원래 버전을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="658d3-133">When you build a .NET Framework application against a strong-named assembly, the application uses that version of the assembly at run time by default, even if a new version is available.</span></span> <span data-ttu-id="658d3-134">그러나 어셈블리의 새 버전을 사용하도록 애플리케이션을 구성할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="658d3-134">However, you can configure the application to run against a newer version of the assembly.</span></span> <span data-ttu-id="658d3-135">런타임에서 이러한 파일을 사용 하 여 사용할 어셈블리 버전을 확인 하는 방법에 대 한 자세한 내용은 [런타임에서 어셈블리를 찾는 방법](../../../deployment/how-the-runtime-locates-assemblies.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="658d3-135">For details on how the runtime uses these files to determine which assembly version to use, see [How the Runtime Locates Assemblies](../../../deployment/how-the-runtime-locates-assemblies.md).</span></span>  
  
 <span data-ttu-id="658d3-136">`bindingRedirect` 요소에 여러 개의 `dependentAssembly` 요소를 사용하면 둘 이상의 어셈블리 버전을 리디렉션할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="658d3-136">You can redirect more than one assembly version by including multiple `bindingRedirect` elements in a `dependentAssembly` element.</span></span> <span data-ttu-id="658d3-137">어셈블리의 새 버전에서 이전 버전으로 리디렉션할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="658d3-137">You can also redirect from a newer version to an older version of the assembly.</span></span>  
  
 <span data-ttu-id="658d3-138">애플리케이션 구성 파일에서 어셈블리 바인딩을 명시적으로 리디렉션하려면 보안 권한이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="658d3-138">Explicit assembly binding redirection in an application configuration file requires a security permission.</span></span> <span data-ttu-id="658d3-139">이는 .NET Framework 어셈블리와 타사 어셈블리의 리디렉션 모두에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="658d3-139">This applies to redirection of .NET Framework assemblies and assemblies from third parties.</span></span> <span data-ttu-id="658d3-140">에 플래그를 설정 하 여 사용 권한을 부여 합니다 <xref:System.Security.Permissions.SecurityPermissionFlag> <xref:System.Security.Permissions.SecurityPermission> .</span><span class="sxs-lookup"><span data-stu-id="658d3-140">The permission is granted by setting the <xref:System.Security.Permissions.SecurityPermissionFlag> flag on the <xref:System.Security.Permissions.SecurityPermission>.</span></span> <span data-ttu-id="658d3-141">자세한 내용은 [어셈블리 바인딩 리디렉션 보안 권한](../../assembly-binding-redirection-security-permission.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="658d3-141">For more information, see [Assembly Binding Redirection Security Permission](../../assembly-binding-redirection-security-permission.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="658d3-142">예제</span><span class="sxs-lookup"><span data-stu-id="658d3-142">Example</span></span>  

 <span data-ttu-id="658d3-143">다음 예제에서는 어셈블리 버전을 다른 버전으로 리디렉션하는 방법을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="658d3-143">The following example shows how to redirect one assembly version to another.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1">  
         <dependentAssembly>  
            <assemblyIdentity name="myAssembly"  
                              publicKeyToken="32ab4ba45e0a69a1"  
                              culture="neutral" />  
            <bindingRedirect oldVersion="1.0.0.0"  
                             newVersion="2.0.0.0"/>  
         </dependentAssembly>  
      </assemblyBinding>  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="658d3-144">참고 항목</span><span class="sxs-lookup"><span data-stu-id="658d3-144">See also</span></span>

- [<span data-ttu-id="658d3-145">런타임 설정 스키마</span><span class="sxs-lookup"><span data-stu-id="658d3-145">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="658d3-146">구성 파일 스키마</span><span class="sxs-lookup"><span data-stu-id="658d3-146">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="658d3-147">어셈블리 버전 리디렉션</span><span class="sxs-lookup"><span data-stu-id="658d3-147">Redirecting Assembly Versions</span></span>](../../redirect-assembly-versions.md)
