---
title: '방법: Windows Forms 애플리케이션에서 글꼴 구성표 변경 내용에 대응'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Windows Forms, font scheme changes
ms.assetid: 4db27702-22e7-43bf-a07d-9a004549853c
ms.openlocfilehash: 6aad851770fb886de5d5c00b544ac6eac2857e42
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59339049"
---
# <a name="how-to-respond-to-font-scheme-changes-in-a-windows-forms-application"></a><span data-ttu-id="86cfc-102">방법: Windows Forms 애플리케이션에서 글꼴 구성표 변경 내용에 대응</span><span class="sxs-lookup"><span data-stu-id="86cfc-102">How to: Respond to Font Scheme Changes in a Windows Forms Application</span></span>
<span data-ttu-id="86cfc-103">Windows 운영 체제에서 사용자 크게 또는 작게 표시 기본 글꼴을 확인 하려면 시스템 글꼴 설정을 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="86cfc-103">In the Windows operating systems, a user can change the system-wide font settings to make the default font appear larger or smaller.</span></span> <span data-ttu-id="86cfc-104">이러한 글꼴 설정을 변경 하는 것이 더 큰 형식 해당 화면에 텍스트를 읽이 필요는 시각 장애가 있는 사용자에 대 한 중요 합니다.</span><span class="sxs-lookup"><span data-stu-id="86cfc-104">Changing these font settings is critical for users who are visually impaired and require larger type to read the text on their screens.</span></span> <span data-ttu-id="86cfc-105">글꼴 구성표 변경 될 때마다 양식 및 포함 된 모든 텍스트의 크기를 늘리거나 줄여 이러한 변경에 반응 하는 Windows Forms 응용 프로그램을 조정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="86cfc-105">You can adjust your Windows Forms application to react to these changes by increasing or decreasing the size of the form and all contained text whenever the font scheme changes.</span></span> <span data-ttu-id="86cfc-106">동적으로 글꼴 크기의 변경 내용을 수용 하기 위해 폼을 하려는 경우에 폼에 코드를 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="86cfc-106">If you want your form to accommodate changes in font sizes dynamically, you can add code to your form.</span></span>  
  
 <span data-ttu-id="86cfc-107">일반적으로 Windows Forms에서 사용 된 기본 글꼴은 글꼴에서 반환 되는 <xref:Microsoft.Win32> 네임 스페이스 호출 `GetStockObject(DEFAULT_GUI_FONT)`합니다.</span><span class="sxs-lookup"><span data-stu-id="86cfc-107">Typically, the default font used by Windows Forms is the font returned by the <xref:Microsoft.Win32> namespace call to `GetStockObject(DEFAULT_GUI_FONT)`.</span></span> <span data-ttu-id="86cfc-108">이 호출에서 반환 되는 글꼴 화면 해상도 변경 하는 경우에 변경 됩니다.</span><span class="sxs-lookup"><span data-stu-id="86cfc-108">The font returned by this call only changes when the screen resolution changes.</span></span> <span data-ttu-id="86cfc-109">코드에서 기본 글꼴을 변경 해야 다음 절차 에서처럼 <xref:System.Drawing.SystemFonts.IconTitleFont%2A> 글꼴 크기의 변경 내용에 응답 합니다.</span><span class="sxs-lookup"><span data-stu-id="86cfc-109">As shown in the following procedure, your code must change the default font to <xref:System.Drawing.SystemFonts.IconTitleFont%2A> to respond to changes in font size.</span></span>  
  
### <a name="to-use-the-desktop-font-and-respond-to-font-scheme-changes"></a><span data-ttu-id="86cfc-110">데스크톱 글꼴을 사용 하 여 글꼴 구성표 변경에 응답</span><span class="sxs-lookup"><span data-stu-id="86cfc-110">To use the desktop font and respond to font scheme changes</span></span>  
  
1. <span data-ttu-id="86cfc-111">폼에 만들고에 원하는 컨트롤을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="86cfc-111">Create your form, and add the controls you want to it.</span></span> <span data-ttu-id="86cfc-112">자세한 내용은 [방법: 명령줄에서 Windows Forms 응용 프로그램을 만듭니다](how-to-create-a-windows-forms-application-from-the-command-line.md) 하 고 [사용 하 여 Windows Forms에서 컨트롤](./controls/controls-to-use-on-windows-forms.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="86cfc-112">For more information, see [How to: Create a Windows Forms Application from the Command Line](how-to-create-a-windows-forms-application-from-the-command-line.md) and [Controls to Use on Windows Forms](./controls/controls-to-use-on-windows-forms.md).</span></span>  
  
2. <span data-ttu-id="86cfc-113">에 대 한 참조를 추가 합니다 <xref:Microsoft.Win32> 코드에 네임 스페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="86cfc-113">Add a reference to the <xref:Microsoft.Win32> namespace to your code.</span></span>  
  
     [!code-csharp[WinFormsAutoScaling#2](~/samples/snippets/csharp/VS_Snippets_Winforms/WinFormsAutoScaling/CS/Form1.cs#2)]
     [!code-vb[WinFormsAutoScaling#2](~/samples/snippets/visualbasic/VS_Snippets_Winforms/WinFormsAutoScaling/VB/Form1.vb#2)]  
  
3. <span data-ttu-id="86cfc-114">필요한 이벤트 처리기를 연결 하는 데 사용 하 여 폼의 기본 글꼴을 변경 하 여 폼의 생성자에 다음 코드를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="86cfc-114">Add the following code to the constructor of your form to hook up required event handlers, and to change the default font in use for the form.</span></span>  
  
     [!code-csharp[WinFormsAutoScaling#3](~/samples/snippets/csharp/VS_Snippets_Winforms/WinFormsAutoScaling/CS/Form1.cs#3)]
     [!code-vb[WinFormsAutoScaling#3](~/samples/snippets/visualbasic/VS_Snippets_Winforms/WinFormsAutoScaling/VB/Form1.vb#3)]  
  
4. <span data-ttu-id="86cfc-115">에 대 한 처리기를 구현 합니다 <xref:Microsoft.Win32.SystemEvents.UserPreferenceChanged> 하면 폼이 자동으로 크기를 조정 하는 이벤트 때는 <xref:Microsoft.Win32.UserPreferenceCategory.Window> 범주 변경 합니다.</span><span class="sxs-lookup"><span data-stu-id="86cfc-115">Implement a handler for the <xref:Microsoft.Win32.SystemEvents.UserPreferenceChanged> event that causes the form to scale automatically when the <xref:Microsoft.Win32.UserPreferenceCategory.Window> category changes.</span></span>  
  
     [!code-csharp[WinFormsAutoScaling#4](~/samples/snippets/csharp/VS_Snippets_Winforms/WinFormsAutoScaling/CS/Form1.cs#4)]
     [!code-vb[WinFormsAutoScaling#4](~/samples/snippets/visualbasic/VS_Snippets_Winforms/WinFormsAutoScaling/VB/Form1.vb#4)]  
  
5. <span data-ttu-id="86cfc-116">마지막으로,에 대 한 처리기를 구현 합니다 <xref:System.Windows.Forms.Form.FormClosing> 분리 하는 이벤트를 <xref:Microsoft.Win32.SystemEvents.UserPreferenceChanged> 이벤트 처리기입니다.</span><span class="sxs-lookup"><span data-stu-id="86cfc-116">Finally, implement a handler for the <xref:System.Windows.Forms.Form.FormClosing> event that detaches the <xref:Microsoft.Win32.SystemEvents.UserPreferenceChanged> event handler.</span></span>  
  
     > [!IMPORTANT]
     > <span data-ttu-id="86cfc-117">이 코드를 포함 하지 않으면 응용 프로그램에 메모리 누수가 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="86cfc-117">Failure to include this code will cause your application to leak memory.</span></span>  
  
     [!code-csharp[WinFormsAutoScaling#5](~/samples/snippets/csharp/VS_Snippets_Winforms/WinFormsAutoScaling/CS/Form1.cs#5)]
     [!code-vb[WinFormsAutoScaling#5](~/samples/snippets/visualbasic/VS_Snippets_Winforms/WinFormsAutoScaling/VB/Form1.vb#5)]  
  
6. <span data-ttu-id="86cfc-118">코드를 컴파일하고 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="86cfc-118">Compile and run the code.</span></span>  
  
### <a name="to-manually-change-the-font-scheme-in-windows-xp"></a><span data-ttu-id="86cfc-119">수동으로 Windows XP에서 글꼴 구성표 변경</span><span class="sxs-lookup"><span data-stu-id="86cfc-119">To manually change the font scheme in Windows XP</span></span>  
  
1. <span data-ttu-id="86cfc-120">Windows Forms 응용 프로그램 실행 되는 동안 Windows 바탕 화면을 마우스 오른쪽 단추로 클릭 하 고 선택 **속성** 바로 가기 메뉴에서.</span><span class="sxs-lookup"><span data-stu-id="86cfc-120">While your Windows Forms application is running, right-click the Windows desktop and choose **Properties** from the shortcut menu.</span></span>  
  
2. <span data-ttu-id="86cfc-121">에 **표시 속성** 대화 상자에서 클릭 합니다 **모양을** 탭 합니다.</span><span class="sxs-lookup"><span data-stu-id="86cfc-121">In the **Display Properties** dialog box, click the **Appearance** tab.</span></span>  
  
3. <span data-ttu-id="86cfc-122">**글꼴 크기** 드롭다운 목록 상자에서 새 글꼴 크기를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="86cfc-122">From the **Font Size** drop-down list box, select a new font size.</span></span>  
  
     <span data-ttu-id="86cfc-123">폼이 데스크톱 글꼴 구성표의 런타임 변경 내용에 반응 이제 알 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="86cfc-123">You'll notice that the form now reacts to run-time changes in the desktop font scheme.</span></span> <span data-ttu-id="86cfc-124">사용자 간에 변경 될 때 **정규**를 **큰 글꼴**, 및 **아주 큰 글꼴**, 폼 글꼴을 변경 하 고 크기가 올바르게 조정 합니다.</span><span class="sxs-lookup"><span data-stu-id="86cfc-124">When the user changes between **Normal**, **Large Fonts**, and **Extra Large Fonts**, the form changes font and scales correctly.</span></span>  
  
## <a name="example"></a><span data-ttu-id="86cfc-125">예제</span><span class="sxs-lookup"><span data-stu-id="86cfc-125">Example</span></span>  
 [!code-csharp[WinFormsAutoScaling#1](~/samples/snippets/csharp/VS_Snippets_Winforms/WinFormsAutoScaling/CS/Form1.cs#1)]
 [!code-vb[WinFormsAutoScaling#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/WinFormsAutoScaling/VB/Form1.vb#1)]  
  
 <span data-ttu-id="86cfc-126">에 대 한 호출을 포함 하는이 코드 예제에서 constructer `InitializeComponent`, Visual Studio에서 새 Windows Forms 프로젝트를 만들 때 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="86cfc-126">The constructer in this code example contains a call to `InitializeComponent`, which is defined when you create a new Windows Forms project in Visual Studio.</span></span> <span data-ttu-id="86cfc-127">명령줄에서 응용 프로그램을 작성 하는 경우이 코드 줄을 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="86cfc-127">Remove this line of code if you are building your application on the command line.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="86cfc-128">참고자료</span><span class="sxs-lookup"><span data-stu-id="86cfc-128">See also</span></span>

- <xref:System.Windows.Forms.ContainerControl.PerformAutoScale%2A>
- [<span data-ttu-id="86cfc-129">Windows Forms의 자동 크기 조정</span><span class="sxs-lookup"><span data-stu-id="86cfc-129">Automatic Scaling in Windows Forms</span></span>](automatic-scaling-in-windows-forms.md)
