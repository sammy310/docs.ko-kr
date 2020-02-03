---
title: 디자이너를 사용 하 여 패널의 배경 설정
ms.date: 03/30/2017
helpviewer_keywords:
- background colors [Windows Forms], Windows Forms Panel controls
- background images [Windows Forms], Windows Forms Panel controls
- Panel control [Windows Forms], background
- colors [Windows Forms], Windows Forms Panel controls
ms.assetid: db83cf54-3c69-4b08-ac6c-25b9b5abb1b0
ms.openlocfilehash: 8bdefba433632f7ba02f549a549c52c7aa56c2d7
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/24/2020
ms.locfileid: "76731925"
---
# <a name="how-to-set-the-background-of-a-windows-forms-panel-using-the-designer"></a><span data-ttu-id="343f5-102">방법: 디자이너를 사용 하 여 Windows Forms 패널의 배경 설정</span><span class="sxs-lookup"><span data-stu-id="343f5-102">How to: Set the background of a Windows Forms panel using the Designer</span></span>

<span data-ttu-id="343f5-103">Windows Forms <xref:System.Windows.Forms.Panel> 컨트롤은 배경색과 배경 이미지를 모두 표시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="343f5-103">A Windows Forms <xref:System.Windows.Forms.Panel> control can display both a background color and a background image.</span></span> <span data-ttu-id="343f5-104"><xref:System.Windows.Forms.Control.BackColor%2A> 속성은 레이블 및 라디오 단추와 같이 패널에 포함 된 컨트롤의 배경색을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="343f5-104">The <xref:System.Windows.Forms.Control.BackColor%2A> property sets the background color for controls that are contained in the panel, such as labels and radio buttons.</span></span> <span data-ttu-id="343f5-105"><xref:System.Windows.Forms.Control.BackgroundImage%2A> 속성이 설정 되지 않은 경우 <xref:System.Windows.Forms.Control.BackColor%2A> 선택이 모든 패널을 채웁니다.</span><span class="sxs-lookup"><span data-stu-id="343f5-105">If the <xref:System.Windows.Forms.Control.BackgroundImage%2A> property is not set, the <xref:System.Windows.Forms.Control.BackColor%2A> selection will fill all of the panel.</span></span> <span data-ttu-id="343f5-106"><xref:System.Windows.Forms.Control.BackgroundImage%2A> 속성이 설정 되어 있으면 패널에 포함 된 컨트롤 뒤에 이미지가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="343f5-106">If the <xref:System.Windows.Forms.Control.BackgroundImage%2A> property is set, the image will be displayed behind the controls that are contained in the panel.</span></span>

<span data-ttu-id="343f5-107">다음 절차에는 <xref:System.Windows.Forms.Panel> 컨트롤을 포함 하는 폼을 포함 하는 **Windows 응용 프로그램** 프로젝트가 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="343f5-107">The following procedure requires a **Windows Application** project with a form that contains a <xref:System.Windows.Forms.Panel> control.</span></span> <span data-ttu-id="343f5-108">Visual Studio에서 이러한 프로젝트를 설정 하는 방법에 대 한 자세한 내용은 [방법: Windows Forms 응용 프로그램 프로젝트 만들기](/visualstudio/ide/step-1-create-a-windows-forms-application-project) 및 [방법: Windows Forms에 컨트롤 추가](how-to-add-controls-to-windows-forms.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="343f5-108">For information about how to set up such a project in Visual Studio, see [How to: Create a Windows Forms application project](/visualstudio/ide/step-1-create-a-windows-forms-application-project) and [How to: Add Controls to Windows Forms](how-to-add-controls-to-windows-forms.md).</span></span>

## <a name="set-the-background-in-the-windows-forms-designer"></a><span data-ttu-id="343f5-109">Windows Forms 디자이너의 배경 설정</span><span class="sxs-lookup"><span data-stu-id="343f5-109">Set the background in the Windows Forms Designer</span></span>

1. <span data-ttu-id="343f5-110">Visual Studio에서 프로젝트를 열고 <xref:System.Windows.Forms.Panel> 컨트롤을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="343f5-110">Open the project in Visual Studio and select the <xref:System.Windows.Forms.Panel> control.</span></span>

2. <span data-ttu-id="343f5-111">**속성** 창에서 <xref:System.Windows.Forms.Control.BackColor%2A> 속성 옆의 화살표 단추를 클릭 하 여 세 개의 탭이 포함 된 창을 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="343f5-111">In the **Properties** window, click the arrow button next to the <xref:System.Windows.Forms.Control.BackColor%2A> property to display a window with three tabs.</span></span>

3. <span data-ttu-id="343f5-112">**사용자 지정** 탭을 선택 하 여 색의 색상표를 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="343f5-112">Select the **Custom** tab to display a palette of colors.</span></span>

4. <span data-ttu-id="343f5-113">**웹** 또는 **시스템** 탭을 선택 하 여 색의 미리 정의 된 이름 목록을 표시 하 고 색을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="343f5-113">Select the **Web** or **System** tab to display a list of predefined names for colors, and then select a color.</span></span>

5. <span data-ttu-id="343f5-114">**속성** 창에서 <xref:System.Windows.Forms.Control.BackgroundImage%2A> 속성 옆의 화살표 단추를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="343f5-114">In the **Properties** window, click the arrow button next to the <xref:System.Windows.Forms.Control.BackgroundImage%2A> property.</span></span>

6. <span data-ttu-id="343f5-115">**열기** 대화 상자에서 표시 하려는 파일을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="343f5-115">In the **Open** dialog box, select the file that you want to display.</span></span>

## <a name="see-also"></a><span data-ttu-id="343f5-116">참고 항목</span><span class="sxs-lookup"><span data-stu-id="343f5-116">See also</span></span>

- <xref:System.Windows.Forms.Control.BackColor%2A>
- <xref:System.Windows.Forms.Control.BackgroundImage%2A>
- [<span data-ttu-id="343f5-117">Panel 컨트롤</span><span class="sxs-lookup"><span data-stu-id="343f5-117">Panel Control</span></span>](panel-control-windows-forms.md)
- [<span data-ttu-id="343f5-118">Panel 컨트롤 개요</span><span class="sxs-lookup"><span data-stu-id="343f5-118">Panel Control Overview</span></span>](panel-control-overview-windows-forms.md)
- [<span data-ttu-id="343f5-119">방법: 디자이너에서 Windows Forms 패널 컨트롤을 사용하여 컨트롤 그룹화</span><span class="sxs-lookup"><span data-stu-id="343f5-119">How to: Group Controls with the Windows Forms Panel Control Using the Designer</span></span>](group-controls-with-wf-panel-control-using-the-designer.md)
