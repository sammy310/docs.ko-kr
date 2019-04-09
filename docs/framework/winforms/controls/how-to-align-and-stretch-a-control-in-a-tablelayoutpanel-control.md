---
title: '방법: TableLayoutPanel 컨트롤에서 컨트롤 맞춤 및 늘이기'
ms.date: 03/30/2017
f1_keywords:
- net.ComponentModel.StyleCollectionEditor.TLP.AlignStretchCtrl
helpviewer_keywords:
- TableLayoutPanel control [Windows Forms], stretching controls
- controls [Windows Forms], stretching
- controls [Windows Forms], aligning
ms.assetid: 7dc1a157-6fee-4995-8ebc-b65bdc0909a8
ms.openlocfilehash: c0bcf91d358d233b5b1d2e300d63112303e87a09
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59095406"
---
# <a name="how-to-align-and-stretch-a-control-in-a-tablelayoutpanel-control"></a><span data-ttu-id="a5dc7-102">방법: TableLayoutPanel 컨트롤에서 컨트롤 맞춤 및 늘이기</span><span class="sxs-lookup"><span data-stu-id="a5dc7-102">How to: Align and Stretch a Control in a TableLayoutPanel Control</span></span>
<span data-ttu-id="a5dc7-103">정렬 하는 컨트롤에서 stretch를 <xref:System.Windows.Forms.TableLayoutPanel> 사용 하 여를 <xref:System.Windows.Forms.Control.Anchor%2A> 및 <xref:System.Windows.Forms.Control.Dock%2A> 속성.</span><span class="sxs-lookup"><span data-stu-id="a5dc7-103">You can align and stretch controls in a <xref:System.Windows.Forms.TableLayoutPanel> with the <xref:System.Windows.Forms.Control.Anchor%2A> and <xref:System.Windows.Forms.Control.Dock%2A> properties.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="a5dc7-104">표시되는 대화 상자와 메뉴 명령은 활성 설정이나 버전에 따라 도움말에서 설명하는 것과 다를 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a5dc7-104">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="a5dc7-105">설정을 변경하려면 **도구** 메뉴에서 **설정 가져오기 및 내보내기** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="a5dc7-105">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="a5dc7-106">자세한 내용은 [Visual Studio IDE 개인 설정](/visualstudio/ide/personalizing-the-visual-studio-ide)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="a5dc7-106">For more information, see [Personalize the Visual Studio IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).</span></span>  
  
### <a name="to-align-and-stretch-a-control"></a><span data-ttu-id="a5dc7-107">맞춤 및 늘이기를 제어 하려면</span><span class="sxs-lookup"><span data-stu-id="a5dc7-107">To align and stretch a control</span></span>  
  
1.  <span data-ttu-id="a5dc7-108"><xref:System.Windows.Forms.TableLayoutPanel> 도구 상자 **에서** 컨트롤을 폼으로 끌어다 놓습니다.</span><span class="sxs-lookup"><span data-stu-id="a5dc7-108">Drag a <xref:System.Windows.Forms.TableLayoutPanel> control from the **Toolbox** onto your form.</span></span>  
  
2.  <span data-ttu-id="a5dc7-109">끌어서를 <xref:System.Windows.Forms.Button> 에서 제어 합니다 **도구 상자** 의 왼쪽 위 셀에는 <xref:System.Windows.Forms.TableLayoutPanel> 컨트롤입니다.</span><span class="sxs-lookup"><span data-stu-id="a5dc7-109">Drag a <xref:System.Windows.Forms.Button> control from the **Toolbox** into the upper-left cell of the <xref:System.Windows.Forms.TableLayoutPanel> control.</span></span> <span data-ttu-id="a5dc7-110"><xref:System.Windows.Forms.Button> 중앙 제어 셀에 배치 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a5dc7-110">The <xref:System.Windows.Forms.Button> control is centered in the cell.</span></span>  
  
3.  <span data-ttu-id="a5dc7-111">값을 설정 합니다 <xref:System.Windows.Forms.Button> 컨트롤의 <xref:System.Windows.Forms.Control.Anchor%2A> 속성을 `Left,Right`입니다.</span><span class="sxs-lookup"><span data-stu-id="a5dc7-111">Set the value of the <xref:System.Windows.Forms.Button> control's <xref:System.Windows.Forms.Control.Anchor%2A> property to `Left,Right`.</span></span> <span data-ttu-id="a5dc7-112"><xref:System.Windows.Forms.Button> 컨트롤이 셀의 너비에 맞게 늘어납니다.</span><span class="sxs-lookup"><span data-stu-id="a5dc7-112">The <xref:System.Windows.Forms.Button> control stretches to match the width of the cell.</span></span>  
  
4.  <span data-ttu-id="a5dc7-113">값을 설정 합니다 <xref:System.Windows.Forms.Button> 컨트롤의 <xref:System.Windows.Forms.Control.Anchor%2A> 속성을 `Top,Bottom`입니다.</span><span class="sxs-lookup"><span data-stu-id="a5dc7-113">Set the value of the <xref:System.Windows.Forms.Button> control's <xref:System.Windows.Forms.Control.Anchor%2A> property to `Top,Bottom`.</span></span> <span data-ttu-id="a5dc7-114"><xref:System.Windows.Forms.Button> 컨트롤이 셀의 높이 맞게 늘어납니다.</span><span class="sxs-lookup"><span data-stu-id="a5dc7-114">The <xref:System.Windows.Forms.Button> control stretches to match the height of the cell.</span></span>  
  
5.  <span data-ttu-id="a5dc7-115">값을 설정 합니다 <xref:System.Windows.Forms.Button> 컨트롤의 <xref:System.Windows.Forms.Control.Dock%2A> 속성을 <xref:System.Windows.Forms.DockStyle.Fill>입니다.</span><span class="sxs-lookup"><span data-stu-id="a5dc7-115">Set the value of the <xref:System.Windows.Forms.Button> control's <xref:System.Windows.Forms.Control.Dock%2A> property to <xref:System.Windows.Forms.DockStyle.Fill>.</span></span> <span data-ttu-id="a5dc7-116"><xref:System.Windows.Forms.Button> 컨트롤이 확장 되어 셀을 채웁니다.</span><span class="sxs-lookup"><span data-stu-id="a5dc7-116">The <xref:System.Windows.Forms.Button> control expands to fill the cell.</span></span>  
  
6.  <span data-ttu-id="a5dc7-117">값을 설정 합니다 <xref:System.Windows.Forms.Button> 컨트롤의 <xref:System.Windows.Forms.Control.Dock%2A> 속성을 <xref:System.Windows.Forms.DockStyle.None>입니다.</span><span class="sxs-lookup"><span data-stu-id="a5dc7-117">Set the value of the <xref:System.Windows.Forms.Button> control's <xref:System.Windows.Forms.Control.Dock%2A> property to <xref:System.Windows.Forms.DockStyle.None>.</span></span> <span data-ttu-id="a5dc7-118"><xref:System.Windows.Forms.Button> 컨트롤 원래 크기를 반환 하 고 셀의 왼쪽 위 모퉁이로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="a5dc7-118">The <xref:System.Windows.Forms.Button> control returns to its original size and moves to the upper-left corner of the cell.</span></span> <span data-ttu-id="a5dc7-119">**Windows Forms 디자이너** 가 설정 된 <xref:System.Windows.Forms.Control.Anchor%2A> 속성을 `Top, Left`입니다.</span><span class="sxs-lookup"><span data-stu-id="a5dc7-119">The **Windows Forms Designer** has set the <xref:System.Windows.Forms.Control.Anchor%2A> property to `Top, Left`.</span></span>  
  
7.  <span data-ttu-id="a5dc7-120">값을 설정 합니다 <xref:System.Windows.Forms.Button> 컨트롤의 <xref:System.Windows.Forms.Control.Anchor%2A> 속성을 `Bottom,Right`입니다.</span><span class="sxs-lookup"><span data-stu-id="a5dc7-120">Set the value of the <xref:System.Windows.Forms.Button> control's <xref:System.Windows.Forms.Control.Anchor%2A> property to `Bottom,Right`.</span></span> <span data-ttu-id="a5dc7-121"><xref:System.Windows.Forms.Button> 셀의 오른쪽 아래 모퉁이에 컨트롤은 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="a5dc7-121">The <xref:System.Windows.Forms.Button> control moves to the lower-right corner of the cell.</span></span>  
  
8.  <span data-ttu-id="a5dc7-122">값을 설정 합니다 <xref:System.Windows.Forms.Button> 컨트롤의 <xref:System.Windows.Forms.Control.Anchor%2A> 속성을 <xref:System.Windows.Forms.AnchorStyles.None>입니다.</span><span class="sxs-lookup"><span data-stu-id="a5dc7-122">Set the value of the <xref:System.Windows.Forms.Button> control's <xref:System.Windows.Forms.Control.Anchor%2A> property to <xref:System.Windows.Forms.AnchorStyles.None>.</span></span> <span data-ttu-id="a5dc7-123"><xref:System.Windows.Forms.Button> 셀의 가운데에 컨트롤은 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="a5dc7-123">The <xref:System.Windows.Forms.Button> control moves to the center of the cell.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a5dc7-124">참고자료</span><span class="sxs-lookup"><span data-stu-id="a5dc7-124">See also</span></span>

- [<span data-ttu-id="a5dc7-125">TableLayoutPanel 컨트롤</span><span class="sxs-lookup"><span data-stu-id="a5dc7-125">TableLayoutPanel Control</span></span>](tablelayoutpanel-control-windows-forms.md)
