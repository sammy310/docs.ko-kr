---
title: '방법: 디자인 타임에 ElementHost 컨트롤 복사 및 붙여넣기'
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Forms, content copying and pasting
- interoperability [WPF]
- ElementHost control [Windows Forms], copying and pasting at design time
- WPF user control [Windows Forms], hosting in Windows Forms
ms.assetid: e570375d-2a68-44ba-b4f7-c781af2d20e8
ms.openlocfilehash: 0f3367deaaec04744a3f812d7f2d08047d7eb588
ms.sourcegitcommit: 0d0a6e96737dfe24d3257b7c94f25d9500f383ea
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/07/2019
ms.locfileid: "65211379"
---
# <a name="how-to-copy-and-paste-an-elementhost-control-at-design-time"></a><span data-ttu-id="f1546-102">방법: 디자인 타임에 ElementHost 컨트롤 복사 및 붙여넣기</span><span class="sxs-lookup"><span data-stu-id="f1546-102">How to: Copy and Paste an ElementHost Control at Design Time</span></span>

<span data-ttu-id="f1546-103">이 절차에서는 Visual Studio에서 Windows Form에 Windows Presentation Foundation (WPF) 컨트롤을 복사 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="f1546-103">This procedure shows you how to copy a Windows Presentation Foundation (WPF) control on a Windows Form in Visual Studio.</span></span>

## <a name="copy-and-paste-an-elementhost-control-at-design-time"></a><span data-ttu-id="f1546-104">복사 하 고 디자인 타임에 ElementHost 컨트롤을 붙여 넣습니다.</span><span class="sxs-lookup"><span data-stu-id="f1546-104">Copy and paste an ElementHost control at design time</span></span>

1. <span data-ttu-id="f1546-105">새 WPF 추가 <xref:System.Windows.Controls.UserControl> Windows Forms 프로젝트에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f1546-105">Add a new WPF <xref:System.Windows.Controls.UserControl> to your Windows Forms project.</span></span> <span data-ttu-id="f1546-106">컨트롤 형식의 기본 이름인 `UserControl1.xaml`을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="f1546-106">Use the default name for the control type, `UserControl1.xaml`.</span></span> <span data-ttu-id="f1546-107">자세한 내용은 [연습: 디자인 타임에 Windows Forms에서 새 WPF 콘텐츠 만들기](walkthrough-creating-new-wpf-content-on-windows-forms-at-design-time.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="f1546-107">For more information, see [Walkthrough: Creating New WPF Content on Windows Forms at Design Time](walkthrough-creating-new-wpf-content-on-windows-forms-at-design-time.md).</span></span>

2. <span data-ttu-id="f1546-108">에 **속성** 창에서 값을 설정 합니다 <xref:System.Windows.FrameworkElement.Width%2A> 및 <xref:System.Windows.FrameworkElement.Height%2A> 의 속성 `UserControl1` 를 `200`합니다.</span><span class="sxs-lookup"><span data-stu-id="f1546-108">In the **Properties** window, set the value of the <xref:System.Windows.FrameworkElement.Width%2A> and <xref:System.Windows.FrameworkElement.Height%2A> properties of `UserControl1` to `200`.</span></span>

3. <span data-ttu-id="f1546-109"><xref:System.Windows.Controls.Control.Background%2A> 속성 값을 `Blue`로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="f1546-109">Set the value of the <xref:System.Windows.Controls.Control.Background%2A> property to `Blue`.</span></span>

4. <span data-ttu-id="f1546-110">프로젝트를 빌드합니다.</span><span class="sxs-lookup"><span data-stu-id="f1546-110">Build the project.</span></span>

5. <span data-ttu-id="f1546-111">Windows Forms 디자이너에서 `Form1`을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="f1546-111">Open `Form1` in the Windows Forms Designer.</span></span>

6. <span data-ttu-id="f1546-112">합니다 **도구 상자**의 인스턴스를 끌어 `UserControl1` 폼입니다.</span><span class="sxs-lookup"><span data-stu-id="f1546-112">From the **Toolbox**, drag an instance of `UserControl1` onto the form.</span></span>

   <span data-ttu-id="f1546-113">`UserControl1` 인스턴스가 `elementHost1`이라는 새 <xref:System.Windows.Forms.Integration.ElementHost> 컨트롤에서 호스트됩니다.</span><span class="sxs-lookup"><span data-stu-id="f1546-113">An instance of `UserControl1` is hosted in a new <xref:System.Windows.Forms.Integration.ElementHost> control named `elementHost1`.</span></span>

7. <span data-ttu-id="f1546-114">`elementHost1`을 선택하고 Ctrl+C를 눌러 클립보드에 복사합니다.</span><span class="sxs-lookup"><span data-stu-id="f1546-114">With `elementHost1` selected, press CTRL+C to copy it to the clipboard.</span></span>

8. <span data-ttu-id="f1546-115">복사한 컨트롤을 폼으로 붙여 넣으려면 CTRL + V 키를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="f1546-115">Press CTRL+V to paste the copied control onto the form.</span></span>

   <span data-ttu-id="f1546-116">새 <xref:System.Windows.Forms.Integration.ElementHost> 제어 라는 `elementHost2` 폼에 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="f1546-116">A new <xref:System.Windows.Forms.Integration.ElementHost> control named `elementHost2` is created on the form.</span></span>

## <a name="see-also"></a><span data-ttu-id="f1546-117">참고자료</span><span class="sxs-lookup"><span data-stu-id="f1546-117">See also</span></span>

- <xref:System.Windows.Forms.Integration.ElementHost>
- <xref:System.Windows.Forms.Integration.WindowsFormsHost>
- [<span data-ttu-id="f1546-118">마이그레이션 및 상호 운용성</span><span class="sxs-lookup"><span data-stu-id="f1546-118">Migration and Interoperability</span></span>](../../wpf/advanced/migration-and-interoperability.md)
- [<span data-ttu-id="f1546-119">WPF 컨트롤 사용</span><span class="sxs-lookup"><span data-stu-id="f1546-119">Using WPF Controls</span></span>](using-wpf-controls.md)
- [<span data-ttu-id="f1546-120">Visual Studio에서 XAML 디자인</span><span class="sxs-lookup"><span data-stu-id="f1546-120">Design XAML in Visual Studio</span></span>](/visualstudio/designers/designing-xaml-in-visual-studio)
