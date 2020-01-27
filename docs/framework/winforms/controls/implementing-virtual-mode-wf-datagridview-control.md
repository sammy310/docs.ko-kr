---
title: '연습: DataGridView 컨트롤에서 가상 모드 구현'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- data [Windows Forms], managing large data sets
- DataGridView control [Windows Forms], virtual mode
- virtual mode [Windows Forms], walkthroughs
- DataGridView control [Windows Forms], large data sets
- walkthroughs [Windows Forms], DataGridView control
ms.assetid: 74eb5276-5ab8-4ce0-8005-dae751d85f7c
ms.openlocfilehash: 5db97b321238bc371c94e627a387bd83ca31b58a
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/24/2020
ms.locfileid: "76746521"
---
# <a name="walkthrough-implementing-virtual-mode-in-the-windows-forms-datagridview-control"></a>연습: Windows Forms DataGridView 컨트롤에서 가상 모드 구현
<xref:System.Windows.Forms.DataGridView> 컨트롤에 매우 많은 양의 테이블 형식 데이터를 표시 하려는 경우 <xref:System.Windows.Forms.DataGridView.VirtualMode%2A> 속성을 `true`로 설정 하 고 컨트롤의 데이터 저장소와의 상호 작용을 명시적으로 관리할 수 있습니다. 이렇게 하면이 상황에서 컨트롤의 성능을 세밀 하 게 조정할 수 있습니다.  
  
 <xref:System.Windows.Forms.DataGridView> 컨트롤은 사용자 지정 데이터 저장소와 상호 작용 하기 위해 처리할 수 있는 몇 가지 이벤트를 제공 합니다. 이 연습에서는 이러한 이벤트 처리기를 구현 하는 과정을 안내 합니다. 이 항목의 코드 예제에서는 매우 간단한 데이터 원본을 설명 하기 위해 사용 합니다. 프로덕션 설정에서는 일반적으로 캐시에 표시 해야 하는 행만 로드 하 고 캐시를 상호 작용 하 고 업데이트 하는 <xref:System.Windows.Forms.DataGridView> 이벤트를 처리 합니다. 자세한 내용은 [Windows Forms DataGridView 컨트롤에서 Just-in-time 데이터 로드를 사용 하 여 가상 모드 구현](implementing-virtual-mode-jit-data-loading-in-the-datagrid.md) 을 참조 하세요.  
  
 이 항목의 코드를 단일 목록으로 복사 하려면 [방법: DataGridView 컨트롤 Windows Forms에서 가상 모드 구현](how-to-implement-virtual-mode-in-the-windows-forms-datagridview-control.md)을 참조 하세요.  
  
## <a name="creating-the-form"></a>폼 만들기  
  
#### <a name="to-implement-virtual-mode"></a>가상 모드를 구현 하려면  
  
1. <xref:System.Windows.Forms.Form>에서 파생 되 고 <xref:System.Windows.Forms.DataGridView> 컨트롤을 포함 하는 클래스를 만듭니다.  
  
     다음 코드에는 몇 가지 기본 초기화가 포함 되어 있습니다. 이후 단계에서 사용 되는 일부 변수를 선언 하 고, `Main` 메서드를 제공 하며, 클래스 생성자에서 간단한 양식 레이아웃을 제공 합니다.  
  
     [!code-cpp[System.Windows.Forms.DataGridView.VirtualMode#001](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CPP/virtualmode.cpp#001)]
     [!code-csharp[System.Windows.Forms.DataGridView.VirtualMode#001](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CS/virtualmode.cs#001)]
     [!code-vb[System.Windows.Forms.DataGridView.VirtualMode#001](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/VB/virtualmode.vb#001)]  
    [!code-cpp[System.Windows.Forms.DataGridView.VirtualMode#002](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CPP/virtualmode.cpp#002)]
    [!code-csharp[System.Windows.Forms.DataGridView.VirtualMode#002](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CS/virtualmode.cs#002)]
    [!code-vb[System.Windows.Forms.DataGridView.VirtualMode#002](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/VB/virtualmode.vb#002)]  
  
2. <xref:System.Windows.Forms.DataGridView> 컨트롤을 초기화 하 고 데이터 저장소를 샘플 값으로 채우는 폼의 <xref:System.Windows.Forms.Form.Load> 이벤트에 대 한 처리기를 구현 합니다.  
  
     [!code-cpp[System.Windows.Forms.DataGridView.VirtualMode#110](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CPP/virtualmode.cpp#110)]
     [!code-csharp[System.Windows.Forms.DataGridView.VirtualMode#110](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CS/virtualmode.cs#110)]
     [!code-vb[System.Windows.Forms.DataGridView.VirtualMode#110](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/VB/virtualmode.vb#110)]  
  
3. 현재 편집 중인 데이터 저장소 또는 `Customer` 개체에서 요청 된 셀 값을 검색 하는 <xref:System.Windows.Forms.DataGridView.CellValueNeeded> 이벤트에 대 한 처리기를 구현 합니다.  
  
     이 이벤트는 <xref:System.Windows.Forms.DataGridView> 컨트롤이 셀을 그려야 할 때마다 발생 합니다.  
  
     [!code-cpp[System.Windows.Forms.DataGridView.VirtualMode#120](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CPP/virtualmode.cpp#120)]
     [!code-csharp[System.Windows.Forms.DataGridView.VirtualMode#120](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CS/virtualmode.cs#120)]
     [!code-vb[System.Windows.Forms.DataGridView.VirtualMode#120](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/VB/virtualmode.vb#120)]  
  
4. 편집 된 행을 나타내는 `Customer` 개체에 편집 된 셀 값을 저장 하는 <xref:System.Windows.Forms.DataGridView.CellValuePushed> 이벤트에 대 한 처리기를 구현 합니다. 이 이벤트는 사용자가 셀 값 변경 내용을 커밋할 때마다 발생 합니다.  
  
     [!code-cpp[System.Windows.Forms.DataGridView.VirtualMode#130](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CPP/virtualmode.cpp#130)]
     [!code-csharp[System.Windows.Forms.DataGridView.VirtualMode#130](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CS/virtualmode.cs#130)]
     [!code-vb[System.Windows.Forms.DataGridView.VirtualMode#130](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/VB/virtualmode.vb#130)]  
  
5. 새로 만든 행을 나타내는 새 `Customer` 개체를 만드는 <xref:System.Windows.Forms.DataGridView.NewRowNeeded> 이벤트에 대 한 처리기를 구현 합니다.  
  
     이 이벤트는 사용자가 새 레코드에 대 한 행을 입력할 때마다 발생 합니다.  
  
     [!code-cpp[System.Windows.Forms.DataGridView.VirtualMode#140](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CPP/virtualmode.cpp#140)]
     [!code-csharp[System.Windows.Forms.DataGridView.VirtualMode#140](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CS/virtualmode.cs#140)]
     [!code-vb[System.Windows.Forms.DataGridView.VirtualMode#140](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/VB/virtualmode.vb#140)]  
  
6. 새 행 또는 수정 된 행을 데이터 저장소에 저장 하는 <xref:System.Windows.Forms.DataGridView.RowValidated> 이벤트에 대 한 처리기를 구현 합니다.  
  
     이 이벤트는 사용자가 현재 행을 변경할 때마다 발생 합니다.  
  
     [!code-cpp[System.Windows.Forms.DataGridView.VirtualMode#150](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CPP/virtualmode.cpp#150)]
     [!code-csharp[System.Windows.Forms.DataGridView.VirtualMode#150](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CS/virtualmode.cs#150)]
     [!code-vb[System.Windows.Forms.DataGridView.VirtualMode#150](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/VB/virtualmode.vb#150)]  
  
7. 사용자가 편집 모드에서 ESC 키를 두 번 누르거나 편집 모드 외부에서 변경할지 때 <xref:System.Windows.Forms.DataGridView.CancelRowEdit> 이벤트가 발생 하는지 여부를 나타내는 <xref:System.Windows.Forms.DataGridView.RowDirtyStateNeeded> 이벤트에 대 한 처리기를 구현 합니다.  
  
     기본적으로 <xref:System.Windows.Forms.DataGridView.CancelRowEdit> <xref:System.Windows.Forms.QuestionEventArgs.Response%2A?displayProperty=nameWithType> 속성이 <xref:System.Windows.Forms.DataGridView.RowDirtyStateNeeded> 이벤트 처리기에서 `true`로 설정 되지 않은 경우 현재 행의 셀이 수정 되 면 행 변경할지 때 발생 합니다. 이 이벤트는 커밋 범위가 런타임에 결정 되는 경우에 유용 합니다.  
  
     [!code-cpp[System.Windows.Forms.DataGridView.VirtualMode#160](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CPP/virtualmode.cpp#160)]
     [!code-csharp[System.Windows.Forms.DataGridView.VirtualMode#160](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CS/virtualmode.cs#160)]
     [!code-vb[System.Windows.Forms.DataGridView.VirtualMode#160](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/VB/virtualmode.vb#160)]  
  
8. 현재 행을 나타내는 `Customer` 개체의 값을 삭제 하는 <xref:System.Windows.Forms.DataGridView.CancelRowEdit> 이벤트에 대 한 처리기를 구현 합니다.  
  
     사용자가 편집 모드에서 ESC 키를 두 번 누르거나 편집 모드 외부에서 변경할지 때이 이벤트가 발생 합니다. 현재 행의 셀이 수정 되지 않았거나 <xref:System.Windows.Forms.QuestionEventArgs.Response%2A?displayProperty=nameWithType> 속성 값이 <xref:System.Windows.Forms.DataGridView.RowDirtyStateNeeded> 이벤트 처리기에서 `false`로 설정 된 경우에는이 이벤트가 발생 하지 않습니다.  
  
     [!code-cpp[System.Windows.Forms.DataGridView.VirtualMode#170](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CPP/virtualmode.cpp#170)]
     [!code-csharp[System.Windows.Forms.DataGridView.VirtualMode#170](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CS/virtualmode.cs#170)]
     [!code-vb[System.Windows.Forms.DataGridView.VirtualMode#170](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/VB/virtualmode.vb#170)]  
  
9. 데이터 저장소에서 기존 `Customer` 개체를 삭제 하거나 새로 만든 행을 나타내는 저장 되지 않은 `Customer` 개체를 삭제 하는 <xref:System.Windows.Forms.DataGridView.UserDeletingRow> 이벤트에 대 한 처리기를 구현 합니다.  
  
     이 이벤트는 사용자가 행 머리글을 클릭 하 고 DELETE 키를 눌러 행을 삭제할 때마다 발생 합니다.  
  
     [!code-cpp[System.Windows.Forms.DataGridView.VirtualMode#180](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CPP/virtualmode.cpp#180)]
     [!code-csharp[System.Windows.Forms.DataGridView.VirtualMode#180](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CS/virtualmode.cs#180)]
     [!code-vb[System.Windows.Forms.DataGridView.VirtualMode#180](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/VB/virtualmode.vb#180)]  
  
10. 이 코드 예제에서 사용 하는 데이터 항목을 나타내는 간단한 `Customers` 클래스를 구현 합니다.  
  
     [!code-cpp[System.Windows.Forms.DataGridView.VirtualMode#200](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CPP/virtualmode.cpp#200)]
     [!code-csharp[System.Windows.Forms.DataGridView.VirtualMode#200](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CS/virtualmode.cs#200)]
     [!code-vb[System.Windows.Forms.DataGridView.VirtualMode#200](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/VB/virtualmode.vb#200)]  
  
## <a name="testing-the-application"></a>응용 프로그램 테스트  
 이제 폼을 테스트 하 여 예상 대로 동작 하는지 확인할 수 있습니다.  
  
#### <a name="to-test-the-form"></a>폼을 테스트 하려면  
  
- 애플리케이션을 컴파일하고 실행합니다.  
  
     3 개의 고객 레코드로 채워진 <xref:System.Windows.Forms.DataGridView> 컨트롤이 표시 됩니다. 행에서 여러 셀의 값을 수정 하 고 편집 모드에서 ESC 키를 두 번 누르고 편집 모드 외부에서 한 번을 눌러 전체 행을 원래 값으로 되돌릴 수 있습니다. 컨트롤에서 행을 수정, 추가 또는 삭제 하는 경우 데이터 저장소의 `Customer` 개체도 수정, 추가 또는 삭제 됩니다.  
  
## <a name="next-steps"></a>다음 단계  
 이 응용 프로그램은 <xref:System.Windows.Forms.DataGridView> 컨트롤에서 가상 모드를 구현 하기 위해 처리 해야 하는 이벤트에 대 한 기본적인 이해를 제공 합니다. 여러 가지 방법으로이 기본 응용 프로그램을 향상 시킬 수 있습니다.  
  
- 외부 데이터베이스의 값을 캐시 하는 데이터 저장소를 구현 합니다. 캐시는 클라이언트 컴퓨터에서 적은 양의 메모리를 사용 하는 동안 표시에 필요한 항목만 포함 하도록 필요에 따라 값을 검색 하 고 삭제 해야 합니다.  
  
- 요구 사항에 따라 데이터 저장소의 성능을 미세 조정 합니다. 예를 들어 더 큰 캐시 크기를 사용 하 고 데이터베이스 쿼리 수를 최소화 하 여 클라이언트 컴퓨터 메모리 제한 보다 저속 네트워크 연결을 보정 하려고 할 수 있습니다.  
  
 외부 데이터베이스에서 값을 캐싱하는 방법에 대 한 자세한 내용은 [방법: Windows Forms DataGridView 컨트롤에서 Just-in-time 데이터 로드를 사용 하 여 가상 모드 구현](virtual-mode-with-just-in-time-data-loading-in-the-datagrid.md)을 참조 하세요.  
  
## <a name="see-also"></a>참조

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridView.VirtualMode%2A>
- <xref:System.Windows.Forms.DataGridView.CellValueNeeded>
- <xref:System.Windows.Forms.DataGridView.CellValuePushed>
- <xref:System.Windows.Forms.DataGridView.NewRowNeeded>
- <xref:System.Windows.Forms.DataGridView.RowValidated>
- <xref:System.Windows.Forms.DataGridView.RowDirtyStateNeeded>
- <xref:System.Windows.Forms.DataGridView.CancelRowEdit>
- <xref:System.Windows.Forms.DataGridView.UserDeletingRow>
- [Windows Forms DataGridView 컨트롤의 성능 조정](performance-tuning-in-the-windows-forms-datagridview-control.md)
- [Windows Forms DataGridView 컨트롤의 크기를 조정하는 최선의 방법](best-practices-for-scaling-the-windows-forms-datagridview-control.md)
- [Windows Forms DataGridView 컨트롤에서 Just-In-Time 데이터 로드를 사용하여 가상 모드 구현](implementing-virtual-mode-jit-data-loading-in-the-datagrid.md)
- [방법: Windows Forms DataGridView 컨트롤에서 가상 모드 구현](how-to-implement-virtual-mode-in-the-windows-forms-datagridview-control.md)
