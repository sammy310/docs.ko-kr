---
title: '방법: 디자이너를 사용하여 Windows Forms 컨트롤에서 표시하는 이미지 설정'
ms.date: 03/30/2017
helpviewer_keywords:
- Button control [Windows Forms], images
- Windows Forms controls, images
- controls [Windows Forms], images
- images [Windows Forms], Windows Forms controls
- examples [Windows Forms], controls
- setting images [Windows Forms], Windows Forms controls
ms.assetid: ae80d07a-e469-4251-90ca-df71f5852454
ms.openlocfilehash: b914509656d3ce67d62dcd23cebdcc3b74278d72
ms.sourcegitcommit: c4e9d05644c9cb89de5ce6002723de107ea2e2c4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/19/2019
ms.locfileid: "65882002"
---
# <a name="how-to-set-the-image-displayed-by-a-windows-forms-control-using-the-designer"></a><span data-ttu-id="3ee03-102">방법: 디자이너를 사용하여 Windows Forms 컨트롤에서 표시하는 이미지 설정</span><span class="sxs-lookup"><span data-stu-id="3ee03-102">How to: Set the Image Displayed by a Windows Forms Control Using the Designer</span></span>
<span data-ttu-id="3ee03-103">여러 Windows Forms 컨트롤 이미지를 표시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3ee03-103">Several Windows Forms controls can display images.</span></span> <span data-ttu-id="3ee03-104">이미지와 같은 디스크 아이콘을 나타내는 단추 컨트롤의 용도 명확히 구분 하는 아이콘 수를 **저장할** 명령입니다.</span><span class="sxs-lookup"><span data-stu-id="3ee03-104">The image can be an icon that clarifies the purpose of the control, such as a disk icon on a button denoting the **Save** command.</span></span> <span data-ttu-id="3ee03-105">또는 아이콘 배경 이미지를 원하는 모양을 제어할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3ee03-105">Alternatively, the icon can be a background image to give the control the appearance you want.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="3ee03-106">표시되는 대화 상자와 메뉴 명령은 활성 설정이나 버전에 따라 도움말에서 설명하는 것과 다를 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3ee03-106">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="3ee03-107">설정을 변경하려면 **도구** 메뉴에서 **설정 가져오기 및 내보내기** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="3ee03-107">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="3ee03-108">자세한 내용은 [Visual Studio IDE 개인 설정](/visualstudio/ide/personalizing-the-visual-studio-ide)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="3ee03-108">For more information, see [Personalize the Visual Studio IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).</span></span>  
  
### <a name="to-set-the-image-displayed-by-a-control"></a><span data-ttu-id="3ee03-109">컨트롤에서 표시 되는 이미지를 설정 하려면</span><span class="sxs-lookup"><span data-stu-id="3ee03-109">To set the image displayed by a control</span></span>  
  
1. <span data-ttu-id="3ee03-110">에 **속성** 창에서를 **이미지** 하거나 **BackgroundImage** 컨트롤의 속성에는 클릭 줄임표 단추 (</span><span class="sxs-lookup"><span data-stu-id="3ee03-110">In the **Properties** window, select the **Image** or **BackgroundImage** property of the control, then click the ellipsis button (</span></span>  
  
     ![Visual Studio의 속성 창에서 줄임표 단추 (...).](./media/visual-studio-ellipsis-button.png)<span data-ttu-id="3ee03-112">)</span><span class="sxs-lookup"><span data-stu-id="3ee03-112">)</span></span>  
  
     <span data-ttu-id="3ee03-113">)를 표시 하는 **리소스 선택** 대화 상자.</span><span class="sxs-lookup"><span data-stu-id="3ee03-113">) to display the **Select Resource** dialog box.</span></span>  
  
2. <span data-ttu-id="3ee03-114">표시 하려는 이미지를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="3ee03-114">Select the image you want to display.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3ee03-115">참고자료</span><span class="sxs-lookup"><span data-stu-id="3ee03-115">See also</span></span>

- <xref:System.Drawing.Image.FromFile%2A>
- <xref:System.Drawing.Image>
- <xref:System.Windows.Forms.Control.BackgroundImage%2A>
- [<span data-ttu-id="3ee03-116">개별 Windows Forms 컨트롤 레이블 지정 및 바로 가기 제공</span><span class="sxs-lookup"><span data-stu-id="3ee03-116">Labeling Individual Windows Forms Controls and Providing Shortcuts to Them</span></span>](labeling-individual-windows-forms-controls-and-providing-shortcuts-to-them.md)
