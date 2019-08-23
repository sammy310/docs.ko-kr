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
ms.openlocfilehash: 68c9653e616388374aad2ad33ac7dab68446241d
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/22/2019
ms.locfileid: "69923417"
---
# <a name="how-to-build-a-standard-ui-dialog-box-by-using-grid"></a><span data-ttu-id="0664f-102">방법: Grid를 사용하여 표준 UI 대화 상자 빌드</span><span class="sxs-lookup"><span data-stu-id="0664f-102">How to: Build a Standard UI Dialog Box by Using Grid</span></span>
<span data-ttu-id="0664f-103">이 예제에서는 요소를 [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] <xref:System.Windows.Controls.Grid> 사용 하 여 표준 대화 상자를 만드는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="0664f-103">This example shows how to create a standard [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] dialog box by using the <xref:System.Windows.Controls.Grid> element.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0664f-104">예제</span><span class="sxs-lookup"><span data-stu-id="0664f-104">Example</span></span>  
 <span data-ttu-id="0664f-105">다음 예제에서는 Windows 운영 체제에서 **실행** 대화 상자와 같은 대화 상자를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="0664f-105">The following example creates a dialog box like the **Run** dialog box in the Windows operating system.</span></span>  
  
 <span data-ttu-id="0664f-106">이 예제에서는를 <xref:System.Windows.Controls.Grid> 만들고 <xref:System.Windows.Controls.ColumnDefinition> 및 <xref:System.Windows.Controls.RowDefinition> 클래스를 사용 하 여 5 개의 열과 4 개의 행을 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="0664f-106">The example creates a <xref:System.Windows.Controls.Grid> and uses the <xref:System.Windows.Controls.ColumnDefinition> and <xref:System.Windows.Controls.RowDefinition> classes to define five columns and four rows.</span></span>  
  
 <span data-ttu-id="0664f-107">그런 다음이 예제에서는 대화 상자 <xref:System.Windows.Controls.Image>에 `RunIcon.png`있는 이미지를 나타내기 위해,를 추가 하 고 배치 합니다.</span><span class="sxs-lookup"><span data-stu-id="0664f-107">The example then adds and positions an <xref:System.Windows.Controls.Image>, `RunIcon.png`, to represent the image that is found in the dialog box.</span></span> <span data-ttu-id="0664f-108">이미지는의 <xref:System.Windows.Controls.Grid> 첫 번째 열과 행 (왼쪽 위 모퉁이)에 배치 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0664f-108">The image is placed in the first column and row of the <xref:System.Windows.Controls.Grid> (the upper-left corner).</span></span>  
  
 <span data-ttu-id="0664f-109">그런 다음 첫 번째 행의 <xref:System.Windows.Controls.TextBlock> 나머지 열을 포함 하는 첫 번째 열에 요소를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="0664f-109">Next, the example adds a <xref:System.Windows.Controls.TextBlock> element to the first column, which spans the remaining columns of the first row.</span></span> <span data-ttu-id="0664f-110">첫 번째 열의 <xref:System.Windows.Controls.TextBlock> 두 번째 행에 다른 요소를 추가 하 여 **열린** 텍스트 상자를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="0664f-110">It adds another <xref:System.Windows.Controls.TextBlock> element to the second row in the first column, to represent the **Open** text box.</span></span> <span data-ttu-id="0664f-111">는 <xref:System.Windows.Controls.TextBlock> 데이터 입력 영역을 나타내는와 같습니다.</span><span class="sxs-lookup"><span data-stu-id="0664f-111">A <xref:System.Windows.Controls.TextBlock> follows, which represents the data entry area.</span></span>  
  
 <span data-ttu-id="0664f-112">마지막으로,이 예에서는 <xref:System.Windows.Controls.Button> **확인**, **취소**및 **찾아보기** 이벤트를 나타내는 세 개의 요소를 최종 행에 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="0664f-112">Finally, the example adds three <xref:System.Windows.Controls.Button> elements to the final row, which represent the **OK**, **Cancel**, and **Browse** events.</span></span>  
  
 [!code-csharp[GridRunDialog#1](~/samples/snippets/csharp/VS_Snippets_Wpf/GridRunDialog/CSharp/window1.xaml.cs#1)]
 [!code-vb[GridRunDialog#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/GridRunDialog/VisualBasic/grid_vb.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="0664f-113">참고자료</span><span class="sxs-lookup"><span data-stu-id="0664f-113">See also</span></span>

- <xref:System.Windows.Controls.Grid>
- <xref:System.Windows.GridUnitType>
- [<span data-ttu-id="0664f-114">패널 개요</span><span class="sxs-lookup"><span data-stu-id="0664f-114">Panels Overview</span></span>](panels-overview.md)
- [<span data-ttu-id="0664f-115">방법 항목</span><span class="sxs-lookup"><span data-stu-id="0664f-115">How-to Topics</span></span>](grid-how-to-topics.md)
