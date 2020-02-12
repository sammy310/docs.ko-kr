---
title: 대화 상자 개요
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- modeless dialog boxes [WPF]
- dialog boxes [WPF]
- message boxes [WPF]
- modal dialog boxes [WPF]
ms.assetid: 0d23d544-a393-4a02-a3aa-d8cd5d3d6511
ms.openlocfilehash: bce2eed5f0e78c16b85b399e588c3d0d68ce7cb7
ms.sourcegitcommit: 011314e0c8eb4cf4a11d92078f58176c8c3efd2d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/11/2020
ms.locfileid: "77123716"
---
# <a name="dialog-boxes-overview"></a><span data-ttu-id="2c09b-102">대화 상자 개요</span><span class="sxs-lookup"><span data-stu-id="2c09b-102">Dialog boxes overview</span></span>
<span data-ttu-id="2c09b-103">독립 실행형 응용 프로그램에는 일반적으로 응용 프로그램이 작동 하는 기본 데이터를 표시 하 고 메뉴 모음, 도구 모음, 상태 표시줄 등의 [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] 메커니즘을 통해 해당 데이터를 처리 하는 기능을 노출 하는 주 창이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2c09b-103">Standalone applications typically have a main window that both displays the main data over which the application operates and exposes the functionality to process that data through [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] mechanisms like menu bars, tool bars, and status bars.</span></span> <span data-ttu-id="2c09b-104">특수 애플리케이션에는 다음을 수행하는 추가 창이 표시될 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2c09b-104">A non-trivial application may also display additional windows to do the following:</span></span>  
  
- <span data-ttu-id="2c09b-105">사용자에게 특정 정보 표시.</span><span class="sxs-lookup"><span data-stu-id="2c09b-105">Display specific information to users.</span></span>  
  
- <span data-ttu-id="2c09b-106">사용자로부터 정보 수집.</span><span class="sxs-lookup"><span data-stu-id="2c09b-106">Gather information from users.</span></span>  
  
- <span data-ttu-id="2c09b-107">정보 표시 및 수집.</span><span class="sxs-lookup"><span data-stu-id="2c09b-107">Both display and gather information.</span></span>  
  
 <span data-ttu-id="2c09b-108">이러한 형식의 창을 *대화 상자*라고 하며, 모달 및 모덜리스의 두 가지 형식이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2c09b-108">These types of windows are known as *dialog boxes*, and there are two types: modal and modeless.</span></span>  
  
 <span data-ttu-id="2c09b-109">*모달* 대화 상자는 함수가 사용자의 추가 데이터를 계속 사용 해야 하는 경우 함수에 의해 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2c09b-109">A *modal* dialog box is displayed by a function when the function needs additional data from a user to continue.</span></span> <span data-ttu-id="2c09b-110">함수가 작동하려면 모달 대화 상자를 통해 데이터를 수집해야 하기 때문에, 모달 대화 상자가 열려 있는 동안에는 사용자가 다른 창을 활성화할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="2c09b-110">Because the function depends on the modal dialog box to gather data, the modal dialog box also prevents a user from activating other windows in the application while it remains open.</span></span> <span data-ttu-id="2c09b-111">대부분의 경우 모달 대화 상자에서 **확인** 또는 **취소** 단추를 눌러 모달 대화 상자를 완료 한 경우 사용자가 신호를 보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2c09b-111">In most cases, a modal dialog box allows a user to signal when they have finished with the modal dialog box by pressing either an **OK** or **Cancel** button.</span></span> <span data-ttu-id="2c09b-112">**확인** 단추를 누르면 사용자가 데이터를 입력 하 고 함수를 통해 해당 데이터를 계속 처리 하려고 합니다.</span><span class="sxs-lookup"><span data-stu-id="2c09b-112">Pressing the **OK** button indicates that a user has entered data and wants the function to continue processing with that data.</span></span> <span data-ttu-id="2c09b-113">**취소** 단추를 누르면 사용자가 함수 실행을 완전히 중지 하는 것을 알 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2c09b-113">Pressing the **Cancel** button indicates that a user wants to stop the function from executing altogether.</span></span> <span data-ttu-id="2c09b-114">데이터를 열고, 저장하고, 인쇄하는 가장 일반적인 모달 대화 상자의 예가 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2c09b-114">The most common examples of modal dialog boxes are shown to open, save, and print data.</span></span>  
  
 <span data-ttu-id="2c09b-115">반면 *모덜리스* 대화 상자는 열려 있는 동안 사용자가 다른 창을 활성화할 수 없도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="2c09b-115">A *modeless* dialog box, on the other hand, does not prevent a user from activating other windows while it is open.</span></span> <span data-ttu-id="2c09b-116">예를 들어, 사용자가 문서에서 특정 단어를 찾으려고 할 때 주 창에서 사용자가 찾으려는 단어를 입력할 대화 상자를 열 때가 많습니다.</span><span class="sxs-lookup"><span data-stu-id="2c09b-116">For example, if a user wants to find occurrences of a particular word in a document, a main window will often open a dialog box to ask a user what word they are looking for.</span></span> <span data-ttu-id="2c09b-117">단어를 찾는다고 해서 사용자가 문서를 편집하지 못하게 되는 것은 아니기 때문에 대화 상자를 모덜로 설정할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="2c09b-117">Since finding a word doesn't prevent a user from editing the document, however, the dialog box doesn't need to be modal.</span></span> <span data-ttu-id="2c09b-118">모덜리스 대화 상자는 최소한 대화 상자를 닫기 위한 **닫기** 단추를 제공 하 고, **다음 찾기** 단추와 같은 특정 함수를 실행 하는 추가 단추를 제공 하 여 단어 검색의 찾기 조건과 일치 하는 다음 단어를 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2c09b-118">A modeless dialog box at least provides a **Close** button to close the dialog box, and may provide additional buttons to execute specific functions, such as a **Find Next** button to find the next word that matches the find criteria of a word search.</span></span>  
  
 <span data-ttu-id="2c09b-119">WPF (Windows Presentation Foundation)를 사용 하면 메시지 상자, 일반 대화 상자 및 사용자 지정 대화 상자를 비롯 한 여러 가지 유형의 대화 상자를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2c09b-119">Windows Presentation Foundation (WPF) allows you to create several types of dialog boxes, including message boxes, common dialog boxes, and custom dialog boxes.</span></span> <span data-ttu-id="2c09b-120">이 항목에서는 각에 대해 설명 하 고, [대화 상자 샘플](https://github.com/Microsoft/WPF-Samples/tree/master/Windows/DialogBox) 에서는 일치 하는 예제를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="2c09b-120">This topic discusses each, and the [Dialog Box Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Windows/DialogBox) provides matching examples.</span></span>  

<a name="Message_Boxes"></a>   
## <a name="message-boxes"></a><span data-ttu-id="2c09b-121">메시지 상자</span><span class="sxs-lookup"><span data-stu-id="2c09b-121">Message boxes</span></span>  
 <span data-ttu-id="2c09b-122">*메시지 상자* 는 텍스트 정보를 표시 하 고 사용자가 단추를 사용 하 여 결정을 내릴 수 있도록 하는 대화 상자입니다.</span><span class="sxs-lookup"><span data-stu-id="2c09b-122">A *message box* is a dialog box that can be used to display textual information and to allow users to make decisions with buttons.</span></span> <span data-ttu-id="2c09b-123">다음 그림에는 텍스트 정보를 표시하고, 질문을 하고, 질문에 대답할 때 사용할 세 개의 단추를 사용자에게 제공하는 메시지 상자가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2c09b-123">The following figure shows a message box that displays textual information, asks a question, and provides the user with three buttons to answer the question.</span></span>  
  
 ![응용 프로그램을 닫기 전에 문서에 대 한 변경 내용을 저장할지 묻는 워드 프로세서 대화 상자입니다.](./media/dialog-boxes-overview/word-processor-dialog.png)  
  
 <span data-ttu-id="2c09b-125">메시지 상자를 만들려면 <xref:System.Windows.MessageBox> 클래스를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="2c09b-125">To create a message box, you use the <xref:System.Windows.MessageBox> class.</span></span> <span data-ttu-id="2c09b-126"><xref:System.Windows.MessageBox>를 사용 하면 다음과 같은 코드를 사용 하 여 메시지 상자 텍스트, 제목, 아이콘 및 단추를 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2c09b-126"><xref:System.Windows.MessageBox> lets you configure the message box text, title, icon, and buttons, using code like the following.</span></span>  
  
 [!code-csharp[DialogBoxesOverviewSnippets#MsgBoxConfigureCODEBEHIND](~/samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxesOverviewSnippets/CSharp/Window1.xaml.cs#msgboxconfigurecodebehind)]
 [!code-vb[DialogBoxesOverviewSnippets#MsgBoxConfigureCODEBEHIND](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DialogBoxesOverviewSnippets/VisualBasic/window1.xaml.vb#msgboxconfigurecodebehind)]  
  
 <span data-ttu-id="2c09b-127">메시지 상자를 표시 하려면 다음 코드에서 보여 주는 것 처럼 `static`<xref:System.Windows.MessageBox.Show%2A> 메서드를 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="2c09b-127">To show a message box, you call the `static`<xref:System.Windows.MessageBox.Show%2A> method, as demonstrated in the following code.</span></span>  
  
 [!code-csharp[DialogBoxesOverviewSnippets#MsgBoxShowCODEBEHIND](~/samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxesOverviewSnippets/CSharp/Window1.xaml.cs#msgboxshowcodebehind)]
 [!code-vb[DialogBoxesOverviewSnippets#MsgBoxShowCODEBEHIND](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DialogBoxesOverviewSnippets/VisualBasic/window1.xaml.vb#msgboxshowcodebehind)]  
  
 <span data-ttu-id="2c09b-128">메시지 상자를 표시하는 코드로 사용자의 결정을 감지하고 처리해야 할 경우는(단추 누름) 다음 코드에서와 같이 코드를 통해 메시지 상자 결과를 검사할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2c09b-128">When code that shows a message box needs to detect and process the user's decision (which button was pressed), the code can inspect the message box result, as shown in the following code.</span></span>  
  
 [!code-csharp[DialogBoxesOverviewSnippets#MsgBoxShowAndResultCODEBEHIND1](~/samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxesOverviewSnippets/CSharp/Window1.xaml.cs#msgboxshowandresultcodebehind1)]
 [!code-vb[DialogBoxesOverviewSnippets#MsgBoxShowAndResultCODEBEHIND1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DialogBoxesOverviewSnippets/VisualBasic/window1.xaml.vb#msgboxshowandresultcodebehind1)]  
  
 <span data-ttu-id="2c09b-129">메시지 상자를 사용 하는 방법에 대 한 자세한 내용은 <xref:System.Windows.MessageBox>, [MessageBox 샘플](https://github.com/Microsoft/WPF-Samples/tree/master/Windows/MessageBox)및 [대화 상자 샘플](https://github.com/Microsoft/WPF-Samples/tree/master/Windows/DialogBox)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="2c09b-129">For more information on using message boxes, see <xref:System.Windows.MessageBox>, [MessageBox Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Windows/MessageBox), and [Dialog Box Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Windows/DialogBox).</span></span>  
  
 <span data-ttu-id="2c09b-130"><xref:System.Windows.MessageBox>는 간단한 대화 상자 사용자 환경을 제공할 수 있지만 <xref:System.Windows.MessageBox>를 사용 하는 경우의 이점은 Xbap (XAML 브라우저 응용 프로그램)와 같은 부분 신뢰 보안 샌드박스 내에서 실행 되는 응용 프로그램에 표시 될 수 있는 유일한 창 형식입니다 ( [보안](../security-wpf.md)참조).</span><span class="sxs-lookup"><span data-stu-id="2c09b-130">Although <xref:System.Windows.MessageBox> may offer a simple dialog box user experience, the advantage of using <xref:System.Windows.MessageBox> is that is the only type of window that can be shown by applications that run within a partial trust security sandbox (see [Security](../security-wpf.md)), such as XAML browser applications (XBAPs).</span></span>  
  
 <span data-ttu-id="2c09b-131">대부분의 대화 상자는 텍스트, 선택(확인란), 상호 배타적인 선택(라디오 단추), 목록 선택(목록 상자, 콤보 상자, 드롭다운 목록 상자)과 같이 메시지 상자의 결과보다 복잡한 데이터를 표시하고 수집합니다.</span><span class="sxs-lookup"><span data-stu-id="2c09b-131">Most dialog boxes display and gather more complex data than the result of a message box, including text, selection (check boxes), mutually exclusive selection (radio buttons), and list selection (list boxes, combo boxes, drop-down list boxes).</span></span> <span data-ttu-id="2c09b-132">이러한 경우, Windows Presentation Foundation (WPF)는 여러 일반적인 대화 상자를 제공 하며,이 중 하나를 사용 하면 완전 신뢰로 실행 되는 응용 프로그램으로 제한 되지만 사용자 고유의 대화 상자를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2c09b-132">For these, Windows Presentation Foundation (WPF) provides several common dialog boxes and allows you to create your own dialog boxes, although the use of either is limited to applications running with full trust.</span></span>  
  
<a name="Common_Dialogs"></a>   
## <a name="common-dialog-boxes"></a><span data-ttu-id="2c09b-133">일반 대화 상자</span><span class="sxs-lookup"><span data-stu-id="2c09b-133">Common dialog boxes</span></span>  
 <span data-ttu-id="2c09b-134">Windows는 파일을 열고, 파일을 저장 하 고, 인쇄 하는 대화 상자를 포함 하 여 모든 응용 프로그램에 공통적인 재사용 가능한 여러 대화 상자를 구현 합니다.</span><span class="sxs-lookup"><span data-stu-id="2c09b-134">Windows implements a variety of reusable dialog boxes that are common to all applications, including dialog boxes for opening files, saving files, and printing.</span></span> <span data-ttu-id="2c09b-135">이러한 대화 상자는 운영 체제에서 구현되므로 운영 체제에서 실행되는 모든 애플리케이션에서 공유할 수 있어 사용자 경험의 일관성에 도움이 됩니다. 운영 체제에서 제공되는 대화 상자를 사용자가 한 애플리케이션에서 익히고 나면 다른 애플리케이션에서 대화 상자의 사용 방법을 다시 익힐 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="2c09b-135">Since these dialog boxes are implemented by the operating system, they can be shared among all the applications that run on the operating system, which helps user experience consistency; when users are familiar with the use of an operating system-provided dialog box in one application, they don't need to learn how to use that dialog box in other applications.</span></span> <span data-ttu-id="2c09b-136">이러한 대화 상자는 모든 응용 프로그램에서 사용할 수 있으며 일관 된 사용자 환경을 제공 하는 데 도움이 되기 때문에 *일반 대화 상자*라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="2c09b-136">Because these dialog boxes are available to all applications and because they help provide a consistent user experience, they are known as *common dialog boxes*.</span></span>  
  
 <span data-ttu-id="2c09b-137">WPF (Windows Presentation Foundation)는 열려 있는 파일을 캡슐화 하 고, 파일을 저장 하 고, 일반 대화 상자를 인쇄 하 여 독립 실행형 응용 프로그램에서 사용할 수 있도록 관리 되는 클래스로 노출 합니다.</span><span class="sxs-lookup"><span data-stu-id="2c09b-137">Windows Presentation Foundation (WPF) encapsulates the open file, save file, and print common dialog boxes and exposes them as managed classes for you to use in standalone applications.</span></span> <span data-ttu-id="2c09b-138">이 항목에서는 각각의 개요를 간략하게 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="2c09b-138">This topic provides a brief overview of each.</span></span>  
  
<a name="Open_File_Dialog"></a>   
### <a name="open-file-dialog"></a><span data-ttu-id="2c09b-139">파일 열기 대화 상자</span><span class="sxs-lookup"><span data-stu-id="2c09b-139">Open File dialog</span></span>  
 <span data-ttu-id="2c09b-140">다음 그림에 표시된 파일 열기 대화 상자는 파일 열기 기능에서 열려는 파일의 이름을 검색할 때 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="2c09b-140">The open file dialog box, shown in the following figure, is used by file opening functionality to retrieve the name of a file to open.</span></span>  
  
 ![파일을 검색할 위치를 보여 주는 열기 대화 상자입니다.](./media/dialog-boxes-overview/open-file-dialog-box.png)  
  
 <span data-ttu-id="2c09b-142">일반 파일 열기 대화 상자는 <xref:Microsoft.Win32.OpenFileDialog> 클래스로 구현 되며 <xref:Microsoft.Win32> 네임 스페이스에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2c09b-142">The common open file dialog box is implemented as the <xref:Microsoft.Win32.OpenFileDialog> class and is located in the <xref:Microsoft.Win32> namespace.</span></span> <span data-ttu-id="2c09b-143">다음 코드에서는 코드를 만들고 구성 및 표시하는 방법과 결과를 처리하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="2c09b-143">The following code shows how to create, configure, and show one, and how to process the result.</span></span>  
  
 [!code-csharp[DialogBoxesOverviewSnippets#OpenFileDialogBoxCODEBEHIND](~/samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxesOverviewSnippets/CSharp/Window1.xaml.cs#openfiledialogboxcodebehind)]
 [!code-vb[DialogBoxesOverviewSnippets#OpenFileDialogBoxCODEBEHIND](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DialogBoxesOverviewSnippets/VisualBasic/window1.xaml.vb#openfiledialogboxcodebehind)]  
  
 <span data-ttu-id="2c09b-144">파일 열기 대화 상자에 대 한 자세한 내용은 <xref:Microsoft.Win32.OpenFileDialog?displayProperty=nameWithType>를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="2c09b-144">For more information on the open file dialog box, see <xref:Microsoft.Win32.OpenFileDialog?displayProperty=nameWithType>.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="2c09b-145"><xref:Microsoft.Win32.OpenFileDialog>를 사용 하 여 부분 신뢰로 실행 되는 응용 프로그램에서 파일 이름을 안전 하 게 검색할 수 있습니다 ( [보안](../security-wpf.md)참조).</span><span class="sxs-lookup"><span data-stu-id="2c09b-145"><xref:Microsoft.Win32.OpenFileDialog> can be used to safely retrieve file names by applications running with partial trust (see [Security](../security-wpf.md)).</span></span>  
  
<a name="Save_File_Dialog"></a>   
### <a name="save-file-dialog-box"></a><span data-ttu-id="2c09b-146">파일 저장 대화 상자</span><span class="sxs-lookup"><span data-stu-id="2c09b-146">Save File dialog box</span></span>  
 <span data-ttu-id="2c09b-147">다음 그림에 표시된 파일 저장 대화 상자는 파일 저장 기능에서 저장하려는 파일의 이름을 검색할 때 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="2c09b-147">The save file dialog box, shown in the following figure, is used by file saving functionality to retrieve the name of a file to save.</span></span>  
  
 ![파일을 저장할 위치를 보여 주는 다른 이름으로 저장 대화 상자가 표시 됩니다.](./media/dialog-boxes-overview/save-file-dialog-box.png)  
  
 <span data-ttu-id="2c09b-149">공용 파일 저장 대화 상자는 <xref:Microsoft.Win32.SaveFileDialog> 클래스로 구현 되며 <xref:Microsoft.Win32> 네임 스페이스에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2c09b-149">The common save file dialog box is implemented as the <xref:Microsoft.Win32.SaveFileDialog> class, and is located in the <xref:Microsoft.Win32> namespace.</span></span> <span data-ttu-id="2c09b-150">다음 코드에서는 코드를 만들고 구성 및 표시하는 방법과 결과를 처리하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="2c09b-150">The following code shows how to create, configure, and show one, and how to process the result.</span></span>  
  
 [!code-csharp[DialogBoxesOverviewSnippets#SaveFileDialogBoxCODEBEHIND](~/samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxesOverviewSnippets/CSharp/Window1.xaml.cs#savefiledialogboxcodebehind)]
 [!code-vb[DialogBoxesOverviewSnippets#SaveFileDialogBoxCODEBEHIND](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DialogBoxesOverviewSnippets/VisualBasic/window1.xaml.vb#savefiledialogboxcodebehind)]  
  
 <span data-ttu-id="2c09b-151">파일 저장 대화 상자에 대 한 자세한 내용은 <xref:Microsoft.Win32.SaveFileDialog?displayProperty=nameWithType>를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="2c09b-151">For more information on the save file dialog box, see <xref:Microsoft.Win32.SaveFileDialog?displayProperty=nameWithType>.</span></span>  
  
<a name="Print_Dialog"></a>   
### <a name="print-dialog-box"></a><span data-ttu-id="2c09b-152">인쇄 대화 상자</span><span class="sxs-lookup"><span data-stu-id="2c09b-152">Print dialog box</span></span>

<span data-ttu-id="2c09b-153">다음 그림에 표시된 인쇄 대화 상자는 인쇄 기능에서 사용자가 데이터를 인쇄할 프린터를 선택하고 구성할 때 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="2c09b-153">The print dialog box, shown in the following figure, is used by printing functionality to choose and configure the printer that a user would like to print data to.</span></span>  
  
![인쇄 대화 상자를 표시 하는 스크린샷](./media/dialog-boxes-overview/print-data-dialog-box.png)  
  
<span data-ttu-id="2c09b-155">일반 인쇄 대화 상자는 <xref:System.Windows.Controls.PrintDialog> 클래스로 구현 되며 <xref:System.Windows.Controls> 네임 스페이스에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2c09b-155">The common print dialog box is implemented as the <xref:System.Windows.Controls.PrintDialog> class, and is located in the <xref:System.Windows.Controls> namespace.</span></span> <span data-ttu-id="2c09b-156">다음 코드에서는 만들고, 구성하고, 표시하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="2c09b-156">The following code shows how to create, configure, and show one.</span></span>  
  
 [!code-csharp[DialogBoxesOverviewSnippets#PrintDialogBoxCODEBEHIND](~/samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxesOverviewSnippets/CSharp/Window1.xaml.cs#printdialogboxcodebehind)]
 [!code-vb[DialogBoxesOverviewSnippets#PrintDialogBoxCODEBEHIND](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DialogBoxesOverviewSnippets/VisualBasic/window1.xaml.vb#printdialogboxcodebehind)]  
  
 <span data-ttu-id="2c09b-157">인쇄 대화 상자에 대 한 자세한 내용은 <xref:System.Windows.Controls.PrintDialog?displayProperty=nameWithType>를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="2c09b-157">For more information on the print dialog box, see <xref:System.Windows.Controls.PrintDialog?displayProperty=nameWithType>.</span></span> <span data-ttu-id="2c09b-158">WPF의 인쇄에 대 한 자세한 내용은 [인쇄 개요](../advanced/printing-overview.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="2c09b-158">For detailed discussion of printing in WPF, see [Printing Overview](../advanced/printing-overview.md).</span></span>  
  
<a name="Custom_Dialog_Boxes"></a>   
## <a name="custom-dialog-boxes"></a><span data-ttu-id="2c09b-159">사용자 지정 대화 상자</span><span class="sxs-lookup"><span data-stu-id="2c09b-159">Custom dialog boxes</span></span>

<span data-ttu-id="2c09b-160">일반 대화 상자는 유용하며 가능한 경우 사용하는 편이 좋지만, 도메인별 대화 상자의 요구 사항은 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="2c09b-160">While common dialog boxes are useful, and should be used when possible, they do not support the requirements of domain-specific dialog boxes.</span></span> <span data-ttu-id="2c09b-161">이러한 경우 사용자가 직접 대화 상자를 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2c09b-161">In these cases, you need to create your own dialog boxes.</span></span> <span data-ttu-id="2c09b-162">살펴보겠지만, 대화 상자는 특별한 동작이 있는 창입니다.</span><span class="sxs-lookup"><span data-stu-id="2c09b-162">As we'll see, a dialog box is a window with special behaviors.</span></span> <span data-ttu-id="2c09b-163"><xref:System.Windows.Window>은 이러한 동작을 구현 하므로 <xref:System.Windows.Window>를 사용 하 여 사용자 지정 모달 및 모덜리스 대화 상자를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="2c09b-163"><xref:System.Windows.Window> implements those behaviors and, consequently, you use <xref:System.Windows.Window> to create custom modal and modeless dialog boxes.</span></span>  
  
<a name="Creating_a_Modal_Custom_Dialog_Box"></a>   
### <a name="creating-a-modal-custom-dialog-box"></a><span data-ttu-id="2c09b-164">모달 사용자 지정 대화 상자 만들기</span><span class="sxs-lookup"><span data-stu-id="2c09b-164">Creating a modal custom dialog box</span></span>

<span data-ttu-id="2c09b-165">이 항목에서는 <xref:System.Windows.Window>를 사용 하 여 `Margins` 대화 상자를 예로 사용 하 여 일반적인 모달 대화 상자 구현을 만드는 방법을 보여 줍니다 ( [대화 상자 샘플](https://github.com/Microsoft/WPF-Samples/tree/master/Windows/DialogBox)참조).</span><span class="sxs-lookup"><span data-stu-id="2c09b-165">This topic shows how to use <xref:System.Windows.Window> to create a typical modal dialog box implementation, using the `Margins` dialog box as an example (see [Dialog Box Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Windows/DialogBox)).</span></span> <span data-ttu-id="2c09b-166">`Margins` 대화 상자는 다음 그림에 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2c09b-166">The `Margins` dialog box is shown in the following figure.</span></span>  
  
 ![왼쪽 여백, 위쪽 여백, 오른쪽 여백 및 아래쪽 여백을 정의 하는 필드를 포함 하는 여백 대화 상자입니다.](./media/dialog-boxes-overview/margin-size-dialog-box.png)  
  
#### <a name="configuring-a-modal-dialog-box"></a><span data-ttu-id="2c09b-168">모달 대화 상자 구성</span><span class="sxs-lookup"><span data-stu-id="2c09b-168">Configuring a modal dialog box</span></span>

<span data-ttu-id="2c09b-169">일반 대화 상자의 사용자 인터페이스에는 다음이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="2c09b-169">The user interface for a typical dialog box includes the following:</span></span>  
  
- <span data-ttu-id="2c09b-170">원하는 데이터를 수집하는 데 필요한 다양한 컨트롤.</span><span class="sxs-lookup"><span data-stu-id="2c09b-170">The various controls that are required to gather the desired data.</span></span>  
  
- <span data-ttu-id="2c09b-171">사용자가 클릭 하 여 대화 상자를 닫고 함수로 돌아가서 처리를 계속 하는 **확인** 단추입니다.</span><span class="sxs-lookup"><span data-stu-id="2c09b-171">An **OK** button that users click to close the dialog box, return to the function, and continue processing.</span></span>  
  
- <span data-ttu-id="2c09b-172">사용자가 클릭 하 여 대화 상자를 닫고 추가 처리에서 함수를 중지 하는 **취소** 단추입니다.</span><span class="sxs-lookup"><span data-stu-id="2c09b-172">A **Cancel** button that users click to close the dialog box and stop the function from further processing.</span></span>  
  
- <span data-ttu-id="2c09b-173">제목 표시줄에 **닫기** 단추가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2c09b-173">A **Close** button in the title bar.</span></span>  
  
- <span data-ttu-id="2c09b-174">아이콘.</span><span class="sxs-lookup"><span data-stu-id="2c09b-174">An icon.</span></span>  
  
- <span data-ttu-id="2c09b-175">**최소화**, **최대화**및 **복원** 단추</span><span class="sxs-lookup"><span data-stu-id="2c09b-175">**Minimize**, **Maximize**, and **Restore** buttons.</span></span>  
  
- <span data-ttu-id="2c09b-176">대화 상자를 최소화, 최대화, 복원 및 닫기 위한 **시스템** 메뉴입니다.</span><span class="sxs-lookup"><span data-stu-id="2c09b-176">A **System** menu to minimize, maximize, restore, and close the dialog box.</span></span>  
  
- <span data-ttu-id="2c09b-177">대화 상자를 연 창의 가운데 및 위치입니다.</span><span class="sxs-lookup"><span data-stu-id="2c09b-177">A position above and in the center of the window that opened the dialog box.</span></span>  
  
- <span data-ttu-id="2c09b-178">가능 하면 크기를 조정 하 여 대화 상자가 너무 작지 않도록 하 고 사용자에 게 유용한 기본 크기를 제공 하는 기능입니다.</span><span class="sxs-lookup"><span data-stu-id="2c09b-178">The ability to be resized where possible to prevent the dialog box from being too small, and to provide the user with a useful default size.</span></span> <span data-ttu-id="2c09b-179">이렇게 하려면 기본값과 최소 차원을 모두 설정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2c09b-179">This requires that you set both the default and a minimum dimensions.</span></span>  
  
- <span data-ttu-id="2c09b-180">**취소** 단추를 누르는 바로 가기 키인 ESC 키입니다.</span><span class="sxs-lookup"><span data-stu-id="2c09b-180">The ESC key as a keyboard shortcut that causes the **Cancel** button to be pressed.</span></span> <span data-ttu-id="2c09b-181">이렇게 하려면 **취소** 단추의 <xref:System.Windows.Controls.Button.IsCancel%2A> 속성을 `true`로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="2c09b-181">You do this by setting the <xref:System.Windows.Controls.Button.IsCancel%2A> property of the **Cancel** button to `true`.</span></span>  
  
- <span data-ttu-id="2c09b-182">**확인** 단추를 누르는 바로 가기 키 인 ENTER 또는 RETURN 키입니다.</span><span class="sxs-lookup"><span data-stu-id="2c09b-182">The ENTER (or RETURN) key as a keyboard shortcut that causes the **OK** button to be pressed.</span></span> <span data-ttu-id="2c09b-183">**확인** 단추의 <xref:System.Windows.Controls.Button.IsDefault%2A> 속성을 `true`설정 하 여이 작업을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="2c09b-183">You do this by setting the <xref:System.Windows.Controls.Button.IsDefault%2A> property of the **OK** button `true`.</span></span>  
  
<span data-ttu-id="2c09b-184">다음 코드에서는 이 구성을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="2c09b-184">The following code demonstrates this configuration.</span></span>  
  
[!code-xaml[MarginsDialogBox XAML file](~/samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxSample/CSharp/MarginsDialogBox.xaml?range=1-16,106-112)]  

[!code-csharp[MarginsDialogBox C# code-behind](~/samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxSample/CSharp/MarginsDialogBox.xaml.cs?range=1-12,67-68)]
[!code-vb[MarginsDialogBox VB code-behind](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DialogBoxSample/VisualBasic/MarginsDialogBox.xaml.vb?range=1-11,61-62)]  
  
<span data-ttu-id="2c09b-185">대화 상자의 사용자 경험은 대화 상자를 여는 창의 메뉴 모음으로 확장됩니다.</span><span class="sxs-lookup"><span data-stu-id="2c09b-185">The user experience for a dialog box also extends into the menu bar of the window that opens the dialog box.</span></span> <span data-ttu-id="2c09b-186">메뉴 항목에서 함수를 계속하기 전에 대화 상자를 통한 사용자 상호 작용을 필요로 하는 함수를 실행하면, 함수의 메뉴 항목 헤더에 다음과 같이 줄임표가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="2c09b-186">When a menu item runs a function that requires user interaction through a dialog box before the function can continue, the menu item for the function will have an ellipsis in its header, as shown here.</span></span>  
  
[!code-xaml[Menu bar of MainWindow.Xaml file](~/samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxSample/CSharp/MainWindow.xaml#L26-L27)]  
  
<span data-ttu-id="2c09b-187">메뉴 항목에서 [정보] 대화 상자와 같이 사용자 상호 작용이 필요하지 않은 대화 상자를 표시하는 함수를 실행할 경우는 줄임표가 필요하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="2c09b-187">When a menu item runs a function that displays a dialog box which does not require user interaction, such as an About dialog box, an ellipsis is not required.</span></span>  
  
#### <a name="opening-a-modal-dialog-box"></a><span data-ttu-id="2c09b-188">모달 대화 상자 열기</span><span class="sxs-lookup"><span data-stu-id="2c09b-188">Opening a modal dialog box</span></span>

<span data-ttu-id="2c09b-189">대화 상자는 일반적으로 워드 프로세서에서 문서 여백을 설정하는 경우와 같이 사용자가 메뉴 항목을 선택하여 도메인 관련 함수를 수행할 때 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="2c09b-189">A dialog box is typically shown as a result of a user selecting a menu item to perform a domain-specific function, such as setting the margins of a document in a word processor.</span></span> <span data-ttu-id="2c09b-190">추가 창을 대화 상자로 표시하는 것은 일반 창을 표시하는 것과 비슷하지만, 추가로 대화 상자 관련 구성이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="2c09b-190">Showing a window as a dialog box is similar to showing a normal window, although it requires additional dialog box-specific configuration.</span></span> <span data-ttu-id="2c09b-191">대화 상자를 인스턴스화하고, 구성하고, 여는 과정 전체가 다음 코드에 표시되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2c09b-191">The entire process of instantiating, configuring, and opening a dialog box is shown in the following code.</span></span>  
  
[!code-csharp[Opening a modal dialog box](~/samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxSample/CSharp/MainWindow.xaml.cs?range=1-11,78-88,193-195)]
[!code-vb[Opening a modal dialog box](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DialogBoxSample/VisualBasic/MainWindow.xaml.vb?range=1-9,58-67,130-132)]  

<span data-ttu-id="2c09b-192">여기서 코드는 대화 상자에 기본 정보 (현재 여백)를 전달 합니다.</span><span class="sxs-lookup"><span data-stu-id="2c09b-192">Here, the code passes default information (the current margins) to the dialog box.</span></span> <span data-ttu-id="2c09b-193">또한 대화 상자를 표시 하는 창에 대 한 참조를 사용 하 여 <xref:System.Windows.Window.Owner%2A?displayProperty=nameWithType> 속성을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="2c09b-193">It also sets the <xref:System.Windows.Window.Owner%2A?displayProperty=nameWithType> property with a reference to the window that is showing the dialog box.</span></span> <span data-ttu-id="2c09b-194">일반적으로 모든 대화 상자에 공통적인 창 상태 관련 동작을 제공 하려면 항상 대화 상자 소유자를 설정 해야 합니다 (자세한 내용은 [WPF 창 개요](wpf-windows-overview.md) 참조).</span><span class="sxs-lookup"><span data-stu-id="2c09b-194">In general, you should always set the owner for a dialog box to provide window state-related behaviors that are common to all dialog boxes (see [WPF Windows Overview](wpf-windows-overview.md) for more information).</span></span>

> [!NOTE]
> <span data-ttu-id="2c09b-195">대화 상자에 대 한 UI (사용자 인터페이스) 자동화를 지원 하려면 소유자를 제공 해야 합니다 ( [Ui 자동화 개요](../../ui-automation/ui-automation-overview.md)참조).</span><span class="sxs-lookup"><span data-stu-id="2c09b-195">You must provide an owner to support user interface (UI) automation for dialog boxes (see [UI Automation Overview](../../ui-automation/ui-automation-overview.md)).</span></span>

<span data-ttu-id="2c09b-196">대화 상자가 구성 된 후에는 <xref:System.Windows.Window.ShowDialog%2A> 메서드를 호출 하 여 모달로 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2c09b-196">After the dialog box is configured, it is shown modally by calling the <xref:System.Windows.Window.ShowDialog%2A> method.</span></span>  
  
#### <a name="validating-user-provided-data"></a><span data-ttu-id="2c09b-197">사용자 제공 데이터의 유효성 검사</span><span class="sxs-lookup"><span data-stu-id="2c09b-197">Validating user-provided data</span></span>

<span data-ttu-id="2c09b-198">대화 상자가 열리고 사용자가 필요한 데이터를 제공할 때, 다음과 같은 이유로 대화 상자에서 제공된 데이터가 유효한지 확인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2c09b-198">When a dialog box is opened and the user provides the required data, a dialog box is responsible for ensuring that the provided data is valid for the following reasons:</span></span>  
  
- <span data-ttu-id="2c09b-199">보안 관점에서, 모든 입력이 유효해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2c09b-199">From a security perspective, all input should be validated.</span></span>  
  
- <span data-ttu-id="2c09b-200">도메인 관련 관점에서, 데이터의 유효성을 검사하면 코드에서 잘못된 데이터를 처리하여 예외를 일으키는 것을 방지할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2c09b-200">From a domain-specific perspective, data validation prevents erroneous data from being processed by the code, which could potentially throw exceptions.</span></span>  
  
- <span data-ttu-id="2c09b-201">사용자 경험 관점에서, 대화 상자는 사용자가 입력한 데이터 중에 어느 것이 유효한지 표시하여 사용자를 도울 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2c09b-201">From a user-experience perspective, a dialog box can help users by showing them which data they have entered is invalid.</span></span>  
  
- <span data-ttu-id="2c09b-202">성능 관점에서, 다중 계층 애플리케이션의 데이터 유효성 검사를 수행하면 클라이언트와 애플리케이션 계층 사이의 왕복 횟수를 줄일 수 있으며 특히 애플리케이션이 웹 서비스나 서버 기반 데이터베이스로 구성된 경우에 효과가 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="2c09b-202">From a performance perspective, data validation in a multi-tier application can reduce the number of round trips between the client and the application tiers, particularly when the application is composed of Web services or server-based databases.</span></span>  

<span data-ttu-id="2c09b-203">WPF에서 바인딩된 컨트롤의 유효성을 검사 하려면 유효성 검사 규칙을 정의 하 고 바인딩과 연결 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2c09b-203">To validate a bound control in WPF, you need to define a validation rule and associate it with the binding.</span></span> <span data-ttu-id="2c09b-204">유효성 검사 규칙은 <xref:System.Windows.Controls.ValidationRule>에서 파생 되는 사용자 지정 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="2c09b-204">A validation rule is a custom class that derives from <xref:System.Windows.Controls.ValidationRule>.</span></span> <span data-ttu-id="2c09b-205">다음 예제에서는 바인딩된 값이 <xref:System.Double> 이며 지정 된 범위 내에 있는지 확인 하는 유효성 검사 규칙 `MarginValidationRule`를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="2c09b-205">The following example shows a validation rule, `MarginValidationRule`, which checks that a bound value is a <xref:System.Double> and is within a specified range.</span></span>  

[!code-csharp[Margin validation rules](~/samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxSample/CSharp/MarginValidationRule.cs)]
[!code-vb[Margin validation rules](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DialogBoxSample/VisualBasic/MarginValidationRule.vb)]  

<span data-ttu-id="2c09b-206">이 코드에서 유효성 검사 규칙의 유효성 검사 논리는 데이터의 유효성을 검사 하 고 적절 한 <xref:System.Windows.Controls.ValidationResult>을 반환 하는 <xref:System.Windows.Controls.ValidationRule.Validate%2A> 메서드를 재정의 하 여 구현 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2c09b-206">In this code, the validation logic of a validation rule is implemented by overriding the <xref:System.Windows.Controls.ValidationRule.Validate%2A> method, which validates the data and returns an appropriate <xref:System.Windows.Controls.ValidationResult>.</span></span>  

<span data-ttu-id="2c09b-207">유효성 검사 규칙을 바인딩 컨트롤과 연결하려면 다음과 같은 표시를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="2c09b-207">To associate the validation rule with the bound control, you use the following markup.</span></span>  
  
[!code-xaml[Associating a validation rule with a control](~/samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxSample/CSharp/MarginsDialogBox.xaml?range=1-16,57-68,111-112)]

<span data-ttu-id="2c09b-208">유효성 검사 규칙이 연결 되 면 바인딩된 컨트롤에 데이터를 입력할 때 WPF가 자동으로 적용 합니다.</span><span class="sxs-lookup"><span data-stu-id="2c09b-208">Once the validation rule is associated, WPF will automatically apply it when data is entered into the bound control.</span></span> <span data-ttu-id="2c09b-209">컨트롤에 잘못 된 데이터가 포함 되어 있는 경우 WPF는 다음 그림과 같이 잘못 된 컨트롤 주위에 빨간색 테두리를 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="2c09b-209">When a control contains invalid data, WPF will display a red border around the invalid control, as shown in the following figure.</span></span>  
  
![잘못 된 왼쪽 여백 값 주위에 빨간색 테두리가 있는 여백 대화 상자입니다.](./media/dialog-boxes-overview/invalid-left-margin-dialog.png)  

<span data-ttu-id="2c09b-211">WPF는 유효한 데이터를 입력할 때까지 사용자를 잘못 된 컨트롤로 제한 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="2c09b-211">WPF does not restrict a user to the invalid control until they have entered valid data.</span></span> <span data-ttu-id="2c09b-212">대화 상자에서 좋은 동작입니다. 사용자는 데이터의 유효성에 관계없이 대화 상자에서 컨트롤을 자유롭게 탐색할 수 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2c09b-212">This is good behavior for a dialog box; a user should be able to freely navigate the controls in a dialog box whether or not data is valid.</span></span> <span data-ttu-id="2c09b-213">그러나이는 사용자가 잘못 된 데이터를 입력 하 고 **확인** 단추를 누를 수 있음을 의미 합니다.</span><span class="sxs-lookup"><span data-stu-id="2c09b-213">However, this means a user can enter invalid data and press the **OK** button.</span></span> <span data-ttu-id="2c09b-214">따라서 코드는 <xref:System.Windows.Controls.Primitives.ButtonBase.Click> 이벤트를 처리 하 여 **확인** 단추를 누를 때 대화 상자에 있는 모든 컨트롤의 유효성을 검사 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2c09b-214">For this reason, your code also needs to validate all controls in a dialog box when the **OK** button is pressed by handling the <xref:System.Windows.Controls.Primitives.ButtonBase.Click> event.</span></span>  
  
[!code-csharp[Validating all controls in a dialog box](~/samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxSample/CSharp/MarginsDialogBox.xaml.cs?range=1-8,26-29,33-68)]
[!code-vb[Validating all controls in a dialog box](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DialogBoxSample/VisualBasic/MarginsDialogBox.xaml.vb?range=1-8,27-29,33-62)]  

<span data-ttu-id="2c09b-215">이 코드는 창에 있는 모든 종속성 개체를 열거 하 고, 잘못 된 경우 (<xref:System.Windows.Controls.Validation.GetHasError%2A>에서 반환 되는 것과 같이 잘못 된 컨트롤이 포커스를 가져오고 `IsValid` 메서드가 `false`을 반환 하 고 창이 잘못 된 것으로 간주 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2c09b-215">This code enumerates all dependency objects on a window and, if any are invalid (as returned by <xref:System.Windows.Controls.Validation.GetHasError%2A>, the invalid control gets the focus, the `IsValid` method returns `false`, and the window is considered invalid.</span></span>  
  
<span data-ttu-id="2c09b-216">대화 상자가 유효하면 안전하게 닫고 반환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2c09b-216">Once a dialog box is valid, it can safely close and return.</span></span> <span data-ttu-id="2c09b-217">반환 과정의 일부로서 결과를 호출 함수에 반환해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2c09b-217">As part of the return process, it needs to return a result to the calling function.</span></span>  
  
#### <a name="setting-the-modal-dialog-result"></a><span data-ttu-id="2c09b-218">모달 대화 상자 결과 설정</span><span class="sxs-lookup"><span data-stu-id="2c09b-218">Setting the modal dialog result</span></span>

<span data-ttu-id="2c09b-219"><xref:System.Windows.Window.ShowDialog%2A>를 사용 하 여 대화 상자를 여는 것은 기본적으로 메서드를 호출 하는 것과 같습니다. <xref:System.Windows.Window.ShowDialog%2A>를 사용 하 여 대화 상자를 연 코드는 <xref:System.Windows.Window.ShowDialog%2A> 반환 될 때까지</span><span class="sxs-lookup"><span data-stu-id="2c09b-219">Opening a dialog box using <xref:System.Windows.Window.ShowDialog%2A> is fundamentally like calling a method: the code that opened the dialog box using <xref:System.Windows.Window.ShowDialog%2A> waits until <xref:System.Windows.Window.ShowDialog%2A> returns.</span></span> <span data-ttu-id="2c09b-220"><xref:System.Windows.Window.ShowDialog%2A> 반환 될 때 사용자가 **확인** 단추를 눌렀는지 아니면 **취소** 단추를 눌렀는지에 따라 호출 하는 코드에서 처리를 계속할지 아니면 처리를 중지할지를 결정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2c09b-220">When <xref:System.Windows.Window.ShowDialog%2A> returns, the code that called it needs to decide whether to continue processing or stop processing, based on whether the user pressed the **OK** button or the **Cancel** button.</span></span> <span data-ttu-id="2c09b-221">이 결정을 용이 하 게 하기 위해 대화 상자에서 사용자의 선택 항목을 <xref:System.Windows.Window.ShowDialog%2A> 메서드에서 반환 되는 <xref:System.Boolean> 값으로 반환 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2c09b-221">To facilitate this decision, the dialog box needs to return the user's choice as a <xref:System.Boolean> value that is returned from the <xref:System.Windows.Window.ShowDialog%2A> method.</span></span>  

<span data-ttu-id="2c09b-222">**확인** 단추를 클릭 하면 <xref:System.Windows.Window.ShowDialog%2A> `true`를 반환 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2c09b-222">When the **OK** button is clicked, <xref:System.Windows.Window.ShowDialog%2A> should return `true`.</span></span> <span data-ttu-id="2c09b-223">**확인** 단추를 클릭 하면 대화 상자의 <xref:System.Windows.Window.DialogResult%2A> 속성을 설정 하 여이를 달성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2c09b-223">This is achieved by setting the <xref:System.Windows.Window.DialogResult%2A> property of the dialog box when the **OK** button is clicked.</span></span>  

[!code-csharp[Responding to the OK button](~/samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxSample/CSharp/MarginsDialogBox.xaml.cs?range=1-8,25-27,32-33,67-68)]
[!code-vb[Responding to the OK button](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DialogBoxSample/VisualBasic/MarginsDialogBox.xaml.vb?range=1-8,27,31-33,61-62)]  

<span data-ttu-id="2c09b-224"><xref:System.Windows.Window.DialogResult%2A> 속성을 설정 하면 창이 자동으로 닫히고 <xref:System.Windows.Window.Close%2A>를 명시적으로 호출 해야 하는 필요성이 줄어듭니다.</span><span class="sxs-lookup"><span data-stu-id="2c09b-224">Note that setting the <xref:System.Windows.Window.DialogResult%2A> property also causes the window to close automatically, which alleviates the need to explicitly call <xref:System.Windows.Window.Close%2A>.</span></span>  
  
<span data-ttu-id="2c09b-225">**취소** 단추를 클릭 하면 <xref:System.Windows.Window.ShowDialog%2A> `false`를 반환 해야 합니다 .이 경우에도 <xref:System.Windows.Window.DialogResult%2A> 속성을 설정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2c09b-225">When the **Cancel** button is clicked, <xref:System.Windows.Window.ShowDialog%2A> should return `false`, which also requires setting the <xref:System.Windows.Window.DialogResult%2A> property.</span></span>  
  
[!code-csharp[Responding to the Cancel button](~/samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxSample/CSharp/MarginsDialogBox.xaml.cs?range=1-8,19-24,67-68)]
[!code-vb[Responding to the Cancel button](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DialogBoxSample/VisualBasic/MarginsDialogBox.xaml.vb?range=1-8,22-25,61-62)]  

<span data-ttu-id="2c09b-226">단추의 <xref:System.Windows.Controls.Button.IsCancel%2A> 속성이 `true`로 설정 되 고 사용자가 **취소** 단추나 ESC 키를 누르면 <xref:System.Windows.Window.DialogResult%2A>가 자동으로 `false`로 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2c09b-226">When a button's <xref:System.Windows.Controls.Button.IsCancel%2A> property is set to `true` and the user presses either the **Cancel** button or the ESC key, <xref:System.Windows.Window.DialogResult%2A> is automatically set to `false`.</span></span> <span data-ttu-id="2c09b-227">다음 태그는 <xref:System.Windows.Controls.Primitives.ButtonBase.Click> 이벤트를 처리할 필요 없이 이전 코드와 동일한 효과를 가집니다.</span><span class="sxs-lookup"><span data-stu-id="2c09b-227">The following markup has the same effect as the preceding code, without the need to handle the <xref:System.Windows.Controls.Primitives.ButtonBase.Click> event.</span></span>  
  
[!code-xaml[Markup instead of handling the Click event](~/samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxSample/CSharp/MarginsDialogBox.xaml#L109-L109)]  

<span data-ttu-id="2c09b-228">사용자가 제목 표시줄에서 **닫기** 단추를 누르거나 **시스템** 메뉴에서 **닫기** 메뉴 항목을 선택 하면 대화 상자가 `false` 자동으로 반환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2c09b-228">A dialog box automatically returns `false` when a user presses the **Close** button in the title bar or chooses the **Close** menu item from the **System** menu.</span></span>  

#### <a name="processing-data-returned-from-a-modal-dialog-box"></a><span data-ttu-id="2c09b-229">모달 대화 상자에서 반환 된 데이터 처리</span><span class="sxs-lookup"><span data-stu-id="2c09b-229">Processing data returned from a modal dialog box</span></span>  

<span data-ttu-id="2c09b-230">대화 상자에서 <xref:System.Windows.Window.DialogResult%2A>를 설정 하는 경우이를 연 함수는 <xref:System.Windows.Window.ShowDialog%2A> 반환 될 때 <xref:System.Windows.Window.DialogResult%2A> 속성을 검사 하 여 대화 상자 결과를 가져올 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2c09b-230">When <xref:System.Windows.Window.DialogResult%2A> is set by a dialog box, the function that opened it can get the dialog box result by inspecting the <xref:System.Windows.Window.DialogResult%2A> property when <xref:System.Windows.Window.ShowDialog%2A> returns.</span></span>  
  
[!code-csharp[Processing data returned from the modal dialog box](~/samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxSample/CSharp/MainWindow.xaml.cs?range=1-10,77-79,89-96,194-195)]
[!code-vb[Processing data returned from the modal dialog box](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DialogBoxSample/VisualBasic/MainWindow.xaml.vb?range=1-9,58,69-73,131-132)]

<span data-ttu-id="2c09b-231">대화 상자 결과가 `true`경우이 함수는 해당 사용자가 제공 하는 데이터를 검색 하 고 처리 하는 큐로이를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="2c09b-231">If the dialog result is `true`, the function uses that as a cue to retrieve and process the data provided by the user.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="2c09b-232"><xref:System.Windows.Window.ShowDialog%2A> 반환 된 후에는 대화 상자를 다시 열 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="2c09b-232">After <xref:System.Windows.Window.ShowDialog%2A> has returned, a dialog box cannot be reopened.</span></span> <span data-ttu-id="2c09b-233">대신 새 인스턴스를 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2c09b-233">Instead, you need to create a new instance.</span></span>

<span data-ttu-id="2c09b-234">대화 상자 결과가 `false`경우 함수는 처리를 적절 하 게 종료 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2c09b-234">If the dialog result is `false`, the function should end processing appropriately.</span></span>  
  
<a name="Creating_a_Modeless_Custom_Dialog_Box"></a>   
### <a name="creating-a-modeless-custom-dialog-box"></a><span data-ttu-id="2c09b-235">모덜리스 사용자 지정 대화 상자 만들기</span><span class="sxs-lookup"><span data-stu-id="2c09b-235">Creating a modeless custom dialog box</span></span>

<span data-ttu-id="2c09b-236">다음 그림의 찾기 대화 상자와 같은 모덜리스 대화 상자는 기본적인 모양이 모덜 대화 상자와 같습니다.</span><span class="sxs-lookup"><span data-stu-id="2c09b-236">A modeless dialog box, such as the Find Dialog Box shown in the following figure, has the same fundamental appearance as the modal dialog box.</span></span>  

![찾기 대화 상자를 표시 하는 스크린샷](./media/dialog-boxes-overview/find-modeless-dialog-box.png)  

<span data-ttu-id="2c09b-238">그러나 다음 섹션에 설명된 것처럼 동작은 약간 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="2c09b-238">However, the behavior is slightly different, as described in the following sections.</span></span>  
  
#### <a name="opening-a-modeless-dialog-box"></a><span data-ttu-id="2c09b-239">모덜리스 대화 상자 열기</span><span class="sxs-lookup"><span data-stu-id="2c09b-239">Opening a modeless dialog box</span></span>

<span data-ttu-id="2c09b-240">모덜리스 대화 상자는 <xref:System.Windows.Window.Show%2A> 메서드를 호출 하 여 열립니다.</span><span class="sxs-lookup"><span data-stu-id="2c09b-240">A modeless dialog box is opened by calling the <xref:System.Windows.Window.Show%2A> method.</span></span>  

[!code-xaml[XAML to define a modeless dialog box](~/samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxSample/CSharp/MainWindow.xaml#L21-L22)]  
 
[!code-csharp[Opening a modeless dialog box](~/samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxSample/CSharp/MainWindow.xaml.cs?range=1-10,65-76,194-195)]
[!code-vb[Openng a modeless dialog box](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DialogBoxSample/VisualBasic/MainWindow.xaml.vb?range=1-9,18-23,131,132)]  

<span data-ttu-id="2c09b-241"><xref:System.Windows.Window.ShowDialog%2A>와 달리 <xref:System.Windows.Window.Show%2A>는 즉시 반환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2c09b-241">Unlike <xref:System.Windows.Window.ShowDialog%2A>, <xref:System.Windows.Window.Show%2A> returns immediately.</span></span> <span data-ttu-id="2c09b-242">따라서 호출하는 창에서는 모덜리스 대화 상자가 닫히는 시기를 알 수 없기 때문에 대화 상자의 결과를 검사하거나 대화 상자에서 더 처리할 데이터를 가져올 시기를 알 수가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="2c09b-242">Consequently, the calling window cannot tell when the modeless dialog box is closed and, therefore, does not know when to check for a dialog box result or get data from the dialog box for further processing.</span></span> <span data-ttu-id="2c09b-243">대신, 대화 상자에서 호출한 창에 처리할 데이터를 반환할 다른 방법을 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2c09b-243">Instead, the dialog box needs to create an alternative way to return data to the calling window for processing.</span></span>  
  
#### <a name="processing-data-returned-from-a-modeless-dialog-box"></a><span data-ttu-id="2c09b-244">모덜리스 대화 상자에서 반환 된 데이터 처리</span><span class="sxs-lookup"><span data-stu-id="2c09b-244">Processing data returned from a modeless dialog box</span></span>  

<span data-ttu-id="2c09b-245">이 예에서 `FindDialogBox`은 특정 빈도 없이 검색 되는 텍스트에 따라 주 창에 하나 이상의 찾기 결과를 반환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2c09b-245">In this example, the `FindDialogBox` may return one or more find results to the main window, depending on the text being searched for without any specific frequency.</span></span> <span data-ttu-id="2c09b-246">모달 대화 상자와 마찬가지로, 모덜리스 대화 상자에서도 속성을 사용하여 결과를 반환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2c09b-246">As with a modal dialog box, a modeless dialog box can return results using properties.</span></span> <span data-ttu-id="2c09b-247">그러나 대화 상자를 소유한 창에서 해당 속성을 검사할 시기를 알아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2c09b-247">However, the window that owns the dialog box needs to know when to check those properties.</span></span> <span data-ttu-id="2c09b-248">한 가지 방법은 대화 상자에서 텍스트를 찾을 때마다 발생하는 이벤트를 구현하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="2c09b-248">One way to enable this is for the dialog box to implement an event that is raised whenever text is found.</span></span> <span data-ttu-id="2c09b-249">`FindDialogBox`는이 목적을 위해 먼저 대리자가 필요한 `TextFoundEvent`을 구현 합니다.</span><span class="sxs-lookup"><span data-stu-id="2c09b-249">`FindDialogBox` implements the `TextFoundEvent` for this purpose, which first requires a delegate.</span></span>  

[!code-csharp[The TextFoundEventHandler delegate](~/samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxSample/CSharp/TextFoundEventHandler.cs)]
[!code-vb[The TextFoundEventHandler delegate](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DialogBoxSample/VisualBasic/TextFoundEventHandler.vb)]  

<span data-ttu-id="2c09b-250">`TextFoundEventHandler` 대리자를 사용 하 여 `TextFoundEvent`를 구현 `FindDialogBox`.</span><span class="sxs-lookup"><span data-stu-id="2c09b-250">Using the `TextFoundEventHandler` delegate, `FindDialogBox` implements the `TextFoundEvent`.</span></span>
  
[!code-csharp[The TextFound event](~/samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxSample/CSharp/FindDialogBox.xaml.cs?range=1-17,125-126)]
[!code-vb[The TextFound event](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DialogBoxSample/VisualBasic/FindDialogBox.xaml.vb?range=1-15,102-103)]

<span data-ttu-id="2c09b-251">따라서 검색 결과가 발견 될 때 이벤트를 발생 시킬 수 `Find`.</span><span class="sxs-lookup"><span data-stu-id="2c09b-251">Consequently, `Find` can raise the event when a search result is found.</span></span>  
  
[!code-csharp[Raising the TextFound event](~/samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxSample/CSharp/FindDialogBox.xaml.cs?range=1-9,50-52,91-94,124-127)]
[!code-vb[Raising the TextFound event](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DialogBoxSample/VisualBasic/FindDialogBox.xaml.vb?range=1-9,15,60-64,102-103)]  

<span data-ttu-id="2c09b-252">소유자 창에서는 그 후에 이 이벤트를 등록하고 처리해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2c09b-252">The owner window then needs to register with and handle this event.</span></span>

[!code-csharp[Registering and handling the event](~/samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxSample/CSharp/MainWindow.xaml.cs?range=1-10,184-195)]
[!code-vb[Registering and handling the event](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DialogBoxSample/VisualBasic/MainWindow.xaml.vb?range=1-9,126-132)]  

#### <a name="closing-a-modeless-dialog-box"></a><span data-ttu-id="2c09b-253">모덜리스 대화 상자 닫기</span><span class="sxs-lookup"><span data-stu-id="2c09b-253">Closing a modeless dialog box</span></span>

<span data-ttu-id="2c09b-254"><xref:System.Windows.Window.DialogResult%2A>를 설정할 필요가 없기 때문에 다음과 같은 시스템 제공 메커니즘을 사용 하 여 모덜리스 대화 상자를 닫을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2c09b-254">Because <xref:System.Windows.Window.DialogResult%2A> does not need to be set, a modeless dialog can be closed using system provide mechanisms, including the following:</span></span>  
  
- <span data-ttu-id="2c09b-255">제목 표시줄에서 **닫기** 단추를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="2c09b-255">Clicking the **Close** button in the title bar.</span></span>  
  
- <span data-ttu-id="2c09b-256">ALT+F4를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="2c09b-256">Pressing ALT+F4.</span></span>  
  
- <span data-ttu-id="2c09b-257">**시스템** 메뉴에서 **닫기** 를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="2c09b-257">Choosing **Close** from the **System** menu.</span></span>  
  
<span data-ttu-id="2c09b-258">또는 **닫기** 단추를 클릭할 때 코드가 <xref:System.Windows.Window.Close%2A>를 호출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2c09b-258">Alternatively, your code can call <xref:System.Windows.Window.Close%2A> when the **Close** button is clicked.</span></span>  

[!code-csharp[Calling the Close method](~/samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxSample/CSharp/FindDialogBox.xaml.cs?range=1-9,119-126)]
[!code-vb[Calling the Close method](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DialogBoxSample/VisualBasic/FindDialogBox.xaml.vb?range=1-9,99-103)]  

## <a name="see-also"></a><span data-ttu-id="2c09b-259">참고 항목</span><span class="sxs-lookup"><span data-stu-id="2c09b-259">See also</span></span>

- [<span data-ttu-id="2c09b-260">팝업 개요</span><span class="sxs-lookup"><span data-stu-id="2c09b-260">Popup Overview</span></span>](../controls/popup-overview.md)
- [<span data-ttu-id="2c09b-261">대화 상자 샘플</span><span class="sxs-lookup"><span data-stu-id="2c09b-261">Dialog Box Sample</span></span>](https://github.com/Microsoft/WPF-Samples/tree/master/Windows/DialogBox)
