---
title: 앱 컴파일
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WPF application [WPF], building
ms.assetid: a58696fd-bdad-4b55-9759-136dfdf8b91c
ms.openlocfilehash: 00c76dfcdcedc7ceaefaaae785368f8b343457a7
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/24/2020
ms.locfileid: "76744771"
---
# <a name="compile-a-wpf-application"></a><span data-ttu-id="d38fd-102">WPF 응용 프로그램 컴파일</span><span class="sxs-lookup"><span data-stu-id="d38fd-102">Compile a WPF Application</span></span>

<span data-ttu-id="d38fd-103">WPF (Windows Presentation Foundation) 응용 프로그램은 .NET Framework 실행 파일 (.exe), 라이브러리 (.dll) 또는 두 어셈블리 형식의 조합으로 빌드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d38fd-103">Windows Presentation Foundation (WPF) applications can be built as .NET Framework executables (.exe), libraries (.dll), or a combination of both types of assemblies.</span></span> <span data-ttu-id="d38fd-104">이 항목에서는 WPF 응용 프로그램을 빌드하는 방법을 소개 하 고 빌드 프로세스의 주요 단계에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="d38fd-104">This topic introduces how to build WPF applications and describes the key steps in the build process.</span></span>

<a name="Building_a_WPF_Application_using_Command_Line"></a>

## <a name="building-a-wpf-application"></a><span data-ttu-id="d38fd-105">WPF 애플리케이션 빌드</span><span class="sxs-lookup"><span data-stu-id="d38fd-105">Building a WPF Application</span></span>

<span data-ttu-id="d38fd-106">다음과 같은 방법으로 WPF 애플리케이션을 컴파일할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d38fd-106">A WPF application can be compiled in the following ways:</span></span>

- <span data-ttu-id="d38fd-107">명령줄.</span><span class="sxs-lookup"><span data-stu-id="d38fd-107">Command-line.</span></span> <span data-ttu-id="d38fd-108">애플리케이션에 코드(XAML 없음)와 애플리케이션 정의 파일만 포함되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d38fd-108">The application must contain only code (no XAML) and an application definition file.</span></span> <span data-ttu-id="d38fd-109">자세한 내용은 [csc.exe를 사용한 명령줄 빌드](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md) 또는 [명령줄에서 빌드(Visual Basic)](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d38fd-109">For more information, see [Command-line Building With csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md) or [Building from the Command Line (Visual Basic)](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md).</span></span>

- <span data-ttu-id="d38fd-110">MSBuild(Microsoft Build Engine).</span><span class="sxs-lookup"><span data-stu-id="d38fd-110">Microsoft Build Engine (MSBuild).</span></span> <span data-ttu-id="d38fd-111">애플리케이션에 코드 및 XAML 파일 외에 MSBuild 프로젝트 파일이 포함되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d38fd-111">In addition to the code and XAML files, the application must contain an MSBuild project file.</span></span> <span data-ttu-id="d38fd-112">자세한 내용은 "MSBuild"를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d38fd-112">For more information, see "MSBuild".</span></span>

- <span data-ttu-id="d38fd-113">보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="d38fd-113">Visual Studio.</span></span> <span data-ttu-id="d38fd-114">Visual Studio는 MSBuild를 사용하여 WPF 애플리케이션을 컴파일하고 UI를 만들기 위한 비주얼 디자이너를 포함하는 통합 개발 환경입니다.</span><span class="sxs-lookup"><span data-stu-id="d38fd-114">Visual Studio is an integrated development environment that compiles WPF applications with MSBuild and includes a visual designer for creating UI.</span></span> <span data-ttu-id="d38fd-115">자세한 내용은 visual Studio를 [사용 하 여 코드 작성 및 관리](/visualstudio/ide/index-writing-code) 및 [VISUAL Studio에서 XAML 디자인](/visualstudio/xaml-tools/designing-xaml-in-visual-studio)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="d38fd-115">For more information, see [Write and manage code using Visual Studio](/visualstudio/ide/index-writing-code) and [Design XAML in Visual Studio](/visualstudio/xaml-tools/designing-xaml-in-visual-studio).</span></span>

<a name="The_Windows_Presentation_Foundation_Build_Pipeline"></a>

## <a name="wpf-build-pipeline"></a><span data-ttu-id="d38fd-116">WPF 빌드 파이프라인</span><span class="sxs-lookup"><span data-stu-id="d38fd-116">WPF Build Pipeline</span></span>

<span data-ttu-id="d38fd-117">WPF 프로젝트를 빌드할 때 언어별 및 WPF 관련 대상의 조합이 호출 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d38fd-117">When a WPF project is built, the combination of language-specific and WPF-specific targets are invoked.</span></span> <span data-ttu-id="d38fd-118">이러한 대상을 실행 중인 프로세스를 빌드 파이프라인이라고 하며 주요 단계는 다음 그림에서와 같이 설명됩니다.</span><span class="sxs-lookup"><span data-stu-id="d38fd-118">The process of executing these targets is called the build pipeline, and the key steps are illustrated by the following figure.</span></span>

<span data-ttu-id="d38fd-119">![WPF 빌드 프로세스](./media/wpfbuildsystem-figure1.png "WPFBuildSystem_Figure1")</span><span class="sxs-lookup"><span data-stu-id="d38fd-119">![WPF build process](./media/wpfbuildsystem-figure1.png "WPFBuildSystem_Figure1")</span></span>

<a name="Pre_Build_Initializations"></a>

### <a name="pre-build-initializations"></a><span data-ttu-id="d38fd-120">빌드 전 초기화</span><span class="sxs-lookup"><span data-stu-id="d38fd-120">Pre-Build Initializations</span></span>

<span data-ttu-id="d38fd-121">빌드하기 전에 MSBuild는 다음을 포함 하 여 중요 한 도구 및 라이브러리의 위치를 결정 합니다.</span><span class="sxs-lookup"><span data-stu-id="d38fd-121">Before building, MSBuild determines the location of important tools and libraries, including the following:</span></span>

- <span data-ttu-id="d38fd-122">.NET Framework입니다.</span><span class="sxs-lookup"><span data-stu-id="d38fd-122">The .NET Framework.</span></span>

- <span data-ttu-id="d38fd-123">Windows SDK 디렉터리입니다.</span><span class="sxs-lookup"><span data-stu-id="d38fd-123">The Windows SDK directories.</span></span>

- <span data-ttu-id="d38fd-124">WPF 참조 어셈블리의 위치입니다.</span><span class="sxs-lookup"><span data-stu-id="d38fd-124">The location of WPF reference assemblies.</span></span>

- <span data-ttu-id="d38fd-125">어셈블리 검색 경로의 속성</span><span class="sxs-lookup"><span data-stu-id="d38fd-125">The property for the assembly search paths.</span></span>

<span data-ttu-id="d38fd-126">MSBuild에서 어셈블리를 검색 하는 첫 번째 위치는 참조 어셈블리 디렉터리 (%ProgramFiles%\Reference Assemblies\Microsoft\Framework\v3.0\\)입니다.</span><span class="sxs-lookup"><span data-stu-id="d38fd-126">The first location where MSBuild searches for assemblies is the reference assembly directory (%ProgramFiles%\Reference Assemblies\Microsoft\Framework\v3.0\\).</span></span> <span data-ttu-id="d38fd-127">이 단계에서 빌드 프로세스는 다양한 속성 및 항목 그룹을 초기화하고 필요한 정리 작업을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="d38fd-127">During this step, the build process also initializes the various properties and item groups and performs any required cleanup work.</span></span>

<a name="Resolving_references"></a>

### <a name="resolving-references"></a><span data-ttu-id="d38fd-128">참조 확인</span><span class="sxs-lookup"><span data-stu-id="d38fd-128">Resolving References</span></span>

<span data-ttu-id="d38fd-129">빌드 프로세스는 애플리케이션 프로젝트를 빌드하는 데 필요한 어셈블리를 찾아서 바인딩합니다.</span><span class="sxs-lookup"><span data-stu-id="d38fd-129">The build process locates and binds the assemblies required to build the application project.</span></span> <span data-ttu-id="d38fd-130">이 논리는 `ResolveAssemblyReference` 작업에 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d38fd-130">This logic is contained in the `ResolveAssemblyReference` task.</span></span> <span data-ttu-id="d38fd-131">프로젝트 파일에서 `Reference`로 선언된 모든 어셈블리는 시스템에 이미 설치된 어셈블리의 메타데이터 및 검색 경로에 대한 정보와 함께 작업에 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="d38fd-131">All assemblies declared as `Reference` in the project file are provided to the task along with information on the search paths and metadata on assemblies already installed on the system.</span></span> <span data-ttu-id="d38fd-132">작업은 어셈블리를 조회 하 고 설치 된 어셈블리의 메타 데이터를 사용 하 여 출력 매니페스트에 표시 되지 않아도 되는 핵심 WPF 어셈블리를 필터링 합니다.</span><span class="sxs-lookup"><span data-stu-id="d38fd-132">The task looks up assemblies and uses the installed assembly's metadata to filter out those core WPF assemblies that need not show up in the output manifests.</span></span> <span data-ttu-id="d38fd-133">이 작업의 목적은 ClickOnce 매니페스트에서 중복되는 정보를 방지하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="d38fd-133">This is done to avoid redundant information in the ClickOnce manifests.</span></span> <span data-ttu-id="d38fd-134">예를 들어, PresentationFramework는 및 WPF에 대해 빌드된 응용 프로그램의 대표로 간주할 수 있으며, 모든 WPF 어셈블리는 .NET Framework가 설치 된 모든 컴퓨터의 동일한 위치에 있으므로 모두 포함할 필요가 없습니다. 매니페스트의 모든 .NET Framework 참조 어셈블리에 대 한 정보입니다.</span><span class="sxs-lookup"><span data-stu-id="d38fd-134">For example, since PresentationFramework.dll can be considered representative of an application built on and for WPF, and since all WPF assemblies exist at the same location on every machine that has the .NET Framework installed, there's no need to include all information on all .NET Framework reference assemblies in the manifests.</span></span>

<a name="Markup_Compilation___Pass_1"></a>

### <a name="markup-compilationpass-1"></a><span data-ttu-id="d38fd-135">태그 컴파일 - 패스 1</span><span class="sxs-lookup"><span data-stu-id="d38fd-135">Markup Compilation—Pass 1</span></span>

<span data-ttu-id="d38fd-136">이 단계에서는 런타임에서 XML 구문 분석 및 속성 값의 유효성을 검사 하지 않도록 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 파일을 구문 분석 하 고 컴파일합니다.</span><span class="sxs-lookup"><span data-stu-id="d38fd-136">In this step, [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] files are parsed and compiled so that the runtime does not spend time parsing XML and validating property values.</span></span> <span data-ttu-id="d38fd-137">컴파일된 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 파일은 사전 토큰화되어 있으므로 런타임 시 이 파일을 로드하면 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 파일을 로드하는 것보다 훨씬 속도가 빨라집니다.</span><span class="sxs-lookup"><span data-stu-id="d38fd-137">The compiled [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] file is pre-tokenized so that, at run time, loading it should be much faster than loading a [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] file.</span></span>

<span data-ttu-id="d38fd-138">이 단계에서 다음 작업은 `Page` 빌드 항목인 모든 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 파일에 대해 수행됩니다.</span><span class="sxs-lookup"><span data-stu-id="d38fd-138">During this step, the following activities take place for every [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] file that is a `Page` build item:</span></span>

1. <span data-ttu-id="d38fd-139">[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 파일은 태그 컴파일러에 의해 구문 분석됩니다.</span><span class="sxs-lookup"><span data-stu-id="d38fd-139">The [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] file is parsed by the markup compiler.</span></span>

2. <span data-ttu-id="d38fd-140">컴파일된 표현은 해당 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]에 대해 만들어져서 obj\Release 폴더에 복사됩니다.</span><span class="sxs-lookup"><span data-stu-id="d38fd-140">A compiled representation is created for that [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] and copied to the obj\Release folder.</span></span>

3. <span data-ttu-id="d38fd-141">새 partial 클래스의 CodeDOM 표현이 만들어져서 obj\Release 폴더에 복사됩니다.</span><span class="sxs-lookup"><span data-stu-id="d38fd-141">A CodeDOM representation of a new partial class is created and copied to the obj\Release folder.</span></span>

<span data-ttu-id="d38fd-142">또한 모든 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 파일에 대해 언어별 코드 파일이 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="d38fd-142">In addition, a language-specific code file is generated for every [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] file.</span></span> <span data-ttu-id="d38fd-143">예를 들어 Visual Basic 프로젝트의 페이지 1. x x x. x x x. x x x. x x x. C# 프로젝트의 Page1.g.cs 페이지에 대해,이 생성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d38fd-143">For example, for a Page1.xaml page in a Visual Basic project, a Page1.g.vb is generated; for a Page1.xaml page in a C# project, a Page1.g.cs is generated.</span></span> <span data-ttu-id="d38fd-144">파일 이름에 ".g"가 있으면 파일이 태그 파일(예: `Page` 또는 `Window`)의 최상위 수준 요소에 대한 partial 클래스 선언을 포함하여 생성된 코드라는 의미입니다.</span><span class="sxs-lookup"><span data-stu-id="d38fd-144">The ".g" in the file name indicates the file is generated code that has a partial class declaration for the top-level element of the markup file (such as `Page` or `Window`).</span></span> <span data-ttu-id="d38fd-145">클래스는 (Visual Basic의`Extends`)의 C# `partial` 한정자를 사용 하 여 선언 되며, 다른 위치에 클래스에 대 한 다른 선언이 있음을 나타내기 위해 일반적으로 코드 Page1.xaml.cs 파일에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d38fd-145">The class is declared with the `partial` modifier in C# (`Extends` in Visual Basic) to indicate there is another declaration for the class elsewhere, usually in the code-behind file Page1.xaml.cs.</span></span>

<span data-ttu-id="d38fd-146">Partial 클래스는 적절 한 기본 클래스 (예: 페이지에 대 한 <xref:System.Windows.Controls.Page>)에서 확장 되 고 <xref:System.Windows.Markup.IComponentConnector?displayProperty=nameWithType> 인터페이스를 구현 합니다.</span><span class="sxs-lookup"><span data-stu-id="d38fd-146">The partial class extends from the appropriate base class (such as <xref:System.Windows.Controls.Page> for a page) and implements the <xref:System.Windows.Markup.IComponentConnector?displayProperty=nameWithType> interface.</span></span> <span data-ttu-id="d38fd-147"><xref:System.Windows.Markup.IComponentConnector> 인터페이스에는 구성 요소를 초기화 하 고 해당 콘텐츠의 요소에 대해 이름 및 이벤트를 연결 하는 메서드가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d38fd-147">The <xref:System.Windows.Markup.IComponentConnector> interface has methods to initialize a component and connect names and events on elements in its content.</span></span> <span data-ttu-id="d38fd-148">결과적으로 생성된 코드 파일에는 다음과 같은 메서드 구현이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d38fd-148">Consequently, the generated code file has a method implementation like the following:</span></span>

```csharp
public void InitializeComponent() {
    if (_contentLoaded) {
        return;
    }
    _contentLoaded = true;
    System.Uri resourceLocater =
        new System.Uri(
            "window1.xaml",
            System.UriKind.RelativeOrAbsolute);
    System.Windows.Application.LoadComponent(this, resourceLocater);
}
```

```vb
Public Sub InitializeComponent() _

    If _contentLoaded Then
        Return
    End If

    _contentLoaded = True
    Dim resourceLocater As System.Uri = _
        New System.Uri("mainwindow.xaml", System.UriKind.Relative)

    System.Windows.Application.LoadComponent(Me, resourceLocater)

End Sub
```

<span data-ttu-id="d38fd-149">기본적으로 태그 컴파일은 MSBuild 엔진과 동일한 <xref:System.AppDomain>에서 실행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d38fd-149">By default, markup compilation runs in the same <xref:System.AppDomain> as the MSBuild engine.</span></span> <span data-ttu-id="d38fd-150">따라서 성능이 크게 향상됩니다.</span><span class="sxs-lookup"><span data-stu-id="d38fd-150">This provides significant performance gains.</span></span> <span data-ttu-id="d38fd-151">이 동작은 `AlwaysCompileMarkupFilesInSeparateDomain` 속성을 통해 전환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d38fd-151">This behavior can be toggled with the `AlwaysCompileMarkupFilesInSeparateDomain` property.</span></span> <span data-ttu-id="d38fd-152">이렇게 하면 별도의 <xref:System.AppDomain>을 언로드하여 모든 참조 어셈블리를 언로드할 이점이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d38fd-152">This has the advantage of unloading all reference assemblies by unloading the separate <xref:System.AppDomain>.</span></span>

<a name="Pass_2_of_Markup_Compilation"></a>

### <a name="markup-compilationpass-2"></a><span data-ttu-id="d38fd-153">태그 컴파일 - 패스 2</span><span class="sxs-lookup"><span data-stu-id="d38fd-153">Markup Compilation—Pass 2</span></span>

<span data-ttu-id="d38fd-154">일부 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 페이지는 태그 컴파일의 패스 1에서 컴파일됩니다.</span><span class="sxs-lookup"><span data-stu-id="d38fd-154">Not all [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] pages are compiled at during pass 1 of markup compilation.</span></span> <span data-ttu-id="d38fd-155">이때 로컬로 정의된 형식 참조(동일한 프로젝트의 코드에서 정의된 형식에 대한 참조)가 있는 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 파일은 컴파일에서 제외됩니다.</span><span class="sxs-lookup"><span data-stu-id="d38fd-155">[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] files that have locally defined type references (references to types defined in code elsewhere in the same project) are exempt from compilation at this time.</span></span> <span data-ttu-id="d38fd-156">이는 로컬로 정의된 형식이 소스에만 있어 아직 컴파일되지 않았기 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="d38fd-156">This is because those locally defined types exist only in source and have not yet been compiled.</span></span> <span data-ttu-id="d38fd-157">이를 확인하기 위해 파서는 추론을 사용하여 태그 파일에서 `x:Name`과 같은 항목을 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="d38fd-157">In order to determine this, the parser uses heuristics that involve looking for items such as `x:Name` in the markup file.</span></span> <span data-ttu-id="d38fd-158">이러한 인스턴스를 찾은 경우 코드 파일이 컴파일될 때까지 해당 태그 파일의 컴파일이 연기되며 나중에 두 번째 태그 컴파일 패스가 이러한 파일을 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="d38fd-158">When such an instance is found, that markup file’s compilation is postponed until the code files have been compiled, after which, the second markup compilation pass processes these files.</span></span>

<a name="File_Classification"></a>

### <a name="file-classification"></a><span data-ttu-id="d38fd-159">파일 분류</span><span class="sxs-lookup"><span data-stu-id="d38fd-159">File Classification</span></span>

<span data-ttu-id="d38fd-160">빌드 프로세스는 출력 파일을 배치할 애플리케이션 어셈블리를 기반으로 다른 리소스 그룹에 출력 파일을 배치합니다.</span><span class="sxs-lookup"><span data-stu-id="d38fd-160">The build process puts output files into different resource groups based on which application assembly they will be placed in.</span></span> <span data-ttu-id="d38fd-161">일반적으로 지역화되지 않은 애플리케이션에서 `Resource`로 표시된 모든 데이터 파일은 주 어셈블리(실행 파일 또는 라이브러리)에 배치됩니다.</span><span class="sxs-lookup"><span data-stu-id="d38fd-161">In a typical nonlocalized application, all data files marked as `Resource` are placed in the main assembly (executable or library).</span></span> <span data-ttu-id="d38fd-162">프로젝트에서 `UICulture`가 설정된 경우 컴파일된 모든 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 파일 및 해당 리소스(특히 언어별로 표시된 리소스)가 위성 리소스 어셈블리에 배치됩니다.</span><span class="sxs-lookup"><span data-stu-id="d38fd-162">When `UICulture` is set in the project, all compiled [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] files and those resources specifically marked as language-specific are placed in the satellite resource assembly.</span></span> <span data-ttu-id="d38fd-163">또한 모든 언어 중립 리소스는 주 어셈블리에 배치됩니다.</span><span class="sxs-lookup"><span data-stu-id="d38fd-163">Furthermore, all language-neutral resources are placed in the main assembly.</span></span> <span data-ttu-id="d38fd-164">빌드 프로세스의 이 단계에서 해당 사항이 결정됩니다.</span><span class="sxs-lookup"><span data-stu-id="d38fd-164">In this step of the build process, that determination is made.</span></span>

<span data-ttu-id="d38fd-165">프로젝트 파일의 `ApplicationDefinition`, `Page` 및 `Resource` 빌드 작업은 `Localizable` 메타데이터(허용 가능한 값은 `true` 및 `false`)를 통해 보강할 수 있으며 이는 파일이 언어와 관련되었는지 또는 언어 중립적인지 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="d38fd-165">The `ApplicationDefinition`, `Page`, and `Resource` build actions in the project file can be augmented with the `Localizable` metadata (acceptable values are `true` and `false`), which dictates whether the file is language-specific or language-neutral.</span></span>

<a name="Core_Compilation"></a>

### <a name="core-compilation"></a><span data-ttu-id="d38fd-166">핵심 컴파일</span><span class="sxs-lookup"><span data-stu-id="d38fd-166">Core Compilation</span></span>

<span data-ttu-id="d38fd-167">핵심 컴파일 단계에서는 코드 파일을 컴파일합니다.</span><span class="sxs-lookup"><span data-stu-id="d38fd-167">The core compile step involves compilation of code files.</span></span> <span data-ttu-id="d38fd-168">이 작업은 언어별 대상 파일 Microsoft.CSharp.targets 및 Microsoft.VisualBasic.targets의 논리에 의해 오케스트레이션됩니다.</span><span class="sxs-lookup"><span data-stu-id="d38fd-168">This is orchestrated by logic in the language-specific targets files Microsoft.CSharp.targets and Microsoft.VisualBasic.targets.</span></span> <span data-ttu-id="d38fd-169">추론을 통해 태그 컴파일러의 단일 패스로 충분하다고 판단된 경우 주 어셈블리가 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="d38fd-169">If heuristics have determined that a single pass of the markup compiler is sufficient, then the main assembly is generated.</span></span> <span data-ttu-id="d38fd-170">그러나 프로젝트에서 하나 이상의 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 파일에 로컬로 정의된 형식에 대한 참조가 있는 경우 태그 컴파일의 두 번째 패스가 완료된 후 최종 애플리케이션 어셈블리가 만들어질 수 있도록 임시 .dll 파일이 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="d38fd-170">However, if one or more [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] files in the project have references to locally defined types, then a temporary .dll file is generated so the final application assemblies may be created after the second pass of markup compilation is complete.</span></span>

<a name="Manifest_generation"></a>

### <a name="manifest-generation"></a><span data-ttu-id="d38fd-171">매니페스트 생성</span><span class="sxs-lookup"><span data-stu-id="d38fd-171">Manifest Generation</span></span>

<span data-ttu-id="d38fd-172">빌드 프로세스가 끝날 때 응용 프로그램 어셈블리와 콘텐츠 파일이 모두 준비 되 면 응용 프로그램에 대 한 ClickOnce 매니페스트가 생성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d38fd-172">At the end of the build process, after all the application assemblies and content files are ready, the ClickOnce manifests for the application are generated.</span></span>

<span data-ttu-id="d38fd-173">배포 매니페스트 파일은 배포 모델, 즉 현재 버전, 업데이트 동작 및 게시자 ID를 디지털 시그니처와 함께 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="d38fd-173">The deployment manifest file describes the deployment model: the current version, update behavior, and publisher identity along with digital signature.</span></span> <span data-ttu-id="d38fd-174">이 매니페스트는 배포를 처리하는 관리자가 작성합니다.</span><span class="sxs-lookup"><span data-stu-id="d38fd-174">This manifest is intended to be authored by administrators who handle deployment.</span></span> <span data-ttu-id="d38fd-175">파일 확장명은 xbap (XAML 브라우저 응용 프로그램 (Xbap)의 경우)이 고, 설치 된 응용 프로그램의 경우 응용 프로그램입니다.</span><span class="sxs-lookup"><span data-stu-id="d38fd-175">The file extension is .xbap (for XAML browser applications (XBAPs)) and .application for installed applications.</span></span> <span data-ttu-id="d38fd-176">.xbap는 `HostInBrowser` 프로젝트 속성에 의해 지정되며 그 결과 매니페스트는 애플리케이션이 브라우저에 호스트되는 것으로 식별합니다.</span><span class="sxs-lookup"><span data-stu-id="d38fd-176">The former is dictated by the `HostInBrowser` project property and as a result the manifest identifies the application as browser-hosted.</span></span>

<span data-ttu-id="d38fd-177">애플리케이션 매니페스트(.exe.manifest 파일)는 애플리케이션 어셈블리 및 종속 라이브러리를 설명하고 애플리케이션에 필요한 사용 권한을 나열합니다.</span><span class="sxs-lookup"><span data-stu-id="d38fd-177">The application manifest (an .exe.manifest file) describes the application assemblies and dependent libraries and lists permissions required by the application.</span></span> <span data-ttu-id="d38fd-178">이 파일은 애플리케이션 개발자가 작성합니다.</span><span class="sxs-lookup"><span data-stu-id="d38fd-178">This file is intended to be authored by the application developer.</span></span> <span data-ttu-id="d38fd-179">ClickOnce 응용 프로그램을 시작 하기 위해 사용자는 응용 프로그램의 배포 매니페스트 파일을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="d38fd-179">In order to launch a ClickOnce application, a user opens the application's deployment manifest file.</span></span>

<span data-ttu-id="d38fd-180">이러한 매니페스트 파일은 항상 Xbap에 대해 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="d38fd-180">These manifest files are always created for XBAPs.</span></span> <span data-ttu-id="d38fd-181">설치된 애플리케이션의 경우 프로젝트 파일에서 `GenerateManifests` 속성 값이 `true`로 지정되지 않는 한 만들어지지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d38fd-181">For installed applications, they are not created unless the `GenerateManifests` property is specified in the project file with value `true`.</span></span>

<span data-ttu-id="d38fd-182">Xbap는 일반적인 인터넷 영역 응용 프로그램에 할당 된 권한 (<xref:System.Security.Permissions.WebBrowserPermission> 및 <xref:System.Security.Permissions.MediaPermission>에 대 한 두 가지 추가 권한을 얻습니다.</span><span class="sxs-lookup"><span data-stu-id="d38fd-182">XBAPs get two additional permissions over and above those permissions assigned to typical Internet zone applications: <xref:System.Security.Permissions.WebBrowserPermission> and <xref:System.Security.Permissions.MediaPermission>.</span></span> <span data-ttu-id="d38fd-183">WPF 빌드 시스템은 응용 프로그램 매니페스트에서 이러한 사용 권한을 선언 합니다.</span><span class="sxs-lookup"><span data-stu-id="d38fd-183">The WPF build system declares those permissions in the application manifest.</span></span>

<a name="Incremental_Build_Support"></a>

## <a name="incremental-build-support"></a><span data-ttu-id="d38fd-184">증분 빌드 지원</span><span class="sxs-lookup"><span data-stu-id="d38fd-184">Incremental Build Support</span></span>

<span data-ttu-id="d38fd-185">WPF 빌드 시스템은 증분 빌드에 대 한 지원을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="d38fd-185">The WPF build system provides support for incremental builds.</span></span> <span data-ttu-id="d38fd-186">태그 또는 코드에 대한 변경 사항을 지능적으로 검색하고 변경 사항의 영향을 받는 아티팩트만 컴파일합니다.</span><span class="sxs-lookup"><span data-stu-id="d38fd-186">It is fairly intelligent about detecting changes made to markup or code, and it compiles only those artifacts affected by the change.</span></span> <span data-ttu-id="d38fd-187">증분 빌드 메커니즘은 다음 파일을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="d38fd-187">The incremental build mechanism uses the following files:</span></span>

- <span data-ttu-id="d38fd-188">현재 컴파일러 상태를 유지 관리하는 $(*AssemblyName*)_MarkupCompiler.Cache 파일</span><span class="sxs-lookup"><span data-stu-id="d38fd-188">An $(*AssemblyName*)_MarkupCompiler.Cache file to maintain current compiler state.</span></span>

- <span data-ttu-id="d38fd-189">로컬로 정의된 형식에 대한 참조가 있는 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 파일을 캐시하는 $(*AssemblyName*) _MarkupCompiler.lref 파일</span><span class="sxs-lookup"><span data-stu-id="d38fd-189">An $(*AssemblyName*)_MarkupCompiler.lref file to cache the [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] files with references to locally defined types.</span></span>

<span data-ttu-id="d38fd-190">다음은 증분 빌드를 제어하는 규칙 집합입니다.</span><span class="sxs-lookup"><span data-stu-id="d38fd-190">The following is a set of rules governing incremental build:</span></span>

- <span data-ttu-id="d38fd-191">파일은 빌드 시스템이 변경을 검색하는 가장 작은 단위입니다.</span><span class="sxs-lookup"><span data-stu-id="d38fd-191">The file is the smallest unit at which the build system detects change.</span></span> <span data-ttu-id="d38fd-192">따라서 코드 파일의 경우 빌드 시스템에서 형식이 변경되었는지 또는 코드가 추가되었는지 확인할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d38fd-192">So, for a code file, the build system cannot tell if a type was changed or if code was added.</span></span> <span data-ttu-id="d38fd-193">이는 프로젝트 파일도 마찬가지입니다.</span><span class="sxs-lookup"><span data-stu-id="d38fd-193">The same holds for project files.</span></span>

- <span data-ttu-id="d38fd-194">증분 빌드 메커니즘은 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 페이지가 클래스를 정의하거나 다른 클래스를 사용한다는 것을 인식해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d38fd-194">The incremental build mechanism must be cognizant that a [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] page either defines a class or uses other classes.</span></span>

- <span data-ttu-id="d38fd-195">`Reference` 항목이 변경된 경우 모든 페이지를 다시 컴파일합니다.</span><span class="sxs-lookup"><span data-stu-id="d38fd-195">If `Reference` entries change, then recompile all pages.</span></span>

- <span data-ttu-id="d38fd-196">코드 파일이 변경되면 로컬로 정의된 형식 참조가 있는 모든 페이지를 다시 컴파일합니다.</span><span class="sxs-lookup"><span data-stu-id="d38fd-196">If a code file changes, recompile all pages with locally defined type references.</span></span>

- <span data-ttu-id="d38fd-197">[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 파일이 변경된 경우:</span><span class="sxs-lookup"><span data-stu-id="d38fd-197">If a [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] file changes:</span></span>

  - <span data-ttu-id="d38fd-198">프로젝트에서 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]이 `Page`로 선언된 경우: [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]에 로컬로 정의된 형식 참조가 없는 경우 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 및 모든 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 페이지를 로컬 참조와 함께 다시 컴파일합니다. [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]에 로컬 참조가 있는 경우 모든 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 페이지를 로컬 참조와 함께 다시 컴파일합니다.</span><span class="sxs-lookup"><span data-stu-id="d38fd-198">If [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] is declared as `Page` in the project: if the [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] does not have locally defined type references, recompile that [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] plus all [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] pages with local references; if the [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] has local references, recompile all [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] pages with local references.</span></span>

  - <span data-ttu-id="d38fd-199">[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 프로젝트에서 `ApplicationDefinition`으로 선언 된 경우: 모든 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 페이지를 다시 컴파일합니다 (원인: 각 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]는 변경 되었을 수 있는 <xref:System.Windows.Application> 형식에 대 한 참조).</span><span class="sxs-lookup"><span data-stu-id="d38fd-199">If [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] is declared as `ApplicationDefinition` in the project: recompile all [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] pages (reason: each [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] has reference to an <xref:System.Windows.Application> type that may have changed).</span></span>

- <span data-ttu-id="d38fd-200">프로젝트 파일에서 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 파일 대신 애플리케이션 정의로 코드 파일을 선언한 경우:</span><span class="sxs-lookup"><span data-stu-id="d38fd-200">If the project file declares a code file as application definition instead of a [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] file:</span></span>

  - <span data-ttu-id="d38fd-201">프로젝트 파일의 `ApplicationClassName` 값이 변경되었는지(새로운 애플리케이션 형식이 있는지) 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="d38fd-201">Check if the `ApplicationClassName` value in the project file has changed (is there a new application type?).</span></span> <span data-ttu-id="d38fd-202">변경된 경우 전체 애플리케이션을 다시 컴파일합니다.</span><span class="sxs-lookup"><span data-stu-id="d38fd-202">If so, recompile the entire application.</span></span>

  - <span data-ttu-id="d38fd-203">변경되지 않은 경우 모든 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 페이지를 로컬 참조와 함께 다시 컴파일합니다.</span><span class="sxs-lookup"><span data-stu-id="d38fd-203">Otherwise, recompile all [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] pages with local references.</span></span>

- <span data-ttu-id="d38fd-204">프로젝트 파일이 변경된 경우: 앞에서 설명한 규칙을 모두 적용하고 다시 컴파일해야 할 항목을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="d38fd-204">If a project file changes: apply all preceding rules and see what needs to be recompiled.</span></span> <span data-ttu-id="d38fd-205">`AssemblyName`, `IntermediateOutputPath`, `RootNamespace` 및 `HostInBrowser` 속성이 변경되면 전체 다시 컴파일됩니다.</span><span class="sxs-lookup"><span data-stu-id="d38fd-205">Changes to the following properties trigger a complete recompile: `AssemblyName`, `IntermediateOutputPath`, `RootNamespace`, and `HostInBrowser`.</span></span>

<span data-ttu-id="d38fd-206">다시 컴파일 작업은 다음과 같은 시나리오로 수행될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d38fd-206">The following recompile scenarios are possible:</span></span>

- <span data-ttu-id="d38fd-207">전체 애플리케이션이 다시 컴파일됩니다.</span><span class="sxs-lookup"><span data-stu-id="d38fd-207">The entire application is recompiled.</span></span>

- <span data-ttu-id="d38fd-208">로컬로 정의된 형식 참조가 있는 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 파일만 다시 컴파일됩니다.</span><span class="sxs-lookup"><span data-stu-id="d38fd-208">Only those [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] files that have locally defined type references are recompiled.</span></span>

- <span data-ttu-id="d38fd-209">모든 항목이 다시 컴파일되지 않습니다(프로젝트의 모든 항목이 변경되지 않음).</span><span class="sxs-lookup"><span data-stu-id="d38fd-209">Nothing is recompiled (if nothing in the project has changed).</span></span>

## <a name="see-also"></a><span data-ttu-id="d38fd-210">참조</span><span class="sxs-lookup"><span data-stu-id="d38fd-210">See also</span></span>

- [<span data-ttu-id="d38fd-211">WPF 애플리케이션 배포</span><span class="sxs-lookup"><span data-stu-id="d38fd-211">Deploying a WPF Application</span></span>](deploying-a-wpf-application-wpf.md)
- [<span data-ttu-id="d38fd-212">WPF MSBuild 참조</span><span class="sxs-lookup"><span data-stu-id="d38fd-212">WPF MSBuild Reference</span></span>](/visualstudio/msbuild/wpf-msbuild-reference)
- [<span data-ttu-id="d38fd-213">WPF의 Pack URI</span><span class="sxs-lookup"><span data-stu-id="d38fd-213">Pack URIs in WPF</span></span>](pack-uris-in-wpf.md)
- [<span data-ttu-id="d38fd-214">WPF 애플리케이션 리소스, 콘텐츠 및 데이터 파일</span><span class="sxs-lookup"><span data-stu-id="d38fd-214">WPF Application Resource, Content, and Data Files</span></span>](wpf-application-resource-content-and-data-files.md)
