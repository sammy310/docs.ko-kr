---
title: '방법: 디자인 타임에 ElementHost 컨트롤 복사하여 붙여넣기'
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Forms, content copying and pasting
- interoperability [WPF]
- ElementHost control [Windows Forms], copying and pasting at design time
- WPF user control [Windows Forms], hosting in Windows Forms
ms.assetid: e570375d-2a68-44ba-b4f7-c781af2d20e8
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: 3d1887eb1161f714962c2c26d6fe618749b26c0f
ms.sourcegitcommit: 5a28f8eb071fcc09b045b0c4ae4b96898673192e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/31/2019
ms.locfileid: "73197485"
---
# <a name="how-to-copy-and-paste-an-elementhost-control"></a><span data-ttu-id="d85d9-102">방법: ElementHost 컨트롤 복사 및 붙여넣기</span><span class="sxs-lookup"><span data-stu-id="d85d9-102">How to: Copy and paste an ElementHost control</span></span>

<span data-ttu-id="d85d9-103">이 절차에서는 Visual Studio에서 Windows Form에 Windows Presentation Foundation (WPF) 컨트롤을 복사 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="d85d9-103">This procedure shows you how to copy a Windows Presentation Foundation (WPF) control on a Windows Form in Visual Studio.</span></span>

1. <span data-ttu-id="d85d9-104">Visual Studio에서 Windows Forms 프로젝트에 새 WPF <xref:System.Windows.Controls.UserControl>를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="d85d9-104">In Visual Studio, add a new WPF <xref:System.Windows.Controls.UserControl> to a Windows Forms project.</span></span> <span data-ttu-id="d85d9-105">컨트롤 형식의 기본 이름인 `UserControl1.xaml`을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="d85d9-105">Use the default name for the control type, `UserControl1.xaml`.</span></span> <span data-ttu-id="d85d9-106">자세한 내용은 [연습: 디자인 타임에 Windows Forms에서 새 WPF 콘텐츠 만들기](walkthrough-creating-new-wpf-content-on-windows-forms-at-design-time.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="d85d9-106">For more information, see [Walkthrough: Creating New WPF Content on Windows Forms at Design Time](walkthrough-creating-new-wpf-content-on-windows-forms-at-design-time.md).</span></span>

2. <span data-ttu-id="d85d9-107">**속성** 창에서 <xref:System.Windows.FrameworkElement.Width%2A> 값을 설정 하 고 `UserControl1`의 <xref:System.Windows.FrameworkElement.Height%2A> 속성을 **200**로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="d85d9-107">In the **Properties** window, set the value of the <xref:System.Windows.FrameworkElement.Width%2A> and <xref:System.Windows.FrameworkElement.Height%2A> properties of `UserControl1` to **200**.</span></span>

3. <span data-ttu-id="d85d9-108"><xref:System.Windows.Controls.Control.Background%2A> 속성의 값을 **Blue**로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="d85d9-108">Set the value of the <xref:System.Windows.Controls.Control.Background%2A> property to **Blue**.</span></span>

4. <span data-ttu-id="d85d9-109">프로젝트를 빌드합니다.</span><span class="sxs-lookup"><span data-stu-id="d85d9-109">Build the project.</span></span>

5. <span data-ttu-id="d85d9-110">Windows Forms 디자이너에서 `Form1`을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="d85d9-110">Open `Form1` in the Windows Forms Designer.</span></span>

6. <span data-ttu-id="d85d9-111">**도구 상자**에서 `UserControl1`의 인스턴스를 폼으로 끌어 옵니다.</span><span class="sxs-lookup"><span data-stu-id="d85d9-111">From the **Toolbox**, drag an instance of `UserControl1` onto the form.</span></span>

   <span data-ttu-id="d85d9-112">`UserControl1` 인스턴스가 `elementHost1`이라는 새 <xref:System.Windows.Forms.Integration.ElementHost> 컨트롤에서 호스트됩니다.</span><span class="sxs-lookup"><span data-stu-id="d85d9-112">An instance of `UserControl1` is hosted in a new <xref:System.Windows.Forms.Integration.ElementHost> control named `elementHost1`.</span></span>

7. <span data-ttu-id="d85d9-113">`elementHost1` 선택 된 상태에서 **ctrl**+**C** 키를 눌러 클립보드로 복사 합니다.</span><span class="sxs-lookup"><span data-stu-id="d85d9-113">With `elementHost1` selected, press **Ctrl**+**C** to copy it to the clipboard.</span></span>

8. <span data-ttu-id="d85d9-114">**Ctrl**+**V** 를 눌러 복사 된 컨트롤을 폼에 붙여넣습니다.</span><span class="sxs-lookup"><span data-stu-id="d85d9-114">Press **Ctrl**+**V** to paste the copied control onto the form.</span></span>

   <span data-ttu-id="d85d9-115">`elementHost2` 이라는 새 <xref:System.Windows.Forms.Integration.ElementHost> 컨트롤이 폼에 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="d85d9-115">A new <xref:System.Windows.Forms.Integration.ElementHost> control named `elementHost2` is created on the form.</span></span>

## <a name="see-also"></a><span data-ttu-id="d85d9-116">참조</span><span class="sxs-lookup"><span data-stu-id="d85d9-116">See also</span></span>

- <xref:System.Windows.Forms.Integration.ElementHost>
- <xref:System.Windows.Forms.Integration.WindowsFormsHost>
- [<span data-ttu-id="d85d9-117">마이그레이션 및 상호 운용성</span><span class="sxs-lookup"><span data-stu-id="d85d9-117">Migration and Interoperability</span></span>](../../wpf/advanced/migration-and-interoperability.md)
- [<span data-ttu-id="d85d9-118">WPF 컨트롤 사용</span><span class="sxs-lookup"><span data-stu-id="d85d9-118">Using WPF Controls</span></span>](using-wpf-controls.md)
- [<span data-ttu-id="d85d9-119">Visual Studio에서 XAML 디자인</span><span class="sxs-lookup"><span data-stu-id="d85d9-119">Design XAML in Visual Studio</span></span>](/visualstudio/xaml-tools/designing-xaml-in-visual-studio)
