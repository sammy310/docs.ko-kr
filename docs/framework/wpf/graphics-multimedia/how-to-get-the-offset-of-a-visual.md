---
title: '방법: 시각적 요소의 오프셋 가져오기'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- getting offset values from visual objects [WPF]
- offset values [WPF], retrieving from visual objects [WPF]
- visual objects [WPF], retrieving offset values from
- retrieving offset values from visual objects [WPF]
ms.assetid: 889a1dd6-1b11-445a-b351-fbb04c53ee34
ms.openlocfilehash: ea03f7b9c3fefde0efa3fa0daaa07a537618f37a
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/05/2019
ms.locfileid: "57374325"
---
# <a name="how-to-get-the-offset-of-a-visual"></a><span data-ttu-id="67d94-102">방법: 시각적 요소의 오프셋 가져오기</span><span class="sxs-lookup"><span data-stu-id="67d94-102">How to: Get the Offset of a Visual</span></span>
<span data-ttu-id="67d94-103">이러한 예제에는 해당 부모 또는 상위 항목 또는 하위 항목을 기준으로 하는 시각적 개체의 오프셋된 값을 검색 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="67d94-103">These examples show how to retrieve the offset value of a visual object that is relative to its parent, or any ancestor or descendant.</span></span>  
  
## <a name="example"></a><span data-ttu-id="67d94-104">예제</span><span class="sxs-lookup"><span data-stu-id="67d94-104">Example</span></span>  
 <span data-ttu-id="67d94-105">다음 태그 예제는 <xref:System.Windows.Controls.TextBlock> 로 정의 된 <xref:System.Windows.FrameworkElement.Margin%2A> 4의 값입니다.</span><span class="sxs-lookup"><span data-stu-id="67d94-105">The following markup example shows a <xref:System.Windows.Controls.TextBlock> that is defined with <xref:System.Windows.FrameworkElement.Margin%2A> value of 4.</span></span>  
  
 [!code-xaml[VisualSnippets#VisualSnippet1](~/samples/snippets/csharp/VS_Snippets_Wpf/VisualSnippets/CSharp/Window1.xaml#visualsnippet1)]  
  
 <span data-ttu-id="67d94-106">다음 코드 예제를 사용 하는 방법을 보여 줍니다 합니다 <xref:System.Windows.Media.VisualTreeHelper.GetOffset%2A> 의 오프셋을 검색 하는 메서드는 <xref:System.Windows.Controls.TextBlock>합니다.</span><span class="sxs-lookup"><span data-stu-id="67d94-106">The following code example shows how to use the <xref:System.Windows.Media.VisualTreeHelper.GetOffset%2A> method to retrieve the offset of the <xref:System.Windows.Controls.TextBlock>.</span></span> <span data-ttu-id="67d94-107">오프셋된 값이 포함 되어 반환 된 <xref:System.Windows.Vector> 값입니다.</span><span class="sxs-lookup"><span data-stu-id="67d94-107">The offset values are contained within the returned <xref:System.Windows.Vector> value.</span></span>  
  
 [!code-csharp[VisualSnippets#VisualSnippet2](~/samples/snippets/csharp/VS_Snippets_Wpf/VisualSnippets/CSharp/Window1.xaml.cs#visualsnippet2)]
 [!code-vb[VisualSnippets#VisualSnippet2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/VisualSnippets/visualbasic/window1.xaml.vb#visualsnippet2)]  
  
 <span data-ttu-id="67d94-108">오프셋을 고려 합니다 <xref:System.Windows.FrameworkElement.Margin%2A> 값입니다.</span><span class="sxs-lookup"><span data-stu-id="67d94-108">The offset takes into account the <xref:System.Windows.FrameworkElement.Margin%2A> value.</span></span> <span data-ttu-id="67d94-109">이 예에서 <xref:System.Windows.Vector.X%2A> 가 4 및 <xref:System.Windows.Vector.Y%2A> 은 4입니다.</span><span class="sxs-lookup"><span data-stu-id="67d94-109">In this case, <xref:System.Windows.Vector.X%2A> is 4, and <xref:System.Windows.Vector.Y%2A> is 4.</span></span>  
  
 <span data-ttu-id="67d94-110">부모에 상대적인 오프셋된 값이 반환된 됩니다는 <xref:System.Windows.Media.Visual>합니다.</span><span class="sxs-lookup"><span data-stu-id="67d94-110">The returned offset value is relative to the parent of the <xref:System.Windows.Media.Visual>.</span></span> <span data-ttu-id="67d94-111">부모에 상대적인 없는 오프셋된 값을 반환 하려는 경우는 <xref:System.Windows.Media.Visual>를 사용 하 여를 <xref:System.Windows.Media.Visual.TransformToAncestor%2A> 메서드.</span><span class="sxs-lookup"><span data-stu-id="67d94-111">If you want to return an offset value that is not relative to the parent of a <xref:System.Windows.Media.Visual>, use the <xref:System.Windows.Media.Visual.TransformToAncestor%2A> method.</span></span>  
  
## <a name="getting-the-offset-relative-to-an-ancestor"></a><span data-ttu-id="67d94-112">상위 요소에 상대적인 오프셋 가져오기</span><span class="sxs-lookup"><span data-stu-id="67d94-112">Getting the Offset Relative to an Ancestor</span></span>  
 <span data-ttu-id="67d94-113">다음 태그 예제는 <xref:System.Windows.Controls.TextBlock> 안에 두 개의 중첩 된 <xref:System.Windows.Controls.StackPanel> 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="67d94-113">The following markup example shows a <xref:System.Windows.Controls.TextBlock> that is nested within two <xref:System.Windows.Controls.StackPanel> objects.</span></span>  
  
 [!code-xaml[VisualSnippets#VisualSnippet7](~/samples/snippets/csharp/VS_Snippets_Wpf/VisualSnippets/CSharp/Window2.xaml#visualsnippet7)]  
  
 <span data-ttu-id="67d94-114">다음 그림에서는 태그의 결과 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="67d94-114">The following illustration shows the results of the markup.</span></span>  
  
 <span data-ttu-id="67d94-115">![개체의 값을 오프셋](./media/visualoffset-01.png "VisualOffset_01")</span><span class="sxs-lookup"><span data-stu-id="67d94-115">![Offset values of objects](./media/visualoffset-01.png "VisualOffset_01")</span></span>  
<span data-ttu-id="67d94-116">두 Stackpanel 내에 중첩 된 TextBlock</span><span class="sxs-lookup"><span data-stu-id="67d94-116">TextBlock nested within two StackPanels</span></span>  
  
 <span data-ttu-id="67d94-117">다음 코드 예제를 사용 하는 방법을 보여 줍니다 합니다 <xref:System.Windows.Media.Visual.TransformToAncestor%2A> 의 오프셋을 검색 하는 메서드를 <xref:System.Windows.Controls.TextBlock> 포함 하는 기준으로 <xref:System.Windows.Window>입니다.</span><span class="sxs-lookup"><span data-stu-id="67d94-117">The following code example shows how to use the <xref:System.Windows.Media.Visual.TransformToAncestor%2A> method to retrieve the offset of the <xref:System.Windows.Controls.TextBlock> relative to the containing <xref:System.Windows.Window>.</span></span> <span data-ttu-id="67d94-118">오프셋된 값이 포함 되어 반환 된 <xref:System.Windows.Media.GeneralTransform> 값입니다.</span><span class="sxs-lookup"><span data-stu-id="67d94-118">The offset values are contained within the returned <xref:System.Windows.Media.GeneralTransform> value.</span></span>  
  
 [!code-csharp[VisualSnippets#VisualSnippet5](~/samples/snippets/csharp/VS_Snippets_Wpf/VisualSnippets/CSharp/Window1.xaml.cs#visualsnippet5)]
 [!code-vb[VisualSnippets#VisualSnippet5](~/samples/snippets/visualbasic/VS_Snippets_Wpf/VisualSnippets/visualbasic/window1.xaml.vb#visualsnippet5)]  
  
 <span data-ttu-id="67d94-119">오프셋을 고려 합니다 <xref:System.Windows.FrameworkElement.Margin%2A> 내의 포함 하는 모든 개체에 대 한 값 <xref:System.Windows.Window>합니다.</span><span class="sxs-lookup"><span data-stu-id="67d94-119">The offset takes into account the <xref:System.Windows.FrameworkElement.Margin%2A> values for all objects within the containing <xref:System.Windows.Window>.</span></span> <span data-ttu-id="67d94-120">이 예에서 <xref:System.Windows.Vector.X%2A> 는 28 (16 + 8 + 4) 및 <xref:System.Windows.Vector.Y%2A> 는 28입니다.</span><span class="sxs-lookup"><span data-stu-id="67d94-120">In this case, <xref:System.Windows.Vector.X%2A> is 28 (16 + 8 + 4), and <xref:System.Windows.Vector.Y%2A> is 28.</span></span>  
  
 <span data-ttu-id="67d94-121">반환된 된 오프셋된 값의 상위 항목을 기준으로는 <xref:System.Windows.Media.Visual>합니다.</span><span class="sxs-lookup"><span data-stu-id="67d94-121">The returned offset value is relative to the ancestor of the <xref:System.Windows.Media.Visual>.</span></span> <span data-ttu-id="67d94-122">하위 항목에 상대적인 오프셋된 값을 반환 하려는 경우는 <xref:System.Windows.Media.Visual>를 사용 하 여를 <xref:System.Windows.Media.Visual.TransformToDescendant%2A> 메서드.</span><span class="sxs-lookup"><span data-stu-id="67d94-122">If you want to return an offset value that is relative to the descendant of a <xref:System.Windows.Media.Visual>, use the <xref:System.Windows.Media.Visual.TransformToDescendant%2A> method.</span></span>  
  
## <a name="getting-the-offset-relative-to-a-descendant"></a><span data-ttu-id="67d94-123">하위 요소에 상대적인 오프셋 가져오기</span><span class="sxs-lookup"><span data-stu-id="67d94-123">Getting the Offset Relative to a Descendant</span></span>  
 <span data-ttu-id="67d94-124">다음 태그 예제는 <xref:System.Windows.Controls.TextBlock> 에 포함 된를 <xref:System.Windows.Controls.StackPanel> 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="67d94-124">The following markup example shows a <xref:System.Windows.Controls.TextBlock> that is contained within a <xref:System.Windows.Controls.StackPanel> object.</span></span>  
  
 [!code-xaml[VisualSnippets#VisualSnippet4](~/samples/snippets/csharp/VS_Snippets_Wpf/VisualSnippets/CSharp/Window1.xaml#visualsnippet4)]  
  
 <span data-ttu-id="67d94-125">다음 코드 예제를 사용 하는 방법을 보여 줍니다 합니다 <xref:System.Windows.Media.Visual.TransformToDescendant%2A> 의 오프셋을 검색 하는 메서드를 <xref:System.Windows.Controls.StackPanel> 해당 자식에 상대적인 <xref:System.Windows.Controls.TextBlock>합니다.</span><span class="sxs-lookup"><span data-stu-id="67d94-125">The following code example shows how to use the <xref:System.Windows.Media.Visual.TransformToDescendant%2A> method to retrieve the offset of the <xref:System.Windows.Controls.StackPanel> relative to its child <xref:System.Windows.Controls.TextBlock>.</span></span> <span data-ttu-id="67d94-126">오프셋된 값이 포함 되어 반환 된 <xref:System.Windows.Media.GeneralTransform> 값입니다.</span><span class="sxs-lookup"><span data-stu-id="67d94-126">The offset values are contained within the returned <xref:System.Windows.Media.GeneralTransform> value.</span></span>  
  
 [!code-csharp[VisualSnippets#VisualSnippet9](~/samples/snippets/csharp/VS_Snippets_Wpf/VisualSnippets/CSharp/Window1.xaml.cs#visualsnippet9)]
 [!code-vb[VisualSnippets#VisualSnippet9](~/samples/snippets/visualbasic/VS_Snippets_Wpf/VisualSnippets/visualbasic/window1.xaml.vb#visualsnippet9)]  
  
 <span data-ttu-id="67d94-127">오프셋을 고려 합니다 <xref:System.Windows.FrameworkElement.Margin%2A> 모든 개체에 대 한 값입니다.</span><span class="sxs-lookup"><span data-stu-id="67d94-127">The offset takes into account the <xref:System.Windows.FrameworkElement.Margin%2A> values for all objects.</span></span> <span data-ttu-id="67d94-128">이 예에서 <xref:System.Windows.Vector.X%2A> -4 이며, 및 <xref:System.Windows.Vector.Y%2A> -4 이며, 합니다.</span><span class="sxs-lookup"><span data-stu-id="67d94-128">In this case, <xref:System.Windows.Vector.X%2A> is -4, and <xref:System.Windows.Vector.Y%2A> is -4.</span></span> <span data-ttu-id="67d94-129">부모 개체는 해당 자식 개체를 기준으로 오프셋 부정적인 되므로 오프셋된 값은 음수 값으로 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="67d94-129">The offset values are negative values, since the parent object is negatively offset relative to its child object.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="67d94-130">참고자료</span><span class="sxs-lookup"><span data-stu-id="67d94-130">See also</span></span>
- <xref:System.Windows.Media.Visual>
- <xref:System.Windows.Media.VisualTreeHelper>
- [<span data-ttu-id="67d94-131">WPF 그래픽 렌더링 개요</span><span class="sxs-lookup"><span data-stu-id="67d94-131">WPF Graphics Rendering Overview</span></span>](wpf-graphics-rendering-overview.md)
