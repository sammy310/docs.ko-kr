---
description: '자세히 알아보기: 데이터 집합 만들기'
title: 데이터 세트 만들기
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 57629d8f-393e-4677-8b83-29ffde27f5fc
ms.openlocfilehash: 7a52c6e73b5ab3ba4bf384d6bab3640b85929fcc
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99739653"
---
# <a name="creating-a-dataset"></a>데이터 세트 만들기

<xref:System.Data.DataSet>의 인스턴스는 <xref:System.Data.DataSet> 생성자를 호출하여 만듭니다. 선택적으로 이름 인수를 지정합니다. <xref:System.Data.DataSet>의 이름을 지정하지 않으면 해당 이름은 "NewDataSet"으로 설정됩니다.  
  
 기존 <xref:System.Data.DataSet>을 기반으로 새 <xref:System.Data.DataSet>을 만들 수도 있습니다. 새 <xref:System.Data.DataSet>은 기존 <xref:System.Data.DataSet>과 동일한 복사본이거나, 관계 구조 또는 스키마는 복사하지만 기존 <xref:System.Data.DataSet>의 데이터는 포함하지 않는 <xref:System.Data.DataSet>의 복제이거나, 또는 <xref:System.Data.DataSet> 메서드를 사용하여 기존 <xref:System.Data.DataSet>의 수정된 행만 포함하는 <xref:System.Data.DataSet.GetChanges%2A>의 하위 집합일 수도 있습니다. 자세한 내용은 [데이터 집합 내용 복사](copying-dataset-contents.md)를 참조 하세요.  
  
 다음 코드 예제에서는 <xref:System.Data.DataSet>의 인스턴스를 생성하는 방법을 보여 줍니다.  
  
```vb  
Dim customerOrders As DataSet = New DataSet("CustomerOrders")  
```  
  
```csharp  
DataSet customerOrders = new DataSet("CustomerOrders");  
```  
  
## <a name="see-also"></a>참고 항목

- [DataAdapter에서 DataSet 채우기](../populating-a-dataset-from-a-dataadapter.md)
- [DataSets, DataTables 및 DataViews](index.md)
- [ADO.NET 개요](../ado-net-overview.md)
