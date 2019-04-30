---
title: '방법: Grid를 사용하여 표준 UI 대화 상자 빌드'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- dialog boxes [WPF], creating
- Grid control [WPF], creating [WPF], dialog box
ms.assetid: d6ac3d51-844b-4d29-96d8-81a696a7b960
ms.openlocfilehash: 0ade908e92e552017acb9ba242ccba2c28c3c995
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62051054"
---
# <a name="how-to-build-a-standard-ui-dialog-box-by-using-grid"></a><span data-ttu-id="e7af3-102">방법: Grid를 사용하여 표준 UI 대화 상자 빌드</span><span class="sxs-lookup"><span data-stu-id="e7af3-102">How to: Build a Standard UI Dialog Box by Using Grid</span></span>
<span data-ttu-id="e7af3-103">이 예제에는 표준을 만드는 방법을 보여 줍니다 [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] 를 사용 하 여 대화 상자는 <xref:System.Windows.Controls.Grid> 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="e7af3-103">This example shows how to create a standard [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] dialog box by using the <xref:System.Windows.Controls.Grid> element.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e7af3-104">예제</span><span class="sxs-lookup"><span data-stu-id="e7af3-104">Example</span></span>  
 <span data-ttu-id="e7af3-105">다음 예제에서는 같은 대화 상자가 합니다 **실행** 대화 상자는 [!INCLUDE[TLA#tla_mswin](../../../../includes/tlasharptla-mswin-md.md)] 운영 체제입니다.</span><span class="sxs-lookup"><span data-stu-id="e7af3-105">The following example creates a dialog box like the **Run** dialog box in the [!INCLUDE[TLA#tla_mswin](../../../../includes/tlasharptla-mswin-md.md)] operating system.</span></span>  
  
 <span data-ttu-id="e7af3-106">만듭니다는 <xref:System.Windows.Controls.Grid> 사용 하는 <xref:System.Windows.Controls.ColumnDefinition> 및 <xref:System.Windows.Controls.RowDefinition> 다섯 개의 열 / 행 4 개를 정의 하는 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="e7af3-106">The example creates a <xref:System.Windows.Controls.Grid> and uses the <xref:System.Windows.Controls.ColumnDefinition> and <xref:System.Windows.Controls.RowDefinition> classes to define five columns and four rows.</span></span>  
  
 <span data-ttu-id="e7af3-107">이 예제에서 다음 추가 하 고 배치를 <xref:System.Windows.Controls.Image>, `RunIcon.png`, 대화 상자에 있는 이미지를 나타내는입니다.</span><span class="sxs-lookup"><span data-stu-id="e7af3-107">The example then adds and positions an <xref:System.Windows.Controls.Image>, `RunIcon.png`, to represent the image that is found in the dialog box.</span></span> <span data-ttu-id="e7af3-108">첫 번째 열과 행에는 이미지가 <xref:System.Windows.Controls.Grid> (왼쪽 위 모서리).</span><span class="sxs-lookup"><span data-stu-id="e7af3-108">The image is placed in the first column and row of the <xref:System.Windows.Controls.Grid> (the upper-left corner).</span></span>  
  
 <span data-ttu-id="e7af3-109">이 예제에서는 추가 하는 다음으로 <xref:System.Windows.Controls.TextBlock> 첫 번째 행의 나머지 열을 포함 하는 첫 번째 열에 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="e7af3-109">Next, the example adds a <xref:System.Windows.Controls.TextBlock> element to the first column, which spans the remaining columns of the first row.</span></span> <span data-ttu-id="e7af3-110">다른 추가 <xref:System.Windows.Controls.TextBlock> 요소를 나타내는 첫 번째 열에서 두 번째 행에는 **오픈** 입력란입니다.</span><span class="sxs-lookup"><span data-stu-id="e7af3-110">It adds another <xref:System.Windows.Controls.TextBlock> element to the second row in the first column, to represent the **Open** text box.</span></span> <span data-ttu-id="e7af3-111"><xref:System.Windows.Controls.TextBlock> 데이터 항목 영역을 나타내는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="e7af3-111">A <xref:System.Windows.Controls.TextBlock> follows, which represents the data entry area.</span></span>  
  
 <span data-ttu-id="e7af3-112">마지막으로,이 예제에서는 추가 세 <xref:System.Windows.Controls.Button> 마지막 행을 나타내는 요소를 **확인**를 **취소**, 및 **찾아보기** 이벤트입니다.</span><span class="sxs-lookup"><span data-stu-id="e7af3-112">Finally, the example adds three <xref:System.Windows.Controls.Button> elements to the final row, which represent the **OK**, **Cancel**, and **Browse** events.</span></span>  
  
 [!code-csharp[GridRunDialog#1](~/samples/snippets/csharp/VS_Snippets_Wpf/GridRunDialog/CSharp/window1.xaml.cs#1)]
 [!code-vb[GridRunDialog#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/GridRunDialog/VisualBasic/grid_vb.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="e7af3-113">참고자료</span><span class="sxs-lookup"><span data-stu-id="e7af3-113">See also</span></span>

- <xref:System.Windows.Controls.Grid>
- <xref:System.Windows.GridUnitType>
- [<span data-ttu-id="e7af3-114">패널 개요</span><span class="sxs-lookup"><span data-stu-id="e7af3-114">Panels Overview</span></span>](panels-overview.md)
- [<span data-ttu-id="e7af3-115">방법 항목</span><span class="sxs-lookup"><span data-stu-id="e7af3-115">How-to Topics</span></span>](grid-how-to-topics.md)
