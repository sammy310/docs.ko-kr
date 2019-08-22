---
title: '방법: 디자인 타임에 ElementHost 컨트롤 복사 및 붙여넣기'
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
ms.openlocfilehash: dfe5244e0c5b61fdf6d940dd16d8c280f013b12c
ms.sourcegitcommit: cdf67135a98a5a51913dacddb58e004a3c867802
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/21/2019
ms.locfileid: "69666175"
---
# <a name="how-to-copy-and-paste-an-elementhost-control"></a><span data-ttu-id="0d8e7-102">방법: ElementHost 컨트롤 복사 및 붙여넣기</span><span class="sxs-lookup"><span data-stu-id="0d8e7-102">How to: Copy and paste an ElementHost control</span></span>

<span data-ttu-id="0d8e7-103">이 절차에서는 Visual Studio에서 Windows Form에 Windows Presentation Foundation (WPF) 컨트롤을 복사 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="0d8e7-103">This procedure shows you how to copy a Windows Presentation Foundation (WPF) control on a Windows Form in Visual Studio.</span></span>

1. <span data-ttu-id="0d8e7-104">Visual Studio에서 Windows Forms 프로젝트에 새 WPF <xref:System.Windows.Controls.UserControl> 를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="0d8e7-104">In Visual Studio, add a new WPF <xref:System.Windows.Controls.UserControl> to a Windows Forms project.</span></span> <span data-ttu-id="0d8e7-105">컨트롤 형식의 기본 이름인 `UserControl1.xaml`을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="0d8e7-105">Use the default name for the control type, `UserControl1.xaml`.</span></span> <span data-ttu-id="0d8e7-106">자세한 내용은 [연습: 디자인 타임](walkthrough-creating-new-wpf-content-on-windows-forms-at-design-time.md)에 WINDOWS FORMS에서 새 WPF 콘텐츠 만들기</span><span class="sxs-lookup"><span data-stu-id="0d8e7-106">For more information, see [Walkthrough: Creating New WPF Content on Windows Forms at Design Time](walkthrough-creating-new-wpf-content-on-windows-forms-at-design-time.md).</span></span>

2. <span data-ttu-id="0d8e7-107">**속성** 창 <xref:System.Windows.FrameworkElement.Width%2A> 에서의 <xref:System.Windows.FrameworkElement.Height%2A> 및`UserControl1` 속성 값을 **200**로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="0d8e7-107">In the **Properties** window, set the value of the <xref:System.Windows.FrameworkElement.Width%2A> and <xref:System.Windows.FrameworkElement.Height%2A> properties of `UserControl1` to **200**.</span></span>

3. <span data-ttu-id="0d8e7-108"><xref:System.Windows.Controls.Control.Background%2A> 속성의 값을 **Blue**로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="0d8e7-108">Set the value of the <xref:System.Windows.Controls.Control.Background%2A> property to **Blue**.</span></span>

4. <span data-ttu-id="0d8e7-109">프로젝트를 빌드합니다.</span><span class="sxs-lookup"><span data-stu-id="0d8e7-109">Build the project.</span></span>

5. <span data-ttu-id="0d8e7-110">Windows Forms 디자이너에서 `Form1`을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="0d8e7-110">Open `Form1` in the Windows Forms Designer.</span></span>

6. <span data-ttu-id="0d8e7-111">**도구 상자**에서의 `UserControl1` 인스턴스를 폼으로 끌어 옵니다.</span><span class="sxs-lookup"><span data-stu-id="0d8e7-111">From the **Toolbox**, drag an instance of `UserControl1` onto the form.</span></span>

   <span data-ttu-id="0d8e7-112">`UserControl1` 인스턴스가 `elementHost1`이라는 새 <xref:System.Windows.Forms.Integration.ElementHost> 컨트롤에서 호스트됩니다.</span><span class="sxs-lookup"><span data-stu-id="0d8e7-112">An instance of `UserControl1` is hosted in a new <xref:System.Windows.Forms.Integration.ElementHost> control named `elementHost1`.</span></span>

7. <span data-ttu-id="0d8e7-113">선택 `elementHost1` 된 상태에서 **Ctrl**+**C** 를 눌러 클립보드로 복사 합니다.</span><span class="sxs-lookup"><span data-stu-id="0d8e7-113">With `elementHost1` selected, press **Ctrl**+**C** to copy it to the clipboard.</span></span>

8. <span data-ttu-id="0d8e7-114">**Ctrl**+**V** 를 눌러 복사 된 컨트롤을 폼에 붙여넣습니다.</span><span class="sxs-lookup"><span data-stu-id="0d8e7-114">Press **Ctrl**+**V** to paste the copied control onto the form.</span></span>

   <span data-ttu-id="0d8e7-115"><xref:System.Windows.Forms.Integration.ElementHost> 이라는`elementHost2` 새 컨트롤이 폼에 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="0d8e7-115">A new <xref:System.Windows.Forms.Integration.ElementHost> control named `elementHost2` is created on the form.</span></span>

## <a name="see-also"></a><span data-ttu-id="0d8e7-116">참고자료</span><span class="sxs-lookup"><span data-stu-id="0d8e7-116">See also</span></span>

- <xref:System.Windows.Forms.Integration.ElementHost>
- <xref:System.Windows.Forms.Integration.WindowsFormsHost>
- [<span data-ttu-id="0d8e7-117">마이그레이션 및 상호 운용성</span><span class="sxs-lookup"><span data-stu-id="0d8e7-117">Migration and Interoperability</span></span>](../../wpf/advanced/migration-and-interoperability.md)
- [<span data-ttu-id="0d8e7-118">WPF 컨트롤 사용</span><span class="sxs-lookup"><span data-stu-id="0d8e7-118">Using WPF Controls</span></span>](using-wpf-controls.md)
- [<span data-ttu-id="0d8e7-119">Visual Studio에서 XAML 디자인</span><span class="sxs-lookup"><span data-stu-id="0d8e7-119">Design XAML in Visual Studio</span></span>](/visualstudio/designers/designing-xaml-in-visual-studio)
