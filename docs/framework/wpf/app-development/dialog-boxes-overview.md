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
ms.openlocfilehash: c98d6a45d151d4b683a21e48eaeb5f4a19eaadb1
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79187448"
---
# <a name="dialog-boxes-overview"></a>대화 상자 개요
독립 실행형 응용 프로그램에는 일반적으로 응용 프로그램이 작동하는 주 데이터를 표시하고 메뉴 모음, 도구 [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] 모음 및 상태 표시줄과 같은 메커니즘을 통해 해당 데이터를 처리하는 기능을 노출하는 주 창이 있습니다. 특수 애플리케이션에는 다음을 수행하는 추가 창이 표시될 수도 있습니다.  
  
- 사용자에게 특정 정보 표시.  
  
- 사용자로부터 정보 수집.  
  
- 정보 표시 및 수집.  
  
 이러한 유형의 창은 *대화 상자라고*하며 모달과 모덜리스의 두 가지 유형이 있습니다.  
  
 기능을 계속하려면 사용자의 추가 데이터가 필요한 경우 *모달* 대화 상자가 함수에 의해 표시됩니다. 함수가 작동하려면 모달 대화 상자를 통해 데이터를 수집해야 하기 때문에, 모달 대화 상자가 열려 있는 동안에는 사용자가 다른 창을 활성화할 수 없습니다. 대부분의 경우 모달 대화 상자를 사용하면 **확인** 또는 **취소** 버튼을 눌러 모달 대화 상자를 완료하면 사용자가 신호를 알 릴 수 있습니다. **확인** 버튼을 누르면 사용자가 데이터를 입력했으며 해당 데이터로 계속 처리되도록 하려는 것을 나타냅니다. **취소** 버튼을 누르면 사용자가 함수가 완전히 실행되지 않도록 중지하려고 합니다. 데이터를 열고, 저장하고, 인쇄하는 가장 일반적인 모달 대화 상자의 예가 나와 있습니다.  
  
 반면에 *모덜리스* 대화 상자는 열려 있는 동안 사용자가 다른 창을 활성화하는 것을 방지하지 않습니다. 예를 들어, 사용자가 문서에서 특정 단어를 찾으려고 할 때 주 창에서 사용자가 찾으려는 단어를 입력할 대화 상자를 열 때가 많습니다. 단어를 찾는다고 해서 사용자가 문서를 편집하지 못하게 되는 것은 아니기 때문에 대화 상자를 모덜로 설정할 필요가 없습니다. 모덜리스 대화 상자는 적어도 대화 상자를 닫는 **닫기** 단추를 제공하며 다음 **찾기** 단추와 같은 특정 기능을 실행하는 추가 단추를 제공하여 단어 검색의 찾기 기준과 일치하는 다음 단어를 찾을 수 있습니다.  
  
 WPF(Windows 프레젠테이션 기반)를 사용하면 메시지 상자, 공통 대화 상자 및 사용자 지정 대화 상자를 비롯한 여러 유형의 대화 상자를 만들 수 있습니다. 이 항목에서는 각각에 대해 설명하고 [대화 상자 샘플에서는](https://github.com/Microsoft/WPF-Samples/tree/master/Windows/DialogBox) 일치하는 예제를 제공합니다.  

<a name="Message_Boxes"></a>
## <a name="message-boxes"></a>메시지 상자  
 *메시지 상자는* 텍스트 정보를 표시하고 사용자가 단추로 의사 결정을 내릴 수 있도록 하는 데 사용할 수 있는 대화 상자입니다. 다음 그림에는 텍스트 정보를 표시하고, 질문을 하고, 질문에 대답할 때 사용할 세 개의 단추를 사용자에게 제공하는 메시지 상자가 있습니다.  
  
 ![응용 프로그램이 닫히기 전에 변경 내용을 문서에 저장할지 묻는 Word Processor 대화 상자입니다.](./media/dialog-boxes-overview/word-processor-dialog.png)  
  
 메시지 상자를 만들려면 클래스를 <xref:System.Windows.MessageBox> 사용합니다. <xref:System.Windows.MessageBox>을 사용하면 다음과 같은 코드를 사용하여 메시지 상자 텍스트, 제목, 아이콘 및 단추를 구성할 수 있습니다.  
  
 [!code-csharp[DialogBoxesOverviewSnippets#MsgBoxConfigureCODEBEHIND](~/samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxesOverviewSnippets/CSharp/Window1.xaml.cs#msgboxconfigurecodebehind)]
 [!code-vb[DialogBoxesOverviewSnippets#MsgBoxConfigureCODEBEHIND](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DialogBoxesOverviewSnippets/VisualBasic/window1.xaml.vb#msgboxconfigurecodebehind)]  
  
 메시지 상자를 표시하려면 다음 `static` <xref:System.Windows.MessageBox.Show%2A> 코드에서 설명한 대로 메서드를 호출합니다.  
  
 [!code-csharp[DialogBoxesOverviewSnippets#MsgBoxShowCODEBEHIND](~/samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxesOverviewSnippets/CSharp/Window1.xaml.cs#msgboxshowcodebehind)]
 [!code-vb[DialogBoxesOverviewSnippets#MsgBoxShowCODEBEHIND](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DialogBoxesOverviewSnippets/VisualBasic/window1.xaml.vb#msgboxshowcodebehind)]  
  
 메시지 상자를 표시하는 코드로 사용자의 결정을 감지하고 처리해야 할 경우는(단추 누름) 다음 코드에서와 같이 코드를 통해 메시지 상자 결과를 검사할 수 있습니다.  
  
 [!code-csharp[DialogBoxesOverviewSnippets#MsgBoxShowAndResultCODEBEHIND1](~/samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxesOverviewSnippets/CSharp/Window1.xaml.cs#msgboxshowandresultcodebehind1)]
 [!code-vb[DialogBoxesOverviewSnippets#MsgBoxShowAndResultCODEBEHIND1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DialogBoxesOverviewSnippets/VisualBasic/window1.xaml.vb#msgboxshowandresultcodebehind1)]  
  
 메시지 상자 사용에 대한 자세한 <xref:System.Windows.MessageBox>내용은 ' [MessageBox 샘플](https://github.com/Microsoft/WPF-Samples/tree/master/Windows/MessageBox)및 [대화 상자 샘플](https://github.com/Microsoft/WPF-Samples/tree/master/Windows/DialogBox)을 참조하십시오.  
  
 간단한 <xref:System.Windows.MessageBox> 대화 상자 사용자 환경을 제공할 수 있지만 <xref:System.Windows.MessageBox> XAML 브라우저 응용 프로그램(XBAPs)과 같은 부분 신뢰 보안 샌드박스(보안 참조) 내에서 실행되는 응용 프로그램에서 표시할 수 있는 유일한 창 유형이라는 장점이 있습니다. [Security](../security-wpf.md)  
  
 대부분의 대화 상자는 텍스트, 선택(확인란), 상호 배타적인 선택(라디오 단추), 목록 선택(목록 상자, 콤보 상자, 드롭다운 목록 상자)과 같이 메시지 상자의 결과보다 복잡한 데이터를 표시하고 수집합니다. WPF(Windows 프레젠테이션 Foundation)는 몇 가지 일반적인 대화 상자를 제공하고 사용자 고유의 대화 상자를 만들 수 있지만 둘 중 하나를 완전히 신뢰로 실행하는 응용 프로그램으로 제한됩니다.  
  
<a name="Common_Dialogs"></a>
## <a name="common-dialog-boxes"></a>일반적인 대화 상자  
 Windows는 파일 열기, 파일 저장 및 인쇄를 위한 대화 상자를 포함하여 모든 응용 프로그램에 공통적인 다양한 재사용 가능한 대화 상자를 구현합니다. 이러한 대화 상자는 운영 체제에서 구현되므로 운영 체제에서 실행되는 모든 애플리케이션에서 공유할 수 있어 사용자 경험의 일관성에 도움이 됩니다. 운영 체제에서 제공되는 대화 상자를 사용자가 한 애플리케이션에서 익히고 나면 다른 애플리케이션에서 대화 상자의 사용 방법을 다시 익힐 필요가 없습니다. 이러한 대화 상자는 모든 응용 프로그램에서 사용할 수 있으며 일관된 사용자 환경을 제공하는 데 도움이 되므로 *일반적인 대화 상자라고 합니다.*  
  
 WPF(Windows 프레젠테이션 Foundation)는 열려 있는 파일을 캡슐화하고 파일을 저장하며 공통 대화 상자를 인쇄하여 독립 실행형 응용 프로그램에서 사용할 수 있는 관리되는 클래스로 노출합니다. 이 항목에서는 각각의 개요를 간략하게 제공합니다.  
  
<a name="Open_File_Dialog"></a>
### <a name="open-file-dialog"></a>파일 대화 상자 열기  
 다음 그림에 표시된 파일 열기 대화 상자는 파일 열기 기능에서 열려는 파일의 이름을 검색할 때 사용됩니다.  
  
 ![파일을 검색할 위치를 보여주는 열기 대화 상자입니다.](./media/dialog-boxes-overview/open-file-dialog-box.png)  
  
 공통 파일 대화 상자는 <xref:Microsoft.Win32.OpenFileDialog> 클래스로 구현되며 네임스페이스에 <xref:Microsoft.Win32> 있습니다. 다음 코드에서는 코드를 만들고 구성 및 표시하는 방법과 결과를 처리하는 방법을 보여 줍니다.  
  
 [!code-csharp[DialogBoxesOverviewSnippets#OpenFileDialogBoxCODEBEHIND](~/samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxesOverviewSnippets/CSharp/Window1.xaml.cs#openfiledialogboxcodebehind)]
 [!code-vb[DialogBoxesOverviewSnippets#OpenFileDialogBoxCODEBEHIND](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DialogBoxesOverviewSnippets/VisualBasic/window1.xaml.vb#openfiledialogboxcodebehind)]  
  
 열려 있는 파일 대화 상자에 대한 <xref:Microsoft.Win32.OpenFileDialog?displayProperty=nameWithType>자세한 내용은 을 참조하십시오.  
  
> [!NOTE]
> <xref:Microsoft.Win32.OpenFileDialog>부분 신뢰로 실행 중인 응용 프로그램에서 파일 이름을 안전하게 검색하는 데 사용할 수 [있습니다(보안](../security-wpf.md)참조).  
  
<a name="Save_File_Dialog"></a>
### <a name="save-file-dialog-box"></a>파일 저장 대화 상자  
 다음 그림에 표시된 파일 저장 대화 상자는 파일 저장 기능에서 저장하려는 파일의 이름을 검색할 때 사용됩니다.  
  
 ![파일을 저장할 위치를 보여주는 대화 상자로 저장합니다.](./media/dialog-boxes-overview/save-file-dialog-box.png)  
  
 공통 저장 파일 대화 상자는 <xref:Microsoft.Win32.SaveFileDialog> 클래스로 구현되며 네임스페이스에 <xref:Microsoft.Win32> 있습니다. 다음 코드에서는 코드를 만들고 구성 및 표시하는 방법과 결과를 처리하는 방법을 보여 줍니다.  
  
 [!code-csharp[DialogBoxesOverviewSnippets#SaveFileDialogBoxCODEBEHIND](~/samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxesOverviewSnippets/CSharp/Window1.xaml.cs#savefiledialogboxcodebehind)]
 [!code-vb[DialogBoxesOverviewSnippets#SaveFileDialogBoxCODEBEHIND](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DialogBoxesOverviewSnippets/VisualBasic/window1.xaml.vb#savefiledialogboxcodebehind)]  
  
 파일 저장 대화 상자에 대한 자세한 <xref:Microsoft.Win32.SaveFileDialog?displayProperty=nameWithType>내용은 을 참조하십시오.  
  
<a name="Print_Dialog"></a>
### <a name="print-dialog-box"></a>인쇄 대화 상자

다음 그림에 표시된 인쇄 대화 상자는 인쇄 기능에서 사용자가 데이터를 인쇄할 프린터를 선택하고 구성할 때 사용됩니다.  
  
![인쇄 대화 상자를 보여 주는 스크린샷입니다.](./media/dialog-boxes-overview/print-data-dialog-box.png)  
  
일반적인 인쇄 대화 상자는 <xref:System.Windows.Controls.PrintDialog> 클래스로 구현되며 네임스페이스에 <xref:System.Windows.Controls> 있습니다. 다음 코드에서는 만들고, 구성하고, 표시하는 방법을 보여 줍니다.  
  
 [!code-csharp[DialogBoxesOverviewSnippets#PrintDialogBoxCODEBEHIND](~/samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxesOverviewSnippets/CSharp/Window1.xaml.cs#printdialogboxcodebehind)]
 [!code-vb[DialogBoxesOverviewSnippets#PrintDialogBoxCODEBEHIND](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DialogBoxesOverviewSnippets/VisualBasic/window1.xaml.vb#printdialogboxcodebehind)]  
  
 인쇄 대화 상자에 대한 자세한 내용은 <xref:System.Windows.Controls.PrintDialog?displayProperty=nameWithType>을 참조하십시오. WPF 인쇄에 대한 자세한 내용은 [인쇄 개요를](../advanced/printing-overview.md)참조하십시오.  
  
<a name="Custom_Dialog_Boxes"></a>
## <a name="custom-dialog-boxes"></a>사용자 지정 대화 상자

일반 대화 상자는 유용하며 가능한 경우 사용하는 편이 좋지만, 도메인별 대화 상자의 요구 사항은 지원하지 않습니다. 이러한 경우 사용자가 직접 대화 상자를 만들어야 합니다. 살펴보겠지만, 대화 상자는 특별한 동작이 있는 창입니다. <xref:System.Windows.Window>따라서 사용자 지정 모달 및 모데리스 대화 상자를 만드는 데 사용합니다. <xref:System.Windows.Window>  
  
<a name="Creating_a_Modal_Custom_Dialog_Box"></a>
### <a name="creating-a-modal-custom-dialog-box"></a>모달 사용자 지정 대화 상자 만들기

이 항목에서는 <xref:System.Windows.Window> `Margins` 대화 상자를 예로 사용하여 일반적인 모달 대화 상자 구현을 만드는 방법을 보여 주며 대화 상자 [샘플](https://github.com/Microsoft/WPF-Samples/tree/master/Windows/DialogBox)참조를 참조합니다. 대화 `Margins` 상자는 다음 그림에 표시됩니다.  
  
 ![왼쪽 여백, 위쪽 여백, 오른쪽 여백 및 아래쪽 여백을 정의하는 필드가 있는 여백 대화 상자입니다.](./media/dialog-boxes-overview/margin-size-dialog-box.png)  
  
#### <a name="configuring-a-modal-dialog-box"></a>모달 대화 상자 구성

일반 대화 상자의 사용자 인터페이스에는 다음이 포함됩니다.  
  
- 원하는 데이터를 수집하는 데 필요한 다양한 컨트롤.  
  
- 사용자가 클릭하여 대화 상자를 닫고 함수로 돌아가고 처리를 계속하는 **확인** 단추입니다.  
  
- 사용자가 클릭하여 대화 상자를 닫고 함수가 추가 처리를 중지하는 **취소** 단추입니다.  
  
- 제목 표시줄의 **닫기** 단추입니다.  
  
- 아이콘.  
  
- **최소화,** **최대화**및 **복원** 단추.  
  
- 대화 상자를 최소화, 최대화, 복원 및 닫는 **시스템** 메뉴입니다.  
  
- 대화 상자를 연 창 의 위와 가운데위치입니다.  
  
- 대화 상자가 너무 작지 않도록 하고 사용자에게 유용한 기본 크기를 제공하기 위해 가능한 한 크기를 조정할 수 있는 기능입니다. 이를 위해서는 기본치와 최소 치수를 모두 설정해야 합니다.  
  
- 취소 **단추를** 누를 수 있는 키보드 단축키로 ESC 키입니다. <xref:System.Windows.Controls.Button.IsCancel%2A> **취소** 단추의 속성을 로 `true`설정하여 이 작업을 수행합니다.  
  
- **입력(또는** RETURN) 키를 키보드 단축키로 사용하여 확인 단추를 누를 수 있습니다. <xref:System.Windows.Controls.Button.IsDefault%2A> **확인** 단추의 `true`속성을 설정 하 여이 작업을 수행 합니다.  
  
다음 코드에서는 이 구성을 보여 줍니다.  
  
[!code-xaml[MarginsDialogBox XAML file](~/samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxSample/CSharp/MarginsDialogBox.xaml?range=1-16,106-112)]  

[!code-csharp[MarginsDialogBox C# code-behind](~/samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxSample/CSharp/MarginsDialogBox.xaml.cs?range=1-12,67-68)]
[!code-vb[MarginsDialogBox VB code-behind](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DialogBoxSample/VisualBasic/MarginsDialogBox.xaml.vb?range=1-11,61-62)]  
  
대화 상자의 사용자 경험은 대화 상자를 여는 창의 메뉴 모음으로 확장됩니다. 메뉴 항목에서 함수를 계속하기 전에 대화 상자를 통한 사용자 상호 작용을 필요로 하는 함수를 실행하면, 함수의 메뉴 항목 헤더에 다음과 같이 줄임표가 표시됩니다.  
  
[!code-xaml[Menu bar of MainWindow.Xaml file](~/samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxSample/CSharp/MainWindow.xaml#L26-L27)]  
  
메뉴 항목에서 [정보] 대화 상자와 같이 사용자 상호 작용이 필요하지 않은 대화 상자를 표시하는 함수를 실행할 경우는 줄임표가 필요하지 않습니다.  
  
#### <a name="opening-a-modal-dialog-box"></a>모달 대화 상자 열기

대화 상자는 일반적으로 워드 프로세서에서 문서 여백을 설정하는 경우와 같이 사용자가 메뉴 항목을 선택하여 도메인 관련 함수를 수행할 때 표시됩니다. 추가 창을 대화 상자로 표시하는 것은 일반 창을 표시하는 것과 비슷하지만, 추가로 대화 상자 관련 구성이 필요합니다. 대화 상자를 인스턴스화하고, 구성하고, 여는 과정 전체가 다음 코드에 표시되어 있습니다.  
  
[!code-csharp[Opening a modal dialog box](~/samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxSample/CSharp/MainWindow.xaml.cs?range=1-11,78-88,193-195)]
[!code-vb[Opening a modal dialog box](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DialogBoxSample/VisualBasic/MainWindow.xaml.vb?range=1-9,58-67,130-132)]  

여기서 코드는 기본 정보(현재 여백)를 대화 상자에 전달합니다. 또한 대화 <xref:System.Windows.Window.Owner%2A?displayProperty=nameWithType> 상자를 표시 하는 창에 대 한 참조와 함께 속성을 설정 합니다. 일반적으로 모든 대화 상자에 공통적인 창 상태 관련 동작을 제공 하도록 항상 대화 상자에 대 한 소유자를 설정 해야 합니다(자세한 내용은 [WPF Windows 개요](wpf-windows-overview.md) 참조).

> [!NOTE]
> 대화 상자에 대한 사용자 인터페이스(UI) 자동화를 지원하는 소유자를 제공해야 [합니다(UI 자동화 개요](../../ui-automation/ui-automation-overview.md)참조).

대화 상자를 구성한 후 메서드를 <xref:System.Windows.Window.ShowDialog%2A> 호출하여 모드로 표시됩니다.  
  
#### <a name="validating-user-provided-data"></a>사용자가 제공한 데이터 유효성 검사

대화 상자가 열리고 사용자가 필요한 데이터를 제공할 때, 다음과 같은 이유로 대화 상자에서 제공된 데이터가 유효한지 확인해야 합니다.  
  
- 보안 관점에서, 모든 입력이 유효해야 합니다.  
  
- 도메인 관련 관점에서, 데이터의 유효성을 검사하면 코드에서 잘못된 데이터를 처리하여 예외를 일으키는 것을 방지할 수 있습니다.  
  
- 사용자 경험 관점에서, 대화 상자는 사용자가 입력한 데이터 중에 어느 것이 유효한지 표시하여 사용자를 도울 수 있습니다.  
  
- 성능 관점에서, 다중 계층 애플리케이션의 데이터 유효성 검사를 수행하면 클라이언트와 애플리케이션 계층 사이의 왕복 횟수를 줄일 수 있으며 특히 애플리케이션이 웹 서비스나 서버 기반 데이터베이스로 구성된 경우에 효과가 좋습니다.  

WPF에서 바인딩된 컨트롤의 유효성을 검사하려면 유효성 검사 규칙을 정의하고 바인딩과 연결해야 합니다. 유효성 검사 규칙은 에서 <xref:System.Windows.Controls.ValidationRule>파생되는 사용자 지정 클래스입니다. 다음 예제에서는 바인딩된 `MarginValidationRule`값이 a이고 <xref:System.Double> 지정된 범위 내에 있는지 확인하는 유효성 검사 규칙을 보여 주습니다.  

[!code-csharp[Margin validation rules](~/samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxSample/CSharp/MarginValidationRule.cs)]
[!code-vb[Margin validation rules](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DialogBoxSample/VisualBasic/MarginValidationRule.vb)]  

이 코드에서는 유효성 검사 규칙의 유효성 검사 논리는 메서드를 재정의하여 구현되며, 이 <xref:System.Windows.Controls.ValidationRule.Validate%2A> 메서드는 데이터의 유효성을 검사하고 적절한 <xref:System.Windows.Controls.ValidationResult>을 반환합니다.  

유효성 검사 규칙을 바인딩 컨트롤과 연결하려면 다음과 같은 표시를 사용합니다.  
  
[!code-xaml[Associating a validation rule with a control](~/samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxSample/CSharp/MarginsDialogBox.xaml?range=1-16,57-68,111-112)]

유효성 검사 규칙이 연결되면 데이터가 바인딩된 컨트롤에 입력될 때 WPF가 자동으로 적용됩니다. 컨트롤에 잘못된 데이터가 포함되어 있으면 다음 그림과 같이 WPF가 잘못된 컨트롤 주위에 빨간색 테두리를 표시합니다.  
  
![잘못된 왼쪽 여백 값 주위에 빨간색 테두리가 있는 여백 대화 상자입니다.](./media/dialog-boxes-overview/invalid-left-margin-dialog.png)  

WPF는 유효한 데이터를 입력할 때까지 사용자를 잘못된 컨트롤로 제한하지 않습니다. 대화 상자에서 좋은 동작입니다. 사용자는 데이터의 유효성에 관계없이 대화 상자에서 컨트롤을 자유롭게 탐색할 수 있어야 합니다. 그러나 이는 사용자가 잘못된 데이터를 입력하고 **확인** 버튼을 누를 수 있습니다. 따라서 <xref:System.Windows.Controls.Primitives.ButtonBase.Click> 코드는 이벤트를 처리하여 **확인** 단추를 누를 때 대화 상자의 모든 컨트롤의 유효성을 검사해야 합니다.  
  
[!code-csharp[Validating all controls in a dialog box](~/samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxSample/CSharp/MarginsDialogBox.xaml.cs?range=1-8,26-29,33-68)]
[!code-vb[Validating all controls in a dialog box](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DialogBoxSample/VisualBasic/MarginsDialogBox.xaml.vb?range=1-8,27-29,33-62)]  

이 코드는 창에 있는 모든 종속성 개체를 등록하고 유효하지 않은 <xref:System.Windows.Controls.Validation.GetHasError%2A>경우(반환된 경우 잘못 `IsValid` 된 `false`컨트롤이 포커스를 가져오고 메서드가 반환 되고 창이 유효하지 않은 것으로 간주됩니다.  
  
대화 상자가 유효하면 안전하게 닫고 반환할 수 있습니다. 반환 과정의 일부로서 결과를 호출 함수에 반환해야 합니다.  
  
#### <a name="setting-the-modal-dialog-result"></a>모달 대화 상자 결과 설정

사용 <xref:System.Windows.Window.ShowDialog%2A> 하 여 대화 상자를 여는 것은 기본적으로 메서드를 호출 하는 <xref:System.Windows.Window.ShowDialog%2A> 것 <xref:System.Windows.Window.ShowDialog%2A> 처럼: 반환될 때까지 대기를 사용 하 여 대화 상자를 열어 코드. 반환 <xref:System.Windows.Window.ShowDialog%2A> 할 때 사용자가 **확인** 단추 또는 **취소** 단추를 누른지 여부에 따라 처리를 계속할지 아니면 처리를 중지할지 여부를 결정해야 합니다. 이 결정을 용이하게 하려면 대화 상자는 <xref:System.Boolean> <xref:System.Windows.Window.ShowDialog%2A> 메서드에서 반환 되는 값으로 사용자의 선택을 반환 해야 합니다.  

**확인** 단추를 <xref:System.Windows.Window.ShowDialog%2A> 클릭하면 을 `true`반환해야 합니다. 이 문제는 **확인** <xref:System.Windows.Window.DialogResult%2A> 단추를 클릭할 때 대화 상자의 속성을 설정하여 수행됩니다.  

[!code-csharp[Responding to the OK button](~/samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxSample/CSharp/MarginsDialogBox.xaml.cs?range=1-8,25-27,32-33,67-68)]
[!code-vb[Responding to the OK button](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DialogBoxSample/VisualBasic/MarginsDialogBox.xaml.vb?range=1-8,27,31-33,61-62)]  

<xref:System.Windows.Window.DialogResult%2A> 또한 속성을 설정하면 창이 자동으로 닫히므로 명시적으로 호출할 <xref:System.Windows.Window.Close%2A>필요가 완화됩니다.  
  
**취소** 단추를 <xref:System.Windows.Window.ShowDialog%2A> 클릭하면 속성을 `false`설정해야 하는 반환해야 <xref:System.Windows.Window.DialogResult%2A> 합니다.  
  
[!code-csharp[Responding to the Cancel button](~/samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxSample/CSharp/MarginsDialogBox.xaml.cs?range=1-8,19-24,67-68)]
[!code-vb[Responding to the Cancel button](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DialogBoxSample/VisualBasic/MarginsDialogBox.xaml.vb?range=1-8,22-25,61-62)]  

<xref:System.Windows.Controls.Button.IsCancel%2A> 단추의 속성이 `true` 설정되고 사용자가 **취소** 단추 또는 ESC 키를 누르면 <xref:System.Windows.Window.DialogResult%2A> 자동으로 로 `false`설정됩니다. 다음 태그는 <xref:System.Windows.Controls.Primitives.ButtonBase.Click> 이벤트를 처리할 필요 없이 이전 코드와 동일한 영향을 미칩니다.  
  
[!code-xaml[Markup instead of handling the Click event](~/samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxSample/CSharp/MarginsDialogBox.xaml#L109-L109)]  

사용자가 제목 표시줄에서 `false` **닫기** 단추를 누르거나 **시스템** 메뉴에서 **메뉴 닫기** 항목을 선택하면 대화 상자가 자동으로 반환됩니다.  

#### <a name="processing-data-returned-from-a-modal-dialog-box"></a>모달 대화 상자에서 반환된 데이터 처리  

대화 <xref:System.Windows.Window.DialogResult%2A> 상자에 의해 설정되면 대화 상자를 연 함수는 반환 할 때 <xref:System.Windows.Window.DialogResult%2A> <xref:System.Windows.Window.ShowDialog%2A> 속성을 검사하여 대화 상자 결과를 얻을 수 있습니다.  
  
[!code-csharp[Processing data returned from the modal dialog box](~/samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxSample/CSharp/MainWindow.xaml.cs?range=1-10,77-79,89-96,194-195)]
[!code-vb[Processing data returned from the modal dialog box](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DialogBoxSample/VisualBasic/MainWindow.xaml.vb?range=1-9,58,69-73,131-132)]

대화 상자 결과가 `true`있는 경우 함수는 이 것을 큐로 사용하여 사용자가 제공한 데이터를 검색하고 처리합니다.  
  
> [!NOTE]
> 반환된 후에는 <xref:System.Windows.Window.ShowDialog%2A> 대화 상자를 다시 열 수 없습니다. 대신 새 인스턴스를 만들어야 합니다.

대화 상자 결과가 `false`있으면 함수가 적절하게 처리를 종료해야 합니다.  
  
<a name="Creating_a_Modeless_Custom_Dialog_Box"></a>
### <a name="creating-a-modeless-custom-dialog-box"></a>모덜리스 사용자 지정 대화 상자 만들기

다음 그림의 찾기 대화 상자와 같은 모덜리스 대화 상자는 기본적인 모양이 모덜 대화 상자와 같습니다.  

![대화 상자 찾기를 보여 주는 스크린샷입니다.](./media/dialog-boxes-overview/find-modeless-dialog-box.png)  

그러나 다음 섹션에 설명된 것처럼 동작은 약간 다릅니다.  
  
#### <a name="opening-a-modeless-dialog-box"></a>모덜리스 대화 상자 열기

메서드를 호출하여 모덜리스 대화 <xref:System.Windows.Window.Show%2A> 상자가 열립니다.  

[!code-xaml[XAML to define a modeless dialog box](~/samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxSample/CSharp/MainWindow.xaml#L21-L22)]  

[!code-csharp[Opening a modeless dialog box](~/samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxSample/CSharp/MainWindow.xaml.cs?range=1-10,65-76,194-195)]
[!code-vb[Openng a modeless dialog box](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DialogBoxSample/VisualBasic/MainWindow.xaml.vb?range=1-9,18-23,131,132)]  

달리 <xref:System.Windows.Window.ShowDialog%2A> <xref:System.Windows.Window.Show%2A> , 즉시 반환합니다. 따라서 호출하는 창에서는 모덜리스 대화 상자가 닫히는 시기를 알 수 없기 때문에 대화 상자의 결과를 검사하거나 대화 상자에서 더 처리할 데이터를 가져올 시기를 알 수가 없습니다. 대신, 대화 상자에서 호출한 창에 처리할 데이터를 반환할 다른 방법을 만들어야 합니다.  
  
#### <a name="processing-data-returned-from-a-modeless-dialog-box"></a>모덜리스 대화 상자에서 반환된 데이터 처리  

이 예제에서는 `FindDialogBox` 특정 빈도 없이 검색중인 텍스트에 따라 하나 이상의 find 결과를 주 창에 반환할 수 있습니다. 모달 대화 상자와 마찬가지로, 모덜리스 대화 상자에서도 속성을 사용하여 결과를 반환할 수 있습니다. 그러나 대화 상자를 소유한 창에서 해당 속성을 검사할 시기를 알아야 합니다. 한 가지 방법은 대화 상자에서 텍스트를 찾을 때마다 발생하는 이벤트를 구현하는 것입니다. `FindDialogBox`먼저 대리자가 필요한 이 목적을 `TextFoundEvent` 위해 구현합니다.  

[!code-csharp[The TextFoundEventHandler delegate](~/samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxSample/CSharp/TextFoundEventHandler.cs)]
[!code-vb[The TextFoundEventHandler delegate](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DialogBoxSample/VisualBasic/TextFoundEventHandler.vb)]  

`TextFoundEventHandler` 대리자를 사용하여 `FindDialogBox` `TextFoundEvent`을 구현합니다.
  
[!code-csharp[The TextFound event](~/samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxSample/CSharp/FindDialogBox.xaml.cs?range=1-17,125-126)]
[!code-vb[The TextFound event](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DialogBoxSample/VisualBasic/FindDialogBox.xaml.vb?range=1-15,102-103)]

따라서 검색 `Find` 결과가 발견되면 이벤트를 발생시킬 수 있습니다.  
  
[!code-csharp[Raising the TextFound event](~/samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxSample/CSharp/FindDialogBox.xaml.cs?range=1-9,50-52,91-94,124-127)]
[!code-vb[Raising the TextFound event](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DialogBoxSample/VisualBasic/FindDialogBox.xaml.vb?range=1-9,15,60-64,102-103)]  

소유자 창에서는 그 후에 이 이벤트를 등록하고 처리해야 합니다.

[!code-csharp[Registering and handling the event](~/samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxSample/CSharp/MainWindow.xaml.cs?range=1-10,184-195)]
[!code-vb[Registering and handling the event](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DialogBoxSample/VisualBasic/MainWindow.xaml.vb?range=1-9,126-132)]  

#### <a name="closing-a-modeless-dialog-box"></a>모덜리스 대화 상자 닫기

<xref:System.Windows.Window.DialogResult%2A> 설정할 필요가 없으므로 다음을 포함한 시스템 제공 메커니즘을 사용하여 모덜리스 대화 상자를 닫을 수 있습니다.  
  
- 제목 표시줄에서 **닫기** 단추를 클릭합니다.  
  
- ALT+F4 누르기.  
  
- **시스템** 메뉴에서 **닫기** 선택.  
  
또는 **닫기** 단추를 <xref:System.Windows.Window.Close%2A> 클릭할 때 코드를 호출할 수 있습니다.  

[!code-csharp[Calling the Close method](~/samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxSample/CSharp/FindDialogBox.xaml.cs?range=1-9,119-126)]
[!code-vb[Calling the Close method](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DialogBoxSample/VisualBasic/FindDialogBox.xaml.vb?range=1-9,99-103)]  

## <a name="see-also"></a>참고 항목

- [팝업 개요](../controls/popup-overview.md)
- [대화 상자 샘플](https://github.com/Microsoft/WPF-Samples/tree/master/Windows/DialogBox)
