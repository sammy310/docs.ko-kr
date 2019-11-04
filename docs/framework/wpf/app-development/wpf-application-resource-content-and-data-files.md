---
title: WPF 애플리케이션 리소스, 콘텐츠 및 데이터 파일
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
ms.openlocfilehash: a31dc2c5431c8201607462e8bdef4b8bae0fb41d
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/03/2019
ms.locfileid: "73460920"
---
# <a name="wpf-application-resource-content-and-data-files"></a>WPF 애플리케이션 리소스, 콘텐츠 및 데이터 파일
Microsoft Windows 응용 프로그램은 종종 [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)], 이미지, 비디오, 오디오 등의 실행 불가능 한 데이터를 포함 하는 파일에 의존 합니다. WPF (Windows Presentation Foundation)는 응용 프로그램 데이터 파일 이라고 하는 이러한 유형의 데이터 파일을 구성 하 고, 식별 하 고, 사용할 수 있는 특별 한 지원을 제공 합니다. 이러한 지원에는 다음을 포함한 특정 애플리케이션 데이터 파일 형식 집합이 포함됩니다.  
  
- **리소스 파일**: 실행 파일이 나 라이브러리 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] 어셈블리로 컴파일되는 데이터 파일입니다.  
  
- **콘텐츠 파일**: 실행 가능 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] 어셈블리와 명시적으로 연결 된 독립 실행형 데이터 파일입니다.  
  
- **원본 사이트 파일**: 실행 파일 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] 어셈블리와 연결 되지 않은 독립 실행형 데이터 파일입니다.  
  
 이 세 가지 파일 형식을 구분하는 한 가지 중요한 차이점은 리소스 파일과 콘텐츠 파일은 빌드할 때 인식된다는 점입니다. 어셈블리는 명시적으로 이 파일을 인식합니다. 그러나 원본 사이트 파일의 경우 어셈블리에 대 한 지식이 없거나 pack URI (uniform resource identifier) 참조를 통한 암시적 지식이 있을 수 있습니다. 후자의 경우 참조 된 원본 파일 파일이 실제로 존재 한다는 보장이 없습니다.  
  
 응용 프로그램 데이터 파일을 참조 하기 위해 Windows Presentation Foundation (WPF)는 Pack URI (uniform resource identifier)를 사용 합니다 .이 스키마는 [wpf의 Pack uri](pack-uris-in-wpf.md)에 자세히 설명 되어 있습니다.  
  
 이 항목에서는 애플리케이션 데이터 파일을 구성하고 사용하는 방법을 설명합니다.  

<a name="Resource_Files"></a>   
## <a name="resource-files"></a>리소스 파일  
 애플리케이션에서 애플리케이션 데이터 파일을 항상 사용할 수 있어야 하는 경우 가용성을 보장하는 유일한 방법은 데이터 파일을 애플리케이션의 주 실행 어셈블리 또는 참조되는 어셈블리 중 하나로 컴파일하는 것입니다. 이 유형의 응용 프로그램 데이터 파일을 *리소스 파일*이라고 합니다.  
  
 다음과 같은 경우에 리소스 파일을 사용해야 합니다.  
  
- 어셈블리로 컴파일한 뒤에는 리소스 파일의 콘텐츠를 업데이트할 필요가 없는 경우.  
  
- 파일 종속성의 수를 줄여 애플리케이션 배포의 복잡성을 줄이려는 경우.  
  
- 응용 프로그램 데이터 파일을 지역화할 수 있어야 합니다 ( [WPF 세계화 및 지역화 개요](../advanced/wpf-globalization-and-localization-overview.md)참조).  
  
> [!NOTE]
> 이 섹션에서 설명 하는 리소스 파일은 [XAML 리소스](../../../desktop-wpf/fundamentals/xaml-resources-define.md) 에 설명 된 리소스 파일과 다르며 [응용 프로그램 리소스 관리 (.net)](/visualstudio/ide/managing-application-resources-dotnet)에 설명 된 포함 된 리소스 또는 링크 된 리소스와 다릅니다.  
  
### <a name="configuring-resource-files"></a>리소스 파일 구성  
 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]에서 리소스 파일은 MSBuild (Microsoft build engine) 프로젝트에 `Resource` 항목으로 포함 되는 파일입니다.  
  
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
> Visual Studio에서는 프로젝트에 파일을 추가 하 고 해당 `Build Action`를 `Resource`으로 설정 하 여 리소스 파일을 만듭니다.  
  
 프로젝트가 빌드되면 MSBuild는 리소스를 어셈블리로 컴파일합니다.  
  
### <a name="using-resource-files"></a>리소스 파일 사용  
 리소스 파일을 로드 하려면 <xref:System.Windows.Application> 클래스의 <xref:System.Windows.Application.GetResourceStream%2A> 메서드를 호출 하 여 원하는 리소스 파일을 식별 하는 pack URI를 전달 합니다. <xref:System.Windows.Application.GetResourceStream%2A>는 리소스 파일을 <xref:System.IO.Stream>로 노출 하 고 해당 콘텐츠 형식을 설명 하는 <xref:System.Windows.Resources.StreamResourceInfo> 개체를 반환 합니다.  
  
 예를 들어 다음 코드는 <xref:System.Windows.Application.GetResourceStream%2A>를 사용 하 여 <xref:System.Windows.Controls.Page> 리소스 파일을 로드 하 고 <xref:System.Windows.Controls.Frame> (`pageFrame`)의 콘텐츠로 설정 하는 방법을 보여 줍니다.  
  
 [!code-csharp[WPFAssemblyResourcesSnippets#LoadAPageResourceFileManuallyCODE](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/CSharp/ResourcesSample/ApplicationGetResourceStreamSnippetWindow.xaml.cs#loadapageresourcefilemanuallycode)]
 [!code-vb[WPFAssemblyResourcesSnippets#LoadAPageResourceFileManuallyCODE](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/VisualBasic/ResourcesSample/ApplicationGetResourceStreamSnippetWindow.xaml.vb#loadapageresourcefilemanuallycode)]  
  
 <xref:System.Windows.Application.GetResourceStream%2A>를 호출 하 여 <xref:System.IO.Stream>에 대 한 액세스를 제공 하는 동안이를 설정할 속성의 형식으로 변환 하는 작업을 추가로 수행 해야 합니다. 대신 코드를 사용 하 여 리소스 파일을 형식의 속성에 직접 로드 하 여 <xref:System.IO.Stream>를 열고 변환 하는 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]을 수행할 수 있습니다.  
  
 다음 예제에서는 코드를 사용 하 여 <xref:System.Windows.Controls.Frame> (`pageFrame`)에 직접 <xref:System.Windows.Controls.Page>를 로드 하는 방법을 보여 줍니다.  
  
 [!code-csharp[WPFAssemblyResourcesSnippets#LoadPageResourceFileFromCODE](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/CSharp/ResourcesSample/ApplicationGetResourceStreamSnippetWindow.xaml.cs#loadpageresourcefilefromcode)]
 [!code-vb[WPFAssemblyResourcesSnippets#LoadPageResourceFileFromCODE](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/VisualBasic/ResourcesSample/ApplicationGetResourceStreamSnippetWindow.xaml.vb#loadpageresourcefilefromcode)]  
  
 다음 예제는 태그를 사용하여 앞의 예제를 구현한 것입니다.  
  
 [!code-xaml[WPFAssemblyResourcesSnippets#LoadPageResourceFileFromXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/CSharp/ResourcesSample/ApplicationGetResourceStreamSnippetWindow.xaml#loadpageresourcefilefromxaml)]  
  
### <a name="application-code-files-as-resource-files"></a>리소스 파일로 사용되는 애플리케이션 코드 파일  
 Windows, 페이지, 유동 문서 및 리소스 사전을 포함 하 여 pack Uri를 사용 하 여 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] 응용 프로그램 코드 파일의 특수 한 집합을 참조할 수 있습니다. 예를 들어 응용 프로그램이 시작 될 때 로드 하려는 창이 나 페이지를 참조 하는 pack URI를 사용 하 여 <xref:System.Windows.Application.StartupUri%2A?displayProperty=nameWithType> 속성을 설정할 수 있습니다.  
  
 [!code-xaml[WPFAssemblyResourcesSnippets#SetApplicationStartupURI](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/CSharp/ResourcesSample/App.xaml#setapplicationstartupuri)]  
  
 XAML 파일이 MSBuild 프로젝트에 `Page` 항목으로 포함 된 경우이 작업을 수행할 수 있습니다.  
  
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
> Visual Studio에서 프로젝트에 새 <xref:System.Windows.Window>, <xref:System.Windows.Navigation.NavigationWindow>, <xref:System.Windows.Controls.Page>, <xref:System.Windows.Documents.FlowDocument>또는 <xref:System.Windows.ResourceDictionary>를 추가 하면 마크업 파일에 대 한 `Build Action` 기본적으로 `Page`됩니다.  
  
 `Page` 항목이 있는 프로젝트가 컴파일되면 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 항목이 이진 형식으로 변환 되 고 연결 된 어셈블리로 컴파일됩니다. 결과적으로 이 파일을 일반적인 리소스 파일과 같은 방법으로 사용할 수 있습니다.  
  
> [!NOTE]
> [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 파일을 `Resource` 항목으로 구성 하 고 코드에 코드를 사용할 수 없는 경우 원시 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 원시 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]의 이진 버전이 아닌 어셈블리로 컴파일됩니다.  
  
<a name="Content_Files"></a>   
## <a name="content-files"></a>콘텐츠 파일  
 *콘텐츠 파일* 은 실행 가능한 어셈블리와 함께 느슨한 파일로 배포 됩니다. 어셈블리로 컴파일되지는 않지만 어셈블리는 각 콘텐츠 파일과 연결되는 메타데이터와 함께 컴파일됩니다.  
  
 데이터 파일을 사용하는 어셈블리를 재컴파일하지 않고 업데이트하고자 하는 애플리케이션 데이터 파일을 애플리케이션에서 필요로 할 때는 콘텐츠 파일을 사용해야 합니다.  
  
### <a name="configuring-content-files"></a>콘텐츠 파일 구성  
 프로젝트에 콘텐츠 파일을 추가 하려면 응용 프로그램 데이터 파일을 `Content` 항목으로 포함 해야 합니다. 또한 콘텐츠 파일이 어셈블리로 직접 컴파일되지 않으므로 MSBuild `CopyToOutputDirectory` metadata 요소를 설정 하 여 콘텐츠 파일이 빌드된 어셈블리에 상대적인 위치로 복사 되도록 지정 해야 합니다. 프로젝트를 빌드할 때마다 리소스를 빌드 출력 폴더로 복사 하려면 `CopyToOutputDirectory` metadata 요소를 `Always` 값으로 설정 합니다. 그렇지 않으면 `PreserveNewest` 값을 사용 하 여 최신 버전의 리소스만 빌드 출력 폴더에 복사 되도록 할 수 있습니다.  
  
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
> Visual Studio에서는 프로젝트에 파일을 추가 하 고 해당 `Build Action` `Content`로 설정 하 고 `Copy to Output Directory`를 `Copy always` (`Always`와 같음) 및 `Copy if newer` (`PreserveNewest`와 같음)로 설정 하 여 콘텐츠 파일을 만듭니다.  
  
 프로젝트가 빌드되면 <xref:System.Windows.Resources.AssemblyAssociatedContentFileAttribute> 특성이 각 콘텐츠 파일에 대 한 어셈블리의 메타 데이터로 컴파일됩니다.  
  
 `[assembly: AssemblyAssociatedContentFile("ContentFile.xaml")]`  
  
 <xref:System.Windows.Resources.AssemblyAssociatedContentFileAttribute> 값은 프로젝트에서 해당 위치에 상대적인 콘텐츠 파일 경로를 의미 합니다. 예를 들어 콘텐츠 파일이 프로젝트 하위 폴더에 있는 경우 추가 경로 정보가 <xref:System.Windows.Resources.AssemblyAssociatedContentFileAttribute> 값에 통합 됩니다.  
  
 `[assembly: AssemblyAssociatedContentFile("Resources/ContentFile.xaml")]`  
  
 <xref:System.Windows.Resources.AssemblyAssociatedContentFileAttribute> 값은 빌드 출력 폴더의 콘텐츠 파일에 대 한 경로 값 이기도 합니다.  
  
### <a name="using-content-files"></a>콘텐츠 파일 사용  
 콘텐츠 파일을 로드 하려면 <xref:System.Windows.Application> 클래스의 <xref:System.Windows.Application.GetContentStream%2A> 메서드를 호출 하 여 원하는 콘텐츠 파일을 식별 하는 pack URI를 전달 합니다. <xref:System.Windows.Application.GetContentStream%2A>는 콘텐츠 파일을 <xref:System.IO.Stream>로 노출 하 고 해당 콘텐츠 형식을 설명 하는 <xref:System.Windows.Resources.StreamResourceInfo> 개체를 반환 합니다.  
  
 예를 들어 다음 코드는 <xref:System.Windows.Application.GetContentStream%2A>를 사용 하 여 <xref:System.Windows.Controls.Page> 콘텐츠 파일을 로드 하 고 <xref:System.Windows.Controls.Frame> (`pageFrame`)의 콘텐츠로 설정 하는 방법을 보여 줍니다.  
  
 [!code-csharp[WPFAssemblyResourcesSnippets#LoadAPageContentFileManuallyCODE](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/CSharp/ResourcesSample/ApplicationGetContentStreamSnippetWindow.xaml.cs#loadapagecontentfilemanuallycode)]
 [!code-vb[WPFAssemblyResourcesSnippets#LoadAPageContentFileManuallyCODE](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/VisualBasic/ResourcesSample/ApplicationGetContentStreamSnippetWindow.xaml.vb#loadapagecontentfilemanuallycode)]  
  
 <xref:System.Windows.Application.GetContentStream%2A>를 호출 하 여 <xref:System.IO.Stream>에 대 한 액세스를 제공 하는 동안이를 설정할 속성의 형식으로 변환 하는 작업을 추가로 수행 해야 합니다. 대신 코드를 사용 하 여 리소스 파일을 형식의 속성에 직접 로드 하 여 <xref:System.IO.Stream>를 열고 변환 하는 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]을 수행할 수 있습니다.  
  
 다음 예제에서는 코드를 사용 하 여 <xref:System.Windows.Controls.Frame> (`pageFrame`)에 직접 <xref:System.Windows.Controls.Page>를 로드 하는 방법을 보여 줍니다.  
  
 [!code-csharp[WPFAssemblyResourcesSnippets#LoadPageContentFileFromCODE](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/CSharp/ResourcesSample/ApplicationGetContentStreamSnippetWindow.xaml.cs#loadpagecontentfilefromcode)]
 [!code-vb[WPFAssemblyResourcesSnippets#LoadPageContentFileFromCODE](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/VisualBasic/ResourcesSample/ApplicationGetContentStreamSnippetWindow.xaml.vb#loadpagecontentfilefromcode)]  
  
 다음 예제는 태그를 사용하여 앞의 예제를 구현한 것입니다.  
  
 [!code-xaml[WPFAssemblyResourcesSnippets#LoadPageContentFileFromXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/CSharp/ResourcesSample/ApplicationGetContentStreamSnippetWindow.xaml#loadpagecontentfilefromxaml)]  
  
<a name="Site_of_Origin_Files"></a>   
## <a name="site-of-origin-files"></a>원본 사이트 파일  
 리소스 파일은 <xref:System.Windows.Resources.AssemblyAssociatedContentFileAttribute>에서 정의한 대로 함께 배포 되는 어셈블리와 명시적으로 관계가 있습니다. 하지만 다음과 같이 어셈블리와 애플리케이션 데이터 파일 사이에 암시적 관계 또는 존재하지 않는 관계를 설정해야 할 경우가 종종 있습니다.  
  
- 파일은 컴파일 시간에 존재 하지 않습니다.  
  
- 런타임까지 어셈블리에 필요한 파일을 모르는 경우.  
  
- 연결된 어셈블리를 재컴파일하지 않고 파일을 업데이트할 수 있어야 하는 경우.  
  
- 애플리케이션에서 오디오나 비디오와 같은 대용량 데이터 파일을 사용하며 사용자가 필요할 때에만 이를 다운로드하도록 하려는 경우.  
  
 File:///및 http://스키마와 같은 기존 URI 스키마를 사용 하 여 이러한 형식의 파일을 로드할 수 있습니다.  
  
 [!code-xaml[WPFAssemblyResourcesSnippets#AbsolutePackUriFileHttpReferenceXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/CSharp/ResourcesSample/AbsolutePackUriPage.xaml#absolutepackurifilehttpreferencexaml)]  
  
 하지만 file:/// 및 http:// 스키마를 사용하려면 애플리케이션이 완전히 신뢰되어야 합니다. 응용 프로그램이 인터넷 또는 인트라넷에서 시작 된 XBAP (XAML 브라우저 응용 프로그램)이 고, 해당 위치에서 시작 된 응용 프로그램에 허용 되는 사용 권한 집합만 요청 하는 경우 느슨한 파일은 응용 프로그램의 원본 사이트 (시작 위치)입니다. 이러한 파일은 *원본 사이트* 파일 이라고 합니다.  
  
 원본 사이트 파일이 부분 신뢰 애플리케이션에서만 사용되는 것은 아니지만 부분 신뢰 애플리케이션에서는 원본 사이트 파일만을 사용할 수 있습니다. 완전 신뢰 애플리케이션의 경우에서도 빌드할 때 인식하지 못한 애플리케이션 데이터 파일을 로드해야 할 경우가 있습니다. 완전 신뢰 애플리케이션은 file:///을 사용할 수 있지만 이 경우 애플리케이션 데이터 파일이 애플리케이션 어셈블리와 같은 폴더 또는 하위 폴더에 설치될 수 있습니다. file:///에는 파일의 전체 경로를 사용해야 하기 때문에 file:///을 사용하는 방법보다 원본 사이트 참조를 사용하는 방법이 쉽습니다.  
  
> [!NOTE]
> 원본 사이트 파일은 클라이언트 컴퓨터의 XBAP (XAML 브라우저 응용 프로그램)를 사용 하 여 캐시 되지 않지만 콘텐츠 파일은입니다. 따라서 구체적으로 요청된 경우에만 다운로드됩니다. XBAP (XAML 브라우저 응용 프로그램) 응용 프로그램에 큰 미디어 파일이 있는 경우 이러한 파일을 원본 사이트로 구성 하면 초기 응용 프로그램 시작 속도가 훨씬 빨라지고 요청 시에만 파일이 다운로드 됩니다.  
  
### <a name="configuring-site-of-origin-files"></a>원본 사이트 파일 구성  
 원본 사이트 파일이 존재 하지 않거나 컴파일할 때 알 수 없는 경우 `XCopy` 명령줄 프로그램 또는 Microsoft Windows를 사용 하 여 필요한 파일을 런타임에 사용할 수 있도록 하기 위해 기존 배포 메커니즘을 사용 해야 합니다. Installer.  
  
 컴파일 시간에서 원본 사이트에 배치 하려는 파일을 알 수 있지만 명시적 종속성을 방지 하려는 경우 해당 파일을 MSBuild 프로젝트에 `None` 항목으로 추가할 수 있습니다. 콘텐츠 파일과 마찬가지로 MSBuild `CopyToOutputDirectory` 특성을 설정 하 여 원본 사이트 파일이 빌드된 어셈블리에 상대적인 위치로 복사 되도록 지정 하 고 `Always` 값 또는 `PreserveNewest` 값을 지정 해야 합니다.  
  
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
> Visual Studio에서는 프로젝트에 파일을 추가 하 고 해당 `Build Action`를 `None`으로 설정 하 여 원본 사이트 파일을 만듭니다.  
  
 프로젝트가 빌드되면 MSBuild는 지정 된 파일을 빌드 출력 폴더에 복사 합니다.  
  
### <a name="using-site-of-origin-files"></a>원본 사이트 파일 사용  
 원본 사이트 파일을 로드 하려면 <xref:System.Windows.Application> 클래스의 <xref:System.Windows.Application.GetRemoteStream%2A> 메서드를 호출 하 여 원하는 원본 사이트 파일을 식별 하는 pack URI를 전달 합니다. <xref:System.Windows.Application.GetRemoteStream%2A> <xref:System.Windows.Resources.StreamResourceInfo> 개체를 반환 합니다 .이 개체는 원본 사이트 파일을 <xref:System.IO.Stream> 표시 하 고 해당 콘텐츠 형식을 설명 합니다.  
  
 예를 들어 다음 코드는 <xref:System.Windows.Application.GetRemoteStream%2A>를 사용 하 여 <xref:System.Windows.Controls.Page> 원본 파일을 로드 하 고 <xref:System.Windows.Controls.Frame> (`pageFrame`)의 콘텐츠로 설정 하는 방법을 보여 줍니다.  
  
 [!code-csharp[WPFAssemblyResourcesSnippets#LoadAPageSOOFileManuallyCODE](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/CSharp/ResourcesSample/SOOPage.xaml.cs#loadapagesoofilemanuallycode)]
 [!code-vb[WPFAssemblyResourcesSnippets#LoadAPageSOOFileManuallyCODE](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/VisualBasic/ResourcesSample/SOOPage.xaml.vb#loadapagesoofilemanuallycode)]  
  
 <xref:System.Windows.Application.GetRemoteStream%2A>를 호출 하 여 <xref:System.IO.Stream>에 대 한 액세스를 제공 하는 동안이를 설정할 속성의 형식으로 변환 하는 작업을 추가로 수행 해야 합니다. 대신 코드를 사용 하 여 리소스 파일을 형식의 속성에 직접 로드 하 여 <xref:System.IO.Stream>를 열고 변환 하는 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]을 수행할 수 있습니다.  
  
 다음 예제에서는 코드를 사용 하 여 <xref:System.Windows.Controls.Frame> (`pageFrame`)에 직접 <xref:System.Windows.Controls.Page>를 로드 하는 방법을 보여 줍니다.  
  
 [!code-csharp[WPFAssemblyResourcesSnippets#LoadPageSOOFileFromCODE](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/CSharp/ResourcesSample/SOOPage.xaml.cs#loadpagesoofilefromcode)]
 [!code-vb[WPFAssemblyResourcesSnippets#LoadPageSOOFileFromCODE](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/VisualBasic/ResourcesSample/SOOPage.xaml.vb#loadpagesoofilefromcode)]  
  
 다음 예제는 태그를 사용하여 앞의 예제를 구현한 것입니다.  
  
 [!code-xaml[WPFAssemblyResourcesSnippets#LoadPageSOOFileFromXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/CSharp/ResourcesSample/SOOPage.xaml#loadpagesoofilefromxaml)]  
  
<a name="Rebuilding_after_Changing_Build_Type"></a>   
## <a name="rebuilding-after-changing-build-type"></a>빌드 형식 변경 후 다시 빌드  
 애플리케이션 데이터 파일의 빌드 형식을 변경한 뒤에는 변경 내용이 적용되도록 전체 애플리케이션을 다시 빌드해야 합니다. 애플리케이션만 빌드하면 변경 내용이 적용되지 않습니다.  
  
## <a name="see-also"></a>참조

- [WPF의 Pack URI](pack-uris-in-wpf.md)
