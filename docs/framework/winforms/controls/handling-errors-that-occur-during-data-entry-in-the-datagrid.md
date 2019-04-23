---
title: '연습: Windows Forms DataGridView 컨트롤에서 데이터 입력 중에 발생하는 오류 처리'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- error handling [Windows Forms], dataGridView control
- data grids [Windows Forms], error handling
- DataGridView control [Windows Forms], error handling
- data entry [Windows Forms], error handling
- error handling [Windows Forms], data entry
- walkthroughs [Windows Forms], DataGridView control
ms.assetid: 30a68b85-d3af-4946-83c1-1e2d010d0511
ms.openlocfilehash: 9e803b6450fb8c9ade4adde5bf98fb1c3c62c861
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59313222"
---
# <a name="walkthrough-handling-errors-that-occur-during-data-entry-in-the-windows-forms-datagridview-control"></a>연습: Windows Forms DataGridView 컨트롤에서 데이터 입력 중에 발생하는 오류 처리
내부 데이터 저장소에서 오류를 처리 하는 것은 데이터 입력 응용 프로그램에 필요한 기능입니다. Windows Forms <xref:System.Windows.Forms.DataGridView> 컨트롤을 사용 하면이 쉽게 노출 하 여는 <xref:System.Windows.Forms.DataGridView.DataError> 데이터 저장소는 끊어진된 비즈니스 규칙 또는 제약 조건 위반을 감지 하는 경우 발생 하는 이벤트입니다.  
  
 이 연습에서는 행을 검색 합니다는 `Customers` Northwind 샘플 데이터베이스의 테이블 및 표시를 <xref:System.Windows.Forms.DataGridView> 제어 합니다. 에 중복 된 `CustomerID` 기존 행을 편집된 하거나 새 행의 값이 검색 되는 <xref:System.Windows.Forms.DataGridView.DataError> 이벤트 발생을 표시 하 여 처리 됩니다는 <xref:System.Windows.Forms.MessageBox> 예외를 설명 하는 합니다.  
  
 이 항목의 코드를 단일 목록으로 복사하려면 [방법: Forms DataGridView 컨트롤의 Windows에서 데이터 입력 중에 발생 하는 오류 처리](handle-errors-that-occur-during-data-entry-in-the-datagrid.md)합니다.  
  
## <a name="prerequisites"></a>전제 조건  
 이 연습을 완료하려면 다음 사항이 필요합니다.  
  
-   Northwind SQL Server 샘플 데이터베이스가 있는 서버에 액세스 합니다.  
  
## <a name="creating-the-form"></a>폼 만들기  
  
#### <a name="to-handle-data-entry-errors-in-the-datagridview-control"></a>DataGridView 컨트롤에서 데이터 입력 오류를 처리 하려면  
  
1. 파생 되는 클래스를 만듭니다 <xref:System.Windows.Forms.Form> 포함 된 <xref:System.Windows.Forms.DataGridView> 컨트롤 및 <xref:System.Windows.Forms.BindingSource> 구성 요소.  
  
     다음 코드 예제에서는 기본 초기화를 제공 하 고 포함 된 `Main` 메서드.  
  
     [!code-csharp[System.Windows.Forms.DataGridView.DataError#01](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.DataError/CS/errorhandling.cs#01)]
     [!code-vb[System.Windows.Forms.DataGridView.DataError#01](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.DataError/VB/errorhandling.vb#01)]  
    [!code-csharp[System.Windows.Forms.DataGridView.DataError#02](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.DataError/CS/errorhandling.cs#02)]
    [!code-vb[System.Windows.Forms.DataGridView.DataError#02](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.DataError/VB/errorhandling.vb#02)]  
  
2. 데이터베이스에 연결 하는 정보를 처리 하는 것에 대 한 폼의 클래스 정의에서 메서드를 구현 합니다.  
  
     사용 하 여이 코드 예제는 `GetData` 채워진를 반환 하는 메서드 <xref:System.Data.DataTable> 개체입니다. 설정 해야 합니다 `connectionString` 데이터베이스에 대 한 적절 한 값으로 변수입니다.  
  
    > [!IMPORTANT]
    >  암호와 같은 중요한 정보를 연결 문자열 내에 저장하면 애플리케이션 보안 문제가 발생할 수 있습니다. 데이터베이스 액세스를 제어할 경우에는 통합 보안이라고도 하는 Windows 인증을 사용하는 방법이 더 안전합니다. 자세한 내용은 [연결 정보 보호](../../data/adonet/protecting-connection-information.md)를 참조하세요.  
  
     [!code-csharp[System.Windows.Forms.DataGridView.DataError#30](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.DataError/CS/errorhandling.cs#30)]
     [!code-vb[System.Windows.Forms.DataGridView.DataError#30](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.DataError/VB/errorhandling.vb#30)]  
  
3. 폼의 처리기를 구현 <xref:System.Windows.Forms.Form.Load> 초기화 하는 이벤트를 <xref:System.Windows.Forms.DataGridView> 및 <xref:System.Windows.Forms.BindingSource> 데이터 바인딩을 설정 합니다.  
  
     [!code-csharp[System.Windows.Forms.DataGridView.DataError#10](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.DataError/CS/errorhandling.cs#10)]
     [!code-vb[System.Windows.Forms.DataGridView.DataError#10](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.DataError/VB/errorhandling.vb#10)]  
  
4. 처리를 <xref:System.Windows.Forms.DataGridView.DataError> 이벤트에는 <xref:System.Windows.Forms.DataGridView>합니다.  
  
     오류에 대 한 컨텍스트는 커밋 작업 인 경우에 오류를 표시 한 <xref:System.Windows.Forms.MessageBox>합니다.  
  
     [!code-csharp[System.Windows.Forms.DataGridView.DataError#20](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.DataError/CS/errorhandling.cs#20)]
     [!code-vb[System.Windows.Forms.DataGridView.DataError#20](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.DataError/VB/errorhandling.vb#20)]  
  
## <a name="testing-the-application"></a>애플리케이션 테스트  
 이제 예상 대로 작동 되도록 폼을 테스트할 수 있습니다.  
  
#### <a name="to-test-the-form"></a>폼을 테스트 하려면  
  
-   F5 키를 눌러 애플리케이션을 실행합니다.  
  
     표시 됩니다는 <xref:System.Windows.Forms.DataGridView> 컨트롤 Customers 테이블의 데이터로 채워집니다. 에 중복 값을 입력 하는 경우 `CustomerID` 편집 커밋, 셀 값을 자동으로 복원 되 고 표시 됩니다는 <xref:System.Windows.Forms.MessageBox> 데이터 입력 오류를 표시 하는 합니다.  
  
## <a name="next-steps"></a>다음 단계  
 이 응용 프로그램의 기본적인 이해를 제공 합니다 <xref:System.Windows.Forms.DataGridView> 컨트롤의 기능입니다. 동작과 모양을 사용자 지정할 수 있습니다는 <xref:System.Windows.Forms.DataGridView> 여러 가지 방법으로 제어 합니다.  
  
-   헤더 및 테두리 스타일을 변경 합니다. 자세한 내용은 [방법: 변경 된 테두리 및 모눈선 스타일에는 Windows Forms DataGridView 컨트롤](change-the-border-and-gridline-styles-in-the-datagrid.md)합니다.  
  
-   사용 하도록 설정 하거나 사용자 입력을 제한 합니다 <xref:System.Windows.Forms.DataGridView> 제어 합니다. 자세한 내용은 [방법: 행 추가 방지 하 고 삭제는 Windows Forms DataGridView 컨트롤](prevent-row-addition-and-deletion-datagridview.md), 및 [방법: 에서 열을 설정 읽기 전용으로 Windows Forms DataGridView 컨트롤](how-to-make-columns-read-only-in-the-windows-forms-datagridview-control.md)합니다.  
  
-   사용자 입력의 유효성을 검사 합니다 <xref:System.Windows.Forms.DataGridView> 제어 합니다. 자세한 내용은 [연습: Forms DataGridView 컨트롤을 Windows의 데이터 유효성 검사](walkthrough-validating-data-in-the-windows-forms-datagridview-control.md)합니다.  
  
-   가상 모드를 사용 하 여 매우 큰 데이터 집합을 처리 합니다. 자세한 내용은 [연습: Forms DataGridView 컨트롤의 Windows에서 가상 모드 구현](implementing-virtual-mode-wf-datagridview-control.md)합니다.  
  
-   셀의 모양을 사용자 지정 합니다. 자세한 내용은 [방법: Windows Forms DataGridView 컨트롤에서 셀 모양 사용자 지정](customize-the-appearance-of-cells-in-the-datagrid.md) 고 [방법: Windows Forms DataGridView 컨트롤에 기본 셀 스타일 설정](how-to-set-default-cell-styles-for-the-windows-forms-datagridview-control.md)합니다.  
  
## <a name="see-also"></a>참고자료

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.BindingSource>
- [Windows Forms DataGridView 컨트롤의 데이터 입력](data-entry-in-the-windows-forms-datagridview-control.md)
- [방법: Windows Forms DataGridView 컨트롤에서 데이터 입력 중에 발생 하는 오류 처리](handle-errors-that-occur-during-data-entry-in-the-datagrid.md)
- [연습: Windows Forms DataGridView 컨트롤의 데이터 유효성 검사](walkthrough-validating-data-in-the-windows-forms-datagridview-control.md)
- [연결 정보 보호](../../data/adonet/protecting-connection-information.md)
