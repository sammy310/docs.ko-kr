---
title: 데이터 집합에 기존 제약 조건 추가
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 307d2809-208b-4cf8-b6a9-5d16f15fc16c
ms.openlocfilehash: 18c391e97baa170b78dcfe0165fb38b6c6d739f4
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59210557"
---
# <a name="adding-existing-constraints-to-a-dataset"></a>데이터 집합에 기존 제약 조건 추가
**채우기** 메서드는 **DataAdapter** 채웁니다를 <xref:System.Data.DataSet> 만 테이블 열과 행을 데이터 원본에서 하지만 제약 조건은 일반적으로에서 설정 하는 데이터 원본에는 **채우기** 메서드는이 스키마 정보를 추가 하지 않습니다 합니다 **데이터 집합** 기본적으로 합니다. 채우는 **데이터 집합** 데이터 원본에서 기존 primary key 제약 조건 정보를 사용 하 여 호출할 수 있습니다는 **FillSchema** 메서드의 **DataAdapter**을 가져오거나 설정 합니다 **MissingSchemaAction** 의 속성을 **DataAdapter** 에 **AddWithKey** 호출 하기 전에 **채우기**합니다. 이렇게 하면 기본 키 제약 조건에는 **데이터 집합** 데이터 소스에서 반영 합니다. 외래 키 제약 조건 정보 포함 되지 않습니다 및에 표시 된 대로 명시적으로 만들어야 합니다 [DataTable 제약 조건](../../../../docs/framework/data/adonet/dataset-datatable-dataview/datatable-constraints.md)합니다.  
  
 스키마 정보 추가 **데이터 집합** primary key 제약 조건으로 포함 되어 있는지 확인 데이터로 채우기 전에 <xref:System.Data.DataTable> 개체를 **데이터 집합**. 결과적으로 추가 하는 경우 입력에 대 한 호출을 **데이터 집합** 내용이, 기본 키 열 정보 각각의 현재 행을 사용 하 여 데이터 원본에서 새 행과 일치 하는 데 사용 됩니다 **DataTable**, 및 현재 데이터 데이터 원본에서 데이터를 사용 하 여 테이블을 덮어씁니다. 스키마 정보 없이 데이터 소스의 새 행에 추가 됩니다는 **데이터 집합**, 중복 행의 결과입니다.  
  
> [!NOTE]
>  자동 증가와 데이터 원본에서 열 식별 되는 **FillSchema** 메서드 또는 **채우기** 메서드를 **MissingSchemaAction** 의  **AddWithKey**를 만듭니다를 **DataColumn** 와 **AutoIncrement** 속성이로 설정 `true`합니다. 그러나 설정 해야 합니다는 **AutoIncrementStep** 하 고 **AutoIncrementSeed** 직접 값입니다. 자동 증분 열에 대 한 자세한 내용은 참조 하세요. [AutoIncrement 열 만들기](../../../../docs/framework/data/adonet/dataset-datatable-dataview/creating-autoincrement-columns.md)합니다.  
  
 사용 하 여 **FillSchema** 또는 설정 된 **MissingSchemaAction** 에 **AddWithKey** 기본 키 열 정보를 확인 하 고 데이터 소스의 추가 처리가 필요 합니다. 이러한 추가 처리로 인해 성능이 낮아질 수 있습니다. 디자인 타임에 기본 키 정보를 알고 있으면 기본 키 열을 명시적으로 지정하여 최상의 성능을 얻을 수 있습니다. 테이블에 대 한 기본 키 정보를 명시적으로 설정 하는 방법에 대 한 내용은 [기본 키 정의](../../../../docs/framework/data/adonet/dataset-datatable-dataview/defining-primary-keys.md)합니다.  
  
 다음 코드 예제에 대 한 스키마 정보를 추가 하는 방법을 보여 줍니다는 **데이터 집합** 사용 하 여 **FillSchema**합니다.  
  
```vb  
Dim custDataSet As DataSet = New DataSet()  
  
custAdapter.FillSchema(custDataSet, SchemaType.Source, "Customers")  
custAdapter.Fill(custDataSet, "Customers")  
```  
  
```csharp  
DataSet custDataSet = new DataSet();  
  
custAdapter.FillSchema(custDataSet, SchemaType.Source, "Customers");  
custAdapter.Fill(custDataSet, "Customers");  
```  
  
 다음 코드 예제에 대 한 스키마 정보를 추가 하는 방법을 보여 줍니다를 **데이터 집합** 를 사용 하 여는 **MissingSchemaAction.AddWithKey** 속성을 **채우기** 메서드.  
  
```vb  
Dim custDataSet As DataSet = New DataSet()  
  
custAdapter.MissingSchemaAction = MissingSchemaAction.AddWithKey  
custAdapter.Fill(custDataSet, "Customers")  
```  
  
```csharp  
DataSet custDataSet = new DataSet();  
  
custAdapter.MissingSchemaAction = MissingSchemaAction.AddWithKey;  
custAdapter.Fill(custDataSet, "Customers");  
```  
  
## <a name="handling-multiple-result-sets"></a>여러 개의 결과 집합 처리  
 경우는 **DataAdapter** 에서 반환 하는 여러 결과 집합에서 발견 합니다 **SelectCommand**, 여러 테이블에 생성 됩니다는 **데이터 집합**. 테이블을 0부터 시작 증분 기본 이름인 주어 집니다 **테이블** *N*부터 **테이블** "Table0" 대신 합니다. 테이블 이름을 인수로 전달 됩니다 합니다 **FillSchema** 메서드는 테이블 이름이 지정 됩니다.는 0부터 시작 증분의 **TableName** *N* 부터**TableName** "TableName0" 대신 합니다.  
  
> [!NOTE]
>  경우는 **FillSchema** 메서드는 **OleDbDataAdapter** 개체는 여러 결과 집합을 반환 하는 명령에 대 한 호출 된 첫 번째 결과 집합의 스키마 정보만 반환 됩니다. 여러 결과 대 한 스키마 정보를 반환할가 사용 하 여를 설정 하면 합니다 **OleDbDataAdapter**를 지정 하는 것이 좋습니다는 **MissingSchemaAction** 의 **AddWithKey** 호출할 때 스키마 정보를 가져오는 및 합니다 **채우기** 메서드.  
  
## <a name="see-also"></a>참고자료

- [DataAdapter 및 DataReader](../../../../docs/framework/data/adonet/dataadapters-and-datareaders.md)
- [DataSet, DataTable 및 DataView](../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)
- [ADO.NET에서 데이터 검색 및 수정](../../../../docs/framework/data/adonet/retrieving-and-modifying-data.md)
- [ADO.NET 관리되는 공급자 및 데이터 집합 개발자 센터](https://go.microsoft.com/fwlink/?LinkId=217917)
