---
title: '방법: 맞춤선과 모눈 Windows Forms에서 컨트롤 정렬'
ms.date: 03/30/2017
f1_keywords:
- GridSize
helpviewer_keywords:
- snap to grid [Windows Forms], Windows Forms Designer
- Windows Forms, grid options in designer
- controls [Windows Forms], aligning
ms.assetid: bb54bce5-880f-4a36-af68-8cf92058dc1c
ms.openlocfilehash: 23a1c850133982c5f0136e4c21e6b73fcb94e887
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/09/2019
ms.locfileid: "57716363"
---
# <a name="how-to-arrange-controls-with-snaplines-and-the-grid-in-windows-forms"></a><span data-ttu-id="aa50e-102">방법: 맞춤선과 모눈 Windows Forms에서 컨트롤 정렬</span><span class="sxs-lookup"><span data-stu-id="aa50e-102">How to: Arrange Controls with Snaplines and the Grid in Windows Forms</span></span>
<span data-ttu-id="aa50e-103">Visual Studio의 레이아웃 기능을 사용 하 여 컨트롤을 폼에 배치 될 위치를 정확 하 게 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="aa50e-103">Using the layout features of Visual Studio, you can precisely direct where controls are placed on a form.</span></span> <span data-ttu-id="aa50e-104">컨트롤을 폼에 추가 하거나 폼에 이동 행과 Windows Forms 디자이너 그리드의 열을 자동으로 정렬할 수 있습니다 하거나 맞춤선 기능을 사용 하 여 컨트롤을 정렬할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="aa50e-104">Controls added to a form or moved on a form can be automatically aligned to the rows and columns of the Windows Forms Designer's grid, or you can align controls by using the snaplines feature.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="aa50e-105">표시되는 대화 상자와 메뉴 명령은 활성 설정이나 버전에 따라 도움말에서 설명하는 것과 다를 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="aa50e-105">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="aa50e-106">설정을 변경하려면 **도구** 메뉴에서 **설정 가져오기 및 내보내기** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="aa50e-106">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="aa50e-107">자세한 내용은 [Visual Studio IDE 개인 설정](/visualstudio/ide/personalizing-the-visual-studio-ide)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="aa50e-107">For more information, see [Personalize the Visual Studio IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).</span></span>  
  
### <a name="to-snap-all-controls-to-the-grid"></a><span data-ttu-id="aa50e-108">모든 컨트롤을 눈금에 맞춤을</span><span class="sxs-lookup"><span data-stu-id="aa50e-108">To snap all controls to the grid</span></span>  
  
-   <span data-ttu-id="aa50e-109">선택 된 **SnapToGrid** Windows Forms 디자이너에서 레이아웃 모드 **옵션** 대화 상자.</span><span class="sxs-lookup"><span data-stu-id="aa50e-109">Select the **SnapToGrid** layout mode in the Windows Forms Designer **Options** dialog box.</span></span>  
  
     <span data-ttu-id="aa50e-110">자세한 내용은 [Windows Forms 디자이너, 옵션 대화 상자, 일반](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/5aazxs78(v=vs.100))합니다.</span><span class="sxs-lookup"><span data-stu-id="aa50e-110">For more information, see [General, Windows Forms Designer, Options Dialog Box](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/5aazxs78(v=vs.100)).</span></span> <span data-ttu-id="aa50e-111">모든 컨트롤 그리드에서 요소에 따라 맞춰집니다.</span><span class="sxs-lookup"><span data-stu-id="aa50e-111">All controls now align themselves along the points on the grid.</span></span>  
  
     <span data-ttu-id="aa50e-112">현재 위치에서이 잠그는 방식으로 개별 컨트롤을 맞출 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="aa50e-112">You can snap individual controls to the grid by locking them in place.</span></span> <span data-ttu-id="aa50e-113">그러나 잠겨 있는 동안 이러한 없습니다 이동 하거나 크기를 조정 합니다.</span><span class="sxs-lookup"><span data-stu-id="aa50e-113">However, while they are locked, they cannot be moved or resized.</span></span> <span data-ttu-id="aa50e-114">잠금 컨트롤에 대 한 자세한 내용은 참조 하세요. [방법: Windows Forms에 컨트롤 잠금](how-to-lock-controls-to-windows-forms.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="aa50e-114">For more information about locking controls, see [How to: Lock Controls to Windows Forms](how-to-lock-controls-to-windows-forms.md).</span></span>  
  
### <a name="to-align-controls-using-snaplines"></a><span data-ttu-id="aa50e-115">맞춤선을 사용 하 여 컨트롤을 맞추려면</span><span class="sxs-lookup"><span data-stu-id="aa50e-115">To align controls using snaplines</span></span>  
  
-   <span data-ttu-id="aa50e-116">선택 된 **맞춤선** Windows Forms 디자이너에서 레이아웃 모드 **옵션** 대화 상자.</span><span class="sxs-lookup"><span data-stu-id="aa50e-116">Select the **SnapLines** layout mode in the Windows Forms Designer **Options** dialog box.</span></span>  
  
     <span data-ttu-id="aa50e-117">자세한 내용은 [연습: Snaplines를 사용 하 여 Forms Windows에서 컨트롤 정렬](walkthrough-arranging-controls-on-windows-forms-using-snaplines.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="aa50e-117">For more information, see [Walkthrough: Arranging Controls on Windows Forms Using Snaplines](walkthrough-arranging-controls-on-windows-forms-using-snaplines.md).</span></span> <span data-ttu-id="aa50e-118">이제 폼에서 컨트롤을 정렬 하려면 맞춤선을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="aa50e-118">You can now use snaplines to align and arrange controls on your form.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="aa50e-119">참고자료</span><span class="sxs-lookup"><span data-stu-id="aa50e-119">See also</span></span>
- <span data-ttu-id="aa50e-120">[일반적으로 Windows Forms 디자이너, 옵션 대화 상자](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/5aazxs78(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="aa50e-120">[General, Windows Forms Designer, Options Dialog Box](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/5aazxs78(v=vs.100))</span></span>
- [<span data-ttu-id="aa50e-121">연습: 맞춤선을 사용 하 여 Windows Forms에서 컨트롤 정렬</span><span class="sxs-lookup"><span data-stu-id="aa50e-121">Walkthrough: Arranging Controls on Windows Forms Using Snaplines</span></span>](walkthrough-arranging-controls-on-windows-forms-using-snaplines.md)
- [<span data-ttu-id="aa50e-122">Windows Forms 컨트롤</span><span class="sxs-lookup"><span data-stu-id="aa50e-122">Windows Forms Controls</span></span>](index.md)
- [<span data-ttu-id="aa50e-123">방법: Windows Forms에 컨트롤 추가</span><span class="sxs-lookup"><span data-stu-id="aa50e-123">How to: Add Controls to Windows Forms</span></span>](how-to-add-controls-to-windows-forms.md)
- [<span data-ttu-id="aa50e-124">Windows Forms에서 컨트롤 정렬</span><span class="sxs-lookup"><span data-stu-id="aa50e-124">Arranging Controls on Windows Forms</span></span>](arranging-controls-on-windows-forms.md)
- [<span data-ttu-id="aa50e-125">개별 Windows Forms 컨트롤 레이블 지정 및 바로 가기 제공</span><span class="sxs-lookup"><span data-stu-id="aa50e-125">Labeling Individual Windows Forms Controls and Providing Shortcuts to Them</span></span>](labeling-individual-windows-forms-controls-and-providing-shortcuts-to-them.md)
- [<span data-ttu-id="aa50e-126">Windows Forms에 사용할 수 있는 컨트롤</span><span class="sxs-lookup"><span data-stu-id="aa50e-126">Controls to Use on Windows Forms</span></span>](controls-to-use-on-windows-forms.md)
- [<span data-ttu-id="aa50e-127">기능별 Windows Forms 컨트롤</span><span class="sxs-lookup"><span data-stu-id="aa50e-127">Windows Forms Controls by Function</span></span>](windows-forms-controls-by-function.md)
