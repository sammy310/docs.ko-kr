---
title: '방법: ListView에 대한 사용자 지정 보기 모드 만들기'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ListView controls [WPF], creating custom View mode
ms.assetid: 71077349-eeb9-4344-ab29-b5df96df3314
ms.openlocfilehash: de11250a2e7529fba3b262e42b6714262738fa90
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59092892"
---
# <a name="how-to-create-a-custom-view-mode-for-a-listview"></a><span data-ttu-id="39eda-102">방법: ListView에 대한 사용자 지정 보기 모드 만들기</span><span class="sxs-lookup"><span data-stu-id="39eda-102">How to: Create a Custom View Mode for a ListView</span></span>
<span data-ttu-id="39eda-103">이 예제에는 사용자 지정을 만드는 방법을 보여 줍니다 <xref:System.Windows.Controls.ListView.View%2A> 에 대 한 모드는 <xref:System.Windows.Controls.ListView> 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="39eda-103">This example shows how to create a custom <xref:System.Windows.Controls.ListView.View%2A> mode for a <xref:System.Windows.Controls.ListView> control.</span></span>  
  
## <a name="example"></a><span data-ttu-id="39eda-104">예제</span><span class="sxs-lookup"><span data-stu-id="39eda-104">Example</span></span>  
 <span data-ttu-id="39eda-105">사용 해야 합니다는 <xref:System.Windows.Controls.ViewBase> 에 대 한 사용자 지정 보기를 만들 때 클래스는 <xref:System.Windows.Controls.ListView> 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="39eda-105">You must use the <xref:System.Windows.Controls.ViewBase> class when you create a custom view for the <xref:System.Windows.Controls.ListView> control.</span></span> <span data-ttu-id="39eda-106">다음 예제에서는 호출 되는 뷰 모드를 `PlainView`에서 파생 되는 <xref:System.Windows.Controls.ViewBase> 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="39eda-106">The following example shows a view mode that is called `PlainView`, which is derived from the <xref:System.Windows.Controls.ViewBase> class.</span></span>  
  
 [!code-csharp[ListViewCustomView#PlainView](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewCustomView/CSharp/PlainView.cs#plainview)]
 [!code-vb[ListViewCustomView#PlainView](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ListViewCustomView/visualbasic/plainview.vb#plainview)]  
  
 <span data-ttu-id="39eda-107">사용자 지정 보기에 스타일을 적용 하려면 사용 된 <xref:System.Windows.Style> 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="39eda-107">To apply a style to the custom view, use the <xref:System.Windows.Style> class.</span></span> <span data-ttu-id="39eda-108">다음 예제에서는 정의 <xref:System.Windows.Style> 에 대 한는 `PlainView` 보기 모드입니다.</span><span class="sxs-lookup"><span data-stu-id="39eda-108">The following example defines a <xref:System.Windows.Style> for the `PlainView` view mode.</span></span> <span data-ttu-id="39eda-109">이전 예제에서는이 스타일의 값으로 설정 합니다 <xref:System.Windows.Controls.ViewBase.DefaultStyleKey%2A> 속성에 대해 정의 된 `PlainView`합니다.</span><span class="sxs-lookup"><span data-stu-id="39eda-109">In the previous example, this style is set as the value of the <xref:System.Windows.Controls.ViewBase.DefaultStyleKey%2A> property that is defined for `PlainView`.</span></span>  
  
 [!code-xaml[ListViewCustomView#PlainViewStyle](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewCustomView/CSharp/Themes/Generic.xaml#plainviewstyle)]  
  
 <span data-ttu-id="39eda-110">사용자 지정 보기 모드에서 데이터의 레이아웃을 정의 하려면 정의 <xref:System.Windows.DataTemplate> 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="39eda-110">To define the layout of data in a custom view mode, define a <xref:System.Windows.DataTemplate> object.</span></span> <span data-ttu-id="39eda-111">다음 예제에서는 정의 <xref:System.Windows.DataTemplate> 데이터를 표시 하려면 사용할 수 있는 여 `PlainView` 보기 모드입니다.</span><span class="sxs-lookup"><span data-stu-id="39eda-111">The following example defines a <xref:System.Windows.DataTemplate> that can be used to display data in the `PlainView` view mode.</span></span>  
  
 [!code-xaml[ListViewCustomView#PlainViewDataTemplate](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewCustomView/CSharp/Window1.xaml#plainviewdatatemplate)]  
  
 <span data-ttu-id="39eda-112">다음 예제에서는 정의 하는 방법을 보여 줍니다는 <xref:System.Windows.ResourceKey> 에 대 한는 `PlainView` 보기 모드를 사용 하는 <xref:System.Windows.DataTemplate> 앞의 예제에 정의 된 합니다.</span><span class="sxs-lookup"><span data-stu-id="39eda-112">The following example shows how to define a <xref:System.Windows.ResourceKey> for the `PlainView` view mode that uses the <xref:System.Windows.DataTemplate> that is defined in the previous example.</span></span>  
  
 [!code-xaml[ListViewCustomView#PlainViewtileView](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewCustomView/CSharp/Window1.xaml#plainviewtileview)]  
  
 <span data-ttu-id="39eda-113"><xref:System.Windows.Controls.ListView> 설정 하는 경우 컨트롤 사용자 지정 보기를 사용할 수는 <xref:System.Windows.Controls.ListView.View%2A> 속성이 리소스 키입니다.</span><span class="sxs-lookup"><span data-stu-id="39eda-113">A <xref:System.Windows.Controls.ListView> control can use a custom view if you set the <xref:System.Windows.Controls.ListView.View%2A> property to the resource key.</span></span> <span data-ttu-id="39eda-114">다음 예제에서는 지정 하는 방법을 보여 줍니다 `PlainView` 에 대 한 보기 모드를 <xref:System.Windows.Controls.ListView>입니다.</span><span class="sxs-lookup"><span data-stu-id="39eda-114">The following example shows how to specify `PlainView` as the view mode for a <xref:System.Windows.Controls.ListView>.</span></span>  
  
 [!code-csharp[ListViewCustomView#ListViewtileViewmode](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewCustomView/CSharp/Window1.xaml.cs#listviewtileviewmode)]
 [!code-vb[ListViewCustomView#ListViewtileViewmode](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ListViewCustomView/visualbasic/window1.xaml.vb#listviewtileviewmode)]  
  
 <span data-ttu-id="39eda-115">전체 샘플을 참조 하세요 [여러 뷰가 포함 된 ListView (C#)](https://github.com/dotnet/samples/tree/master/snippets/csharp/VS_Snippets_Wpf/ListViewCustomView/CSharp) 하거나 [여러 Views(Visual Basic)를 사용 하 여 ListView](https://github.com/dotnet/samples/tree/master/snippets/visualbasic/VS_Snippets_Wpf/ListViewCustomView/visualbasic)합니다.</span><span class="sxs-lookup"><span data-stu-id="39eda-115">For the complete sample, see [ListView with Multiple Views(C#)](https://github.com/dotnet/samples/tree/master/snippets/csharp/VS_Snippets_Wpf/ListViewCustomView/CSharp) or [ListView with Multiple Views(Visual Basic)](https://github.com/dotnet/samples/tree/master/snippets/visualbasic/VS_Snippets_Wpf/ListViewCustomView/visualbasic).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="39eda-116">참고자료</span><span class="sxs-lookup"><span data-stu-id="39eda-116">See also</span></span>

- <xref:System.Windows.Controls.ListView>
- <xref:System.Windows.Controls.GridView>
- [<span data-ttu-id="39eda-117">방법 항목</span><span class="sxs-lookup"><span data-stu-id="39eda-117">How-to Topics</span></span>](listview-how-to-topics.md)
- [<span data-ttu-id="39eda-118">ListView 개요</span><span class="sxs-lookup"><span data-stu-id="39eda-118">ListView Overview</span></span>](listview-overview.md)
- [<span data-ttu-id="39eda-119">GridView 개요</span><span class="sxs-lookup"><span data-stu-id="39eda-119">GridView Overview</span></span>](gridview-overview.md)
