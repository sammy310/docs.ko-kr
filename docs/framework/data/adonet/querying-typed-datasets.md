---
title: 형식화된 데이터 세트 쿼리
ms.date: 08/15/2018
dev_langs:
- csharp
- vb
ms.assetid: ad712fa1-2baf-462a-b163-574cce6d376a
ms.openlocfilehash: d956fd5f07c108146d20623bcf811266380c132c
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61651742"
---
# <a name="query-typed-datasets"></a>형식화 된 데이터 집합 쿼리

하는 경우의 스키마를 <xref:System.Data.DataSet> 응용 프로그램 디자인 타임에 알려진는 형식화 된를 사용 하는 것이 좋습니다 <xref:System.Data.DataSet> LINQ to DataSet 사용 하는 경우. 형식화된 <xref:System.Data.DataSet>은 <xref:System.Data.DataSet>에서 파생된 클래스입니다. 따라서 <xref:System.Data.DataSet>의 모든 메서드, 이벤트 및 속성이 상속됩니다. 또한 형식화된 <xref:System.Data.DataSet>에서는 강력한 형식의 메서드, 이벤트 및 속성을 제공합니다. 즉, 컬렉션 기반의 메서드 대신 이름을 사용하여 테이블과 열에 액세스할 수 있습니다. 이렇게 하면 간단하고 이해하기 쉬운 쿼리를 만들 수 있습니다. 자세한 내용은 [형식화 된 데이터 집합](../../../../docs/framework/data/adonet/dataset-datatable-dataview/typed-datasets.md)합니다.

LINQ to DataSet 형식화 된 쿼리도 지원 <xref:System.Data.DataSet>합니다. 형식화된 <xref:System.Data.DataSet>을 사용하면 열 데이터에 액세스하기 위해 제네릭 <xref:System.Data.DataRowExtensions.Field%2A> 메서드 또는 <xref:System.Data.DataRowExtensions.SetField%2A> 메서드를 사용하지 않아도 됩니다. <xref:System.Data.DataSet>에 형식 정보가 있기 때문에 컴파일 타임에 속성 이름을 사용할 수 있습니다. LINQ to DataSet 런타임에 코드 대신 컴파일될 때 형식 불일치 오류가 발생 있도록를 올바른 형식으로 열 값에 대 한 액세스를 제공 합니다.

형식화 된 쿼리를 시작 하기 전에 <xref:System.Data.DataSet>를 사용 하 여 클래스를 생성 해야 합니다 **데이터 집합 디자이너** Visual Studio에서. 자세한 내용은 [만들기 및 데이터 집합 구성](/visualstudio/data-tools/create-and-configure-datasets-in-visual-studio)합니다.

## <a name="example"></a>예제

다음 예제에서는 형식화된 <xref:System.Data.DataSet>에 대한 쿼리를 보여 줍니다.

```csharp
var query = from o in orders
            where o.OnlineOrderFlag == true
            select new { o.SalesOrderID,
                         o.OrderDate,
                         o.SalesOrderNumber };

foreach(var order in query)
{
    Console.WriteLine("{0}\t{1:d}\t{2}",
      order.SalesOrderID,
      order.OrderDate,
      order.SalesOrderNumber);
}
```

```vb
Dim orders = ds.Tables("SalesOrderHeader")

Dim query = _
       From o In orders _
       Where o.OnlineOrderFlag = True _
       Select New {SalesOrderID := o.SalesOrderID, _
                   OrderDate := o.OrderDate, _
                   SalesOrderNumber := o.SalesOrderNumber}

For Each Dim onlineOrder In query
 Console.WriteLine("{0}\t{1:d}\t{2}", _
 onlineOrder.SalesOrderID, _
 onlineOrder.OrderDate, _
 onlineOrder.SalesOrderNumber)
Next
```

## <a name="see-also"></a>참고자료

- [데이터 집합 쿼리](../../../../docs/framework/data/adonet/querying-datasets-linq-to-dataset.md)
- [크로스 테이블 쿼리](../../../../docs/framework/data/adonet/cross-table-queries-linq-to-dataset.md)
- [단일 테이블 쿼리](../../../../docs/framework/data/adonet/single-table-queries-linq-to-dataset.md)
