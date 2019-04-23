---
title: '방법: ListView에서 각 항목에 대한 MouseDoubleClick 이벤트 처리'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ListView controls [WPF], MouseDoubleClick event
ms.assetid: 81b39369-655a-4585-ac58-4640e5bb8fed
ms.openlocfilehash: 443e5c620ef5bf240d3e317f0234aac0b29b456f
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59145082"
---
# <a name="how-to-handle-the-mousedoubleclick-event-for-each-item-in-a-listview"></a><span data-ttu-id="2f936-102">방법: ListView에서 각 항목에 대한 MouseDoubleClick 이벤트 처리</span><span class="sxs-lookup"><span data-stu-id="2f936-102">How to: Handle the MouseDoubleClick Event for Each Item in a ListView</span></span>
<span data-ttu-id="2f936-103">항목에 대해 이벤트를 처리 하는 <xref:System.Windows.Controls.ListView>, 각 이벤트 처리기를 추가 해야 <xref:System.Windows.Controls.ListViewItem>합니다.</span><span class="sxs-lookup"><span data-stu-id="2f936-103">To handle an event for an item in a <xref:System.Windows.Controls.ListView>, you need to add an event handler to each <xref:System.Windows.Controls.ListViewItem>.</span></span> <span data-ttu-id="2f936-104">경우는 <xref:System.Windows.Controls.ListView> 바인딩된 데이터 원본에 명시적으로 만들지를 <xref:System.Windows.Controls.ListViewItem>, 추가 하 여 각 항목에 대 한 이벤트를 처리할 수 있지만 <xref:System.Windows.EventSetter> 의 스타일을 <xref:System.Windows.Controls.ListViewItem>.</span><span class="sxs-lookup"><span data-stu-id="2f936-104">When a <xref:System.Windows.Controls.ListView> is bound to a data source, you don't explicitly create a <xref:System.Windows.Controls.ListViewItem>, but you can handle the event for each item by adding an <xref:System.Windows.EventSetter> to a style of a <xref:System.Windows.Controls.ListViewItem>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="2f936-105">예제</span><span class="sxs-lookup"><span data-stu-id="2f936-105">Example</span></span>  
 <span data-ttu-id="2f936-106">다음 예제에서는 데이터 바인딩된 <xref:System.Windows.Controls.ListView> 만들고는 <xref:System.Windows.Style> 각 이벤트 처리기를 추가 하려면 <xref:System.Windows.Controls.ListViewItem>합니다.</span><span class="sxs-lookup"><span data-stu-id="2f936-106">The following example creates a data-bound <xref:System.Windows.Controls.ListView> and creates a <xref:System.Windows.Style> to add an event handler to each <xref:System.Windows.Controls.ListViewItem>.</span></span>  
  
 [!code-xaml[ListViewHowTos#1](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewHowTos/CSharp/Window1.xaml#1)]  
[!code-xaml[ListViewHowTos#5](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewHowTos/CSharp/Window1.xaml#5)]  
[!code-xaml[ListViewHowTos#2](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewHowTos/CSharp/Window1.xaml#2)]  
  
 <span data-ttu-id="2f936-107">다음 예제에서는 처리 된 <xref:System.Windows.Controls.Control.MouseDoubleClick> 이벤트입니다.</span><span class="sxs-lookup"><span data-stu-id="2f936-107">The following example handles the <xref:System.Windows.Controls.Control.MouseDoubleClick> event.</span></span>  
  
 [!code-csharp[ListViewHowTos#6](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewHowTos/CSharp/Window1.xaml.cs#6)]
 [!code-vb[ListViewHowTos#6](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ListViewHowTos/VisualBasic/Window1.xaml.vb#6)]  
  
> [!NOTE]
>  <span data-ttu-id="2f936-108">바인딩하는 것이 일반적 이지만 <xref:System.Windows.Controls.ListView> 데이터 원본에 각 이벤트 처리기를 추가할 스타일을 사용할 수 있습니다 <xref:System.Windows.Controls.ListViewItem> 는 비-데이터 바인딩된 <xref:System.Windows.Controls.ListView> 명시적으로 만드는 하는지 여부에 관계 없이 <xref:System.Windows.Controls.ListViewItem>합니다.</span><span class="sxs-lookup"><span data-stu-id="2f936-108">Although it is most common to bind a <xref:System.Windows.Controls.ListView> to a data source, you can use a style to add an event handler to each <xref:System.Windows.Controls.ListViewItem> in a non-data-bound <xref:System.Windows.Controls.ListView> regardless of whether you explicitly create a <xref:System.Windows.Controls.ListViewItem>.</span></span>  <span data-ttu-id="2f936-109">에 대 한 자세한 정보에 대 한 명시적 및 암시적으로 생성 <xref:System.Windows.Controls.ListViewItem> 컨트롤을 참조 하세요. <xref:System.Windows.Controls.ItemsControl>합니다.</span><span class="sxs-lookup"><span data-stu-id="2f936-109">For more information about explicitly and implicitly created <xref:System.Windows.Controls.ListViewItem> controls, see <xref:System.Windows.Controls.ItemsControl>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2f936-110">참고자료</span><span class="sxs-lookup"><span data-stu-id="2f936-110">See also</span></span>

- <xref:System.Xml.XmlElement>
- [<span data-ttu-id="2f936-111">데이터 바인딩 개요</span><span class="sxs-lookup"><span data-stu-id="2f936-111">Data Binding Overview</span></span>](../data/data-binding-overview.md)
- [<span data-ttu-id="2f936-112">스타일 지정 및 템플릿</span><span class="sxs-lookup"><span data-stu-id="2f936-112">Styling and Templating</span></span>](styling-and-templating.md)
- [<span data-ttu-id="2f936-113">XMLDataProvider 및 XPath 쿼리를 사용하여 XML 데이터에 바인딩</span><span class="sxs-lookup"><span data-stu-id="2f936-113">Bind to XML Data Using an XMLDataProvider and XPath Queries</span></span>](../data/how-to-bind-to-xml-data-using-an-xmldataprovider-and-xpath-queries.md)
- [<span data-ttu-id="2f936-114">ListView 개요</span><span class="sxs-lookup"><span data-stu-id="2f936-114">ListView Overview</span></span>](listview-overview.md)
