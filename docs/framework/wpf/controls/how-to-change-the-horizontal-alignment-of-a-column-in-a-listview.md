---
title: '방법: ListView에 있는 열의 가로 맞춤 변경'
ms.date: 03/30/2017
helpviewer_keywords:
- ListView controls [WPF], horizontal alignment [WPF]
ms.assetid: b9573e44-9dad-4d14-939c-7859ca372758
ms.openlocfilehash: 5447f1a73b008b2ed4f345eba00f4d631e11e257
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/03/2019
ms.locfileid: "73458598"
---
# <a name="how-to-change-the-horizontal-alignment-of-a-column-in-a-listview"></a><span data-ttu-id="5f8b4-102">방법: ListView에 있는 열의 가로 맞춤 변경</span><span class="sxs-lookup"><span data-stu-id="5f8b4-102">How to: Change the Horizontal Alignment of a Column in a ListView</span></span>
<span data-ttu-id="5f8b4-103">기본적으로 <xref:System.Windows.Controls.ListViewItem>의 각 열에 대 한 내용은 왼쪽에 맞춰집니다.</span><span class="sxs-lookup"><span data-stu-id="5f8b4-103">By default, the content of each column in a <xref:System.Windows.Controls.ListViewItem> is left-aligned.</span></span> <span data-ttu-id="5f8b4-104"><xref:System.Windows.DataTemplate>를 제공 하 고 <xref:System.Windows.DataTemplate>내의 요소에서 <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> 속성을 설정 하 여 각 열의 맞춤을 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5f8b4-104">You can change the alignment of each column by providing a <xref:System.Windows.DataTemplate> and setting the <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> property on the element within the <xref:System.Windows.DataTemplate>.</span></span> <span data-ttu-id="5f8b4-105">이 항목에서는 <xref:System.Windows.Controls.ListView>에서 기본적으로 콘텐츠를 정렬 하는 방법과 <xref:System.Windows.Controls.ListView>한 열의 맞춤을 변경 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="5f8b4-105">This topic shows how a <xref:System.Windows.Controls.ListView> aligns its content by default and how to change the alignment of one column in a <xref:System.Windows.Controls.ListView>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5f8b4-106">예제</span><span class="sxs-lookup"><span data-stu-id="5f8b4-106">Example</span></span>  
 <span data-ttu-id="5f8b4-107">다음 예에서는 `Title` 및 `ISBN` 열의 데이터를 왼쪽에 맞춥니다.</span><span class="sxs-lookup"><span data-stu-id="5f8b4-107">In the following example, the data in the `Title` and `ISBN` columns is left-aligned.</span></span>  
  
 [!code-xaml[ListViewHowTos#1](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewHowTos/CSharp/Window1.xaml#1)]  
[!code-xaml[ListViewHowTos#2](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewHowTos/CSharp/Window1.xaml#2)]  
  
 <span data-ttu-id="5f8b4-108">`ISBN` 열의 맞춤을 변경 하려면 각 <xref:System.Windows.Controls.ListViewItem>의 <xref:System.Windows.Controls.Control.HorizontalContentAlignment%2A> 속성이 <xref:System.Windows.HorizontalAlignment.Stretch>되도록 지정 하 여 각 <xref:System.Windows.Controls.ListViewItem>의 요소가 각 열의 전체 너비를 따라 확장 되거나 배치 될 수 있도록 지정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5f8b4-108">To change the alignment of the `ISBN` column, you need to specify that the <xref:System.Windows.Controls.Control.HorizontalContentAlignment%2A> property of each <xref:System.Windows.Controls.ListViewItem> is <xref:System.Windows.HorizontalAlignment.Stretch>, so that the elements in each <xref:System.Windows.Controls.ListViewItem> can span or be positioned along the entire width of each column.</span></span> <span data-ttu-id="5f8b4-109"><xref:System.Windows.Controls.ListView> 데이터 원본에 바인딩되므로 <xref:System.Windows.Controls.Control.HorizontalContentAlignment%2A>를 설정 하는 스타일을 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5f8b4-109">Because the <xref:System.Windows.Controls.ListView> is bound to a data source, you need to create a style that sets the <xref:System.Windows.Controls.Control.HorizontalContentAlignment%2A>.</span></span> <span data-ttu-id="5f8b4-110">다음으로 <xref:System.Windows.Controls.GridViewColumn.DisplayMemberBinding%2A> 속성을 사용 하는 대신 <xref:System.Windows.DataTemplate>를 사용 하 여 콘텐츠를 표시 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5f8b4-110">Next, you need to use a <xref:System.Windows.DataTemplate> to display the content instead of using the <xref:System.Windows.Controls.GridViewColumn.DisplayMemberBinding%2A> property.</span></span> <span data-ttu-id="5f8b4-111">각 템플릿의 `ISBN`를 표시 하기 위해 <xref:System.Windows.DataTemplate>는 <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> 속성이 <xref:System.Windows.HorizontalAlignment.Right>로 설정 된 <xref:System.Windows.Controls.TextBlock>만 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5f8b4-111">To display the `ISBN` of each template, the <xref:System.Windows.DataTemplate> can just contain a <xref:System.Windows.Controls.TextBlock> that has its <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> property set to <xref:System.Windows.HorizontalAlignment.Right>.</span></span>  
  
 <span data-ttu-id="5f8b4-112">다음 예제에서는 `ISBN` 열을 오른쪽에 맞추도록 설정 하 고 <xref:System.Windows.DataTemplate>를 참조 하도록 <xref:System.Windows.Controls.GridViewColumn>를 변경 하는 데 필요한 스타일과 <xref:System.Windows.DataTemplate>를 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="5f8b4-112">The following example defines the style and <xref:System.Windows.DataTemplate> necessary to make the `ISBN` column right-aligned, and changes the <xref:System.Windows.Controls.GridViewColumn> to reference the <xref:System.Windows.DataTemplate>.</span></span>  
  
 [!code-xaml[ListViewHowTos#3](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewHowTos/CSharp/Window1.xaml#3)]  
[!code-xaml[ListViewHowTos#4](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewHowTos/CSharp/Window1.xaml#4)]  
  
## <a name="see-also"></a><span data-ttu-id="5f8b4-113">참조</span><span class="sxs-lookup"><span data-stu-id="5f8b4-113">See also</span></span>

- [<span data-ttu-id="5f8b4-114">데이터 바인딩 개요</span><span class="sxs-lookup"><span data-stu-id="5f8b4-114">Data Binding Overview</span></span>](../../../desktop-wpf/data/data-binding-overview.md)
- [<span data-ttu-id="5f8b4-115">데이터 템플릿 개요</span><span class="sxs-lookup"><span data-stu-id="5f8b4-115">Data Templating Overview</span></span>](../data/data-templating-overview.md)
- [<span data-ttu-id="5f8b4-116">XMLDataProvider 및 XPath 쿼리를 사용하여 XML 데이터에 바인딩</span><span class="sxs-lookup"><span data-stu-id="5f8b4-116">Bind to XML Data Using an XMLDataProvider and XPath Queries</span></span>](../data/how-to-bind-to-xml-data-using-an-xmldataprovider-and-xpath-queries.md)
- [<span data-ttu-id="5f8b4-117">ListView 개요</span><span class="sxs-lookup"><span data-stu-id="5f8b4-117">ListView Overview</span></span>](listview-overview.md)
