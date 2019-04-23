---
title: '방법: 데이터에 ListBox 바인딩'
ms.date: 03/30/2017
helpviewer_keywords:
- ListBox controls [WPF], binding data to
- data binding [WPF], ListBox control
- binding data [WPF], to ListBox control
ms.assetid: de93a907-709a-44a7-84bf-578b846a3d8b
ms.openlocfilehash: 4dea53a524247d18628b3e7e7b2c06906dced53d
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59106442"
---
# <a name="how-to-bind-a-listbox-to-data"></a><span data-ttu-id="2543e-102">방법: 데이터에 ListBox 바인딩</span><span class="sxs-lookup"><span data-stu-id="2543e-102">How to: Bind a ListBox to Data</span></span>
<span data-ttu-id="2543e-103">응용 프로그램 개발자가 만들 수 있습니다 <xref:System.Windows.Controls.ListBox> 각각의 내용을 지정 하지 않고 컨트롤 <xref:System.Windows.Controls.ListBoxItem> 개별적으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="2543e-103">An application developer can create <xref:System.Windows.Controls.ListBox> controls without specifying the contents of each <xref:System.Windows.Controls.ListBoxItem> separately.</span></span> <span data-ttu-id="2543e-104">개별 항목에 데이터를 바인딩할 데이터 바인딩을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2543e-104">You can use data binding to bind data to the individual items.</span></span>  
  
 <span data-ttu-id="2543e-105">다음 예제에서는 만드는 방법을 보여 줍니다.는 <xref:System.Windows.Controls.ListBox> 채우는 합니다 <xref:System.Windows.Controls.ListBoxItem> 라는 데이터 원본에 데이터 바인딩하여 요소 *색*합니다.</span><span class="sxs-lookup"><span data-stu-id="2543e-105">The following example shows how to create a <xref:System.Windows.Controls.ListBox> that populates the <xref:System.Windows.Controls.ListBoxItem> elements by data binding to a data source called *Colors*.</span></span> <span data-ttu-id="2543e-106">사용 하 여 필요 없는 경우 <xref:System.Windows.Controls.ListBoxItem> 각 항목의 내용을 지정 하는 태그입니다.</span><span class="sxs-lookup"><span data-stu-id="2543e-106">In this case it is not necessary to use <xref:System.Windows.Controls.ListBoxItem> tags to specify the content of each item.</span></span>  
  
## <a name="example"></a><span data-ttu-id="2543e-107">예제</span><span class="sxs-lookup"><span data-stu-id="2543e-107">Example</span></span>  
 [!code-xaml[ListBoxEvent#7](~/samples/snippets/csharp/VS_Snippets_Wpf/ListBoxEvent/CSharp/Pane1.xaml#7)]  
[!code-xaml[ListBoxEvent#3](~/samples/snippets/csharp/VS_Snippets_Wpf/ListBoxEvent/CSharp/Pane1.xaml#3)]  
  
## <a name="see-also"></a><span data-ttu-id="2543e-108">참고자료</span><span class="sxs-lookup"><span data-stu-id="2543e-108">See also</span></span>

- <xref:System.Windows.Controls.ListBox>
- <xref:System.Windows.Controls.ListBoxItem>
- [<span data-ttu-id="2543e-109">컨트롤</span><span class="sxs-lookup"><span data-stu-id="2543e-109">Controls</span></span>](../advanced/optimizing-performance-controls.md)
