---
description: C# 컴파일러 옵션. C# 컴파일러의 동작을 제어하는 옵션에 대해 알아봅니다.
title: C# 컴파일러 옵션
ms.date: 03/12/2021
f1_keywords:
- cs.build.options
helpviewer_keywords:
- compiler options [C#]
- csc.exe
- cl.exe compiler, C# options
- Visual C# compiler
- Visual C#, compiler options
ms.assetid: d3403556-1816-4546-a782-e8223a772e44
ms.openlocfilehash: cbe4db51652e8bfd00c555b6ddd230e124a08360
ms.sourcegitcommit: 0bb8074d524e0dcf165430b744bb143461f17026
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/15/2021
ms.locfileid: "103478471"
---
# <a name="c-compiler-options"></a><span data-ttu-id="41969-104">C# 컴파일러 옵션</span><span class="sxs-lookup"><span data-stu-id="41969-104">C# Compiler Options</span></span>

<span data-ttu-id="41969-105">이 섹션에서는 C# 컴파일러에서 해석되는 옵션에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="41969-105">This section describes the options interpreted by the C# compiler.</span></span> <span data-ttu-id="41969-106">.NET 프로젝트에서 컴파일러 옵션을 설정하는 방법에는 두 가지가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="41969-106">There are two different ways to set compiler options in .NET projects:</span></span>

- <span data-ttu-id="41969-107">***\*.csproj 파일에서 옵션 지정***: *\*.csproj* 파일의 모든 컴파일러 옵션에 대해 XML 요소를 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="41969-107">***Specify option in your \*.csproj file***: You can add XML elements for any compiler option in your *\*.csproj* file.</span></span> <span data-ttu-id="41969-108">요소 이름은 컴파일러 옵션과 동일합니다.</span><span class="sxs-lookup"><span data-stu-id="41969-108">The element name is the same as the compiler option.</span></span> <span data-ttu-id="41969-109">XML 요소의 값은 컴파일러 옵션의 값을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="41969-109">The value of the XML element sets the value of the compiler option.</span></span> <span data-ttu-id="41969-110">프로젝트 파일에서 옵션을 설정하는 방법에 대한 자세한 내용은 [.NET SDK 프로젝트용 MSBuild 속성](../../../core/project-sdk/msbuild-props.md) 문서를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="41969-110">For more information on setting options in project files, see the article [MSBuild properties for .NET SDK Projects](../../../core/project-sdk/msbuild-props.md).</span></span>
- <span data-ttu-id="41969-111">***Visual Studio 속성 페이지 사용***: Visual Studio는 빌드 속성을 편집할 수 있는 속성 페이지를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="41969-111">***Using the Visual Studio Property pages***: Visual Studio provides property pages to edit build properties.</span></span> <span data-ttu-id="41969-112">자세히 알아보려면 [프로젝트 및 솔루션 속성 관리 - Windows](/visualstudio/ide/managing-project-and-solution-properties#c-visual-basic-and-f-projects) 또는 [프로젝트 및 솔루션 속성 관리 - Mac](/visualstudio/mac/managing-solutions-and-project-properties)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="41969-112">To learn more about them, see [Manage project and solution properties - Windows](/visualstudio/ide/managing-project-and-solution-properties#c-visual-basic-and-f-projects) or [Manage project and solution properties - Mac](/visualstudio/mac/managing-solutions-and-project-properties).</span></span>

## <a name="net-framework-projects"></a><span data-ttu-id="41969-113">.NET Framework 프로젝트</span><span class="sxs-lookup"><span data-stu-id="41969-113">.NET Framework projects</span></span>

> [!IMPORTANT]
> <span data-ttu-id="41969-114">이 섹션은 .NET Framework 프로젝트에만 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="41969-114">This section applies to .NET Framework projects only.</span></span>

<span data-ttu-id="41969-115">위에서 설명한 메커니즘 외에도 .NET Framework 프로젝트에 대한 두 가지 추가 메서드를 사용하여 컴파일러 옵션을 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="41969-115">In addition to the mechanisms described above, you can set compiler options using two additional methods for .NET Framework projects:</span></span>

- <span data-ttu-id="41969-116">**.NET Framework 프로젝트의 명령줄 인수**: .NET Framework 프로젝트는 프로젝트를 빌드하는 데 `dotnet build` 대신 *csc.exe* 를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="41969-116">**Command line arguments for .NET Framework projects**: .NET Framework projects use *csc.exe* instead of `dotnet build` to build projects.</span></span> <span data-ttu-id="41969-117">.NET Framework 프로젝트에 대한 *csc.exe* 명령줄 인수를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="41969-117">You can specify command line arguments to *csc.exe* for .NET Framework projects.</span></span>
- <span data-ttu-id="41969-118">**컴파일된 ASP.NET 페이지**: .NET Framework 프로젝트는 *web.config* 파일의 섹션을 사용하여 페이지를 컴파일합니다.</span><span class="sxs-lookup"><span data-stu-id="41969-118">**Compiled ASP.NET pages**: .NET Framework projects use a section of the *web.config* file for compiling pages.</span></span> <span data-ttu-id="41969-119">새로운 빌드 시스템과 ASP.NET Core 프로젝트의 경우, 프로젝트 파일에서 옵션을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="41969-119">For the new build system, and ASP.NET Core projects, options are taken from the project file.</span></span>

<span data-ttu-id="41969-120">일부 컴파일러 옵션의 단어는 *csc.exe* 및 .NET Framework 프로젝트에서 새 MSBuild 시스템으로 변경되었습니다.</span><span class="sxs-lookup"><span data-stu-id="41969-120">The word for some compiler options changed from *csc.exe* and .NET Framework projects to the new MSBuild system.</span></span> <span data-ttu-id="41969-121">이 섹션에서는 새로운 구문이 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="41969-121">The new syntax is used throughout this section.</span></span> <span data-ttu-id="41969-122">두 버전은 각 페이지의 맨 위에 나열됩니다.</span><span class="sxs-lookup"><span data-stu-id="41969-122">Both versions are listed at the top of each page.</span></span> <span data-ttu-id="41969-123">*csc.exe* 의 경우, 옵션과 콜론 뒤에 모든 인수가 나열됩니다.</span><span class="sxs-lookup"><span data-stu-id="41969-123">For *csc.exe*, any arguments are listed following the option and a colon.</span></span> <span data-ttu-id="41969-124">예를 들어 `-doc` 옵션은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="41969-124">For example, the `-doc` option would be:</span></span>

```console
-doc:DocFile.xml
```

<span data-ttu-id="41969-125">명령 프롬프트에서 실행 파일(*csc.exe*)의 이름을 입력하여 C# 컴파일러를 호출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="41969-125">You can invoke the C# compiler by typing the name of its executable file (*csc.exe*) at a command prompt.</span></span>

<span data-ttu-id="41969-126">.NET Framework 프로젝트의 경우 명령줄에서 *csc.exe* 를 실행할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="41969-126">For .NET Framework projects, you can also run *csc.exe* from the command line.</span></span> <span data-ttu-id="41969-127">모든 컴파일러 옵션은 **-옵션** 및 **/옵션** 의 두 가지 형태로 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="41969-127">Every compiler option is available in two forms: **-option** and **/option**.</span></span> <span data-ttu-id="41969-128">.NET Framework 웹 프로젝트에서는 *web.config* 파일에서 코드 숨김으로 컴파일하는 옵션을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="41969-128">In .NET Framework web projects, you specify options for compiling code-behind in the *web.config* file.</span></span> <span data-ttu-id="41969-129">자세한 내용은 [\<compiler> 요소](../../../framework/configure-apps/file-schema/compiler/compiler-element.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="41969-129">For more information, see [\<compiler> Element](../../../framework/configure-apps/file-schema/compiler/compiler-element.md).</span></span>

<span data-ttu-id="41969-130">**Visual Studio용 개발자 명령 프롬프트** 창을 사용하는 경우 필요한 환경 변수가 모두 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="41969-130">If you use the **Developer Command Prompt for Visual Studio** window, all the necessary environment variables are set for you.</span></span> <span data-ttu-id="41969-131">이 도구에 액세스하는 방법에 대한 자세한 내용은 [Visual Studio용 개발자 명령 프롬프트](../../../framework/tools/developer-command-prompt-for-vs.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="41969-131">For information on how to access this tool, see [Developer Command Prompt for Visual Studio](../../../framework/tools/developer-command-prompt-for-vs.md).</span></span>

<span data-ttu-id="41969-132">*csc.exe* 실행 파일은 대개 *Windows* 디렉터리 아래의 Microsoft.NET\Framework\\ *\<Version>* 폴더에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="41969-132">The *csc.exe* executable file is usually located in the Microsoft.NET\Framework\\*\<Version>* folder under the *Windows* directory.</span></span> <span data-ttu-id="41969-133">이 위치는 개별 컴퓨터의 구성에 따라 다를 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="41969-133">Its location might vary depending on the exact configuration of a particular computer.</span></span> <span data-ttu-id="41969-134">컴퓨터에 .NET Framework 버전이 두 개 이상 설치된 경우 이 파일의 여러 버전을 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="41969-134">If more than one version of .NET Framework is installed on your computer, you'll find multiple versions of this file.</span></span> <span data-ttu-id="41969-135">해당 설치에 대한 자세한 내용은 [방법: 설치된 .NET Framework 버전 확인](../../../framework/migration-guide/how-to-determine-which-versions-are-installed.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="41969-135">For more information about such installations, see [How to: determine which versions of the .NET Framework are installed](../../../framework/migration-guide/how-to-determine-which-versions-are-installed.md).</span></span>
