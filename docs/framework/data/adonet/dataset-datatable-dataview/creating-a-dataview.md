---
title: DataView 만들기
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: b1cc02d1-23b1-4439-a998-0da1899f3442
ms.openlocfilehash: 05122f7c980c4b7dfdb27eec73464a4f0556ba99
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59096682"
---
# <a name="creating-a-dataview"></a>DataView 만들기
<xref:System.Data.DataView>를 만드는 방법은 두 가지입니다. 사용할 수는 **DataView** 생성자에 대 한 참조를 만들 수 있습니다는 <xref:System.Data.DataTable.DefaultView%2A> 의 속성은 <xref:System.Data.DataTable>합니다. 합니다 **DataView** 생성자 비워 둘 수 있습니다, 또는 중 하나를 수행 하는 **DataTable** 단일 인수로 또는 **DataTable** 필터 조건, 정렬 조건 및 행과 함께 상태 필터입니다. 에 사용할 수 있는 추가 인수에 대 한 자세한 합니다 **DataView**를 참조 하세요 [정렬 및 필터링 데이터](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/sorting-and-filtering-data.md)입니다.  
  
 때문에 대 한 인덱스를 **DataView** 때 작성 되는 **DataView** 만들어지면 있으면 및를 **정렬**, **RowFilter**, 또는  **RowStateFilter** 속성이 수정, 모든 초기 정렬 순서를 제공 하거나 만들 때 생성자 인수로 필터링 기준을 하 여 최적의 성능을 얻습니다 합니다 **DataView**합니다. 만들기는 **DataView** 정렬 또는 필터 조건을 지정 하 고 다음 설정 하지 않고 합니다 **정렬**를 **RowFilter**, 또는 **RowStateFilter** 속성에는 나중에 인덱스를 두 번 이상 빌드해야 하면: 면 때 합니다 **DataView** 만들어지면 및 다시 정렬 또는 필터 속성은입니다.  
  
 만든 경우는 **DataView** 인수를 사용 하지 않는 생성자를 사용 하 여, 됩니다 사용할 수는 **DataView** 설정 해야 합니다 **테이블** 속성 .  
  
 다음 코드 예제에는 만드는 방법을 보여 줍니다는 **DataView** 사용 하는 **DataView** 생성자입니다. A **RowFilter**, **정렬** 열 및 **DataViewRowState** 와 함께 제공 되는 **DataTable**.  
  
```vb  
Dim custDV As DataView = New DataView(custDS.Tables("Customers"), _  
    "Country = 'USA'", _  
    "ContactName", _  
    DataViewRowState.CurrentRows)  
```  
  
```csharp  
DataView custDV = new DataView(custDS.Tables["Customers"],   
    "Country = 'USA'",   
    "ContactName",   
    DataViewRowState.CurrentRows);  
```  
  
 다음 코드 예제에는 기본값에 대 한 참조를 가져오는 방법을 보여 줍니다 **DataView** 의 **DataTable** 사용 하는 **DefaultView** 테이블의 속성입니다.  
  
```vb  
Dim custDV As DataView = custDS.Tables("Customers").DefaultView  
```  
  
```csharp  
DataView custDV = custDS.Tables["Customers"].DefaultView;  
```  
  
## <a name="see-also"></a>참고자료

- <xref:System.Data.DataTable>
- <xref:System.Data.DataView>
- [데이터 보기](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/dataviews.md)
- [데이터 정렬 및 필터링](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/sorting-and-filtering-data.md)
- [DataTables](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/datatables.md)
- [ADO.NET 관리되는 공급자 및 데이터 집합 개발자 센터](https://go.microsoft.com/fwlink/?LinkId=217917)
