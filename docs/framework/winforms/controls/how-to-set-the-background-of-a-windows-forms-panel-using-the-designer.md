---
title: '방법: 디자이너를 사용하여 Windows Forms 패널 배경 설정'
ms.date: 03/30/2017
helpviewer_keywords:
- background colors [Windows Forms], Windows Forms Panel controls
- background images [Windows Forms], Windows Forms Panel controls
- Panel control [Windows Forms], background
- colors [Windows Forms], Windows Forms Panel controls
ms.assetid: db83cf54-3c69-4b08-ac6c-25b9b5abb1b0
ms.openlocfilehash: 6927a7118c43ced03623a9764a3ef1e0814c95cb
ms.sourcegitcommit: 0d0a6e96737dfe24d3257b7c94f25d9500f383ea
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/07/2019
ms.locfileid: "65211638"
---
# <a name="how-to-set-the-background-of-a-windows-forms-panel-using-the-designer"></a><span data-ttu-id="48a46-102">방법: 디자이너를 사용 하 여 Windows Forms 패널의 배경 설정</span><span class="sxs-lookup"><span data-stu-id="48a46-102">How to: Set the background of a Windows Forms panel using the Designer</span></span>

<span data-ttu-id="48a46-103">Windows Forms <xref:System.Windows.Forms.Panel> 컨트롤 배경색 및 배경 이미지를 표시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="48a46-103">A Windows Forms <xref:System.Windows.Forms.Panel> control can display both a background color and a background image.</span></span> <span data-ttu-id="48a46-104"><xref:System.Windows.Forms.Control.BackColor%2A> 속성 패널 레이블 등에서 포함 된 라디오 단추를 컨트롤에 대 한 배경색을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="48a46-104">The <xref:System.Windows.Forms.Control.BackColor%2A> property sets the background color for controls that are contained in the panel, such as labels and radio buttons.</span></span> <span data-ttu-id="48a46-105">경우는 <xref:System.Windows.Forms.Control.BackgroundImage%2A> 속성을 설정 하지 않으면는 <xref:System.Windows.Forms.Control.BackColor%2A> 선택 패널의 모든 입력 됩니다.</span><span class="sxs-lookup"><span data-stu-id="48a46-105">If the <xref:System.Windows.Forms.Control.BackgroundImage%2A> property is not set, the <xref:System.Windows.Forms.Control.BackColor%2A> selection will fill all of the panel.</span></span> <span data-ttu-id="48a46-106">경우는 <xref:System.Windows.Forms.Control.BackgroundImage%2A> 속성이 설정 되 면 이미지 패널에 포함 된 컨트롤 뒤에 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="48a46-106">If the <xref:System.Windows.Forms.Control.BackgroundImage%2A> property is set, the image will be displayed behind the controls that are contained in the panel.</span></span>

<span data-ttu-id="48a46-107">다음 절차를 수행 하려면을 **Windows 응용 프로그램** 포함 된 폼을 사용 하 여 프로젝트를 <xref:System.Windows.Forms.Panel> 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="48a46-107">The following procedure requires a **Windows Application** project with a form that contains a <xref:System.Windows.Forms.Panel> control.</span></span> <span data-ttu-id="48a46-108">Visual Studio에서 이러한 프로젝트를 설정 하는 방법에 대 한 정보를 참조 하세요. [방법: Windows Forms 응용 프로그램 프로젝트를 만듭니다](/visualstudio/ide/step-1-create-a-windows-forms-application-project) 고 [방법: Windows Forms에 컨트롤 추가](how-to-add-controls-to-windows-forms.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="48a46-108">For information about how to set up such a project in Visual Studio, see [How to: Create a Windows Forms application project](/visualstudio/ide/step-1-create-a-windows-forms-application-project) and [How to: Add Controls to Windows Forms](how-to-add-controls-to-windows-forms.md).</span></span>

## <a name="set-the-background-in-the-windows-forms-designer"></a><span data-ttu-id="48a46-109">Windows Forms 디자이너의 배경 설정</span><span class="sxs-lookup"><span data-stu-id="48a46-109">Set the background in the Windows Forms Designer</span></span>

1. <span data-ttu-id="48a46-110">Visual Studio에서 프로젝트를 열고 선택 된 <xref:System.Windows.Forms.Panel> 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="48a46-110">Open the project in Visual Studio and select the <xref:System.Windows.Forms.Panel> control.</span></span>

2. <span data-ttu-id="48a46-111">에 **속성** 창, 화살표 옆의 단추 클릭을 <xref:System.Windows.Forms.Control.BackColor%2A> 속성 창을 표시 하는 세 개의 탭을 사용 하 여 합니다.</span><span class="sxs-lookup"><span data-stu-id="48a46-111">In the **Properties** window, click the arrow button next to the <xref:System.Windows.Forms.Control.BackColor%2A> property to display a window with three tabs.</span></span>

3. <span data-ttu-id="48a46-112">선택 된 **사용자 지정** 색상표를 표시 하려면 탭 합니다.</span><span class="sxs-lookup"><span data-stu-id="48a46-112">Select the **Custom** tab to display a palette of colors.</span></span>

4. <span data-ttu-id="48a46-113">선택 된 **웹** 또는 **시스템** 미리 정의 된 색 이름 목록을 표시 하려면 탭 및 색을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="48a46-113">Select the **Web** or **System** tab to display a list of predefined names for colors, and then select a color.</span></span>

5. <span data-ttu-id="48a46-114">에 **속성** 창, 화살표 옆의 단추 클릭을 <xref:System.Windows.Forms.Control.BackgroundImage%2A> 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="48a46-114">In the **Properties** window, click the arrow button next to the <xref:System.Windows.Forms.Control.BackgroundImage%2A> property.</span></span>

6. <span data-ttu-id="48a46-115">에 **열려** 대화 상자를 표시 하려는 파일을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="48a46-115">In the **Open** dialog box, select the file that you want to display.</span></span>

## <a name="see-also"></a><span data-ttu-id="48a46-116">참고자료</span><span class="sxs-lookup"><span data-stu-id="48a46-116">See also</span></span>

- <xref:System.Windows.Forms.Control.BackColor%2A>
- <xref:System.Windows.Forms.Control.BackgroundImage%2A>
- [<span data-ttu-id="48a46-117">Panel 컨트롤</span><span class="sxs-lookup"><span data-stu-id="48a46-117">Panel Control</span></span>](panel-control-windows-forms.md)
- [<span data-ttu-id="48a46-118">Panel 컨트롤 개요</span><span class="sxs-lookup"><span data-stu-id="48a46-118">Panel Control Overview</span></span>](panel-control-overview-windows-forms.md)
- [<span data-ttu-id="48a46-119">방법: 디자이너를 사용 하 여 Windows Forms 패널 컨트롤을 사용 하 여 그룹 컨트롤</span><span class="sxs-lookup"><span data-stu-id="48a46-119">How to: Group Controls with the Windows Forms Panel Control Using the Designer</span></span>](group-controls-with-wf-panel-control-using-the-designer.md)
