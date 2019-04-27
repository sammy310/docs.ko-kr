---
title: DataTables
ms.date: 03/30/2017
ms.assetid: 52ff0e32-3e5a-41de-9a3b-7b04ea52b83e
ms.openlocfilehash: f6509400d7f6633749155f778e3ba58ec6c27ec2
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61880001"
---
# <a name="datatables"></a>DataTables
<xref:System.Data.DataSet>은 테이블 컬렉션, 관계 및 제약 조건으로 구성되어 있습니다. Ado.net에서는 <xref:System.Data.DataTable> 개체에서 테이블을 나타내는 데 사용 되며를 **데이터 집합**합니다. A **DataTable** 메모리 내 관계형 데이터의 테이블 데이터가 로컬 합니다. 상주 하지만 Microsoft SQL Server를 사용 하 여 같은 데이터 원본에서 채울 수 있습니다 하는.NET 기반 응용 프로그램을 **DataAdapter** 자세한 내용은 참조 하십시오 [DataAdapter에서 DataSet 채우기](../../../../../docs/framework/data/adonet/populating-a-dataset-from-a-dataadapter.md) .  
  
 합니다 **DataTable** 클래스의 멤버인 합니다 **System.Data** .NET Framework 클래스 라이브러리 내의 네임 스페이스입니다. 만들고 사용할 수는 **DataTable** 독립적으로 또는 멤버인을 **데이터 집합**, 및 **DataTable** 개체 다른.NET Framework 개체와 함께에서 사용할 수도 있습니다 포함 된 <xref:System.Data.DataView>합니다. 테이블 컬렉션에 액세스를 **데이터 집합** 를 통해를 **테이블** 속성을 **데이터 집합** 개체.  
  
 테이블의 스키마나 구조는 열이나 제약 조건에 의해 표시됩니다. 스키마를 정의 하는 **DataTable** 사용 하 여 <xref:System.Data.DataColumn> 개체 뿐만 <xref:System.Data.ForeignKeyConstraint> 및 <xref:System.Data.UniqueConstraint> 개체입니다. 테이블 열은 데이터 소스 열에 매핑될 수 있습니다. 또한 이 열은 식에서 계산된 값을 포함하며 값을 자동으로 증가시키고 기본 키 값을 포함할 수 있습니다.  
  
 스키마 이외에 **DataTable** 포함 하 고 데이터를 정렬 하는 행이 있어야 합니다. <xref:System.Data.DataRow> 클래스는 테이블에 포함된 실제 데이터를 나타냅니다. 사용할 합니다 **DataRow** 및 해당 속성 및 메서드를 검색, 평가 및 테이블의 데이터를 조작 합니다. 액세스 하는 행 내에서 데이터를 변경 합니다 **DataRow** 개체의 현재 및 원래 상태를 유지 관리 합니다.  
  
 테이블에서 하나 이상의 관련 열을 사용하면 테이블 간에 부모-자식 관계를 만들 수 있습니다. 간의 관계를 만들면 **DataTable** 사용 하 여 개체를 <xref:System.Data.DataRelation>입니다. **DataRelation** 개체는 특정 행의 관련된 자식 또는 부모 행을 반환 하려면 사용할 수 있습니다. 자세한 내용은 [Datarelation 추가](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/adding-datarelations.md)합니다.  
  
## <a name="in-this-section"></a>섹션 내용  
 [DataTable 만들기](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/creating-a-datatable.md)  
 만드는 방법을 설명를 **DataTable** 에 추가 하는 **데이터 집합**합니다.  
  
 [DataTable 스키마 정의](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/datatable-schema-definition.md)  
 만들기 및 사용 하는 방법에 대 한 정보를 제공 **DataColumn** 개체 및 제약 조건입니다.  
  
 [DataTable에서 데이터 조작](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/manipulating-data-in-a-datatable.md)  
 테이블에서 데이터를 추가, 수정 및 삭제하는 방법에 대해 설명합니다. 사용 하는 방법에 설명 **DataTable** 데이터 테이블의 변경 내용을 검사 하는 이벤트입니다.  
  
 [DataTable 이벤트 처리](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/handling-datatable-events.md)  
 사용에 대 한 사용할 수 있는 이벤트에 대 한 정보를 제공 된 **DataTable**, 열 값을 수정 하거나 행을 추가 하거나 삭제할 때 이벤트를 포함 하 여 합니다.  
  
## <a name="related-sections"></a>관련 단원  
 [ADO.NET](../../../../../docs/framework/data/adonet/index.md)  
 ADO.NET 아키텍처 및 구성 요소에 대해 설명하고, 이를 사용하여 기존 데이터 소스에 액세스하고 응용 프로그램 데이터를 관리하는 방법을 설명합니다.  
  
 [DataSet, DataTable 및 DataView](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)  
 ADO.NET에 대 한 정보를 제공 **데이터 집합** 테이블 간의 관계를 만드는 방법을 포함 합니다.  
  
 <xref:System.Data.Constraint>  
 에 대 한 참조 정보를 제공 합니다 **제약 조건** 개체입니다.  
  
 <xref:System.Data.DataColumn>  
 에 대 한 참조 정보를 제공 합니다 **DataColumn** 개체입니다.  
  
 <xref:System.Data.DataSet>  
 에 대 한 참조 정보를 제공 합니다 **데이터 집합** 개체입니다.  
  
 <xref:System.Data.DataTable>  
 에 대 한 참조 정보를 제공 합니다 **DataTable** 개체입니다.  
  
 [클래스 라이브러리 개요](../../../../../docs/standard/class-library-overview.md)  
 .NET Framework 클래스 라이브러리에 간략하게 포함 하 여는 **시스템** 네임 스페이스의 두 번째 수준 네임 스페이스와 **System.Data**합니다.  
  
## <a name="see-also"></a>참고자료

- [ADO.NET 관리되는 공급자 및 데이터 집합 개발자 센터](https://go.microsoft.com/fwlink/?LinkId=217917)
