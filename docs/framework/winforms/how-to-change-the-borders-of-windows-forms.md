---
title: 폼 테두리 변경
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- Windows Forms, changing the borders
ms.assetid: b3d5fa56-80c6-4b10-b505-f9672307ed55
ms.openlocfilehash: 2c8eb25b44c7406e4312f432f2d69524346f94d6
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/24/2020
ms.locfileid: "76739572"
---
# <a name="how-to-change-the-borders-of-windows-forms"></a><span data-ttu-id="b8b1c-102">방법: Windows Forms의 테두리 변경</span><span class="sxs-lookup"><span data-stu-id="b8b1c-102">How to: Change the Borders of Windows Forms</span></span>
<span data-ttu-id="b8b1c-103">Windows Forms의 모양과 동작을 결정할 때 선택할 수 있는 여러 테두리 스타일이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b8b1c-103">You have several border styles to choose from when you are determining the appearance and behavior of your Windows Forms.</span></span> <span data-ttu-id="b8b1c-104"><xref:System.Windows.Forms.Form.FormBorderStyle%2A> 속성을 변경하여 폼의 크기 조정 동작을 제어할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b8b1c-104">By changing the <xref:System.Windows.Forms.Form.FormBorderStyle%2A> property, you can control the resizing behavior of the form.</span></span> <span data-ttu-id="b8b1c-105">또한 <xref:System.Windows.Forms.Form.FormBorderStyle%2A>을 설정하면 캡션 표시줄 표시 방식 및 표시되는 단추에 영향을 줍니다.</span><span class="sxs-lookup"><span data-stu-id="b8b1c-105">In addition, setting the <xref:System.Windows.Forms.Form.FormBorderStyle%2A> affects how the caption bar is displayed as well as what buttons might appear on it.</span></span> <span data-ttu-id="b8b1c-106">자세한 내용은 <xref:System.Windows.Forms.FormBorderStyle>을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="b8b1c-106">For more information, see <xref:System.Windows.Forms.FormBorderStyle>.</span></span>  
  
 <span data-ttu-id="b8b1c-107">Visual Studio에서는 이 작업이 광범위하게 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="b8b1c-107">There is extensive support for this task in Visual Studio.</span></span>  
  
 <span data-ttu-id="b8b1c-108">[방법: 디자이너를 사용 하 여 Windows Forms 테두리 변경](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/yettzh3e(v=vs.100))도 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="b8b1c-108">See also [How to: Change the Borders of Windows Forms Using the Designer](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/yettzh3e(v=vs.100)).</span></span>  
  
### <a name="to-set-the-border-style-of-windows-forms-programmatically"></a><span data-ttu-id="b8b1c-109">Windows Forms의 테두리 스타일을 프로그래밍 방식으로 설정하려면</span><span class="sxs-lookup"><span data-stu-id="b8b1c-109">To set the border style of Windows Forms programmatically</span></span>  
  
- <span data-ttu-id="b8b1c-110"><xref:System.Windows.Forms.Form.FormBorderStyle%2A> 속성을 원하는 스타일로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="b8b1c-110">Set the <xref:System.Windows.Forms.Form.FormBorderStyle%2A> property to the style you want.</span></span> <span data-ttu-id="b8b1c-111">다음 코드 예제에서는 `DlgBx1` 폼의 테두리 스타일을 <xref:System.Windows.Forms.FormBorderStyle.FixedDialog>로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="b8b1c-111">The following code example sets the border style of form `DlgBx1` to <xref:System.Windows.Forms.FormBorderStyle.FixedDialog>.</span></span>  
  
    ```vb  
    DlgBx1.FormBorderStyle = System.Windows.Forms.FormBorderStyle.FixedDialog  
    ```  
  
    ```csharp  
    DlgBx1.FormBorderStyle = System.Windows.Forms.FormBorderStyle.FixedDialog;  
    ```  
  
    ```cpp  
    DlgBx1->FormBorderStyle =  
       System::Windows::Forms::FormBorderStyle::FixedDialog;  
    ```  
  
     <span data-ttu-id="b8b1c-112">또한 [방법: 디자인 타임에 대화 상자 만들기를](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/55cz5x2c(v=vs.100))참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="b8b1c-112">Also see [How to: Create Dialog Boxes at Design Time](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/55cz5x2c(v=vs.100)).</span></span>  
  
     <span data-ttu-id="b8b1c-113">또한 선택적 **최소화** 및 **최대화** 단추를 제공 하는 폼에 대 한 테두리 스타일을 선택한 경우 이러한 단추 중 하나 또는 둘 다를 사용할지 여부를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b8b1c-113">Additionally, if you have chosen a border style for the form that provides optional **Minimize** and **Maximize** buttons, you can specify whether you want either or both of these buttons to be functional.</span></span> <span data-ttu-id="b8b1c-114">이러한 단추는 사용자 환경을 긴밀히 제어하려는 경우에 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="b8b1c-114">These buttons are useful when you want to closely control the user experience.</span></span> <span data-ttu-id="b8b1c-115">**최소화** 및 **최대화** 단추는 기본적으로 사용 하도록 설정 되어 있으며 **속성** 창을 통해 해당 기능을 조작할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b8b1c-115">The **Minimize** and **Maximize** buttons are enabled by default, and their functionality is manipulated through the **Properties** window.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b8b1c-116">참고 항목</span><span class="sxs-lookup"><span data-stu-id="b8b1c-116">See also</span></span>

- <xref:System.Windows.Forms.FormBorderStyle>
- <xref:System.Windows.Forms.FormBorderStyle.FixedDialog>
- [<span data-ttu-id="b8b1c-117">Windows Forms 시작</span><span class="sxs-lookup"><span data-stu-id="b8b1c-117">Getting Started with Windows Forms</span></span>](getting-started-with-windows-forms.md)
