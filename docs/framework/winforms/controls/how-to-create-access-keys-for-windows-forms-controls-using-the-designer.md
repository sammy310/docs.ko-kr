---
title: '방법: 디자이너를 사용하여 Windows Forms 컨트롤에 대한 선택키 만들기'
ms.date: 03/30/2017
helpviewer_keywords:
- controls [Windows Forms], access keys
- Button control [Windows Forms], access keys
- dialog box controls [Windows Forms], mnemonics
- access keys [Windows Forms], creating for controls
- mnemonics [Windows Forms], adding to dialog box controls
- ampersand character in shortcut key
- Windows Forms controls, access keys
- examples [Windows Forms], controls
- Text property [Windows Forms], specifying access keys for controls
- keyboard shortcuts [Windows Forms], creating for controls
- access keys [Windows Forms], Windows Forms
- ALT key
ms.assetid: 4c374c4c-4ca9-4a68-ac96-9dc3ab0f518a
ms.openlocfilehash: 900a955173c28c7b86fce73e418561ed437719c4
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59216927"
---
# <a name="how-to-create-access-keys-for-windows-forms-controls-using-the-designer"></a><span data-ttu-id="205ad-102">방법: 디자이너를 사용하여 Windows Forms 컨트롤에 대한 선택키 만들기</span><span class="sxs-lookup"><span data-stu-id="205ad-102">How to: Create Access Keys for Windows Forms Controls Using the Designer</span></span>
<span data-ttu-id="205ad-103">*선택키가* 은 메뉴, 메뉴 항목 또는 예: 단추 컨트롤의 레이블 텍스트에 밑줄이 그어진된 문자입니다.</span><span class="sxs-lookup"><span data-stu-id="205ad-103">An *access key* is an underlined character in the text of a menu, menu item, or the label of a control such as a button.</span></span> <span data-ttu-id="205ad-104">사용자를가 단추를 미리 정의 된 액세스 키를 사용 하 여 함께에서 ALT 키를 눌러 "클릭" 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="205ad-104">It enables the user to "click" a button by pressing the ALT key in combination with the predefined access key.</span></span> <span data-ttu-id="205ad-105">예를 들어, 단추 폼을 인쇄 하는 프로시저를 실행 하는 경우 및 해당 `Text` "Print" 추가 앰퍼샌드 (&) "P" 하면 문자에 밑줄을 표시 "P" 단추 텍스트의 런타임 시 문자 앞에 속성을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="205ad-105">For example, if a button runs a procedure to print a form, and therefore its `Text` property is set to "Print," adding an ampersand (&) before the letter "P" causes the letter "P" to be underlined in the button text at run time.</span></span> <span data-ttu-id="205ad-106">ALT + P를 눌러 단추와 연결 된 명령을 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="205ad-106">The user can run the command associated with the button by pressing ALT+P.</span></span> <span data-ttu-id="205ad-107">포커스를 받을 수 있는 컨트롤에 대 한 액세스 키를 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="205ad-107">You cannot have an access key for a control that cannot receive focus.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="205ad-108">표시되는 대화 상자와 메뉴 명령은 활성 설정이나 버전에 따라 도움말에서 설명하는 것과 다를 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="205ad-108">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="205ad-109">설정을 변경하려면 **도구** 메뉴에서 **설정 가져오기 및 내보내기** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="205ad-109">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="205ad-110">자세한 내용은 [Visual Studio IDE 개인 설정](/visualstudio/ide/personalizing-the-visual-studio-ide)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="205ad-110">For more information, see [Personalize the Visual Studio IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).</span></span>  
  
### <a name="to-create-an-access-key-for-a-control"></a><span data-ttu-id="205ad-111">컨트롤에 대 한 액세스 키를 만들려면</span><span class="sxs-lookup"><span data-stu-id="205ad-111">To create an access key for a control</span></span>  
  
1.  <span data-ttu-id="205ad-112">에 **속성** 창에서 `Text` 속성 앰퍼샌드를 포함 하는 문자열 (&) 앞에 대 한 액세스 키가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="205ad-112">In the **Properties** window, set the `Text` property to a string that includes an ampersand (&) before the letter that will be the access key.</span></span> <span data-ttu-id="205ad-113">예를 들어, 입력을 설정 하려면 문자 "P" 액세스 키로 **인쇄 및** 모눈에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="205ad-113">For example, to set the letter "P" as the access key, type **&Print** into the grid.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="205ad-114">참고자료</span><span class="sxs-lookup"><span data-stu-id="205ad-114">See also</span></span>

- <xref:System.Windows.Forms.Button>
- [<span data-ttu-id="205ad-115">방법: Windows Forms 단추 클릭에 응답</span><span class="sxs-lookup"><span data-stu-id="205ad-115">How to: Respond to Windows Forms Button Clicks</span></span>](how-to-respond-to-windows-forms-button-clicks.md)
- [<span data-ttu-id="205ad-116">방법: Windows Forms 컨트롤에서 표시하는 텍스트 설정</span><span class="sxs-lookup"><span data-stu-id="205ad-116">How to: Set the Text Displayed by a Windows Forms Control</span></span>](how-to-set-the-text-displayed-by-a-windows-forms-control.md)
- [<span data-ttu-id="205ad-117">개별 Windows Forms 컨트롤 레이블 지정 및 바로 가기 제공</span><span class="sxs-lookup"><span data-stu-id="205ad-117">Labeling Individual Windows Forms Controls and Providing Shortcuts to Them</span></span>](labeling-individual-windows-forms-controls-and-providing-shortcuts-to-them.md)
