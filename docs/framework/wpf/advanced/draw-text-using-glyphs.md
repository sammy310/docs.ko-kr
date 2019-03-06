---
title: 문자 모양을 사용하여 텍스트 그리기
ms.date: 03/30/2017
helpviewer_keywords:
- text [WPF], drawing with Glyphs objects
- Glyphs objects [WPF], drawing text
- typography [WPF], Glyphs objects
ms.assetid: 587ab17e-a419-4ad5-b6da-8933a8e83d97
ms.openlocfilehash: 155f0b756b43ad8cfd0ddde63a5e86854f5f1624
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/05/2019
ms.locfileid: "57363009"
---
# <a name="draw-text-using-glyphs"></a><span data-ttu-id="69e8c-102">문자 모양을 사용하여 텍스트 그리기</span><span class="sxs-lookup"><span data-stu-id="69e8c-102">Draw Text Using Glyphs</span></span>
<span data-ttu-id="69e8c-103">이 항목에서는 하위 수준 사용 하는 방법에 설명 <xref:System.Windows.Documents.Glyphs> 에서 텍스트를 표시 하는 개체 [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]합니다.</span><span class="sxs-lookup"><span data-stu-id="69e8c-103">This topic explains how to use the low-level <xref:System.Windows.Documents.Glyphs> object to display text in [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)].</span></span>  
  
## <a name="example"></a><span data-ttu-id="69e8c-104">예제</span><span class="sxs-lookup"><span data-stu-id="69e8c-104">Example</span></span>  
 <span data-ttu-id="69e8c-105">다음 예제에서는 속성을 정의 하는 방법을 보여는 <xref:System.Windows.Documents.Glyphs> 개체의 [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]합니다.</span><span class="sxs-lookup"><span data-stu-id="69e8c-105">The following examples show how to define properties for a <xref:System.Windows.Documents.Glyphs> object in [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)].</span></span> <span data-ttu-id="69e8c-106">합니다 <xref:System.Windows.Documents.Glyphs> 개체의 출력을 나타냅니다는 <xref:System.Windows.Media.GlyphRun> 에서 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]합니다.</span><span class="sxs-lookup"><span data-stu-id="69e8c-106">The <xref:System.Windows.Documents.Glyphs> object represents the output of a <xref:System.Windows.Media.GlyphRun> in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)].</span></span> <span data-ttu-id="69e8c-107">이 예에서는 로컬 컴퓨터의 C:\WINDOWS\Fonts 폴더에 Arial, Courier New 및 Times New Roman 글꼴이 설치되어 있다고 가정합니다.</span><span class="sxs-lookup"><span data-stu-id="69e8c-107">The examples assume that the Arial, Courier New, and Times New Roman fonts are installed in the C:\WINDOWS\Fonts folder on the local computer.</span></span>  
  
 [!code-xaml[GlyphsOvwSample1#1](~/samples/snippets/csharp/VS_Snippets_Wpf/GlyphsOvwSample1/CS/default.xaml#1)]  
  
 <span data-ttu-id="69e8c-108">이 예의 다른 속성을 정의 하는 방법을 보여 줍니다 <xref:System.Windows.Documents.Glyphs> 개체 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]합니다.</span><span class="sxs-lookup"><span data-stu-id="69e8c-108">This example shows how to define other properties of <xref:System.Windows.Documents.Glyphs> objects in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)].</span></span>  
  
 [!code-xaml[GlyphsOvwSamp2#1](~/samples/snippets/csharp/VS_Snippets_Wpf/GlyphsOvwSamp2/CS/default.xaml#1)]  
  
## <a name="see-also"></a><span data-ttu-id="69e8c-109">참고자료</span><span class="sxs-lookup"><span data-stu-id="69e8c-109">See also</span></span>
- [<span data-ttu-id="69e8c-110">WPF의 입력 체계</span><span class="sxs-lookup"><span data-stu-id="69e8c-110">Typography in WPF</span></span>](typography-in-wpf.md)
