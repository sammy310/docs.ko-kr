---
title: '방법: ListView에서 트리거를 사용하여 선택한 항목의 스타일 지정'
ms.date: 03/30/2017
helpviewer_keywords:
- ListView controls [WPF], styling
ms.assetid: 1e2bdce0-afe8-4507-9b18-f33de43de25a
ms.openlocfilehash: 8c2d4adb2471c0f1891288573ce6b6460b20151d
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/05/2019
ms.locfileid: "57367923"
---
# <a name="how-to-use-triggers-to-style-selected-items-in-a-listview"></a><span data-ttu-id="34c1c-102">방법: ListView에서 트리거를 사용하여 선택한 항목의 스타일 지정</span><span class="sxs-lookup"><span data-stu-id="34c1c-102">How to: Use Triggers to Style Selected Items in a ListView</span></span>
<span data-ttu-id="34c1c-103">정의 하는 방법을 보여 주는이 예제 <xref:System.Windows.Style.Triggers%2A> 에 대 한는 <xref:System.Windows.Controls.ListViewItem> 컨트롤 있도록 속성 값을 <xref:System.Windows.Controls.ListViewItem> 변경을 <xref:System.Windows.Style> 의 <xref:System.Windows.Controls.ListViewItem> 변경에 대 한 응답에서입니다.</span><span class="sxs-lookup"><span data-stu-id="34c1c-103">This example shows how to define <xref:System.Windows.Style.Triggers%2A> for a <xref:System.Windows.Controls.ListViewItem> control so that when a property value of a <xref:System.Windows.Controls.ListViewItem> changes, the <xref:System.Windows.Style> of the <xref:System.Windows.Controls.ListViewItem> changes in response.</span></span>  
  
## <a name="example"></a><span data-ttu-id="34c1c-104">예제</span><span class="sxs-lookup"><span data-stu-id="34c1c-104">Example</span></span>  
 <span data-ttu-id="34c1c-105">원하는 경우는 <xref:System.Windows.Style> 의 <xref:System.Windows.Controls.ListViewItem> 속성 변경에 대 한 응답을 변경 하려면 정의 <xref:System.Windows.Style.Triggers%2A> 에 대 한를 <xref:System.Windows.Style> 변경 합니다.</span><span class="sxs-lookup"><span data-stu-id="34c1c-105">If you want the <xref:System.Windows.Style> of a <xref:System.Windows.Controls.ListViewItem> to change in response to property changes, define <xref:System.Windows.Style.Triggers%2A> for the <xref:System.Windows.Style> change.</span></span>  
  
 <span data-ttu-id="34c1c-106">다음 예제에서는 정의 <xref:System.Windows.Trigger> 설정 하는 <xref:System.Windows.Controls.Control.Foreground%2A> 속성을 <xref:System.Windows.Media.Brushes.Blue%2A> 변경 합니다 <xref:System.Windows.FrameworkElement.Cursor%2A> 표시할를 <xref:System.Windows.Input.CursorType.Hand> 때를 <xref:System.Windows.UIElement.IsMouseOver%2A> 속성 변경 `true`.</span><span class="sxs-lookup"><span data-stu-id="34c1c-106">The following example defines a <xref:System.Windows.Trigger> that sets the <xref:System.Windows.Controls.Control.Foreground%2A> property to <xref:System.Windows.Media.Brushes.Blue%2A> and changes the <xref:System.Windows.FrameworkElement.Cursor%2A> to display a <xref:System.Windows.Input.CursorType.Hand> when the <xref:System.Windows.UIElement.IsMouseOver%2A> property changes to `true`.</span></span>  
  
 [!code-xaml[ListViewChkBox#ListViewItemTriggersStart](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewChkBox/CS/window1.xaml#listviewitemtriggersstart)]  
[!code-xaml[ListViewChkBox#Trigger](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewChkBox/CS/window1.xaml#trigger)]  
[!code-xaml[ListViewChkBox#ListViewItemTriggersEnd](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewChkBox/CS/window1.xaml#listviewitemtriggersend)]  
  
 <span data-ttu-id="34c1c-107">다음 예제에서는 정의 <xref:System.Windows.MultiTrigger> 설정 하는 <xref:System.Windows.Controls.Control.Foreground%2A> 의 속성을 <xref:System.Windows.Controls.ListViewItem> 를 <xref:System.Windows.Media.Brushes.Yellow%2A> 경우는 <xref:System.Windows.Controls.ListViewItem> 선택한 항목 이며 키보드 포커스가.</span><span class="sxs-lookup"><span data-stu-id="34c1c-107">The following example defines a <xref:System.Windows.MultiTrigger> that sets the <xref:System.Windows.Controls.Control.Foreground%2A> property of a <xref:System.Windows.Controls.ListViewItem> to <xref:System.Windows.Media.Brushes.Yellow%2A> when the <xref:System.Windows.Controls.ListViewItem> is the selected item and has keyboard focus.</span></span>  
  
 [!code-xaml[ListViewChkBox#ListViewItemTriggersStart](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewChkBox/CS/window1.xaml#listviewitemtriggersstart)]  
[!code-xaml[ListViewChkBox#MultiTrigger](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewChkBox/CS/window1.xaml#multitrigger)]  
[!code-xaml[ListViewChkBox#ListViewItemTriggersEnd](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewChkBox/CS/window1.xaml#listviewitemtriggersend)]  
  
## <a name="see-also"></a><span data-ttu-id="34c1c-108">참고자료</span><span class="sxs-lookup"><span data-stu-id="34c1c-108">See also</span></span>
- <xref:System.Windows.Controls.Control>
- <xref:System.Windows.Controls.ListView>
- <xref:System.Windows.Controls.GridView>
- [<span data-ttu-id="34c1c-109">방법 항목</span><span class="sxs-lookup"><span data-stu-id="34c1c-109">How-to Topics</span></span>](listview-how-to-topics.md)
- [<span data-ttu-id="34c1c-110">ListView 개요</span><span class="sxs-lookup"><span data-stu-id="34c1c-110">ListView Overview</span></span>](listview-overview.md)
- [<span data-ttu-id="34c1c-111">GridView 개요</span><span class="sxs-lookup"><span data-stu-id="34c1c-111">GridView Overview</span></span>](gridview-overview.md)
