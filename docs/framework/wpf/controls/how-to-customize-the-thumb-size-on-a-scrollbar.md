---
title: '방법: ScrollBar의 Thumb 크기 사용자 지정'
ms.date: 03/30/2017
helpviewer_keywords:
- ScrollBar control [WPF]
- customizing thumb size [WPF]
- thumb size [WPF]
ms.assetid: fa32b866-5ca1-4e73-85e7-2ac64b80d194
ms.openlocfilehash: 60ae7c4e95801036c5deb0c485645297509b830c
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61911055"
---
# <a name="how-to-customize-the-thumb-size-on-a-scrollbar"></a><span data-ttu-id="69bcf-102">방법: ScrollBar의 Thumb 크기 사용자 지정</span><span class="sxs-lookup"><span data-stu-id="69bcf-102">How to: Customize the Thumb Size on a ScrollBar</span></span>
<span data-ttu-id="69bcf-103">이 항목에서는 설정 하는 방법에 설명 합니다 <xref:System.Windows.Controls.Primitives.Thumb> 의 <xref:System.Windows.Controls.Primitives.ScrollBar> 고정 된 크기 및 최소 크기를 지정 하는 방법에는 <xref:System.Windows.Controls.Primitives.Thumb> 의 <xref:System.Windows.Controls.Primitives.ScrollBar>.</span><span class="sxs-lookup"><span data-stu-id="69bcf-103">This topic explains how to set the <xref:System.Windows.Controls.Primitives.Thumb> of a <xref:System.Windows.Controls.Primitives.ScrollBar> to a fixed size and how to specify a minimum size for the <xref:System.Windows.Controls.Primitives.Thumb> of a <xref:System.Windows.Controls.Primitives.ScrollBar>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="69bcf-104">예제</span><span class="sxs-lookup"><span data-stu-id="69bcf-104">Example</span></span>  
  
## <a name="description"></a><span data-ttu-id="69bcf-105">설명</span><span class="sxs-lookup"><span data-stu-id="69bcf-105">Description</span></span>  
 <span data-ttu-id="69bcf-106">다음 예에서는 <xref:System.Windows.Controls.Primitives.ScrollBar> 있는 <xref:System.Windows.Controls.Primitives.Thumb> 고정 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="69bcf-106">The following example creates a <xref:System.Windows.Controls.Primitives.ScrollBar> that has a <xref:System.Windows.Controls.Primitives.Thumb> with a fixed size.</span></span> <span data-ttu-id="69bcf-107">예제에서는 <xref:System.Windows.Controls.Primitives.Track.ViewportSize%2A> 의 속성을 <xref:System.Windows.Controls.Primitives.Thumb> 에 <xref:System.Double.NaN> 의 높이 가져오거나 설정는 <xref:System.Windows.Controls.Primitives.Thumb>.</span><span class="sxs-lookup"><span data-stu-id="69bcf-107">The example sets the <xref:System.Windows.Controls.Primitives.Track.ViewportSize%2A> property of the <xref:System.Windows.Controls.Primitives.Thumb> to <xref:System.Double.NaN> and sets the height of the <xref:System.Windows.Controls.Primitives.Thumb>.</span></span>  <span data-ttu-id="69bcf-108">가로 만들려면 <xref:System.Windows.Controls.Primitives.ScrollBar> 사용 하 여는 <xref:System.Windows.Controls.Primitives.Thumb> 는 고정된 폭, 너비를 설정 합니다 <xref:System.Windows.Controls.Primitives.Thumb>.</span><span class="sxs-lookup"><span data-stu-id="69bcf-108">To create a horizontal <xref:System.Windows.Controls.Primitives.ScrollBar> with a <xref:System.Windows.Controls.Primitives.Thumb> that has a fixed width, set the width of the <xref:System.Windows.Controls.Primitives.Thumb>.</span></span>  
  
## <a name="code"></a><span data-ttu-id="69bcf-109">코드</span><span class="sxs-lookup"><span data-stu-id="69bcf-109">Code</span></span>  
 [!code-xaml[ScrollBarCustomThumbSize#1](~/samples/snippets/csharp/VS_Snippets_Wpf/ScrollBarCustomThumbSize/CS/Window1.xaml#1)]  
  
## <a name="description"></a><span data-ttu-id="69bcf-110">설명</span><span class="sxs-lookup"><span data-stu-id="69bcf-110">Description</span></span>  
 <span data-ttu-id="69bcf-111">다음 예에서는 <xref:System.Windows.Controls.Primitives.ScrollBar> 있는 <xref:System.Windows.Controls.Primitives.Thumb> 최소 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="69bcf-111">The following example creates a <xref:System.Windows.Controls.Primitives.ScrollBar> that has a <xref:System.Windows.Controls.Primitives.Thumb> with a minimum size.</span></span> <span data-ttu-id="69bcf-112">값을 설정 하는 예제 <xref:System.Windows.SystemParameters.VerticalScrollBarButtonHeightKey%2A>합니다.</span><span class="sxs-lookup"><span data-stu-id="69bcf-112">The example sets the value of <xref:System.Windows.SystemParameters.VerticalScrollBarButtonHeightKey%2A>.</span></span> <span data-ttu-id="69bcf-113">가로 만들려면 <xref:System.Windows.Controls.Primitives.ScrollBar> 사용 하 여는 <xref:System.Windows.Controls.Primitives.Thumb> 는 최소 너비에 설정 합니다 <xref:System.Windows.SystemParameters.HorizontalScrollBarButtonWidthKey%2A>합니다.</span><span class="sxs-lookup"><span data-stu-id="69bcf-113">To create a horizontal <xref:System.Windows.Controls.Primitives.ScrollBar> with a <xref:System.Windows.Controls.Primitives.Thumb> that has a minimum width, set the <xref:System.Windows.SystemParameters.HorizontalScrollBarButtonWidthKey%2A>.</span></span>  
  
## <a name="code"></a><span data-ttu-id="69bcf-114">코드</span><span class="sxs-lookup"><span data-stu-id="69bcf-114">Code</span></span>  
 [!code-xaml[ScrollBarCustomThumbSize#2](~/samples/snippets/csharp/VS_Snippets_Wpf/ScrollBarCustomThumbSize/CS/Window1.xaml#2)]  
  
## <a name="see-also"></a><span data-ttu-id="69bcf-115">참고자료</span><span class="sxs-lookup"><span data-stu-id="69bcf-115">See also</span></span>

- [<span data-ttu-id="69bcf-116">ScrollBar 스타일 및 템플릿</span><span class="sxs-lookup"><span data-stu-id="69bcf-116">ScrollBar Styles and Templates</span></span>](scrollbar-styles-and-templates.md)
