---
title: 응용 프로그램 리소스, 콘텐츠 및 데이터 파일
description: Windows Presentation Foundation (WPF)에서 응용 프로그램 데이터 파일을 구성, 식별 및 사용 하기 위한 특별 지원에 대해 알아봅니다.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WPF application [WPF], files
- loose resources [WPF]
- content files [WPF]
- Site of Origin files [WPF]
- resource files [WPF]
- remote files [WPF]
- embedded resources [WPF]
- files [WPF]
- referencing application files [WPF]
- application development [WPF], files
- application management [WPF]
ms.assetid: 7ad2943b-3961-41d3-8fc6-1582d43f5d99
ms.openlocfilehash: 324b3eb922f0fd1d1d9ad00105a06a7fbdb8effd
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/01/2020
ms.locfileid: "85622863"
---
# <a name="wpf-application-resource-content-and-data-files"></a><span data-ttu-id="e32eb-103">WPF 애플리케이션 리소스, 콘텐츠 및 데이터 파일</span><span class="sxs-lookup"><span data-stu-id="e32eb-103">WPF Application Resource, Content, and Data Files</span></span>
<span data-ttu-id="e32eb-104">Microsoft Windows 응용 프로그램은 종종 [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] 이미지, 비디오, 오디오 등의 실행 불가능 한 데이터를 포함 하는 파일에 의존 합니다.</span><span class="sxs-lookup"><span data-stu-id="e32eb-104">Microsoft Windows applications often depend on files that contain non-executable data, such as [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)], images, video, and audio.</span></span> <span data-ttu-id="e32eb-105">WPF (Windows Presentation Foundation)는 응용 프로그램 데이터 파일 이라고 하는 이러한 유형의 데이터 파일을 구성 하 고, 식별 하 고, 사용할 수 있는 특별 한 지원을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="e32eb-105">Windows Presentation Foundation (WPF) offers special support for configuring, identifying, and using these types of data files, which are called application data files.</span></span> <span data-ttu-id="e32eb-106">이러한 지원에는 다음을 포함한 특정 애플리케이션 데이터 파일 형식 집합이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="e32eb-106">This support revolves around a specific set of application data file types, including:</span></span>  
  
- <span data-ttu-id="e32eb-107">**리소스 파일**: 실행 파일이 나 라이브러리 WPF 어셈블리로 컴파일되는 데이터 파일입니다.</span><span class="sxs-lookup"><span data-stu-id="e32eb-107">**Resource Files**: Data files that are compiled into either an executable or library WPF assembly.</span></span>  
  
- <span data-ttu-id="e32eb-108">**콘텐츠 파일**: 실행 가능 WPF 어셈블리와 명시적으로 연결 된 독립 실행형 데이터 파일입니다.</span><span class="sxs-lookup"><span data-stu-id="e32eb-108">**Content Files**: Standalone data files that have an explicit association with an executable WPF assembly.</span></span>  
  
- <span data-ttu-id="e32eb-109">**원본 사이트 파일**: 실행 가능 WPF 어셈블리와 연결 되지 않은 독립 실행형 데이터 파일입니다.</span><span class="sxs-lookup"><span data-stu-id="e32eb-109">**Site of Origin Files**: Standalone data files that have no association with an executable WPF assembly.</span></span>  
  
 <span data-ttu-id="e32eb-110">이 세 가지 파일 형식을 구분하는 한 가지 중요한 차이점은 리소스 파일과 콘텐츠 파일은 빌드할 때 인식된다는 점입니다. 어셈블리는 명시적으로 이 파일을 인식합니다.</span><span class="sxs-lookup"><span data-stu-id="e32eb-110">One important distinction to make between these three types of files is that resource files and content files are known at build time; an assembly has explicit knowledge of them.</span></span> <span data-ttu-id="e32eb-111">그러나 원본 사이트 파일의 경우 어셈블리에 대 한 지식이 없거나 pack URI (uniform resource identifier) 참조를 통한 암시적 지식이 있을 수 있습니다. 후자의 경우 참조 된 원본 파일 파일이 실제로 존재 한다는 보장이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="e32eb-111">For site of origin files, however, an assembly may have no knowledge of them at all, or implicit knowledge through a pack uniform resource identifier (URI) reference; the case of the latter, there is no guarantee that the referenced site of origin file actually exists.</span></span>  
  
 <span data-ttu-id="e32eb-112">응용 프로그램 데이터 파일을 참조 하기 위해 Windows Presentation Foundation (WPF)는 Pack URI (uniform resource identifier)를 사용 합니다 .이 스키마는 [wpf의 Pack uri](pack-uris-in-wpf.md)에 자세히 설명 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e32eb-112">To reference application data files, Windows Presentation Foundation (WPF) uses the Pack uniform resource identifier (URI) Scheme, which is described in detail in [Pack URIs in WPF](pack-uris-in-wpf.md)).</span></span>  
  
 <span data-ttu-id="e32eb-113">이 항목에서는 애플리케이션 데이터 파일을 구성하고 사용하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="e32eb-113">This topic describes how to configure and use application data files.</span></span>  

<a name="Resource_Files"></a>
## <a name="resource-files"></a><span data-ttu-id="e32eb-114">리소스 파일</span><span class="sxs-lookup"><span data-stu-id="e32eb-114">Resource Files</span></span>  
 <span data-ttu-id="e32eb-115">애플리케이션에서 애플리케이션 데이터 파일을 항상 사용할 수 있어야 하는 경우 가용성을 보장하는 유일한 방법은 데이터 파일을 애플리케이션의 주 실행 어셈블리 또는 참조되는 어셈블리 중 하나로 컴파일하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="e32eb-115">If an application data file must always be available to an application, the only way to guarantee availability is to compile it into an application's main executable assembly or one of its referenced assemblies.</span></span> <span data-ttu-id="e32eb-116">이 유형의 응용 프로그램 데이터 파일을 *리소스 파일*이라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="e32eb-116">This type of application data file is known as a *resource file*.</span></span>  
  
 <span data-ttu-id="e32eb-117">다음과 같은 경우에 리소스 파일을 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e32eb-117">You should use resource files when:</span></span>  
  
- <span data-ttu-id="e32eb-118">어셈블리로 컴파일한 뒤에는 리소스 파일의 콘텐츠를 업데이트할 필요가 없는 경우.</span><span class="sxs-lookup"><span data-stu-id="e32eb-118">You don't need to update the resource file's content after it is compiled into an assembly.</span></span>  
  
- <span data-ttu-id="e32eb-119">파일 종속성의 수를 줄여 애플리케이션 배포의 복잡성을 줄이려는 경우.</span><span class="sxs-lookup"><span data-stu-id="e32eb-119">You want to simplify application distribution complexity by reducing the number of file dependencies.</span></span>  
  
- <span data-ttu-id="e32eb-120">응용 프로그램 데이터 파일을 지역화할 수 있어야 합니다 ( [WPF 세계화 및 지역화 개요](../advanced/wpf-globalization-and-localization-overview.md)참조).</span><span class="sxs-lookup"><span data-stu-id="e32eb-120">Your application data file needs to be localizable (see [WPF Globalization and Localization Overview](../advanced/wpf-globalization-and-localization-overview.md)).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="e32eb-121">이 섹션에서 설명 하는 리소스 파일은 [XAML 리소스](../../../desktop-wpf/fundamentals/xaml-resources-define.md) 에 설명 된 리소스 파일과 다르며 [응용 프로그램 리소스 관리 (.net)](/visualstudio/ide/managing-application-resources-dotnet)에 설명 된 포함 된 리소스 또는 링크 된 리소스와 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="e32eb-121">The resource files described in this section are different than the resource files described in [XAML Resources](../../../desktop-wpf/fundamentals/xaml-resources-define.md) and different than the embedded or linked resources described in [Manage Application Resources (.NET)](/visualstudio/ide/managing-application-resources-dotnet).</span></span>  
  
### <a name="configuring-resource-files"></a><span data-ttu-id="e32eb-122">리소스 파일 구성</span><span class="sxs-lookup"><span data-stu-id="e32eb-122">Configuring Resource Files</span></span>  
 <span data-ttu-id="e32eb-123">WPF에서 리소스 파일은 MSBuild (Microsoft build engine) 프로젝트에 항목으로 포함 되는 파일입니다 `Resource` .</span><span class="sxs-lookup"><span data-stu-id="e32eb-123">In WPF, a resource file is a file that is included in an Microsoft build engine (MSBuild) project as a `Resource` item.</span></span>  
  
```xml  
<Project xmlns="http://schemas.microsoft.com/developer/msbuild/2003" ... >  
  ...  
  <ItemGroup>  
    <Resource Include="ResourceFile.xaml" />  
  </ItemGroup>  
  ...  
</Project>  
```  
  
> [!NOTE]
> <span data-ttu-id="e32eb-124">Visual Studio에서는 프로젝트에 파일을 추가 하 고를로 설정 하 여 리소스 파일을 만듭니다 `Build Action` `Resource` .</span><span class="sxs-lookup"><span data-stu-id="e32eb-124">In Visual Studio, you create a resource file by adding a file to a project and setting its `Build Action` to `Resource`.</span></span>  
  
 <span data-ttu-id="e32eb-125">프로젝트가 빌드되면 MSBuild는 리소스를 어셈블리로 컴파일합니다.</span><span class="sxs-lookup"><span data-stu-id="e32eb-125">When the project is built, MSBuild compiles the resource into the assembly.</span></span>  
  
### <a name="using-resource-files"></a><span data-ttu-id="e32eb-126">리소스 파일 사용</span><span class="sxs-lookup"><span data-stu-id="e32eb-126">Using Resource Files</span></span>  
 <span data-ttu-id="e32eb-127">리소스 파일을 로드 하기 위해 <xref:System.Windows.Application.GetResourceStream%2A> <xref:System.Windows.Application> 원하는 리소스 파일을 식별 하는 pack URI를 전달 하 여 클래스의 메서드를 호출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e32eb-127">To load a resource file, you can call the <xref:System.Windows.Application.GetResourceStream%2A> method of the <xref:System.Windows.Application> class, passing a pack URI that identifies the desired resource file.</span></span> <span data-ttu-id="e32eb-128"><xref:System.Windows.Application.GetResourceStream%2A><xref:System.Windows.Resources.StreamResourceInfo>리소스 파일을로 노출 하 <xref:System.IO.Stream> 고 해당 콘텐츠 형식을 설명 하는 개체를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="e32eb-128"><xref:System.Windows.Application.GetResourceStream%2A> returns a <xref:System.Windows.Resources.StreamResourceInfo> object, which exposes the resource file as a <xref:System.IO.Stream> and describes its content type.</span></span>  
  
 <span data-ttu-id="e32eb-129">예를 들어 다음 코드에서는를 사용 하 여 <xref:System.Windows.Application.GetResourceStream%2A> 리소스 파일을 로드 하 <xref:System.Windows.Controls.Page> 고이를 ()의 콘텐츠로 설정 하는 방법을 보여 줍니다 <xref:System.Windows.Controls.Frame> `pageFrame` .</span><span class="sxs-lookup"><span data-stu-id="e32eb-129">As an example, the following code shows how to use <xref:System.Windows.Application.GetResourceStream%2A> to load a <xref:System.Windows.Controls.Page> resource file and set it as the content of a <xref:System.Windows.Controls.Frame> (`pageFrame`):</span></span>  
  
 [!code-csharp[WPFAssemblyResourcesSnippets#LoadAPageResourceFileManuallyCODE](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/CSharp/ResourcesSample/ApplicationGetResourceStreamSnippetWindow.xaml.cs#loadapageresourcefilemanuallycode)]
 [!code-vb[WPFAssemblyResourcesSnippets#LoadAPageResourceFileManuallyCODE](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/VisualBasic/ResourcesSample/ApplicationGetResourceStreamSnippetWindow.xaml.vb#loadapageresourcefilemanuallycode)]  
  
 <span data-ttu-id="e32eb-130">를 호출 하는 동안에 대 한 액세스를 제공 하는 동안를 사용 하 여 <xref:System.Windows.Application.GetResourceStream%2A> <xref:System.IO.Stream> 설정할 속성의 형식으로 변환 하는 작업을 추가로 수행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e32eb-130">While calling <xref:System.Windows.Application.GetResourceStream%2A> gives you access to the <xref:System.IO.Stream>, you need to perform the additional work of converting it to the type of the property that you'll be setting it with.</span></span> <span data-ttu-id="e32eb-131">대신, <xref:System.IO.Stream> 코드를 사용 하 여 리소스 파일을 형식의 속성에 직접 로드 하 여 WPF가를 열고 변환 하도록 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e32eb-131">Instead, you can let WPF take care of opening and converting the <xref:System.IO.Stream> by loading a resource file directly into the property of a type using code.</span></span>  
  
 <span data-ttu-id="e32eb-132">다음 예제에서는 <xref:System.Windows.Controls.Page> <xref:System.Windows.Controls.Frame> 코드를 사용 하 여를 ()으로 직접 로드 하는 방법을 보여 줍니다 `pageFrame` .</span><span class="sxs-lookup"><span data-stu-id="e32eb-132">The following example shows how to load a <xref:System.Windows.Controls.Page> directly into a <xref:System.Windows.Controls.Frame> (`pageFrame`) using code.</span></span>  
  
 [!code-csharp[WPFAssemblyResourcesSnippets#LoadPageResourceFileFromCODE](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/CSharp/ResourcesSample/ApplicationGetResourceStreamSnippetWindow.xaml.cs#loadpageresourcefilefromcode)]
 [!code-vb[WPFAssemblyResourcesSnippets#LoadPageResourceFileFromCODE](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/VisualBasic/ResourcesSample/ApplicationGetResourceStreamSnippetWindow.xaml.vb#loadpageresourcefilefromcode)]  
  
 <span data-ttu-id="e32eb-133">다음 예제는 태그를 사용하여 앞의 예제를 구현한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="e32eb-133">The following example is the markup equivalent of the preceding example.</span></span>  
  
 [!code-xaml[WPFAssemblyResourcesSnippets#LoadPageResourceFileFromXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/CSharp/ResourcesSample/ApplicationGetResourceStreamSnippetWindow.xaml#loadpageresourcefilefromxaml)]  
  
### <a name="application-code-files-as-resource-files"></a><span data-ttu-id="e32eb-134">리소스 파일로 사용되는 애플리케이션 코드 파일</span><span class="sxs-lookup"><span data-stu-id="e32eb-134">Application Code Files as Resource Files</span></span>  
 <span data-ttu-id="e32eb-135">Windows, 페이지, 유동 문서 및 리소스 사전을 비롯 한 pack Uri를 사용 하 여 특별 한 WPF 응용 프로그램 코드 파일 집합을 참조할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e32eb-135">A special set of WPF application code files can be referenced using pack URIs, including windows, pages, flow documents, and resource dictionaries.</span></span> <span data-ttu-id="e32eb-136">예를 들어 <xref:System.Windows.Application.StartupUri%2A?displayProperty=nameWithType> 응용 프로그램이 시작 될 때 로드 하려는 창이 나 페이지를 참조 하는 PACK URI를 사용 하 여 속성을 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e32eb-136">For example, you can set the <xref:System.Windows.Application.StartupUri%2A?displayProperty=nameWithType> property with a pack URI that references the window or page that you would like to load when an application starts.</span></span>  
  
 [!code-xaml[WPFAssemblyResourcesSnippets#SetApplicationStartupURI](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/CSharp/ResourcesSample/App.xaml#setapplicationstartupuri)]  
  
 <span data-ttu-id="e32eb-137">XAML 파일이 항목으로 MSBuild 프로젝트에 포함 되는 경우이 작업을 수행할 수 있습니다 `Page` .</span><span class="sxs-lookup"><span data-stu-id="e32eb-137">You can do this when a XAML file is included in an MSBuild project as a `Page` item.</span></span>  
  
```xml  
<Project xmlns="http://schemas.microsoft.com/developer/msbuild/2003" ... >  
  ...  
  <ItemGroup>  
    <Page Include="MainWindow.xaml" />  
  </ItemGroup>  
  ...  
</Project>  
```  
  
> [!NOTE]
> <span data-ttu-id="e32eb-138">Visual Studio에서 새 <xref:System.Windows.Window> ,, <xref:System.Windows.Navigation.NavigationWindow> <xref:System.Windows.Controls.Page> , <xref:System.Windows.Documents.FlowDocument> 또는를 프로젝트에 추가 하면 <xref:System.Windows.ResourceDictionary> `Build Action` 마크업 파일에 대 한가 기본적으로로 바뀝니다 `Page` .</span><span class="sxs-lookup"><span data-stu-id="e32eb-138">In Visual Studio, you add a new <xref:System.Windows.Window>, <xref:System.Windows.Navigation.NavigationWindow>, <xref:System.Windows.Controls.Page>, <xref:System.Windows.Documents.FlowDocument>, or <xref:System.Windows.ResourceDictionary> to a project, the `Build Action` for the markup file will default to `Page`.</span></span>  
  
 <span data-ttu-id="e32eb-139">항목이 있는 프로젝트를 `Page` 컴파일하면 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 항목이 이진 형식으로 변환 되 고 연결 된 어셈블리로 컴파일됩니다.</span><span class="sxs-lookup"><span data-stu-id="e32eb-139">When a project with `Page` items is compiled, the [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] items are converted to binary format and compiled into the associated assembly.</span></span> <span data-ttu-id="e32eb-140">결과적으로 이 파일을 일반적인 리소스 파일과 같은 방법으로 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e32eb-140">Consequently, these files can be used in the same way as typical resource files.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="e32eb-141">[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]파일이 항목으로 구성 되 `Resource` 고 코드 숨김으로 구성 되지 않은 경우 raw는 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 이진 버전의 raw가 아닌 어셈블리로 컴파일됩니다 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="e32eb-141">If a [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] file is configured as a `Resource` item, and does not have a code-behind file, the raw [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] is compiled into an assembly rather than a binary version of the raw [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)].</span></span>  
  
<a name="Content_Files"></a>
## <a name="content-files"></a><span data-ttu-id="e32eb-142">콘텐츠 파일</span><span class="sxs-lookup"><span data-stu-id="e32eb-142">Content Files</span></span>  
 <span data-ttu-id="e32eb-143">*콘텐츠 파일* 은 실행 가능한 어셈블리와 함께 느슨한 파일로 배포 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e32eb-143">A *content file* is distributed as a loose file alongside an executable assembly.</span></span> <span data-ttu-id="e32eb-144">어셈블리로 컴파일되지는 않지만 어셈블리는 각 콘텐츠 파일과 연결되는 메타데이터와 함께 컴파일됩니다.</span><span class="sxs-lookup"><span data-stu-id="e32eb-144">Although they are not compiled into an assembly, assemblies are compiled with metadata that establishes an association with each content file.</span></span>  
  
 <span data-ttu-id="e32eb-145">데이터 파일을 사용하는 어셈블리를 재컴파일하지 않고 업데이트하고자 하는 애플리케이션 데이터 파일을 애플리케이션에서 필요로 할 때는 콘텐츠 파일을 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e32eb-145">You should use content files when your application requires a specific set of application data files that you want to be able to update without recompiling the assembly that consumes them.</span></span>  
  
### <a name="configuring-content-files"></a><span data-ttu-id="e32eb-146">콘텐츠 파일 구성</span><span class="sxs-lookup"><span data-stu-id="e32eb-146">Configuring Content Files</span></span>  
 <span data-ttu-id="e32eb-147">프로젝트에 콘텐츠 파일을 추가 하려면 응용 프로그램 데이터 파일을 항목으로 포함 해야 합니다 `Content` .</span><span class="sxs-lookup"><span data-stu-id="e32eb-147">To add a content file to a project, an application data file must be included as a `Content` item.</span></span> <span data-ttu-id="e32eb-148">또한 콘텐츠 파일이 어셈블리로 직접 컴파일되지 않으므로 MSBuild 메타 데이터 요소를 설정 하 여 `CopyToOutputDirectory` 콘텐츠 파일이 빌드된 어셈블리에 상대적인 위치로 복사 되도록 지정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e32eb-148">Furthermore, because a content file is not compiled directly into the assembly, you need to set the MSBuild `CopyToOutputDirectory` metadata element to specify that the content file is copied to a location that is relative to the built assembly.</span></span> <span data-ttu-id="e32eb-149">프로젝트를 빌드할 때마다 리소스를 빌드 출력 폴더로 복사 하려면 `CopyToOutputDirectory` 메타 데이터 요소를 값으로 설정 `Always` 합니다.</span><span class="sxs-lookup"><span data-stu-id="e32eb-149">If you want the resource to be copied to the build output folder every time a project is built, you set the `CopyToOutputDirectory` metadata element with the `Always` value.</span></span> <span data-ttu-id="e32eb-150">그렇지 않으면 값을 사용 하 여 최신 버전의 리소스만 빌드 출력 폴더에 복사 되도록 할 수 있습니다 `PreserveNewest` .</span><span class="sxs-lookup"><span data-stu-id="e32eb-150">Otherwise, you can ensure that only the newest version of the resource is copied to the build output folder by using the `PreserveNewest` value.</span></span>  
  
 <span data-ttu-id="e32eb-151">다음 예제에서는 리소스의 새 버전이 프로젝트에 추가된 경우에만 콘텐츠 파일이 빌드 출력 폴더에 복사되는 방식으로 구성된 파일을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="e32eb-151">The following shows a file that is configured as a content file which is copied to the build output folder only when a new version of the resource is added to the project.</span></span>  
  
```xml  
<Project xmlns="http://schemas.microsoft.com/developer/msbuild/2003" ... >  
  ...  
  <ItemGroup>  
    <Content Include="ContentFile.xaml">  
      <CopyToOutputDirectory>PreserveNewest</CopyToOutputDirectory>  
    </Content>  
  </ItemGroup>  
  ...  
</Project>  
```  
  
> [!NOTE]
> <span data-ttu-id="e32eb-152">Visual Studio에서는 프로젝트에 파일을 추가 하 고를로 설정 하 여 콘텐츠 파일을 만들고,를로 설정 하 고 `Build Action` (와 같음)를로 `Content` 설정 `Copy to Output Directory` `Copy always` `Always` `Copy if newer` `PreserveNewest` 합니다.</span><span class="sxs-lookup"><span data-stu-id="e32eb-152">In Visual Studio, you create a content file by adding a file to a project and setting its `Build Action` to `Content`, and set its `Copy to Output Directory` to `Copy always` (same as `Always`) and `Copy if newer` (same as `PreserveNewest`).</span></span>  
  
 <span data-ttu-id="e32eb-153">프로젝트를 빌드할 때 <xref:System.Windows.Resources.AssemblyAssociatedContentFileAttribute> 특성은 각 콘텐츠 파일에 대 한 어셈블리의 메타 데이터로 컴파일됩니다.</span><span class="sxs-lookup"><span data-stu-id="e32eb-153">When the project is built, an <xref:System.Windows.Resources.AssemblyAssociatedContentFileAttribute> attribute is compiled into the metadata of the assembly for each content file.</span></span>  
  
 `[assembly: AssemblyAssociatedContentFile("ContentFile.xaml")]`  
  
 <span data-ttu-id="e32eb-154">값은 <xref:System.Windows.Resources.AssemblyAssociatedContentFileAttribute> 프로젝트의 위치를 기준으로 콘텐츠 파일의 경로를 암시 합니다.</span><span class="sxs-lookup"><span data-stu-id="e32eb-154">The value of the <xref:System.Windows.Resources.AssemblyAssociatedContentFileAttribute> implies the path to the content file relative to its position in the project.</span></span> <span data-ttu-id="e32eb-155">예를 들어 콘텐츠 파일이 프로젝트 하위 폴더에 있는 경우 추가 경로 정보가 값에 통합 됩니다 <xref:System.Windows.Resources.AssemblyAssociatedContentFileAttribute> .</span><span class="sxs-lookup"><span data-stu-id="e32eb-155">For example, if a content file was located in a project subfolder, the additional path information would be incorporated into the <xref:System.Windows.Resources.AssemblyAssociatedContentFileAttribute> value.</span></span>  
  
 `[assembly: AssemblyAssociatedContentFile("Resources/ContentFile.xaml")]`  
  
 <span data-ttu-id="e32eb-156"><xref:System.Windows.Resources.AssemblyAssociatedContentFileAttribute>값은 빌드 출력 폴더의 콘텐츠 파일에 대 한 경로 값 이기도 합니다.</span><span class="sxs-lookup"><span data-stu-id="e32eb-156">The <xref:System.Windows.Resources.AssemblyAssociatedContentFileAttribute> value is also the value of the path to the content file in the build output folder.</span></span>  
  
### <a name="using-content-files"></a><span data-ttu-id="e32eb-157">콘텐츠 파일 사용</span><span class="sxs-lookup"><span data-stu-id="e32eb-157">Using Content Files</span></span>  
 <span data-ttu-id="e32eb-158">콘텐츠 파일을 로드 하려면 클래스의 메서드를 호출 하 여 <xref:System.Windows.Application.GetContentStream%2A> <xref:System.Windows.Application> 원하는 콘텐츠 파일을 식별 하는 pack URI를 전달 합니다.</span><span class="sxs-lookup"><span data-stu-id="e32eb-158">To load a content file, you can call the <xref:System.Windows.Application.GetContentStream%2A> method of the <xref:System.Windows.Application> class, passing a pack URI that identifies the desired content file.</span></span> <span data-ttu-id="e32eb-159"><xref:System.Windows.Application.GetContentStream%2A><xref:System.Windows.Resources.StreamResourceInfo>콘텐츠 파일을로 노출 하 <xref:System.IO.Stream> 고 해당 콘텐츠 형식을 설명 하는 개체를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="e32eb-159"><xref:System.Windows.Application.GetContentStream%2A> returns a <xref:System.Windows.Resources.StreamResourceInfo> object, which exposes the content file as a <xref:System.IO.Stream> and describes its content type.</span></span>  
  
 <span data-ttu-id="e32eb-160">예를 들어 다음 코드에서는를 사용 하 여 <xref:System.Windows.Application.GetContentStream%2A> 콘텐츠 파일을 로드 하 <xref:System.Windows.Controls.Page> 고이를 ()의 콘텐츠로 설정 하는 방법을 보여 줍니다 <xref:System.Windows.Controls.Frame> `pageFrame` .</span><span class="sxs-lookup"><span data-stu-id="e32eb-160">As an example, the following code shows how to use <xref:System.Windows.Application.GetContentStream%2A> to load a <xref:System.Windows.Controls.Page> content file and set it as the content of a <xref:System.Windows.Controls.Frame> (`pageFrame`).</span></span>  
  
 [!code-csharp[WPFAssemblyResourcesSnippets#LoadAPageContentFileManuallyCODE](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/CSharp/ResourcesSample/ApplicationGetContentStreamSnippetWindow.xaml.cs#loadapagecontentfilemanuallycode)]
 [!code-vb[WPFAssemblyResourcesSnippets#LoadAPageContentFileManuallyCODE](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/VisualBasic/ResourcesSample/ApplicationGetContentStreamSnippetWindow.xaml.vb#loadapagecontentfilemanuallycode)]  
  
 <span data-ttu-id="e32eb-161">를 호출 하는 동안에 대 한 액세스를 제공 하는 동안를 사용 하 여 <xref:System.Windows.Application.GetContentStream%2A> <xref:System.IO.Stream> 설정할 속성의 형식으로 변환 하는 작업을 추가로 수행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e32eb-161">While calling <xref:System.Windows.Application.GetContentStream%2A> gives you access to the <xref:System.IO.Stream>, you need to perform the additional work of converting it to the type of the property that you'll be setting it with.</span></span> <span data-ttu-id="e32eb-162">대신, <xref:System.IO.Stream> 코드를 사용 하 여 리소스 파일을 형식의 속성에 직접 로드 하 여 WPF가를 열고 변환 하도록 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e32eb-162">Instead, you can let WPF take care of opening and converting the <xref:System.IO.Stream> by loading a resource file directly into the property of a type using code.</span></span>  
  
 <span data-ttu-id="e32eb-163">다음 예제에서는 <xref:System.Windows.Controls.Page> <xref:System.Windows.Controls.Frame> 코드를 사용 하 여를 ()으로 직접 로드 하는 방법을 보여 줍니다 `pageFrame` .</span><span class="sxs-lookup"><span data-stu-id="e32eb-163">The following example shows how to load a <xref:System.Windows.Controls.Page> directly into a <xref:System.Windows.Controls.Frame> (`pageFrame`) using code.</span></span>  
  
 [!code-csharp[WPFAssemblyResourcesSnippets#LoadPageContentFileFromCODE](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/CSharp/ResourcesSample/ApplicationGetContentStreamSnippetWindow.xaml.cs#loadpagecontentfilefromcode)]
 [!code-vb[WPFAssemblyResourcesSnippets#LoadPageContentFileFromCODE](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/VisualBasic/ResourcesSample/ApplicationGetContentStreamSnippetWindow.xaml.vb#loadpagecontentfilefromcode)]  
  
 <span data-ttu-id="e32eb-164">다음 예제는 태그를 사용하여 앞의 예제를 구현한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="e32eb-164">The following example is the markup equivalent of the preceding example.</span></span>  
  
 [!code-xaml[WPFAssemblyResourcesSnippets#LoadPageContentFileFromXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/CSharp/ResourcesSample/ApplicationGetContentStreamSnippetWindow.xaml#loadpagecontentfilefromxaml)]  
  
<a name="Site_of_Origin_Files"></a>
## <a name="site-of-origin-files"></a><span data-ttu-id="e32eb-165">원본 사이트 파일</span><span class="sxs-lookup"><span data-stu-id="e32eb-165">Site of Origin Files</span></span>  
 <span data-ttu-id="e32eb-166">리소스 파일은에서 정의한 대로 함께 배포 되는 어셈블리와 명시적으로 관계가 있습니다 <xref:System.Windows.Resources.AssemblyAssociatedContentFileAttribute> .</span><span class="sxs-lookup"><span data-stu-id="e32eb-166">Resource files have an explicit relationship with the assemblies that they are distributed alongside, as defined by the <xref:System.Windows.Resources.AssemblyAssociatedContentFileAttribute>.</span></span> <span data-ttu-id="e32eb-167">하지만 다음과 같이 어셈블리와 애플리케이션 데이터 파일 사이에 암시적 관계 또는 존재하지 않는 관계를 설정해야 할 경우가 종종 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e32eb-167">But, there are times when you may want to establish either an implicit or non-existent relationship between an assembly and an application data file, including when:</span></span>  
  
- <span data-ttu-id="e32eb-168">파일은 컴파일 시간에 존재 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e32eb-168">A file doesn't exist at compile time.</span></span>  
  
- <span data-ttu-id="e32eb-169">런타임까지 어셈블리에 필요한 파일을 모르는 경우.</span><span class="sxs-lookup"><span data-stu-id="e32eb-169">You don't know what files your assembly will require until run time.</span></span>  
  
- <span data-ttu-id="e32eb-170">연결된 어셈블리를 재컴파일하지 않고 파일을 업데이트할 수 있어야 하는 경우.</span><span class="sxs-lookup"><span data-stu-id="e32eb-170">You want to be able to update files without recompiling the assembly that they are associated with.</span></span>  
  
- <span data-ttu-id="e32eb-171">애플리케이션에서 오디오나 비디오와 같은 대용량 데이터 파일을 사용하며 사용자가 필요할 때에만 이를 다운로드하도록 하려는 경우.</span><span class="sxs-lookup"><span data-stu-id="e32eb-171">Your application uses large data files, such as audio and video, and you only want users to download them if they choose to.</span></span>  
  
 <span data-ttu-id="e32eb-172">및 스키마와 같은 기존 URI 체계를 사용 하 여 이러한 형식의 파일을 로드할 수 있습니다 `file:///` `http://` .</span><span class="sxs-lookup"><span data-stu-id="e32eb-172">It is possible to load these types of files by using traditional URI schemes, such as the `file:///` and `http://` schemes.</span></span>  
  
 [!code-xaml[WPFAssemblyResourcesSnippets#AbsolutePackUriFileHttpReferenceXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/CSharp/ResourcesSample/AbsolutePackUriPage.xaml#absolutepackurifilehttpreferencexaml)]  
  
 <span data-ttu-id="e32eb-173">그러나 `file:///` 및 스키마를 `http://` 사용할 경우 응용 프로그램에 완전 신뢰가 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="e32eb-173">However, the `file:///` and `http://` schemes require your application to have full trust.</span></span> <span data-ttu-id="e32eb-174">응용 프로그램이 인터넷 또는 인트라넷에서 시작 된 XBAP (XAML 브라우저 응용 프로그램)이 고, 해당 위치에서 시작 된 응용 프로그램에 허용 되는 사용 권한 집합만 요청 하는 경우 느슨한 파일은 응용 프로그램의 원본 사이트 (시작 위치) 에서만 로드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e32eb-174">If your application is a XAML browser application (XBAP) that was launched from the Internet or intranet, and it requests only the set of permissions that are allowed for applications launched from those locations, loose files can only be loaded from the application's site of origin (launch location).</span></span> <span data-ttu-id="e32eb-175">이러한 파일은 *원본 사이트* 파일 이라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="e32eb-175">Such files are known as *site of origin* files.</span></span>  
  
 <span data-ttu-id="e32eb-176">원본 사이트 파일이 부분 신뢰 애플리케이션에서만 사용되는 것은 아니지만 부분 신뢰 애플리케이션에서는 원본 사이트 파일만을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e32eb-176">Site of origin files are the only option for partial trust applications, although are not limited to partial trust applications.</span></span> <span data-ttu-id="e32eb-177">완전 신뢰 애플리케이션의 경우에서도 빌드할 때 인식하지 못한 애플리케이션 데이터 파일을 로드해야 할 경우가 있습니다. 완전 신뢰 애플리케이션은 file:///을 사용할 수 있지만 이 경우 애플리케이션 데이터 파일이 애플리케이션 어셈블리와 같은 폴더 또는 하위 폴더에 설치될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e32eb-177">Full trust applications may still need to load application data files that they do not know about at build time; while full trust applications could use file:///, it is likely that the application data files will be installed in the same folder as, or a subfolder of, the application assembly.</span></span> <span data-ttu-id="e32eb-178">file:///에는 파일의 전체 경로를 사용해야 하기 때문에 file:///을 사용하는 방법보다 원본 사이트 참조를 사용하는 방법이 쉽습니다.</span><span class="sxs-lookup"><span data-stu-id="e32eb-178">In this case, using site of origin referencing is easier than using file:///, because using file:/// requires you to work out the full path the file.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="e32eb-179">원본 사이트 파일은 클라이언트 컴퓨터의 XBAP (XAML 브라우저 응용 프로그램)를 사용 하 여 캐시 되지 않지만 콘텐츠 파일은입니다.</span><span class="sxs-lookup"><span data-stu-id="e32eb-179">Site of origin files are not cached with an XAML browser application (XBAP) on a client machine, while content files are.</span></span> <span data-ttu-id="e32eb-180">따라서 구체적으로 요청된 경우에만 다운로드됩니다.</span><span class="sxs-lookup"><span data-stu-id="e32eb-180">Consequently, they are only downloaded when specifically requested.</span></span> <span data-ttu-id="e32eb-181">XBAP (XAML 브라우저 응용 프로그램) 응용 프로그램에 큰 미디어 파일이 있는 경우 이러한 파일을 원본 사이트로 구성 하면 초기 응용 프로그램 시작 속도가 훨씬 빨라지고 요청 시에만 파일이 다운로드 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e32eb-181">If an XAML browser application (XBAP) application has large media files, configuring them as site of origin files means the initial application launch is much faster, and the files are only downloaded on demand.</span></span>  
  
### <a name="configuring-site-of-origin-files"></a><span data-ttu-id="e32eb-182">원본 사이트 파일 구성</span><span class="sxs-lookup"><span data-stu-id="e32eb-182">Configuring Site of Origin Files</span></span>  
 <span data-ttu-id="e32eb-183">원본 사이트 파일이 없거나 컴파일할 때 알 수 없는 경우 명령줄 프로그램 또는 Microsoft Windows Installer를 사용 하는 등의 방법으로 필요한 파일을 런타임에 사용할 수 있도록 하기 위해 기존 배포 메커니즘을 사용 해야 `XCopy` 합니다.</span><span class="sxs-lookup"><span data-stu-id="e32eb-183">If your site of origin files are non-existent or unknown at compile time, you need to use traditional deployment mechanisms for ensuring the required files are available at run time, including using either the `XCopy` command-line program or the Microsoft Windows Installer.</span></span>  
  
 <span data-ttu-id="e32eb-184">컴파일 시간에서 원본 사이트에 배치 하려는 파일을 알 수 있지만 명시적 종속성을 방지 하려는 경우 해당 파일을 MSBuild 프로젝트에 항목으로 추가할 수 있습니다 `None` .</span><span class="sxs-lookup"><span data-stu-id="e32eb-184">If you do know at compile time the files that you would like to be located at the site of origin, but still want to avoid an explicit dependency, you can add those files to an MSBuild project as `None` item.</span></span> <span data-ttu-id="e32eb-185">콘텐츠 파일과 마찬가지로 MSBuild 특성을 설정 하 여 `CopyToOutputDirectory` 원본 사이트 파일이 빌드된 어셈블리에 상대적인 위치로 복사 되도록 지정 하 고 `Always` 값 또는 값을 지정 해야 합니다 `PreserveNewest` .</span><span class="sxs-lookup"><span data-stu-id="e32eb-185">As with content files, you need to set the MSBuild `CopyToOutputDirectory` attribute to specify that the site of origin file is copied to a location that is relative to the built assembly, by specifying either the `Always` value or the `PreserveNewest` value.</span></span>  
  
```xml  
<Project xmlns="http://schemas.microsoft.com/developer/msbuild/2003" ... >  
  ...  
  <None Include="PageSiteOfOriginFile.xaml">  
    <CopyToOutputDirectory>Always</CopyToOutputDirectory>  
  </None>  
  ...  
</Project>  
```  
  
> [!NOTE]
> <span data-ttu-id="e32eb-186">Visual Studio에서는 프로젝트에 파일을 추가 하 고를로 설정 하 여 원본 사이트 파일을 만듭니다 `Build Action` `None` .</span><span class="sxs-lookup"><span data-stu-id="e32eb-186">In Visual Studio, you create a site of origin file by adding a file to a project and setting its `Build Action` to `None`.</span></span>  
  
 <span data-ttu-id="e32eb-187">프로젝트가 빌드되면 MSBuild는 지정 된 파일을 빌드 출력 폴더에 복사 합니다.</span><span class="sxs-lookup"><span data-stu-id="e32eb-187">When the project is built, MSBuild copies the specified files to the build output folder.</span></span>  
  
### <a name="using-site-of-origin-files"></a><span data-ttu-id="e32eb-188">원본 사이트 파일 사용</span><span class="sxs-lookup"><span data-stu-id="e32eb-188">Using Site of Origin Files</span></span>  
 <span data-ttu-id="e32eb-189">원본 사이트 파일을 로드 하기 위해 <xref:System.Windows.Application.GetRemoteStream%2A> <xref:System.Windows.Application> 필요한 원본 사이트 파일을 식별 하는 pack URI를 전달 하 여 클래스의 메서드를 호출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e32eb-189">To load a site of origin file, you can call the <xref:System.Windows.Application.GetRemoteStream%2A> method of the <xref:System.Windows.Application> class, passing a pack URI that identifies the desired site of origin file.</span></span> <span data-ttu-id="e32eb-190"><xref:System.Windows.Application.GetRemoteStream%2A><xref:System.Windows.Resources.StreamResourceInfo>원본 사이트 파일을로 노출 하 <xref:System.IO.Stream> 고 해당 콘텐츠 형식을 설명 하는 개체를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="e32eb-190"><xref:System.Windows.Application.GetRemoteStream%2A> returns a <xref:System.Windows.Resources.StreamResourceInfo> object, which exposes the site of origin file as a <xref:System.IO.Stream> and describes its content type.</span></span>  
  
 <span data-ttu-id="e32eb-191">예를 들어, 다음 코드는를 사용 하 여 <xref:System.Windows.Application.GetRemoteStream%2A> <xref:System.Windows.Controls.Page> 원본 사이트 파일을 로드 하 고이를 ()의 콘텐츠로 설정 하는 방법을 보여 줍니다 <xref:System.Windows.Controls.Frame> `pageFrame` .</span><span class="sxs-lookup"><span data-stu-id="e32eb-191">As an example, the following code shows how to use <xref:System.Windows.Application.GetRemoteStream%2A> to load a <xref:System.Windows.Controls.Page> site of origin file and set it as the content of a <xref:System.Windows.Controls.Frame> (`pageFrame`).</span></span>  
  
 [!code-csharp[WPFAssemblyResourcesSnippets#LoadAPageSOOFileManuallyCODE](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/CSharp/ResourcesSample/SOOPage.xaml.cs#loadapagesoofilemanuallycode)]
 [!code-vb[WPFAssemblyResourcesSnippets#LoadAPageSOOFileManuallyCODE](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/VisualBasic/ResourcesSample/SOOPage.xaml.vb#loadapagesoofilemanuallycode)]  
  
 <span data-ttu-id="e32eb-192">를 호출 하는 동안에 대 한 액세스를 제공 하는 동안를 사용 하 여 <xref:System.Windows.Application.GetRemoteStream%2A> <xref:System.IO.Stream> 설정할 속성의 형식으로 변환 하는 작업을 추가로 수행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e32eb-192">While calling <xref:System.Windows.Application.GetRemoteStream%2A> gives you access to the <xref:System.IO.Stream>, you need to perform the additional work of converting it to the type of the property that you'll be setting it with.</span></span> <span data-ttu-id="e32eb-193">대신, <xref:System.IO.Stream> 코드를 사용 하 여 리소스 파일을 형식의 속성에 직접 로드 하 여 WPF가를 열고 변환 하도록 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e32eb-193">Instead, you can let WPF take care of opening and converting the <xref:System.IO.Stream> by loading a resource file directly into the property of a type using code.</span></span>  
  
 <span data-ttu-id="e32eb-194">다음 예제에서는 <xref:System.Windows.Controls.Page> <xref:System.Windows.Controls.Frame> 코드를 사용 하 여를 ()으로 직접 로드 하는 방법을 보여 줍니다 `pageFrame` .</span><span class="sxs-lookup"><span data-stu-id="e32eb-194">The following example shows how to load a <xref:System.Windows.Controls.Page> directly into a <xref:System.Windows.Controls.Frame> (`pageFrame`) using code.</span></span>  
  
 [!code-csharp[WPFAssemblyResourcesSnippets#LoadPageSOOFileFromCODE](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/CSharp/ResourcesSample/SOOPage.xaml.cs#loadpagesoofilefromcode)]
 [!code-vb[WPFAssemblyResourcesSnippets#LoadPageSOOFileFromCODE](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/VisualBasic/ResourcesSample/SOOPage.xaml.vb#loadpagesoofilefromcode)]  
  
 <span data-ttu-id="e32eb-195">다음 예제는 태그를 사용하여 앞의 예제를 구현한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="e32eb-195">The following example is the markup equivalent of the preceding example.</span></span>  
  
 [!code-xaml[WPFAssemblyResourcesSnippets#LoadPageSOOFileFromXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/CSharp/ResourcesSample/SOOPage.xaml#loadpagesoofilefromxaml)]  
  
<a name="Rebuilding_after_Changing_Build_Type"></a>
## <a name="rebuilding-after-changing-build-type"></a><span data-ttu-id="e32eb-196">빌드 형식 변경 후 다시 빌드</span><span class="sxs-lookup"><span data-stu-id="e32eb-196">Rebuilding After Changing Build Type</span></span>  
 <span data-ttu-id="e32eb-197">애플리케이션 데이터 파일의 빌드 형식을 변경한 뒤에는 변경 내용이 적용되도록 전체 애플리케이션을 다시 빌드해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e32eb-197">After you change the build type of an application data file, you need to rebuild the entire application to ensure those changes are applied.</span></span> <span data-ttu-id="e32eb-198">애플리케이션만 빌드하면 변경 내용이 적용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e32eb-198">If you only build the application, the changes are not applied.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e32eb-199">참조</span><span class="sxs-lookup"><span data-stu-id="e32eb-199">See also</span></span>

- [<span data-ttu-id="e32eb-200">WPF의 Pack URI</span><span class="sxs-lookup"><span data-stu-id="e32eb-200">Pack URIs in WPF</span></span>](pack-uris-in-wpf.md)
