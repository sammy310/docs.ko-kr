---
title: 데이터 집합 만들기
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 57629d8f-393e-4677-8b83-29ffde27f5fc
ms.openlocfilehash: d2d17056e6dcd29ef9b5c5e8c3024a32fce32bd5
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61879881"
---
# <a name="creating-a-dataset"></a>데이터 집합 만들기
<xref:System.Data.DataSet>의 인스턴스는 <xref:System.Data.DataSet> 생성자를 호출하여 만듭니다. 선택적으로 이름 인수를 지정합니다. <xref:System.Data.DataSet>의 이름을 지정하지 않으면 해당 이름은 "NewDataSet"으로 설정됩니다.  
  
 기존 <xref:System.Data.DataSet>을 기반으로 새 <xref:System.Data.DataSet>을 만들 수도 있습니다. 새 <xref:System.Data.DataSet>은 기존 <xref:System.Data.DataSet>과 동일한 복사본이거나, 관계 구조 또는 스키마는 복사하지만 기존 <xref:System.Data.DataSet>의 데이터는 포함하지 않는 <xref:System.Data.DataSet>의 복제이거나, 또는 <xref:System.Data.DataSet> 메서드를 사용하여 기존 <xref:System.Data.DataSet>의 수정된 행만 포함하는 <xref:System.Data.DataSet.GetChanges%2A>의 하위 집합일 수도 있습니다. 자세한 내용은 [데이터 집합 콘텐츠 복사](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/copying-dataset-contents.md)합니다.  
  
 다음 코드 예제에서는 <xref:System.Data.DataSet>의 인스턴스를 생성하는 방법을 보여 줍니다.  
  
```vb  
Dim customerOrders As DataSet = New DataSet("CustomerOrders")  
```  
  
```csharp  
DataSet customerOrders = new DataSet("CustomerOrders");  
```  
  
## <a name="see-also"></a>참고자료

- [DataAdapter에서 데이터 집합 채우기](../../../../../docs/framework/data/adonet/populating-a-dataset-from-a-dataadapter.md)
- [DataSet, DataTable 및 DataView](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)
- [ADO.NET 관리되는 공급자 및 데이터 집합 개발자 센터](https://go.microsoft.com/fwlink/?LinkId=217917)
