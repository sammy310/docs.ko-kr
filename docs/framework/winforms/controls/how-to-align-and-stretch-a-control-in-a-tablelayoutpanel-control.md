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
ms.openlocfilehash: fd32593bcad9e3f3ef93edee8aa2659d423f9feb
ms.sourcegitcommit: 0d0a6e96737dfe24d3257b7c94f25d9500f383ea
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/07/2019
ms.locfileid: "65210359"
---
# <a name="how-to-align-and-stretch-a-control-in-a-tablelayoutpanel-control"></a><span data-ttu-id="12697-102">방법: TableLayoutPanel 컨트롤에서 컨트롤 맞춤 및 늘이기</span><span class="sxs-lookup"><span data-stu-id="12697-102">How to: Align and Stretch a Control in a TableLayoutPanel Control</span></span>

<span data-ttu-id="12697-103">정렬 하는 컨트롤에서 stretch를 <xref:System.Windows.Forms.TableLayoutPanel> 사용 하 여를 <xref:System.Windows.Forms.Control.Anchor%2A> 및 <xref:System.Windows.Forms.Control.Dock%2A> 속성.</span><span class="sxs-lookup"><span data-stu-id="12697-103">You can align and stretch controls in a <xref:System.Windows.Forms.TableLayoutPanel> with the <xref:System.Windows.Forms.Control.Anchor%2A> and <xref:System.Windows.Forms.Control.Dock%2A> properties.</span></span>

## <a name="align-and-stretch-a-control"></a><span data-ttu-id="12697-104">맞춤 및 늘이기 컨트롤</span><span class="sxs-lookup"><span data-stu-id="12697-104">Align and stretch a control</span></span>

1. <span data-ttu-id="12697-105">Visual Studio에서 끌어를 <xref:System.Windows.Forms.TableLayoutPanel> 에서 제어 합니다 **도구 상자** 폼입니다.</span><span class="sxs-lookup"><span data-stu-id="12697-105">In Visual Studio, drag a <xref:System.Windows.Forms.TableLayoutPanel> control from the **Toolbox** onto your form.</span></span>

2. <span data-ttu-id="12697-106">끌어서를 <xref:System.Windows.Forms.Button> 에서 제어 합니다 **도구 상자** 의 왼쪽 위 셀에는 <xref:System.Windows.Forms.TableLayoutPanel> 컨트롤입니다.</span><span class="sxs-lookup"><span data-stu-id="12697-106">Drag a <xref:System.Windows.Forms.Button> control from the **Toolbox** into the upper-left cell of the <xref:System.Windows.Forms.TableLayoutPanel> control.</span></span> <span data-ttu-id="12697-107"><xref:System.Windows.Forms.Button> 중앙 제어 셀에 배치 됩니다.</span><span class="sxs-lookup"><span data-stu-id="12697-107">The <xref:System.Windows.Forms.Button> control is centered in the cell.</span></span>

3. <span data-ttu-id="12697-108">값을 설정 합니다 <xref:System.Windows.Forms.Button> 컨트롤의 <xref:System.Windows.Forms.Control.Anchor%2A> 속성을 `Left,Right`입니다.</span><span class="sxs-lookup"><span data-stu-id="12697-108">Set the value of the <xref:System.Windows.Forms.Button> control's <xref:System.Windows.Forms.Control.Anchor%2A> property to `Left,Right`.</span></span> <span data-ttu-id="12697-109"><xref:System.Windows.Forms.Button> 컨트롤이 셀의 너비에 맞게 늘어납니다.</span><span class="sxs-lookup"><span data-stu-id="12697-109">The <xref:System.Windows.Forms.Button> control stretches to match the width of the cell.</span></span>

4. <span data-ttu-id="12697-110">값을 설정 합니다 <xref:System.Windows.Forms.Button> 컨트롤의 <xref:System.Windows.Forms.Control.Anchor%2A> 속성을 `Top,Bottom`입니다.</span><span class="sxs-lookup"><span data-stu-id="12697-110">Set the value of the <xref:System.Windows.Forms.Button> control's <xref:System.Windows.Forms.Control.Anchor%2A> property to `Top,Bottom`.</span></span> <span data-ttu-id="12697-111"><xref:System.Windows.Forms.Button> 컨트롤이 셀의 높이 맞게 늘어납니다.</span><span class="sxs-lookup"><span data-stu-id="12697-111">The <xref:System.Windows.Forms.Button> control stretches to match the height of the cell.</span></span>

5. <span data-ttu-id="12697-112">값을 설정 합니다 <xref:System.Windows.Forms.Button> 컨트롤의 <xref:System.Windows.Forms.Control.Dock%2A> 속성을 <xref:System.Windows.Forms.DockStyle.Fill>입니다.</span><span class="sxs-lookup"><span data-stu-id="12697-112">Set the value of the <xref:System.Windows.Forms.Button> control's <xref:System.Windows.Forms.Control.Dock%2A> property to <xref:System.Windows.Forms.DockStyle.Fill>.</span></span> <span data-ttu-id="12697-113"><xref:System.Windows.Forms.Button> 컨트롤이 확장 되어 셀을 채웁니다.</span><span class="sxs-lookup"><span data-stu-id="12697-113">The <xref:System.Windows.Forms.Button> control expands to fill the cell.</span></span>

6. <span data-ttu-id="12697-114">값을 설정 합니다 <xref:System.Windows.Forms.Button> 컨트롤의 <xref:System.Windows.Forms.Control.Dock%2A> 속성을 <xref:System.Windows.Forms.DockStyle.None>입니다.</span><span class="sxs-lookup"><span data-stu-id="12697-114">Set the value of the <xref:System.Windows.Forms.Button> control's <xref:System.Windows.Forms.Control.Dock%2A> property to <xref:System.Windows.Forms.DockStyle.None>.</span></span> <span data-ttu-id="12697-115"><xref:System.Windows.Forms.Button> 컨트롤 원래 크기를 반환 하 고 셀의 왼쪽 위 모퉁이로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="12697-115">The <xref:System.Windows.Forms.Button> control returns to its original size and moves to the upper-left corner of the cell.</span></span> <span data-ttu-id="12697-116">**Windows Forms 디자이너** 가 설정 된 <xref:System.Windows.Forms.Control.Anchor%2A> 속성을 `Top, Left`입니다.</span><span class="sxs-lookup"><span data-stu-id="12697-116">The **Windows Forms Designer** has set the <xref:System.Windows.Forms.Control.Anchor%2A> property to `Top, Left`.</span></span>

7. <span data-ttu-id="12697-117">값을 설정 합니다 <xref:System.Windows.Forms.Button> 컨트롤의 <xref:System.Windows.Forms.Control.Anchor%2A> 속성을 `Bottom,Right`입니다.</span><span class="sxs-lookup"><span data-stu-id="12697-117">Set the value of the <xref:System.Windows.Forms.Button> control's <xref:System.Windows.Forms.Control.Anchor%2A> property to `Bottom,Right`.</span></span> <span data-ttu-id="12697-118"><xref:System.Windows.Forms.Button> 셀의 오른쪽 아래 모퉁이에 컨트롤은 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="12697-118">The <xref:System.Windows.Forms.Button> control moves to the lower-right corner of the cell.</span></span>

8. <span data-ttu-id="12697-119">값을 설정 합니다 <xref:System.Windows.Forms.Button> 컨트롤의 <xref:System.Windows.Forms.Control.Anchor%2A> 속성을 <xref:System.Windows.Forms.AnchorStyles.None>입니다.</span><span class="sxs-lookup"><span data-stu-id="12697-119">Set the value of the <xref:System.Windows.Forms.Button> control's <xref:System.Windows.Forms.Control.Anchor%2A> property to <xref:System.Windows.Forms.AnchorStyles.None>.</span></span> <span data-ttu-id="12697-120"><xref:System.Windows.Forms.Button> 셀의 가운데에 컨트롤은 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="12697-120">The <xref:System.Windows.Forms.Button> control moves to the center of the cell.</span></span>

## <a name="see-also"></a><span data-ttu-id="12697-121">참고자료</span><span class="sxs-lookup"><span data-stu-id="12697-121">See also</span></span>

- [<span data-ttu-id="12697-122">TableLayoutPanel 컨트롤</span><span class="sxs-lookup"><span data-stu-id="12697-122">TableLayoutPanel Control</span></span>](tablelayoutpanel-control-windows-forms.md)
