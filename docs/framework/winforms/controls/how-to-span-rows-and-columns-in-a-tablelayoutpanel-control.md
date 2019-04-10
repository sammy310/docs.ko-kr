---
title: '방법: TableLayoutPanel 컨트롤에서 행 및 열 확장'
ms.date: 03/30/2017
f1_keywords:
- net.ComponentModel.StyleCollectionEditor.TLP.SpanRowsColumns
helpviewer_keywords:
- columns [Windows Forms], spanning
- merging cells
- TableLayoutPanel control [Windows Forms], spanning rows and columns
- rows [Windows Forms], spanning
- cells [Windows Forms], merging
ms.assetid: a8a2fdd3-a848-48b0-a4cd-4e85ebded87e
ms.openlocfilehash: 2b2a46bf53dd6ec9bc93a74cca37dffaaaf79751
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59193137"
---
# <a name="how-to-span-rows-and-columns-in-a-tablelayoutpanel-control"></a><span data-ttu-id="a0ada-102">방법: TableLayoutPanel 컨트롤에서 행 및 열 확장</span><span class="sxs-lookup"><span data-stu-id="a0ada-102">How to: Span Rows and Columns in a TableLayoutPanel Control</span></span>
<span data-ttu-id="a0ada-103">컨트롤을 <xref:System.Windows.Forms.TableLayoutPanel> 인접 한 행과 열을 확장할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a0ada-103">Controls in a <xref:System.Windows.Forms.TableLayoutPanel> control can span adjacent rows and columns.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="a0ada-104">표시되는 대화 상자와 메뉴 명령은 활성 설정이나 버전에 따라 도움말에서 설명하는 것과 다를 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a0ada-104">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="a0ada-105">설정을 변경하려면 **도구** 메뉴에서 **설정 가져오기 및 내보내기** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="a0ada-105">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="a0ada-106">자세한 내용은 [Visual Studio IDE 개인 설정](/visualstudio/ide/personalizing-the-visual-studio-ide)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="a0ada-106">For more information, see [Personalize the Visual Studio IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).</span></span>  
  
### <a name="to-span-columns-and-rows"></a><span data-ttu-id="a0ada-107">열과 행에 걸쳐</span><span class="sxs-lookup"><span data-stu-id="a0ada-107">To span columns and rows</span></span>  
  
1.  <span data-ttu-id="a0ada-108"><xref:System.Windows.Forms.TableLayoutPanel> 도구 상자 **에서** 컨트롤을 폼으로 끌어다 놓습니다.</span><span class="sxs-lookup"><span data-stu-id="a0ada-108">Drag a <xref:System.Windows.Forms.TableLayoutPanel> control from the **Toolbox** onto your form.</span></span>  
  
2.  <span data-ttu-id="a0ada-109">끌어서를 <xref:System.Windows.Forms.Button> 에서 제어 합니다 **도구 상자** 의 왼쪽 위 셀에는 <xref:System.Windows.Forms.TableLayoutPanel> 컨트롤입니다.</span><span class="sxs-lookup"><span data-stu-id="a0ada-109">Drag a <xref:System.Windows.Forms.Button> control from the **Toolbox** into the upper-left cell of the <xref:System.Windows.Forms.TableLayoutPanel> control.</span></span>  
  
3.  <span data-ttu-id="a0ada-110">설정 된 <xref:System.Windows.Forms.Button> 컨트롤의 **ColumnSpan** 속성을 **2**합니다.</span><span class="sxs-lookup"><span data-stu-id="a0ada-110">Set the <xref:System.Windows.Forms.Button> control's **ColumnSpan** property to **2**.</span></span> <span data-ttu-id="a0ada-111"><xref:System.Windows.Forms.Button> 컨트롤 첫 번째와 두 번째 열으로 확장 합니다.</span><span class="sxs-lookup"><span data-stu-id="a0ada-111">Note that the <xref:System.Windows.Forms.Button> control spans the first and second columns.</span></span>  
  
4.  <span data-ttu-id="a0ada-112">설정 된 <xref:System.Windows.Forms.Button> 컨트롤의 **RowSpan** 속성을 **2**합니다.</span><span class="sxs-lookup"><span data-stu-id="a0ada-112">Set the <xref:System.Windows.Forms.Button> control's **RowSpan** property to **2**.</span></span> <span data-ttu-id="a0ada-113"><xref:System.Windows.Forms.Button> 첫 번째와 두 번째 행을 차지 하는 컨트롤입니다.</span><span class="sxs-lookup"><span data-stu-id="a0ada-113">Note that the <xref:System.Windows.Forms.Button> control spans the first and second rows.</span></span>  
  
5.  <span data-ttu-id="a0ada-114">설정 된 <xref:System.Windows.Forms.Button> 컨트롤의 **ColumnSpan** 속성을 **1**합니다.</span><span class="sxs-lookup"><span data-stu-id="a0ada-114">Set the <xref:System.Windows.Forms.Button> control's **ColumnSpan** property to **1**.</span></span> <span data-ttu-id="a0ada-115"><xref:System.Windows.Forms.Button> 컨트롤 첫 번째 열으로 이동 하 고 첫 번째 및 두 번째 행을 차지 합니다.</span><span class="sxs-lookup"><span data-stu-id="a0ada-115">Note that the <xref:System.Windows.Forms.Button> control moves into the first column and spans the first and second rows.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a0ada-116">참고자료</span><span class="sxs-lookup"><span data-stu-id="a0ada-116">See also</span></span>

- [<span data-ttu-id="a0ada-117">TableLayoutPanel 컨트롤</span><span class="sxs-lookup"><span data-stu-id="a0ada-117">TableLayoutPanel Control</span></span>](tablelayoutpanel-control-windows-forms.md)
