---
title: GlyphRun 개체 및 Glyphs 요소 소개
ms.date: 03/30/2017
helpviewer_keywords:
- typography [WPF], Glyphs element
- Glyphs elements [WPF]
- GlyphRun object [WPF]
- text [WPF], glyphs
- glyphs [WPF]
- typography [WPF], GlyphRun object
ms.assetid: 746ca769-a331-4435-9b95-f72a883b67c1
ms.openlocfilehash: 2f7bb3fb4f28b063c78dde9f9f354b38a5e707f3
ms.sourcegitcommit: 1f12db2d852d05bed8c53845f0b5a57a762979c8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2019
ms.locfileid: "72581899"
---
# <a name="introduction-to-the-glyphrun-object-and-glyphs-element"></a><span data-ttu-id="75816-102">GlyphRun 개체 및 Glyphs 요소 소개</span><span class="sxs-lookup"><span data-stu-id="75816-102">Introduction to the GlyphRun Object and Glyphs Element</span></span>
<span data-ttu-id="75816-103">이 항목에서는 <xref:System.Windows.Media.GlyphRun> 개체와 <xref:System.Windows.Documents.Glyphs> 요소에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="75816-103">This topic describes the <xref:System.Windows.Media.GlyphRun> object and the <xref:System.Windows.Documents.Glyphs> element.</span></span>  

<a name="text_glyphrunovw_intro"></a>   
## <a name="introduction-to-glyphrun"></a><span data-ttu-id="75816-104">GlyphRun 소개</span><span class="sxs-lookup"><span data-stu-id="75816-104">Introduction to GlyphRun</span></span>  
 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]<span data-ttu-id="75816-105">는 서식 지정 후 텍스트를 가로채 고 유지 하려는 고객을 위해 <xref:System.Windows.Documents.Glyphs>에 직접 액세스할 수 있는 문자 모양 수준 태그를 포함 한 고급 텍스트 지원을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="75816-105">provides advanced text support including glyph-level markup with direct access to <xref:System.Windows.Documents.Glyphs> for customers who want to intercept and persist text after formatting.</span></span> <span data-ttu-id="75816-106">이러한 기능을 통해 다음과 같은 각 시나리오의 다양한 텍스트 렌더링 요구 사항을 충족시킬 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="75816-106">These features provide critical support for the different text rendering requirements in each of the following scenarios.</span></span>  
  
1. <span data-ttu-id="75816-107">고정된 형식 문서의 화면 표시</span><span class="sxs-lookup"><span data-stu-id="75816-107">Screen display of fixed-format documents.</span></span>  
  
2. <span data-ttu-id="75816-108">인쇄 시나리오</span><span class="sxs-lookup"><span data-stu-id="75816-108">Print scenarios.</span></span>  
  
    - <span data-ttu-id="75816-109">디바이스 프린터 언어로서의 [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]</span><span class="sxs-lookup"><span data-stu-id="75816-109">[!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] as a device printer language.</span></span>  
  
    - <span data-ttu-id="75816-110">Microsoft XPS Document Writer.</span><span class="sxs-lookup"><span data-stu-id="75816-110">Microsoft XPS Document Writer.</span></span>  
  
    - <span data-ttu-id="75816-111">이전 프린터 드라이버, [!INCLUDE[TLA#tla_win32](../../../../includes/tlasharptla-win32-md.md)] 애플리케이션에서 고정된 형식으로의 출력</span><span class="sxs-lookup"><span data-stu-id="75816-111">Previous printer drivers, output from [!INCLUDE[TLA#tla_win32](../../../../includes/tlasharptla-win32-md.md)] applications to the fixed format.</span></span>  
  
    - <span data-ttu-id="75816-112">인쇄 스풀 형식</span><span class="sxs-lookup"><span data-stu-id="75816-112">Print spool format.</span></span>  
  
3. <span data-ttu-id="75816-113">이전 버전의 Windows 및 기타 컴퓨팅 장치에 대 한 클라이언트를 포함 하는 고정 형식 문서 표시입니다.</span><span class="sxs-lookup"><span data-stu-id="75816-113">Fixed-format document representation, including clients for previous versions of Windows and other computing devices.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="75816-114"><xref:System.Windows.Documents.Glyphs> 및 <xref:System.Windows.Media.GlyphRun>은 고정 형식의 문서 프레젠테이션 및 인쇄 시나리오를 위해 설계 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="75816-114"><xref:System.Windows.Documents.Glyphs> and <xref:System.Windows.Media.GlyphRun> are designed for fixed-format document presentation and print scenarios.</span></span> [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]<span data-ttu-id="75816-115">는 일반적인 레이아웃 및 [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] 시나리오에 대 한 여러 요소 (예: <xref:System.Windows.Controls.Label> 및 <xref:System.Windows.Controls.TextBlock>)를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="75816-115">provides several elements for general layout and [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] scenarios such as <xref:System.Windows.Controls.Label> and <xref:System.Windows.Controls.TextBlock>.</span></span> <span data-ttu-id="75816-116">레이아웃 및 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] 시나리오에 대한 자세한 내용은 [WPF의 입력 체계](typography-in-wpf.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="75816-116">For more information on layout and [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] scenarios, see the [Typography in WPF](typography-in-wpf.md).</span></span>  
  
<a name="text_glyphrunovw_glyphrunobject"></a>   
## <a name="the-glyphrun-object"></a><span data-ttu-id="75816-117">GlyphRun 개체</span><span class="sxs-lookup"><span data-stu-id="75816-117">The GlyphRun Object</span></span>  
 <span data-ttu-id="75816-118">@No__t_0 개체는 단일 글꼴의 단일 면에서 단일 크기로 렌더링 스타일을 사용 하 여 문자 모양의 시퀀스를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="75816-118">The <xref:System.Windows.Media.GlyphRun> object represents a sequence of glyphs from a single face of a single font at a single size, and with a single rendering style.</span></span>  
  
 <span data-ttu-id="75816-119"><xref:System.Windows.Media.GlyphRun>에는 문자 모양 <xref:System.Windows.Documents.Glyphs.Indices%2A>와 같은 글꼴 세부 정보와 개별 문자 모양 위치가 모두 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="75816-119"><xref:System.Windows.Media.GlyphRun> includes both font details such as glyph <xref:System.Windows.Documents.Glyphs.Indices%2A> and individual glyph positions.</span></span> <span data-ttu-id="75816-120">또한 실행이 생성 된 원래 유니코드 코드 요소, 문자-문자 모양 버퍼 오프셋 매핑 정보 및 문자별 및 문자 모양 별 플래그를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="75816-120">It also includes the original Unicode code points the run was generated from, character-to-glyph buffer offset mapping information, and per-character and per-glyph flags.</span></span>  
  
 <span data-ttu-id="75816-121"><xref:System.Windows.Media.GlyphRun>에는 해당 하는 상위 수준 <xref:System.Windows.FrameworkElement>, <xref:System.Windows.Documents.Glyphs>가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="75816-121"><xref:System.Windows.Media.GlyphRun> has a corresponding high-level <xref:System.Windows.FrameworkElement>, <xref:System.Windows.Documents.Glyphs>.</span></span> <span data-ttu-id="75816-122"><xref:System.Windows.Documents.Glyphs>는 요소 트리 및 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 태그에서 <xref:System.Windows.Media.GlyphRun> 출력을 나타내는 데 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="75816-122"><xref:System.Windows.Documents.Glyphs> can be used in the element tree and in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] markup to represent <xref:System.Windows.Media.GlyphRun> output.</span></span>  
  
<a name="text_glyphrunovw_glyphselement"></a>   
## <a name="the-glyphs-element"></a><span data-ttu-id="75816-123">문자 모양 요소</span><span class="sxs-lookup"><span data-stu-id="75816-123">The Glyphs Element</span></span>  
 <span data-ttu-id="75816-124">@No__t_0 요소는 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]의 <xref:System.Windows.Media.GlyphRun> 출력을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="75816-124">The <xref:System.Windows.Documents.Glyphs> element represents the output of a <xref:System.Windows.Media.GlyphRun> in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)].</span></span> <span data-ttu-id="75816-125">다음 태그 구문은 <xref:System.Windows.Documents.Glyphs> 요소를 설명 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="75816-125">The following markup syntax is used to describe the <xref:System.Windows.Documents.Glyphs> element.</span></span>  
  
 [!code-xaml[GlyphsOvwSample1#1](~/samples/snippets/csharp/VS_Snippets_Wpf/GlyphsOvwSample1/CS/default.xaml#1)]  
  
 <span data-ttu-id="75816-126">다음 속성 정의는 샘플 태그의 처음 네 특성에 해당합니다.</span><span class="sxs-lookup"><span data-stu-id="75816-126">The following property definitions correspond to the first four attributes in the sample markup.</span></span>  
  
|<span data-ttu-id="75816-127">속성</span><span class="sxs-lookup"><span data-stu-id="75816-127">Property</span></span>|<span data-ttu-id="75816-128">설명</span><span class="sxs-lookup"><span data-stu-id="75816-128">Description</span></span>|  
|--------------|-----------------|  
|<xref:System.Windows.Documents.Glyphs.FontUri%2A>|<span data-ttu-id="75816-129">응용 프로그램 .exe 나 컨테이너에 파일 이름, 웹 URI (uniform resource identifier) 또는 리소스 참조 등의 리소스 식별자를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="75816-129">Specifies a resource identifier: file name, Web uniform resource identifier (URI), or resource reference in the application .exe or container.</span></span>|  
|<xref:System.Windows.Documents.Glyphs.FontRenderingEmSize%2A>|<span data-ttu-id="75816-130">글꼴 크기를 그리기 화면 단위로 지정합니다(기본값은 .96인치).</span><span class="sxs-lookup"><span data-stu-id="75816-130">Specifies the font size in drawing surface units (default is .96 inches).</span></span>|  
|<xref:System.Windows.Documents.Glyphs.StyleSimulations%2A>|<span data-ttu-id="75816-131">굵게 및 기울임꼴 스타일에 대한 플래그를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="75816-131">Specifies flags for bold and Italic styles.</span></span>|  
|<xref:System.Windows.Documents.Glyphs.BidiLevel%2A>|<span data-ttu-id="75816-132">양방향 레이아웃 수준을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="75816-132">Specifies the bidirectional layout level.</span></span> <span data-ttu-id="75816-133">짝수 및 0 값은 왼쪽에서 오른쪽 레이아웃을 나타내며, 홀수 값은 오른쪽에서 왼쪽 레이아웃을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="75816-133">Even-numbered and zero values imply left-to-right layout; odd-numbered values imply right-to-left layout.</span></span>|  
  
<a name="text_glyphrunovw_indicesproperty"></a>   
### <a name="indices-property"></a><span data-ttu-id="75816-134">Indices 속성</span><span class="sxs-lookup"><span data-stu-id="75816-134">Indices property</span></span>  
 <span data-ttu-id="75816-135">@No__t_0 속성은 문자 모양 사양의 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="75816-135">The <xref:System.Windows.Documents.Glyphs.Indices%2A> property is a string of glyph specifications.</span></span> <span data-ttu-id="75816-136">문자 모양의 시퀀스가 단일 클러스터를 구성하는 경우 클러스터 첫 번째 문자 모양의 사양 앞에 문자 모양의 개수와 클러스터를 구성하는 코드 포인트 수에 대한 사양이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="75816-136">Where a sequence of glyphs forms a single cluster, the specification of the first glyph in the cluster is preceded by a specification of how many glyphs and how many code points combine to form the cluster.</span></span> <span data-ttu-id="75816-137">@No__t_0 속성은 다음 속성을 하나의 문자열로 수집 합니다.</span><span class="sxs-lookup"><span data-stu-id="75816-137">The <xref:System.Windows.Documents.Glyphs.Indices%2A> property collects in one string the following properties.</span></span>  
  
- <span data-ttu-id="75816-138">문자 모양 인덱스</span><span class="sxs-lookup"><span data-stu-id="75816-138">Glyph indices</span></span>  
  
- <span data-ttu-id="75816-139">문자 모양의 사전 너비</span><span class="sxs-lookup"><span data-stu-id="75816-139">Glyph advance widths</span></span>  
  
- <span data-ttu-id="75816-140">문자 모양 첨부 벡터 조합</span><span class="sxs-lookup"><span data-stu-id="75816-140">Combining glyph attachment vectors</span></span>  
  
- <span data-ttu-id="75816-141">코드 포인트에서 문자 모양으로 클러스터 매핑</span><span class="sxs-lookup"><span data-stu-id="75816-141">Cluster mapping from code points to glyphs</span></span>  
  
- <span data-ttu-id="75816-142">문자 모양 플래그</span><span class="sxs-lookup"><span data-stu-id="75816-142">Glyph flags</span></span>  
  
 <span data-ttu-id="75816-143">각 문자 모양 사양에는 다음 형식이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="75816-143">Each glyph specification has the following form.</span></span>  
  
 `[GlyphIndex][,[Advance][,[uOffset][,[vOffset][,[Flags]]]]]`  
  
<a name="text_glyphrunovw_glyphmetrics"></a>   
## <a name="glyph-metrics"></a><span data-ttu-id="75816-144">문자 모양 메트릭</span><span class="sxs-lookup"><span data-stu-id="75816-144">Glyph Metrics</span></span>  
 <span data-ttu-id="75816-145">각 문자 모양은 다른 <xref:System.Windows.Documents.Glyphs>에 맞추는 방법을 지정 하는 메트릭을 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="75816-145">Each glyph defines metrics that specify how it aligns with other <xref:System.Windows.Documents.Glyphs>.</span></span> <span data-ttu-id="75816-146">다음 그래픽에서는 서로 다른 두 문자 모양 문자의 다양한 입력 체계의 품질을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="75816-146">The following graphic defines the various typographic qualities of two different glyph characters.</span></span>  
  
 <span data-ttu-id="75816-147">![문자 모양 측정 다이어](./media/glyph-example.png "glyph_example")</span><span class="sxs-lookup"><span data-stu-id="75816-147">![Diagraph of glyph measurements](./media/glyph-example.png "glyph_example")</span></span>  
  
<a name="text_glyphrunovw_glyphsmarkup"></a>   
## <a name="glyphs-markup"></a><span data-ttu-id="75816-148">문자 모양 태그</span><span class="sxs-lookup"><span data-stu-id="75816-148">Glyphs Markup</span></span>  
 <span data-ttu-id="75816-149">다음 코드 예제에서는 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]의 <xref:System.Windows.Documents.Glyphs> 요소에 대 한 다양 한 속성을 사용 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="75816-149">The following code example shows how to use various properties of the <xref:System.Windows.Documents.Glyphs> element in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)].</span></span>  
  
 [!code-xaml[GlyphsOvwSamp2#1](~/samples/snippets/csharp/VS_Snippets_Wpf/GlyphsOvwSamp2/CS/default.xaml#1)]  
  
## <a name="see-also"></a><span data-ttu-id="75816-150">참조</span><span class="sxs-lookup"><span data-stu-id="75816-150">See also</span></span>

- [<span data-ttu-id="75816-151">WPF의 입력 체계</span><span class="sxs-lookup"><span data-stu-id="75816-151">Typography in WPF</span></span>](typography-in-wpf.md)
- [<span data-ttu-id="75816-152">WPF의 문서</span><span class="sxs-lookup"><span data-stu-id="75816-152">Documents in WPF</span></span>](documents-in-wpf.md)
- [<span data-ttu-id="75816-153">텍스트</span><span class="sxs-lookup"><span data-stu-id="75816-153">Text</span></span>](optimizing-performance-text.md)
