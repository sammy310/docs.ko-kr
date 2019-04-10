---
title: WPF의 Pack URI
ms.date: 03/30/2017
helpviewer_keywords:
- pack URI scheme [WPF]
- loading embedded resources [WPF]
- URIs (Uniform Resource Identifiers)
- Uniform Resource Identifiers (URIs)
- loading non-resource files
- application management [WPF]
ms.assetid: 43adb517-21a7-4df3-98e8-09e9cdf764c4
ms.openlocfilehash: a36cdf9f8cce935c8310e2ce9ffc79f67d077fe6
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59225146"
---
# <a name="pack-uris-in-wpf"></a>WPF의 Pack URI
Windows Presentation Foundation (WPF), [!INCLUDE[TLA#tla_uri#plural](../../../../includes/tlasharptla-urisharpplural-md.md)] 식별 하 고 다음을 비롯 한 다양 한 방식 파일을 로드 하는 데 사용 됩니다.  
  
-   지정 된 [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] 표시할 때 응용 프로그램이 처음 시작 합니다.  
  
-   이미지 로드  
  
-   페이지 탐색  
  
-   비실행 데이터 파일 로드  
  
 또한 [!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)] 식별 하 고 다양 한 다음을 비롯 한 위치에서에서 파일 로드를 사용할 수 있습니다.  
  
-   현재 어셈블리입니다.  
  
-   참조된 어셈블리  
  
-   어셈블리에 상대적인 위치  
  
-   애플리케이션의 원본 사이트  
  
 식별 하 고 이러한 위치에서 이러한 형식의 파일을 로드 하는 것에 대 한 일관 된 메커니즘을 제공할 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] 확장성을 이용 합니다 *pack URI 체계*합니다. 이 항목에서는 스키마의 개요를 제공, 팩을 생성 하는 방법에 설명 [!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)] 는 다양 한 시나리오에 대 한 설명 absolute 및 relative [!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)] 하 고 [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] 팩을 사용 하는 방법을 보여 주기 전에 해상도 [!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)] 두 태그에서 및 코드입니다.  

<a name="The_Pack_URI_Scheme"></a>   
## <a name="the-pack-uri-scheme"></a>Pack URI 체계  
 Pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] 체계를 사용 하 여 합니다 [Open Packaging Conventions](https://go.microsoft.com/fwlink/?LinkID=71255) 구성 및 콘텐츠 식별에 대 한 모델을 설명 하는 (OPC) 사양입니다. 이 모델의 주요 요소는 패키지와 파트 위치를 *패키지* 인지 하는 논리 컨테이너 하나에 대 한 더 많은 논리 *파트*합니다. 다음 그림에서는 이 개념을 보여 줍니다.  
  
 ![패키지 및 파트 다이어그램](./media/pack-uris-in-wpf/wpf-package-parts-diagram.png)  
  
 OPC 사양 부분을 식별 하려면 RFC 2396의 확장성을 이용 합니다 (리소스 URI (Uniform Identifier): 팩을 정의 하려면 제네릭 구문) [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] 구성표입니다.  
  
 지정 된 구성표를 [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] 접두사로 정의 됩니다 http, ftp 및 file은 잘 알려진 예입니다. Pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] 체계 "pack"을 사용 하 여 해당 체계로 및 두 개의 구성 요소를 포함 합니다: 인증 기관과 경로. 다음은 pack에 대 한 형식 [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)]합니다.  
  
 pack://*authority*/*path*
  
 *기관* 파트에서 포함 된 패키지의 유형을 지정 하는 동안 합니다 *경로* 패키지 내의 파트의 위치를 지정 합니다.  
  
 다음 그림에서는 이 개념을 보여 줍니다.  
  
 ![패키지, 권한 및 경로의 관계](./media/pack-uris-in-wpf/wpf-relationship-diagram.png)  
  
 패키지와 파트는 애플리케이션 및 파일과 유사합니다. 즉, 애플리케이션(패키지)은 다음을 비롯한 하나 이상의 파일(파트)을 포함할 수 있습니다.  
  
-   로컬 어셈블리로 컴파일되는 리소스 파일  
  
-   참조된 어셈블리로 컴파일되는 리소스 파일  
  
-   참조하는 어셈블리로 컴파일되는 리소스 파일  
  
-   콘텐츠 파일  
  
-   원본 사이트 파일  
  
 이러한 종류의 파일에 액세스 하려면 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] 두 기관을 지원: 응용 프로그램: / / / 및 siteoforigin:///: / / /입니다. application:/// 인증 기관은 리소스 및 콘텐츠 파일을 비롯하여 컴파일 시 알려진 애플리케이션 데이터 파일을 식별합니다. siteoforigin:/// 인증 기관은 원본 사이트 파일을 식별합니다. 다음 그림에서는 각 인증 기관의 범위를 보여 줍니다.  
  
 ![Pack URI 다이어그램](./media/pack-uris-in-wpf/wpf-pack-uri-scheme.png)  
  
> [!NOTE]
>  팩의 인증 기관 구성 요소가 [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] 포함 된 [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] 패키지를 가리키는 RFC 2396을 따라야 합니다. 또한 “/” 문자를 “,” 문자로 바꾸고 “%” 및 “?” 같은 예약 문자는 이스케이프해야 합니다. 자세한 내용은 OPC를 참조하세요.  
  
 다음 섹션에서는 팩을 생성 하는 방법에 설명 [!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)] 적절 한 경로와 함께이 두 인증 기관과 리소스, 콘텐츠 및 원본 사이트 파일을 식별 하는 데 사용 합니다.  
  
<a name="Resource_File_Pack_URIs___Local_Assembly"></a>   
## <a name="resource-file-pack-uris"></a>리소스 파일 Pack URI  
 리소스 파일으로 구성 된 [!INCLUDE[TLA2#tla_msbuild](../../../../includes/tla2sharptla-msbuild-md.md)]`Resource` 항목 및 어셈블리에 컴파일됩니다. [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] 팩의 생성을 지원 [!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)] 리소스 파일을 로컬 어셈블리로 컴파일된 되거나 로컬 어셈블리에서 참조 되는 어셈블리로 컴파일되는 데 사용할 수 있는 합니다.  
  
<a name="Local_Assembly_Resource_File"></a>   
### <a name="local-assembly-resource-file"></a>로컬 어셈블리 리소스 파일  
 Pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] 리소스에 대 한 로컬 어셈블리로 컴파일되는 파일은 다음 인증 기관과 경로 사용 합니다.  
  
-   **인증 기관**: application:///  
  
-   **경로**: 로컬 어셈블리 프로젝트 폴더 루트에 상대적인 경로 포함 하는 리소스 파일의 이름입니다.  
  
 다음 예제에서는 pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] 에 대 한는 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 로컬 어셈블리의 프로젝트 폴더의 루트에 있는 리소스 파일입니다.  
  
 `pack://application:,,,/ResourceFile.xaml`  
  
 다음 예제에서는 pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] 에 대 한는 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 로컬 어셈블리의 프로젝트 폴더의 하위 폴더에 있는 리소스 파일입니다.  
  
 `pack://application:,,,/Subfolder/ResourceFile.xaml`  
  
<a name="Resource_File_Pack_URIs___Referenced_Assembly"></a>   
### <a name="referenced-assembly-resource-file"></a>참조된 어셈블리 리소스 파일  
 Pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] 리소스에 대 한 참조 된 어셈블리로 컴파일되는 파일은 다음 인증 기관과 경로 사용 합니다.  
  
-   **인증 기관**: application:///  
  
-   **경로**: 참조 된 어셈블리로 컴파일되는 리소스 파일의 이름입니다. 경로는 다음 형식을 따라야 합니다.  
  
     *AssemblyShortName*{*;Version*]{*;PublicKey*];component/*Path*  
  
    -   **AssemblyShortName**: 참조된 어셈블리에 대한 약식 이름  
  
    -   **;Version**[옵션]: 리소스 파일을 포함하는 참조된 어셈블리의 버전. 동일한 약식 이름을 갖는 두 개 이상의 참조된 어셈블리가 로드된 경우 사용됩니다.  
  
    -   **;PublicKey**[옵션]: 참조된 어셈블리를 서명하는 데 사용된 공개 키. 동일한 약식 이름을 갖는 두 개 이상의 참조된 어셈블리가 로드된 경우 사용됩니다.  
  
    -   **;component**: 참조되는 어셈블리가 로컬 어셈블리에서 참조된다는 것을 지정  
  
    -   **/Path**: 참조된 어셈블리 프로젝트 폴더의 루트에 상대적인 경로를 포함한 리소스 파일의 이름  
  
 다음 예제에서는 pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] 에 대 한는 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 참조 된 어셈블리의 프로젝트 폴더의 루트에 있는 리소스 파일입니다.  
  
 `pack://application:,,,/ReferencedAssembly;component/ResourceFile.xaml`  
  
 다음 예제에서는 pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] 에 대 한는 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 참조 된 어셈블리의 프로젝트 폴더의 하위 폴더에 있는 리소스 파일입니다.  
  
 `pack://application:,,,/ReferencedAssembly;component/Subfolder/ResourceFile.xaml`  
  
 다음 예제에서는 pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] 에 대 한는 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 참조, 버전별 어셈블리의 프로젝트 폴더의 루트 폴더에 있는 리소스 파일입니다.  
  
 `pack://application:,,,/ReferencedAssembly;v1.0.0.1;component/ResourceFile.xaml`  
  
 pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] 참조 된 어셈블리 리소스 파일의 구문에만 사용할 수: / / / 기관. 예를 들어, 다음에서 지원 되지 않습니다 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]합니다.  
  
 `pack://siteoforigin:,,,/SomeAssembly;component/ResourceFile.xaml`  
  
<a name="Content_File_Pack_URIs"></a>   
## <a name="content-file-pack-uris"></a>콘텐츠 파일 Pack URI  
 Pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] 는 다음 인증 기관과 경로 사용 하는 콘텐츠 파일:  
  
-   **인증 기관**: application:///  
  
-   **경로**: 응용 프로그램의 주 실행 어셈블리의 파일 시스템 위치에 상대적인 경로 포함 하는 콘텐츠 파일의 이름입니다.  
  
 다음 예제에서는 pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] 에 대 한는 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 실행 가능한 어셈블리와 동일한 폴더에 있는 콘텐츠 파일입니다.  
  
 `pack://application:,,,/ContentFile.xaml`  
  
 다음 예제에서는 pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] 에 대 한는 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 응용 프로그램의 실행 가능한 어셈블리에 상대적인 하위 폴더에 있는 콘텐츠 파일입니다.  
  
 `pack://application:,,,/Subfolder/ContentFile.xaml`  
  
> [!NOTE]
>  [!INCLUDE[TLA2#tla_html](../../../../includes/tla2sharptla-html-md.md)] 콘텐츠 파일을 탐색할 수 없습니다. 합니다 [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] 구성표에 대 한 탐색 지원 [!INCLUDE[TLA2#tla_html](../../../../includes/tla2sharptla-html-md.md)] 원본 사이트에 있는 파일입니다.  
  
<a name="The_siteoforigin_____Authority"></a>   
## <a name="site-of-origin-pack-uris"></a>원본 사이트 Pack URI  
 Pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] 원본 사이트에 대 한 파일은 다음 인증 기관과 경로 사용 합니다.  
  
-   **인증 기관**: siteoforigin:///  
  
-   **경로**: 사이트는 실행 가능 어셈블리가 시작 된 위치에 상대적인 경로 포함 한 원본 파일의 이름입니다.  
  
 다음 예제에서는 pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] 에 대 한는 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 원본 사이트 파일을 실행 가능 어셈블리가 시작 된 위치에 저장 합니다.  
  
 `pack://siteoforigin:,,,/SiteOfOriginFile.xaml`  
  
 다음 예제에서는 pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] 에 대 한는 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 원본 사이트 파일을 응용 프로그램의 실행 가능 어셈블리가 시작 된 위치를 기준으로 하는 하위 폴더에 저장 합니다.  
  
 `pack://siteoforigin:,,,/Subfolder/SiteOfOriginFile.xaml`  
  
<a name="Page_Files"></a>   
## <a name="page-files"></a>페이지 파일  
 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 으로 구성 된 파일 [!INCLUDE[TLA2#tla_msbuild](../../../../includes/tla2sharptla-msbuild-md.md)]`Page` 항목 리소스 파일과 같은 방식으로 어셈블리로 컴파일됩니다. 따라서 [!INCLUDE[TLA2#tla_msbuild](../../../../includes/tla2sharptla-msbuild-md.md)]`Page` 팩을 사용 하 여 항목을 식별할 수 있습니다 [!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)] 리소스 파일에 대 한 합니다.  
  
 유형에 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 일반적으로 구성 된 파일 [!INCLUDE[TLA2#tla_msbuild](../../../../includes/tla2sharptla-msbuild-md.md)]`Page` 항목에 해당 루트 요소로 다음 중 하나:  
  
-   <xref:System.Windows.Window?displayProperty=nameWithType>  
  
-   <xref:System.Windows.Controls.Page?displayProperty=nameWithType>  
  
-   <xref:System.Windows.Navigation.PageFunction%601?displayProperty=nameWithType>  
  
-   <xref:System.Windows.ResourceDictionary?displayProperty=nameWithType>  
  
-   <xref:System.Windows.Documents.FlowDocument?displayProperty=nameWithType>  
  
-   <xref:System.Windows.Controls.UserControl?displayProperty=nameWithType>  
  
<a name="Absolute_vs_Relative_Pack_URIs"></a>   
## <a name="absolute-vs-relative-pack-uris"></a>절대 및 상대 Pack URI  
 정규화 된 pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] 체계, 인증 기관 및 경로 포함 하며 절대 pack 것으로 간주 됩니다 [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)]합니다. 개발자에 게 쉽게 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 요소를 일반적으로 상대 pack 사용 하 여 적절 한 특성을 설정 하는 데 허용 [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)], 경로만 포함 합니다.  
  
 예를 들어 다음과 같은 절대 pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] 로컬 어셈블리에 리소스 파일에 대 한 합니다.  
  
 `pack://application:,,,/ResourceFile.xaml`  
  
 상대 pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] 이 리소스를 참조 하는 파일에는 다음 것입니다.  
  
 `/ResourceFile.xaml`  
  
> [!NOTE]
>  원본 사이트 파일에 어셈블리를 사용 하 여 연결 되어 있지 않으므로 참조할 수를 절대 pack을 사용 하 여 [!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)]입니다.  
  
 기본적으로 상대 pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] 태그 또는 참조를 포함 하는 코드의 위치에 상대적인 것으로 간주 됩니다. 그러나 앞에 백슬래시를 사용 하는 경우 상대 pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] 참조 한 다음 응용 프로그램의 루트에 상대적인 것으로 간주 됩니다. 예를 들어 다음과 같은 프로젝트 구조를 가정해 봅니다.  
  
 `App.xaml`  
  
 `Page2.xaml`  
  
 `\SubFolder`  
  
 `+ Page1.xaml`  
  
 `+ Page2.xaml`  
  
 Page1.xaml를 [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] 를 참조 하는 *루트*\SubFolder\Page2.xaml, 참조는 다음과 같은 상대 pack을 사용할 수 [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)]입니다.  
  
 `Page2.xaml`  
  
 Page1.xaml를 [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] 를 참조 하는 *루트*\Page2.xaml, 참조는 다음과 같은 상대 pack을 사용할 수 [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)]입니다.  
  
 `/Page2.xaml`  
  
<a name="Pack_URI_Resolution"></a>   
## <a name="pack-uri-resolution"></a>Pack URI 확인  
 팩 형식의 [!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)] 팩용 수 있도록 [!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)] 다른 유형의 파일을 동일 하 게 표시 합니다. 예를 들어 다음과 같은 절대 pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)]합니다.  
  
 `pack://application:,,,/ResourceOrContentFile.xaml`  
  
 이 절대 pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] 로컬 어셈블리에 리소스 파일 또는 콘텐츠 파일을 참조할 수 있습니다. 다음과 같은 상대에 대 한 마찬가지 [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)]합니다.  
  
 `/ResourceOrContentFile.xaml`  
  
 형식의 파일을 확인 하기 위해 팩을 [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] 를 참조 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] 확인 [!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)] 로컬 어셈블리와 같은 경험적 접근을 사용 하 여 콘텐츠 파일에서 리소스 파일:  
  
1.  프로브에 대 한 어셈블리 메타 데이터를 <xref:System.Windows.Resources.AssemblyAssociatedContentFileAttribute> 팩은 일치 하는 특성 [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)]합니다.  
  
2.  경우는 <xref:System.Windows.Resources.AssemblyAssociatedContentFileAttribute> 특성이 있으면 pack 경로의 [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] 콘텐츠 파일을 가리킵니다.  
  
3.  경우는 <xref:System.Windows.Resources.AssemblyAssociatedContentFileAttribute> 특성이 없으면 로컬 어셈블리로 컴파일되는 리소스 파일 집합을 조사 합니다.  
  
4.  팩의 경로 일치 하는 리소스 파일이 있으면 [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] 발견 되는 팩 경로의 [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] 리소스 파일을 가리킵니다.  
  
5.  리소스가 없는 경우, 내부적으로 만든 <xref:System.Uri> 올바르지 않습니다.  
  
 [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] 해결 방법에 대 한 적용 되지 않습니다 [!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)] 는 다음을 참조 하십시오.  
  
-   참조 된 어셈블리의 콘텐츠 파일: 하 여 이러한 파일 형식은 지원 되지 않습니다 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]합니다.  
  
-   참조 된 어셈블리에 포함 된 파일: [!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)] 식별 하는 참조 된 어셈블리의 이름을 둘 다 포함 되어 있으므로 고유 하며 `;component` 접미사.  
  
-   원본 사이트 파일: [!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)] 식별 하는 팩에서 식별할 수 있는 유일한 파일 이므로 고유 [!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)] siteoforigin:/// 인증 포함 된: / / / 기관.  
  
 팩는 한 가지 단순화 [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] 확인 코드가 리소스 및 콘텐츠 파일의 위치와 다소 독립적일 수 있습니다. 예를 들어 팩은 콘텐츠 파일을 다시 구성 되는 로컬 어셈블리의 리소스 파일이 있다고 [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] 팩을 사용 하는 코드와 마찬가지로 똑같이 리소스 유지에 대 한 [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)]합니다.  
  
<a name="Programming_with_Pack_URIs"></a>   
## <a name="programming-with-pack-uris"></a>Pack URI를 사용한 프로그래밍  
 많은 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] 팩을 사용 하 여 설정할 수 있는 속성을 구현 하는 클래스 [!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)]등.  
  
-   <xref:System.Windows.Application.StartupUri%2A?displayProperty=nameWithType>  
  
-   <xref:System.Windows.Controls.Frame.Source%2A?displayProperty=nameWithType>  
  
-   <xref:System.Windows.Navigation.NavigationWindow.Source%2A?displayProperty=nameWithType>  
  
-   <xref:System.Windows.Documents.Hyperlink.NavigateUri%2A?displayProperty=nameWithType>  
  
-   <xref:System.Windows.Window.Icon%2A?displayProperty=nameWithType>  
  
-   <xref:System.Windows.Controls.Image.Source%2A?displayProperty=nameWithType>  
  
 이러한 속성을 태그와 코드 모두에서 설정할 수 있습니다. 이 섹션에서는 두 경우에 대한 기본 구조를 설명한 다음 일반적인 시나리오 예제를 보여 줍니다.  
  
<a name="Using_Pack_URIs_in_Markup"></a>   
### <a name="using-pack-uris-in-markup"></a>태그에서 Pack URI 사용  
 Pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] 팩을 사용 하 여 특성의 요소를 설정 하 여 태그에 지정 된 [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)]합니다. 예를 들어:  
  
 `<element attribute="pack://application:,,,/File.xaml" />`  
  
 테이블 1에서는 다양 한 절대 pack 보여 줍니다. [!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)] 는 태그에 지정할 수 있습니다.  
  
 표 1: 태그의 절대 Pack Uri  
  
|파일|절대 pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)]|  
|----------|-------------------------------------------------------------------------------------------------------------------------|  
|리소스 파일 - 로컬 어셈블리|`"pack://application:,,,/ResourceFile.xaml"`|  
|하위 폴더의 리소스 파일 - 로컬 어셈블리|`"pack://application:,,,/Subfolder/ResourceFile.xaml"`|  
|리소스 파일 - 참조된 어셈블리|`"pack://application:,,,/ReferencedAssembly;component/ResourceFile.xaml"`|  
|참조된 어셈블리의 하위 폴더에 있는 리소스 파일|`"pack://application:,,,/ReferencedAssembly;component/Subfolder/ResourceFile.xaml"`|  
|버전이 있는 참조된 어셈블리의 리소스 파일|`"pack://application:,,,/ReferencedAssembly;v1.0.0.0;component/ResourceFile.xaml"`|  
|콘텐츠 파일|`"pack://application:,,,/ContentFile.xaml"`|  
|하위 폴더의 콘텐츠 파일|`"pack://application:,,,/Subfolder/ContentFile.xaml"`|  
|원본 사이트 파일|`"pack://siteoforigin:,,,/SOOFile.xaml"`|  
|하위 폴더의 원본 사이트 파일|`"pack://siteoforigin:,,,/Subfolder/SOOFile.xaml"`|  
  
 테이블 2에서는 다양 한 상대 pack 보여 줍니다. [!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)] 는 태그에 지정할 수 있습니다.  
  
 표 2: 태그의 상대 Pack Uri  
  
|파일|상대 pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)]|  
|----------|-------------------------------------------------------------------------------------------------------------------------|  
|로컬 어셈블리의 리소스 파일|`"/ResourceFile.xaml"`|  
|로컬 어셈블리의 하위 폴더에 있는 리소스 파일|`"/Subfolder/ResourceFile.xaml"`|  
|참조된 어셈블리의 리소스 파일|`"/ReferencedAssembly;component/ResourceFile.xaml"`|  
|참조된 어셈블리의 하위 폴더에 있는 리소스 파일|`"/ReferencedAssembly;component/Subfolder/ResourceFile.xaml"`|  
|콘텐츠 파일|`"/ContentFile.xaml"`|  
|하위 폴더의 콘텐츠 파일|`"/Subfolder/ContentFile.xaml"`|  
  
<a name="Using_Pack_URIs_in_Code"></a>   
### <a name="using-pack-uris-in-code"></a>코드에서 Pack URI 사용  
 팩을 지정 [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] 인스턴스화하여 코드에는 <xref:System.Uri> 팩을 전달과 클래스 [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] 생성자에 매개 변수로 합니다. 다음 예제를 통해 볼 수 있습니다.  
  
```csharp  
Uri uri = new Uri("pack://application:,,,/File.xaml");  
```  
  
 기본적으로 <xref:System.Uri> 클래스는 pack [!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)] 에 절대 경로 여야 합니다. 인스턴스의 경우 예외가 발생 하는 결과적으로 <xref:System.Uri> 상대 pack을 사용 하 여 클래스를 만들 [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)]합니다.  
  
```csharp  
Uri uri = new Uri("/File.xaml");  
```  
  
 다행 스럽게도 합니다 <xref:System.Uri.%23ctor%28System.String%2CSystem.UriKind%29> 오버 로드는 <xref:System.Uri> 형식의 매개 변수를 허용 하는 클래스 생성자 <xref:System.UriKind> 지정할 수 있도록 팩을 여부를 [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] 가 절대 인지 상대 합니다.  
  
```csharp  
// Absolute URI (default)  
Uri absoluteUri = new Uri("pack://application:,,,/File.xaml", UriKind.Absolute);  
// Relative URI  
Uri relativeUri = new Uri("/File.xaml",   
                        UriKind.Relative);  
```  
  
 만 지정 해야 <xref:System.UriKind.Absolute> 나 <xref:System.UriKind.Relative> 되었음을 확인 하는 경우 제공 된 pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] 둘 중 하나는 합니다. 팩의 유형을 알 수 없는 경우 [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] 사용 되는, 팩을 사용자가 입력 하는 경우와 같은 [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] 런타임 시 사용 하 여 <xref:System.UriKind.RelativeOrAbsolute> 대신 합니다.  
  
```csharp  
// Relative or Absolute URI provided by user via a text box  
TextBox userProvidedUriTextBox = new TextBox();  
Uri uri = new Uri(userProvidedUriTextBox.Text, UriKind.RelativeOrAbsolute);  
```  
  
 표 3은 다양 한 상대 pack 보여줍니다 [!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)] 를 사용 하 여 코드에서 지정할 수 있는 <xref:System.Uri?displayProperty=nameWithType>합니다.  
  
 표 3: 코드의 절대 Pack Uri  
  
|파일|절대 pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)]|  
|----------|-------------------------------------------------------------------------------------------------------------------------|  
|리소스 파일 - 로컬 어셈블리|`Uri uri = new Uri("pack://application:,,,/ResourceFile.xaml", UriKind.Absolute);`|  
|하위 폴더의 리소스 파일 - 로컬 어셈블리|`Uri uri = new Uri("pack://application:,,,/Subfolder/ResourceFile.xaml", UriKind.Absolute);`|  
|리소스 파일 - 참조된 어셈블리|`Uri uri = new Uri("pack://application:,,,/ReferencedAssembly;component/ResourceFile.xaml", UriKind.Absolute);`|  
|참조된 어셈블리의 하위 폴더에 있는 리소스 파일|`Uri uri = new Uri("pack://application:,,,/ReferencedAssembly;component/Subfolder/ResourceFile.xaml", UriKind.Absolute);`|  
|버전이 있는 참조된 어셈블리의 리소스 파일|`Uri uri = new Uri("pack://application:,,,/ReferencedAssembly;v1.0.0.0;component/ResourceFile.xaml", UriKind.Absolute);`|  
|콘텐츠 파일|`Uri uri = new Uri("pack://application:,,,/ContentFile.xaml", UriKind.Absolute);`|  
|하위 폴더의 콘텐츠 파일|`Uri uri = new Uri("pack://application:,,,/Subfolder/ContentFile.xaml", UriKind.Absolute);`|  
|원본 사이트 파일|`Uri uri = new Uri("pack://siteoforigin:,,,/SOOFile.xaml", UriKind.Absolute);`|  
|하위 폴더의 원본 사이트 파일|`Uri uri = new Uri("pack://siteoforigin:,,,/Subfolder/SOOFile.xaml", UriKind.Absolute);`|  
  
 표 4에는 다양 한 상대 pack 보여 줍니다 [!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)] 사용 하 여 코드에서 지정할 수 있는 <xref:System.Uri?displayProperty=nameWithType>합니다.  
  
 표 4: 코드의 상대 Pack Uri  
  
|파일|상대 pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)]|  
|----------|-------------------------------------------------------------------------------------------------------------------------|  
|리소스 파일 - 로컬 어셈블리|`Uri uri = new Uri("/ResourceFile.xaml", UriKind.Relative);`|  
|하위 폴더의 리소스 파일 - 로컬 어셈블리|`Uri uri = new Uri("/Subfolder/ResourceFile.xaml", UriKind.Relative);`|  
|리소스 파일 - 참조된 어셈블리|`Uri uri = new Uri("/ReferencedAssembly;component/ResourceFile.xaml", UriKind.Relative);`|  
|하위 폴더의 리소스 파일 - 참조된 어셈블리|`Uri uri = new Uri("/ReferencedAssembly;component/Subfolder/ResourceFile.xaml", UriKind.Relative);`|  
|콘텐츠 파일|`Uri uri = new Uri("/ContentFile.xaml", UriKind.Relative);`|  
|하위 폴더의 콘텐츠 파일|`Uri uri = new Uri("/Subfolder/ContentFile.xaml", UriKind.Relative);`|  
  
<a name="Common_Pack_URI_Scenarios"></a>   
### <a name="common-pack-uri-scenarios"></a>일반적인 Pack URI 시나리오  
 이전 섹션에서는 팩을 생성 하는 방법을 설명한 [!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)] 리소스, 콘텐츠 및 원본 사이트 파일을 식별 합니다. [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]이러한 구성은 다양 한 방법으로 사용 되 고 다음 섹션에서 몇 가지 일반적인 사용법을 설명 합니다.  
  
<a name="Specifying_the_UI_to_Show_when_an_Application_Starts"></a>   
#### <a name="specifying-the-ui-to-show-when-an-application-starts"></a>애플리케이션을 시작할 때 표시되는 UI 지정  
 <xref:System.Windows.Application.StartupUri%2A> 첫 번째 지정 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] 때 표시 되는 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] 응용 프로그램이 시작 됩니다. 독립 실행형 응용 프로그램의 경우는 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] 다음 예와에서 같이 창 일 수 있습니다.  
  
 [!code-xaml[PackURIOverviewSnippets#StartupUriWindow](~/samples/snippets/csharp/VS_Snippets_Wpf/PackURIOverviewSnippets/CS/Copy of App.xaml#startupuriwindow)]  
  
 독립 실행형 응용 프로그램 및 [!INCLUDE[TLA#tla_xbap#plural](../../../../includes/tlasharptla-xbapsharpplural-md.md)] 다음 예제에서와 같이 초기 UI로 페이지를 지정할 수도 있습니다.  
  
 [!code-xaml[PackURIOverviewSnippets#StartupUriPage](~/samples/snippets/csharp/VS_Snippets_Wpf/PackURIOverviewSnippets/CS/App.xaml#startupuripage)]  
  
 응용 프로그램은 독립 실행형 응용 프로그램 및 페이지를 사용 하 여 지정한 경우 <xref:System.Windows.Application.StartupUri%2A>, [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] 열립니다는 <xref:System.Windows.Navigation.NavigationWindow> 페이지를 호스팅합니다. 에 대 한 [!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)], 호스트 브라우저에 페이지가 표시 됩니다.  
  
<a name="Navigating_to_a_Page"></a>   
#### <a name="navigating-to-a-page"></a>페이지 탐색  
 다음 예제에서는 페이지를 탐색하는 방법을 보여 줍니다.  
  
 [!code-xaml[NavigationOverviewSnippets#HyperlinkXAML1](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/PageWithHyperlink.xaml#hyperlinkxaml1)]  
[!code-xaml[NavigationOverviewSnippets#HyperlinkXAML2](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/PageWithHyperlink.xaml#hyperlinkxaml2)]  
[!code-xaml[NavigationOverviewSnippets#HyperlinkXAML3](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/PageWithHyperlink.xaml#hyperlinkxaml3)]  
  
 탐색 하는 다양 한 방법에 대 한 자세한 내용은 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]를 참조 하세요 [탐색 개요](navigation-overview.md)합니다.  
  
<a name="Specifying_a_Window_Icon"></a>   
#### <a name="specifying-a-window-icon"></a>창 아이콘 지정  
 다음 예제에서는 URI를 사용하여 창 아이콘을 지정하는 방법을 보여 줍니다.  
  
 [!code-xaml[WindowIconSnippets#WindowIconSetXAML](~/samples/snippets/xaml/VS_Snippets_Wpf/WindowIconSnippets/XAML/MainWindow.xaml#windowiconsetxaml)]  
  
 자세한 내용은 <xref:System.Windows.Window.Icon%2A>을 참조하세요.  
  
<a name="Loading_Image__Audio__and_Video_Files"></a>   
#### <a name="loading-image-audio-and-video-files"></a>이미지, 오디오 및 비디오 파일 로드  
 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] 다양 한 미디어 유형 모두를 식별 하 고 팩을 사용 하 여 로드를 사용 하도록 응용 프로그램을 사용 하면 [!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)]다음 예제에 나와 있는 것 처럼 합니다.  
  
 [!code-xaml[MediaPlayerVideoSample#VideoPackURIAtSOO](~/samples/snippets/csharp/VS_Snippets_Wpf/MediaPlayerVideoSample/CS/HomePage.xaml#videopackuriatsoo)]  
  
 [!code-xaml[MediaPlayerAudioSample#AudioPackURIAtSOO](~/samples/snippets/csharp/VS_Snippets_Wpf/MediaPlayerAudioSample/CS/HomePage.xaml#audiopackuriatsoo)]  
  
 [!code-xaml[ImageSample#ImagePackURIContent](~/samples/snippets/csharp/VS_Snippets_Wpf/ImageSample/CS/HomePage.xaml#imagepackuricontent)]  
  
 미디어 콘텐츠가 포함 된 작업에 대 한 자세한 내용은 참조 하세요. [그래픽 및 멀티미디어](../graphics-multimedia/index.md)합니다.  
  
<a name="Loading_a_Resource_Dictionary_from_the_Site_of_Origin"></a>   
#### <a name="loading-a-resource-dictionary-from-the-site-of-origin"></a>원본 사이트에서 리소스 사전 로드  
 리소스 사전 (<xref:System.Windows.ResourceDictionary>) 응용 프로그램 테마를 지 원하는 데 사용할 수 있습니다. 테마를 만들고 관리하는 한 가지 방법은 애플리케이션의 원본 사이트에 위치한 리소스 사전으로 여러 개의 테마를 만드는 것입니다. 이렇게 하면 애플리케이션을 다시 컴파일하여 배포할 필요 없이 테마를 추가하고 업데이트할 수 있습니다. 이러한 리소스 사전은 확인할 수 있으며 팩을 사용 하 여 로드 [!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)], 다음 예제에 나와 있는 합니다.  
  
 [!code-xaml[ResourceDictionarySnippets#ResourceDictionaryPackURI](~/samples/snippets/csharp/VS_Snippets_Wpf/ResourceDictionarySnippets/CS/App.xaml#resourcedictionarypackuri)]  
  
 테마에 대 한 개요 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]를 참조 하세요 [스타일 및 템플릿](../controls/styling-and-templating.md)합니다.  
  
## <a name="see-also"></a>참고자료

- [WPF 애플리케이션 리소스, 콘텐츠 및 데이터 파일](wpf-application-resource-content-and-data-files.md)
