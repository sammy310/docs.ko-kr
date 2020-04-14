---
title: '방법: ListView의 사용자 지정 뷰 모드 만들기'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ListView controls [WPF], creating custom View mode
ms.assetid: 71077349-eeb9-4344-ab29-b5df96df3314
ms.openlocfilehash: 3b9ca17bddcecb1895205fca76f0a489ecf25c4f
ms.sourcegitcommit: 7980a91f90ae5eca859db7e6bfa03e23e76a1a50
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/13/2020
ms.locfileid: "81243221"
---
# <a name="how-to-create-a-custom-view-mode-for-a-listview"></a><span data-ttu-id="8114c-102">방법: ListView에 대한 사용자 지정 보기 모드 만들기</span><span class="sxs-lookup"><span data-stu-id="8114c-102">How to: Create a custom view mode for a ListView</span></span>

<span data-ttu-id="8114c-103">이 예제에서는 컨트롤에 <xref:System.Windows.Controls.ListView.View%2A> 대한 사용자 <xref:System.Windows.Controls.ListView> 지정 모드를 만드는 방법을 보여 주며 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8114c-103">This example shows how to create a custom <xref:System.Windows.Controls.ListView.View%2A> mode for a <xref:System.Windows.Controls.ListView> control.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8114c-104">예제</span><span class="sxs-lookup"><span data-stu-id="8114c-104">Example</span></span>  
 <span data-ttu-id="8114c-105">컨트롤에 대한 <xref:System.Windows.Controls.ViewBase> 사용자 지정 보기를 만들 <xref:System.Windows.Controls.ListView> 때 클래스를 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8114c-105">You must use the <xref:System.Windows.Controls.ViewBase> class when you create a custom view for the <xref:System.Windows.Controls.ListView> control.</span></span> <span data-ttu-id="8114c-106">다음 예제에서는 클래스에서 `PlainView` 파생 된 보기 모드라는 것을 보여 주며 <xref:System.Windows.Controls.ViewBase> 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8114c-106">The following example shows a view mode called `PlainView` that's derived from the <xref:System.Windows.Controls.ViewBase> class.</span></span>  
  
 [!code-csharp[ListViewCustomView#PlainView](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewCustomView/CSharp/PlainView.cs#plainview)]
 [!code-vb[ListViewCustomView#PlainView](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ListViewCustomView/visualbasic/plainview.vb#plainview)]  
  
 <span data-ttu-id="8114c-107">사용자 지정 보기에 스타일을 적용하려면 <xref:System.Windows.Style> 클래스를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="8114c-107">To apply a style to the custom view, use the <xref:System.Windows.Style> class.</span></span> <span data-ttu-id="8114c-108">다음 예제는 뷰 <xref:System.Windows.Style> 모드에 대한 a를 정의합니다. `PlainView`</span><span class="sxs-lookup"><span data-stu-id="8114c-108">The following example defines a <xref:System.Windows.Style> for the `PlainView` view mode.</span></span> <span data-ttu-id="8114c-109">이전 예제에서 이 스타일은 에 대해 <xref:System.Windows.Controls.ViewBase.DefaultStyleKey%2A> `PlainView`정의된 속성값으로 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="8114c-109">In the previous example, this style is set as the value of the <xref:System.Windows.Controls.ViewBase.DefaultStyleKey%2A> property that's defined for `PlainView`.</span></span>  
  
 [!code-xaml[ListViewCustomView#PlainViewStyle](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewCustomView/CSharp/Themes/Generic.xaml#plainviewstyle)]  
  
 <span data-ttu-id="8114c-110">사용자 지정 뷰 모드에서 데이터 레이아웃을 정의하려면 개체를 정의합니다. <xref:System.Windows.DataTemplate></span><span class="sxs-lookup"><span data-stu-id="8114c-110">To define the layout of data in a custom view mode, define a <xref:System.Windows.DataTemplate> object.</span></span> <span data-ttu-id="8114c-111">다음 예제에서는 <xref:System.Windows.DataTemplate> `PlainView` 뷰 모드에서 데이터를 표시하는 데 사용할 수 있는 를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="8114c-111">The following example defines a <xref:System.Windows.DataTemplate> that can be used to display data in the `PlainView` view mode.</span></span>  
  
 [!code-xaml[ListViewCustomView#PlainViewDataTemplate](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewCustomView/CSharp/Window1.xaml#plainviewdatatemplate)]  
  
 <span data-ttu-id="8114c-112">다음 예제에서는 이전 예제에서 `PlainView` 정의된 뷰 모드를 <xref:System.Windows.DataTemplate> 사용하는 뷰 모드를 정의하는 <xref:System.Windows.ResourceKey> 방법을 보여 주습니다.</span><span class="sxs-lookup"><span data-stu-id="8114c-112">The following example shows how to define a <xref:System.Windows.ResourceKey> for the `PlainView` view mode that uses the <xref:System.Windows.DataTemplate> that is defined in the previous example.</span></span>  
  
 [!code-xaml[ListViewCustomView#PlainViewtileView](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewCustomView/CSharp/Window1.xaml#plainviewtileview)]  
  
 <span data-ttu-id="8114c-113"><xref:System.Windows.Controls.ListView> 속성을 리소스 키로 설정하는 경우 <xref:System.Windows.Controls.ListView.View%2A> 컨트롤은 사용자 지정 보기를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8114c-113">A <xref:System.Windows.Controls.ListView> control can use a custom view if you set the <xref:System.Windows.Controls.ListView.View%2A> property to the resource key.</span></span> <span data-ttu-id="8114c-114">다음 예제에서는 `PlainView` <xref:System.Windows.Controls.ListView>에 대한 뷰 모드로 지정하는 방법을 보여 주며 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8114c-114">The following example shows how to specify `PlainView` as the view mode for a <xref:System.Windows.Controls.ListView>.</span></span>  
  
 [!code-csharp[ListViewCustomView#ListViewtileViewmode](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewCustomView/CSharp/Window1.xaml.cs#listviewtileviewmode)]
 [!code-vb[ListViewCustomView#ListViewtileViewmode](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ListViewCustomView/visualbasic/window1.xaml.vb#listviewtileviewmode)]  
  
 <span data-ttu-id="8114c-115">전체 샘플은 [여러 뷰가 있는 ListView(C#)](https://github.com/dotnet/docs/tree/master/samples/snippets/csharp/VS_Snippets_Wpf/ListViewCustomView/CSharp) 또는 [여러 뷰가 있는 ListView(시각적 기본)를](https://github.com/dotnet/docs/tree/master/samples/snippets/visualbasic/VS_Snippets_Wpf/ListViewCustomView/visualbasic)참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="8114c-115">For the complete sample, see [ListView with Multiple Views (C#)](https://github.com/dotnet/docs/tree/master/samples/snippets/csharp/VS_Snippets_Wpf/ListViewCustomView/CSharp) or [ListView with Multiple Views (Visual Basic)](https://github.com/dotnet/docs/tree/master/samples/snippets/visualbasic/VS_Snippets_Wpf/ListViewCustomView/visualbasic).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8114c-116">참고 항목</span><span class="sxs-lookup"><span data-stu-id="8114c-116">See also</span></span>

- <xref:System.Windows.Controls.ListView>
- <xref:System.Windows.Controls.GridView>
- [<span data-ttu-id="8114c-117">방법 도움말 항목</span><span class="sxs-lookup"><span data-stu-id="8114c-117">How-to Topics</span></span>](listview-how-to-topics.md)
- [<span data-ttu-id="8114c-118">ListView 개요</span><span class="sxs-lookup"><span data-stu-id="8114c-118">ListView Overview</span></span>](listview-overview.md)
- [<span data-ttu-id="8114c-119">GridView 개요</span><span class="sxs-lookup"><span data-stu-id="8114c-119">GridView Overview</span></span>](gridview-overview.md)
