---
description: dotnet 애플리케이션에 포함된 Windows 리소스를 제어하는 C# 컴파일러 옵션입니다.
title: C# 컴파일러 옵션 - 리소스 옵션
ms.date: 03/12/2021
f1_keywords:
- cs.build.options
helpviewer_keywords:
- Win32Resource compiler option [C#]
- Win32Icon compiler option [C#]
- Win32Manifest compiler option [C#]
- NoWin32Manifest compiler option [C#]
- Resources compiler option [C#]
- LinkResources compiler option [C#]
ms.openlocfilehash: fe2da8cae67bc597d2b84a395861a0e4c32c9d72
ms.sourcegitcommit: 0bb8074d524e0dcf165430b744bb143461f17026
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/15/2021
ms.locfileid: "103482436"
---
# <a name="c-compiler-options-that-specify-resources"></a><span data-ttu-id="40220-103">리소스를 지정하는 C# 컴파일러 옵션</span><span class="sxs-lookup"><span data-stu-id="40220-103">C# Compiler Options that specify resources</span></span>

<span data-ttu-id="40220-104">다음 옵션은 C# 컴파일러에서 Win32 리소스를 만들거나 가져오는 방법을 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="40220-104">The following options control how the C# compiler creates or imports Win32 resources.</span></span> <span data-ttu-id="40220-105">새 MSBuild 구문은 **굵게** 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="40220-105">The new MSBuild syntax is shown in **Bold**.</span></span> <span data-ttu-id="40220-106">이전 *csc.exe* 구문은 `code style`에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="40220-106">The older *csc.exe* syntax is shown in `code style`.</span></span>

- <span data-ttu-id="40220-107">**Win32Resource** / `-win32res`: Win32 리소스 파일(.res)을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="40220-107">**Win32Resource** / `-win32res`: Specify a Win32 resource file (.res).</span></span>
- <span data-ttu-id="40220-108">**Win32Icon** / `-win32icon`: 지정한 어셈블리 파일에서 메타데이터를 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="40220-108">**Win32Icon** / `-win32icon`: Reference metadata from the specified assembly file or files.</span></span>
- <span data-ttu-id="40220-109">**Win32Manifest** / `-win32manifest`: Win32 매니페스트 파일(.xml)을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="40220-109">**Win32Manifest** / `-win32manifest`: Specify a Win32 manifest file (.xml).</span></span>
- <span data-ttu-id="40220-110">**NoWin32Manifest** / `-nowin32manifest`: 기본 Win32 매니페스트를 포함하지 마세요.</span><span class="sxs-lookup"><span data-stu-id="40220-110">**NoWin32Manifest** / `-nowin32manifest`: Don't include the default Win32 manifest.</span></span>
- <span data-ttu-id="40220-111">**Resources** / `-resource`: 지정된 리소스(약식: /res)를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="40220-111">**Resources** / `-resource`: Embed the specified resource (Short form: /res).</span></span>
- <span data-ttu-id="40220-112">**LinkResources** / `-linkresources`: 지정된 리소스를 이 어셈블리에 연결합니다.</span><span class="sxs-lookup"><span data-stu-id="40220-112">**LinkResources** / `-linkresources`: Link the specified resource to this assembly.</span></span>

## <a name="win32resource"></a><span data-ttu-id="40220-113">Win32Resource</span><span class="sxs-lookup"><span data-stu-id="40220-113">Win32Resource</span></span>

<span data-ttu-id="40220-114">**Win32Resource** 옵션은 출력 파일에 Win32 리소스를 삽입합니다.</span><span class="sxs-lookup"><span data-stu-id="40220-114">The **Win32Resource** option inserts a Win32 resource in the output file.</span></span>

```xml
<Win32Resource>filename</Win32Resource>
```

<span data-ttu-id="40220-115">`filename`은 출력 파일에 추가할 리소스 파일입니다.</span><span class="sxs-lookup"><span data-stu-id="40220-115">`filename` is the resource file that you want to add to your output file.</span></span> <span data-ttu-id="40220-116">Win32 리소스는 파일 탐색기에서 애플리케이션을 식별하는 데 도움이 되는 버전 정보나 비트맵 (아이콘) 정보를 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="40220-116">A Win32 resource can contain version or bitmap (icon) information that would help identify your application in the File Explorer.</span></span> <span data-ttu-id="40220-117">이 옵션을 지정하지 않으면 컴파일러에서 어셈블리 버전을 기반으로 버전 정보를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="40220-117">If you don't specify this option, the compiler will generate version information based on the assembly version.</span></span>

## <a name="win32icon"></a><span data-ttu-id="40220-118">Win32Icon</span><span class="sxs-lookup"><span data-stu-id="40220-118">Win32Icon</span></span>

<span data-ttu-id="40220-119">**Win32Icon** 옵션은 .ico 파일을 출력 파일에 삽입하여 파일 탐색기에서 출력 파일을 원하는 모양으로 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="40220-119">The **Win32Icon** option inserts an .ico file in the output file, which gives the output file the desired appearance in the File Explorer.</span></span>
  
```xml
<Win32Icon>filename</Win32Icon>
```

<span data-ttu-id="40220-120">`filename`은 출력 파일에 추가할 *.ico* 파일입니다.</span><span class="sxs-lookup"><span data-stu-id="40220-120">`filename` is the *.ico* file that you want to add to your output file.</span></span> <span data-ttu-id="40220-121">*.ico* 파일은 [리소스 컴파일러](/windows/desktop/menurc/resource-compiler)로 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="40220-121">An *.ico* file can be created with the [Resource Compiler](/windows/desktop/menurc/resource-compiler).</span></span> <span data-ttu-id="40220-122">리소스 컴파일러는 Visual C++ 프로그램을 컴파일할 때 호출됩니다. *.ico* 파일은 *.rc* 파일에서 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="40220-122">The Resource Compiler is invoked when you compile a Visual C++ program; an *.ico* file is created from the *.rc* file.</span></span>

## <a name="win32manifest"></a><span data-ttu-id="40220-123">Win32Manifest</span><span class="sxs-lookup"><span data-stu-id="40220-123">Win32Manifest</span></span>

<span data-ttu-id="40220-124">**Win32Manifest** 옵션을 사용하여 프로젝트의 PE(포팅 가능한 실행 파일) 파일에 포함할 사용자 정의 Win32 애플리케이션 매니페스트 파일을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="40220-124">Use the **Win32Manifest** option to specify a user-defined Win32 application manifest file to be embedded into a project's portable executable (PE) file.</span></span>

```xml
<Win32Manifest>filename</Win32Manifest>
```

<span data-ttu-id="40220-125">`filename`은 사용자 지정 매니페스트 파일의 이름과 위치입니다.</span><span class="sxs-lookup"><span data-stu-id="40220-125">`filename` is the name and location of the custom manifest file.</span></span> <span data-ttu-id="40220-126">기본적으로 C# 컴파일러에는 "asInvoker"의 요청된 실행 수준을 지정하는 애플리케이션 매니페스트가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="40220-126">By default, the C# compiler embeds an application manifest that specifies a requested execution level of "asInvoker".</span></span> <span data-ttu-id="40220-127">실행 파일이 빌드된 동일한 폴더에 매니페스트를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="40220-127">It creates the manifest in the same folder in which the executable is built.</span></span> <span data-ttu-id="40220-128">예를 들어 "highestAvailable" 또는 "requireAdministrator"의 요청된 실행 수준을 지정하기 위해 사용자 지정 매니페스트를 제공하려면 이 옵션을 사용하여 파일 이름을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="40220-128">If you want to supply a custom manifest, for example to specify a requested execution level of "highestAvailable" or "requireAdministrator," use this option to specify the name of the file.</span></span>

> [!NOTE]
> <span data-ttu-id="40220-129">이 옵션과 **Win32Resources** 옵션은 함께 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="40220-129">This option and the **Win32Resources** option are mutually exclusive.</span></span> <span data-ttu-id="40220-130">같은 명령줄에서 두 옵션을 모두 사용하려고 하면 빌드 오류가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="40220-130">If you try to use both options in the same command line you will get a build error.</span></span>

<span data-ttu-id="40220-131">요청된 실행 수준을 지정하는 애플리케이션 매니페스트가 없는 애플리케이션은 Windows의 사용자 계정 컨트롤 기능에 따라 파일 및 레지스트리 가상화의 적용을 받습니다.</span><span class="sxs-lookup"><span data-stu-id="40220-131">An application that has no application manifest that specifies a requested execution level will be subject to file and registry virtualization under the User Account Control feature in Windows.</span></span> <span data-ttu-id="40220-132">자세한 내용은 [사용자 계정 컨트롤](/windows/access-protection/user-account-control/user-account-control-overview)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="40220-132">For more information, see [User Account Control](/windows/access-protection/user-account-control/user-account-control-overview).</span></span>

<span data-ttu-id="40220-133">다음 조건 중 하나라도 참인 경우 애플리케이션에 가상화가 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="40220-133">Your application will be subject to virtualization if either of these conditions is true:</span></span>
  
- <span data-ttu-id="40220-134">**NoWin32Manifest** 옵션을 사용하고 **Win32Resource** 옵션을 사용하여 이후 빌드 단계 또는 Windows Resource( *.res*) 파일의 일부로 매니페스트를 제공하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="40220-134">You use the **NoWin32Manifest** option and you don't provide a manifest in a later build step or as part of a Windows Resource (*.res*) file by using the **Win32Resource** option.</span></span>
- <span data-ttu-id="40220-135">요청한 실행 수준을 지정하지 않는 사용자 지정 매니페스트를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="40220-135">You provide a custom manifest that doesn't specify a requested execution level.</span></span>

<span data-ttu-id="40220-136">Visual Studio는 기본 *.manifest* 파일을 만들고 이를 실행 파일과 함께 debug 및 release 디렉터리에 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="40220-136">Visual Studio creates a default *.manifest* file and stores it in the debug and release directories alongside the executable file.</span></span> <span data-ttu-id="40220-137">텍스트 편집기에서 파일을 만들고 프로젝트에 파일을 추가하여 사용자 지정 매니페스트를 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="40220-137">You can add a custom manifest by creating one in any text editor and then adding the file to the project.</span></span> <span data-ttu-id="40220-138">또는 **솔루션 탐색기** 에서 **프로젝트** 아이콘을 마우스 오른쪽 단추로 클릭하고 **새 항목 추가** 를 선택한 다음, **애플리케이션 매니페스트 파일** 을 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="40220-138">Or, you can right-click the **Project** icon in **Solution Explorer**, select **Add New Item**, and then select **Application Manifest File**.</span></span> <span data-ttu-id="40220-139">신규 또는 기존 매니페스트 파일을 추가하면 **매니페스트** 드롭다운 목록에 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="40220-139">After you've added your new or existing manifest file, it will appear in the **Manifest** drop down list.</span></span> <span data-ttu-id="40220-140">자세한 내용은 [프로젝트 디자이너, 애플리케이션 페이지(C#)](/visualstudio/ide/reference/application-page-project-designer-csharp)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="40220-140">For more information, see [Application Page, Project Designer (C#)](/visualstudio/ide/reference/application-page-project-designer-csharp).</span></span>

<span data-ttu-id="40220-141">**NoWin32Manifest** 옵션을 사용하여 애플리케이션 매니페스트를 사용자 지정 빌드 후 단계 또는 Win32 리소스 파일의 일부로 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="40220-141">You can provide the application manifest as a custom post-build step or as part of a Win32 resource file by using the **NoWin32Manifest** option.</span></span> <span data-ttu-id="40220-142">애플리케이션이 Windows Vista에서 파일 또는 레지스트리 가상화의 적용을 받도록 하려면 동일한 옵션을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="40220-142">Use that same option if you want your application to be subject to file or registry virtualization on Windows Vista.</span></span>
  
## <a name="nowin32manifest"></a><span data-ttu-id="40220-143">NoWin32Manifest</span><span class="sxs-lookup"><span data-stu-id="40220-143">NoWin32Manifest</span></span>

<span data-ttu-id="40220-144">**NoWin32Manifest** 옵션을 사용하면 실행 파일에 애플리케이션 매니페스트를 포함하지 않도록 컴파일러에 지시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="40220-144">Use the **NoWin32Manifest** option to instruct the compiler not to embed any application manifest into the executable file.</span></span>

```xml  
<NoWin32Manifest />
```

<span data-ttu-id="40220-145">이 옵션을 사용하는 경우 Win32 리소스 파일에서 또는 이후 빌드 단계 중에 애플리케이션 매니페스트를 제공하지 않으면 Windows Vista에서 애플리케이션에 가상화가 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="40220-145">When this option is used, the application will be subject to virtualization on Windows Vista unless you provide an application manifest in a Win32 Resource file or during a later build step.</span></span>

<span data-ttu-id="40220-146">Visual Studio의 **애플리케이션 속성** 페이지에 있는 **매니페스트** 드롭다운 목록에서 **매니페스트 없이 애플리케이션 만들기** 옵션을 선택하여 이 옵션을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="40220-146">In Visual Studio, set this option in the **Application Property** page by selecting the **Create Application Without a Manifest** option in the **Manifest** drop down list.</span></span> <span data-ttu-id="40220-147">자세한 내용은 [프로젝트 디자이너, 애플리케이션 페이지(C#)](/visualstudio/ide/reference/application-page-project-designer-csharp)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="40220-147">For more information, see [Application Page, Project Designer (C#)](/visualstudio/ide/reference/application-page-project-designer-csharp).</span></span>

## <a name="resources"></a><span data-ttu-id="40220-148">리소스</span><span class="sxs-lookup"><span data-stu-id="40220-148">Resources</span></span>

<span data-ttu-id="40220-149">출력 파일에 지정된 리소스를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="40220-149">Embeds the specified resource into the output file.</span></span>

```xml
<Resources Include=filename>
  <LogicalName>identifier</LogicalName>
  <Access>accessibility-modifier</Access>
</Resources>
```

<span data-ttu-id="40220-150">`filename`은 출력 파일에 포함할 .NET 리소스 파일입니다.</span><span class="sxs-lookup"><span data-stu-id="40220-150">`filename` is the .NET resource file that you want to embed in the output file.</span></span> <span data-ttu-id="40220-151">`identifier`(선택 사항)는 리소스의 논리적 이름으로, 리소스를 로드하는 데 사용되는 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="40220-151">`identifier` (optional) is the logical name for the resource; the name that is used to load the resource.</span></span> <span data-ttu-id="40220-152">기본값은 파일 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="40220-152">The default is the name of the file.</span></span> <span data-ttu-id="40220-153">`accessibility-modifier`(선택 사항)는 리소스의 접근성(퍼블릭 또는 프라이빗)입니다.</span><span class="sxs-lookup"><span data-stu-id="40220-153">`accessibility-modifier` (optional) is the accessibility of the resource: public or private.</span></span> <span data-ttu-id="40220-154">기본값은 public입니다.</span><span class="sxs-lookup"><span data-stu-id="40220-154">The default is public.</span></span> <span data-ttu-id="40220-155">기본적으로 리소스는 C# 컴파일러를 사용하여 생성될 때 어셈블리에서 퍼블릭입니다.</span><span class="sxs-lookup"><span data-stu-id="40220-155">By default, resources are public in the assembly when they're created by using the C# compiler.</span></span> <span data-ttu-id="40220-156">리소스를 private로 만들려면 접근성 한정자로 `private`를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="40220-156">To make the resources private, specify `private` as the accessibility modifier.</span></span> <span data-ttu-id="40220-157">`public` 또는 `private` 이외의 다른 접근성은 허용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="40220-157">No other accessibility other than `public` or `private` is allowed.</span></span> <span data-ttu-id="40220-158">예를 들어 `filename`이 [Resgen.exe](../../../framework/tools/resgen-exe-resource-file-generator.md) 또는 개발 환경에서 만들어진 .NET 리소스 파일인 경우에는 <xref:System.Resources> 네임스페이스의 멤버를 사용하여 해당 파일에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="40220-158">If `filename` is a .NET resource file created, for example, by [Resgen.exe](../../../framework/tools/resgen-exe-resource-file-generator.md) or in the development environment, it can be accessed with members in the <xref:System.Resources> namespace.</span></span> <span data-ttu-id="40220-159">자세한 내용은 <xref:System.Resources.ResourceManager?displayProperty=nameWithType>를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="40220-159">For more information, see <xref:System.Resources.ResourceManager?displayProperty=nameWithType>.</span></span> <span data-ttu-id="40220-160">다른 모든 리소스의 경우에는 런타임에 `GetManifestResource` 클래스의 <xref:System.Reflection.Assembly> 메서드를 사용하여 리소스에 액세스합니다.</span><span class="sxs-lookup"><span data-stu-id="40220-160">For all other resources, use the `GetManifestResource` methods in the <xref:System.Reflection.Assembly> class to access the resource at run time.</span></span> <span data-ttu-id="40220-161">출력 파일에 있는 리소스의 순서는 프로젝트 파일에 지정된 순서에 따라 결정됩니다.</span><span class="sxs-lookup"><span data-stu-id="40220-161">The order of the resources in the output file is determined from the order specified in the project file.</span></span>  
  
## <a name="linkresources"></a><span data-ttu-id="40220-162">LinkResources</span><span class="sxs-lookup"><span data-stu-id="40220-162">LinkResources</span></span>

<span data-ttu-id="40220-163">출력 파일에 .NET 리소스에 대한 링크를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="40220-163">Creates a link to a .NET resource in the output file.</span></span> <span data-ttu-id="40220-164">리소스 파일은 출력 파일에 추가되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="40220-164">The resource file isn't added to the output file.</span></span> <span data-ttu-id="40220-165">**LinkResources** 는 출력 파일에 리소스 파일을 포함하는 **Resource** 옵션과 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="40220-165">**LinkResources** differs from the **Resource** option, which does embed a resource file in the output file.</span></span>

```xml
<LinkResources Include=filename>
  <LogicalName>identifier</LogicalName>
  <Access>accessibility-modifier</Access>
</LinkResources>
```

<span data-ttu-id="40220-166">`filename`은 어셈블리에서 연결할 .NET 리소스 파일입니다.</span><span class="sxs-lookup"><span data-stu-id="40220-166">`filename` is the .NET resource file to which you want to link from the assembly.</span></span> <span data-ttu-id="40220-167">`identifier`(선택 사항)는 리소스의 논리적 이름으로, 리소스를 로드하는 데 사용되는 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="40220-167">`identifier` (optional) is the logical name for the resource; the name that is used to load the resource.</span></span> <span data-ttu-id="40220-168">기본값은 파일 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="40220-168">The default is the name of the file.</span></span> <span data-ttu-id="40220-169">`accessibility-modifier`(선택 사항)는 리소스의 접근성(퍼블릭 또는 프라이빗)입니다.</span><span class="sxs-lookup"><span data-stu-id="40220-169">`accessibility-modifier` (optional) is the accessibility of the resource: public or private.</span></span> <span data-ttu-id="40220-170">기본값은 public입니다.</span><span class="sxs-lookup"><span data-stu-id="40220-170">The default is public.</span></span> <span data-ttu-id="40220-171">기본적으로 연결된 리소스는 C# 컴파일러로 생성될 때 어셈블리에서 퍼블릭입니다.</span><span class="sxs-lookup"><span data-stu-id="40220-171">By default, linked resources are public in the assembly when they're created with the C# compiler.</span></span> <span data-ttu-id="40220-172">리소스를 private로 만들려면 접근성 한정자로 `private`를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="40220-172">To make the resources private, specify `private` as the accessibility modifier.</span></span> <span data-ttu-id="40220-173">`public` 또는 `private` 이외의 다른 한정자는 허용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="40220-173">No other modifier other than `public` or `private` is allowed.</span></span> <span data-ttu-id="40220-174">예를 들어 `filename`이 [Resgen.exe](../../../framework/tools/resgen-exe-resource-file-generator.md) 또는 개발 환경에서 만들어진 .NET 리소스 파일인 경우에는 <xref:System.Resources> 네임스페이스의 멤버를 사용하여 해당 파일에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="40220-174">If `filename` is a .NET resource file created, for example, by [Resgen.exe](../../../framework/tools/resgen-exe-resource-file-generator.md) or in the development environment, it can be accessed with members in the <xref:System.Resources> namespace.</span></span> <span data-ttu-id="40220-175">자세한 내용은 <xref:System.Resources.ResourceManager?displayProperty=nameWithType>를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="40220-175">For more information, see <xref:System.Resources.ResourceManager?displayProperty=nameWithType>.</span></span> <span data-ttu-id="40220-176">다른 모든 리소스의 경우에는 런타임에 `GetManifestResource` 클래스의 <xref:System.Reflection.Assembly> 메서드를 사용하여 리소스에 액세스합니다.</span><span class="sxs-lookup"><span data-stu-id="40220-176">For all other resources, use the `GetManifestResource` methods in the <xref:System.Reflection.Assembly> class to access the resource at run time.</span></span> <span data-ttu-id="40220-177">`filename`에 지정된 파일은 모든 형식일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="40220-177">The file specified in `filename` can be any format.</span></span> <span data-ttu-id="40220-178">예를 들어 네이티브 DLL을 어셈블리의 일부로 설정하면 전역 어셈블리 캐시에 설치하고 어셈블리의 관리 코드에서 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="40220-178">For example, you may want to make a native DLL part of the assembly, so that it can be installed into the global assembly cache and accessed from managed code in the assembly.</span></span> <span data-ttu-id="40220-179">어셈블리 링커에서도 동일한 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="40220-179">You can do the same thing in the Assembly Linker.</span></span> <span data-ttu-id="40220-180">자세한 내용은 [Al.exe(어셈블리 링커)](../../../framework/tools/al-exe-assembly-linker.md) 및 [어셈블리 및 전역 어셈블리 캐시 사용](../../../framework/app-domains/working-with-assemblies-and-the-gac.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="40220-180">For more information, see [Al.exe (Assembly Linker)](../../../framework/tools/al-exe-assembly-linker.md) and [Working with Assemblies and the Global Assembly Cache](../../../framework/app-domains/working-with-assemblies-and-the-gac.md).</span></span>
