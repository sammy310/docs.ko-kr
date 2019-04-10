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
ms.openlocfilehash: 162414dbd4b0f5e15eceaf73c87c122701fefc4e
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59177413"
---
# <a name="dialog-boxes-overview"></a>대화 상자 개요
독립 실행형 응용 프로그램에는 일반적으로는 응용 프로그램이 작동 하 고를 통해 해당 데이터를 처리 하는 기능을 노출 합니다. 기본 데이터를 표시 하는 주 창이 있는 [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] 메뉴 모음, 도구 모음 및 상태 표시줄과 같은 메커니즘입니다. 특수 애플리케이션에는 다음을 수행하는 추가 창이 표시될 수도 있습니다.  
  
-   사용자에게 특정 정보 표시.  
  
-   사용자로부터 정보 수집.  
  
-   정보 표시 및 수집.  
  
 이러한 유형의 창 이라고 *대화 상자*, 두 가지 유형이 있습니다 및: 모달 및 모덜리스 합니다.  
  
 A *모달* 함수를 계속 하려면 사용자의 추가 데이터가 필요한 경우 함수에서 대화 상자가 표시 됩니다. 함수가 작동하려면 모달 대화 상자를 통해 데이터를 수집해야 하기 때문에, 모달 대화 상자가 열려 있는 동안에는 사용자가 다른 창을 활성화할 수 없습니다. 대부분의 경우 모달 대화 상자를 눌러 모달 대화 상자를 사용 하 여 종료 되었음을 알리기 위해 사용자를 수 있습니다.는 **확인** 하거나 **취소** 단추입니다. 키를 눌러 합니다 **확인** 사용자가 데이터를 입력 하 고 해당 데이터를 사용 하 여 처리를 계속 해 서 함수로 단추를 나타냅니다. 키를 눌러 합니다 **취소** 단추 사용자 함수가 실행을 완전히 되지 않도록 중지 하기 원한다는 것을 나타냅니다. 데이터를 열고, 저장하고, 인쇄하는 가장 일반적인 모달 대화 상자의 예가 나와 있습니다.  
  
 A *모덜리스* 대화 상자에서 다른 한편으로 해도 사용자가 열려 있는 동안 다른 창을 활성화할 합니다. 예를 들어, 사용자가 문서에서 특정 단어를 찾으려고 할 때 주 창에서 사용자가 찾으려는 단어를 입력할 대화 상자를 열 때가 많습니다. 단어를 찾는다고 해서 사용자가 문서를 편집하지 못하게 되는 것은 아니기 때문에 대화 상자를 모덜로 설정할 필요가 없습니다. 모덜리스 대화 상자를 **닫습니다** 대화 상자를 닫으려면 단추와 같은 특정 기능을 실행 하기 위한 추가 단추를 제공할 수 있습니다를 **다음 찾기** 찾으려면 다음 단추는 단어 word 검색 조건과 일치 합니다.  
  
 Windows Presentation Foundation (WPF)를 사용 하면 여러 유형의 메시지 상자, 일반 대화 상자 및 사용자 지정 대화 상자를 포함 하 여 대화 상자를 만들 수 있습니다. 이 항목에서는 각각에 대해 설명 하며 [대화 상자 샘플](https://go.microsoft.com/fwlink/?LinkID=159984) 일치 하는 예제를 제공 합니다.  

<a name="Message_Boxes"></a>   
## <a name="message-boxes"></a>메시지 상자  
 A *메시지 상자* 는 텍스트 정보를 표시 하 고 사용자가 단추를 사용 하 여 결정을 내릴 수 있도록 사용할 수 있는 대화 상자. 다음 그림에는 텍스트 정보를 표시하고, 질문을 하고, 질문에 대답할 때 사용할 세 개의 단추를 사용자에게 제공하는 메시지 상자가 있습니다.  
  
 ![응용 프로그램 전에 문서에 변경 내용을 저장할 것인지 묻는 워드 프로세서 대화 상자를 닫습니다.](./media/dialog-boxes-overview/word-processor-dialog.png)  
  
 메시지 상자를 만들려면 사용 하 여 <xref:System.Windows.MessageBox> 클래스입니다. <xref:System.Windows.MessageBox> 메시지 상자 텍스트, 제목, 아이콘 및 단추, 다음과 같은 코드를 사용 하 여 구성할 수 있습니다.  
  
 [!code-csharp[DialogBoxesOverviewSnippets#MsgBoxConfigureCODEBEHIND](~/samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxesOverviewSnippets/CSharp/Window1.xaml.cs#msgboxconfigurecodebehind)]
 [!code-vb[DialogBoxesOverviewSnippets#MsgBoxConfigureCODEBEHIND](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DialogBoxesOverviewSnippets/VisualBasic/window1.xaml.vb#msgboxconfigurecodebehind)]  
  
 메시지 상자를 표시 하려면 호출을 `static`<xref:System.Windows.MessageBox.Show%2A> 메서드를 다음 코드 에서처럼 합니다.  
  
 [!code-csharp[DialogBoxesOverviewSnippets#MsgBoxShowCODEBEHIND](~/samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxesOverviewSnippets/CSharp/Window1.xaml.cs#msgboxshowcodebehind)]
 [!code-vb[DialogBoxesOverviewSnippets#MsgBoxShowCODEBEHIND](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DialogBoxesOverviewSnippets/VisualBasic/window1.xaml.vb#msgboxshowcodebehind)]  
  
 메시지 상자를 표시하는 코드로 사용자의 결정을 감지하고 처리해야 할 경우는(단추 누름) 다음 코드에서와 같이 코드를 통해 메시지 상자 결과를 검사할 수 있습니다.  
  
 [!code-csharp[DialogBoxesOverviewSnippets#MsgBoxShowAndResultCODEBEHIND1](~/samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxesOverviewSnippets/CSharp/Window1.xaml.cs#msgboxshowandresultcodebehind1)]
 [!code-vb[DialogBoxesOverviewSnippets#MsgBoxShowAndResultCODEBEHIND1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DialogBoxesOverviewSnippets/VisualBasic/window1.xaml.vb#msgboxshowandresultcodebehind1)]  
  
 메시지 상자 사용에 대 한 자세한 내용은 참조 하세요. <xref:System.Windows.MessageBox>하십시오 [MessageBox 샘플](https://go.microsoft.com/fwlink/?LinkID=160023), 및 [대화 상자 샘플](https://go.microsoft.com/fwlink/?LinkID=159984)합니다.  
  
 하지만 <xref:System.Windows.MessageBox> 간단한 대화 상자 사용자 경험을 사용 하는 이점은 제공할 수 있습니다 <xref:System.Windows.MessageBox> 부분 신뢰 보안 샌드박스 내에서 실행 되는 응용 프로그램에서 표시 될 수 있는 창의 유형만 (참조 [보안](../security-wpf.md)), 같은 [!INCLUDE[TLA#tla_xbap#plural](../../../../includes/tlasharptla-xbapsharpplural-md.md)]합니다.  
  
 대부분의 대화 상자는 텍스트, 선택(확인란), 상호 배타적인 선택(라디오 단추), 목록 선택(목록 상자, 콤보 상자, 드롭다운 목록 상자)과 같이 메시지 상자의 결과보다 복잡한 데이터를 표시하고 수집합니다. 이러한 경우를 위해 Windows Presentation Foundation (WPF) 몇 가지 일반적인 대화 상자를 제공 및 사용은 완전 신뢰로 실행 되는 응용 프로그램으로 제한 됩니다. 하지만 사용자가 직접 대화 상자를 만들 수 있습니다.  
  
<a name="Common_Dialogs"></a>   
## <a name="common-dialog-boxes"></a>일반 대화 상자  
 [!INCLUDE[TLA#tla_mswin](../../../../includes/tlasharptla-mswin-md.md)] 다양 한 파일 열기, 파일 저장 및 인쇄에 대 한 대화 상자를 포함 하는 모든 응용 프로그램에 공통 되는 재사용 가능 대화 상자를 구현 합니다. 이러한 대화 상자는 운영 체제에서 구현되므로 운영 체제에서 실행되는 모든 애플리케이션에서 공유할 수 있어 사용자 경험의 일관성에 도움이 됩니다. 운영 체제에서 제공되는 대화 상자를 사용자가 한 애플리케이션에서 익히고 나면 다른 애플리케이션에서 대화 상자의 사용 방법을 다시 익힐 필요가 없습니다. 이러한 대화 상자는 모든 응용 프로그램에 사용할 수 있고 라고 일관 된 사용자 경험에 도움이 되므로 *공용 대화 상자*합니다.  
  
 Windows Presentation Foundation (WPF) 캡슐화 열려 있는 파일, 파일을 저장 및 인쇄 일반 대화 상자 및 독립 실행형 응용 프로그램에서 사용 하 여 관리 되는 클래스로 노출 합니다. 이 항목에서는 각각의 개요를 간략하게 제공합니다.  
  
<a name="Open_File_Dialog"></a>   
### <a name="open-file-dialog"></a>파일 열기 대화 상자  
 다음 그림에 표시된 파일 열기 대화 상자는 파일 열기 기능에서 열려는 파일의 이름을 검색할 때 사용됩니다.  
  
 ![파일을 검색할 위치를 보여 주는 열린 대화 상자.](./media/dialog-boxes-overview/open-file-dialog-box.png)  
  
 일반 파일 열기 대화 상자 구현 됩니다 합니다 <xref:Microsoft.Win32.OpenFileDialog> 클래스 및에 <xref:Microsoft.Win32> 네임 스페이스입니다. 다음 코드에서는 코드를 만들고 구성 및 표시하는 방법과 결과를 처리하는 방법을 보여 줍니다.  
  
 [!code-csharp[DialogBoxesOverviewSnippets#OpenFileDialogBoxCODEBEHIND](~/samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxesOverviewSnippets/CSharp/Window1.xaml.cs#openfiledialogboxcodebehind)]
 [!code-vb[DialogBoxesOverviewSnippets#OpenFileDialogBoxCODEBEHIND](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DialogBoxesOverviewSnippets/VisualBasic/window1.xaml.vb#openfiledialogboxcodebehind)]  
  
 파일 열기 대화 상자에 대 한 자세한 내용은 참조 하세요. <xref:Microsoft.Win32.OpenFileDialog?displayProperty=nameWithType>합니다.  
  
> [!NOTE]
>  <xref:Microsoft.Win32.OpenFileDialog> 부분 신뢰로 실행 되는 응용 프로그램에서 안전 하 게 파일 이름을 검색 하려면 사용할 수 있습니다 (참조 [보안](../security-wpf.md)).  
  
<a name="Save_File_Dialog"></a>   
### <a name="save-file-dialog-box"></a>파일 저장 대화 상자  
 다음 그림에 표시된 파일 저장 대화 상자는 파일 저장 기능에서 저장하려는 파일의 이름을 검색할 때 사용됩니다.  
  
 ![다른 이름으로 저장 대화 상자는 파일을 저장할 위치를 표시 합니다.](./media/dialog-boxes-overview/save-file-dialog-box.png)  
  
 파일 저장 대화 상자는 일반적으로 구현 됩니다 합니다 <xref:Microsoft.Win32.SaveFileDialog> 클래스 및에 <xref:Microsoft.Win32> 네임 스페이스입니다. 다음 코드에서는 코드를 만들고 구성 및 표시하는 방법과 결과를 처리하는 방법을 보여 줍니다.  
  
 [!code-csharp[DialogBoxesOverviewSnippets#SaveFileDialogBoxCODEBEHIND](~/samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxesOverviewSnippets/CSharp/Window1.xaml.cs#savefiledialogboxcodebehind)]
 [!code-vb[DialogBoxesOverviewSnippets#SaveFileDialogBoxCODEBEHIND](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DialogBoxesOverviewSnippets/VisualBasic/window1.xaml.vb#savefiledialogboxcodebehind)]  
  
 저장에 대 한 자세한 내용은 파일 대화 상자, 참조 <xref:Microsoft.Win32.SaveFileDialog?displayProperty=nameWithType>합니다.  
  
<a name="Print_Dialog"></a>   
### <a name="print-dialog-box"></a>인쇄 대화 상자  
 다음 그림에 표시된 인쇄 대화 상자는 인쇄 기능에서 사용자가 데이터를 인쇄할 프린터를 선택하고 구성할 때 사용됩니다.  
  
 ![인쇄 대화 상자를 보여 주는 스크린샷.](./media/dialog-boxes-overview/print-data-dialog-box.png)  
  
 일반적인 인쇄 대화 상자 구현 됩니다 합니다 <xref:System.Windows.Controls.PrintDialog> 클래스 및에 <xref:System.Windows.Controls> 네임 스페이스입니다. 다음 코드에서는 만들고, 구성하고, 표시하는 방법을 보여 줍니다.  
  
 [!code-csharp[DialogBoxesOverviewSnippets#PrintDialogBoxCODEBEHIND](~/samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxesOverviewSnippets/CSharp/Window1.xaml.cs#printdialogboxcodebehind)]
 [!code-vb[DialogBoxesOverviewSnippets#PrintDialogBoxCODEBEHIND](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DialogBoxesOverviewSnippets/VisualBasic/window1.xaml.vb#printdialogboxcodebehind)]  
  
 인쇄 대화 상자에 대 한 자세한 내용은 참조 하세요. <xref:System.Windows.Controls.PrintDialog?displayProperty=nameWithType>합니다. 에 대 한 자세한 설명은의 인쇄 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]를 참조 하세요 [인쇄 개요](../advanced/printing-overview.md)합니다.  
  
<a name="Custom_Dialog_Boxes"></a>   
## <a name="custom-dialog-boxes"></a>사용자 지정 대화 상자  
 일반 대화 상자는 유용하며 가능한 경우 사용하는 편이 좋지만, 도메인별 대화 상자의 요구 사항은 지원하지 않습니다. 이러한 경우 사용자가 직접 대화 상자를 만들어야 합니다. 살펴보겠지만, 대화 상자는 특별한 동작이 있는 창입니다. <xref:System.Windows.Window> 이러한 동작을 구현 및 사용 하는 결과적으로 <xref:System.Windows.Window> 사용자 지정 모달 및 모덜리스 대화 상자를 만들려면.  
  
<a name="Creating_a_Modal_Custom_Dialog_Box"></a>   
### <a name="creating-a-modal-custom-dialog-box"></a>모달 사용자 지정 대화 상자 만들기  
 이 항목에서는 사용 하는 방법을 보여 줍니다 <xref:System.Windows.Window> 는 일반적인 모달 대화 상자 구현을 만드는 사용 하는 `Margins` 예를 들어 대화 상자 (참조 [대화 상자 샘플](https://go.microsoft.com/fwlink/?LinkID=159984)). `Margins` 대화 상자는 다음 그림에 표시 됩니다.  
  
 ![왼쪽된 여백, 위쪽 여백, 오른쪽 여백 및 아래쪽 여백을 정의 하는 필드를 사용 하 여 여백 대화 상자입니다.](./media/dialog-boxes-overview/margin-size-dialog-box.png)  
  
#### <a name="configuring-a-modal-dialog-box"></a>모달 대화 상자 구성  
 일반 대화 상자의 사용자 인터페이스에는 다음이 포함됩니다.  
  
-   원하는 데이터를 수집하는 데 필요한 다양한 컨트롤.  
  
-   표시는 **확인** 단추는 사용자 함수에 반환 된 대화 상자를 닫으려면 클릭 하 고 처리를 계속 합니다.  
  
-   표시는 **취소** 단추 사용자가 대화 상자를 닫고 함수의 처리를 중지 하려면 클릭 합니다.  
  
-   표시 된 **닫기** 제목 표시줄에 단추입니다.  
  
-   아이콘 표시.  
  
-   보여 주는 **최소화**를 **최대화**, 및 **복원** 단추입니다.  
  
-   표시 된 **시스템** 메뉴를 최소화, 최대화, 복원 및 대화 상자를 닫습니다.  
  
-   대화 상자를 열 창의 위와 가운데에 열기.  
  
-   대화 상자가 너무 작아지는 것을 방지할 수 있도록 대화 상자는 가능한 한 크기를 조정할 수 있게 해야 하며, 사용자에게 유용한 기본 크기를 제공할 수 있도록 기본 크기와 최소 크기를 적절하게 설정해야 합니다.  
  
-   ESC 키를 발생 시키는 바로 가기 키로 구성 해야 합니다 **취소** 단추를 누른 것입니다. 설정 하 여 이렇게 합니다 <xref:System.Windows.Controls.Button.IsCancel%2A> 의 속성을 **취소** 단추를 `true`.  
  
-   ENTER (또는 RETURN) 키를 누르거나 바로 가기 키를 발생 시키는으로 구성 해야 합니다 **확인** 단추를 누른 것입니다. 설정 하 여 이렇게 합니다 <xref:System.Windows.Controls.Button.IsDefault%2A> 의 속성을 **확인** 단추 `true`.  
  
 다음 코드에서는 이 구성을 보여 줍니다.  
  
 [!code-xaml[DialogBoxSample#MarginsDialogBoxMainBitsMARKUP1](~/samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxSample/CSharp/MarginsDialogBox.xaml#marginsdialogboxmainbitsmarkup1)]  
[!code-xaml[DialogBoxSample#MarginsDialogBoxMainBitsMARKUP2](~/samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxSample/CSharp/MarginsDialogBox.xaml#marginsdialogboxmainbitsmarkup2)]  
  
 [!code-csharp[DialogBoxSample#MarginsDialogBoxMainBitsCODEBEHIND1](~/samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxSample/CSharp/MarginsDialogBox.xaml.cs#marginsdialogboxmainbitscodebehind1)]
 [!code-vb[DialogBoxSample#MarginsDialogBoxMainBitsCODEBEHIND1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DialogBoxSample/VisualBasic/MarginsDialogBox.xaml.vb#marginsdialogboxmainbitscodebehind1)]  
[!code-csharp[DialogBoxSample#MarginsDialogBoxMainBitsCODEBEHIND2](~/samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxSample/CSharp/MarginsDialogBox.xaml.cs#marginsdialogboxmainbitscodebehind2)]
[!code-vb[DialogBoxSample#MarginsDialogBoxMainBitsCODEBEHIND2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DialogBoxSample/VisualBasic/MarginsDialogBox.xaml.vb#marginsdialogboxmainbitscodebehind2)]  
  
 대화 상자의 사용자 경험은 대화 상자를 여는 창의 메뉴 모음으로 확장됩니다. 메뉴 항목에서 함수를 계속하기 전에 대화 상자를 통한 사용자 상호 작용을 필요로 하는 함수를 실행하면, 함수의 메뉴 항목 헤더에 다음과 같이 줄임표가 표시됩니다.  
  
 [!code-xaml[DialogBoxSample#MainWindowMarginsDialogBoxMenuItemMARKUP1](~/samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxSample/CSharp/MainWindow.xaml#mainwindowmarginsdialogboxmenuitemmarkup1)]  
[!code-xaml[DialogBoxSample#MainWindowMarginsDialogBoxMenuItemMARKUP2](~/samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxSample/CSharp/MainWindow.xaml#mainwindowmarginsdialogboxmenuitemmarkup2)]  
  
 메뉴 항목에서 [정보] 대화 상자와 같이 사용자 상호 작용이 필요하지 않은 대화 상자를 표시하는 함수를 실행할 경우는 줄임표가 필요하지 않습니다.  
  
#### <a name="opening-a-modal-dialog-box"></a>모달 대화 상자 열기  
 대화 상자는 일반적으로 워드 프로세서에서 문서 여백을 설정하는 경우와 같이 사용자가 메뉴 항목을 선택하여 도메인 관련 함수를 수행할 때 표시됩니다. 추가 창을 대화 상자로 표시하는 것은 일반 창을 표시하는 것과 비슷하지만, 추가로 대화 상자 관련 구성이 필요합니다. 대화 상자를 인스턴스화하고, 구성하고, 여는 과정 전체가 다음 코드에 표시되어 있습니다.  
  
 [!code-csharp[DialogBoxSample#OpenMarginsDialogCODEBEHIND1](~/samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxSample/CSharp/MainWindow.xaml.cs#openmarginsdialogcodebehind1)]
 [!code-vb[DialogBoxSample#OpenMarginsDialogCODEBEHIND1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DialogBoxSample/VisualBasic/MainWindow.xaml.vb#openmarginsdialogcodebehind1)]  
[!code-csharp[DialogBoxSample#OpenMarginsDialogCODEBEHIND2](~/samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxSample/CSharp/MainWindow.xaml.cs#openmarginsdialogcodebehind2)]
[!code-vb[DialogBoxSample#OpenMarginsDialogCODEBEHIND2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DialogBoxSample/VisualBasic/MainWindow.xaml.vb#openmarginsdialogcodebehind2)]  
[!code-csharp[DialogBoxSample#OpenMarginsDialogCODEBEHIND3](~/samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxSample/CSharp/MainWindow.xaml.cs#openmarginsdialogcodebehind3)]
[!code-vb[DialogBoxSample#OpenMarginsDialogCODEBEHIND3](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DialogBoxSample/VisualBasic/MainWindow.xaml.vb#openmarginsdialogcodebehind3)]  
[!code-csharp[DialogBoxSample#OpenMarginsDialogCODEBEHIND4](~/samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxSample/CSharp/MainWindow.xaml.cs#openmarginsdialogcodebehind4)]
[!code-vb[DialogBoxSample#OpenMarginsDialogCODEBEHIND4](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DialogBoxSample/VisualBasic/MainWindow.xaml.vb#openmarginsdialogcodebehind4)]  
  
 여기에서 코드는 대화 상자로 기본 정보(현재 여백)를 전달합니다. 또한는 <xref:System.Windows.Window.Owner%2A?displayProperty=nameWithType> 속성 대화 상자를 표시 하는 창에 대 한 참조를 사용 하 여 합니다. 일반적으로 모든 대화 상자에 공통적인 창 상태 관련 동작을 제공 하기 위해 대화 상자에 대 한 소유자 항상 설정 해야 합니다 (참조 [WPF Windows 개요](wpf-windows-overview.md) 자세한).  
  
> [!NOTE]
>  지원 하려면 소유자를 제공 해야 합니다 [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] 대화 상자에 대 한 자동화 (참조 [UI 자동화 개요](../../ui-automation/ui-automation-overview.md)).  
  
 대화 상자를 구성한 후 모달로 표시를 호출 하 여는 <xref:System.Windows.Window.ShowDialog%2A> 메서드.  
  
#### <a name="validating-user-provided-data"></a>사용자가 제공한 데이터의 유효성 검사  
 대화 상자가 열리고 사용자가 필요한 데이터를 제공할 때, 다음과 같은 이유로 대화 상자에서 제공된 데이터가 유효한지 확인해야 합니다.  
  
-   보안 관점에서, 모든 입력이 유효해야 합니다.  
  
-   도메인 관련 관점에서, 데이터의 유효성을 검사하면 코드에서 잘못된 데이터를 처리하여 예외를 일으키는 것을 방지할 수 있습니다.  
  
-   사용자 경험 관점에서, 대화 상자는 사용자가 입력한 데이터 중에 어느 것이 유효한지 표시하여 사용자를 도울 수 있습니다.  
  
-   성능 관점에서, 다중 계층 애플리케이션의 데이터 유효성 검사를 수행하면 클라이언트와 애플리케이션 계층 사이의 왕복 횟수를 줄일 수 있으며 특히 애플리케이션이 웹 서비스나 서버 기반 데이터베이스로 구성된 경우에 효과가 좋습니다.  
  
 바인딩된 컨트롤의 유효성을 검사 하려면 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)], 유효성 검사 규칙을 정의 하 고 바인딩을 사용 하 여 연결 해야 합니다. 유효성 검사 규칙은 사용자 지정 클래스에서 파생 되는 <xref:System.Windows.Controls.ValidationRule>합니다. 다음 예에서는 유효성 검사 규칙을 보여 줍니다 `MarginValidationRule`, 바인딩된 값이 있는지 검사 하는 <xref:System.Double> 지정된 된 범위 내에 있는 합니다.  
  
 [!code-csharp[DialogBoxSample#MarginValidationRuleCODE](~/samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxSample/CSharp/MarginValidationRule.cs#marginvalidationrulecode)]
 [!code-vb[DialogBoxSample#MarginValidationRuleCODE](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DialogBoxSample/VisualBasic/MarginValidationRule.vb#marginvalidationrulecode)]  
  
 이 코드는 유효성 검사 규칙의 유효성 검사 논리를 재정의 하 여 구현 됩니다 합니다 <xref:System.Windows.Controls.ValidationRule.Validate%2A> 데이터의 유효성을 검사 하 고 적절 한 반환 하는 메서드를 <xref:System.Windows.Controls.ValidationResult>입니다.  
  
 유효성 검사 규칙을 바인딩 컨트롤과 연결하려면 다음과 같은 표시를 사용합니다.  
  
 [!code-xaml[DialogBoxSample#MarginsValidationMARKUP1](~/samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxSample/CSharp/MarginsDialogBox.xaml#marginsvalidationmarkup1)]  
[!code-xaml[DialogBoxSample#MarginsValidationMARKUP2](~/samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxSample/CSharp/MarginsDialogBox.xaml#marginsvalidationmarkup2)]  
[!code-xaml[DialogBoxSample#MarginsValidationMARKUP3](~/samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxSample/CSharp/MarginsDialogBox.xaml#marginsvalidationmarkup3)]  
  
 유효성 검사 규칙 연결 되 면 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] 데이터 바인딩된 컨트롤에 입력 되 면을 자동으로 적용 됩니다. 컨트롤에 잘못 된 데이터가 포함 된 경우 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] 다음 그림에 표시 된 대로 잘못 된 컨트롤 주위에 빨간색 테두리를 표시 됩니다.  
  
 ![잘못 된 왼쪽된 여백 값 주위에 빨간색 테두리를 사용 하 여 여백 대화 상자입니다.](./media/dialog-boxes-overview/invalid-left-margin-dialog.png)  
  
 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] 유효한 데이터를 입력할 때까지 잘못 된 컨트롤에 사용자를 제한 하지 않습니다. 대화 상자에서 좋은 동작입니다. 사용자는 데이터의 유효성에 관계없이 대화 상자에서 컨트롤을 자유롭게 탐색할 수 있어야 합니다. 그러나이 경우 잘못 된 데이터 및 키를 눌러 입력할 수 있는 합니다 **확인** 단추입니다. 따라서이 코드에서는 대화 상자에서 모든 컨트롤의 유효성을 검사 하려면 상자는 **확인** 처리 하 여 단추를 누를 <xref:System.Windows.Controls.Primitives.ButtonBase.Click> 이벤트입니다.  
  
 [!code-csharp[DialogBoxSample#MarginsDialogBoxValidationCODEBEHIND1](~/samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxSample/CSharp/MarginsDialogBox.xaml.cs#marginsdialogboxvalidationcodebehind1)]
 [!code-vb[DialogBoxSample#MarginsDialogBoxValidationCODEBEHIND1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DialogBoxSample/VisualBasic/MarginsDialogBox.xaml.vb#marginsdialogboxvalidationcodebehind1)]  
[!code-csharp[DialogBoxSample#MarginsDialogBoxValidationCODEBEHIND2](~/samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxSample/CSharp/MarginsDialogBox.xaml.cs#marginsdialogboxvalidationcodebehind2)]
[!code-vb[DialogBoxSample#MarginsDialogBoxValidationCODEBEHIND2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DialogBoxSample/VisualBasic/MarginsDialogBox.xaml.vb#marginsdialogboxvalidationcodebehind2)]  
[!code-csharp[DialogBoxSample#MarginsDialogBoxValidationCODEBEHIND3](~/samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxSample/CSharp/MarginsDialogBox.xaml.cs#marginsdialogboxvalidationcodebehind3)]
[!code-vb[DialogBoxSample#MarginsDialogBoxValidationCODEBEHIND3](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DialogBoxSample/VisualBasic/MarginsDialogBox.xaml.vb#marginsdialogboxvalidationcodebehind3)]  
  
 창에 모든 종속성 개체를 열거 하는이 코드 및 유효 하지 않는 경우 (반환한 <xref:System.Windows.Controls.Validation.GetHasError%2A>, 잘못 된 컨트롤이 포커스를 `IsValid` 메서드가 반환 되는 `false`, 창 잘못 된 것으로 간주 됩니다.  
  
 대화 상자가 유효하면 안전하게 닫고 반환할 수 있습니다. 반환 과정의 일부로서 결과를 호출 함수에 반환해야 합니다.  
  
#### <a name="setting-the-modal-dialog-result"></a>모달 대화 상자 결과 설정  
 사용 하 여 대화 상자를 열어 <xref:System.Windows.Window.ShowDialog%2A> 메서드를 호출 하는 것은 기본적으로: 사용 하 여 대화 상자를 연 코드 <xref:System.Windows.Window.ShowDialog%2A> 때까지 대기 <xref:System.Windows.Window.ShowDialog%2A> 반환 합니다. 때 <xref:System.Windows.Window.ShowDialog%2A> 사용자가 누른 반환 하 고, 코드를 호출한 기반 여부를 계속 처리 하거나 처리가 중지 여부를 결정 합니다 **확인** 단추 또는 **취소** 단추입니다. 이 결정을 위해 대화 상자를 사용자의 선택 항목으로 반환 해야는 <xref:System.Boolean> 에서 반환 되는 값은 <xref:System.Windows.Window.ShowDialog%2A> 메서드.  
  
 경우는 **확인** 단추를 클릭 <xref:System.Windows.Window.ShowDialog%2A> 반환할지 `true`합니다. 설정 하 여 이렇게 합니다 <xref:System.Windows.Window.DialogResult%2A> 속성 대화 상자는 **확인** 단추를 클릭 합니다.  
  
 [!code-csharp[DialogBoxSample#MarginsDialogBoxOKResultSetCODEBEHIND1](~/samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxSample/CSharp/MarginsDialogBox.xaml.cs#marginsdialogboxokresultsetcodebehind1)]
 [!code-vb[DialogBoxSample#MarginsDialogBoxOKResultSetCODEBEHIND1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DialogBoxSample/VisualBasic/MarginsDialogBox.xaml.vb#marginsdialogboxokresultsetcodebehind1)]  
[!code-csharp[DialogBoxSample#MarginsDialogBoxOKResultSetCODEBEHIND2](~/samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxSample/CSharp/MarginsDialogBox.xaml.cs#marginsdialogboxokresultsetcodebehind2)]
[!code-vb[DialogBoxSample#MarginsDialogBoxOKResultSetCODEBEHIND2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DialogBoxSample/VisualBasic/MarginsDialogBox.xaml.vb#marginsdialogboxokresultsetcodebehind2)]  
[!code-csharp[DialogBoxSample#MarginsDialogBoxOKResultSetCODEBEHIND3](~/samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxSample/CSharp/MarginsDialogBox.xaml.cs#marginsdialogboxokresultsetcodebehind3)]
[!code-vb[DialogBoxSample#MarginsDialogBoxOKResultSetCODEBEHIND3](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DialogBoxSample/VisualBasic/MarginsDialogBox.xaml.vb#marginsdialogboxokresultsetcodebehind3)]  
[!code-csharp[DialogBoxSample#MarginsDialogBoxOKResultSetCODEBEHIND4](~/samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxSample/CSharp/MarginsDialogBox.xaml.cs#marginsdialogboxokresultsetcodebehind4)]
[!code-vb[DialogBoxSample#MarginsDialogBoxOKResultSetCODEBEHIND4](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DialogBoxSample/VisualBasic/MarginsDialogBox.xaml.vb#marginsdialogboxokresultsetcodebehind4)]  
  
 설정 합니다 <xref:System.Windows.Window.DialogResult%2A> 속성에 해도 창이 자동으로 닫히므로 명시적으로 호출할 필요가 없어졌습니다 <xref:System.Windows.Window.Close%2A>합니다.  
  
 경우는 **취소** 단추를 클릭 <xref:System.Windows.Window.ShowDialog%2A> 반환 해야 `false`를 설정 해야 합니다 <xref:System.Windows.Window.DialogResult%2A> 속성.  
  
 [!code-csharp[DialogBoxSample#MarginsDialogBoxCancelResultSetCODEBEHIND1](~/samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxSample/CSharp/MarginsDialogBox.xaml.cs#marginsdialogboxcancelresultsetcodebehind1)]
 [!code-vb[DialogBoxSample#MarginsDialogBoxCancelResultSetCODEBEHIND1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DialogBoxSample/VisualBasic/MarginsDialogBox.xaml.vb#marginsdialogboxcancelresultsetcodebehind1)]  
[!code-csharp[DialogBoxSample#MarginsDialogBoxCancelResultSetCODEBEHIND2](~/samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxSample/CSharp/MarginsDialogBox.xaml.cs#marginsdialogboxcancelresultsetcodebehind2)]
[!code-vb[DialogBoxSample#MarginsDialogBoxCancelResultSetCODEBEHIND2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DialogBoxSample/VisualBasic/MarginsDialogBox.xaml.vb#marginsdialogboxcancelresultsetcodebehind2)]  
[!code-csharp[DialogBoxSample#MarginsDialogBoxCancelResultSetCODEBEHIND3](~/samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxSample/CSharp/MarginsDialogBox.xaml.cs#marginsdialogboxcancelresultsetcodebehind3)]
[!code-vb[DialogBoxSample#MarginsDialogBoxCancelResultSetCODEBEHIND3](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DialogBoxSample/VisualBasic/MarginsDialogBox.xaml.vb#marginsdialogboxcancelresultsetcodebehind3)]  
  
 때 단추의 <xref:System.Windows.Controls.Button.IsCancel%2A> 속성이로 설정 되어 `true` 사용자가 및 합니다 **취소** 단추나 ESC 키를 <xref:System.Windows.Window.DialogResult%2A> 로 자동 설정 됩니다 `false`합니다. 위의 코드에서 처리 하지 않아도 것과 동일한 효과가 다음 태그는 <xref:System.Windows.Controls.Primitives.ButtonBase.Click> 이벤트입니다.  
  
 [!code-xaml[DialogBoxSample#MarginsDialogDefaultCancelMARKUP](~/samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxSample/CSharp/MarginsDialogBox.xaml#marginsdialogdefaultcancelmarkup)]  
  
 대화 상자가 자동으로 반환 합니다. `false` 누를 때 합니다 **닫기** 제목 표시줄 단추 선택 하거나 선택 하는 **닫기** 메뉴 항목을를 **시스템** 메뉴.  
  
#### <a name="processing-data-returned-from-a-modal-dialog-box"></a>모달 대화 상자에서 반환된 데이터 처리  
 때 <xref:System.Windows.Window.DialogResult%2A> 설정 대화 상자를 여는 함수 결과 얻을 수 대화 상자를 검사 하 여는 <xref:System.Windows.Window.DialogResult%2A> 속성 때 <xref:System.Windows.Window.ShowDialog%2A> 반환 합니다.  
  
 [!code-csharp[DialogBoxSample#OpenMarginsDialogProcessReturnCODEBEHIND1](~/samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxSample/CSharp/MainWindow.xaml.cs#openmarginsdialogprocessreturncodebehind1)]
 [!code-vb[DialogBoxSample#OpenMarginsDialogProcessReturnCODEBEHIND1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DialogBoxSample/VisualBasic/MainWindow.xaml.vb#openmarginsdialogprocessreturncodebehind1)]  
[!code-csharp[DialogBoxSample#OpenMarginsDialogProcessReturnCODEBEHIND2](~/samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxSample/CSharp/MainWindow.xaml.cs#openmarginsdialogprocessreturncodebehind2)]
[!code-vb[DialogBoxSample#OpenMarginsDialogProcessReturnCODEBEHIND2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DialogBoxSample/VisualBasic/MainWindow.xaml.vb#openmarginsdialogprocessreturncodebehind2)]  
[!code-csharp[DialogBoxSample#OpenMarginsDialogProcessReturnCODEBEHIND3](~/samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxSample/CSharp/MainWindow.xaml.cs#openmarginsdialogprocessreturncodebehind3)]
[!code-vb[DialogBoxSample#OpenMarginsDialogProcessReturnCODEBEHIND3](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DialogBoxSample/VisualBasic/MainWindow.xaml.vb#openmarginsdialogprocessreturncodebehind3)]  
[!code-csharp[DialogBoxSample#OpenMarginsDialogProcessReturnCODEBEHIND4](~/samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxSample/CSharp/MainWindow.xaml.cs#openmarginsdialogprocessreturncodebehind4)]
[!code-vb[DialogBoxSample#OpenMarginsDialogProcessReturnCODEBEHIND4](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DialogBoxSample/VisualBasic/MainWindow.xaml.vb#openmarginsdialogprocessreturncodebehind4)]  
  
 대화 상자 결과 이면 `true`, 함수를 검색 하 고 사용자가 제공 되는 데이터 처리를 신호로 사용 합니다.  
  
> [!NOTE]
>  후 <xref:System.Windows.Window.ShowDialog%2A> 가 반환 된 대화 상자를 다시 열 수 없습니다. 대신 새 인스턴스를 만들어야 합니다.  
  
 대화 상자 결과 이면 `false`, 함수에서 적절 하 게 처리를 끝내 야 합니다.  
  
<a name="Creating_a_Modeless_Custom_Dialog_Box"></a>   
### <a name="creating-a-modeless-custom-dialog-box"></a>모덜리스 사용자 지정 대화 상자 만들기  
 다음 그림의 찾기 대화 상자와 같은 모덜리스 대화 상자는 기본적인 모양이 모덜 대화 상자와 같습니다.  
  
 ![찾기 대화 상자를 보여 주는 스크린샷.](./media/dialog-boxes-overview/find-modeless-dialog-box.png)  
  
 그러나 다음 섹션에 설명된 것처럼 동작은 약간 다릅니다.  
  
#### <a name="opening-a-modeless-dialog-box"></a>모덜리스 대화 상자 열기  
 모덜리스 대화 상자를 호출 하 여 열릴는 <xref:System.Windows.Window.Show%2A> 메서드.  
  
 [!code-xaml[DialogBoxSample#OpenFindDialogMARKUP1](~/samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxSample/CSharp/MainWindow.xaml#openfinddialogmarkup1)]  
  
 [!code-csharp[DialogBoxSample#OpenFindDialogCODEBEHIND1](~/samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxSample/CSharp/MainWindow.xaml.cs#openfinddialogcodebehind1)]
 [!code-vb[DialogBoxSample#OpenFindDialogCODEBEHIND1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DialogBoxSample/VisualBasic/MainWindow.xaml.vb#openfinddialogcodebehind1)]  
[!code-csharp[DialogBoxSample#OpenFindDialogCODEBEHIND2](~/samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxSample/CSharp/MainWindow.xaml.cs#openfinddialogcodebehind2)]
[!code-vb[DialogBoxSample#OpenFindDialogCODEBEHIND2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DialogBoxSample/VisualBasic/MainWindow.xaml.vb#openfinddialogcodebehind2)]  
[!code-csharp[DialogBoxSample#OpenFindDialogCODEBEHIND3](~/samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxSample/CSharp/MainWindow.xaml.cs#openfinddialogcodebehind3)]
[!code-vb[DialogBoxSample#OpenFindDialogCODEBEHIND3](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DialogBoxSample/VisualBasic/MainWindow.xaml.vb#openfinddialogcodebehind3)]  
  
 와 달리 <xref:System.Windows.Window.ShowDialog%2A>, <xref:System.Windows.Window.Show%2A> 즉시 반환 합니다. 따라서 호출하는 창에서는 모덜리스 대화 상자가 닫히는 시기를 알 수 없기 때문에 대화 상자의 결과를 검사하거나 대화 상자에서 더 처리할 데이터를 가져올 시기를 알 수가 없습니다. 대신, 대화 상자에서 호출한 창에 처리할 데이터를 반환할 다른 방법을 만들어야 합니다.  
  
#### <a name="processing-data-returned-from-a-modeless-dialog-box"></a>모덜리스 대화 상자에서 반환된 데이터 처리  
 이 예제는 `FindDialogBox` 하나 이상의 찾기에 대 한 특정 빈도 없이 검색 되는 텍스트에 따라 주 창에 결과 반환할 수 있습니다. 모달 대화 상자와 마찬가지로, 모덜리스 대화 상자에서도 속성을 사용하여 결과를 반환할 수 있습니다. 그러나 대화 상자를 소유한 창에서 해당 속성을 검사할 시기를 알아야 합니다. 한 가지 방법은 대화 상자에서 텍스트를 찾을 때마다 발생하는 이벤트를 구현하는 것입니다. `FindDialogBox` 구현 된 `TextFoundEvent` 는 먼저가이 목적을 위해 대리자를 요구 합니다.  
  
 [!code-csharp[DialogBoxSample#TextFoundEventHandlerCODE](~/samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxSample/CSharp/TextFoundEventHandler.cs#textfoundeventhandlercode)]
 [!code-vb[DialogBoxSample#TextFoundEventHandlerCODE](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DialogBoxSample/VisualBasic/TextFoundEventHandler.vb#textfoundeventhandlercode)]  
  
 사용 하 여는 `TextFoundEventHandler` 대리자 `FindDialogBox` 구현 된 `TextFoundEvent`합니다.  
  
 [!code-csharp[DialogBoxSample#TextFoundEventCODEBEHIND1](~/samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxSample/CSharp/FindDialogBox.xaml.cs#textfoundeventcodebehind1)]
 [!code-vb[DialogBoxSample#TextFoundEventCODEBEHIND1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DialogBoxSample/VisualBasic/FindDialogBox.xaml.vb#textfoundeventcodebehind1)]  
[!code-csharp[DialogBoxSample#TextFoundEventCODEBEHIND2](~/samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxSample/CSharp/FindDialogBox.xaml.cs#textfoundeventcodebehind2)]
[!code-vb[DialogBoxSample#TextFoundEventCODEBEHIND2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DialogBoxSample/VisualBasic/FindDialogBox.xaml.vb#textfoundeventcodebehind2)]  
  
 따라서 `Find` 검색 결과 발견 되 면 이벤트를 발생 시킬 수 있습니다.  
  
 [!code-csharp[DialogBoxSample#TextFoundEventRaiseCODEBEHIND1](~/samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxSample/CSharp/FindDialogBox.xaml.cs#textfoundeventraisecodebehind1)]
 [!code-vb[DialogBoxSample#TextFoundEventRaiseCODEBEHIND1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DialogBoxSample/VisualBasic/FindDialogBox.xaml.vb#textfoundeventraisecodebehind1)]  
[!code-csharp[DialogBoxSample#TextFoundEventRaiseCODEBEHIND2](~/samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxSample/CSharp/FindDialogBox.xaml.cs#textfoundeventraisecodebehind2)]
[!code-vb[DialogBoxSample#TextFoundEventRaiseCODEBEHIND2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DialogBoxSample/VisualBasic/FindDialogBox.xaml.vb#textfoundeventraisecodebehind2)]  
[!code-csharp[DialogBoxSample#TextFoundEventRaiseCODEBEHIND3](~/samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxSample/CSharp/FindDialogBox.xaml.cs#textfoundeventraisecodebehind3)]
[!code-vb[DialogBoxSample#TextFoundEventRaiseCODEBEHIND3](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DialogBoxSample/VisualBasic/FindDialogBox.xaml.vb#textfoundeventraisecodebehind3)]  
[!code-csharp[DialogBoxSample#TextFoundEventRaiseCODEBEHIND4](~/samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxSample/CSharp/FindDialogBox.xaml.cs#textfoundeventraisecodebehind4)]
[!code-vb[DialogBoxSample#TextFoundEventRaiseCODEBEHIND4](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DialogBoxSample/VisualBasic/FindDialogBox.xaml.vb#textfoundeventraisecodebehind4)]  
[!code-csharp[DialogBoxSample#TextFoundEventRaiseCODEBEHIND5](~/samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxSample/CSharp/FindDialogBox.xaml.cs#textfoundeventraisecodebehind5)]
[!code-vb[DialogBoxSample#TextFoundEventRaiseCODEBEHIND5](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DialogBoxSample/VisualBasic/FindDialogBox.xaml.vb#textfoundeventraisecodebehind5)]  
  
 소유자 창에서는 그 후에 이 이벤트를 등록하고 처리해야 합니다.  
  
 [!code-csharp[DialogBoxSample#OpenFindDialogResultCODEBEHIND1](~/samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxSample/CSharp/MainWindow.xaml.cs#openfinddialogresultcodebehind1)]
 [!code-vb[DialogBoxSample#OpenFindDialogResultCODEBEHIND1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DialogBoxSample/VisualBasic/MainWindow.xaml.vb#openfinddialogresultcodebehind1)]  
[!code-csharp[DialogBoxSample#OpenFindDialogResultCODEBEHIND2](~/samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxSample/CSharp/MainWindow.xaml.cs#openfinddialogresultcodebehind2)]
[!code-vb[DialogBoxSample#OpenFindDialogResultCODEBEHIND2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DialogBoxSample/VisualBasic/MainWindow.xaml.vb#openfinddialogresultcodebehind2)]  
  
#### <a name="closing-a-modeless-dialog-box"></a>모덜리스 대화 상자 닫기  
 때문에 <xref:System.Windows.Window.DialogResult%2A> 시스템을 사용 하 여 모덜리스 대화 상자를 닫을 수 있습니다 설정 하지 않아도 다음을 포함 하는 메커니즘을 제공 합니다.  
  
-   클릭 하 여 **닫기** 제목 표시줄에 단추입니다.  
  
-   ALT+F4 누르기.  
  
-   선택 **닫습니다** 에서 합니다 **시스템** 메뉴.  
  
 코드 또는 호출할 수 있습니다 <xref:System.Windows.Window.Close%2A> 때 합니다 **닫기** 단추를 클릭 합니다.  
  
 [!code-csharp[DialogBoxSample#FindDialogCloseCODEBEHIND1](~/samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxSample/CSharp/FindDialogBox.xaml.cs#finddialogclosecodebehind1)]
 [!code-vb[DialogBoxSample#FindDialogCloseCODEBEHIND1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DialogBoxSample/VisualBasic/FindDialogBox.xaml.vb#finddialogclosecodebehind1)]  
[!code-csharp[DialogBoxSample#FindDialogCloseCODEBEHIND2](~/samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxSample/CSharp/FindDialogBox.xaml.cs#finddialogclosecodebehind2)]
[!code-vb[DialogBoxSample#FindDialogCloseCODEBEHIND2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DialogBoxSample/VisualBasic/FindDialogBox.xaml.vb#finddialogclosecodebehind2)]  
  
## <a name="see-also"></a>참고자료

- [Popup 개요](../controls/popup-overview.md)
- [대화 상자 샘플](https://go.microsoft.com/fwlink/?LinkID=159984)
- [ColorPicker 사용자 지정 컨트롤 샘플](https://go.microsoft.com/fwlink/?LinkID=159977)
