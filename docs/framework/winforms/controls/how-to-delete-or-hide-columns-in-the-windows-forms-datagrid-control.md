---
title: '방법: Windows Forms DataGrid 컨트롤에서 열 삭제 또는 숨기기'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- data grids [Windows Forms], deleting columns
- DataGrid control [Windows Forms], deleting columns
- data grids [Windows Forms], hiding columns
- columns [Windows Forms], hiding
- columns [Windows Forms], deleting in data grids
- DataGrid control [Windows Forms], hiding columns
ms.assetid: bcd0dd96-6687-4c48-b0e1-d5287b93ac91
ms.openlocfilehash: d3f1f013cbb5e41c997014f556602b01bab62914
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/09/2019
ms.locfileid: "59297514"
---
# <a name="how-to-delete-or-hide-columns-in-the-windows-forms-datagrid-control"></a>방법: Windows Forms DataGrid 컨트롤에서 열 삭제 또는 숨기기
> [!NOTE]
>  <xref:System.Windows.Forms.DataGridView> 컨트롤은 <xref:System.Windows.Forms.DataGrid> 컨트롤을 대체하고 여기에 다른 기능을 추가하여 새로 도입된 컨트롤이지만 이전 버전과의 호환성 및 이후 사용 가능성을 고려하여 <xref:System.Windows.Forms.DataGrid> 컨트롤을 계속 유지하도록 선택할 수 있습니다. 자세한 내용은 [Windows Forms DataGridView 및 DataGrid 컨트롤의 차이점](differences-between-the-windows-forms-datagridview-and-datagrid-controls.md)을 참조하십시오.  
  
 프로그래밍 방식으로 삭제 하거나 Windows Forms에서 열을 숨길 수 있습니다 <xref:System.Windows.Forms.DataGrid> 컨트롤의 메서드와 속성을 사용 하 여 합니다 <xref:System.Windows.Forms.GridColumnStylesCollection> 하 고 <xref:System.Windows.Forms.DataGridColumnStyle> 개체 (멤버의 <xref:System.Windows.Forms.DataGridTableStyle> 클래스).  
  
 삭제 되거나 숨겨진 열 모눈에 바인딩되어 있고 프로그래밍 방식으로 액세스할 수 있습니다 데이터 원본에 여전히 존재 합니다. 더 이상만 datagrid에 표시 됩니다.  
  
> [!NOTE]
>  응용 프로그램 데이터의 특정 열에 액세스 하지 않습니다 하 고 원하지 않는 datagrid에 표시 하는 경우 다음 아마도 필요는 없습니다 처음에 데이터 원본에 포함 합니다.  
  
### <a name="to-delete-a-column-from-the-datagrid-programmatically"></a>프로그래밍 방식으로 DataGrid에서 열을 삭제 하려면  
  
1. 폼의 선언 영역에서의 새 인스턴스를 선언 합니다 <xref:System.Windows.Forms.DataGridTableStyle> 클래스입니다.  
  
2. 설정 된 <xref:System.Windows.Forms.DataGridTableStyle.MappingName%2A?displayProperty=nameWithType> 테이블 스타일을 적용 하려는 데이터 원본에 대 한 속성입니다. 다음 예제에서는 <xref:System.Windows.Forms.DataGrid.DataMember%2A?displayProperty=nameWithType> 이미 설정 되었다고 가정 하는 속성입니다.  
  
3. 새 추가 <xref:System.Windows.Forms.DataGridTableStyle> datagrid의 테이블 스타일 컬렉션 개체입니다.  
  
4. 호출 된 <xref:System.Windows.Forms.GridColumnStylesCollection.RemoveAt%2A> 메서드를 <xref:System.Windows.Forms.DataGrid>의 <xref:System.Windows.Forms.DataGridTableStyle.GridColumnStyles%2A> 컬렉션을 삭제 하는 열의 열 인덱스를 지정 하 합니다.  
  
    ```vb  
    ' Declare a new DataGridTableStyle in the  
    ' declarations area of your form.  
    Dim ts As DataGridTableStyle = New DataGridTableStyle()  
  
    Sub DeleteColumn()  
       ' Set the DataGridTableStyle.MappingName property  
       ' to the table in the data source to map to.  
       ts.MappingName = DataGrid1.DataMember  
  
       ' Add it to the datagrid's TableStyles collection  
       DataGrid1.TableStyles.Add(ts)  
  
       ' Delete the first column (index 0)  
       DataGrid1.TableStyles(0).GridColumnStyles.RemoveAt(0)  
    End Sub  
    ```  
  
    ```csharp  
    // Declare a new DataGridTableStyle in the  
    // declarations area of your form.  
    DataGridTableStyle ts = new DataGridTableStyle();  
  
    private void deleteColumn()  
    {  
       // Set the DataGridTableStyle.MappingName property  
       // to the table in the data source to map to.  
       ts.MappingName = dataGrid1.DataMember;  
  
       // Add it to the datagrid's TableStyles collection  
       dataGrid1.TableStyles.Add(ts);  
  
       // Delete the first column (index 0)  
       dataGrid1.TableStyles[0].GridColumnStyles.RemoveAt(0);  
    }  
    ```  
  
### <a name="to-hide-a-column-in-the-datagrid-programmatically"></a>프로그래밍 방식으로 DataGrid의 열을 숨기려면  
  
1. 폼의 선언 영역에서의 새 인스턴스를 선언 합니다 <xref:System.Windows.Forms.DataGridTableStyle> 클래스입니다.  
  
2. 설정 합니다 <xref:System.Windows.Forms.DataGridTableStyle.MappingName%2A> 의 속성을 <xref:System.Windows.Forms.DataGridTableStyle> 테이블 스타일을 적용 하려는 데이터 원본에 합니다. 다음 코드 예제에서는 <xref:System.Windows.Forms.DataGrid.DataMember%2A?displayProperty=nameWithType> 이미 설정 되었다고 가정 하는 속성입니다.  
  
3. 새 추가 <xref:System.Windows.Forms.DataGridTableStyle> datagrid의 테이블 스타일 컬렉션 개체입니다.  
  
4. 설정 하 여 열을 숨기려면 해당 `Width` 속성을 0, 열을 숨기려면 열 인덱스를 지정 합니다.  
  
    ```vb  
    ' Declare a new DataGridTableStyle in the  
    ' declarations area of your form.  
    Dim ts As DataGridTableStyle = New DataGridTableStyle()  
  
    Sub HideColumn()  
       ' Set the DataGridTableStyle.MappingName property  
       ' to the table in the data source to map to.  
       ts.MappingName = DataGrid1.DataMember  
  
       ' Add it to the datagrid's TableStyles collection  
       DataGrid1.TableStyles.Add(ts)  
  
       ' Hide the first column (index 0)  
       DataGrid1.TableStyles(0).GridColumnStyles(0).Width = 0  
    End Sub  
    ```  
  
    ```csharp  
    // Declare a new DataGridTableStyle in the  
    // declarations area of your form.  
    DataGridTableStyle ts = new DataGridTableStyle();  
  
    private void hideColumn()  
    {  
       // Set the DataGridTableStyle.MappingName property  
       // to the table in the data source to map to.  
       ts.MappingName = dataGrid1.DataMember;  
  
       // Add it to the datagrid's TableStyles collection  
       dataGrid1.TableStyles.Add(ts);  
  
       // Hide the first column (index 0)  
       dataGrid1.TableStyles[0].GridColumnStyles[0].Width = 0;  
    }  
    ```  
  
## <a name="see-also"></a>참고자료

- [방법: 런타임에 Windows Forms DataGrid 컨트롤에 표시되는 데이터 변경](change-displayed-data-at-run-time-wf-datagrid-control.md)
- [방법: Windows Forms DataGrid 컨트롤에 테이블 및 열 추가](how-to-add-tables-and-columns-to-the-windows-forms-datagrid-control.md)
