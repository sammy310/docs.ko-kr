---
title: Windows Forms 앱에서 글꼴 구성표 변경에 응답
titleSuffix: ''
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Windows Forms, font scheme changes
ms.assetid: 4db27702-22e7-43bf-a07d-9a004549853c
ms.openlocfilehash: e3b96139a7cfd4b268d81b1da58229527e2beb87
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/24/2020
ms.locfileid: "76739233"
---
# <a name="how-to-respond-to-font-scheme-changes-in-a-windows-forms-application"></a><span data-ttu-id="0626a-102">방법: Windows Forms 애플리케이션에서 글꼴 구성표 변경에 응답</span><span class="sxs-lookup"><span data-stu-id="0626a-102">How to: Respond to Font Scheme Changes in a Windows Forms Application</span></span>
<span data-ttu-id="0626a-103">Windows 운영 체제에서 사용자는 시스템 수준 글꼴 설정을 변경 하 여 기본 글꼴이 더 크거나 작게 표시 되도록 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0626a-103">In the Windows operating systems, a user can change the system-wide font settings to make the default font appear larger or smaller.</span></span> <span data-ttu-id="0626a-104">이러한 글꼴 설정을 변경 하는 것은 시각적으로 손상 된 사용자에 게 중요 하며, 화면에서 텍스트를 읽는 데 더 큰 형식이 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="0626a-104">Changing these font settings is critical for users who are visually impaired and require larger type to read the text on their screens.</span></span> <span data-ttu-id="0626a-105">글꼴 구성표가 변경 될 때마다 폼 및 포함 된 모든 텍스트의 크기를 늘리거나 줄여서 이러한 변경 내용에 대응 하도록 Windows Forms 응용 프로그램을 조정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0626a-105">You can adjust your Windows Forms application to react to these changes by increasing or decreasing the size of the form and all contained text whenever the font scheme changes.</span></span> <span data-ttu-id="0626a-106">폼에 변경 내용을 동적으로 적용 하려면 폼에 코드를 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0626a-106">If you want your form to accommodate changes in font sizes dynamically, you can add code to your form.</span></span>  
  
 <span data-ttu-id="0626a-107">일반적으로 Windows Forms에서 사용 하는 기본 글꼴은 `GetStockObject(DEFAULT_GUI_FONT)`에 대 한 <xref:Microsoft.Win32> 네임 스페이스 호출에서 반환 되는 글꼴입니다.</span><span class="sxs-lookup"><span data-stu-id="0626a-107">Typically, the default font used by Windows Forms is the font returned by the <xref:Microsoft.Win32> namespace call to `GetStockObject(DEFAULT_GUI_FONT)`.</span></span> <span data-ttu-id="0626a-108">이 호출에서 반환 되는 글꼴은 화면 해상도가 변경 되는 경우에만 변경 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0626a-108">The font returned by this call only changes when the screen resolution changes.</span></span> <span data-ttu-id="0626a-109">다음 절차에 표시 된 것 처럼 코드는 글꼴 크기의 변경 내용에 응답 하려면 <xref:System.Drawing.SystemFonts.IconTitleFont%2A> 기본 글꼴을 변경 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0626a-109">As shown in the following procedure, your code must change the default font to <xref:System.Drawing.SystemFonts.IconTitleFont%2A> to respond to changes in font size.</span></span>  
  
### <a name="to-use-the-desktop-font-and-respond-to-font-scheme-changes"></a><span data-ttu-id="0626a-110">바탕 화면 글꼴을 사용 하 고 글꼴 구성표 변경에 응답 하려면</span><span class="sxs-lookup"><span data-stu-id="0626a-110">To use the desktop font and respond to font scheme changes</span></span>  
  
1. <span data-ttu-id="0626a-111">양식을 만들고 원하는 컨트롤을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="0626a-111">Create your form, and add the controls you want to it.</span></span> <span data-ttu-id="0626a-112">자세한 내용은 [방법: 명령줄에서 Windows Forms 응용 프로그램 만들기](how-to-create-a-windows-forms-application-from-the-command-line.md) 및 [Windows Forms에서 사용할 컨트롤](./controls/controls-to-use-on-windows-forms.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="0626a-112">For more information, see [How to: Create a Windows Forms Application from the Command Line](how-to-create-a-windows-forms-application-from-the-command-line.md) and [Controls to Use on Windows Forms](./controls/controls-to-use-on-windows-forms.md).</span></span>  
  
2. <span data-ttu-id="0626a-113"><xref:Microsoft.Win32> 네임 스페이스에 대 한 참조를 코드에 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="0626a-113">Add a reference to the <xref:Microsoft.Win32> namespace to your code.</span></span>  
  
     [!code-csharp[WinFormsAutoScaling#2](~/samples/snippets/csharp/VS_Snippets_Winforms/WinFormsAutoScaling/CS/Form1.cs#2)]
     [!code-vb[WinFormsAutoScaling#2](~/samples/snippets/visualbasic/VS_Snippets_Winforms/WinFormsAutoScaling/VB/Form1.vb#2)]  
  
3. <span data-ttu-id="0626a-114">폼의 생성자에 다음 코드를 추가 하 여 필요한 이벤트 처리기를 연결 하 고 폼에 사용 되는 기본 글꼴을 변경 합니다.</span><span class="sxs-lookup"><span data-stu-id="0626a-114">Add the following code to the constructor of your form to hook up required event handlers, and to change the default font in use for the form.</span></span>  
  
     [!code-csharp[WinFormsAutoScaling#3](~/samples/snippets/csharp/VS_Snippets_Winforms/WinFormsAutoScaling/CS/Form1.cs#3)]
     [!code-vb[WinFormsAutoScaling#3](~/samples/snippets/visualbasic/VS_Snippets_Winforms/WinFormsAutoScaling/VB/Form1.vb#3)]  
  
4. <span data-ttu-id="0626a-115"><xref:Microsoft.Win32.UserPreferenceCategory.Window> 범주가 변경 될 때 폼이 자동으로 확장 되도록 하는 <xref:Microsoft.Win32.SystemEvents.UserPreferenceChanged> 이벤트에 대 한 처리기를 구현 합니다.</span><span class="sxs-lookup"><span data-stu-id="0626a-115">Implement a handler for the <xref:Microsoft.Win32.SystemEvents.UserPreferenceChanged> event that causes the form to scale automatically when the <xref:Microsoft.Win32.UserPreferenceCategory.Window> category changes.</span></span>  
  
     [!code-csharp[WinFormsAutoScaling#4](~/samples/snippets/csharp/VS_Snippets_Winforms/WinFormsAutoScaling/CS/Form1.cs#4)]
     [!code-vb[WinFormsAutoScaling#4](~/samples/snippets/visualbasic/VS_Snippets_Winforms/WinFormsAutoScaling/VB/Form1.vb#4)]  
  
5. <span data-ttu-id="0626a-116">마지막으로 <xref:Microsoft.Win32.SystemEvents.UserPreferenceChanged> 이벤트 처리기를 분리 하는 <xref:System.Windows.Forms.Form.FormClosing> 이벤트에 대 한 처리기를 구현 합니다.</span><span class="sxs-lookup"><span data-stu-id="0626a-116">Finally, implement a handler for the <xref:System.Windows.Forms.Form.FormClosing> event that detaches the <xref:Microsoft.Win32.SystemEvents.UserPreferenceChanged> event handler.</span></span>  
  
     > [!IMPORTANT]
     > <span data-ttu-id="0626a-117">이 코드를 포함 하지 않으면 응용 프로그램에서 메모리 누수가 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="0626a-117">Failure to include this code will cause your application to leak memory.</span></span>  
  
     [!code-csharp[WinFormsAutoScaling#5](~/samples/snippets/csharp/VS_Snippets_Winforms/WinFormsAutoScaling/CS/Form1.cs#5)]
     [!code-vb[WinFormsAutoScaling#5](~/samples/snippets/visualbasic/VS_Snippets_Winforms/WinFormsAutoScaling/VB/Form1.vb#5)]  
  
6. <span data-ttu-id="0626a-118">코드를 컴파일하고 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="0626a-118">Compile and run the code.</span></span>  
  
### <a name="to-manually-change-the-font-scheme-in-windows-xp"></a><span data-ttu-id="0626a-119">Windows XP에서 글꼴 구성표를 수동으로 변경 하려면</span><span class="sxs-lookup"><span data-stu-id="0626a-119">To manually change the font scheme in Windows XP</span></span>  
  
1. <span data-ttu-id="0626a-120">Windows Forms 응용 프로그램이 실행 되는 동안 Windows 바탕 화면을 마우스 오른쪽 단추로 클릭 하 고 바로 가기 메뉴에서 **속성** 을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="0626a-120">While your Windows Forms application is running, right-click the Windows desktop and choose **Properties** from the shortcut menu.</span></span>  
  
2. <span data-ttu-id="0626a-121">**표시 속성** 대화 상자에서 **모양** 탭을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="0626a-121">In the **Display Properties** dialog box, click the **Appearance** tab.</span></span>  
  
3. <span data-ttu-id="0626a-122">**글꼴 크기** 드롭다운 목록 상자에서 새 글꼴 크기를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="0626a-122">From the **Font Size** drop-down list box, select a new font size.</span></span>  
  
     <span data-ttu-id="0626a-123">이제 양식이 바탕 화면 글꼴 구성표의 런타임 변경 내용에 반응 하는 것을 알 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0626a-123">You'll notice that the form now reacts to run-time changes in the desktop font scheme.</span></span> <span data-ttu-id="0626a-124">사용자가 **보통**, **대형 글꼴**및 초대형 **글꼴**사이에서 변경 하는 경우 폼이 글꼴을 변경 하 고 크기를 올바르게 조정 합니다.</span><span class="sxs-lookup"><span data-stu-id="0626a-124">When the user changes between **Normal**, **Large Fonts**, and **Extra Large Fonts**, the form changes font and scales correctly.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0626a-125">예제</span><span class="sxs-lookup"><span data-stu-id="0626a-125">Example</span></span>  
 [!code-csharp[WinFormsAutoScaling#1](~/samples/snippets/csharp/VS_Snippets_Winforms/WinFormsAutoScaling/CS/Form1.cs#1)]
 [!code-vb[WinFormsAutoScaling#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/WinFormsAutoScaling/VB/Form1.vb#1)]  
  
 <span data-ttu-id="0626a-126">이 코드 예제의 생성자에는 Visual Studio에서 새 Windows Forms 프로젝트를 만들 때 정의 되는 `InitializeComponent`에 대 한 호출이 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0626a-126">The constructor in this code example contains a call to `InitializeComponent`, which is defined when you create a new Windows Forms project in Visual Studio.</span></span> <span data-ttu-id="0626a-127">명령줄에서 응용 프로그램을 빌드하는 경우이 코드 줄을 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="0626a-127">Remove this line of code if you are building your application on the command line.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0626a-128">참고 항목</span><span class="sxs-lookup"><span data-stu-id="0626a-128">See also</span></span>

- <xref:System.Windows.Forms.ContainerControl.PerformAutoScale%2A>
- [<span data-ttu-id="0626a-129">Windows Forms의 자동 크기 조정</span><span class="sxs-lookup"><span data-stu-id="0626a-129">Automatic Scaling in Windows Forms</span></span>](automatic-scaling-in-windows-forms.md)
