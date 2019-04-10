---
title: '방법: Windows Forms DataGrid 컨트롤 서식 지정'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- columns [Windows Forms], DataGrid control
- colors [Windows Forms], applying to DataGrid controls
- DataGrid control [Windows Forms], formatting
- columns [Windows Forms], formatting in DataGrid control
- DataGrid control [Windows Forms], default styles
- tables [Windows Forms], formatting in DataGrid control
- formatting [Windows Forms]
ms.assetid: a50fcc3b-8abf-47ec-9029-7f268af4ddb1
ms.openlocfilehash: a07fde63463d209e0006de9be677636f19fd93a8
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59147903"
---
# <a name="how-to-format-the-windows-forms-datagrid-control"></a>방법: Windows Forms DataGrid 컨트롤 서식 지정
> [!NOTE]
>  <xref:System.Windows.Forms.DataGridView> 컨트롤은 <xref:System.Windows.Forms.DataGrid> 컨트롤을 대체하고 여기에 다른 기능을 추가하여 새로 도입된 컨트롤이지만 이전 버전과의 호환성 및 이후 사용 가능성을 고려하여 <xref:System.Windows.Forms.DataGrid> 컨트롤을 계속 유지하도록 선택할 수 있습니다. 자세한 내용은 [Windows Forms DataGridView 및 DataGrid 컨트롤의 차이점](differences-between-the-windows-forms-datagridview-and-datagrid-controls.md)을 참조하십시오.  
  
 다양 한 부분에 서로 다른 색을 적용 한 <xref:System.Windows.Forms.DataGrid> 컨트롤에서 정보를 더 쉽게 읽고 해석 하기 시킬 수 있습니다. 색 행 및 열에 적용할 수 있습니다. 행 및 열 수 또한 숨겨지거나 표시 되려고 판단에 따라 합니다.  
  
 서식 지정의 세 가지 기본 요소를 가지는 <xref:System.Windows.Forms.DataGrid> 제어 합니다. 데이터 표시 되는 기본 스타일을 설정 하는 속성을 설정할 수 있습니다. 그런 다음이 기초로 런타임에 표시 되는 특정 테이블 방식을 사용자 지정할 수 있습니다. 마지막으로, 색 뿐만 아니라 데이터 표에 표시 된 열을 수정할 수 있습니다 하 고 기타 서식 표시 됩니다.  
  
 데이터 표 서식 지정에 사용 되는 첫 단계로,의 속성을 설정할 수는 <xref:System.Windows.Forms.DataGrid> 자체입니다. 이러한 색 및 형식을 선택할 수는 변경할 수 있습니다 다음 데이터 테이블 및 열 표시에 따라 기본을 형성 합니다.  
  
### <a name="to-establish-a-default-style-for-the-datagrid-control"></a>DataGrid 컨트롤에 대 한 기본 스타일을 설정 하려면  
  
1.  다음 속성을 적절 하 게 설정 합니다.  
  
    |속성|설명|  
    |--------------|-----------------|  
    |<xref:System.Windows.Forms.DataGrid.AlternatingBackColor%2A>|<xref:System.Windows.Forms.DataGrid.BackColor%2A> 속성 그리드의 짝수 번호 행의 색을 정의 합니다. 설정 하는 경우는 <xref:System.Windows.Forms.DataGrid.AlternatingBackColor%2A> 다른 색으로 속성을 다른 모든 행이 새로운 색으로 설정할지 (행에 1, 3, 5, 및 등).|  
    |<xref:System.Windows.Forms.DataGrid.BackColor%2A>|그리드의 짝수 번호 행의 배경색 (행에 0, 2, 4, 6 및 등).|  
    |<xref:System.Windows.Forms.DataGrid.BackgroundColor%2A>|반면를 <xref:System.Windows.Forms.DataGrid.BackColor%2A> 하 고 <xref:System.Windows.Forms.DataGrid.AlternatingBackColor%2A> 표의 행 색을 결정 하는 속성을 <xref:System.Windows.Forms.DataGrid.BackgroundColor%2A> 모눈을 아래쪽으로 스크롤할 경우 또는 몇 개의 행에 포함 된 경우 표시만 되는 맨 영역의 색을 결정 하는 속성 표입니다.|  
    |<xref:System.Windows.Forms.DataGrid.BorderStyle%2A>|눈금의 테두리 스타일 중 하나는 <xref:System.Windows.Forms.BorderStyle> 열거형 값입니다.|  
    |<xref:System.Windows.Forms.DataGrid.CaptionBackColor%2A>|표 형태 위에 즉시 표시 되는 데이터 표 창 캡션의 배경색입니다.|  
    |<xref:System.Windows.Forms.DataGrid.CaptionFont%2A>|그리드의 맨 위에 있는 캡션의 글꼴입니다.|  
    |<xref:System.Windows.Forms.DataGrid.CaptionForeColor%2A>|표 창 캡션의 배경색입니다.|  
    |<xref:System.Windows.Forms.Control.Font%2A>|표의 텍스트를 표시 하는 데 사용 되는 글꼴입니다.|  
    |<xref:System.Windows.Forms.DataGrid.ForeColor%2A>|데이터 그리드의 행에 있는 데이터가 표시 되는 글꼴의 색입니다.|  
    |<xref:System.Windows.Forms.DataGrid.GridLineColor%2A>|데이터 그리드의 모눈선의 색입니다.|  
    |<xref:System.Windows.Forms.DataGrid.GridLineStyle%2A>|중 하나는 그리드의 셀을 구분 하는 선의 스타일을 <xref:System.Windows.Forms.DataGridLineStyle> 열거형 값입니다.|  
    |<xref:System.Windows.Forms.DataGrid.HeaderBackColor%2A>|행 및 열 머리글의 배경색입니다.|  
    |<xref:System.Windows.Forms.DataGrid.HeaderFont%2A>|열 머리글에 사용 되는 글꼴입니다.|  
    |<xref:System.Windows.Forms.DataGrid.HeaderForeColor%2A>|열 머리글 텍스트 및 + /-문자 모양을 (여러 개의 관련된 테이블 표시 될 때 행을 확장)를 포함 하는 표의 열 머리글의 전경색입니다.|  
    |<xref:System.Windows.Forms.DataGrid.LinkColor%2A>|자식 테이블, 관계 이름 및 등에 대 한 링크를 포함 하 여 데이터 표의 모든 링크의 텍스트 색입니다.|  
    |<xref:System.Windows.Forms.DataGrid.ParentRowsBackColor%2A>|자식 테이블의 부모 행의 배경색 이것이입니다.|  
    |<xref:System.Windows.Forms.DataGrid.ParentRowsForeColor%2A>|자식 테이블의 부모 행의 전경색 이것이입니다.|  
    |<xref:System.Windows.Forms.DataGrid.ParentRowsLabelStyle%2A>|테이블 및 열 이름을 이용 하 여 부모 행에 표시 되는지 여부를 결정 합니다 <xref:System.Windows.Forms.DataGridParentRowsLabelStyle> 열거형입니다.|  
    |<xref:System.Windows.Forms.DataGrid.PreferredColumnWidth%2A>|데이터 표에서 열의 기본 너비(픽셀)입니다. 다시 설정 하기 전에이 속성을 설정 합니다 <xref:System.Windows.Forms.DataGrid.DataSource%2A> 및 <xref:System.Windows.Forms.DataGrid.DataMember%2A> 속성 (중 하나 개별적으로 또는 <xref:System.Windows.Forms.DataGrid.SetDataBinding%2A> 메서드), 또는 속성이 영향을 주지 것입니다.<br /><br /> 속성이 0 보다 작은 값으로 설정할 수 없습니다.|  
    |<xref:System.Windows.Forms.DataGrid.PreferredRowHeight%2A>|눈금의 행 (픽셀) 행 높이입니다. 다시 설정 하기 전에이 속성을 설정 합니다 <xref:System.Windows.Forms.DataGrid.DataSource%2A> 및 <xref:System.Windows.Forms.DataGrid.DataMember%2A> 속성 (중 하나 개별적으로 또는 <xref:System.Windows.Forms.DataGrid.SetDataBinding%2A> 메서드), 또는 속성이 영향을 주지 것입니다.<br /><br /> 속성이 0 보다 작은 값으로 설정할 수 없습니다.|  
    |<xref:System.Windows.Forms.DataGrid.RowHeaderWidth%2A>|그리드의 행 머리글의 너비입니다.|  
    |<xref:System.Windows.Forms.DataGrid.SelectionBackColor%2A>|행 또는 셀을 선택 하면 이것이 배경색입니다.|  
    |<xref:System.Windows.Forms.DataGrid.SelectionForeColor%2A>|행 또는 셀을 선택 하면 이것이 전경색입니다.|  
  
    > [!NOTE]
    >  컨트롤에 잘못 된 색 선택 (예를 들어, 빨강 및 녹색)으로 인해 액세스할 수 없도록 하는 컨트롤의 색을 사용자 지정 하는 경우를 염두에 둡니다. 에 있는 색을 사용 합니다 **시스템 색** 이 문제를 방지 하려면 색상표입니다.  
  
     다음 절차에서는 폼에 가정는 <xref:System.Windows.Forms.DataGrid> 컨트롤이 데이터 테이블에 바인딩되어 있습니다. 자세한 내용은 [데이터 원본에 Windows Forms DataGrid 컨트롤 바인딩](how-to-bind-the-windows-forms-datagrid-control-to-a-data-source.md)합니다.  
  
### <a name="to-set-the-table-and-column-style-of-a-data-table-programmatically"></a>데이터 테이블의 테이블 및 열 스타일을 프로그래밍 방식으로 설정 하려면  
  
1.  새 테이블 스타일을 만들고 해당 속성을 설정 합니다.  
  
2.  열 스타일을 만들고 해당 속성을 설정 합니다.  
  
3.  테이블 스타일의 열 스타일 컬렉션에 열 스타일을 추가 합니다.  
  
4.  데이터 그리드 테이블 스타일 컬렉션에 테이블 스타일을 추가 합니다.  
  
5.  아래 예제에서의 새 인스턴스를 만듭니다 <xref:System.Windows.Forms.DataGridTableStyle> 설정 및 해당 <xref:System.Windows.Forms.DataGridTableStyle.MappingName%2A> 속성입니다.  
  
6.  새 인스턴스를 만듭니다는 **GridColumnStyle** 설정 하 고 해당 **MappingName** (및 일부 다른 레이아웃 및 표시 속성).  
  
7.  만들려는 각 열 스타일에 대해 2 ~ 6 단계를 반복 합니다.  
  
     다음 예제에서는 어떻게를 <xref:System.Windows.Forms.DataGridTextBoxColumn> 열에 표시 되는 이름 이므로 만들어집니다. 열 스타일을 추가 하는 또한 합니다 <xref:System.Windows.Forms.GridColumnStylesCollection> 테이블 스타일의 테이블 스타일을 추가 하 고는 <xref:System.Windows.Forms.GridTableStylesCollection> 데이터 그리드입니다.  
  
    ```vb  
    Private Sub CreateAuthorFirstNameColumn()  
       ' Add a GridTableStyle and set the MappingName   
       ' to the name of the DataTable.  
       Dim TSAuthors As New DataGridTableStyle()  
       TSAuthors.MappingName = "Authors"  
  
       ' Add a GridColumnStyle and set the MappingName   
       ' to the name of a DataColumn in the DataTable.   
       ' Set the HeaderText and Width properties.   
       Dim TCFirstName As New DataGridTextBoxColumn()  
       TCFirstName.MappingName = "AV_FName"  
       TCFirstName.HeaderText = "First Name"  
       TCFirstName.Width = 75  
       TSAuthors.GridColumnStyles.Add(TCFirstName)  
  
       ' Add the DataGridTableStyle instance to   
       ' the GridTableStylesCollection.   
       myDataGrid.TableStyles.Add(TSAuthors)  
    End Sub  
    ```  
  
    ```csharp  
    private void addCustomDataTableStyle()  
    {  
       // Add a GridTableStyle and set the MappingName   
       // to the name of the DataTable.  
       DataGridTableStyle TSAuthors = new DataGridTableStyle();  
       TSAuthors.MappingName = "Authors";  
  
       // Add a GridColumnStyle and set the MappingName   
       // to the name of a DataColumn in the DataTable.   
       // Set the HeaderText and Width properties.   
       DataGridColumnStyle TCFirstName = new DataGridTextBoxColumn();  
       TCFirstName.MappingName = " AV_FName";  
       TCFirstName.HeaderText = "First Name";  
       TCFirstName.Width = 75;  
       TSAuthors.GridColumnStyles.Add(TCFirstName);  
  
       // Add the DataGridTableStyle instance to   
       // the GridTableStylesCollection.   
       dataGrid1.TableStyles.Add(TSAuthors);  
    }  
    ```  
  
    ```cpp  
    private:  
       void addCustomDataTableStyle()  
       {  
          // Add a GridTableStyle and set the MappingName   
          // to the name of the DataTable.  
          DataGridTableStyle^ TSAuthors = new DataGridTableStyle();  
          TSAuthors->MappingName = "Authors";  
  
          // Add a GridColumnStyle and set the MappingName   
          // to the name of a DataColumn in the DataTable.   
          // Set the HeaderText and Width properties.   
          DataGridColumnStyle^ TCFirstName = gcnew DataGridTextBoxColumn();  
          TCFirstName->MappingName = "AV_FName";  
          TCFirstName->HeaderText = "First Name";  
          TCFirstName->Width = 75;  
          TSAuthors->GridColumnStyles->Add(TCFirstName);  
  
          // Add the DataGridTableStyle instance to   
          // the GridTableStylesCollection.   
          dataGrid1->TableStyles->Add(TSAuthors);  
       }  
    ```  
  
## <a name="see-also"></a>참고자료

- <xref:System.Windows.Forms.GridTableStylesCollection>
- <xref:System.Windows.Forms.GridColumnStylesCollection>
- <xref:System.Windows.Forms.DataGrid>
- [방법: Windows Forms DataGrid 컨트롤에서 열 삭제 또는 숨기기](how-to-delete-or-hide-columns-in-the-windows-forms-datagrid-control.md)
- [DataGrid 컨트롤](datagrid-control-windows-forms.md)
