---
title: '방법: Windows Forms에서 컨트롤의 크기 조정'
ms.date: 03/30/2017
f1_keywords:
- Size.Height
- Size.Width
helpviewer_keywords:
- controls [Windows Forms], resizing
- size [Windows Forms], controls
- Windows Forms controls, size
ms.assetid: d2dba441-a8c0-4705-b8e8-2e5d86d6e7ec
author: jillre
ms.author: jillfra
manager: jillfra
ms.openlocfilehash: 3aacc9434199eb7881e362a67e1fe0c08784c4a7
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/03/2019
ms.locfileid: "73459548"
---
# <a name="how-to-resize-controls-on-windows-forms"></a><span data-ttu-id="0e23d-102">방법: Windows Forms에서 컨트롤 크기 조정</span><span class="sxs-lookup"><span data-stu-id="0e23d-102">How to: Resize controls on Windows Forms</span></span>

<span data-ttu-id="0e23d-103">개별 컨트롤의 크기를 조정할 수 있으며, <xref:System.Windows.Forms.Button> 및 <xref:System.Windows.Forms.GroupBox> 컨트롤과 같이 동일 하거나 다른 종류의 여러 컨트롤의 크기를 조정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0e23d-103">You can resize individual controls, and you can resize multiple controls of the same or different kind, such as <xref:System.Windows.Forms.Button> and <xref:System.Windows.Forms.GroupBox> controls.</span></span>

## <a name="to-resize-a-control"></a><span data-ttu-id="0e23d-104">컨트롤의 크기를 조정 하려면</span><span class="sxs-lookup"><span data-stu-id="0e23d-104">To resize a control</span></span>

<span data-ttu-id="0e23d-105">Visual Studio에서 크기를 조정할 컨트롤을 선택 하 고 8 개의 크기 조정 핸들 중 하나를 끕니다.</span><span class="sxs-lookup"><span data-stu-id="0e23d-105">In Visual Studio, select the control to be resized and drag one of the eight sizing handles.</span></span>

> [!NOTE]
> <span data-ttu-id="0e23d-106">컨트롤을 선택 하 고 **Shift** 키를 누른 채 **화살표** 키를 눌러 한 번에 한 픽셀씩 컨트롤의 크기를 조정 합니다.</span><span class="sxs-lookup"><span data-stu-id="0e23d-106">Select the control and press the **arrow** keys while holding down the **Shift** key to resize the control one pixel at a time.</span></span> <span data-ttu-id="0e23d-107">**Shift** 키와 **Ctrl** 키를 누른 채 **아래쪽 화살표** 또는 **오른쪽 화살표** 키를 눌러 컨트롤의 크기를 크게 늘립니다.</span><span class="sxs-lookup"><span data-stu-id="0e23d-107">Press the **down arrow** or **right arrow** keys while holding down the **Shift** and **Ctrl** keys to resize the control in large increments.</span></span>

## <a name="to-resize-multiple-controls-on-a-form"></a><span data-ttu-id="0e23d-108">폼에서 여러 컨트롤의 크기를 조정 하려면</span><span class="sxs-lookup"><span data-stu-id="0e23d-108">To resize multiple controls on a form</span></span>

1. <span data-ttu-id="0e23d-109">Visual Studio에서 **Ctrl** 또는 **Shift** 키를 누르고 크기를 조정 하려는 컨트롤을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="0e23d-109">In Visual Studio, hold down the **Ctrl** or **Shift** key and select the controls you want to resize.</span></span> <span data-ttu-id="0e23d-110">선택한 첫 번째 컨트롤의 크기는 다른 컨트롤에 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0e23d-110">The size of the first control you select is used for the other controls.</span></span>

2. <span data-ttu-id="0e23d-111">**서식** 메뉴에서 **같은 크기로 설정**을 선택 하 고 네 가지 옵션 중 하나를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="0e23d-111">On the **Format** menu, choose **Make Same Size**, and select one of the four options.</span></span> <span data-ttu-id="0e23d-112">처음 세 명령은 첫 번째 선택 된 컨트롤과 일치 하도록 컨트롤의 크기를 변경 합니다.</span><span class="sxs-lookup"><span data-stu-id="0e23d-112">The first three commands change the dimensions of the controls to match the first-selected control.</span></span>

## <a name="see-also"></a><span data-ttu-id="0e23d-113">참조</span><span class="sxs-lookup"><span data-stu-id="0e23d-113">See also</span></span>

- [<span data-ttu-id="0e23d-114">Windows Forms 컨트롤</span><span class="sxs-lookup"><span data-stu-id="0e23d-114">Windows Forms Controls</span></span>](index.md)
- [<span data-ttu-id="0e23d-115">개별 Windows Forms 컨트롤 레이블 지정 및 바로 가기 제공</span><span class="sxs-lookup"><span data-stu-id="0e23d-115">Labeling Individual Windows Forms Controls and Providing Shortcuts to Them</span></span>](labeling-individual-windows-forms-controls-and-providing-shortcuts-to-them.md)
- [<span data-ttu-id="0e23d-116">Windows Forms에 사용할 수 있는 컨트롤</span><span class="sxs-lookup"><span data-stu-id="0e23d-116">Controls to Use on Windows Forms</span></span>](controls-to-use-on-windows-forms.md)
- [<span data-ttu-id="0e23d-117">기능별 Windows Forms 컨트롤</span><span class="sxs-lookup"><span data-stu-id="0e23d-117">Windows Forms Controls by Function</span></span>](windows-forms-controls-by-function.md)
- <span data-ttu-id="0e23d-118">[방법: 디자이너를 사용 하 여 Windows Forms 크기 조정](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/37k2zkwx(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="0e23d-118">[How to: Resize Windows Forms Using the Designer](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/37k2zkwx(v=vs.100))</span></span>
