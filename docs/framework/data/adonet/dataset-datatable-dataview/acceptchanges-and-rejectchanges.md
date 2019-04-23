---
title: AcceptChanges 및 RejectChanges
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: e2d1a6fe-31f9-4b83-9728-06c406a3394e
ms.openlocfilehash: bbcc666b99c2bade479e5ee51750b043c820845d
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59172902"
---
# <a name="acceptchanges-and-rejectchanges"></a>AcceptChanges 및 RejectChanges
데이터에 대 한 변경 내용의 정확성을 확인 한 후는 <xref:System.Data.DataTable>를 사용 하 여 변경 내용을 적용할 수 있습니다 합니다 <xref:System.Data.DataRow.AcceptChanges%2A> 메서드의 <xref:System.Data.DataRow>, <xref:System.Data.DataTable>, 또는 <xref:System.Data.DataSet>로 설정 됩니다는 **현재** 행 값을 **원래** 값을 설정 합니다 합니다 **RowState** 속성을 **Unchanged**합니다. 수락 하거나 거부 하는 변경 내용을 모두 지웁니다 **RowError** 정보와 집합 합니다 **HasErrors** 속성을 **false**합니다. 또한, 변경 사항을 승인하거나 거부하면 데이터 소스에서 데이터를 업데이트하는 데도 영향을 줄 수 있습니다. 자세한 내용은 [Dataadapter 사용 하 여 데이터 원본 업데이트](../../../../../docs/framework/data/adonet/updating-data-sources-with-dataadapters.md)합니다.  
  
 외래 키 제약 조건이 있는 경우는 **DataTable**, 변경 내용을 승인 또는 거부를 사용 하 여 **AcceptChanges** 하 고 **RejectChanges** 합니다 의자식행으로전파됩니다 **DataRow** 에 따라 합니다 **ForeignKeyConstraint.AcceptRejectRule**합니다. 자세한 내용은 [DataTable 제약 조건](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/datatable-constraints.md)합니다.  
  
 다음 예제에서는 오류가 발생한 행을 검사하여 가능한 경우 오류를 해결하고 오류를 해결할 수 없는 경우에는 해당 행을 거부합니다. 해결 된 경우 오류를 참고 합니다 **RowError** 값이 빈 문자열을 다시 설정 발생 합니다 **HasErrors** 속성을 설정할 **false**. 오류가 발생 한 모든 행 해결 되거나 거부 된 경우 **AcceptChanges** 전체에 대 한 모든 변경 내용을 적용 하기 위해 호출 됩니다 **DataTable**합니다.  
  
```vb  
If workTable.HasErrors Then  
  Dim errRow As DataRow  
  
  For Each errRow in workTable.GetErrors()  
  
    If errRow.RowError = "Total cannot exceed 1000." Then  
      errRow("Total") = 1000  
      errRow.RowError = ""    ' Clear the error.  
    Else  
      errRow.RejectChanges()  
    End If  
  Next  
End If  
  
workTable.AcceptChanges()  
```  
  
```csharp  
if (workTable.HasErrors)  
{  
  
  foreach (DataRow errRow in workTable.GetErrors())  
  {  
    if (errRow.RowError == "Total cannot exceed 1000.")  
    {  
      errRow["Total"] = 1000;  
      errRow.RowError = "";    // Clear the error.  
    }  
    else  
      errRow.RejectChanges();  
  }  
}  
  
workTable.AcceptChanges();  
```  
  
## <a name="see-also"></a>참고자료

- <xref:System.Data.DataRow>
- <xref:System.Data.DataSet>
- <xref:System.Data.DataTable>
- [DataTable에서 데이터 조작](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/manipulating-data-in-a-datatable.md)
- [ADO.NET 관리되는 공급자 및 데이터 집합 개발자 센터](https://go.microsoft.com/fwlink/?LinkId=217917)
