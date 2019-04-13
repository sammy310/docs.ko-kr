---
title: WPF의 전역화
ms.date: 03/30/2017
helpviewer_keywords:
- XAML [WPF], international user interface
- XAML [WPF], globalization
- international user interface [WPF], XAML
- globalization [WPF]
ms.assetid: 4571ccfe-8a60-4f06-9b37-7ac0b1c2d10f
ms.openlocfilehash: 9a08fdeaa3517b1483af3f9958ad2db1c64648b8
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59084169"
---
# <a name="globalization-for-wpf"></a>WPF의 전역화
이 항목에서는 소개를 작성할 때 알고 있어야 하는 문제 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] 글로벌 시장 용 응용 프로그램입니다. 전역화 프로그래밍 요소에 정의 된 [!INCLUDE[TLA#tla_net](../../../../includes/tlasharptla-net-md.md)] 에서 `System.Globalization`합니다.

<a name="xaml_globalization"></a>
## <a name="xaml-globalization"></a>XAML 전역화
 [!INCLUDE[TLA#tla_xaml#initcap](../../../../includes/tlasharptla-xamlsharpinitcap-md.md)] 더해서 [!INCLUDE[TLA#tla_xml](../../../../includes/tlasharptla-xml-md.md)] 에 정의 된 전역화 지원을 활용 하 고는 [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] 사양입니다. 다음 섹션에서는 일부 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 고려해 야 하는 기능입니다.

<a name="char_reference"></a>
### <a name="character-references"></a>문자 참조
문자 참조를 제공 UTF16 코드 단위의 특정 [!INCLUDE[TLA#tla_unicode](../../../../includes/tlasharptla-unicode-md.md)] 나타내는 10 진수 또는 16 진수 문자입니다. 다음 예제에서는 'Ϩ' 콥트어 CAPITAL LETTER 가로에 10 진수 문자 참조를 보여 줍니다.

```
&#1000;
```

다음 예제에서는 16 진수 문자 참조를 보여 줍니다. 가 **x** 16 진수 앞에 있습니다.

```
&#x3E8;
```

<a name="encoding"></a>
### <a name="encoding"></a>인코딩
 지 원하는 인코딩은 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 됩니다 [!INCLUDE[TLA#tla_ascii](../../../../includes/tlasharptla-ascii-md.md)], [!INCLUDE[TLA2#tla_unicode](../../../../includes/tla2sharptla-unicode-md.md)] utf-16 및 u t F-8입니다. 맨 앞에 인코딩 문은 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 문서. 인코딩 특성이 없으며 바이트 순서가 없으면 기본적으로 구문 분석기가 UTF-8로 설정됩니다. UTF-8과 UTF-16이 기본 인코딩입니다. UTF-7은 지원되지 않습니다. 다음 예제에서 u t F-8 인코딩을 지정 하는 방법에 설명 된 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 파일입니다.

```
?xml encoding="UTF-8"?
```

<a name="lang_attrib"></a>
### <a name="language-attribute"></a>언어 특성
 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 사용 하 여 [xml: lang](../../xaml-services/xml-lang-handling-in-xaml.md) 를 요소의 언어 특성을 나타냅니다.  활용 하기 위해 합니다 <xref:System.Globalization.CultureInfo> 클래스의 미리 정의 된 문화권 이름 중 하나일 언어 특성 값을 해야 <xref:System.Globalization.CultureInfo>합니다. [xml:lang](../../xaml-services/xml-lang-handling-in-xaml.md)은 요소 트리에서 상속 가능하며(반드시 종속성 속성 상속성때문이 아니라 XML 규칙에 따름), 명시적으로 할당되지 않은 경우 기본값은 비어 있습니다.

 언어를 지정할 때 언어 특성이 매우 유용합니다. 예를 들어, 프랑스, 퀘벡, 벨기에 및 스위스의 프랑스어에는 다른 철자, 어휘 및 발음이 있습니다. 중국어, 일본어 및 한국어에서 코드 포인트 공유할 수도 [!INCLUDE[TLA2#tla_unicode](../../../../includes/tla2sharptla-unicode-md.md)], 하지만 표의 문자 모양은 서로 다르고 완전히 다른 글꼴을 사용 합니다.

 다음 [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] 사용 하 여 예제를 `fr-CA` 언어 특성 캐나다 프랑스어를 지정 합니다.

```xml
<TextBlock xml:lang="fr-CA">Découvrir la France</TextBlock>
```

<a name="unicode"></a>
### <a name="unicode"></a>유니코드(Unicode)
 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 모든 지원 [!INCLUDE[TLA2#tla_unicode](../../../../includes/tla2sharptla-unicode-md.md)] 서로게이트를 포함 하는 기능입니다. 문자 집합에 매핑될 수 있다면 [!INCLUDE[TLA2#tla_unicode](../../../../includes/tla2sharptla-unicode-md.md)], 지원 됩니다. 예를 들어, GB18030에서는 중국어, 일본어 및 한국어(CFK) 확장 A와 B에 매핑되는 일부 문자와 서로게이트 쌍을 소개하므로 완전히 지원됩니다. A [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 응용 프로그램에서 사용할 수 <xref:System.Globalization.StringInfo> 결합 문자 또는 서로게이트 쌍 인지 파악 하지 않고도 문자열을 조작할 수 있습니다.

<a name="design_intl_ui_with_xaml"></a>
## <a name="designing-an-international-user-interface-with-xaml"></a>XAML로 국가별 사용자 인터페이스 설계
 이 섹션에서는 설명 [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] 응용 프로그램을 작성할 때 고려해 야 하는 기능입니다.

<a name="intl_text"></a>
### <a name="international-text"></a>국가별 텍스트
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 모든 Microsoft.NET Framework 지원 쓰기 시스템에 대 한 기본 제공 처리를 포함합니다.

 현재 지원되는 스크립트는 다음과 같습니다.

-   아랍어

-   벵골어

-   데바나가리어

-   키릴 자모

-   그리스어

-   구자라트어

-   굴묵키어

-   히브리어

-   표의 문자 스크립트

-   칸나다어

-   라오어

-   라틴어

-   말라얄람어

-   몽골어

-   오리야어

-   시리아어

-   타밀어

-   텔루구어

-   타나 문자

-   태국어*

-   티베트어

 * 이 릴리스에서는 태국어 텍스트의 표시 및 편집이 지원되며, 단어 구분은 지원되지 않습니다.

 현재 지원되지 않는 스크립트는 다음과 같습니다.

-   크메르어

-   한국어 옛 한글

-   미얀마어

-   스리랑카어

 모든 쓰기 시스템 엔진 지원 [!INCLUDE[TLA#tla_opentype](../../../../includes/tlasharptla-opentype-md.md)] 글꼴입니다. [!INCLUDE[TLA2#tla_opentype](../../../../includes/tla2sharptla-opentype-md.md)] 글꼴 포함 될 수 있습니다는 [!INCLUDE[TLA2#tla_opentype](../../../../includes/tla2sharptla-opentype-md.md)] 레이아웃 테이블을 더 잘 국가별 글꼴과 최고급 글꼴을 디자인 하는 글꼴 생성기를 사용 하도록 설정 합니다. [!INCLUDE[TLA2#tla_opentype](../../../../includes/tla2sharptla-opentype-md.md)] 글꼴 레이아웃 테이블에 대 한 정보가 문자 모양 대체, 문자 모양 위치 지정, 양쪽 맞춤 및 기준선 위치 지정 텍스트 레이아웃을 개선 하기 위해 텍스트 처리 응용 프로그램을 사용 하도록 설정 합니다.

 [!INCLUDE[TLA2#tla_opentype](../../../../includes/tla2sharptla-opentype-md.md)] 글꼴 큰 문자 모양 처리를 사용 하 여 집합 허용 [!INCLUDE[TLA2#tla_unicode](../../../../includes/tla2sharptla-unicode-md.md)] 인코딩. 이러한 인코딩을 사용하면 글꼴 문자 모양 변형 외에도 광범위한 국가별 지원이 가능합니다.

 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 텍스트 렌더링으로 구동 되며 [!INCLUDE[TLA#tla_ct](../../../../includes/tlasharptla-ct-md.md)] 해상도 독립성을 지 원하는 하위 픽셀 기술을 합니다. 이 기능을 통해 가독성이 크게 향상되며, 모든 스크립트에 대해 고품질 잡지 스타일 문서를 지원하는 기능을 제공합니다.

<a name="intl_layout"></a>
### <a name="international-layout"></a>국가별 레이아웃
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 매우 편리 하 게 지원 가로, 양방향 및 세로 레이아웃을 제공 합니다. 프레젠테이션 프레임 워크에서는 <xref:System.Windows.FrameworkElement.FlowDirection%2A> 레이아웃을 정의 하려면 속성을 사용할 수 있습니다. 흐름 방향 패턴은 다음과 같습니다.

-   *LeftToRight* - 라틴어, 동아시아어 등을 위한 가로 레이아웃.

-   *RightToLeft* - 아랍어, 히브리어 등을 위한 양방향.

<a name="developing_localizable_apps"></a>
## <a name="developing-localizable-applications"></a>지역화 가능 애플리케이션 개발
 글로벌 사용을 위해 애플리케이션을 작성할 때 애플리케이션을 지역화해야 한다는 점에 유의해야 합니다. 다음 항목에서는 고려할 사항을 제공합니다.

<a name="mui"></a>
### <a name="multilingual-user-interface"></a>다국어 사용자 인터페이스
 다국어 사용자 인터페이스 (MUI)는 한 [!INCLUDE[TLA#tla_ms](../../../../includes/tlasharptla-ms-md.md)] 전환에 대 한 지원 [!INCLUDE[TLA2#tla_ui#plural](../../../../includes/tla2sharptla-uisharpplural-md.md)] 다른 언어에서입니다. [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] MUI를 지원 하기 위해 어셈블리 모델을 사용 하는 응용 프로그램입니다. 한 애플리케이션에는 언어 중립 어셈블리 외에도 언어별 위성 리소스 어셈블리도 포함됩니다. 진입점은 기본 어셈블리에서 관리되는 .EXE입니다.  [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 리소스 로더는 활용을 [!INCLUDE[TLA2#tla_netframewk](../../../../includes/tla2sharptla-netframewk-md.md)]의 resource manager 리소스 조회 및 대체 (fallback)를 지원 합니다. 여러 언어 위성 어셈블리는 동일한 기본 어셈블리와 작동합니다. 로드 되는 리소스 어셈블리가 종속 된 <xref:System.Globalization.CultureInfo.CurrentUICulture%2A> 현재 스레드의 합니다.

<a name="localizable_ui"></a>
### <a name="localizable-user-interface"></a>지역화할 수 있는 사용자 인터페이스
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 응용 프로그램 사용 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 정의에 해당 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]합니다. [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 개발자가 속성 및 논리 집합이 포함 된 개체의 계층을 지정할 수 있습니다. 주된 용도 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 개발 하는 데 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 하지만 응용 프로그램의 계층을 지정 하려면 사용할 수 [!INCLUDE[TLA#tla_clr](../../../../includes/tlasharptla-clr-md.md)] 개체입니다. 대부분의 개발자가 사용할 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 는 응용 프로그램을 지정 하려면 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] C#과 같은 프로그래밍 언어를 사용 하 여 사용자 상호 작용에 반응 하 고 있습니다.

 리소스의 관점에서을 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 파일을 언어별 설명 하도록 설계 된 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] 리소스 요소 이며 따라서, 최종 배포 형식은 국가별 언어를 지원 하도록 지역화 해야 합니다. 때문에 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 없습니다 이벤트를 처리할 여러 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 응용 프로그램에이 작업을 수행 하는 코드 블록을 포함 합니다. 자세한 내용은 [XAML 개요 (WPF)](xaml-overview-wpf.md)합니다. 코드를 제거 하 고 다른 이진 파일로 컴파일할 때를 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 파일은 XAML의 BAML 양식으로 토큰화 됩니다. XAML 파일의 BAML 양식, 이미지 및 기타 형식의 관리 리소스 개체는 위성 리소스 어셈블리에 포함되어 다른 언어로 지역화되거나, 지역화가 필요하지 않은 경우 기본 어셈블리에 포함됩니다.

> [!NOTE]
>  [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 응용 프로그램을 지 원하는 모든는 [!INCLUDE[TLA2#tla_netframewk](../../../../includes/tla2sharptla-netframewk-md.md)][!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)] 문자열 테이블, 이미지 등을 비롯 한 리소스입니다.

<a name="building_localizable_apps"></a>
### <a name="building-localizable-applications"></a>지역화 가능 애플리케이션 빌드
 지역화에 맞게 의미를 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] 를 다른 문화권입니다. 확인을 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 응용 프로그램을 개발자가 지역화 가능한 리소스를 모두 리소스 어셈블리에 빌드해야 하는 데 필요한 지역화 합니다. 다른 언어로 지역화 된 리소스 어셈블리 및 코드 숨김에서는 리소스 관리 [!INCLUDE[TLA#tla_api](../../../../includes/tlasharptla-api-md.md)] 를 로드 합니다. 에 필요한 파일 중 하나는 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 응용 프로그램은 프로젝트 파일 (.proj)입니다. 애플리케이션에서 사용하는 모든 리소스는 프로젝트 파일에 포함되어야 합니다. .csprop 파일의 다음 예에서는 이 작업을 수행하는 방법을 보여줍니다.

```xml
<Resource Include="data\picture1.jpg"/>
<EmbeddedResource Include="data\stringtable.en-US.restext"/>
```

 응용 프로그램에서 리소스 인스턴스화하는 데는 <xref:System.Resources.ResourceManager> 하 고 사용 하려는 리소스를 로드 합니다. 다음 예제에서는 이 작업을 수행하는 방법을 보여 줍니다.

 [!code-csharp[LocalizationResources#2](~/samples/snippets/csharp/VS_Snippets_Wpf/LocalizationResources/CSharp/page1.xaml.cs#2)]

<a name="using_clickonce"></a>
## <a name="using-clickonce-with-localized-applications"></a>지역화된 애플리케이션에서 ClickOnce 사용
 ClickOnce는 Visual Studio 2005를 사용 하 여 제공 될 새 Windows Forms 배포 기술입니다. 애플리케이션 설치 및 웹 애플리케이션의 업그레이드를 수행할 수 있습니다. ClickOnce로 배포된 애플리케이션이 지역화되면 지역화된 문화권에서만 볼 수 있습니다. 예를 들어 일본어로 지역화 된 응용 프로그램을 배포 하는 경우만 볼 수 있습니다 일본어 [!INCLUDE[TLA#tla_win](../../../../includes/tlasharptla-win-md.md)] 영어 Windows에 없습니다. 일본어 사용자가 Windows의 영어 버전에 대 한 일반적인 시나리오 이므로 문제가 초래 됩니다.

 이 문제는 중립 언어 대체 특성을 설정하여 해결합니다. 애플리케이션 개발자가 선택적으로 기본 어셈블리에서 리소스를 제거하고 특정 문화권에 해당하는 위성 어셈블리에서 해당 리소스를 찾을 수 있게 지정할 수 있습니다. 이 프로세스 사용을 제어 하는 <xref:System.Resources.NeutralResourcesLanguageAttribute>합니다. 생성자는 <xref:System.Resources.NeutralResourcesLanguageAttribute> 클래스에 사용 하는 두 개의 서명을 <xref:System.Resources.UltimateResourceFallbackLocation> 위치를 지정 하려면 매개 변수 위치는 <xref:System.Resources.ResourceManager> 대체 (fallback) 리소스를 추출 해야: 주 어셈블리 또는 위성 어셈블리입니다. 다음 예제에서는 이 특성을 사용하는 방법을 보여 줍니다. Ultimate 대체 (fallback) 위치에 대 한 코드는 다음과 같이 하면 됩니다.는 <xref:System.Resources.ResourceManager> 현재 실행 중인 어셈블리의 디렉터리의 "de" 하위 디렉터리에 있는 리소스를 찾도록 합니다.

```
[assembly: NeutralResourcesLanguageAttribute(
    "de" , UltimateResourceFallbackLocation.Satellite)]
```

## <a name="see-also"></a>참고자료

- [WPF 전역화 및 지역화 개요](wpf-globalization-and-localization-overview.md)
