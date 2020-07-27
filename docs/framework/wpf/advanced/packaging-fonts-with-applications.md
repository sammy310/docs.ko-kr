---
title: 애플리케이션과 함께 글꼴 패키징
description: 콘텐츠 및 리소스 항목으로 글꼴을 추가 하 고 글꼴 사용에 대 한 제한을 포함 하 여 Windows Presentation Foundation 응용 프로그램으로 글꼴을 패키지 하는 방법을 알아봅니다.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- applications [WPF], packaging fonts with
- fonts [WPF], packaging with applications
- typography [WPF], packaging fonts with applications
- packaging fonts with applications [WPF]
ms.assetid: db15ee48-4d24-49f5-8b9d-a64460865286
ms.openlocfilehash: 725f05c22eda199d86e5ec5dbb6bdd899ee66a5d
ms.sourcegitcommit: 87cfeb69226fef01acb17c56c86f978f4f4a13db
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/24/2020
ms.locfileid: "87166352"
---
# <a name="packaging-fonts-with-applications"></a><span data-ttu-id="3d1ef-103">애플리케이션과 함께 글꼴 패키징</span><span class="sxs-lookup"><span data-stu-id="3d1ef-103">Packaging Fonts with Applications</span></span>
<span data-ttu-id="3d1ef-104">이 항목에서는 응용 프로그램을 사용 하 여 글꼴을 패키지 하는 방법에 대 한 개요를 제공 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] 합니다.</span><span class="sxs-lookup"><span data-stu-id="3d1ef-104">This topic provides an overview of how to package fonts with your [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] application.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="3d1ef-105">대부분의 소프트웨어와 마찬가지로 글꼴 파일도 판매되는 것이 아니라 사용이 허가됩니다.</span><span class="sxs-lookup"><span data-stu-id="3d1ef-105">As with most types of software, font files are licensed, rather than sold.</span></span> <span data-ttu-id="3d1ef-106">글꼴 사용을 관리 하는 라이선스는 공급 업체 마다 다르지만 일반적으로 Microsoft에서 제공 하는 글꼴을 포함 하 여 응용 프로그램 및 Windows에서 제공 하는 글꼴을 포함 하 여 응용 프로그램 내에 글꼴을 포함 하거나 재배포 하는 것을 허용 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="3d1ef-106">Licenses that govern the use of fonts vary from vendor to vendor but in general most licenses, including those covering the fonts Microsoft supplies with applications and Windows, do not allow the fonts to be embedded within applications or otherwise redistributed.</span></span> <span data-ttu-id="3d1ef-107">따라서 개발자는 애플리케이션 내에 포함하거나 기타 다른 방법으로 재배포하려는 글꼴에 대해 필요한 라이선스 권한이 있는지 확인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3d1ef-107">Therefore, as a developer it is your responsibility to ensure that you have the required license rights for any font you embed within an application or otherwise redistribute.</span></span>  

<a name="introduction_to_packaging_fonts"></a>
## <a name="introduction-to-packaging-fonts"></a><span data-ttu-id="3d1ef-108">글꼴 패키징 소개</span><span class="sxs-lookup"><span data-stu-id="3d1ef-108">Introduction to Packaging Fonts</span></span>  
 <span data-ttu-id="3d1ef-109">[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]응용 프로그램 내에서 사용자 인터페이스 텍스트와 기타 형식의 텍스트 기반 콘텐츠를 표시 하는 리소스로 글꼴을 쉽게 패키지할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3d1ef-109">You can easily package fonts as resources within your [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] applications to display user interface text and other types of text based content.</span></span> <span data-ttu-id="3d1ef-110">글꼴은 애플리케이션의 어셈블리 파일 내에 포함하거나 별도로 저장할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3d1ef-110">The fonts can be separate from or embedded within the application's assembly files.</span></span> <span data-ttu-id="3d1ef-111">리소스 전용 글꼴 라이브러리를 만들어 애플리케이션에서 이를 참조하도록 할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3d1ef-111">You can also create a resource-only font library, which your application can reference.</span></span>  
  
 <span data-ttu-id="3d1ef-112">OpenType 및 TrueType® 글꼴에는 글꼴에 대 한 글꼴 포함 라이선스 권한을 나타내는 형식 플래그 fsType가 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3d1ef-112">OpenType and TrueType® fonts contain a type flag, fsType, that indicates font embedding licensing rights for the font.</span></span> <span data-ttu-id="3d1ef-113">그러나 이 형식 플래그는 문서에 저장된 포함된 글꼴만 참조하고 애플리케이션에 포함된 글꼴은 참조하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="3d1ef-113">However, this type flag only refers to embedded fonts stored in a document–it does not refer to fonts embedded in an application.</span></span> <span data-ttu-id="3d1ef-114">개체를 만들고 해당 속성을 참조 하 여 글꼴에 대 한 글꼴 포함 권한을 검색할 수 있습니다 <xref:System.Windows.Media.GlyphTypeface> <xref:System.Windows.Media.GlyphTypeface.EmbeddingRights%2A> .</span><span class="sxs-lookup"><span data-stu-id="3d1ef-114">You can retrieve the font embedding rights for a font by creating a <xref:System.Windows.Media.GlyphTypeface> object and referencing its <xref:System.Windows.Media.GlyphTypeface.EmbeddingRights%2A> property.</span></span> <span data-ttu-id="3d1ef-115">FsType 플래그에 대 한 자세한 내용은 [OpenType 사양의](https://www.microsoft.com/typography/otspec/os2.htm) "OS/2 및 Windows 메트릭" 섹션을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="3d1ef-115">Refer to the "OS/2 and Windows Metrics" section of the [OpenType Specification](https://www.microsoft.com/typography/otspec/os2.htm) for more information on the fsType flag.</span></span>  
  
 <span data-ttu-id="3d1ef-116">[Microsoft 입력 체계](https://docs.microsoft.com/typography/) 웹 사이트에는 특정 글꼴 공급 업체를 찾거나 사용자 지정 작업을 위한 글꼴 공급 업체를 찾는 데 도움이 되는 연락처 정보가 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3d1ef-116">The [Microsoft Typography](https://docs.microsoft.com/typography/) Web site includes contact information that can help you locate a particular font vendor or find a font vendor for custom work.</span></span>  
  
<a name="adding_fonts_as_content_items"></a>
## <a name="adding-fonts-as-content-items"></a><span data-ttu-id="3d1ef-117">콘텐츠 항목으로 글꼴 추가</span><span class="sxs-lookup"><span data-stu-id="3d1ef-117">Adding Fonts as Content Items</span></span>  
 <span data-ttu-id="3d1ef-118">애플리케이션의 어셈블리 파일과는 별도의 프로젝트 콘텐츠 항목으로 애플리케이션에 글꼴을 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3d1ef-118">You can add fonts to your application as project content items that are separate from the application's assembly files.</span></span> <span data-ttu-id="3d1ef-119">이 경우 콘텐츠 항목이 어셈블리에 리소스로 포함되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="3d1ef-119">This means that content items are not embedded as resources within an assembly.</span></span> <span data-ttu-id="3d1ef-120">다음 프로젝트 파일 예제에서는 콘텐츠 항목을 정의하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="3d1ef-120">The following project file example shows how to define content items.</span></span>  
  
```xml  
<Project DefaultTargets="Build"  
                xmlns="http://schemas.microsoft.com/developer/msbuild/2003">  
  <!-- Other project build settings ... -->  
  
  <ItemGroup>  
    <Content Include="Peric.ttf" />  
    <Content Include="Pericl.ttf" />  
  </ItemGroup>  
</Project>  
```  
  
 <span data-ttu-id="3d1ef-121">애플리케이션에서 런타임에 글꼴을 사용할 수 있도록 하려면 애플리케이션의 배포 디렉터리에서 해당 글꼴에 액세스할 수 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3d1ef-121">In order to ensure that the application can use the fonts at run time, the fonts must be accessible in the application's deployment directory.</span></span> <span data-ttu-id="3d1ef-122">`<CopyToOutputDirectory>`응용 프로그램의 프로젝트 파일에 있는 요소를 사용 하면 빌드 프로세스 중에 응용 프로그램 배포 디렉터리에 글꼴을 자동으로 복사할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3d1ef-122">The `<CopyToOutputDirectory>` element in the application's project file allows you to automatically copy the fonts to the application deployment directory during the build process.</span></span> <span data-ttu-id="3d1ef-123">다음 프로젝트 파일 예제에서는 글꼴을 배포 디렉터리에 복사하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="3d1ef-123">The following project file example shows how to copy fonts to the deployment directory.</span></span>  
  
```xml  
<ItemGroup>  
  <Content Include="Peric.ttf">  
    <CopyToOutputDirectory>PreserveNewest</CopyToOutputDirectory>  
  </Content>  
  <Content Include="Pericl.ttf">  
    <CopyToOutputDirectory>PreserveNewest</CopyToOutputDirectory>  
  </Content>  
</ItemGroup>  
```  
  
 <span data-ttu-id="3d1ef-124">다음 코드 예제에서는 애플리케이션의 글꼴을 콘텐츠 항목으로 참조하는 방법을 보여 줍니다. 참조되는 콘텐츠 항목은 애플리케이션의 어셈블리 파일과 동일한 디렉터리에 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3d1ef-124">The following code example shows how to reference the application's font as a content item—the referenced content item must be in the same directory as the application's assembly files.</span></span>  
  
 [!code-xaml[FontSnippets#FontPackageSnippet8](~/samples/snippets/csharp/VS_Snippets_Wpf/FontSnippets/CSharp/FontPackageSnippets.xaml#fontpackagesnippet8)]  
  
<a name="adding_fonts_as_resource_items"></a>
## <a name="adding-fonts-as-resource-items"></a><span data-ttu-id="3d1ef-125">리소스 항목으로 글꼴 추가</span><span class="sxs-lookup"><span data-stu-id="3d1ef-125">Adding Fonts as Resource Items</span></span>  
 <span data-ttu-id="3d1ef-126">애플리케이션의 어셈블리 파일에 포함된 프로젝트 리소스 항목으로 애플리케이션에 글꼴을 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3d1ef-126">You can add fonts to your application as project resource items that are embedded within the application's assembly files.</span></span> <span data-ttu-id="3d1ef-127">리소스에 별도의 하위 디렉터리를 사용하면 애플리케이션의 프로젝트 파일을 보다 간편하게 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3d1ef-127">Using a separate subdirectory for resources helps to organize the application's project files.</span></span> <span data-ttu-id="3d1ef-128">다음 프로젝트 파일 예제에서는 별도의 하위 디렉터리에 리소스 항목으로 글꼴을 정의하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="3d1ef-128">The following project file example shows how to define fonts as resource items in a separate subdirectory.</span></span>  
  
```xml  
<Project DefaultTargets="Build"  
                xmlns="http://schemas.microsoft.com/developer/msbuild/2003">  
  <!-- Other project build settings ... -->  
  
  <ItemGroup>  
    <Resource Include="resources\Peric.ttf" />  
    <Resource Include="resources\Pericl.ttf" />  
  </ItemGroup>  
</Project>  
```  
  
> [!NOTE]
> <span data-ttu-id="3d1ef-129">응용 프로그램에 리소스를 리소스로 추가 하는 경우 `<Resource>` `<EmbeddedResource>` 응용 프로그램의 프로젝트 파일에서 요소가 아니라 요소를 설정 하 고 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="3d1ef-129">When you add fonts as resources to your application, make sure you are setting the `<Resource>` element, and not the `<EmbeddedResource>` element in your application's project file.</span></span> <span data-ttu-id="3d1ef-130">`<EmbeddedResource>`빌드 작업에 대 한 요소가 지원 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="3d1ef-130">The `<EmbeddedResource>` element for the build action is not supported.</span></span>  
  
 <span data-ttu-id="3d1ef-131">다음 태그 예제에서는 애플리케이션의 글꼴 리소스를 참조하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="3d1ef-131">The following markup example shows how to reference the application's font resources.</span></span>  
  
 [!code-xaml[FontSnippets#FontPackageSnippet1](~/samples/snippets/csharp/VS_Snippets_Wpf/FontSnippets/CSharp/FontPackageSnippets.xaml#fontpackagesnippet1)]  
  
### <a name="referencing-font-resource-items-from-code"></a><span data-ttu-id="3d1ef-132">코드에서 글꼴 리소스 항목 참조</span><span class="sxs-lookup"><span data-stu-id="3d1ef-132">Referencing Font Resource Items from Code</span></span>  
 <span data-ttu-id="3d1ef-133">코드에서 글꼴 리소스 항목을 참조 하려면 기본 URI (uniform resource identifier) 라는 두 부분으로 구성 된 글꼴 리소스 참조를 제공 해야 합니다. 및 글꼴 위치 참조입니다.</span><span class="sxs-lookup"><span data-stu-id="3d1ef-133">In order to reference font resource items from code, you must supply a two-part font resource reference: the base uniform resource identifier (URI); and the font location reference.</span></span> <span data-ttu-id="3d1ef-134">이러한 값은 메서드의 매개 변수로 사용 됩니다 <xref:System.Windows.Media.FontFamily.%23ctor%2A> .</span><span class="sxs-lookup"><span data-stu-id="3d1ef-134">These values are used as the parameters for the <xref:System.Windows.Media.FontFamily.%23ctor%2A> method.</span></span> <span data-ttu-id="3d1ef-135">다음 코드 예제에서는 라는 프로젝트 하위 디렉터리에서 응용 프로그램의 글꼴 리소스를 참조 하는 방법을 보여 줍니다 `resources` .</span><span class="sxs-lookup"><span data-stu-id="3d1ef-135">The following code example shows how to reference the application's font resources in the project subdirectory called `resources`.</span></span>  
  
 [!code-csharp[FontSnippets#FontPackageSnippet2](~/samples/snippets/csharp/VS_Snippets_Wpf/FontSnippets/CSharp/FontPackageSnippets.xaml.cs#fontpackagesnippet2)]
 [!code-vb[FontSnippets#FontPackageSnippet2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/FontSnippets/visualbasic/fontpackagesnippets.xaml.vb#fontpackagesnippet2)]  
  
 <span data-ttu-id="3d1ef-136">기본 URI (uniform resource identifier)는 글꼴 리소스가 있는 응용 프로그램 하위 디렉터리를 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3d1ef-136">The base uniform resource identifier (URI) can include the application subdirectory where the font resource resides.</span></span> <span data-ttu-id="3d1ef-137">이 경우 글꼴 위치 참조는 디렉터리를 지정할 필요가 없지만, 선행 ""을 포함 해야 합니다 .이는 `./` 기본 URI (uniform resource identifier)로 지정 된 동일한 디렉터리에 글꼴 리소스가 있음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="3d1ef-137">In this case, the font location reference would not need to specify a directory, but would have to include a leading "`./`", which indicates the font resource is in the same directory specified by the base uniform resource identifier (URI).</span></span> <span data-ttu-id="3d1ef-138">다음 코드 예제에서는 위의 코드 예제에 나오는 것과 동일한 글꼴 리소스 항목을 참조하는 다른 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="3d1ef-138">The following code example shows an alternate way of referencing the font resource item—it is equivalent to the previous code example.</span></span>  
  
 [!code-csharp[FontSnippets#FontPackageSnippet5](~/samples/snippets/csharp/VS_Snippets_Wpf/FontSnippets/CSharp/FontPackageSnippets.xaml.cs#fontpackagesnippet5)]
 [!code-vb[FontSnippets#FontPackageSnippet5](~/samples/snippets/visualbasic/VS_Snippets_Wpf/FontSnippets/visualbasic/fontpackagesnippets.xaml.vb#fontpackagesnippet5)]  
  
### <a name="referencing-fonts-from-the-same-application-subdirectory"></a><span data-ttu-id="3d1ef-139">동일한 애플리케이션 하위 디렉터리에서 글꼴 참조</span><span class="sxs-lookup"><span data-stu-id="3d1ef-139">Referencing Fonts from the Same Application Subdirectory</span></span>  
 <span data-ttu-id="3d1ef-140">애플리케이션 콘텐츠와 리소스 파일을 모두 애플리케이션 프로젝트의 동일한 사용자 정의 하위 디렉터리에 배치할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3d1ef-140">You can place both application content and resource files within the same user-defined subdirectory of your application project.</span></span> <span data-ttu-id="3d1ef-141">다음 프로젝트 파일 예제에서는 동일한 하위 디렉터리에 정의된 콘텐츠 페이지와 글꼴 리소스를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="3d1ef-141">The following project file example shows a content page and font resources defined in the same subdirectory.</span></span>  
  
```xml  
<ItemGroup>  
  <Page Include="pages\HomePage.xaml" />  
</ItemGroup>  
<ItemGroup>  
  <Resource Include="pages\Peric.ttf" />  
  <Resource Include="pages\Pericl.ttf" />  
</ItemGroup>  
```  
  
 <span data-ttu-id="3d1ef-142">애플리케이션 콘텐츠와 글꼴이 동일한 하위 디렉터리에 있으므로 글꼴 참조가 애플리케이션 콘텐츠를 기준으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="3d1ef-142">Since the application content and font are in the same subdirectory, the font reference is relative to the application content.</span></span> <span data-ttu-id="3d1ef-143">다음 예제에서는 글꼴이 애플리케이션과 동일한 디렉터리에 있는 경우 애플리케이션의 글꼴 리소스를 참조하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="3d1ef-143">The following examples show how to reference the application's font resource when the font is in the same directory as the application.</span></span>  
  
 [!code-xaml[FontSnippets#FontPackageSnippet3](~/samples/snippets/csharp/VS_Snippets_Wpf/FontSnippets/CSharp/pages/HomePage.xaml#fontpackagesnippet3)]  
  
 [!code-csharp[FontSnippets#FontPackageSnippet4](~/samples/snippets/csharp/VS_Snippets_Wpf/FontSnippets/CSharp/pages/HomePage.xaml.cs#fontpackagesnippet4)]
 [!code-vb[FontSnippets#FontPackageSnippet4](~/samples/snippets/visualbasic/VS_Snippets_Wpf/FontSnippets/visualbasic/pages/homepage.xaml.vb#fontpackagesnippet4)]  
  
### <a name="enumerating-fonts-in-an-application"></a><span data-ttu-id="3d1ef-144">애플리케이션의 글꼴 열거</span><span class="sxs-lookup"><span data-stu-id="3d1ef-144">Enumerating Fonts in an Application</span></span>  
 <span data-ttu-id="3d1ef-145">응용 프로그램에서 리소스 항목으로 글꼴을 열거 하려면 또는 메서드 중 하나를 사용 <xref:System.Windows.Media.Fonts.GetFontFamilies%2A> <xref:System.Windows.Media.Fonts.GetTypefaces%2A> 합니다.</span><span class="sxs-lookup"><span data-stu-id="3d1ef-145">To enumerate fonts as resource items in your application, use either the <xref:System.Windows.Media.Fonts.GetFontFamilies%2A> or <xref:System.Windows.Media.Fonts.GetTypefaces%2A> method.</span></span> <span data-ttu-id="3d1ef-146">다음 예제에서는 메서드를 사용 하 여 <xref:System.Windows.Media.Fonts.GetFontFamilies%2A> <xref:System.Windows.Media.FontFamily> 응용 프로그램 글꼴 위치에서 개체의 컬렉션을 반환 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="3d1ef-146">The following example shows how to use the <xref:System.Windows.Media.Fonts.GetFontFamilies%2A> method to return the collection of <xref:System.Windows.Media.FontFamily> objects from the application font location.</span></span> <span data-ttu-id="3d1ef-147">이 경우에는 애플리케이션에 “resources”라는 하위 디렉터리가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3d1ef-147">In this case, the application contains a subdirectory named "resources".</span></span>  
  
 [!code-csharp[FontSnippets#FontsSnippet3](~/samples/snippets/csharp/VS_Snippets_Wpf/FontSnippets/CSharp/FontFamilySnippets.xaml.cs#fontssnippet3)]
 [!code-vb[FontSnippets#FontsSnippet3](~/samples/snippets/visualbasic/VS_Snippets_Wpf/FontSnippets/visualbasic/fontfamilysnippets.xaml.vb#fontssnippet3)]  
  
 <span data-ttu-id="3d1ef-148">다음 예제에서는 메서드를 사용 하 여 <xref:System.Windows.Media.Fonts.GetTypefaces%2A> <xref:System.Windows.Media.Typeface> 응용 프로그램 글꼴 위치에서 개체의 컬렉션을 반환 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="3d1ef-148">The following example shows how to use the <xref:System.Windows.Media.Fonts.GetTypefaces%2A> method to return the collection of <xref:System.Windows.Media.Typeface> objects from the application font location.</span></span> <span data-ttu-id="3d1ef-149">이 경우에는 애플리케이션에 “resources”라는 하위 디렉터리가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3d1ef-149">In this case, the application contains a subdirectory named "resources".</span></span>  
  
 [!code-csharp[FontSnippets#FontsSnippet7](~/samples/snippets/csharp/VS_Snippets_Wpf/FontSnippets/CSharp/FontFamilySnippets.xaml.cs#fontssnippet7)]
 [!code-vb[FontSnippets#FontsSnippet7](~/samples/snippets/visualbasic/VS_Snippets_Wpf/FontSnippets/visualbasic/fontfamilysnippets.xaml.vb#fontssnippet7)]  
  
<a name="creating_a_font_resource_library"></a>
## <a name="creating-a-font-resource-library"></a><span data-ttu-id="3d1ef-150">글꼴 리소스 라이브러리 만들기</span><span class="sxs-lookup"><span data-stu-id="3d1ef-150">Creating a Font Resource Library</span></span>  
 <span data-ttu-id="3d1ef-151">글꼴만 포함된 리소스 전용 라이브러리를 만들 수 있습니다. 이러한 유형의 라이브러리 프로젝트에는 코드가 포함되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="3d1ef-151">You can create a resource-only library that contains only fonts—no code is part of this type of library project.</span></span> <span data-ttu-id="3d1ef-152">리소스 전용 라이브러리는 일반적으로 리소스와 리소스를 사용하는 애플리케이션 코드를 분리하려는 경우에 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="3d1ef-152">Creating a resource-only library is a common technique for decoupling resources from the application code that uses them.</span></span> <span data-ttu-id="3d1ef-153">리소스 전용 라이브러리를 만들면 라이브러리 어셈블리를 여러 애플리케이션 프로젝트에 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3d1ef-153">This also allows the library assembly to be included with multiple application projects.</span></span> <span data-ttu-id="3d1ef-154">다음 프로젝트 파일 예제에서는 리소스 전용 라이브러리 프로젝트의 주요 부분을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="3d1ef-154">The following project file example shows the key portions of a resource-only library project.</span></span>  
  
```xml  
<PropertyGroup>  
  <AssemblyName>FontLibrary</AssemblyName>  
  <OutputType>library</OutputType>  
  ...  
</PropertyGroup>  
...
<ItemGroup>  
  <Resource Include="Kooten.ttf" />  
  <Resource Include="Pesca.ttf" />  
</ItemGroup  
```  
  
### <a name="referencing-a-font-in-a-resource-library"></a><span data-ttu-id="3d1ef-155">리소스 라이브러리의 글꼴 참조</span><span class="sxs-lookup"><span data-stu-id="3d1ef-155">Referencing a Font in a Resource Library</span></span>  
 <span data-ttu-id="3d1ef-156">애플리케이션에서 리소스 라이브러리의 글꼴을 참조하려면 라이브러리 어셈블리의 이름을 글꼴 참조의 접두사로 지정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3d1ef-156">To reference a font in a resource library from your application, you must prefix the font reference with the name of the library assembly.</span></span> <span data-ttu-id="3d1ef-157">이 경우 글꼴 리소스 어셈블리는 “FontLibrary”입니다.</span><span class="sxs-lookup"><span data-stu-id="3d1ef-157">In this case, the font resource assembly is "FontLibrary".</span></span> <span data-ttu-id="3d1ef-158">어셈블리 이름을 어셈블리 내의 참조와 구분하려면 ‘;’ 문자를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="3d1ef-158">To separate the assembly name from the reference within the assembly, use a ';' character.</span></span> <span data-ttu-id="3d1ef-159">글꼴 이름에 “Component” 키워드와 참조를 차례로 추가하면 글꼴 라이브러리의 리소스에 대한 전체 참조가 완성됩니다.</span><span class="sxs-lookup"><span data-stu-id="3d1ef-159">Adding the "Component" keyword followed by the reference to the font name completes the full reference to the font library's resource.</span></span> <span data-ttu-id="3d1ef-160">다음 코드 예제에서는 리소스 라이브러리 어셈블리의 글꼴을 참조하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="3d1ef-160">The following code example shows how to reference a font in a resource library assembly.</span></span>  
  
 [!code-xaml[OpenTypeFontsSample#OpenTypeFontsSample1](~/samples/snippets/csharp/VS_Snippets_Wpf/OpenTypeFontsSample/CS/Kootenay.xaml#opentypefontssample1)]  
  
> [!NOTE]
> <span data-ttu-id="3d1ef-161">이 SDK에는 응용 프로그램과 함께 사용할 수 있는 샘플 OpenType 글꼴 집합이 포함 되어 있습니다 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="3d1ef-161">This SDK contains a set of sample OpenType fonts that you can use with [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] applications.</span></span> <span data-ttu-id="3d1ef-162">글꼴은 리소스 전용 라이브러리에 정의되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3d1ef-162">The fonts are defined in a resource-only library.</span></span> <span data-ttu-id="3d1ef-163">자세한 내용은 [샘플 OpenType 글꼴 팩](sample-opentype-font-pack.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="3d1ef-163">For more information, see [Sample OpenType Font Pack](sample-opentype-font-pack.md).</span></span>  
  
<a name="limitations_on_font_usage"></a>
## <a name="limitations-on-font-usage"></a><span data-ttu-id="3d1ef-164">글꼴 사용의 제한 사항</span><span class="sxs-lookup"><span data-stu-id="3d1ef-164">Limitations on Font Usage</span></span>  
 <span data-ttu-id="3d1ef-165">다음 목록에서는 응용 프로그램의 글꼴 패키징 및 사용에 대 한 몇 가지 제한 사항을 설명 합니다 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="3d1ef-165">The following list describes several limitations on the packaging and use of fonts in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] applications:</span></span>  
  
- <span data-ttu-id="3d1ef-166">**글꼴 포함 권한 비트:** [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 애플리케이션은 글꼴 포함 권한 비트를 확인하거나 적용하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="3d1ef-166">**Font embedding permission bits:** [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] applications do not check or enforce any font embedding permission bits.</span></span> <span data-ttu-id="3d1ef-167">자세한 내용은 [Introduction_to_Packing 글꼴](#introduction_to_packaging_fonts) 섹션을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="3d1ef-167">See the [Introduction_to_Packing Fonts](#introduction_to_packaging_fonts) section for more information.</span></span>  
  
- <span data-ttu-id="3d1ef-168">**원본 사이트 글꼴:** [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 응용 프로그램은 http 또는 ftp URI (uniform resource identifier)에 대 한 글꼴 참조를 허용 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="3d1ef-168">**Site of origin fonts:** [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] applications do not allow a font reference to an http or ftp uniform resource identifier (URI).</span></span>  
  
- <span data-ttu-id="3d1ef-169">**Pack: notation** [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 을 사용 하는 절대 URI: 응용 프로그램에서는 <xref:System.Windows.Media.FontFamily> "pack:"를 사용 하 여 프로그래밍 방식으로 개체를 만들 수 없습니다 .이는 절대 URI (uniform resource identifier) 참조의 일부로 서</span><span class="sxs-lookup"><span data-stu-id="3d1ef-169">**Absolute URI using the pack: notation:** [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] applications do not allow you to create a <xref:System.Windows.Media.FontFamily> object programmatically using "pack:" as part of the absolute uniform resource identifier (URI) reference to a font.</span></span> <span data-ttu-id="3d1ef-170">예를 들어 `"pack://application:,,,/resources/#Pericles Light"` 은 잘못 된 글꼴 참조입니다.</span><span class="sxs-lookup"><span data-stu-id="3d1ef-170">For example, `"pack://application:,,,/resources/#Pericles Light"` is an invalid font reference.</span></span>  
  
- <span data-ttu-id="3d1ef-171">**자동 글꼴 포함:** 디자인 타임에는 애플리케이션에서 사용하는 글꼴을 검색하여 애플리케이션의 리소스에 자동으로 해당 글꼴을 포함하는 기능이 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="3d1ef-171">**Automatic font embedding:** During design time, there is no support for searching an application's use of fonts and automatically embedding the fonts in the application's resources.</span></span>  
  
- <span data-ttu-id="3d1ef-172">**글꼴 하위 집합:** [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 애플리케이션은 고정되지 않은 문서에 대해서는 글꼴 하위 집합을 만드는 것을 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="3d1ef-172">**Font subsets:** [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] applications do not support the creation of font subsets for non-fixed documents.</span></span>  
  
- <span data-ttu-id="3d1ef-173">올바르지 않은 참조가 있는 경우 애플리케이션에서는 사용 가능한 글꼴로 대체합니다.</span><span class="sxs-lookup"><span data-stu-id="3d1ef-173">In cases where there is an incorrect reference, the application falls back to using an available font.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3d1ef-174">참고 항목</span><span class="sxs-lookup"><span data-stu-id="3d1ef-174">See also</span></span>

- <xref:System.Windows.Documents.Typography>
- <xref:System.Windows.Media.FontFamily>
- <span data-ttu-id="3d1ef-175">[Microsoft Typography: Links, News, and Contacts](https://docs.microsoft.com/typography/)(Microsoft 입력 체계: 링크, 뉴스 및 연락처)</span><span class="sxs-lookup"><span data-stu-id="3d1ef-175">[Microsoft Typography: Links, News, and Contacts](https://docs.microsoft.com/typography/)</span></span>
- [<span data-ttu-id="3d1ef-176">OpenType 사양</span><span class="sxs-lookup"><span data-stu-id="3d1ef-176">OpenType Specification</span></span>](https://www.microsoft.com/typography/otspec/)
- [<span data-ttu-id="3d1ef-177">OpenType 글꼴 기능</span><span class="sxs-lookup"><span data-stu-id="3d1ef-177">OpenType Font Features</span></span>](opentype-font-features.md)
- [<span data-ttu-id="3d1ef-178">샘플 OpenType 글꼴 팩</span><span class="sxs-lookup"><span data-stu-id="3d1ef-178">Sample OpenType Font Pack</span></span>](sample-opentype-font-pack.md)
