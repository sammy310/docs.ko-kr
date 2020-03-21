---
title: DataView 만들기
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: b1cc02d1-23b1-4439-a998-0da1899f3442
ms.openlocfilehash: 9d21b17068ff3ce5b0bd3990144383d7f9ded2f9
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79151340"
---
# <a name="creating-a-dataview"></a>DataView 만들기
<xref:System.Data.DataView>를 만드는 방법은 두 가지입니다. **DataView** 생성기를 사용하거나 <xref:System.Data.DataTable.DefaultView%2A> <xref:System.Data.DataTable>의 속성에 대한 참조를 만들 수 있습니다. **DataView** 생성자는 비어 있거나 **DataTable을** 단일 인수로 사용할 수 있거나 필터 조건, 정렬 조건 및 행 상태 필터와 함께 **DataTable을** 사용할 수 있습니다. **DataView에서**사용할 수 있는 추가 인수에 대한 자세한 내용은 [데이터 정렬 및 필터링](sorting-and-filtering-data.md)을 참조하십시오.  
  
 **DataView에** 대 한 인덱스는 **DataView를** 만들 때 와 **정렬**, **RowFilter**또는 **RowStateFilter** 속성 중 하나만 수정 될 때 모두 빌드되므로 **DataView를**만들 때 초기 정렬 순서 또는 필터링 조건을 생성자 인수로 제공하여 최상의 성능을 얻을 수 있습니다. 정렬 또는 필터 조건을 지정하지 않고 **DataView를** 만든 다음 **Sort**, **RowFilter**또는 **RowStateFilter** 속성을 설정하지 않고 나중에 **DataView를** 만들 때 한 번, 정렬 또는 필터 속성이 수정될 때 인덱스를 두 번 이상 빌드합니다.  
  
 인수를 사용하지 않는 생성기를 사용하여 **DataView를** 만드는 경우 **Table** 속성을 설정하기 전까지는 **DataView를** 사용할 수 없습니다.  
  
 다음 코드 예제에서는 **DataView** 생성기를 사용하여 **DataView를** 만드는 방법을 보여 줍니다. **행 필터,** **정렬** 열 및 **DataViewRowState는** **DataTable**.  
  
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
  
 다음 코드 예제에서는 테이블의 **DefaultView** 속성을 사용하여 **DataTable의** 기본 **DataView에** 대한 참조를 가져오는 방법을 보여 줍니다.  
  
```vb  
Dim custDV As DataView = custDS.Tables("Customers").DefaultView  
```  
  
```csharp  
DataView custDV = custDS.Tables["Customers"].DefaultView;  
```  
  
## <a name="see-also"></a>참고 항목

- <xref:System.Data.DataTable>
- <xref:System.Data.DataView>
- [DataView](dataviews.md)
- [데이터 정렬 및 필터링](sorting-and-filtering-data.md)
- [DataTable](datatables.md)
- [ADO.NET 개요](../ado-net-overview.md)
