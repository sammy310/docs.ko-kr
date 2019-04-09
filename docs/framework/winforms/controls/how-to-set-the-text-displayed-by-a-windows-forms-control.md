---
title: '방법: Windows Forms 컨트롤에서 표시하는 텍스트 설정'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- Windows Forms, captions
- Button control [Windows Forms], button text
- StdFont object and CommandButton caption
- captions [Windows Forms], Windows Forms controls
- Text property [Windows Forms], Windows Forms control
- Button control [Windows Forms], text display
- labels [Windows Forms], adding to CommandButton control
- buttons [Windows Forms], text
- captions [Windows Forms], setting
- text
- examples [Windows Forms], controls
- text [Windows Forms], Windows Forms controls
- controls [Windows Forms], captions
- forms [Windows Forms], captions
ms.assetid: 36b95bff-8780-479d-b86a-f1a0673653aa
ms.openlocfilehash: e9bf2077f10648dbe3ebf214bbbf9546cbb398c3
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59096188"
---
# <a name="how-to-set-the-text-displayed-by-a-windows-forms-control"></a><span data-ttu-id="10dbe-102">방법: Windows Forms 컨트롤에서 표시하는 텍스트 설정</span><span class="sxs-lookup"><span data-stu-id="10dbe-102">How to: Set the Text Displayed by a Windows Forms Control</span></span>
<span data-ttu-id="10dbe-103">Windows Forms 컨트롤은 일반적으로 컨트롤의 기본 기능과 관련된 일부 텍스트를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="10dbe-103">Windows Forms controls usually display some text that is related to the primary function of the control.</span></span> <span data-ttu-id="10dbe-104">예를 들어 <xref:System.Windows.Forms.Button> 컨트롤은 일반적으로 단추를 클릭할 때 수행되는 동작을 나타내는 캡션을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="10dbe-104">For example, a <xref:System.Windows.Forms.Button> control usually displays a caption indicating what action will be performed when the button is clicked.</span></span> <span data-ttu-id="10dbe-105">모든 컨트롤에 대해 <xref:System.Windows.Forms.Control.Text%2A> 속성을 사용하여 텍스트를 설정하거나 반환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="10dbe-105">For all controls, you can set or return the text by using the <xref:System.Windows.Forms.Control.Text%2A> property.</span></span> <span data-ttu-id="10dbe-106"><xref:System.Windows.Forms.Control.Font%2A> 속성을 사용하여 글꼴을 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="10dbe-106">You can change the font by using the <xref:System.Windows.Forms.Control.Font%2A> property.</span></span> <span data-ttu-id="10dbe-107">디자이너를 사용하여 텍스트를 설정할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="10dbe-107">You can also set the text using the designer.</span></span>  <span data-ttu-id="10dbe-108">또한 참조 [방법: Windows Forms 디자이너를 사용 하 여 컨트롤에 대 한 액세스 키를 만듭니다](how-to-create-access-keys-for-windows-forms-controls-using-the-designer.md), [방법: 설정 하 여 표시 되는 텍스트는 Windows Forms 디자이너를 사용 하 여 컨트롤](how-to-set-the-text-displayed-by-a-windows-forms-control-using-the-designer.md), [방법: 설정 하 여 표시 되는 이미지를 Windows Forms 디자이너를 사용 하 여 컨트롤](how-to-set-the-image-displayed-by-a-windows-forms-control-using-the-designer.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="10dbe-108">Also see [How to: Create Access Keys for Windows Forms Controls Using the Designer](how-to-create-access-keys-for-windows-forms-controls-using-the-designer.md), [How to: Set the Text Displayed by a Windows Forms Control Using the Designer](how-to-set-the-text-displayed-by-a-windows-forms-control-using-the-designer.md), [How to: Set the Image Displayed by a Windows Forms Control Using the Designer](how-to-set-the-image-displayed-by-a-windows-forms-control-using-the-designer.md).</span></span>  
  
### <a name="to-set-the-text-displayed-by-a-control-programmatically"></a><span data-ttu-id="10dbe-109">프로그래밍 방식으로 컨트롤에 표시되는 텍스트를 설정하려면</span><span class="sxs-lookup"><span data-stu-id="10dbe-109">To set the text displayed by a control programmatically</span></span>  
  
1.  <span data-ttu-id="10dbe-110"><xref:System.Windows.Forms.Control.Text%2A> 속성을 문자열로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="10dbe-110">Set the <xref:System.Windows.Forms.Control.Text%2A> property to a string.</span></span>  
  
     <span data-ttu-id="10dbe-111">밑줄이 그어진된 액세스 키를 만들려면 앰퍼샌드가 포함 (&) 앞에 대 한 액세스 키가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="10dbe-111">To create an underlined access key, includes an ampersand (&) before the letter that will be the access key.</span></span>  
  
2.  <span data-ttu-id="10dbe-112"><xref:System.Windows.Forms.Control.Font%2A> 속성을 <xref:System.Drawing.Font> 형식의 개체로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="10dbe-112">Set the <xref:System.Windows.Forms.Control.Font%2A> property to an object of type <xref:System.Drawing.Font>.</span></span>  
  
    ```vb  
    Button1.Text = "Click here to save changes"  
    Button1.Font = New Font("Arial", 10, FontStyle.Bold, GraphicsUnit.Point)  
    ```  
  
    ```csharp  
    button1.Text = "Click here to save changes";  
    button1.Font = new Font("Arial", 10, FontStyle.Bold,  
       GraphicsUnit.Point);  
    ```  
  
    ```cpp  
    button1->Text = "Click here to save changes";  
    button1->Font = new System::Drawing::Font("Arial",  
       10, FontStyle::Bold, GraphicsUnit::Point);  
    ```  
  
    > [!NOTE]
    >  <span data-ttu-id="10dbe-113">이스케이프 문자를 사용하여 일반적으로 다르게 해석하는 메뉴 항목과 같은 사용자 인터페이스 요소에 특수 문자를 표시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="10dbe-113">You can use an escape character to display a special character in user-interface elements that would normally interpret them differently, such as menu items.</span></span> <span data-ttu-id="10dbe-114">다음 코드 줄에서 메뉴 항목의 텍스트를 읽을 설정 하는 예를 들어 "& Now For Something 완전히 다른":</span><span class="sxs-lookup"><span data-stu-id="10dbe-114">For example, the following line of code sets the menu item's text to read "& Now For Something Completely Different":</span></span>  
  
    ```vb  
    MPMenuItem.Text = "&& Now For Something Completely Different"  
    ```  
  
    ```csharp  
    mpMenuItem.Text = "&& Now For Something Completely Different";  
    ```  
  
    ```cpp  
    mpMenuItem->Text = "&& Now For Something Completely Different";  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="10dbe-115">참고자료</span><span class="sxs-lookup"><span data-stu-id="10dbe-115">See also</span></span>

- <xref:System.Windows.Forms.Control.Text%2A?displayProperty=nameWithType>
- [<span data-ttu-id="10dbe-116">방법: Windows Forms 컨트롤에 대한 선택키 만들기</span><span class="sxs-lookup"><span data-stu-id="10dbe-116">How to: Create Access Keys for Windows Forms Controls</span></span>](how-to-create-access-keys-for-windows-forms-controls.md)
- [<span data-ttu-id="10dbe-117">방법: Windows Forms 단추 클릭에 응답</span><span class="sxs-lookup"><span data-stu-id="10dbe-117">How to: Respond to Windows Forms Button Clicks</span></span>](how-to-respond-to-windows-forms-button-clicks.md)
