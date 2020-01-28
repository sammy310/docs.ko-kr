---
title: 전역화
ms.date: 03/30/2017
helpviewer_keywords:
- XAML [WPF], international user interface
- XAML [WPF], globalization
- international user interface [WPF], XAML
- globalization [WPF]
ms.assetid: 4571ccfe-8a60-4f06-9b37-7ac0b1c2d10f
ms.openlocfilehash: 95c0368889dfa4e69b5e40b32ea19ba845aa5c30
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/24/2020
ms.locfileid: "76747059"
---
# <a name="globalization-for-wpf"></a><span data-ttu-id="0a9c2-102">WPF의 전역화</span><span class="sxs-lookup"><span data-stu-id="0a9c2-102">Globalization for WPF</span></span>
<span data-ttu-id="0a9c2-103">이 항목에서는 글로벌 시장을 위해 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] 응용 프로그램을 작성할 때 알아야 하는 문제를 소개 합니다.</span><span class="sxs-lookup"><span data-stu-id="0a9c2-103">This topic introduces issues that you should be aware of when writing [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] applications for the global market.</span></span> <span data-ttu-id="0a9c2-104">세계화 프로그래밍 요소는 <xref:System.Globalization> 네임 스페이스의 .NET에 정의 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0a9c2-104">The globalization programming elements are defined in .NET in the <xref:System.Globalization> namespace.</span></span>

<a name="xaml_globalization"></a>
## <a name="xaml-globalization"></a><span data-ttu-id="0a9c2-105">XAML 전역화</span><span class="sxs-lookup"><span data-stu-id="0a9c2-105">XAML Globalization</span></span>
 <span data-ttu-id="0a9c2-106">Extensible Application Markup Language (XAML)은 XML을 기반으로 하며 XML 사양에 정의 된 전역화 지원을 활용 합니다.</span><span class="sxs-lookup"><span data-stu-id="0a9c2-106">Extensible Application Markup Language (XAML) is based on XML and takes advantage of the globalization support defined in the XML specification.</span></span> <span data-ttu-id="0a9c2-107">다음 섹션에서는 알고 있어야 하는 몇 가지 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 기능에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="0a9c2-107">The following sections describe some [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] features that you should be aware of.</span></span>

<a name="char_reference"></a>
### <a name="character-references"></a><span data-ttu-id="0a9c2-108">문자 참조</span><span class="sxs-lookup"><span data-stu-id="0a9c2-108">Character References</span></span>
<span data-ttu-id="0a9c2-109">문자 참조는 10 진수 또는 16 진수로 나타내는 특정 유니코드 문자의 UTF16 코드 단위를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="0a9c2-109">A character reference gives the UTF16 code unit of the particular Unicode character it represents, in either decimal or hexadecimal.</span></span> <span data-ttu-id="0a9c2-110">다음 예제에서는 콥트어 대문자 가로 또는 ' Ϩ '에 대 한 10 진수 문자 참조를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="0a9c2-110">The following example shows a decimal character reference for the COPTIC CAPITAL LETTER HORI, or 'Ϩ':</span></span>

```
&#1000;
```

<span data-ttu-id="0a9c2-111">다음 예제에서는 16 진수 문자 참조를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="0a9c2-111">The following example shows a hexadecimal character reference.</span></span> <span data-ttu-id="0a9c2-112">16 진수 앞에 **x** 가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0a9c2-112">Notice that it has an **x** in front of the hexadecimal number.</span></span>

```
&#x3E8;
```

<a name="encoding"></a>
### <a name="encoding"></a><span data-ttu-id="0a9c2-113">Encoding</span><span class="sxs-lookup"><span data-stu-id="0a9c2-113">Encoding</span></span>
 <span data-ttu-id="0a9c2-114">[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]에서 지원 되는 인코딩은 ASCII, 유니코드 UTF-16 및 u t f-8입니다.</span><span class="sxs-lookup"><span data-stu-id="0a9c2-114">The encoding supported by [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] are ASCII, Unicode UTF-16, and UTF-8.</span></span> <span data-ttu-id="0a9c2-115">Encoding 문은 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 문서의 시작 부분에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0a9c2-115">The encoding statement is at the beginning of [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] document.</span></span> <span data-ttu-id="0a9c2-116">인코딩 특성이 없으며 바이트 순서가 없으면 기본적으로 구문 분석기가 UTF-8로 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="0a9c2-116">If no encoding attribute exists and there is no byte-order, the parser defaults to UTF-8.</span></span> <span data-ttu-id="0a9c2-117">UTF-8과 UTF-16이 기본 인코딩입니다.</span><span class="sxs-lookup"><span data-stu-id="0a9c2-117">UTF-8 and UTF-16 are the preferred encodings.</span></span> <span data-ttu-id="0a9c2-118">UTF-7은 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0a9c2-118">UTF-7 is not supported.</span></span> <span data-ttu-id="0a9c2-119">다음 예에서는 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 파일에서 UTF-8 인코딩을 지정 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="0a9c2-119">The following example demonstrates how to specify a UTF-8 encoding in a [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] file.</span></span>

```xaml
?xml encoding="UTF-8"?
```

<a name="lang_attrib"></a>
### <a name="language-attribute"></a><span data-ttu-id="0a9c2-120">언어 특성</span><span class="sxs-lookup"><span data-stu-id="0a9c2-120">Language Attribute</span></span>
 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]<span data-ttu-id="0a9c2-121">는 [xml: lang](../../../desktop-wpf/xaml-services/xml-language-handling.md) 을 사용 하 여 요소의 language 특성을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="0a9c2-121">uses [xml:lang](../../../desktop-wpf/xaml-services/xml-language-handling.md) to represent the language attribute of an element.</span></span>  <span data-ttu-id="0a9c2-122"><xref:System.Globalization.CultureInfo> 클래스를 활용 하려면 language 특성 값이 <xref:System.Globalization.CultureInfo>에서 미리 정의 된 문화권 이름 중 하나 여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0a9c2-122">To take advantage of the <xref:System.Globalization.CultureInfo> class, the language attribute value needs to be one of the culture names predefined by <xref:System.Globalization.CultureInfo>.</span></span> <span data-ttu-id="0a9c2-123">[xml:lang](../../../desktop-wpf/xaml-services/xml-language-handling.md)은 요소 트리에서 상속 가능하며(반드시 종속성 속성 상속성때문이 아니라 XML 규칙에 따름), 명시적으로 할당되지 않은 경우 기본값은 비어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0a9c2-123">[xml:lang](../../../desktop-wpf/xaml-services/xml-language-handling.md) is inheritable in the element tree (by XML rules, not necessarily because of dependency property inheritance) and its default value is an empty string if it is not assigned explicitly.</span></span>

 <span data-ttu-id="0a9c2-124">언어를 지정할 때 언어 특성이 매우 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="0a9c2-124">The language attribute is very useful for specifying dialects.</span></span> <span data-ttu-id="0a9c2-125">예를 들어, 프랑스, 퀘벡, 벨기에 및 스위스의 프랑스어에는 다른 철자, 어휘 및 발음이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0a9c2-125">For example, French has different spelling, vocabulary, and pronunciation in France, Quebec, Belgium, and Switzerland.</span></span> <span data-ttu-id="0a9c2-126">또한 중국어, 일본어 및 한국어는 유니코드에서 코드 점수를 공유 하지만 표의 문자 모양은 서로 다르며 완전히 다른 글꼴을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="0a9c2-126">Also Chinese, Japanese, and Korean share code points in Unicode, but the ideographic shapes are different and they use totally different fonts.</span></span>

 <span data-ttu-id="0a9c2-127">다음 [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] 예제에서는 `fr-CA` language 특성을 사용 하 여 캐나다 프랑스어를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="0a9c2-127">The following [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] example uses the `fr-CA` language attribute to specify Canadian French.</span></span>

```xaml
<TextBlock xml:lang="fr-CA">Découvrir la France</TextBlock>
```

<a name="unicode"></a>
### <a name="unicode"></a><span data-ttu-id="0a9c2-128">유니코드(Unicode)</span><span class="sxs-lookup"><span data-stu-id="0a9c2-128">Unicode</span></span>
 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]<span data-ttu-id="0a9c2-129">은 서로게이트를 비롯 한 모든 유니코드 기능을 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="0a9c2-129">supports all Unicode features including surrogates.</span></span> <span data-ttu-id="0a9c2-130">문자 집합을 유니코드에 매핑할 수 있으면 지원 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0a9c2-130">As long as the character set can be mapped to Unicode, it is supported.</span></span> <span data-ttu-id="0a9c2-131">예를 들어, GB18030에서는 중국어, 일본어 및 한국어(CFK) 확장 A와 B에 매핑되는 일부 문자와 서로게이트 쌍을 소개하므로 완전히 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="0a9c2-131">For example, GB18030 introduces some characters that are mapped to the Chinese, Japanese, and Korean (CFK) extension A and B and surrogate pairs, therefore it is fully supported.</span></span> <span data-ttu-id="0a9c2-132">[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 응용 프로그램은 <xref:System.Globalization.StringInfo>를 사용 하 여 서로게이트 쌍 또는 결합 문자가 있는지 여부를 몰라도 문자열을 조작할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0a9c2-132">A [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] application can use <xref:System.Globalization.StringInfo> to manipulate strings without understanding whether they have surrogate pairs or combining characters.</span></span>

<a name="design_intl_ui_with_xaml"></a>
## <a name="designing-an-international-user-interface-with-xaml"></a><span data-ttu-id="0a9c2-133">XAML로 국가별 사용자 인터페이스 설계</span><span class="sxs-lookup"><span data-stu-id="0a9c2-133">Designing an International User Interface with XAML</span></span>
 <span data-ttu-id="0a9c2-134">이 섹션에서는 응용 프로그램을 작성할 때 고려해 야 하는 [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] 기능에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="0a9c2-134">This section describes [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] features that you should consider when writing an application.</span></span>

<a name="intl_text"></a>
### <a name="international-text"></a><span data-ttu-id="0a9c2-135">국가별 텍스트</span><span class="sxs-lookup"><span data-stu-id="0a9c2-135">International Text</span></span>
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]<span data-ttu-id="0a9c2-136">에는 모든 Microsoft .NET Framework에서 지원 되는 쓰기 시스템에 대 한 기본 제공 처리가 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0a9c2-136">includes built-in processing for all Microsoft .NET Framework supported writing systems.</span></span>

 <span data-ttu-id="0a9c2-137">현재 지원되는 스크립트는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="0a9c2-137">The following scripts are currently supported:</span></span>

- <span data-ttu-id="0a9c2-138">아랍어</span><span class="sxs-lookup"><span data-stu-id="0a9c2-138">Arabic</span></span>

- <span data-ttu-id="0a9c2-139">벵골어</span><span class="sxs-lookup"><span data-stu-id="0a9c2-139">Bengali</span></span>

- <span data-ttu-id="0a9c2-140">데바나가리어</span><span class="sxs-lookup"><span data-stu-id="0a9c2-140">Devanagari</span></span>

- <span data-ttu-id="0a9c2-141">키릴 자모</span><span class="sxs-lookup"><span data-stu-id="0a9c2-141">Cyrillic</span></span>

- <span data-ttu-id="0a9c2-142">그리스어</span><span class="sxs-lookup"><span data-stu-id="0a9c2-142">Greek</span></span>

- <span data-ttu-id="0a9c2-143">구자라트어</span><span class="sxs-lookup"><span data-stu-id="0a9c2-143">Gujarati</span></span>

- <span data-ttu-id="0a9c2-144">굴묵키어</span><span class="sxs-lookup"><span data-stu-id="0a9c2-144">Gurmukhi</span></span>

- <span data-ttu-id="0a9c2-145">히브리어</span><span class="sxs-lookup"><span data-stu-id="0a9c2-145">Hebrew</span></span>

- <span data-ttu-id="0a9c2-146">표의 문자 스크립트</span><span class="sxs-lookup"><span data-stu-id="0a9c2-146">Ideographic scripts</span></span>

- <span data-ttu-id="0a9c2-147">칸나다어</span><span class="sxs-lookup"><span data-stu-id="0a9c2-147">Kannada</span></span>

- <span data-ttu-id="0a9c2-148">라오어</span><span class="sxs-lookup"><span data-stu-id="0a9c2-148">Lao</span></span>

- <span data-ttu-id="0a9c2-149">라틴어</span><span class="sxs-lookup"><span data-stu-id="0a9c2-149">Latin</span></span>

- <span data-ttu-id="0a9c2-150">말라얄람어</span><span class="sxs-lookup"><span data-stu-id="0a9c2-150">Malayalam</span></span>

- <span data-ttu-id="0a9c2-151">몽골어</span><span class="sxs-lookup"><span data-stu-id="0a9c2-151">Mongolian</span></span>

- <span data-ttu-id="0a9c2-152">오리야어</span><span class="sxs-lookup"><span data-stu-id="0a9c2-152">Odia</span></span>

- <span data-ttu-id="0a9c2-153">시리아어</span><span class="sxs-lookup"><span data-stu-id="0a9c2-153">Syriac</span></span>

- <span data-ttu-id="0a9c2-154">타밀어</span><span class="sxs-lookup"><span data-stu-id="0a9c2-154">Tamil</span></span>

- <span data-ttu-id="0a9c2-155">텔루구어</span><span class="sxs-lookup"><span data-stu-id="0a9c2-155">Telugu</span></span>

- <span data-ttu-id="0a9c2-156">타나 문자</span><span class="sxs-lookup"><span data-stu-id="0a9c2-156">Thaana</span></span>

- <span data-ttu-id="0a9c2-157">태국어\*</span><span class="sxs-lookup"><span data-stu-id="0a9c2-157">Thai\*</span></span>

- <span data-ttu-id="0a9c2-158">티베트어</span><span class="sxs-lookup"><span data-stu-id="0a9c2-158">Tibetan</span></span>

 <span data-ttu-id="0a9c2-159">\* 이 릴리스에서는 태국어 텍스트의 표시 및 편집이 지원되며, 단어 구분은 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0a9c2-159">\*In this release the display and editing of Thai text is supported; word breaking is not.</span></span>

 <span data-ttu-id="0a9c2-160">현재 지원되지 않는 스크립트는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="0a9c2-160">The following scripts are not currently supported:</span></span>

- <span data-ttu-id="0a9c2-161">크메르어</span><span class="sxs-lookup"><span data-stu-id="0a9c2-161">Khmer</span></span>

- <span data-ttu-id="0a9c2-162">한국어 옛 한글</span><span class="sxs-lookup"><span data-stu-id="0a9c2-162">Korean Old Hangul</span></span>

- <span data-ttu-id="0a9c2-163">미얀마어</span><span class="sxs-lookup"><span data-stu-id="0a9c2-163">Myanmar</span></span>

- <span data-ttu-id="0a9c2-164">스리랑카어</span><span class="sxs-lookup"><span data-stu-id="0a9c2-164">Sinhala</span></span>

 <span data-ttu-id="0a9c2-165">모든 쓰기 시스템 엔진은 OpenType 글꼴을 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="0a9c2-165">All the writing system engines support OpenType fonts.</span></span> <span data-ttu-id="0a9c2-166">OpenType 글꼴에는 글꼴 작성자가 향상 된 국제 글꼴 및 고급 인쇄 글꼴을 디자인할 수 있도록 하는 OpenType 레이아웃 테이블이 포함 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0a9c2-166">OpenType fonts can include the OpenType layout tables that enable font creators to design better international and high-end typographic fonts.</span></span> <span data-ttu-id="0a9c2-167">OpenType 글꼴 레이아웃 표에는 문자 모양 대체, 문자 모양 위치 지정, 양쪽 맞춤 및 기준선 위치에 대 한 정보가 포함 되어 텍스트 처리 응용 프로그램이 텍스트 레이아웃을 향상 시킬 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="0a9c2-167">The OpenType font layout tables contain information about glyph substitutions, glyph positioning, justification, and baseline positioning, enabling text-processing applications to improve text layout.</span></span>

 <span data-ttu-id="0a9c2-168">OpenType 글꼴을 사용 하면 유니코드 인코딩을 사용 하 여 긴 문자 모양 집합을 처리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0a9c2-168">OpenType fonts allow the handling of large glyph sets using Unicode encoding.</span></span> <span data-ttu-id="0a9c2-169">이러한 인코딩을 사용하면 글꼴 문자 모양 변형 외에도 광범위한 국가별 지원이 가능합니다.</span><span class="sxs-lookup"><span data-stu-id="0a9c2-169">Such encoding enables broad international support as well as for typographic glyph variants.</span></span>

 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <span data-ttu-id="0a9c2-170">텍스트 렌더링은 해상도 독립성을 지 원하는 Microsoft ClearType 하위 픽셀 기술을 기반으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="0a9c2-170">text rendering is powered by Microsoft ClearType sub-pixel technology that supports resolution independence.</span></span> <span data-ttu-id="0a9c2-171">이 기능을 통해 가독성이 크게 향상되며, 모든 스크립트에 대해 고품질 잡지 스타일 문서를 지원하는 기능을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="0a9c2-171">This significantly improves legibility and provides the ability to support high quality magazine style documents for all scripts.</span></span>

<a name="intl_layout"></a>
### <a name="international-layout"></a><span data-ttu-id="0a9c2-172">국가별 레이아웃</span><span class="sxs-lookup"><span data-stu-id="0a9c2-172">International Layout</span></span>
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]<span data-ttu-id="0a9c2-173">에서는 가로, 양방향 및 세로 레이아웃을 지원하는 매우 편리한 방법을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="0a9c2-173">provides a very convenient way to support horizontal, bidirectional, and vertical layouts.</span></span> <span data-ttu-id="0a9c2-174">프레젠테이션 프레임 워크에서 <xref:System.Windows.FrameworkElement.FlowDirection%2A> 속성을 사용 하 여 레이아웃을 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0a9c2-174">In presentation framework the <xref:System.Windows.FrameworkElement.FlowDirection%2A> property can be used to define layout.</span></span> <span data-ttu-id="0a9c2-175">흐름 방향 패턴은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="0a9c2-175">The flow direction patterns are:</span></span>

- <span data-ttu-id="0a9c2-176">*LeftToRight* - 라틴어, 동아시아어 등을 위한 가로 레이아웃.</span><span class="sxs-lookup"><span data-stu-id="0a9c2-176">*LeftToRight* - horizontal layout for Latin, East Asian and so forth.</span></span>

- <span data-ttu-id="0a9c2-177">*RightToLeft* - 아랍어, 히브리어 등을 위한 양방향.</span><span class="sxs-lookup"><span data-stu-id="0a9c2-177">*RightToLeft* - bidirectional for Arabic, Hebrew and so forth.</span></span>

<a name="developing_localizable_apps"></a>
## <a name="developing-localizable-applications"></a><span data-ttu-id="0a9c2-178">지역화 가능 애플리케이션 개발</span><span class="sxs-lookup"><span data-stu-id="0a9c2-178">Developing Localizable Applications</span></span>
 <span data-ttu-id="0a9c2-179">글로벌 사용을 위해 애플리케이션을 작성할 때 애플리케이션을 지역화해야 한다는 점에 유의해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0a9c2-179">When you write an application for global consumption you should keep in mind that the application must be localizable.</span></span> <span data-ttu-id="0a9c2-180">다음 항목에서는 고려할 사항을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="0a9c2-180">The following topics point out things to consider.</span></span>

<a name="mui"></a>
### <a name="multilingual-user-interface"></a><span data-ttu-id="0a9c2-181">다국어 사용자 인터페이스</span><span class="sxs-lookup"><span data-stu-id="0a9c2-181">Multilingual User Interface</span></span>
 <span data-ttu-id="0a9c2-182">MUI (다국어 사용자 인터페이스)는 한 언어에서 다른 언어로 Ui를 전환 하기 위한 Microsoft 지원입니다.</span><span class="sxs-lookup"><span data-stu-id="0a9c2-182">Multilingual User Interfaces (MUI) is a Microsoft support for switching UIs from one language to another.</span></span> <span data-ttu-id="0a9c2-183">[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 응용 프로그램은 어셈블리 모델을 사용 하 여 MUI를 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="0a9c2-183">A [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] application uses the assembly model to support MUI.</span></span> <span data-ttu-id="0a9c2-184">한 애플리케이션에는 언어 중립 어셈블리 외에도 언어별 위성 리소스 어셈블리도 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="0a9c2-184">One application contains language-neutral assemblies as well as language-dependent satellite resource assemblies.</span></span> <span data-ttu-id="0a9c2-185">진입점은 기본 어셈블리에서 관리되는 .EXE입니다.</span><span class="sxs-lookup"><span data-stu-id="0a9c2-185">The entry point is a managed .EXE in the main assembly.</span></span>  [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <span data-ttu-id="0a9c2-186">리소스 로더는 프레임 워크의 resource manager를 활용 하 여 리소스 조회 및 대체를 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="0a9c2-186">resource loader takes advantage of the Framework's resource manager to support resource lookup and fallback.</span></span> <span data-ttu-id="0a9c2-187">여러 언어 위성 어셈블리는 동일한 기본 어셈블리와 작동합니다.</span><span class="sxs-lookup"><span data-stu-id="0a9c2-187">Multiple language satellite assemblies work with the same main assembly.</span></span> <span data-ttu-id="0a9c2-188">로드 되는 리소스 어셈블리는 현재 스레드의 <xref:System.Globalization.CultureInfo.CurrentUICulture%2A>에 따라 달라 집니다.</span><span class="sxs-lookup"><span data-stu-id="0a9c2-188">The resource assembly that is loaded depends on the <xref:System.Globalization.CultureInfo.CurrentUICulture%2A> of the current thread.</span></span>

<a name="localizable_ui"></a>
### <a name="localizable-user-interface"></a><span data-ttu-id="0a9c2-189">지역화할 수 있는 사용자 인터페이스</span><span class="sxs-lookup"><span data-stu-id="0a9c2-189">Localizable User Interface</span></span>
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <span data-ttu-id="0a9c2-190">응용 프로그램은 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]를 사용 하 여 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]을 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="0a9c2-190">applications use [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] to define their [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)].</span></span> [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]<span data-ttu-id="0a9c2-191">를 사용하면 개발자가 속성 및 논리 집합이 포함된 개체의 계층 구조를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0a9c2-191">allows developers to specify a hierarchy of objects with a set of properties and logic.</span></span> <span data-ttu-id="0a9c2-192">[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]의 주요 용도는 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 응용 프로그램을 개발 하는 것 이지만 CLR (공용 언어 런타임) 개체의 계층 구조를 지정 하는 데 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0a9c2-192">The primary use of [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] is to develop [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] applications but it can be used to specify a hierarchy of any common language runtime (CLR) objects.</span></span> <span data-ttu-id="0a9c2-193">대부분의 개발자는 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]를 사용 하 여 응용 프로그램의 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]를 지정 하 고 C# 와 같은 프로그래밍 언어를 사용 하 여 사용자 상호 작용에 대응 합니다.</span><span class="sxs-lookup"><span data-stu-id="0a9c2-193">Most developers use [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] to specify their application's [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] and use a programming language such as C# to react to user interaction.</span></span>

 <span data-ttu-id="0a9c2-194">리소스 관점에서 언어 종속 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]를 설명 하도록 디자인 된 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 파일은 리소스 요소 이므로 최종 배포 형식을 지역화 하 여 국제 언어를 지원 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0a9c2-194">From a resource point of view, a [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] file designed to describe a language-dependent [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] is a resource element and therefore its final distribution format must be localizable to support international languages.</span></span> <span data-ttu-id="0a9c2-195">[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]는 이벤트를 처리할 수 없기 때문에 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 응용 프로그램은이 작업을 수행 하는 코드 블록을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="0a9c2-195">Because [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] cannot handle events many [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] applications contain blocks of code to do this.</span></span> <span data-ttu-id="0a9c2-196">자세한 내용은 [XAML 개요 (WPF)](../../../desktop-wpf/fundamentals/xaml.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="0a9c2-196">For more information, see [XAML Overview (WPF)](../../../desktop-wpf/fundamentals/xaml.md).</span></span> <span data-ttu-id="0a9c2-197">[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 파일이 BAML 형식의 XAML로 토큰화 될 때 코드는 제거 되 고 다른 이진 파일로 컴파일됩니다.</span><span class="sxs-lookup"><span data-stu-id="0a9c2-197">Code is stripped out and compiled into different binaries when a [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] file is tokenized into the BAML form of XAML.</span></span> <span data-ttu-id="0a9c2-198">XAML 파일의 BAML 양식, 이미지 및 기타 형식의 관리 리소스 개체는 위성 리소스 어셈블리에 포함되어 다른 언어로 지역화되거나, 지역화가 필요하지 않은 경우 기본 어셈블리에 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="0a9c2-198">The BAML form of XAML files, images, and other types of managed resource objects are embedded in the satellite resource assembly, which can be localized into other languages, or the main assembly when localization is not required.</span></span>

> [!NOTE]
> [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <span data-ttu-id="0a9c2-199">응용 프로그램은 문자열 테이블, 이미지 등을 비롯 한 모든 FrameworkCLR 리소스를 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="0a9c2-199">applications support all the FrameworkCLR resources including string tables, images, and so forth.</span></span>

<a name="building_localizable_apps"></a>
### <a name="building-localizable-applications"></a><span data-ttu-id="0a9c2-200">지역화 가능 애플리케이션 빌드</span><span class="sxs-lookup"><span data-stu-id="0a9c2-200">Building Localizable Applications</span></span>
 <span data-ttu-id="0a9c2-201">지역화는 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]을 다른 문화권에 맞게 조정 하는 것을 의미 합니다.</span><span class="sxs-lookup"><span data-stu-id="0a9c2-201">Localization means to adapt a [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] to different cultures.</span></span> <span data-ttu-id="0a9c2-202">[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 응용 프로그램을 지역화 가능 하 게 만들려면 개발자가 지역화 가능한 리소스를 모두 리소스 어셈블리에 빌드해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0a9c2-202">To make a [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] application localizable, developers need to build all the localizable resources into a resource assembly.</span></span> <span data-ttu-id="0a9c2-203">리소스 어셈블리는 다른 언어로 지역화 되며 코드 숨김이 리소스 관리 API를 사용 하 여 로드 합니다.</span><span class="sxs-lookup"><span data-stu-id="0a9c2-203">The resource assembly is localized into different languages, and the code-behind uses resource management API to load.</span></span> <span data-ttu-id="0a9c2-204">[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 응용 프로그램에 필요한 파일 중 하나는 프로젝트 파일 (proj)입니다.</span><span class="sxs-lookup"><span data-stu-id="0a9c2-204">One of the files required for a [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] application is a project file (.proj).</span></span> <span data-ttu-id="0a9c2-205">애플리케이션에서 사용하는 모든 리소스는 프로젝트 파일에 포함되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0a9c2-205">All resources that you use in your application should be included in the project file.</span></span> <span data-ttu-id="0a9c2-206">.csprop 파일의 다음 예에서는 이 작업을 수행하는 방법을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="0a9c2-206">The following example from a .csproj file shows how to do this.</span></span>

```xml
<Resource Include="data\picture1.jpg"/>
<EmbeddedResource Include="data\stringtable.en-US.restext"/>
```

 <span data-ttu-id="0a9c2-207">응용 프로그램에서 리소스를 사용 하려면 <xref:System.Resources.ResourceManager>를 인스턴스화하고 사용 하려는 리소스를 로드 합니다.</span><span class="sxs-lookup"><span data-stu-id="0a9c2-207">To use a resource in your application instantiate a <xref:System.Resources.ResourceManager> and load the resource you want to use.</span></span> <span data-ttu-id="0a9c2-208">다음 예제에서는 이 작업을 수행하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="0a9c2-208">The following example demonstrates how to do this.</span></span>

 [!code-csharp[LocalizationResources#2](~/samples/snippets/csharp/VS_Snippets_Wpf/LocalizationResources/CSharp/page1.xaml.cs#2)]

<a name="using_clickonce"></a>
## <a name="using-clickonce-with-localized-applications"></a><span data-ttu-id="0a9c2-209">지역화된 애플리케이션에서 ClickOnce 사용</span><span class="sxs-lookup"><span data-stu-id="0a9c2-209">Using ClickOnce with Localized Applications</span></span>
 <span data-ttu-id="0a9c2-210">ClickOnce는 Visual Studio 2005와 함께 제공 되는 새로운 Windows Forms 배포 기술입니다.</span><span class="sxs-lookup"><span data-stu-id="0a9c2-210">ClickOnce is a new Windows Forms deployment technology that will ship with Visual Studio 2005.</span></span> <span data-ttu-id="0a9c2-211">애플리케이션 설치 및 웹 애플리케이션의 업그레이드를 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0a9c2-211">It enables application installation and upgrading of Web applications.</span></span> <span data-ttu-id="0a9c2-212">ClickOnce로 배포된 애플리케이션이 지역화되면 지역화된 문화권에서만 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0a9c2-212">When an application that was deployed with ClickOnce is localized it can only be viewed on the localized culture.</span></span> <span data-ttu-id="0a9c2-213">예를 들어 배포 된 응용 프로그램이 일본어로 지역화 된 경우 영어 창이 아닌 일본어 Microsoft Windows 에서만 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0a9c2-213">For example, if a deployed application is localized to Japanese it can only be viewed on Japanese Microsoft Windows not on English Windows.</span></span> <span data-ttu-id="0a9c2-214">이것은 일본어 사용자가 영어 버전의 Windows를 실행 하는 일반적인 시나리오 이기 때문에 문제가 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="0a9c2-214">This presents a problem because it is a common scenario for Japanese users to run an English version of Windows.</span></span>

 <span data-ttu-id="0a9c2-215">이 문제는 중립 언어 대체 특성을 설정하여 해결합니다.</span><span class="sxs-lookup"><span data-stu-id="0a9c2-215">The solution to this problem is setting the neutral language fallback attribute.</span></span> <span data-ttu-id="0a9c2-216">애플리케이션 개발자가 선택적으로 기본 어셈블리에서 리소스를 제거하고 특정 문화권에 해당하는 위성 어셈블리에서 해당 리소스를 찾을 수 있게 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0a9c2-216">An application developer can optionally remove resources from the main assembly and specify that the resources can be found in a satellite assembly corresponding to a specific culture.</span></span> <span data-ttu-id="0a9c2-217">이 프로세스를 제어 하려면 <xref:System.Resources.NeutralResourcesLanguageAttribute>을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="0a9c2-217">To control this process use the <xref:System.Resources.NeutralResourcesLanguageAttribute>.</span></span> <span data-ttu-id="0a9c2-218"><xref:System.Resources.NeutralResourcesLanguageAttribute> 클래스의 생성자에는 두 개의 시그니처가 있습니다. 하나는 <xref:System.Resources.UltimateResourceFallbackLocation> 매개 변수를 사용 하 여 <xref:System.Resources.ResourceManager>에서 대체 리소스를 추출할 위치를 지정 합니다. 주 어셈블리 또는 위성 어셈블리입니다.</span><span class="sxs-lookup"><span data-stu-id="0a9c2-218">The constructor of the <xref:System.Resources.NeutralResourcesLanguageAttribute> class has two signatures, one that takes an <xref:System.Resources.UltimateResourceFallbackLocation> parameter to specify the location where the <xref:System.Resources.ResourceManager> should extract the fallback resources: main assembly or satellite assembly.</span></span> <span data-ttu-id="0a9c2-219">다음 예제에서는 이 특성을 사용하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="0a9c2-219">The following example shows how to use the attribute.</span></span> <span data-ttu-id="0a9c2-220">최종 대체 (fallback) 위치에 대 한 코드는 <xref:System.Resources.ResourceManager>에서 현재 실행 중인 어셈블리의 디렉터리에 있는 "de" 하위 디렉터리에 있는 리소스를 찾도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="0a9c2-220">For the ultimate fallback location, the code causes the <xref:System.Resources.ResourceManager> to look for the resources in the "de" subdirectory of the directory of the currently executing assembly.</span></span>

```csharp
[assembly: NeutralResourcesLanguageAttribute(
    "de" , UltimateResourceFallbackLocation.Satellite)]
```

## <a name="see-also"></a><span data-ttu-id="0a9c2-221">참조</span><span class="sxs-lookup"><span data-stu-id="0a9c2-221">See also</span></span>

- [<span data-ttu-id="0a9c2-222">WPF 전역화 및 지역화 개요</span><span class="sxs-lookup"><span data-stu-id="0a9c2-222">WPF Globalization and Localization Overview</span></span>](wpf-globalization-and-localization-overview.md)
