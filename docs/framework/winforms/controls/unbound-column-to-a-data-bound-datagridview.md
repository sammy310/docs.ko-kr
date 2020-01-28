---
title: 데이터 바인딩된 DataGridView 컨트롤에 바인딩되지 않은 열 추가
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- columns [Windows Forms], unbound data
- data grids [Windows Forms], adding unbound columns
- DataGridView control [Windows Forms], unbound data
ms.assetid: f7bdc4d8-ba8e-421b-ad62-82d936f01372
ms.openlocfilehash: 807bbc121f33c35d70068571e76637c078ecb3da
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/24/2020
ms.locfileid: "76747071"
---
# <a name="how-to-add-an-unbound-column-to-a-data-bound-windows-forms-datagridview-control"></a>방법: 데이터 바인딩된 Windows Forms DataGridView 컨트롤에 바인딩되지 않은 열 추가
<xref:System.Windows.Forms.DataGridView> 컨트롤에서 표시하는 데이터는 대개 일종의 데이터 소스에서 가져오지만 데이터 소스에서 가져오지 않는 데이터 열을 표시할 수 있습니다. 이 열 유형을 바인딩되지 않은 열이라고 합니다. 바인딩되지 않은 열에서는 대부분 폼을 사용할 수 있습니다. 대부분 경우에 바인딩되지 않은 열은 데이터 행의 세부 정보에 액세스하는 데 사용됩니다.  
  
 다음 코드 예제에서는 마스터/세부 정보 시나리오를 구현할 때 부모 테이블의 특정 행과 관련 된 자식 테이블을 표시 하는 **세부 정보** 단추의 바인딩되지 않은 열을 만드는 방법을 보여 줍니다. 단추 클릭에 응답하려면 자식 테이블이 포함된 폼을 표시하는 <xref:System.Windows.Forms.DataGridView.CellClick?displayProperty=nameWithType> 이벤트 처리기를 구현합니다.  
  
 Visual Studio에서는 이 작업이 지원됩니다.  또한 [방법: 디자이너를 사용 하 여 Windows Forms DataGridView 컨트롤에서 열 추가 및 제거](add-and-remove-columns-in-the-datagrid-using-the-designer.md)를 참조 하세요.  
  
## <a name="example"></a>예  
 [!code-csharp[System.Windows.Forms.DataGridViewMisc#010](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#010)]
 [!code-vb[System.Windows.Forms.DataGridViewMisc#010](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#010)]  
  
## <a name="compiling-the-code"></a>코드 컴파일  
 이 예제에는 다음 사항이 필요합니다.  
  
- `dataGridView1`이라는 <xref:System.Windows.Forms.DataGridView> 컨트롤  
  
- <xref:System?displayProperty=nameWithType> 및 <xref:System.Windows.Forms?displayProperty=nameWithType> 어셈블리에 대한 참조  
  
## <a name="see-also"></a>참조

- <xref:System.Windows.Forms.DataGridView>
- [Windows Forms DataGridView 컨트롤에서 데이터 표시](displaying-data-in-the-windows-forms-datagridview-control.md)
- [Windows Forms DataGridView 컨트롤의 데이터 디스플레이 모드](data-display-modes-in-the-windows-forms-datagridview-control.md)
