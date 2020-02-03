---
title: 컨트롤에 대 한 액세스 키 만들기
ms.date: 08/20/2019
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
ms.openlocfilehash: 7f6b0a5838cacfc1189fba819a54b3423d567ea0
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/24/2020
ms.locfileid: "76731164"
---
# <a name="how-to-create-access-keys-for-windows-forms-controls"></a><span data-ttu-id="2f04d-102">방법: Windows Forms 컨트롤에 대 한 선택 키 만들기</span><span class="sxs-lookup"><span data-stu-id="2f04d-102">How to: Create access keys for Windows Forms controls</span></span>

<span data-ttu-id="2f04d-103">*선택 키는* 메뉴, 메뉴 항목 또는 단추와 같은 컨트롤의 레이블 텍스트에서 밑줄 친 문자입니다.</span><span class="sxs-lookup"><span data-stu-id="2f04d-103">An *access key* is an underlined character in the text of a menu, menu item, or the label of a control such as a button.</span></span> <span data-ttu-id="2f04d-104">사용자는 액세스 키를 사용 하 여 미리 정의 된 액세스 키와 함께 Alt 키를 눌러 단추를 "클릭" 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2f04d-104">With an access key, the user can "click" a button by pressing the Alt key in combination with the predefined access key.</span></span> <span data-ttu-id="2f04d-105">예를 들어 단추가 폼을 인쇄 하는 프로시저를 실행 하는 경우 해당 `Text` 속성이 "Print"로 설정 되 면 문자 "P" 앞에 앰퍼샌드를 추가 하면 런타임에 단추 텍스트에서 문자 "P"에 밑줄이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2f04d-105">For example, if a button runs a procedure to print a form, and therefore its `Text` property is set to "Print," adding an ampersand before the letter "P" causes the letter "P" to be underlined in the button text at run time.</span></span> <span data-ttu-id="2f04d-106">사용자는 Alt + P를 눌러 단추와 연결 된 명령을 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2f04d-106">The user can run the command associated with the button by pressing Alt+P.</span></span>

<span data-ttu-id="2f04d-107">포커스를 받을 수 없는 컨트롤에는 액세스 키를 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="2f04d-107">Controls that cannot receive focus can't have access keys.</span></span>

## <a name="programmatic"></a><span data-ttu-id="2f04d-108">프로그래밍 방식</span><span class="sxs-lookup"><span data-stu-id="2f04d-108">Programmatic</span></span>

<span data-ttu-id="2f04d-109">`Text` 속성을 바로 가기로 사용할 문자 앞에 앰퍼샌드 (&)가 포함 된 문자열로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="2f04d-109">Set the `Text` property to a string that includes an ampersand (&) before the letter that will be the shortcut.</span></span>

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
> <span data-ttu-id="2f04d-110">선택 키를 만들지 않고 캡션에 앰퍼샌드를 사용 하려면 두 개의 앰퍼샌드 (& &)를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="2f04d-110">To use an ampersand in a caption without creating an access key, include two ampersands (&&).</span></span> <span data-ttu-id="2f04d-111">하나의 앰퍼샌드는 캡션에 표시 되 고 문자에는 밑줄이 표시 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="2f04d-111">A single ampersand is displayed in the caption and no characters are underlined.</span></span>

## <a name="designer"></a><span data-ttu-id="2f04d-112">디자이너</span><span class="sxs-lookup"><span data-stu-id="2f04d-112">Designer</span></span>

<span data-ttu-id="2f04d-113">Visual Studio의 **속성** 창에서 **텍스트** 속성을 선택 키가 될 문자 앞에 앰퍼샌드 (' & ')가 포함 된 문자열로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="2f04d-113">In the **Properties** window of Visual Studio, set the **Text** property to a string that includes an ampersand ('&') before the letter that will be the access key.</span></span> <span data-ttu-id="2f04d-114">예를 들어 "P" 문자를 선택 키로 설정 하려면 **& 인쇄**를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="2f04d-114">For example, to set the letter "P" as the access key, enter **&Print**.</span></span>

## <a name="see-also"></a><span data-ttu-id="2f04d-115">참고 항목</span><span class="sxs-lookup"><span data-stu-id="2f04d-115">See also</span></span>

- <xref:System.Windows.Forms.Button>
- [<span data-ttu-id="2f04d-116">방법: Windows Forms 단추 클릭에 응답</span><span class="sxs-lookup"><span data-stu-id="2f04d-116">How to: Respond to Windows Forms Button Clicks</span></span>](how-to-respond-to-windows-forms-button-clicks.md)
- [<span data-ttu-id="2f04d-117">방법: Windows Forms 컨트롤에서 표시하는 텍스트 설정</span><span class="sxs-lookup"><span data-stu-id="2f04d-117">How to: Set the Text Displayed by a Windows Forms Control</span></span>](how-to-set-the-text-displayed-by-a-windows-forms-control.md)
- [<span data-ttu-id="2f04d-118">개별 Windows Forms 컨트롤 레이블 지정 및 바로 가기 제공</span><span class="sxs-lookup"><span data-stu-id="2f04d-118">Labeling Individual Windows Forms Controls and Providing Shortcuts to Them</span></span>](labeling-individual-windows-forms-controls-and-providing-shortcuts-to-them.md)
