---
title: '방법: ListView의 각 항목에 대한 MouseDoubleClick 이벤트 처리'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ListView controls [WPF], MouseDoubleClick event
ms.assetid: 81b39369-655a-4585-ac58-4640e5bb8fed
ms.openlocfilehash: 7bbc7bad36b3b1f2c92065e5f5699e5a86ac6189
ms.sourcegitcommit: 62285ec11fa8e8424bab00511a90760c60e63c95
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/20/2020
ms.locfileid: "81646102"
---
# <a name="how-to-handle-the-mousedoubleclick-event-for-each-item-in-a-listview"></a><span data-ttu-id="302ca-102">방법: ListView의 각 항목에 대한 MouseDoubleClick 이벤트 처리</span><span class="sxs-lookup"><span data-stu-id="302ca-102">How to: Handle the MouseDoubleClick Event for Each Item in a ListView</span></span>
<span data-ttu-id="302ca-103"><xref:System.Windows.Controls.ListView>에서 항목에 대한 이벤트를 처리하려면 각 <xref:System.Windows.Controls.ListViewItem>에 이벤트 처리기를 추가해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="302ca-103">To handle an event for an item in a <xref:System.Windows.Controls.ListView>, you need to add an event handler to each <xref:System.Windows.Controls.ListViewItem>.</span></span> <span data-ttu-id="302ca-104">a가 <xref:System.Windows.Controls.ListView> 데이터 원본에 바인딩된 경우 <xref:System.Windows.Controls.ListViewItem>을 명시적으로 만들지 않지만 <xref:System.Windows.EventSetter> <xref:System.Windows.Controls.ListViewItem>의 스타일에 를 추가하여 각 항목에 대한 이벤트를 처리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="302ca-104">When a <xref:System.Windows.Controls.ListView> is bound to a data source, you don't explicitly create a <xref:System.Windows.Controls.ListViewItem>, but you can handle the event for each item by adding an <xref:System.Windows.EventSetter> to a style of a <xref:System.Windows.Controls.ListViewItem>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="302ca-105">예제</span><span class="sxs-lookup"><span data-stu-id="302ca-105">Example</span></span>  
 <span data-ttu-id="302ca-106">다음 예제는 데이터 바인딩을 <xref:System.Windows.Controls.ListView> 만들고 <xref:System.Windows.Style> 각 <xref:System.Windows.Controls.ListViewItem>에 이벤트 처리기를 추가할 a를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="302ca-106">The following example creates a data-bound <xref:System.Windows.Controls.ListView> and creates a <xref:System.Windows.Style> to add an event handler to each <xref:System.Windows.Controls.ListViewItem>.</span></span>  
  
 [!code-xaml[ListViewHowTos#1](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewHowTos/CSharp/Window1.xaml#1)]  
[!code-xaml[ListViewHowTos#5](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewHowTos/CSharp/Window1.xaml#5)]  
[!code-xaml[ListViewHowTos#2](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewHowTos/CSharp/Window1.xaml#2)]  
  
 <span data-ttu-id="302ca-107">다음 예제에서는 처리 된 <xref:System.Windows.Controls.Control.MouseDoubleClick> 이벤트입니다.</span><span class="sxs-lookup"><span data-stu-id="302ca-107">The following example handles the <xref:System.Windows.Controls.Control.MouseDoubleClick> event.</span></span>  
  
 [!code-csharp[ListViewHowTos#6](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewHowTos/CSharp/Window1.xaml.cs#6)]
 [!code-vb[ListViewHowTos#6](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ListViewHowTos/VisualBasic/Window1.xaml.vb#6)]  
  
> [!NOTE]
> <span data-ttu-id="302ca-108">데이터 <xref:System.Windows.Controls.ListView> 원본에 바인딩하는 것이 가장 일반적이지만 스타일을 사용하여 <xref:System.Windows.Controls.ListViewItem> <xref:System.Windows.Controls.ListView> <xref:System.Windows.Controls.ListViewItem>을 명시적으로 만들지 여부에 관계없이 데이터 바인딩되지 않은 각 데이터 바인딩의 각 처리기를 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="302ca-108">Although it is most common to bind a <xref:System.Windows.Controls.ListView> to a data source, you can use a style to add an event handler to each <xref:System.Windows.Controls.ListViewItem> in a non-data-bound <xref:System.Windows.Controls.ListView> regardless of whether you explicitly create a <xref:System.Windows.Controls.ListViewItem>.</span></span>  <span data-ttu-id="302ca-109">명시적 및 암시적으로 생성된 <xref:System.Windows.Controls.ListViewItem> 컨트롤에 <xref:System.Windows.Controls.ItemsControl>대한 자세한 내용은 을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="302ca-109">For more information about explicitly and implicitly created <xref:System.Windows.Controls.ListViewItem> controls, see <xref:System.Windows.Controls.ItemsControl>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="302ca-110">참고 항목</span><span class="sxs-lookup"><span data-stu-id="302ca-110">See also</span></span>

- <xref:System.Xml.XmlElement>
- [<span data-ttu-id="302ca-111">데이터 바인딩 개요</span><span class="sxs-lookup"><span data-stu-id="302ca-111">Data Binding Overview</span></span>](../../../desktop-wpf/data/data-binding-overview.md)
- [<span data-ttu-id="302ca-112">스타일 지정 및 템플릿</span><span class="sxs-lookup"><span data-stu-id="302ca-112">Styling and Templating</span></span>](../../../desktop-wpf/fundamentals/styles-templates-overview.md)
- [<span data-ttu-id="302ca-113">XMLDataProvider 및 XPath 쿼리를 사용하여 XML 데이터에 바인딩</span><span class="sxs-lookup"><span data-stu-id="302ca-113">Bind to XML Data Using an XMLDataProvider and XPath Queries</span></span>](../data/how-to-bind-to-xml-data-using-an-xmldataprovider-and-xpath-queries.md)
- [<span data-ttu-id="302ca-114">ListView 개요</span><span class="sxs-lookup"><span data-stu-id="302ca-114">ListView Overview</span></span>](listview-overview.md)
