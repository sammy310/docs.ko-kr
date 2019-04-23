---
title: '방법: Windows Forms 컨트롤에 대한 선택키 만들기'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- controls [Windows Forms], access keys
- Button control [Windows Forms], access keys
- dialog box controls [Windows Forms], mnemonics
- access keys [Windows Forms], creating for controls
- mnemonics [Windows Forms], adding to dialog box controls
- mnemonics
- ampersand character in shortcut key
- Windows Forms controls, access keys
- examples [Windows Forms], controls
- Text property [Windows Forms], specifying access keys for controls
- keyboard shortcuts [Windows Forms], creating for controls
- access keys [Windows Forms], Windows Forms
- ALT key
ms.assetid: 4faa0991-28ec-4eca-91db-51dc2cd6a7ac
ms.openlocfilehash: e6c829553163359301bad2cd896fc43562ee8069
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59334460"
---
# <a name="how-to-create-access-keys-for-windows-forms-controls"></a><span data-ttu-id="b41e0-102">방법: Windows Forms 컨트롤에 대한 선택키 만들기</span><span class="sxs-lookup"><span data-stu-id="b41e0-102">How to: Create Access Keys for Windows Forms Controls</span></span>
<span data-ttu-id="b41e0-103">*선택키가* 은 메뉴, 메뉴 항목 또는 예: 단추 컨트롤의 레이블 텍스트에 밑줄이 그어진된 문자입니다.</span><span class="sxs-lookup"><span data-stu-id="b41e0-103">An *access key* is an underlined character in the text of a menu, menu item, or the label of a control such as a button.</span></span> <span data-ttu-id="b41e0-104">액세스 키가 있는 사용자 수 "단추를 클릭" 미리 정의 된 액세스 키를 사용 하 여 함께에서 ALT 키를 눌러.</span><span class="sxs-lookup"><span data-stu-id="b41e0-104">With an access key, the user can "click" a button by pressing the ALT key in combination with the predefined access key.</span></span> <span data-ttu-id="b41e0-105">예를 들어, 단추 폼을 인쇄 하는 프로시저를 실행 하는 경우 및 해당 `Text` 속성 "Print", "P" 문자로 하면 문자에는 런타임에 단추 텍스트에 밑줄이 표시 된 "P" 전에 앰퍼샌드를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="b41e0-105">For example, if a button runs a procedure to print a form, and therefore its `Text` property is set to "Print," adding an ampersand before the letter "P" causes the letter "P" to be underlined in the button text at run time.</span></span> <span data-ttu-id="b41e0-106">ALT + P를 눌러 단추와 연결 된 명령을 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b41e0-106">The user can run the command associated with the button by pressing ALT+P.</span></span> <span data-ttu-id="b41e0-107">포커스를 받을 수 있는 컨트롤에 대 한 액세스 키를 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="b41e0-107">You cannot have an access key for a control that cannot receive focus.</span></span>  
  
### <a name="to-create-an-access-key-for-a-control"></a><span data-ttu-id="b41e0-108">컨트롤에 대 한 액세스 키를 만들려면</span><span class="sxs-lookup"><span data-stu-id="b41e0-108">To create an access key for a control</span></span>  
  
1. <span data-ttu-id="b41e0-109">설정 된 `Text` 앰퍼샌드를 포함 하는 문자열 (&) 문자 바로 가기로 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="b41e0-109">Set the `Text` property to a string that includes an ampersand (&) before the letter that will be the shortcut.</span></span>  
  
    ```vb  
    ' Set the letter "P" as an access key.  
    Button1.Text = "&Print"  
    ```  
  
    ```csharp  
    // Set the letter "P" as an access key.  
    button1.Text = "&Print";  
    ```  
  
    ```cpp  
    // Set the letter "P" as an access key.  
    button1->Text = "&Print";  
    ```  
  
    > [!NOTE]
    >  <span data-ttu-id="b41e0-110">앰퍼샌드 캡션을 액세스 키를 만들지 않고를 넣으려면 두 앰퍼샌드 (& &).</span><span class="sxs-lookup"><span data-stu-id="b41e0-110">To include an ampersand in a caption without creating an access key, include two ampersands (&&).</span></span> <span data-ttu-id="b41e0-111">단일 앰퍼샌드 캡션의 나타나고 문자가 없는 밑줄이 표시 되 면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b41e0-111">A single ampersand is displayed in the caption and no characters are underlined.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b41e0-112">참고자료</span><span class="sxs-lookup"><span data-stu-id="b41e0-112">See also</span></span>

- <xref:System.Windows.Forms.Button>
- [<span data-ttu-id="b41e0-113">방법: Windows Forms 단추 클릭에 응답</span><span class="sxs-lookup"><span data-stu-id="b41e0-113">How to: Respond to Windows Forms Button Clicks</span></span>](how-to-respond-to-windows-forms-button-clicks.md)
- [<span data-ttu-id="b41e0-114">방법: 설정 하 여 표시 되는 텍스트는 Windows Forms 컨트롤</span><span class="sxs-lookup"><span data-stu-id="b41e0-114">How to: Set the Text Displayed by a Windows Forms Control</span></span>](how-to-set-the-text-displayed-by-a-windows-forms-control.md)
- [<span data-ttu-id="b41e0-115">개별 Windows Forms 컨트롤 레이블 지정 및 바로 가기 제공</span><span class="sxs-lookup"><span data-stu-id="b41e0-115">Labeling Individual Windows Forms Controls and Providing Shortcuts to Them</span></span>](labeling-individual-windows-forms-controls-and-providing-shortcuts-to-them.md)
