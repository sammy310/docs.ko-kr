---
title: <loadFromRemoteSources> 요소
ms.date: 05/24/2018
helpviewer_keywords:
- loadFromRemoteSources element
- <loadFromRemoteSources> element
ms.assetid: 006d1280-2ac3-4db6-a984-a3d4e275046a
ms.openlocfilehash: a0dcffe378cdd09de0fbd8f0a6ef0635c033fd9c
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/06/2020
ms.locfileid: "79154064"
---
# <a name="loadfromremotesources-element"></a><span data-ttu-id="4783b-102">\<loadFromRemoteSources> 요소</span><span class="sxs-lookup"><span data-stu-id="4783b-102">\<loadFromRemoteSources> element</span></span>
<span data-ttu-id="4783b-103">원격 소스에서 로드 된 어셈블리에 .NET Framework 4 이상에서 완전 신뢰를 부여 해야 하는지 여부를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="4783b-103">Specifies whether assemblies loaded from remote sources should be granted full trust in .NET Framework 4 and later.</span></span>
  
> [!NOTE]
> <span data-ttu-id="4783b-104">Visual Studio 프로젝트 오류 목록 또는 빌드 오류의 오류 메시지 때문에이 문서를 전달 하 [는 경우 방법: Visual studio에서 웹의 어셈블리 사용](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/ee890038(v=vs.100))을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="4783b-104">If you were directed to this article because of an error message in the Visual Studio project error list or a build error, see [How to: Use an Assembly from the Web in Visual Studio](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/ee890038(v=vs.100)).</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<loadFromRemoteSources>**  
  
## <a name="syntax"></a><span data-ttu-id="4783b-105">구문</span><span class="sxs-lookup"><span data-stu-id="4783b-105">Syntax</span></span>  
  
```xml  
<loadFromRemoteSources
   enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="4783b-106">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="4783b-106">Attributes and elements</span></span>
 <span data-ttu-id="4783b-107">다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="4783b-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="4783b-108">특성</span><span class="sxs-lookup"><span data-stu-id="4783b-108">Attributes</span></span>  
  
|<span data-ttu-id="4783b-109">attribute</span><span class="sxs-lookup"><span data-stu-id="4783b-109">Attribute</span></span>|<span data-ttu-id="4783b-110">Description</span><span class="sxs-lookup"><span data-stu-id="4783b-110">Description</span></span>|  
|---------------|-----------------|  
|`enabled`|<span data-ttu-id="4783b-111">필수 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="4783b-111">Required attribute.</span></span><br /><br /> <span data-ttu-id="4783b-112">원격 소스에서 로드 된 어셈블리에 완전 신뢰 권한을 부여 해야 하는지 여부를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="4783b-112">Specifies whether an assembly that is loaded from a remote source should be granted full trust.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="4783b-113">enabled 특성</span><span class="sxs-lookup"><span data-stu-id="4783b-113">enabled attribute</span></span>  
  
|<span data-ttu-id="4783b-114">값</span><span class="sxs-lookup"><span data-stu-id="4783b-114">Value</span></span>|<span data-ttu-id="4783b-115">Description</span><span class="sxs-lookup"><span data-stu-id="4783b-115">Description</span></span>|  
|-----------|-----------------|  
|`false`|<span data-ttu-id="4783b-116">원격 원본에서 응용 프로그램에 완전 신뢰를 부여 하지 마십시오.</span><span class="sxs-lookup"><span data-stu-id="4783b-116">Do not grant full trust to applications from remote sources.</span></span> <span data-ttu-id="4783b-117">기본값입니다.</span><span class="sxs-lookup"><span data-stu-id="4783b-117">This is the default.</span></span>|  
|`true`|<span data-ttu-id="4783b-118">원격 원본에서 응용 프로그램에 완전 신뢰를 부여 합니다.</span><span class="sxs-lookup"><span data-stu-id="4783b-118">Grant full trust to applications from remote sources.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="4783b-119">자식 요소</span><span class="sxs-lookup"><span data-stu-id="4783b-119">Child elements</span></span>  
 <span data-ttu-id="4783b-120">없음</span><span class="sxs-lookup"><span data-stu-id="4783b-120">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="4783b-121">부모 요소</span><span class="sxs-lookup"><span data-stu-id="4783b-121">Parent elements</span></span>  
  
|<span data-ttu-id="4783b-122">요소</span><span class="sxs-lookup"><span data-stu-id="4783b-122">Element</span></span>|<span data-ttu-id="4783b-123">Description</span><span class="sxs-lookup"><span data-stu-id="4783b-123">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="4783b-124">공용 언어 런타임 및 .NET Framework 애플리케이션에서 사용하는 모든 구성 파일의 루트 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="4783b-124">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="4783b-125">런타임 초기화 옵션에 대한 정보를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="4783b-125">Contains information about runtime initialization options.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4783b-126">설명</span><span class="sxs-lookup"><span data-stu-id="4783b-126">Remarks</span></span>

<span data-ttu-id="4783b-127">.NET Framework 3.5 이전 버전에서 원격 위치에서 어셈블리를 로드 하는 경우 어셈블리의 코드는 로드 되는 영역에 따라 권한 부여 집합을 사용 하 여 부분 신뢰로 실행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4783b-127">In the .NET Framework 3.5 and earlier versions, if you load an assembly from a remote location, code in the assembly runs in partial trust with a grant set that depends on the zone from which it is loaded.</span></span> <span data-ttu-id="4783b-128">예를 들어 웹 사이트에서 어셈블리를 로드 하는 경우 인터넷 영역에 로드 되 고 인터넷 권한 집합이 부여 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4783b-128">For example, if you load an assembly from a website, it is loaded into the Internet zone and granted the Internet permission set.</span></span> <span data-ttu-id="4783b-129">즉, 인터넷 샌드박스에서 실행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4783b-129">In other words, it executes in an Internet sandbox.</span></span>

<span data-ttu-id="4783b-130">.NET Framework 4부터 CAS (코드 액세스 보안) 정책이 사용 하지 않도록 설정 되 고 어셈블리가 완전 신뢰로 로드 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4783b-130">Starting with the .NET Framework 4, code access security (CAS) policy is disabled and assemblies are loaded in full trust.</span></span> <span data-ttu-id="4783b-131">일반적으로이는 이전에 샌드 박싱 된 메서드로 로드 된 어셈블리에 완전 신뢰를 부여 <xref:System.Reflection.Assembly.LoadFrom%2A?displayProperty=nameWithType> 합니다.</span><span class="sxs-lookup"><span data-stu-id="4783b-131">Ordinarily, this would grant full trust to assemblies loaded with the <xref:System.Reflection.Assembly.LoadFrom%2A?displayProperty=nameWithType> method that previously had been sandboxed.</span></span> <span data-ttu-id="4783b-132">이를 방지 하기 위해 원격 소스에서 로드 된 어셈블리에서 코드를 실행 하는 기능은 기본적으로 비활성화 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4783b-132">To prevent this, the ability to run code in assemblies loaded from a remote source is disabled by default.</span></span> <span data-ttu-id="4783b-133">기본적으로 원격 어셈블리를 로드 하려고 하면 <xref:System.IO.FileLoadException> 다음과 같은 예외 메시지가 포함 된이 throw 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4783b-133">By default, if you attempt to load a remote assembly, a <xref:System.IO.FileLoadException> with an exception message like the following is thrown:</span></span>

```text
System.IO.FileNotFoundException: Could not load file or assembly 'file:assem.dll' or one of its dependencies. Operation is not supported.
(Exception from HRESULT: 0x80131515)
File name: 'file:assem.dll' --->
System.NotSupportedException: An attempt was made to load an assembly from a network location which would have caused the assembly
to be sandboxed in previous versions of the .NET Framework. This release of the .NET Framework does not enable CAS policy by default,
so this load may be dangerous. If this load is not intended to sandbox the assembly, please enable the loadFromRemoteSources switch.
```

<span data-ttu-id="4783b-134">어셈블리를 로드 하 고 해당 코드를 실행 하려면 다음 중 하나를 수행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4783b-134">To load the assembly and execute its code, you must either:</span></span>

- <span data-ttu-id="4783b-135">어셈블리에 대 한 샌드박스를 명시적으로 만듭니다. [방법: 샌드박스에서 부분적으로 신뢰할 수 있는 코드 실행](../../../misc/how-to-run-partially-trusted-code-in-a-sandbox.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="4783b-135">Explicitly create a sandbox for the assembly (see [How to: Run Partially Trusted Code in a Sandbox](../../../misc/how-to-run-partially-trusted-code-in-a-sandbox.md)).</span></span>

- <span data-ttu-id="4783b-136">완전 신뢰에서 어셈블리의 코드를 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="4783b-136">Run the assembly's code in full trust.</span></span> <span data-ttu-id="4783b-137">요소를 구성 하 여이 작업을 수행 `<loadFromRemoteSources>` 합니다.</span><span class="sxs-lookup"><span data-stu-id="4783b-137">You do this by configuring the `<loadFromRemoteSources>` element.</span></span> <span data-ttu-id="4783b-138">이를 통해 이전 버전의 .NET Framework에서 부분 신뢰로 실행 되는 어셈블리가 이제 .NET Framework 4 이상 버전에서 완전 신뢰로 실행 되도록 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4783b-138">It lets you specify that the assemblies that run in partial trust in earlier versions of the .NET Framework now run in full trust in the .NET Framework 4 and later versions.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="4783b-139">어셈블리가 완전 신뢰로 실행 되지 않아야 하는 경우이 구성 요소를 설정 하지 마십시오.</span><span class="sxs-lookup"><span data-stu-id="4783b-139">If the assembly should not run in full trust, do not set this configuration element.</span></span> <span data-ttu-id="4783b-140">대신 어셈블리를 로드할 샌드박스가 적용 된을 만듭니다 <xref:System.AppDomain> .</span><span class="sxs-lookup"><span data-stu-id="4783b-140">Instead, create a sandboxed <xref:System.AppDomain> in which to load the assembly.</span></span>

<span data-ttu-id="4783b-141">`enabled`요소에 대 한 특성은 `<loadFromRemoteSources>` CAS (코드 액세스 보안)를 사용 하지 않도록 설정한 경우에만 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4783b-141">The `enabled` attribute for the `<loadFromRemoteSources>` element is effective only when code access security (CAS) is disabled.</span></span> <span data-ttu-id="4783b-142">기본적으로 CAS 정책은 .NET Framework 4 이상 버전에서 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="4783b-142">By default, CAS policy is disabled in the .NET Framework 4 and later versions.</span></span> <span data-ttu-id="4783b-143">`enabled`를로 설정 하면 `true` 원격 어셈블리에 완전 신뢰가 부여 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4783b-143">If you set `enabled` to `true`, remote assemblies are granted full trust.</span></span>

<span data-ttu-id="4783b-144">`enabled`가로 설정 되지 않은 경우 `true` <xref:System.IO.FileLoadException> 다음 조건 중 하나에서이 throw 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4783b-144">If `enabled` is not set to `true`, a <xref:System.IO.FileLoadException> is thrown under the either of the following conditions:</span></span>

- <span data-ttu-id="4783b-145">현재 도메인의 샌드 박싱 동작은 .NET Framework 3.5의 동작과 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="4783b-145">The sandboxing behavior of the current domain is different from its behavior in the .NET Framework 3.5.</span></span> <span data-ttu-id="4783b-146">이렇게 하려면 CAS 정책을 사용 하지 않도록 설정 해야 하 고 현재 도메인을 샌드 박싱 하지 않아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4783b-146">This requires CAS policy to be disabled, and the current domain not to be sandboxed.</span></span>

- <span data-ttu-id="4783b-147">로드 되는 어셈블리가 영역에 속하지 않습니다 `MyComputer` .</span><span class="sxs-lookup"><span data-stu-id="4783b-147">The assembly being loaded is not from the `MyComputer` zone.</span></span>

<span data-ttu-id="4783b-148">요소를 `<loadFromRemoteSources>` 로 설정 `true` 하면이 예외가 throw 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="4783b-148">Setting the `<loadFromRemoteSources>` element to `true` prevents this exception from being thrown.</span></span> <span data-ttu-id="4783b-149">이를 통해 보안을 위해 로드 된 어셈블리를 sandbox 하는 데 공용 언어 런타임에 의존 하지 않도록 지정 하 고 완전 신뢰로 실행 되도록 허용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4783b-149">It enables you to specify that you are not relying on the common language runtime to sandbox the loaded assemblies for security, and that they can be allowed to execute in full trust.</span></span>

## <a name="notes"></a><span data-ttu-id="4783b-150">메모</span><span class="sxs-lookup"><span data-stu-id="4783b-150">Notes</span></span>

- <span data-ttu-id="4783b-151">.NET Framework 4.5 이상 버전에서 로컬 네트워크 공유의 어셈블리는 기본적으로 완전 신뢰로 실행 됩니다. 요소를 사용 하도록 설정할 필요는 없습니다 `<loadFromRemoteSources>` .</span><span class="sxs-lookup"><span data-stu-id="4783b-151">In the .NET Framework 4.5 and later versions, assemblies on local network shares run in full trust by default; you do not have to enable the `<loadFromRemoteSources>` element.</span></span>

- <span data-ttu-id="4783b-152">애플리케이션을 웹에서 복사한 경우, Windows에서는 해당 프로그램이 로컬 컴퓨터에 있더라도 웹 애플리케이션이라는 플래그가 지정됩니다.</span><span class="sxs-lookup"><span data-stu-id="4783b-152">If an application has been copied from the web, it is flagged by Windows as being a web application, even if it resides on the local computer.</span></span> <span data-ttu-id="4783b-153">해당 파일 속성을 변경 하 여 해당 지정을 변경 하거나, 요소를 사용 `<loadFromRemoteSources>` 하 여 어셈블리에 완전 신뢰를 부여할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4783b-153">You can change that designation by changing its file properties, or you can use the `<loadFromRemoteSources>` element to grant the assembly full trust.</span></span> <span data-ttu-id="4783b-154">또는 <xref:System.Reflection.Assembly.UnsafeLoadFrom%2A> 메서드를 사용하여 운영 체제가 웹에서 로드되었음을 표시하는 로컬 어셈블리를 로드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4783b-154">As an alternative, you can use the <xref:System.Reflection.Assembly.UnsafeLoadFrom%2A> method to load a local assembly that the operating system has flagged as having been loaded from the web.</span></span>

- <span data-ttu-id="4783b-155"><xref:System.IO.FileLoadException>Windows 가상 PC 응용 프로그램에서 실행 되는 응용 프로그램에서가 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4783b-155">You may get a <xref:System.IO.FileLoadException> in an application that is running in a Windows Virtual PC application.</span></span> <span data-ttu-id="4783b-156">호스팅 컴퓨터의 연결 된 폴더에서 파일을 로드 하려고 하면이 문제가 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4783b-156">This can happen when you try to load a file from linked folders on the hosting computer.</span></span> <span data-ttu-id="4783b-157">[원격 데스크톱 서비스](/windows/win32/termserv/terminal-services-portal) (터미널 서비스)를 통해 연결 된 폴더에서 파일을 로드 하려고 할 때에도 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4783b-157">It can also occur when you try to load a file from a folder linked over [Remote Desktop Services](/windows/win32/termserv/terminal-services-portal) (Terminal Services).</span></span> <span data-ttu-id="4783b-158">예외를 방지 하려면 `enabled` 를로 설정 `true` 합니다.</span><span class="sxs-lookup"><span data-stu-id="4783b-158">To avoid the exception, set `enabled` to `true`.</span></span>

## <a name="configuration-file"></a><span data-ttu-id="4783b-159">구성 파일</span><span class="sxs-lookup"><span data-stu-id="4783b-159">Configuration file</span></span>

<span data-ttu-id="4783b-160">이 요소는 일반적으로 애플리케이션 구성 파일에서 사용하지만 컨텍스트에 따라 다른 구성 파일에서도 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4783b-160">This element is typically used in the application configuration file, but can be used in other configuration files depending upon the context.</span></span> <span data-ttu-id="4783b-161">자세한 내용은 .NET 보안 블로그에서 [Ca 정책의 더 암시적인 사용: loadFromRemoteSources](https://docs.microsoft.com/archive/blogs/shawnfa/more-implicit-uses-of-cas-policy-loadfromremotesources) 문서를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="4783b-161">For more information, see the article [More Implicit Uses of CAS Policy: loadFromRemoteSources](https://docs.microsoft.com/archive/blogs/shawnfa/more-implicit-uses-of-cas-policy-loadfromremotesources) in the .NET Security blog.</span></span>  

## <a name="example"></a><span data-ttu-id="4783b-162">예제</span><span class="sxs-lookup"><span data-stu-id="4783b-162">Example</span></span>

<span data-ttu-id="4783b-163">다음 예제에서는 원격 소스에서 로드 된 어셈블리에 완전 신뢰를 부여 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="4783b-163">The following example shows how to grant full trust to assemblies loaded from remote sources.</span></span>

```xml
<configuration>  
   <runtime>  
      <loadFromRemoteSources enabled="true"/>  
   </runtime>  
</configuration>  
```

## <a name="see-also"></a><span data-ttu-id="4783b-164">참고 항목</span><span class="sxs-lookup"><span data-stu-id="4783b-164">See also</span></span>

- [<span data-ttu-id="4783b-165">CAS 정책의 보다 암시적 사용: loadFromRemoteSources</span><span class="sxs-lookup"><span data-stu-id="4783b-165">More Implicit Uses of CAS Policy: loadFromRemoteSources</span></span>](https://docs.microsoft.com/archive/blogs/shawnfa/more-implicit-uses-of-cas-policy-loadfromremotesources)
- [<span data-ttu-id="4783b-166">방법: 샌드박스에서 부분적으로 신뢰할 수 있는 코드 실행</span><span class="sxs-lookup"><span data-stu-id="4783b-166">How to: Run Partially Trusted Code in a Sandbox</span></span>](../../../misc/how-to-run-partially-trusted-code-in-a-sandbox.md)
- [<span data-ttu-id="4783b-167">런타임 설정 스키마</span><span class="sxs-lookup"><span data-stu-id="4783b-167">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="4783b-168">구성 파일 스키마</span><span class="sxs-lookup"><span data-stu-id="4783b-168">Configuration File Schema</span></span>](../index.md)
- <xref:System.Reflection.Assembly.LoadFrom%2A?displayProperty=nameWithType>
