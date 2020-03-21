---
title: 데이터를 데이터그리드뷰 제어에 바인딩
ms.date: 02/08/2019
dev_langs:
- csharp
- vb
helpviewer_keywords:
- data binding [Windows Forms], grids
- data binding [Windows Forms], DataGridView control
- DataGridView control [Windows Forms], data binding
ms.assetid: 1660f69c-5711-45d2-abc1-e25bc6779124
ms.openlocfilehash: 643dcd37cd1bb3f8b5938fedff66c67cd68278ff
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79182271"
---
# <a name="how-to-bind-data-to-the-windows-forms-datagridview-control"></a>방법: Windows 양식 DataGridView 컨트롤에 데이터를 바인딩합니다.

컨트롤은 <xref:System.Windows.Forms.DataGridView> 표준 Windows Forms 데이터 바인딩 모델을 지원하므로 다양한 데이터 원본에 바인딩할 수 있습니다. 일반적으로 데이터 원본과의 <xref:System.Windows.Forms.BindingSource> 상호 작용을 관리하는 에 바인딩합니다. 모든 <xref:System.Windows.Forms.BindingSource> Windows Forms 데이터 원본이 될 수 있으므로 데이터의 위치를 선택하거나 수정할 때 유연성이 뛰어나습니다. 컨트롤이 지원하는 데이터 <xref:System.Windows.Forms.DataGridView> 원본에 대한 자세한 내용은 [DataGridView 컨트롤 개요를](datagridview-control-overview-windows-forms.md)참조하십시오.  

Visual Studio는 DataGridView 컨트롤에 대한 데이터 바인딩을 광범위하게 지원합니다. 자세한 내용은 디자이너를 [사용하여 Windows Forms DataGridView 컨트롤에 데이터를 바인딩하는 방법을](bind-data-to-the-datagrid-using-the-designer.md)참조하십시오.  

DataGridView 컨트롤을 데이터에 연결하려면 다음을 수행하십시오.

1. 데이터 검색 세부 정보를 처리하는 메서드를 구현합니다. 다음 코드 예제에서는 `GetData` <xref:System.Data.SqlClient.SqlDataAdapter>을 초기화하고 이를 사용하여 을 채우는 <xref:System.Data.DataTable>메서드를 구현합니다. 그런 다음 <xref:System.Data.DataTable> <xref:System.Windows.Forms.BindingSource>에 바인딩합니다.

2. 폼의 <xref:System.Windows.Forms.Form.Load> 이벤트 처리기에서 <xref:System.Windows.Forms.DataGridView> <xref:System.Windows.Forms.BindingSource>컨트롤을 에 바인딩하고 `GetData` 메서드를 호출하여 데이터를 검색합니다.  

## <a name="example"></a>예제

이 전체 코드 예제에서는 데이터베이스에서 데이터를 검색하여 DataGridView 컨트롤을 Windows 형식으로 채웁니다. 양식에는 데이터를 다시 로드하고 데이터베이스에 변경 내용을 제출하는 단추도 있습니다.  

이 예제에는 다음 사항이 필요합니다.

- 노스윈드 SQL Server 샘플 데이터베이스에 대한 액세스. Northwind 샘플 데이터베이스 설치에 대한 자세한 내용은 [ADO.NET 코드 샘플에 대한 샘플 데이터베이스 받기를](../../data/adonet/sql/linq/downloading-sample-databases.md)참조하십시오.

- 시스템, System.Windows.Forms, System.Data 및 System.Xml 어셈블리에 대한 참조입니다.  

이 예제를 빌드하고 실행하려면 새 Windows Forms 프로젝트의 *Form1* 코드 파일에 코드를 붙여넣습니다. C# 또는 Visual Basic 명령줄에서 빌드에 대한 자세한 내용은 [csc.exe를 가진 명령줄 빌드](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md) 또는 [명령줄에서 빌드를](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md)참조하십시오.  
  
예제의 `connectionString` 변수를 Northwind SQL Server 샘플 데이터베이스 연결에 대한 값으로 채웁니다. 통합 보안이라고도 하는 Windows 인증은 연결 문자열에 암호를 저장하는 것보다 데이터베이스에 연결하는 보다 안전한 방법입니다. 연결 보안에 대한 자세한 내용은 [연결 정보 보호를](../../data/adonet/protecting-connection-information.md)참조하십시오.  

[!code-csharp[System.Windows.Forms.DataGridViewBoundEditable](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewBoundEditable/CS/datagridviewboundeditable.cs)]
[!code-vb[System.Windows.Forms.DataGridViewBoundEditable](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewBoundEditable/VB/datagridviewboundeditable.vb)]  
  
## <a name="see-also"></a>참고 항목

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridView.DataSource%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.BindingSource>
- [Windows 양식 데이터그리드뷰 컨트롤에 데이터 표시](displaying-data-in-the-windows-forms-datagridview-control.md)
- [연결 정보 보호](../../data/adonet/protecting-connection-information.md)
