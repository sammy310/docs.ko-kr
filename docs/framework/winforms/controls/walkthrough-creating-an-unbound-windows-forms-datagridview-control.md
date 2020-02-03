---
title: 바인딩되지 않은 DataGridView 컨트롤 만들기
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- data [Windows Forms], displaying without binding to data source
- DataGridView control [Windows Forms], unbound data
- DataGridView control [Windows Forms], displaying data without binding to a data source
- data [Windows Forms], unbound
- walkthroughs [Windows Forms], DataGridView control
ms.assetid: 5a8d6afa-1b4b-4b24-8db8-501086ffdebe
ms.openlocfilehash: ceb75d4ee845d1f643d4d88d5a9f1bde73edcc70
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/24/2020
ms.locfileid: "76740181"
---
# <a name="walkthrough-creating-an-unbound-windows-forms-datagridview-control"></a>연습: 바인딩되지 않은 Windows Forms DataGridView 컨트롤 만들기
데이터베이스에서 시작 되지 않는 테이블 형식 데이터를 표시 하는 것이 좋습니다. 예를 들어, 2 차원 문자열 배열의 내용을 표시할 수 있습니다. <xref:System.Windows.Forms.DataGridView> 클래스는 데이터 소스에 바인딩하지 않고 데이터를 표시 하는 쉽고 사용자 지정 가능한 방법을 제공 합니다. 이 연습에서는 <xref:System.Windows.Forms.DataGridView> 컨트롤을 채우고 "바인딩되지 않은" 모드에서 행의 추가 및 삭제를 관리 하는 방법을 보여 줍니다. 기본적으로 사용자는 새 행을 추가할 수 있습니다. 행 추가를 방지 하려면 <xref:System.Windows.Forms.DataGridView.AllowUserToAddRows%2A> 속성을 `false`설정 합니다.  
  
 이 항목의 코드를 단일 목록으로 복사 하려면 [방법: 바인딩되지 않은 Windows Forms DataGridView 컨트롤 만들기](how-to-create-an-unbound-windows-forms-datagridview-control.md)를 참조 하세요.  
  
## <a name="creating-the-form"></a>폼 만들기  
  
#### <a name="to-use-an-unbound-datagridview-control"></a>바인딩되지 않은 DataGridView 컨트롤을 사용 하려면  
  
1. <xref:System.Windows.Forms.Form>에서 파생 되 고 다음 변수 선언 및 `Main` 메서드를 포함 하는 클래스를 만듭니다.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewSimpleUnbound#01](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSimpleUnbound/CS/simpleunbound.cs#01)]
     [!code-vb[System.Windows.Forms.DataGridViewSimpleUnbound#01](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSimpleUnbound/VB/simpleunbound.vb#01)]  
    [!code-csharp[System.Windows.Forms.DataGridViewSimpleUnbound#02](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSimpleUnbound/CS/simpleunbound.cs#02)]
    [!code-vb[System.Windows.Forms.DataGridViewSimpleUnbound#02](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSimpleUnbound/VB/simpleunbound.vb#02)]  
  
2. 폼의 클래스 정의에 `SetupLayout` 메서드를 구현 하 여 폼의 레이아웃을 설정 합니다.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewSimpleUnbound#20](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSimpleUnbound/CS/simpleunbound.cs#20)]
     [!code-vb[System.Windows.Forms.DataGridViewSimpleUnbound#20](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSimpleUnbound/VB/simpleunbound.vb#20)]  
  
3. `SetupDataGridView` 메서드를 만들어 <xref:System.Windows.Forms.DataGridView> 열과 속성을 설정 합니다.  
  
     이 메서드는 먼저 <xref:System.Windows.Forms.DataGridView> 컨트롤을 폼의 <xref:System.Windows.Forms.Control.Controls%2A> 컬렉션에 추가 합니다. 그런 다음 <xref:System.Windows.Forms.DataGridView.ColumnCount%2A> 속성을 사용 하 여 표시할 열 수를 설정 합니다. 열 머리글의 기본 스타일은 <xref:System.Windows.Forms.DataGridView.ColumnHeadersDefaultCellStyle%2A> 속성이 반환 하는 <xref:System.Windows.Forms.DataGridViewCellStyle>의 <xref:System.Windows.Forms.DataGridViewCellStyle.BackColor%2A>, <xref:System.Windows.Forms.DataGridViewCellStyle.ForeColor%2A>및 <xref:System.Windows.Forms.DataGridViewCellStyle.Font%2A> 속성을 설정 하 여 설정 됩니다.  
  
     레이아웃 및 모양 속성을 설정한 다음 열 이름이 할당 됩니다. 이 메서드가 종료 되 면 <xref:System.Windows.Forms.DataGridView> 컨트롤을 채울 준비가 된 것입니다.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewSimpleUnbound#30](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSimpleUnbound/CS/simpleunbound.cs#30)]
     [!code-vb[System.Windows.Forms.DataGridViewSimpleUnbound#30](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSimpleUnbound/VB/simpleunbound.vb#30)]  
  
4. <xref:System.Windows.Forms.DataGridView> 컨트롤에 행을 추가 하는 `PopulateDataGridView` 메서드를 만듭니다.  
  
     각 행은 노래와 관련 정보를 나타냅니다.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewSimpleUnbound#40](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSimpleUnbound/CS/simpleunbound.cs#40)]
     [!code-vb[System.Windows.Forms.DataGridViewSimpleUnbound#40](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSimpleUnbound/VB/simpleunbound.vb#40)]  
  
5. 유틸리티 메서드가 준비 되 면 이벤트 처리기를 연결할 수 있습니다.  
  
     **추가** 및 **삭제** 단추의 <xref:System.Windows.Forms.Control.Click> 이벤트, 폼의 <xref:System.Windows.Forms.Form.Load> 이벤트 및 <xref:System.Windows.Forms.DataGridView> 컨트롤의 <xref:System.Windows.Forms.DataGridView.CellFormatting> 이벤트를 처리 합니다.  
  
     **추가** 단추의 <xref:System.Windows.Forms.Control.Click> 이벤트가 발생 하면 새 빈 행이 <xref:System.Windows.Forms.DataGridView>에 추가 됩니다.  
  
     **삭제** 단추의 <xref:System.Windows.Forms.Control.Click> 이벤트가 발생 하면 새 레코드의 행이 아닌 한 선택한 행이 삭제 됩니다 .이 경우 사용자가 새 행을 추가할 수 있습니다. 이 행은 항상 <xref:System.Windows.Forms.DataGridView> 컨트롤의 마지막 행입니다.  
  
     폼의 <xref:System.Windows.Forms.Form.Load> 이벤트가 발생 하면 `SetupLayout`, `SetupDataGridView`및 `PopulateDataGridView` 유틸리티 메서드가 호출 됩니다.  
  
     <xref:System.Windows.Forms.DataGridView.CellFormatting> 이벤트가 발생 하는 경우에는 셀의 값을 구문 분석할 수 없는 경우 `Date` 열의 각 셀에 긴 날짜 형식이 지정 됩니다.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewSimpleUnbound#10](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSimpleUnbound/CS/simpleunbound.cs#10)]
     [!code-vb[System.Windows.Forms.DataGridViewSimpleUnbound#10](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSimpleUnbound/VB/simpleunbound.vb#10)]  
  
## <a name="testing-the-application"></a>애플리케이션 테스트  
 이제 폼을 테스트 하 여 예상 대로 동작 하는지 확인할 수 있습니다.  
  
#### <a name="to-test-the-form"></a>폼을 테스트 하려면  
  
- F5 키를 눌러 애플리케이션을 실행합니다.  
  
     `PopulateDataGridView`에 나열 된 노래를 표시 하는 <xref:System.Windows.Forms.DataGridView> 컨트롤이 표시 됩니다. **행 추가** 단추를 사용 하 여 새 행을 추가 하 고 **행 삭제** 단추를 사용 하 여 선택한 행을 삭제할 수 있습니다. 바인딩되지 않은 <xref:System.Windows.Forms.DataGridView> 컨트롤은 데이터 저장소이 고 해당 데이터는 <xref:System.Data.DataSet> 또는 배열과 같은 외부 소스와는 독립적입니다.  
  
## <a name="next-steps"></a>다음 단계  
 이 응용 프로그램은 <xref:System.Windows.Forms.DataGridView> 컨트롤의 기능에 대 한 기본적인 이해를 제공 합니다. 여러 가지 방법으로 <xref:System.Windows.Forms.DataGridView> 컨트롤의 모양과 동작을 사용자 지정할 수 있습니다.  
  
- 테두리 및 머리글 스타일을 변경 합니다. 자세한 내용은 [방법: 테두리 및 Windows Forms DataGridView 컨트롤의 모눈선 스타일 변경](change-the-border-and-gridline-styles-in-the-datagrid.md)합니다.  
  
- 사용자 입력을 <xref:System.Windows.Forms.DataGridView> 컨트롤로 설정 하거나 제한 합니다. 자세한 내용은 [방법: Datagridview 컨트롤 Windows Forms에서 행 추가 및 삭제 방지](prevent-row-addition-and-deletion-datagridview.md)및 [방법: Windows Forms Datagridview 컨트롤에서 열을 읽기 전용으로 설정](how-to-make-columns-read-only-in-the-windows-forms-datagridview-control.md)을 참조 하세요.  
  
- 데이터베이스 관련 오류에 대 한 사용자 입력을 확인 합니다. 자세한 내용은 [연습: Windows Forms DataGridView 컨트롤에서 데이터 입력 중에 발생 하는 오류 처리](handling-errors-that-occur-during-data-entry-in-the-datagrid.md)를 참조 하세요.  
  
- 가상 모드를 사용 하 여 매우 큰 데이터 집합을 처리 합니다. 자세한 내용은 [연습: Windows Forms DataGridView 컨트롤에서 가상 모드 구현](implementing-virtual-mode-wf-datagridview-control.md)을 참조 하세요.  
  
- 셀의 모양을 사용자 지정 합니다. 자세한 내용은 [방법: Datagridview 컨트롤 Windows Forms에서 셀 모양 사용자 지정](customize-the-appearance-of-cells-in-the-datagrid.md) 및 [방법: Windows Forms Datagridview 컨트롤의 기본 셀 스타일 설정](how-to-set-default-cell-styles-for-the-windows-forms-datagridview-control.md)을 참조 하세요.  
  
## <a name="see-also"></a>참고 항목

- <xref:System.Windows.Forms.DataGridView>
- [Windows Forms DataGridView 컨트롤에서 데이터 표시](displaying-data-in-the-windows-forms-datagridview-control.md)
- [방법: 바인딩되지 않은 Windows Forms DataGridView 컨트롤 만들기](how-to-create-an-unbound-windows-forms-datagridview-control.md)
- [Windows Forms DataGridView 컨트롤의 데이터 디스플레이 모드](data-display-modes-in-the-windows-forms-datagridview-control.md)
