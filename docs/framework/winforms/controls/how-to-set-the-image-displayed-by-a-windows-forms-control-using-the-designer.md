---
title: '방법: 설정 하 여 표시 되는 이미지를 Windows Forms 디자이너를 사용 하는 컨트롤'
ms.date: 03/30/2017
helpviewer_keywords:
- Button control [Windows Forms], images
- Windows Forms controls, images
- controls [Windows Forms], images
- images [Windows Forms], Windows Forms controls
- examples [Windows Forms], controls
- setting images [Windows Forms], Windows Forms controls
ms.assetid: ae80d07a-e469-4251-90ca-df71f5852454
ms.openlocfilehash: 265fc88fb2bb9aef0696ea0d7e707ae07084df1d
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/09/2019
ms.locfileid: "57702259"
---
# <a name="how-to-set-the-image-displayed-by-a-windows-forms-control-using-the-designer"></a><span data-ttu-id="89d42-102">방법: 설정 하 여 표시 되는 이미지를 Windows Forms 디자이너를 사용 하는 컨트롤</span><span class="sxs-lookup"><span data-stu-id="89d42-102">How to: Set the Image Displayed by a Windows Forms Control Using the Designer</span></span>
<span data-ttu-id="89d42-103">여러 Windows Forms 컨트롤 이미지를 표시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="89d42-103">Several Windows Forms controls can display images.</span></span> <span data-ttu-id="89d42-104">이미지와 같은 디스크 아이콘을 나타내는 단추 컨트롤의 용도 명확히 구분 하는 아이콘 수를 **저장할** 명령입니다.</span><span class="sxs-lookup"><span data-stu-id="89d42-104">The image can be an icon that clarifies the purpose of the control, such as a disk icon on a button denoting the **Save** command.</span></span> <span data-ttu-id="89d42-105">또는 아이콘 배경 이미지를 원하는 모양을 제어할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="89d42-105">Alternatively, the icon can be a background image to give the control the appearance you want.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="89d42-106">표시되는 대화 상자와 메뉴 명령은 활성 설정이나 버전에 따라 도움말에서 설명하는 것과 다를 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="89d42-106">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="89d42-107">설정을 변경하려면 **도구** 메뉴에서 **설정 가져오기 및 내보내기** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="89d42-107">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="89d42-108">자세한 내용은 [Visual Studio IDE 개인 설정](/visualstudio/ide/personalizing-the-visual-studio-ide)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="89d42-108">For more information, see [Personalize the Visual Studio IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).</span></span>  
  
### <a name="to-set-the-image-displayed-by-a-control"></a><span data-ttu-id="89d42-109">컨트롤에서 표시 되는 이미지를 설정 하려면</span><span class="sxs-lookup"><span data-stu-id="89d42-109">To set the image displayed by a control</span></span>  
  
1.  <span data-ttu-id="89d42-110">에 **속성** 창에서를 **이미지** 하거나 **BackgroundImage** 컨트롤의 속성에는 클릭 줄임표 단추 (</span><span class="sxs-lookup"><span data-stu-id="89d42-110">In the **Properties** window, select the **Image** or **BackgroundImage** property of the control, then click the ellipsis button (</span></span>  
  
     <span data-ttu-id="89d42-111">![VisualStudioEllipsesButton 스크린 샷](../media/vbellipsesbutton.png "vbEllipsesButton")</span><span class="sxs-lookup"><span data-stu-id="89d42-111">![VisualStudioEllipsesButton screenshot](../media/vbellipsesbutton.png "vbEllipsesButton")</span></span>  
  
     <span data-ttu-id="89d42-112">)를 표시 하는 **리소스 선택** 대화 상자.</span><span class="sxs-lookup"><span data-stu-id="89d42-112">) to display the **Select Resource** dialog box.</span></span>  
  
2.  <span data-ttu-id="89d42-113">표시 하려는 이미지를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="89d42-113">Select the image you want to display.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="89d42-114">참고자료</span><span class="sxs-lookup"><span data-stu-id="89d42-114">See also</span></span>
- <xref:System.Drawing.Image.FromFile%2A>
- <xref:System.Drawing.Image>
- <xref:System.Windows.Forms.Control.BackgroundImage%2A>
- [<span data-ttu-id="89d42-115">개별 Windows Forms 컨트롤 레이블 지정 및 바로 가기 제공</span><span class="sxs-lookup"><span data-stu-id="89d42-115">Labeling Individual Windows Forms Controls and Providing Shortcuts to Them</span></span>](labeling-individual-windows-forms-controls-and-providing-shortcuts-to-them.md)
