---
title: '방법: GridView를 구현하는 ListView 행의 스타일 지정'
ms.date: 03/30/2017
helpviewer_keywords:
- GridView controls [WPF], styling rows
- styling rows in ListViews implementing GridViews [WPF]
- ListView controls [WPF], styling rows with GridViews
ms.assetid: 2e406ba2-70a0-4e62-841f-0934859de76e
ms.openlocfilehash: 0c8806c399959fdc1466e0839ba469881718092b
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/05/2019
ms.locfileid: "57361631"
---
# <a name="how-to-style-a-row-in-a-listview-that-implements-a-gridview"></a><span data-ttu-id="d4d45-102">방법: GridView를 구현하는 ListView 행의 스타일 지정</span><span class="sxs-lookup"><span data-stu-id="d4d45-102">How to: Style a Row in a ListView That Implements a GridView</span></span>
<span data-ttu-id="d4d45-103">행 스타일을 지정 하는 방법을 보여주는이 예제는 <xref:System.Windows.Controls.ListView> 구현 하는 컨트롤을 <xref:System.Windows.Controls.GridView> <xref:System.Windows.Controls.ListView.View%2A> 모드입니다.</span><span class="sxs-lookup"><span data-stu-id="d4d45-103">This example shows how to style a row in a <xref:System.Windows.Controls.ListView> control that implements a <xref:System.Windows.Controls.GridView><xref:System.Windows.Controls.ListView.View%2A> mode.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d4d45-104">예제</span><span class="sxs-lookup"><span data-stu-id="d4d45-104">Example</span></span>  
 <span data-ttu-id="d4d45-105">행 스타일 지정할 수 있습니다는 <xref:System.Windows.Controls.ListView> 설정 하 여 컨트롤을 <xref:System.Windows.Controls.ItemsControl.ItemContainerStyle%2A> 에 <xref:System.Windows.Controls.ListView> 컨트롤.</span><span class="sxs-lookup"><span data-stu-id="d4d45-105">You can style a row in a <xref:System.Windows.Controls.ListView> control by setting an <xref:System.Windows.Controls.ItemsControl.ItemContainerStyle%2A> on the <xref:System.Windows.Controls.ListView> control.</span></span> <span data-ttu-id="d4d45-106">로 표현 되는 해당 항목에 대 한 스타일 설정 <xref:System.Windows.Controls.ListViewItem> 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="d4d45-106">Set the style for its items that are represented as <xref:System.Windows.Controls.ListViewItem> objects.</span></span> <span data-ttu-id="d4d45-107">합니다 <xref:System.Windows.Controls.ItemsControl.ItemContainerStyle%2A> 참조는 <xref:System.Windows.Controls.ControlTemplate> 행 내용을 표시 하는 데 사용 되는 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="d4d45-107">The <xref:System.Windows.Controls.ItemsControl.ItemContainerStyle%2A> references the <xref:System.Windows.Controls.ControlTemplate> objects that are used to display the row content.</span></span>  
  
 <span data-ttu-id="d4d45-108">다음 예제가 포함되어 있는 원래의 전체 샘플에서는 [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] 데이터베이스에 저장된 곡 모음집 정보를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="d4d45-108">The complete sample, which the following examples are extracted from, displays a collection of song information that is stored in an [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] database.</span></span> <span data-ttu-id="d4d45-109">데이터베이스의 각 곡에는 순위 필드가 있으며 이 필드의 값은 곡 정보 행의 표시 방법을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="d4d45-109">Each song in the database has a rating field and the value of this field specifies how to display a row of song information.</span></span>  
  
 <span data-ttu-id="d4d45-110">다음 예제에서는 정의 하는 방법을 보여 줍니다 <xref:System.Windows.Controls.ItemsControl.ItemContainerStyle%2A> 에 대 한는 <xref:System.Windows.Controls.ListViewItem> 곡 모음집의 곡을 나타내는 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="d4d45-110">The following example shows how to define <xref:System.Windows.Controls.ItemsControl.ItemContainerStyle%2A> for the <xref:System.Windows.Controls.ListViewItem> objects that represent the songs in the song collection.</span></span> <span data-ttu-id="d4d45-111">합니다 <xref:System.Windows.Controls.ItemsControl.ItemContainerStyle%2A> 참조가 <xref:System.Windows.Controls.ControlTemplate> 곡 정보 행을 표시 하는 방법을 지정 하는 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="d4d45-111">The <xref:System.Windows.Controls.ItemsControl.ItemContainerStyle%2A> references <xref:System.Windows.Controls.ControlTemplate> objects that specify how to display a row of song information.</span></span>  
  
 [!code-xaml[ListViewItemStyleSnippet#ItemContainerStyle](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewItemStyleSnippet/CS/Window1.xaml#itemcontainerstyle)]  
  
 <span data-ttu-id="d4d45-112">에서는 다음 예제는 <xref:System.Windows.Controls.ControlTemplate> 텍스트 문자열을 추가 하는 `"Strongly Recommended"` 행입니다.</span><span class="sxs-lookup"><span data-stu-id="d4d45-112">The following example shows a <xref:System.Windows.Controls.ControlTemplate> that adds the text string `"Strongly Recommended"` to the row.</span></span> <span data-ttu-id="d4d45-113">이 서식 파일에서 참조 되는 <xref:System.Windows.Controls.ItemsControl.ItemContainerStyle%2A> 곡의 5 (5)의 값이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d4d45-113">This template is referenced in the <xref:System.Windows.Controls.ItemsControl.ItemContainerStyle%2A> and displays when the song's rating has a value of 5 (five).</span></span> <span data-ttu-id="d4d45-114"><xref:System.Windows.Controls.ControlTemplate> 포함를 <xref:System.Windows.Controls.GridViewRowPresenter> 정의 된 대로 열에서 행의 내용을 배치 하는 개체는 <xref:System.Windows.Controls.GridView> 보기 모드입니다.</span><span class="sxs-lookup"><span data-stu-id="d4d45-114">The <xref:System.Windows.Controls.ControlTemplate> includes a <xref:System.Windows.Controls.GridViewRowPresenter> object that lays out the contents of the row in columns as defined by the <xref:System.Windows.Controls.GridView> view mode.</span></span>  
  
 [!code-xaml[ListViewItemStyleSnippet#ControlTemplate](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewItemStyleSnippet/CS/Window1.xaml#controltemplate)]  
  
 <span data-ttu-id="d4d45-115">다음 예제에서는 정의 <xref:System.Windows.Controls.GridView>합니다.</span><span class="sxs-lookup"><span data-stu-id="d4d45-115">The following example defines <xref:System.Windows.Controls.GridView>.</span></span>  
  
 [!code-xaml[ListViewItemStyleSnippet#GridView](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewItemStyleSnippet/CS/Window1.xaml#gridview)]  
  
## <a name="see-also"></a><span data-ttu-id="d4d45-116">참고자료</span><span class="sxs-lookup"><span data-stu-id="d4d45-116">See also</span></span>
- <xref:System.Windows.Controls.ListView>
- <xref:System.Windows.Controls.GridView>
- [<span data-ttu-id="d4d45-117">방법 항목</span><span class="sxs-lookup"><span data-stu-id="d4d45-117">How-to Topics</span></span>](listview-how-to-topics.md)
- [<span data-ttu-id="d4d45-118">ListView 개요</span><span class="sxs-lookup"><span data-stu-id="d4d45-118">ListView Overview</span></span>](listview-overview.md)
- [<span data-ttu-id="d4d45-119">스타일 지정 및 템플릿</span><span class="sxs-lookup"><span data-stu-id="d4d45-119">Styling and Templating</span></span>](styling-and-templating.md)
