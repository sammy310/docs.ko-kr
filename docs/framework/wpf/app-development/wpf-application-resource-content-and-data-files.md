---
title: 응용 프로그램 리소스, 콘텐츠 및 데이터 파일
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
ms.openlocfilehash: f17898972eeef66447060db32bae5fae377b710e
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79186198"
---
# <a name="wpf-application-resource-content-and-data-files"></a>WPF 애플리케이션 리소스, 콘텐츠 및 데이터 파일
Microsoft Windows 응용 프로그램은 종종 . 이미지, 비디오 및 오디오와 같은 [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]실행 불가능한 데이터가 포함된 파일에 의존합니다. WPF(Windows 프레젠테이션 재단)는 응용 프로그램 데이터 파일이라고 하는 이러한 유형의 데이터 파일을 구성, 식별 및 사용하는 데 특별한 지원을 제공합니다. 이러한 지원에는 다음을 포함한 특정 애플리케이션 데이터 파일 형식 집합이 포함됩니다.  
  
- **리소스 파일**: 실행 파일 또는 라이브러리 WPF 어셈블리로 컴파일되는 데이터 파일입니다.  
  
- **콘텐츠 파일**: 실행 WPF 어셈블리와 명시적 연관이 있는 독립 실행형 데이터 파일입니다.  
  
- **원본 파일 사이트**: 실행 파일 WPF 어셈블리와 연관이 없는 독립 실행형 데이터 파일입니다.  
  
 이 세 가지 파일 형식을 구분하는 한 가지 중요한 차이점은 리소스 파일과 콘텐츠 파일은 빌드할 때 인식된다는 점입니다. 어셈블리는 명시적으로 이 파일을 인식합니다. 그러나 원본 파일의 사이트에 대 한 어셈블리는 그들에 대 한 지식이 전혀 없을 수 있습니다., 또는 팩 균일 한 리소스 식별자 (URI) 참조를 통해 암시적 지식; 후자의 경우 참조된 원본 파일이 실제로 존재한다는 보장은 없습니다.  
  
 응용 프로그램 데이터 파일을 참조하기 위해 WPF(Windows 프레젠테이션 Foundation)는 [WPF의 팩 URI에](pack-uris-in-wpf.md)자세히 설명되어 있는 Pack 균일한 리소스 식별자(URI) 체계를 사용합니다.  
  
 이 항목에서는 애플리케이션 데이터 파일을 구성하고 사용하는 방법을 설명합니다.  

<a name="Resource_Files"></a>
## <a name="resource-files"></a>리소스 파일  
 애플리케이션에서 애플리케이션 데이터 파일을 항상 사용할 수 있어야 하는 경우 가용성을 보장하는 유일한 방법은 데이터 파일을 애플리케이션의 주 실행 어셈블리 또는 참조되는 어셈블리 중 하나로 컴파일하는 것입니다. 이러한 유형의 응용 프로그램 데이터 파일을 *리소스 파일이라고*합니다.  
  
 다음과 같은 경우에 리소스 파일을 사용해야 합니다.  
  
- 어셈블리로 컴파일한 뒤에는 리소스 파일의 콘텐츠를 업데이트할 필요가 없는 경우.  
  
- 파일 종속성의 수를 줄여 애플리케이션 배포의 복잡성을 줄이려는 경우.  
  
- 응용 프로그램 데이터 파일을 현지화할 수 있어야 [합니다(WPF 전역화 및 지역화 개요](../advanced/wpf-globalization-and-localization-overview.md)참조).  
  
> [!NOTE]
> 이 섹션에서 설명하는 리소스 파일은 [XAML 리소스에](../../../desktop-wpf/fundamentals/xaml-resources-define.md) 설명된 리소스 파일과 다르며 [응용 프로그램 리소스 관리(.NET)에](/visualstudio/ide/managing-application-resources-dotnet)설명된 포함된 리소스 또는 연결된 리소스와 다릅니다.  
  
### <a name="configuring-resource-files"></a>리소스 파일 구성  
 WPF에서 리소스 파일은 Microsoft 빌드 엔진(MSBuild) 프로젝트에 항목으로 포함된 `Resource` 파일입니다.  
  
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
> Visual Studio에서 프로젝트에 파일을 추가하고 에 `Build Action` 파일을 설정하여 리소스 `Resource`파일을 만듭니다.  
  
 프로젝트가 빌드되면 MSBuild는 리소스를 어셈블리에 컴파일합니다.  
  
### <a name="using-resource-files"></a>리소스 파일 사용  
 리소스 파일을 로드하려면 <xref:System.Windows.Application.GetResourceStream%2A> <xref:System.Windows.Application> 원하는 리소스 파일을 식별하는 팩 URI를 전달하는 클래스의 메서드를 호출할 수 있습니다. <xref:System.Windows.Application.GetResourceStream%2A><xref:System.Windows.Resources.StreamResourceInfo> 리소스 파일을 로 <xref:System.IO.Stream> 노출하고 해당 콘텐츠 형식을 설명하는 개체를 반환합니다.  
  
 예를 들어 다음 <xref:System.Windows.Application.GetResourceStream%2A> 코드는 <xref:System.Windows.Controls.Page> 리소스 파일을 로드하고 <xref:System.Windows.Controls.Frame> (의`pageFrame`콘텐츠로 설정하는 데 사용하는 방법을 보여 주며)  
  
 [!code-csharp[WPFAssemblyResourcesSnippets#LoadAPageResourceFileManuallyCODE](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/CSharp/ResourcesSample/ApplicationGetResourceStreamSnippetWindow.xaml.cs#loadapageresourcefilemanuallycode)]
 [!code-vb[WPFAssemblyResourcesSnippets#LoadAPageResourceFileManuallyCODE](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/VisualBasic/ResourcesSample/ApplicationGetResourceStreamSnippetWindow.xaml.vb#loadapageresourcefilemanuallycode)]  
  
 호출을 <xref:System.Windows.Application.GetResourceStream%2A> 사용하면 <xref:System.IO.Stream>에 액세스할 수 있지만 을 설정하는 속성의 유형으로 변환하는 추가 작업을 수행해야 합니다. 대신 WPF가 코드를 사용하여 리소스 파일을 직접 <xref:System.IO.Stream> 코드 의 속성으로 로드하여 개열고 변환할 수 있도록 할 수 있습니다.  
  
 다음 예제에서는 코드를 사용하여 <xref:System.Windows.Controls.Page> <xref:System.Windows.Controls.Frame> ()에`pageFrame`직접 로드하는 방법을 보여 주며 있습니다.  
  
 [!code-csharp[WPFAssemblyResourcesSnippets#LoadPageResourceFileFromCODE](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/CSharp/ResourcesSample/ApplicationGetResourceStreamSnippetWindow.xaml.cs#loadpageresourcefilefromcode)]
 [!code-vb[WPFAssemblyResourcesSnippets#LoadPageResourceFileFromCODE](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/VisualBasic/ResourcesSample/ApplicationGetResourceStreamSnippetWindow.xaml.vb#loadpageresourcefilefromcode)]  
  
 다음 예제는 태그를 사용하여 앞의 예제를 구현한 것입니다.  
  
 [!code-xaml[WPFAssemblyResourcesSnippets#LoadPageResourceFileFromXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/CSharp/ResourcesSample/ApplicationGetResourceStreamSnippetWindow.xaml#loadpageresourcefilefromxaml)]  
  
### <a name="application-code-files-as-resource-files"></a>리소스 파일로 사용되는 애플리케이션 코드 파일  
 WPF 응용 프로그램 코드 파일의 특별 한 집합은 창, 페이지, 흐름 문서 및 리소스 사전을 포함 하 여 pack URI를 사용 하 여 참조할 수 있습니다. 예를 들어 응용 프로그램이 <xref:System.Windows.Application.StartupUri%2A?displayProperty=nameWithType> 시작될 때 로드할 창이나 페이지를 참조하는 pack URI를 사용하여 속성을 설정할 수 있습니다.  
  
 [!code-xaml[WPFAssemblyResourcesSnippets#SetApplicationStartupURI](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/CSharp/ResourcesSample/App.xaml#setapplicationstartupuri)]  
  
 XAML 파일이 MSBuild 프로젝트에 항목으로 포함된 경우 `Page` 이 작업을 수행할 수 있습니다.  
  
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
> <xref:System.Windows.Window>Visual Studio에서 새 을 <xref:System.Windows.Navigation.NavigationWindow> <xref:System.Windows.Controls.Page> <xref:System.Windows.Documents.FlowDocument> <xref:System.Windows.ResourceDictionary> 추가하거나 프로젝트에 태그 파일의 `Build Action` 기본값에 대해 추가합니다. `Page`  
  
 항목이 있는 `Page` 프로젝트가 컴파일되면 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 항목이 이진 형식으로 변환되고 관련 어셈블리로 컴파일됩니다. 결과적으로 이 파일을 일반적인 리소스 파일과 같은 방법으로 사용할 수 있습니다.  
  
> [!NOTE]
> 파일이 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] `Resource` 항목으로 구성되어 있고 코드 숨결 파일이 없는 경우 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 원시 는 원시의 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]이진 버전이 아닌 어셈블리로 컴파일됩니다.  
  
<a name="Content_Files"></a>
## <a name="content-files"></a>콘텐츠 파일  
 *콘텐츠 파일은* 실행 파일 어셈블리와 함께 느슨한 파일로 배포됩니다. 어셈블리로 컴파일되지는 않지만 어셈블리는 각 콘텐츠 파일과 연결되는 메타데이터와 함께 컴파일됩니다.  
  
 데이터 파일을 사용하는 어셈블리를 재컴파일하지 않고 업데이트하고자 하는 애플리케이션 데이터 파일을 애플리케이션에서 필요로 할 때는 콘텐츠 파일을 사용해야 합니다.  
  
### <a name="configuring-content-files"></a>콘텐츠 파일 구성  
 프로젝트에 콘텐츠 파일을 추가하려면 응용 프로그램 데이터 파일을 `Content` 항목으로 포함해야 합니다. 또한 콘텐츠 파일이 어셈블리에 직접 컴파일되지 않으므로 MSBuild `CopyToOutputDirectory` 메타데이터 요소를 설정하여 콘텐츠 파일이 빌드된 어셈블리를 기준으로 하는 위치에 복사되도록 지정해야 합니다. 프로젝트를 빌드할 때마다 리소스를 빌드 출력 폴더에 복사하려면 `CopyToOutputDirectory` `Always` 값으로 메타데이터 요소를 설정합니다. 그렇지 않으면 `PreserveNewest` 값을 사용하여 리소스의 최신 버전만 빌드 출력 폴더에 복사되도록 할 수 있습니다.  
  
 다음 예제에서는 리소스의 새 버전이 프로젝트에 추가된 경우에만 콘텐츠 파일이 빌드 출력 폴더에 복사되는 방식으로 구성된 파일을 보여 줍니다.  
  
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
> Visual Studio에서는 `Build Action` 프로젝트에 파일을 추가하고 의 파일을 `Content`에 `Copy to Output Directory` `Copy always` 설정하고(와 `Always` `Copy if newer` `PreserveNewest`같으며) 및 (와 동일)로 설정하여 컨텐트 파일을 만듭니다.  
  
 프로젝트가 빌드되면 <xref:System.Windows.Resources.AssemblyAssociatedContentFileAttribute> 특성이 각 콘텐츠 파일에 대한 어셈블리의 메타데이터로 컴파일됩니다.  
  
 `[assembly: AssemblyAssociatedContentFile("ContentFile.xaml")]`  
  
 값은 <xref:System.Windows.Resources.AssemblyAssociatedContentFileAttribute> 프로젝트의 위치를 기준으로 콘텐츠 파일에 대한 경로를 의미합니다. 예를 들어 콘텐츠 파일이 프로젝트 하위 폴더에 있는 경우 추가 경로 <xref:System.Windows.Resources.AssemblyAssociatedContentFileAttribute> 정보가 값에 통합됩니다.  
  
 `[assembly: AssemblyAssociatedContentFile("Resources/ContentFile.xaml")]`  
  
 이 <xref:System.Windows.Resources.AssemblyAssociatedContentFileAttribute> 값은 빌드 출력 폴더의 콘텐츠 파일에 대한 경로의 값이기도 합니다.  
  
### <a name="using-content-files"></a>콘텐츠 파일 사용  
 콘텐츠 파일을 로드하려면 클래스의 <xref:System.Windows.Application.GetContentStream%2A> 메서드를 <xref:System.Windows.Application> 호출하여 원하는 콘텐츠 파일을 식별하는 pack URI를 전달할 수 있습니다. <xref:System.Windows.Application.GetContentStream%2A>는 <xref:System.Windows.Resources.StreamResourceInfo> 콘텐츠 파일을 로 <xref:System.IO.Stream> 노출하고 해당 콘텐츠 형식을 설명하는 개체를 반환합니다.  
  
 예를 들어 다음 <xref:System.Windows.Application.GetContentStream%2A> 코드는 <xref:System.Windows.Controls.Page> 콘텐츠 파일을 로드하고 ()의 <xref:System.Windows.Controls.Frame> `pageFrame`콘텐츠로 설정하는 데 사용하는 방법을 보여 주며 있습니다.  
  
 [!code-csharp[WPFAssemblyResourcesSnippets#LoadAPageContentFileManuallyCODE](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/CSharp/ResourcesSample/ApplicationGetContentStreamSnippetWindow.xaml.cs#loadapagecontentfilemanuallycode)]
 [!code-vb[WPFAssemblyResourcesSnippets#LoadAPageContentFileManuallyCODE](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/VisualBasic/ResourcesSample/ApplicationGetContentStreamSnippetWindow.xaml.vb#loadapagecontentfilemanuallycode)]  
  
 호출을 <xref:System.Windows.Application.GetContentStream%2A> 사용하면 <xref:System.IO.Stream>에 액세스할 수 있지만 을 설정하는 속성의 유형으로 변환하는 추가 작업을 수행해야 합니다. 대신 WPF가 코드를 사용하여 리소스 파일을 직접 <xref:System.IO.Stream> 코드 의 속성으로 로드하여 개열고 변환할 수 있도록 할 수 있습니다.  
  
 다음 예제에서는 코드를 사용하여 <xref:System.Windows.Controls.Page> <xref:System.Windows.Controls.Frame> ()에`pageFrame`직접 로드하는 방법을 보여 주며 있습니다.  
  
 [!code-csharp[WPFAssemblyResourcesSnippets#LoadPageContentFileFromCODE](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/CSharp/ResourcesSample/ApplicationGetContentStreamSnippetWindow.xaml.cs#loadpagecontentfilefromcode)]
 [!code-vb[WPFAssemblyResourcesSnippets#LoadPageContentFileFromCODE](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/VisualBasic/ResourcesSample/ApplicationGetContentStreamSnippetWindow.xaml.vb#loadpagecontentfilefromcode)]  
  
 다음 예제는 태그를 사용하여 앞의 예제를 구현한 것입니다.  
  
 [!code-xaml[WPFAssemblyResourcesSnippets#LoadPageContentFileFromXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/CSharp/ResourcesSample/ApplicationGetContentStreamSnippetWindow.xaml#loadpagecontentfilefromxaml)]  
  
<a name="Site_of_Origin_Files"></a>
## <a name="site-of-origin-files"></a>원본 사이트 파일  
 리소스 파일은 <xref:System.Windows.Resources.AssemblyAssociatedContentFileAttribute>에 정의된 대로 함께 배포되는 어셈블리와 명시적 관계를 가짐을 가짐으로써 하지만 다음과 같이 어셈블리와 애플리케이션 데이터 파일 사이에 암시적 관계 또는 존재하지 않는 관계를 설정해야 할 경우가 종종 있습니다.  
  
- 컴파일 타임에 파일이 존재하지 않습니다.  
  
- 런타임까지 어셈블리에 필요한 파일을 모르는 경우.  
  
- 연결된 어셈블리를 재컴파일하지 않고 파일을 업데이트할 수 있어야 하는 경우.  
  
- 애플리케이션에서 오디오나 비디오와 같은 대용량 데이터 파일을 사용하며 사용자가 필요할 때에만 이를 다운로드하도록 하려는 경우.  
  
 file:/// 및 http:// 스키마와 같은 기존 URI 스키마를 사용하여 이러한 유형의 파일을 로드할 수 있습니다.  
  
 [!code-xaml[WPFAssemblyResourcesSnippets#AbsolutePackUriFileHttpReferenceXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/CSharp/ResourcesSample/AbsolutePackUriPage.xaml#absolutepackurifilehttpreferencexaml)]  
  
 하지만 file:/// 및 http:// 스키마를 사용하려면 애플리케이션이 완전히 신뢰되어야 합니다. 응용 프로그램이 인터넷 또는 인트라넷에서 시작된 XAML 브라우저 응용 프로그램(XBAP)이고 해당 위치에서 시작된 응용 프로그램에 대해 허용되는 권한 집합만 요청하는 경우 느슨한 파일은 응용 프로그램의 출처(시작 위치)를 참조하십시오. 이러한 파일을 *원본 파일의 사이트라고* 합니다.  
  
 원본 사이트 파일이 부분 신뢰 애플리케이션에서만 사용되는 것은 아니지만 부분 신뢰 애플리케이션에서는 원본 사이트 파일만을 사용할 수 있습니다. 완전 신뢰 애플리케이션의 경우에서도 빌드할 때 인식하지 못한 애플리케이션 데이터 파일을 로드해야 할 경우가 있습니다. 완전 신뢰 애플리케이션은 file:///을 사용할 수 있지만 이 경우 애플리케이션 데이터 파일이 애플리케이션 어셈블리와 같은 폴더 또는 하위 폴더에 설치될 수 있습니다. file:///에는 파일의 전체 경로를 사용해야 하기 때문에 file:///을 사용하는 방법보다 원본 사이트 참조를 사용하는 방법이 쉽습니다.  
  
> [!NOTE]
> 원본 파일의 사이트는 클라이언트 컴퓨터에서 XAML 브라우저 응용 프로그램(XBAP)으로 캐시되지 않지만 콘텐츠 파일은 캐시됩니다. 따라서 구체적으로 요청된 경우에만 다운로드됩니다. XAML 브라우저 응용 프로그램(XBAP) 응용 프로그램에 대용량 미디어 파일이 있는 경우 원본 파일 사이트로 구성하면 초기 응용 프로그램 실행이 훨씬 빨라지고 파일은 필요에 따라 다운로드됩니다.  
  
### <a name="configuring-site-of-origin-files"></a>원본 사이트 파일 구성  
 원본 파일의 사이트가 컴파일 타임에 존재하지 않거나 알 수 없는 경우 `XCopy` 명령줄 프로그램 또는 Microsoft Windows Installer를 사용하는 것을 포함하여 필요한 파일을 런타임에 사용할 수 있도록 하기 위해 기존의 배포 메커니즘을 사용해야 합니다.  
  
 컴파일 타임에 원본 사이트에 위치하고 싶지만 명시적 종속성을 피하려는 파일을 컴파일 타임에 알고 있는 경우 해당 파일을 MSBuild `None` 프로젝트에 항목으로 추가할 수 있습니다. 콘텐츠 파일과 마찬가지로 MSBuild `CopyToOutputDirectory` 특성을 설정하여 `Always` 원본 파일의 사이트가 값이나 `PreserveNewest` 값을 지정하여 빌드된 어셈블리와 관련된 위치에 복사되도록 지정해야 합니다.  
  
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
> Visual Studio에서 프로젝트에 파일을 추가하고 로 `Build Action` 설정하여 원본 파일의 사이트를 `None`만듭니다.  
  
 프로젝트가 빌드되면 MSBuild는 지정된 파일을 빌드 출력 폴더에 복사합니다.  
  
### <a name="using-site-of-origin-files"></a>원본 사이트 파일 사용  
 원본 파일의 사이트를 로드하려면 <xref:System.Windows.Application.GetRemoteStream%2A> <xref:System.Windows.Application> 원하는 원본 파일 사이트를 식별하는 팩 URI를 전달하는 클래스의 메서드를 호출할 수 있습니다. <xref:System.Windows.Application.GetRemoteStream%2A><xref:System.Windows.Resources.StreamResourceInfo> 원본 파일의 사이트를 a로 <xref:System.IO.Stream> 노출하고 해당 콘텐츠 형식을 설명하는 개체를 반환합니다.  
  
 예를 들어 다음 코드는 원본 <xref:System.Windows.Application.GetRemoteStream%2A> <xref:System.Windows.Controls.Page> 파일의 사이트를 로드하고 ()의 <xref:System.Windows.Controls.Frame> `pageFrame`내용으로 설정하는 데 사용하는 방법을 보여 주며 있습니다.  
  
 [!code-csharp[WPFAssemblyResourcesSnippets#LoadAPageSOOFileManuallyCODE](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/CSharp/ResourcesSample/SOOPage.xaml.cs#loadapagesoofilemanuallycode)]
 [!code-vb[WPFAssemblyResourcesSnippets#LoadAPageSOOFileManuallyCODE](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/VisualBasic/ResourcesSample/SOOPage.xaml.vb#loadapagesoofilemanuallycode)]  
  
 호출을 <xref:System.Windows.Application.GetRemoteStream%2A> 사용하면 <xref:System.IO.Stream>에 액세스할 수 있지만 을 설정하는 속성의 유형으로 변환하는 추가 작업을 수행해야 합니다. 대신 WPF가 코드를 사용하여 리소스 파일을 직접 <xref:System.IO.Stream> 코드 의 속성으로 로드하여 개열고 변환할 수 있도록 할 수 있습니다.  
  
 다음 예제에서는 코드를 사용하여 <xref:System.Windows.Controls.Page> <xref:System.Windows.Controls.Frame> ()에`pageFrame`직접 로드하는 방법을 보여 주며 있습니다.  
  
 [!code-csharp[WPFAssemblyResourcesSnippets#LoadPageSOOFileFromCODE](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/CSharp/ResourcesSample/SOOPage.xaml.cs#loadpagesoofilefromcode)]
 [!code-vb[WPFAssemblyResourcesSnippets#LoadPageSOOFileFromCODE](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/VisualBasic/ResourcesSample/SOOPage.xaml.vb#loadpagesoofilefromcode)]  
  
 다음 예제는 태그를 사용하여 앞의 예제를 구현한 것입니다.  
  
 [!code-xaml[WPFAssemblyResourcesSnippets#LoadPageSOOFileFromXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/CSharp/ResourcesSample/SOOPage.xaml#loadpagesoofilefromxaml)]  
  
<a name="Rebuilding_after_Changing_Build_Type"></a>
## <a name="rebuilding-after-changing-build-type"></a>빌드 형식 변경 후 다시 빌드  
 애플리케이션 데이터 파일의 빌드 형식을 변경한 뒤에는 변경 내용이 적용되도록 전체 애플리케이션을 다시 빌드해야 합니다. 애플리케이션만 빌드하면 변경 내용이 적용되지 않습니다.  
  
## <a name="see-also"></a>참고 항목

- [WPF의 Pack URI](pack-uris-in-wpf.md)
