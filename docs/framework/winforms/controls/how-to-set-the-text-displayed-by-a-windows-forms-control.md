---
title: 컨트롤에 표시 되는 텍스트 설정
description: Windows Forms 컨트롤에 표시 되는 텍스트를 설정 하는 방법을 알아봅니다. 텍스트 속성을 사용 하 여 텍스트를 설정 하거나 반환 하거나 Font 속성을 사용 하 여 글꼴을 변경 합니다.
ms.date: 08/20/2019
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
ms.openlocfilehash: 35bae5830bfee8ab91f7b6c7b9dcc6d6b8db00ca
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/01/2020
ms.locfileid: "85622850"
---
# <a name="how-to-set-the-text-displayed-by-a-windows-forms-control"></a><span data-ttu-id="fe614-104">방법: Windows Forms 컨트롤에 표시 되는 텍스트 설정</span><span class="sxs-lookup"><span data-stu-id="fe614-104">How to: Set the text displayed by a Windows Forms control</span></span>

<span data-ttu-id="fe614-105">Windows Forms 컨트롤은 일반적으로 컨트롤의 기본 함수와 관련 된 일부 텍스트를 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="fe614-105">Windows Forms controls usually display some text that's related to the primary function of the control.</span></span> <span data-ttu-id="fe614-106">예를 들어, <xref:System.Windows.Forms.Button> 컨트롤은 일반적으로 단추를 클릭 하는 경우 수행할 동작을 나타내는 캡션을 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="fe614-106">For example, a <xref:System.Windows.Forms.Button> control usually displays a caption indicating what action will be performed if the button is clicked.</span></span> <span data-ttu-id="fe614-107">모든 컨트롤에 대해 <xref:System.Windows.Forms.Control.Text%2A> 속성을 사용하여 텍스트를 설정하거나 반환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fe614-107">For all controls, you can set or return the text by using the <xref:System.Windows.Forms.Control.Text%2A> property.</span></span> <span data-ttu-id="fe614-108"><xref:System.Windows.Forms.Control.Font%2A> 속성을 사용하여 글꼴을 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fe614-108">You can change the font by using the <xref:System.Windows.Forms.Control.Font%2A> property.</span></span>

<span data-ttu-id="fe614-109">[디자이너](#designer)를 사용 하 여 텍스트를 설정할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fe614-109">You can also set the text by using the [designer](#designer).</span></span>

## <a name="programmatic"></a><span data-ttu-id="fe614-110">프로그래밍 방식</span><span class="sxs-lookup"><span data-stu-id="fe614-110">Programmatic</span></span>

1. <span data-ttu-id="fe614-111"><xref:System.Windows.Forms.Control.Text%2A> 속성을 문자열로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="fe614-111">Set the <xref:System.Windows.Forms.Control.Text%2A> property to a string.</span></span>

   <span data-ttu-id="fe614-112">밑줄이 그어진 액세스 키를 만들기 위해에는 선택 키가 될 문자 앞에 앰퍼샌드 (&)가 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="fe614-112">To create an underlined access key, includes an ampersand (&) before the letter that will be the access key.</span></span>

2. <span data-ttu-id="fe614-113"><xref:System.Windows.Forms.Control.Font%2A> 속성을 <xref:System.Drawing.Font> 형식의 개체로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="fe614-113">Set the <xref:System.Windows.Forms.Control.Font%2A> property to an object of type <xref:System.Drawing.Font>.</span></span>

    ```vb
    Button1.Text = "Click here to save changes"
    Button1.Font = New Font("Arial", 10, FontStyle.Bold, GraphicsUnit.Point)
    ```

    ```csharp
    button1.Text = "Click here to save changes";
    button1.Font = new Font("Arial", 10, FontStyle.Bold, GraphicsUnit.Point);
    ```

    ```cpp
    button1->Text = "Click here to save changes";
    button1->Font = new System::Drawing::Font("Arial", 10, FontStyle::Bold, GraphicsUnit::Point);
    ```

    > [!NOTE]
    > <span data-ttu-id="fe614-114">이스케이프 문자를 사용하여 일반적으로 다르게 해석하는 메뉴 항목과 같은 사용자 인터페이스 요소에 특수 문자를 표시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fe614-114">You can use an escape character to display a special character in user-interface elements that would normally interpret them differently, such as menu items.</span></span> <span data-ttu-id="fe614-115">예를 들어 다음 코드 줄은 메뉴 항목의 텍스트를 "& 이제 완전히 다른 항목을 읽도록" 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="fe614-115">For example, the following line of code sets the menu item's text to read "& Now For Something Completely Different":</span></span>

    ```vb
    MPMenuItem.Text = "&& Now For Something Completely Different"
    ```

    ```csharp
    mpMenuItem.Text = "&& Now For Something Completely Different";
    ```

    ```cpp
    mpMenuItem->Text = "&& Now For Something Completely Different";
    ```

## <a name="designer"></a><span data-ttu-id="fe614-116">디자이너</span><span class="sxs-lookup"><span data-stu-id="fe614-116">Designer</span></span>

1. <span data-ttu-id="fe614-117">Visual Studio의 **속성** 창에서 컨트롤의 **Text** 속성을 적절 한 문자열로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="fe614-117">In the **Properties** window in Visual Studio, set the **Text** property of the control to an appropriate string.</span></span>

   <span data-ttu-id="fe614-118">밑줄이 있는 바로 가기 키를 만들려면 바로 가기 키가 될 문자 앞에 앰퍼샌드 (&)를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="fe614-118">To create an underlined shortcut key, includes an ampersand (&) before the letter that will be the shortcut key.</span></span>

2. <span data-ttu-id="fe614-119">**속성** 창의 Font 속성 옆에 있는 줄임표 단추 ( ![ Visual Studio 속성 창)에서 줄임표 단추 (...)를 선택 ](./media/visual-studio-ellipsis-button.png) 합니다. **Font**</span><span class="sxs-lookup"><span data-stu-id="fe614-119">In the **Properties** window, select the ellipsis button (![Ellipsis button (...) in the Properties window of Visual Studio](./media/visual-studio-ellipsis-button.png)) next to the **Font** property.</span></span>

   <span data-ttu-id="fe614-120">표준 글꼴 대화 상자에서 글꼴, 글꼴 스타일, 크기, 효과 (취소선 또는 밑줄 등) 및 원하는 스크립트를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="fe614-120">In the standard font dialog box, select the font, font style, size, effects (such as strikeout or underline), and script that you want.</span></span>

## <a name="see-also"></a><span data-ttu-id="fe614-121">참고 항목</span><span class="sxs-lookup"><span data-stu-id="fe614-121">See also</span></span>

- <xref:System.Windows.Forms.Control.Text%2A?displayProperty=nameWithType>
- [<span data-ttu-id="fe614-122">방법: Windows Forms 컨트롤에 대한 선택키 만들기</span><span class="sxs-lookup"><span data-stu-id="fe614-122">How to: Create Access Keys for Windows Forms Controls</span></span>](how-to-create-access-keys-for-windows-forms-controls.md)
- [<span data-ttu-id="fe614-123">방법: Windows Forms 단추 클릭에 응답</span><span class="sxs-lookup"><span data-stu-id="fe614-123">How to: Respond to Windows Forms Button Clicks</span></span>](how-to-respond-to-windows-forms-button-clicks.md)
