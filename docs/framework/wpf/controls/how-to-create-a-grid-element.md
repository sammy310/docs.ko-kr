---
title: '방법: Grid 요소 만들기'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Grid control [WPF], creating [WPF], grid instance
ms.assetid: b2f07626-9df8-43b8-8d36-492f3cb42837
ms.openlocfilehash: ebb9369da73bd595338e5b6ef42bda639bde6ed4
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59134539"
---
# <a name="how-to-create-a-grid-element"></a><span data-ttu-id="0e718-102">방법: Grid 요소 만들기</span><span class="sxs-lookup"><span data-stu-id="0e718-102">How to: Create a Grid Element</span></span>
## <a name="example"></a><span data-ttu-id="0e718-103">예제</span><span class="sxs-lookup"><span data-stu-id="0e718-103">Example</span></span>  
 <span data-ttu-id="0e718-104">다음 예제에서는 만들고의 인스턴스를 사용 하는 방법을 보여 줍니다 <xref:System.Windows.Controls.Grid> 중 하나를 사용 하 여 [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] 또는 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="0e718-104">The following example shows how to create and use an instance of <xref:System.Windows.Controls.Grid> by using either [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] or code.</span></span> <span data-ttu-id="0e718-105">이 예제에서는 세 <xref:System.Windows.Controls.ColumnDefinition> 개체 및 3 <xref:System.Windows.Controls.RowDefinition> 9에 있는 표를 만들려면 셀, 워크시트와 같이 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="0e718-105">This example uses three <xref:System.Windows.Controls.ColumnDefinition> objects and three <xref:System.Windows.Controls.RowDefinition> objects to create a grid that has nine cells, such as in a worksheet.</span></span> <span data-ttu-id="0e718-106">각 셀을 포함을 <xref:System.Windows.Controls.TextBlock> 데이터 및 맨 위 행을 나타내는 요소에 포함 되어는 <xref:System.Windows.Controls.TextBlock> 사용 하 여를 <xref:System.Windows.Controls.Grid.ColumnSpan%2A> 적용 하는 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="0e718-106">Each cell contains a <xref:System.Windows.Controls.TextBlock> element that represents data, and the top row contains a <xref:System.Windows.Controls.TextBlock> with the <xref:System.Windows.Controls.Grid.ColumnSpan%2A> property applied.</span></span> <span data-ttu-id="0e718-107">각 셀의 경계를 표시 하는 <xref:System.Windows.Controls.Grid.ShowGridLines%2A> 속성을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0e718-107">To show the boundaries of each cell, the <xref:System.Windows.Controls.Grid.ShowGridLines%2A> property is enabled.</span></span>  
  
 [!code-csharp[Grid#3](~/samples/snippets/csharp/VS_Snippets_Wpf/Grid/CSharp/Grid_Code.cs#3)]
 [!code-vb[Grid#3](~/samples/snippets/visualbasic/VS_Snippets_Wpf/Grid/VisualBasic/grid_vb.vb#3)]
 [!code-xaml[Grid#3](~/samples/snippets/xaml/VS_Snippets_Wpf/Grid/XAML/default.xaml#3)]  
  
  <span data-ttu-id="0e718-108">어느 방법이 든 아래와 같이 동일한 훨씬 보이는 사용자 인터페이스를 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="0e718-108">Either approach will generate a user interface that looks much the same, like the one below.</span></span>

  ![스크린샷 세 개의 열을 분할할 표를 포함 하는 WPF 사용자 인터페이스를 보여 줍니다.](././media/how-to-create-a-grid-element/how-to-create-a-grid-element.png)
## <a name="see-also"></a><span data-ttu-id="0e718-112">참고자료</span><span class="sxs-lookup"><span data-stu-id="0e718-112">See also</span></span>

- <xref:System.Windows.Controls.Grid>
- [<span data-ttu-id="0e718-113">패널 개요</span><span class="sxs-lookup"><span data-stu-id="0e718-113">Panels Overview</span></span>](panels-overview.md)
