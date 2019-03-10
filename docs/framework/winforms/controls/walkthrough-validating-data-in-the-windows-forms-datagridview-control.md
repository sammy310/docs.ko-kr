---
title: '연습: Windows Forms DataGridView 컨트롤의 데이터 유효성 검사'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- validating data [Windows Forms], Windows Forms
- data [Windows Forms], validation
- DataGridView control [Windows Forms], data validation
- data grids [Windows Forms], validating data
- data validation [Windows Forms], Windows Forms
- walkthroughs [Windows Forms], DataGridView control
ms.assetid: a4f1d015-2969-430c-8ea2-b612d179c290
ms.openlocfilehash: 6bb46a9bc54652d781d3421051b7d6e09fc91772
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/09/2019
ms.locfileid: "57710032"
---
# <a name="walkthrough-validating-data-in-the-windows-forms-datagridview-control"></a>연습: Windows Forms DataGridView 컨트롤의 데이터 유효성 검사
데이터 항목 기능을 사용자에 게 표시할 때 자주를 양식에 입력 된 데이터의 유효성을 검사 해야 합니다. <xref:System.Windows.Forms.DataGridView> 클래스는 데이터는 데이터 저장소에 커밋되기 전에 유효성 검사를 수행 하는 편리한 방법을 제공 합니다. 처리 하 여 데이터를 확인할 수 있습니다는 <xref:System.Windows.Forms.DataGridView.CellValidating> 이벤트에 의해 발생 하는 <xref:System.Windows.Forms.DataGridView> 현재 셀이 변경 되는 경우.  
  
 이 연습에서는 행을 검색 합니다는 `Customers` Northwind 샘플 데이터베이스의 테이블 및 표시를 <xref:System.Windows.Forms.DataGridView> 제어 합니다. 사용자가 셀을 편집 하는 경우는 `CompanyName` 열과 셀을 유지 하려고 합니다 <xref:System.Windows.Forms.DataGridView.CellValidating> 이벤트 처리기는 비어 있지 않습니다; 새 값이 빈 문자열인 경우 되도록 새 회사 이름 문자열을 검사는 <xref:System.Windows.Forms.DataGridView> 사용자의 커서를 방지 하는 비어 있지 않은 문자열이 입력 될 때까지 셀 나갈 수 없도록 합니다.  
  
 이 항목의 코드를 단일 목록으로 복사하려면 [방법: Windows Forms DataGridView 컨트롤의 데이터 유효성 검사](how-to-validate-data-in-the-windows-forms-datagridview-control.md)합니다.  
  
## <a name="prerequisites"></a>전제 조건  
 이 연습을 완료하려면 다음 사항이 필요합니다.  
  
-   Northwind SQL Server 샘플 데이터베이스가 있는 서버에 액세스 합니다.  
  
## <a name="creating-the-form"></a>폼 만들기  
  
#### <a name="to-validate-data-entered-in-a-datagridview"></a>DataGridView에 입력 된 데이터의 유효성을 검사 하려면  
  
1.  파생 되는 클래스를 만듭니다 <xref:System.Windows.Forms.Form> 포함 된 <xref:System.Windows.Forms.DataGridView> 컨트롤 및 <xref:System.Windows.Forms.BindingSource> 구성 요소.  
  
     다음 코드 예제에서는 기본 초기화를 제공 하 고 포함 된 `Main` 메서드.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewDataValidation#01](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewDataValidation/CS/datavalidation.cs#01)]
     [!code-vb[System.Windows.Forms.DataGridViewDataValidation#01](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewDataValidation/VB/datavalidation.vb#01)]  
    [!code-csharp[System.Windows.Forms.DataGridViewDataValidation#02](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewDataValidation/CS/datavalidation.cs#02)]
    [!code-vb[System.Windows.Forms.DataGridViewDataValidation#02](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewDataValidation/VB/datavalidation.vb#02)]  
  
2.  데이터베이스에 연결 하는 정보를 처리 하는 것에 대 한 폼의 클래스 정의에서 메서드를 구현 합니다.  
  
     사용 하 여이 코드 예제는 `GetData` 채워진를 반환 하는 메서드 <xref:System.Data.DataTable> 개체입니다. 설정 해야 합니다 `connectionString` 데이터베이스에 대 한 적절 한 값으로 변수입니다.  
  
    > [!IMPORTANT]
    >  암호와 같은 중요한 정보를 연결 문자열 내에 저장하면 애플리케이션 보안 문제가 발생할 수 있습니다. Windows 인증을 라고도 통합된 보안을 사용 하는 데이터베이스에 대 한 액세스를 제어 하는 더욱 안전한 방식입니다. 자세한 내용은 [연결 정보 보호](../../data/adonet/protecting-connection-information.md)를 참조하세요.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewDataValidation#30](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewDataValidation/CS/datavalidation.cs#30)]
     [!code-vb[System.Windows.Forms.DataGridViewDataValidation#30](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewDataValidation/VB/datavalidation.vb#30)]  
  
3.  폼의 처리기를 구현 <xref:System.Windows.Forms.Form.Load> 초기화 하는 이벤트를 <xref:System.Windows.Forms.DataGridView> 및 <xref:System.Windows.Forms.BindingSource> 데이터 바인딩을 설정 합니다.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewDataValidation#10](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewDataValidation/CS/datavalidation.cs#10)]
     [!code-vb[System.Windows.Forms.DataGridViewDataValidation#10](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewDataValidation/VB/datavalidation.vb#10)]  
  
4.  에 대 한 처리기를 구현 합니다 <xref:System.Windows.Forms.DataGridView> 컨트롤의 <xref:System.Windows.Forms.DataGridView.CellValidating> 고 <xref:System.Windows.Forms.DataGridView.CellEndEdit> 이벤트입니다.  
  
     <xref:System.Windows.Forms.DataGridView.CellValidating> 이벤트 처리기가 결정 하는 위치 하는지 여부를 셀의 값을 `CompanyName` 열이 비어 합니다. 셀 값에는 유효성 검사가 실패 하면, 설정 합니다 <xref:System.ComponentModel.CancelEventArgs.Cancel%2A> 의 속성을 <xref:System.Windows.Forms.DataGridViewCellValidatingEventArgs?displayProperty=nameWithType> 클래스를 `true`. 이 인해는 <xref:System.Windows.Forms.DataGridView> 커서에서 셀 나갈 수 없도록 방지 하기 위해 제어 합니다. 설정 된 <xref:System.Windows.Forms.DataGridViewRow.ErrorText%2A> 행을 설명 하는 문자열 속성입니다. 오류 텍스트를 포함 하는 도구 설명이 있는 오류 아이콘이 표시 됩니다. 에 <xref:System.Windows.Forms.DataGridView.CellEndEdit> 이벤트 처리기를 설정 합니다 <xref:System.Windows.Forms.DataGridViewRow.ErrorText%2A> 속성을 빈 문자열로 행. <xref:System.Windows.Forms.DataGridView.CellEndEdit> 셀 유효성 검사가 실패 하는 경우 수행할 수 없습니다. 편집 모드를 종료 하는 경우에 이벤트가 발생 합니다.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewDataValidation#20](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewDataValidation/CS/datavalidation.cs#20)]
     [!code-vb[System.Windows.Forms.DataGridViewDataValidation#20](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewDataValidation/VB/datavalidation.vb#20)]  
  
## <a name="testing-the-application"></a>애플리케이션 테스트  
 이제 예상 대로 작동 되도록 폼을 테스트할 수 있습니다.  
  
#### <a name="to-test-the-form"></a>폼을 테스트 하려면  
  
-   애플리케이션을 컴파일하고 실행합니다.  
  
     표시 됩니다는 <xref:System.Windows.Forms.DataGridView> 데이터로 채워진는 `Customers` 테이블입니다. 셀을 두 번 클릭 합니다 `CompanyName` 열 값을 편집할 수 있습니다. 모든 문자를 삭제 하 고 셀을 종료 하려면 TAB 키를 누르면는 <xref:System.Windows.Forms.DataGridView> 종료 수 없습니다. 셀에는 비어 있지 않은 문자열을 입력할 경우는 <xref:System.Windows.Forms.DataGridView> 제어를 사용 하면 셀을 종료 합니다.  
  
## <a name="next-steps"></a>다음 단계  
 이 응용 프로그램의 기본적인 이해를 제공 합니다 <xref:System.Windows.Forms.DataGridView> 컨트롤의 기능입니다. 동작과 모양을 사용자 지정할 수 있습니다는 <xref:System.Windows.Forms.DataGridView> 여러 가지 방법으로 제어 합니다.  
  
-   헤더 및 테두리 스타일을 변경 합니다. 자세한 내용은 [방법: 변경 된 테두리 및 모눈선 스타일에는 Windows Forms DataGridView 컨트롤](change-the-border-and-gridline-styles-in-the-datagrid.md)합니다.  
  
-   사용 하도록 설정 하거나 사용자 입력을 제한 합니다 <xref:System.Windows.Forms.DataGridView> 제어 합니다. 자세한 내용은 [방법: 행 추가 방지 하 고 삭제는 Windows Forms DataGridView 컨트롤](prevent-row-addition-and-deletion-datagridview.md), 및 [방법: 에서 열을 설정 읽기 전용으로 Windows Forms DataGridView 컨트롤](how-to-make-columns-read-only-in-the-windows-forms-datagridview-control.md)합니다.  
  
-   데이터베이스 관련 오류에 대 한 사용자 입력을 확인 합니다. 자세한 내용은 [연습: Forms DataGridView 컨트롤의 Windows에서 데이터 입력 중에 발생 하는 오류 처리](handling-errors-that-occur-during-data-entry-in-the-datagrid.md)합니다.  
  
-   가상 모드를 사용 하 여 매우 큰 데이터 집합을 처리 합니다. 자세한 내용은 [연습: Forms DataGridView 컨트롤의 Windows에서 가상 모드 구현](implementing-virtual-mode-wf-datagridview-control.md)합니다.  
  
-   셀의 모양을 사용자 지정 합니다. 자세한 내용은 [방법: Windows Forms DataGridView 컨트롤에서 셀 모양 사용자 지정](customize-the-appearance-of-cells-in-the-datagrid.md) 고 [방법: Windows Forms DataGridView 컨트롤의 글꼴 및 색 스타일 설정](how-to-set-font-and-color-styles-in-the-windows-forms-datagridview-control.md)합니다.  
  
## <a name="see-also"></a>참고자료
- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.BindingSource>
- [Windows Forms DataGridView 컨트롤의 데이터 입력](data-entry-in-the-windows-forms-datagridview-control.md)
- [방법: Windows Forms DataGridView 컨트롤의 데이터 유효성 검사](how-to-validate-data-in-the-windows-forms-datagridview-control.md)
- [연습: Windows Forms DataGridView 컨트롤에서 데이터 입력 중에 발생 하는 오류 처리](handling-errors-that-occur-during-data-entry-in-the-datagrid.md)
- [연결 정보 보호](../../data/adonet/protecting-connection-information.md)
