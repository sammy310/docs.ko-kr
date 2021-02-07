---
description: '자세히 알아보기: 데이터 집합에 기존 제약 조건 추가'
title: 데이터 세트에 기존 제약 조건 추가
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 307d2809-208b-4cf8-b6a9-5d16f15fc16c
ms.openlocfilehash: cad0dd1bd16747a5e76e10784d00c14cd9aa8c2a
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99729574"
---
# <a name="adding-existing-constraints-to-a-dataset"></a>데이터 세트에 기존 제약 조건 추가

**DataAdapter** 의 **Fill** 메서드는 <xref:System.Data.DataSet> 데이터 원본의 테이블 열과 행만 사용 하 여를 채웁니다. 제약 조건은 일반적으로 데이터 원본에 의해 설정 되지만 **Fill** 메서드는 기본적으로이 스키마 정보를 데이터 **집합** 에 추가 하지 않습니다. 데이터 원본의 기존 기본 키 제약 조건 정보를 사용 하 여 데이터 **집합** 을 채우려면 **dataadapter** 의 **FillSchema** 메서드를 호출 하거나 **Fill** 을 호출 하기 전에 **dataadapter** 의 **MissingSchemaAction** 속성을 **AddWithKey** 로 설정할 수 있습니다. 이렇게 하면 **DataSet** 의 기본 키 제약 조건이 데이터 원본의 해당 제약 조건을 반영합니다. Foreign key 제약 조건 정보는 포함 되지 않으며 [DataTable 제약 조건](./dataset-datatable-dataview/datatable-constraints.md)에 표시 된 대로 명시적으로 만들어야 합니다.  
  
**DataSet** 를 데이터로 채우기 전에 스키마 정보를 추가하면 기본 키 제약 조건이 <xref:System.Data.DataTable> 개체와 함께 **DataSet** 에 포함됩니다. 결과적으로 **DataSet** 의 Fill에 대한 추가 호출이 있으면 기본 키 열 정보를 사용하여 데이터 원본의 새 행을 각 **DataTable** 의 현재 행과 일치시키고 해당 테이블의 현재 데이터를 데이터 원본의 데이터로 덮어씁니다. 스키마 정보가 없으면 데이터 원본의 새 행이 **DataSet** 에 추가되어 결국 행이 중복됩니다.  
  
> [!NOTE]
> 데이터 원본의 열이 자동 증가, **FillSchema** 메서드 또는 **Fill** 메서드 ( **MissingSchemaAction** **AddWithKey**)로 식별 되 면 **AutoIncrement** 속성이로 설정 된 **DataColumn** 을 만듭니다 `true` . 그러나 **AutoIncrementStep** 및 **AutoIncrementSeed** 값은 직접 설정해야 합니다. 자동 증분 열에 대 한 자세한 내용은 [AutoIncrement 열 만들기](./dataset-datatable-dataview/creating-autoincrement-columns.md)를 참조 하세요.  
  
**FillSchema** 를 사용하거나 **MissingSchemaAction** 을 **AddWithKey** 로 설정하려면 기본 키 열 정보를 확인하기 위해 데이터 원본에서 추가 처리를 수행해야 합니다. 이러한 추가 처리로 인해 성능이 낮아질 수 있습니다. 디자인 타임에 기본 키 정보를 알고 있으면 기본 키 열을 명시적으로 지정하여 최상의 성능을 얻을 수 있습니다. 테이블에 대 한 기본 키 정보를 명시적으로 설정 하는 방법에 대 한 자세한 내용은 [기본 키 정의](./dataset-datatable-dataview/defining-primary-keys.md)를 참조 하세요.
  
다음 코드 예제에서는 **FillSchema** 를 사용 하 여 **데이터 집합** 에 스키마 정보를 추가 하는 방법을 보여 줍니다.
  
```vb  
Dim custDataSet As New DataSet()  
  
custAdapter.FillSchema(custDataSet, SchemaType.Source, "Customers")  
custAdapter.Fill(custDataSet, "Customers")  
```  
  
```csharp  
var custDataSet = new DataSet();  
  
custAdapter.FillSchema(custDataSet, SchemaType.Source, "Customers");  
custAdapter.Fill(custDataSet, "Customers");  
```  
  
다음 코드 예제에서는 **Fill** 메서드의 **MissingSchemaAction. AddWithKey** 속성을 사용 하 여 **데이터 집합** 에 스키마 정보를 추가 하는 방법을 보여 줍니다.
  
```vb  
Dim custDataSet As New DataSet()  
  
custAdapter.MissingSchemaAction = MissingSchemaAction.AddWithKey  
custAdapter.Fill(custDataSet, "Customers")  
```  
  
```csharp  
var custDataSet = new DataSet();  
  
custAdapter.MissingSchemaAction = MissingSchemaAction.AddWithKey;  
custAdapter.Fill(custDataSet, "Customers");  
```  
  
## <a name="handling-multiple-result-sets"></a>다중 결과 집합 처리  

**DataAdapter** 가 **SelectCommand** 에서 반환 된 여러 결과 집합을 발견 하는 경우 **데이터 집합** 에 여러 개의 테이블을 만듭니다. 테이블에는 0부터 시작하되 “Table0”이 아니라 **Table** 로 시작하는 증분 기본 이름 **Table** *N* 이 지정됩니다. 테이블 이름이 **FillSchema** 메서드에 인수로 전달 되는 경우 테이블에는 0부터 시작 하는 증분 이름 (예를 들어, "TableName0  " 대신 **tablename** *으로 시작*)이 지정 됩니다.  
  
> [!NOTE]
> 여러 결과 집합을 반환 하는 명령에 대해 **OleDbDataAdapter** 개체의 **FillSchema** 메서드를 호출 하면 첫 번째 결과 집합의 스키마 정보만 반환 됩니다. **OleDbDataAdapter** 를 사용 하 여 여러 결과 집합에 대 한 스키마 정보를 반환 하는 경우 **MissingSchemaAction** 의 **AddWithKey** 를 지정 하 고 **Fill** 메서드를 호출할 때 스키마 정보를 가져오는 것이 좋습니다.  
  
## <a name="see-also"></a>참고 항목

- [DataAdapters 및 DataReaders](dataadapters-and-datareaders.md)
- [DataSets, DataTables 및 DataViews](./dataset-datatable-dataview/index.md)
- [ADO.NET에서 데이터 검색 및 수정](retrieving-and-modifying-data.md)
- [ADO.NET 개요](ado-net-overview.md)
