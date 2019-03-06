---
title: '방법: 데이터에 ListBox 바인딩'
ms.date: 03/30/2017
helpviewer_keywords:
- ListBox controls [WPF], binding data to
- data binding [WPF], ListBox control
- binding data [WPF], to ListBox control
ms.assetid: de93a907-709a-44a7-84bf-578b846a3d8b
ms.openlocfilehash: 2cbcb0fb859605c33e2d92559b4a47aa1725472c
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/05/2019
ms.locfileid: "57372883"
---
# <a name="how-to-bind-a-listbox-to-data"></a><span data-ttu-id="b26d1-102">방법: 데이터에 ListBox 바인딩</span><span class="sxs-lookup"><span data-stu-id="b26d1-102">How to: Bind a ListBox to Data</span></span>
<span data-ttu-id="b26d1-103">응용 프로그램 개발자가 만들 수 있습니다 <xref:System.Windows.Controls.ListBox> 각각의 내용을 지정 하지 않고 컨트롤 <xref:System.Windows.Controls.ListBoxItem> 개별적으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="b26d1-103">An application developer can create <xref:System.Windows.Controls.ListBox> controls without specifying the contents of each <xref:System.Windows.Controls.ListBoxItem> separately.</span></span> <span data-ttu-id="b26d1-104">개별 항목에 데이터를 바인딩할 데이터 바인딩을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b26d1-104">You can use data binding to bind data to the individual items.</span></span>  
  
 <span data-ttu-id="b26d1-105">다음 예제에서는 만드는 방법을 보여 줍니다.는 <xref:System.Windows.Controls.ListBox> 채우는 합니다 <xref:System.Windows.Controls.ListBoxItem> 라는 데이터 원본에 데이터 바인딩하여 요소 *색*합니다.</span><span class="sxs-lookup"><span data-stu-id="b26d1-105">The following example shows how to create a <xref:System.Windows.Controls.ListBox> that populates the <xref:System.Windows.Controls.ListBoxItem> elements by data binding to a data source called *Colors*.</span></span> <span data-ttu-id="b26d1-106">사용 하 여 필요 없는 경우 <xref:System.Windows.Controls.ListBoxItem> 각 항목의 내용을 지정 하는 태그입니다.</span><span class="sxs-lookup"><span data-stu-id="b26d1-106">In this case it is not necessary to use <xref:System.Windows.Controls.ListBoxItem> tags to specify the content of each item.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b26d1-107">예제</span><span class="sxs-lookup"><span data-stu-id="b26d1-107">Example</span></span>  
 [!code-xaml[ListBoxEvent#7](~/samples/snippets/csharp/VS_Snippets_Wpf/ListBoxEvent/CSharp/Pane1.xaml#7)]  
[!code-xaml[ListBoxEvent#3](~/samples/snippets/csharp/VS_Snippets_Wpf/ListBoxEvent/CSharp/Pane1.xaml#3)]  
  
## <a name="see-also"></a><span data-ttu-id="b26d1-108">참고자료</span><span class="sxs-lookup"><span data-stu-id="b26d1-108">See also</span></span>
- <xref:System.Windows.Controls.ListBox>
- <xref:System.Windows.Controls.ListBoxItem>
- [<span data-ttu-id="b26d1-109">컨트롤</span><span class="sxs-lookup"><span data-stu-id="b26d1-109">Controls</span></span>](../advanced/optimizing-performance-controls.md)
