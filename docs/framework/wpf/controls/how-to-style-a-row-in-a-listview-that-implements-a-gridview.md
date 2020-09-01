---
title: '방법: GridView를 사용 하는 ListView의 행 스타일'
ms.date: 03/30/2017
helpviewer_keywords:
- GridView controls [WPF], styling rows
- styling rows in ListViews implementing GridViews [WPF]
- ListView controls [WPF], styling rows with GridViews
ms.assetid: 2e406ba2-70a0-4e62-841f-0934859de76e
ms.openlocfilehash: 4b8b8e2f1b2d7207a37205d981bf2dab3f65122e
ms.sourcegitcommit: e0803b8975d3eb12e735a5d07637020dd6dac5ef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/01/2020
ms.locfileid: "89271947"
---
# <a name="how-to-style-a-row-in-a-listview-that-implements-a-gridview"></a><span data-ttu-id="ee2c9-102">방법: GridView를 구현하는 ListView 행의 스타일 지정</span><span class="sxs-lookup"><span data-stu-id="ee2c9-102">How to: Style a Row in a ListView That Implements a GridView</span></span>
<span data-ttu-id="ee2c9-103">이 예제에서는 <xref:System.Windows.Controls.ListView> 모드를 사용 하는 컨트롤에서 행의 스타일을 만드는 방법을 보여 줍니다 <xref:System.Windows.Controls.GridView> <xref:System.Windows.Controls.ListView.View%2A> .</span><span class="sxs-lookup"><span data-stu-id="ee2c9-103">This example shows how to style a row in a <xref:System.Windows.Controls.ListView> control that uses a <xref:System.Windows.Controls.GridView> <xref:System.Windows.Controls.ListView.View%2A> mode.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ee2c9-104">예</span><span class="sxs-lookup"><span data-stu-id="ee2c9-104">Example</span></span>  
 <span data-ttu-id="ee2c9-105">컨트롤 <xref:System.Windows.Controls.ListView> 에서을 설정 하 여 컨트롤의 행에 스타일을 지정할 수 있습니다 <xref:System.Windows.Controls.ItemsControl.ItemContainerStyle%2A> <xref:System.Windows.Controls.ListView> .</span><span class="sxs-lookup"><span data-stu-id="ee2c9-105">You can style a row in a <xref:System.Windows.Controls.ListView> control by setting an <xref:System.Windows.Controls.ItemsControl.ItemContainerStyle%2A> on the <xref:System.Windows.Controls.ListView> control.</span></span> <span data-ttu-id="ee2c9-106">개체로 표시 되는 항목에 대 한 스타일을 설정 합니다 <xref:System.Windows.Controls.ListViewItem> .</span><span class="sxs-lookup"><span data-stu-id="ee2c9-106">Set the style for its items that are represented as <xref:System.Windows.Controls.ListViewItem> objects.</span></span> <span data-ttu-id="ee2c9-107">는 <xref:System.Windows.Controls.ItemsControl.ItemContainerStyle%2A> <xref:System.Windows.Controls.ControlTemplate> 행 내용을 표시 하는 데 사용 되는 개체를 참조 합니다.</span><span class="sxs-lookup"><span data-stu-id="ee2c9-107">The <xref:System.Windows.Controls.ItemsControl.ItemContainerStyle%2A> references the <xref:System.Windows.Controls.ControlTemplate> objects that are used to display the row content.</span></span>  
  
 <span data-ttu-id="ee2c9-108">다음 예제가에서 추출 되는 전체 예제는 XML 데이터베이스에 저장 되는 노래 정보 컬렉션을 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="ee2c9-108">The complete sample, which the following examples are extracted from, displays a collection of song information that is stored in an XML database.</span></span> <span data-ttu-id="ee2c9-109">데이터베이스의 각 곡에는 순위 필드가 있으며 이 필드의 값은 곡 정보 행의 표시 방법을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="ee2c9-109">Each song in the database has a rating field and the value of this field specifies how to display a row of song information.</span></span>  
  
 <span data-ttu-id="ee2c9-110">다음 예제에서는 <xref:System.Windows.Controls.ItemsControl.ItemContainerStyle%2A> <xref:System.Windows.Controls.ListViewItem> song 컬렉션의 곡을 나타내는 개체에 대해를 정의 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="ee2c9-110">The following example shows how to define <xref:System.Windows.Controls.ItemsControl.ItemContainerStyle%2A> for the <xref:System.Windows.Controls.ListViewItem> objects that represent the songs in the song collection.</span></span> <span data-ttu-id="ee2c9-111"><xref:System.Windows.Controls.ItemsControl.ItemContainerStyle%2A> <xref:System.Windows.Controls.ControlTemplate> 노래 정보 행을 표시 하는 방법을 지정 하는 참조 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="ee2c9-111">The <xref:System.Windows.Controls.ItemsControl.ItemContainerStyle%2A> references <xref:System.Windows.Controls.ControlTemplate> objects that specify how to display a row of song information.</span></span>  
  
 [!code-xaml[ListViewItemStyleSnippet#ItemContainerStyle](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewItemStyleSnippet/CS/Window1.xaml#itemcontainerstyle)]  
  
 <span data-ttu-id="ee2c9-112">다음 예제에서는 <xref:System.Windows.Controls.ControlTemplate> 텍스트 문자열을 행에 추가 하는을 보여 줍니다 `"Strongly Recommended"` .</span><span class="sxs-lookup"><span data-stu-id="ee2c9-112">The following example shows a <xref:System.Windows.Controls.ControlTemplate> that adds the text string `"Strongly Recommended"` to the row.</span></span> <span data-ttu-id="ee2c9-113">이 템플릿은에서 참조 되 <xref:System.Windows.Controls.ItemsControl.ItemContainerStyle%2A> 고 곡의 등급 값이 5 (5) 인 경우를 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="ee2c9-113">This template is referenced in the <xref:System.Windows.Controls.ItemsControl.ItemContainerStyle%2A> and displays when the song's rating has a value of 5 (five).</span></span> <span data-ttu-id="ee2c9-114">에는 <xref:System.Windows.Controls.ControlTemplate> <xref:System.Windows.Controls.GridViewRowPresenter> 뷰 모드에 정의 된 대로 열에 행 내용을 배치 하는 개체가 포함 되어 있습니다 <xref:System.Windows.Controls.GridView> .</span><span class="sxs-lookup"><span data-stu-id="ee2c9-114">The <xref:System.Windows.Controls.ControlTemplate> includes a <xref:System.Windows.Controls.GridViewRowPresenter> object that lays out the contents of the row in columns as defined by the <xref:System.Windows.Controls.GridView> view mode.</span></span>  
  
 [!code-xaml[ListViewItemStyleSnippet#ControlTemplate](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewItemStyleSnippet/CS/Window1.xaml#controltemplate)]  
  
 <span data-ttu-id="ee2c9-115">다음 예에서는를 정의 <xref:System.Windows.Controls.GridView> 합니다.</span><span class="sxs-lookup"><span data-stu-id="ee2c9-115">The following example defines <xref:System.Windows.Controls.GridView>.</span></span>  
  
 [!code-xaml[ListViewItemStyleSnippet#GridView](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewItemStyleSnippet/CS/Window1.xaml#gridview)]  
  
## <a name="see-also"></a><span data-ttu-id="ee2c9-116">참고 항목</span><span class="sxs-lookup"><span data-stu-id="ee2c9-116">See also</span></span>

- <xref:System.Windows.Controls.ListView>
- <xref:System.Windows.Controls.GridView>
- [<span data-ttu-id="ee2c9-117">방법 도움말 항목</span><span class="sxs-lookup"><span data-stu-id="ee2c9-117">How-to Topics</span></span>](listview-how-to-topics.md)
- [<span data-ttu-id="ee2c9-118">ListView 개요</span><span class="sxs-lookup"><span data-stu-id="ee2c9-118">ListView Overview</span></span>](listview-overview.md)
- [<span data-ttu-id="ee2c9-119">스타일 지정 및 템플릿</span><span class="sxs-lookup"><span data-stu-id="ee2c9-119">Styling and Templating</span></span>](../../../desktop-wpf/fundamentals/styles-templates-overview.md)
