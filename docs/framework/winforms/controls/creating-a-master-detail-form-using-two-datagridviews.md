---
title: '연습: 두 개의 Windows Forms DataGridView 컨트롤을 사용 하 여 마스터-세부 폼 만들기'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- DataGridView control [Windows Forms], master/detail form
- parent-child tables [Windows Forms], displaying on Windows Forms
- master-details lists [Windows Forms], displaying on Windows Forms
- walkthroughs [Windows Forms], DataGridView control
ms.assetid: c5fa29e8-47f7-4691-829b-0e697a691f36
ms.openlocfilehash: 774151efb136207a1c4f7a2f8f812bbbaefbf9e1
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/28/2019
ms.locfileid: "64648216"
---
# <a name="walkthrough-creating-a-masterdetail-form-using-two-windows-forms-datagridview-controls"></a>연습: 두 개의 Windows Forms DataGridView 컨트롤을 사용하여 마스터/세부 양식 만들기
사용에 대 한 가장 일반적인 시나리오 중 하나를 <xref:System.Windows.Forms.DataGridView> 컨트롤은 합니다 *마스터/세부 정보* 두 데이터베이스 테이블 간의 부모/자식 관계를 표시 되는 폼입니다. 마스터 테이블에서 행을 선택 하면 해당 자식 데이터를 사용 하 여 업데이트 세부 정보 테이블.  
  
 마스터/세부 폼을 구현 하는 것은 간의 상호 작용을 사용 하 여 쉽게 합니다 <xref:System.Windows.Forms.DataGridView> 컨트롤 및 <xref:System.Windows.Forms.BindingSource> 구성 요소입니다. 이 연습에서는 두 개를 사용 하 여 폼 빌드됩니다 <xref:System.Windows.Forms.DataGridView> 컨트롤과 두 <xref:System.Windows.Forms.BindingSource> 구성 요소입니다. Northwind SQL Server 예제 데이터베이스의 테이블과 관련 된 두 폼 표시 됩니다. `Customers` 및 `Orders`합니다. 마스터 데이터베이스에 모든 고객을 표시 하는 폼을 완료 하면 더 <xref:System.Windows.Forms.DataGridView> 하 고 선택한 고객 세부 정보에 대 한 모든 주문을 <xref:System.Windows.Forms.DataGridView>합니다.  
  
 이 항목의 코드를 단일 목록으로 복사하려면 [방법: 두 개의 Windows Forms DataGridView 컨트롤을 사용 하 여 마스터/세부 폼 만들기](create-a-master-detail-form-using-two-datagridviews.md)합니다.  
  
## <a name="prerequisites"></a>전제 조건  
 이 연습을 완료하려면 다음 사항이 필요합니다.  
  
- Northwind SQL Server 샘플 데이터베이스가 있는 서버에 액세스 합니다.  
  
## <a name="creating-the-form"></a>폼 만들기  
  
#### <a name="to-create-a-masterdetail-form"></a>마스터/세부 폼을 만들려면  
  
1. 파생 되는 클래스를 만듭니다 <xref:System.Windows.Forms.Form> 두 포함 <xref:System.Windows.Forms.DataGridView> 컨트롤과 두 <xref:System.Windows.Forms.BindingSource> 구성 요소입니다. 다음 코드는 기본 폼의 초기화를 제공 하 고 포함 된 `Main` 메서드. Visual Studio 디자이너를 사용 하 여 폼을 만드는 경우이 코드는 대신 디자이너 생성된 코드를 사용할 수 있지만 변수 선언에 여기에 표시 된 이름을 사용 해야 합니다.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMasterDetails#01](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMasterDetails/CS/masterdetails.cs#01)]
     [!code-vb[System.Windows.Forms.DataGridViewMasterDetails#01](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMasterDetails/VB/masterdetails.vb#01)]  
    [!code-csharp[System.Windows.Forms.DataGridViewMasterDetails#02](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMasterDetails/CS/masterdetails.cs#02)]
    [!code-vb[System.Windows.Forms.DataGridViewMasterDetails#02](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMasterDetails/VB/masterdetails.vb#02)]  
  
2. 데이터베이스에 연결 하는 세부 정보를 처리 하는 것에 대 한 폼의 클래스 정의에서 메서드를 구현 합니다. 이 예제에서는 `GetData` 채우는 메서드를 <xref:System.Data.DataSet> 개체, 추가 <xref:System.Data.DataRelation> 개체 데이터 집합에 바인딩합니다는 <xref:System.Windows.Forms.BindingSource> 구성 요소입니다. `connectionString` 변수를 사용자의 데이터베이스에 적합한 값으로 설정해야 합니다.  
  
    > [!IMPORTANT]
    >  암호와 같은 중요한 정보를 연결 문자열 내에 저장하면 애플리케이션 보안 문제가 발생할 수 있습니다. 데이터베이스 액세스를 제어할 경우에는 통합 보안이라고도 하는 Windows 인증을 사용하는 방법이 더 안전합니다. 자세한 내용은 [연결 정보 보호](../../data/adonet/protecting-connection-information.md)를 참조하세요.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMasterDetails#20](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMasterDetails/CS/masterdetails.cs#20)]
     [!code-vb[System.Windows.Forms.DataGridViewMasterDetails#20](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMasterDetails/VB/masterdetails.vb#20)]  
  
3. 폼의 처리기를 구현 <xref:System.Windows.Forms.Form.Load> 바인딩하는 이벤트를 <xref:System.Windows.Forms.DataGridView> 컨트롤을 합니다 <xref:System.Windows.Forms.BindingSource> 구성 요소 및 호출을 `GetData` 메서드. 다음 예제에서는 크기를 조정 하는 코드를 포함 <xref:System.Windows.Forms.DataGridView> 표시 된 데이터에 맞게 열입니다.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMasterDetails#10](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMasterDetails/CS/masterdetails.cs#10)]
     [!code-vb[System.Windows.Forms.DataGridViewMasterDetails#10](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMasterDetails/VB/masterdetails.vb#10)]  
  
## <a name="testing-the-application"></a>애플리케이션 테스트  
 이제 예상 대로 작동 되도록 폼을 테스트할 수 있습니다.  
  
#### <a name="to-test-the-form"></a>폼을 테스트 하려면  
  
- 애플리케이션을 컴파일하고 실행합니다.  
  
     두 가지를 살펴보면 <xref:System.Windows.Forms.DataGridView> 상하로 제어 합니다. 맨 위에 Northwind에서 고객 `Customers` 테이블 이며 맨 아래에 `Orders` 선택한 고객에 게 해당 합니다. 위에 있는 다른 행을 선택 하면 <xref:System.Windows.Forms.DataGridView>, 아래 내용의 <xref:System.Windows.Forms.DataGridView> 적절 하 게 변경 합니다.  
  
## <a name="next-steps"></a>다음 단계  
 이 응용 프로그램의 기본적인 이해를 제공 합니다 <xref:System.Windows.Forms.DataGridView> 컨트롤의 기능입니다. 동작과 모양을 사용자 지정할 수 있습니다는 <xref:System.Windows.Forms.DataGridView> 여러 가지 방법으로 제어 합니다.  
  
- 헤더 및 테두리 스타일을 변경 합니다. 자세한 내용은 [방법: 변경 된 테두리 및 모눈선 스타일에는 Windows Forms DataGridView 컨트롤](change-the-border-and-gridline-styles-in-the-datagrid.md)합니다.  
  
- 사용 하도록 설정 하거나 사용자 입력을 제한 합니다 <xref:System.Windows.Forms.DataGridView> 제어 합니다. 자세한 내용은 [방법: 행 추가 방지 하 고 삭제는 Windows Forms DataGridView 컨트롤](prevent-row-addition-and-deletion-datagridview.md), 및 [방법: 에서 열을 설정 읽기 전용으로 Windows Forms DataGridView 컨트롤](how-to-make-columns-read-only-in-the-windows-forms-datagridview-control.md)합니다.  
  
- 사용자 입력의 유효성을 검사 합니다 <xref:System.Windows.Forms.DataGridView> 제어 합니다. 자세한 내용은 [연습: Forms DataGridView 컨트롤을 Windows의 데이터 유효성 검사](walkthrough-validating-data-in-the-windows-forms-datagridview-control.md)합니다.  
  
- 가상 모드를 사용 하 여 매우 큰 데이터 집합을 처리 합니다. 자세한 내용은 [연습: Forms DataGridView 컨트롤의 Windows에서 가상 모드 구현](implementing-virtual-mode-wf-datagridview-control.md)합니다.  
  
- 셀의 모양을 사용자 지정 합니다. 자세한 내용은 [방법: Windows Forms DataGridView 컨트롤에서 셀 모양 사용자 지정](customize-the-appearance-of-cells-in-the-datagrid.md) 고 [방법: Windows Forms DataGridView 컨트롤에 기본 셀 스타일 설정](how-to-set-default-cell-styles-for-the-windows-forms-datagridview-control.md)합니다.  
  
## <a name="see-also"></a>참고자료

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.BindingSource>
- [Windows Forms DataGridView 컨트롤에서 데이터 표시](displaying-data-in-the-windows-forms-datagridview-control.md)
- [방법: 두 개의 Windows Forms DataGridView 컨트롤을 사용 하 여 마스터/세부 폼 만들기](create-a-master-detail-form-using-two-datagridviews.md)
- [연결 정보 보호](../../data/adonet/protecting-connection-information.md)
