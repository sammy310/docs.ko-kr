---
title: '방법: ListView에서 열의 가로 맞춤 변경'
ms.date: 03/30/2017
helpviewer_keywords:
- ListView controls [WPF], horizontal alignment [WPF]
ms.assetid: b9573e44-9dad-4d14-939c-7859ca372758
ms.openlocfilehash: 528a711c1cf7992bb32c0aa4d6e81d71744c9f80
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61911068"
---
# <a name="how-to-change-the-horizontal-alignment-of-a-column-in-a-listview"></a><span data-ttu-id="1994c-102">방법: ListView에서 열의 가로 맞춤 변경</span><span class="sxs-lookup"><span data-stu-id="1994c-102">How to: Change the Horizontal Alignment of a Column in a ListView</span></span>
<span data-ttu-id="1994c-103">기본적으로 각 열에 콘텐츠를 <xref:System.Windows.Controls.ListViewItem> 왼쪽에 맞춰집니다.</span><span class="sxs-lookup"><span data-stu-id="1994c-103">By default, the content of each column in a <xref:System.Windows.Controls.ListViewItem> is left-aligned.</span></span> <span data-ttu-id="1994c-104">제공 하 여 각 열의 맞춤을 변경할 수 있습니다는 <xref:System.Windows.DataTemplate> 설정 합니다 <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> 내 요소의 속성에는 <xref:System.Windows.DataTemplate>.</span><span class="sxs-lookup"><span data-stu-id="1994c-104">You can change the alignment of each column by providing a <xref:System.Windows.DataTemplate> and setting the <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> property on the element within the <xref:System.Windows.DataTemplate>.</span></span> <span data-ttu-id="1994c-105">이 항목에서는 어떻게를 <xref:System.Windows.Controls.ListView> 의 한 열에 맞춤을 변경 하는 방법 및 기본적으로 해당 내용을 맞춥니다.는 <xref:System.Windows.Controls.ListView>합니다.</span><span class="sxs-lookup"><span data-stu-id="1994c-105">This topic shows how a <xref:System.Windows.Controls.ListView> aligns its content by default and how to change the alignment of one column in a <xref:System.Windows.Controls.ListView>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="1994c-106">예제</span><span class="sxs-lookup"><span data-stu-id="1994c-106">Example</span></span>  
 <span data-ttu-id="1994c-107">다음 예제에서는의 데이터에에서는 `Title` 및 `ISBN` 열 왼쪽에 맞춰집니다.</span><span class="sxs-lookup"><span data-stu-id="1994c-107">In the following example, the data in the `Title` and `ISBN` columns is left-aligned.</span></span>  
  
 [!code-xaml[ListViewHowTos#1](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewHowTos/CSharp/Window1.xaml#1)]  
[!code-xaml[ListViewHowTos#2](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewHowTos/CSharp/Window1.xaml#2)]  
  
 <span data-ttu-id="1994c-108">맞춤을 변경 하는 `ISBN` 열을 지정 해야 하는 합니다 <xref:System.Windows.Controls.Control.HorizontalContentAlignment%2A> 각 속성 <xref:System.Windows.Controls.ListViewItem> 는 <xref:System.Windows.HorizontalAlignment.Stretch>되도록 각 요소 <xref:System.Windows.Controls.ListViewItem> 에 걸쳐 있을 수 또는 각 열의 너비를 전체 놓일.</span><span class="sxs-lookup"><span data-stu-id="1994c-108">To change the alignment of the `ISBN` column, you need to specify that the <xref:System.Windows.Controls.Control.HorizontalContentAlignment%2A> property of each <xref:System.Windows.Controls.ListViewItem> is <xref:System.Windows.HorizontalAlignment.Stretch>, so that the elements in each <xref:System.Windows.Controls.ListViewItem> can span or be positioned along the entire width of each column.</span></span> <span data-ttu-id="1994c-109">때문에 <xref:System.Windows.Controls.ListView> 바인딩된 데이터 원본에 설정 하는 스타일을 생성 해야 합니다 <xref:System.Windows.Controls.Control.HorizontalContentAlignment%2A>합니다.</span><span class="sxs-lookup"><span data-stu-id="1994c-109">Because the <xref:System.Windows.Controls.ListView> is bound to a data source, you need to create a style that sets the <xref:System.Windows.Controls.Control.HorizontalContentAlignment%2A>.</span></span> <span data-ttu-id="1994c-110">사용 해야 하는 다음에 <xref:System.Windows.DataTemplate> 사용 하는 대신 내용을 표시 하는 <xref:System.Windows.Controls.GridViewColumn.DisplayMemberBinding%2A> 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="1994c-110">Next, you need to use a <xref:System.Windows.DataTemplate> to display the content instead of using the <xref:System.Windows.Controls.GridViewColumn.DisplayMemberBinding%2A> property.</span></span> <span data-ttu-id="1994c-111">표시할 합니다 `ISBN` 각 템플릿의 합니다 <xref:System.Windows.DataTemplate> 만 포함할 수 있습니다를 <xref:System.Windows.Controls.TextBlock> 있는 해당 <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> 속성이로 설정 <xref:System.Windows.HorizontalAlignment.Right>.</span><span class="sxs-lookup"><span data-stu-id="1994c-111">To display the `ISBN` of each template, the <xref:System.Windows.DataTemplate> can just contain a <xref:System.Windows.Controls.TextBlock> that has its <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> property set to <xref:System.Windows.HorizontalAlignment.Right>.</span></span>  
  
 <span data-ttu-id="1994c-112">스타일을 정의 하는 다음 예제에서는 및 <xref:System.Windows.DataTemplate> 하는 데 필요한를 `ISBN` 오른쪽 맞춤, 열 및 변경 합니다 <xref:System.Windows.Controls.GridViewColumn> 참조는 <xref:System.Windows.DataTemplate>.</span><span class="sxs-lookup"><span data-stu-id="1994c-112">The following example defines the style and <xref:System.Windows.DataTemplate> necessary to make the `ISBN` column right-aligned, and changes the <xref:System.Windows.Controls.GridViewColumn> to reference the <xref:System.Windows.DataTemplate>.</span></span>  
  
 [!code-xaml[ListViewHowTos#3](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewHowTos/CSharp/Window1.xaml#3)]  
[!code-xaml[ListViewHowTos#4](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewHowTos/CSharp/Window1.xaml#4)]  
  
## <a name="see-also"></a><span data-ttu-id="1994c-113">참고자료</span><span class="sxs-lookup"><span data-stu-id="1994c-113">See also</span></span>

- [<span data-ttu-id="1994c-114">데이터 바인딩 개요</span><span class="sxs-lookup"><span data-stu-id="1994c-114">Data Binding Overview</span></span>](../data/data-binding-overview.md)
- [<span data-ttu-id="1994c-115">데이터 템플릿 개요</span><span class="sxs-lookup"><span data-stu-id="1994c-115">Data Templating Overview</span></span>](../data/data-templating-overview.md)
- [<span data-ttu-id="1994c-116">XMLDataProvider 및 XPath 쿼리를 사용하여 XML 데이터에 바인딩</span><span class="sxs-lookup"><span data-stu-id="1994c-116">Bind to XML Data Using an XMLDataProvider and XPath Queries</span></span>](../data/how-to-bind-to-xml-data-using-an-xmldataprovider-and-xpath-queries.md)
- [<span data-ttu-id="1994c-117">ListView 개요</span><span class="sxs-lookup"><span data-stu-id="1994c-117">ListView Overview</span></span>](listview-overview.md)
