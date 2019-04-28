---
title: 데이터 보기 수정
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 697a3991-b660-4a5a-8a54-1a2304ff158e
ms.openlocfilehash: 6e340b9b72735598650d2eefa6e19ab40fffc2e4
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61607416"
---
# <a name="modifying-dataviews"></a>데이터 보기 수정
<xref:System.Data.DataView>를 사용하여 원본 테이블의 데이터 행을 추가, 삭제 또는 수정할 수 있습니다. 사용 하는 기능을 **DataView** 의 세 가지 부울 속성 중 하나를 설정 하 여 제어 기본 테이블의 데이터를 수정 하는 **DataView**합니다. 이러한 속성에는 <xref:System.Data.DataView.AllowNew%2A>, <xref:System.Data.DataView.AllowEdit%2A> 및 <xref:System.Data.DataView.AllowDelete%2A>가 있습니다. 으로 설정 됩니다 **true** 기본적으로 합니다.  
  
 경우 **AllowNew** 은 **true**를 사용할 수는 <xref:System.Data.DataView.AddNew%2A> 메서드의 **DataView** 새 <xref:System.Data.DataRowView>합니다. 기본 추가 실제로 새 행을 하지 않은 <xref:System.Data.DataTable> 될 때까지 합니다 <xref:System.Data.DataRowView.EndEdit%2A> 메서드는 **DataRowView** 라고 합니다. 경우는 <xref:System.Data.DataRowView.CancelEdit%2A> 메서드를 **DataRowView** 은 호출, 새 행이 삭제 됩니다. 하나만 편집할 수는 또한 **DataRowView** 번입니다. 호출 하는 경우는 **AddNew** 또는 **BeginEdit** 메서드를 **DataRowView** 보류 된 행이 있지만 **EndEdit** 에서 암시적으로 호출 되는 보류 중인 행입니다. 때 **EndEdit** 가 호출 변경 내용이 적용 된 기본 **DataTable** 수 나중에 커밋하거나 거부할 사용 하 여를 **AcceptChanges** 또는  **RejectChanges** 의 메서드를 **DataTable**, **DataSet**, 또는 **DataRow** 개체. 경우 **AllowNew** 는 **false**를 호출 하는 경우 예외가 throw 됩니다는 **AddNew** 메서드를 **DataRowView**합니다.  
  
 경우 **AllowEdit** 됩니다 **true**의 내용을 수정할 수 있습니다를 **DataRow** 를 통해를 **DataRowView**합니다. 변경 내용을 사용 하 여 원본 행을 확인할 수 있습니다 **DataRowView.EndEdit** 하거나 사용 하 여 변경 내용을 거부할 **DataRowView.CancelEdit**합니다. 행은 한 번에 하나씩만 편집할 수 있습니다. 호출 하는 경우는 **AddNew** 또는 **BeginEdit** 의 메서드를 **DataRowView** 보류 된 행 있기는 **EndEdit** 에서 암시적으로 호출 됩니다 보류 중인 행입니다. 때 **EndEdit** 가 호출 제안 된 변경 내용에 배치 됩니다는 **현재** 은 기본 행 버전 **DataRow** 수 나중에 커밋하거나 거부할 를사용하여 **AcceptChanges** 또는 **RejectChanges** 의 메서드를 **DataTable**를 **DataSet**, 또는 **DataRow** 개체입니다. 하는 경우 **AllowEdit** 됩니다 **false**의 값을 수정 하려고 하면 예외가 throw 됩니다는 **DataView**합니다.  
  
 기존 **DataRowView** 편집 중인 기본 이벤트 **DataTable** 제안 된 변경 내용으로 계속 발생 합니다. 호출 하는 경우 사용자에 게 유의 **EndEdit** 또는 **CancelEdit** 내부 **DataRow**보류 중, 변경 또는 적용 여부에 관계 없이 취소 됩니다  **EndEdit** 나 **CancelEdit** 라고 하는 **DataRowView**합니다.  
  
 경우 **AllowDelete** 됩니다 **true**에서 행을 삭제할 수 있습니다는 **DataView** 사용 하 여를 **삭제** 메서드의 **DataView**  나 **DataRowView** 개체에 행 내부에서 삭제 됩니다 **DataTable**합니다. 나중에 커밋 또는 사용 하 여 삭제를 거부할 수 있습니다 **AcceptChanges** 하거나 **RejectChanges** 각각. 경우 **AllowDelete** 은 **false**를 호출 하는 경우 예외가 throw 됩니다는 **삭제** 메서드를 **DataView** 또는  **DataRowView**합니다.  
  
 사용 하는 다음 코드 예제에서는 사용 하지 않도록 설정 합니다 **DataView** 를 삭제 하며 사용 하 여 기본 테이블에 새 행을 추가 합니다 **DataView**.  
  
```vb  
Dim custTable As DataTable = custDS.Tables("Customers")  
Dim custView As DataView = custTable.DefaultView  
custView.Sort = "CompanyName"  
  
custView.AllowDelete = False  
  
Dim newDRV As DataRowView = custView.AddNew()  
newDRV("CustomerID") = "ABCDE"  
newDRV("CompanyName") = "ABC Products"  
newDRV.EndEdit()  
```  
  
```csharp  
DataTable custTable = custDS.Tables["Customers"];  
DataView custView = custTable.DefaultView;  
custView.Sort = "CompanyName";  
  
custView.AllowDelete = false;  
  
DataRowView newDRV = custView.AddNew();  
newDRV["CustomerID"] = "ABCDE";  
newDRV["CompanyName"] = "ABC Products";  
newDRV.EndEdit();  
```  
  
## <a name="see-also"></a>참고자료

- <xref:System.Data.DataTable>
- <xref:System.Data.DataView>
- <xref:System.Data.DataRowView>
- [DataView](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/dataviews.md)
- [ADO.NET 관리되는 공급자 및 데이터 집합 개발자 센터](https://go.microsoft.com/fwlink/?LinkId=217917)
