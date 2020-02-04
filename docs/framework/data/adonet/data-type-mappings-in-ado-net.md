---
title: 데이터 형식 매핑
ms.date: 03/30/2017
ms.assetid: d4afab94-ada6-4c77-a73c-41f17bae6b5a
ms.openlocfilehash: 610cdc1a679b0c51125075076120e12db97da421
ms.sourcegitcommit: 19014f9c081ca2ff19652ca12503828db8239d48
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "76980199"
---
# <a name="data-type-mappings-in-adonet"></a>ADO.NET에서 데이터 형식 매핑
.NET Framework는 런타임에 형식이 선언, 사용 및 관리되는 방법을 정의하는 공용 형식 시스템을 기반으로 합니다. .NET Framework는 값 형식과 참조 형식으로 구성되며, 두 형식 모두 <xref:System.Object> 기본 형식에서 파생됩니다. 데이터 소스로 작업할 경우 데이터 형식을 명시적으로 지정하지 않으면 데이터 공급자에서 데이터 형식이 유추됩니다. 예를 들어 <xref:System.Data.DataSet> 개체는 모든 데이터 소스에 대해 독립적입니다. `DataSet`의 데이터는 데이터 소스에서 검색되며 변경 내용은 `DataAdapter`를 사용하여 데이터 소스에 다시 적용됩니다. 즉, `DataAdapter`에서 `DataSet`의 <xref:System.Data.DataTable>를 데이터 원본의 값으로 채울 때 `DataTable`에 있는 열의 결과 데이터 형식은 데이터 원본에 연결 하는 데 사용 되는 .NET Framework 데이터 공급자와 관련 된 형식이 아닌 .NET Framework 형식입니다.  
  
 마찬가지로 `DataReader`이 데이터 원본에서 값을 반환 하는 경우 결과 값은 .NET Framework 형식의 지역 변수에 저장 됩니다. `DataAdapter` `Fill` 작업과 `DataReader`의 `Get` 메서드 모두 .NET Framework 데이터 공급자에서 반환 된 값에서 .NET Framework 형식이 유추 됩니다.  
  
 반환되는 값의 형식을 알고 있는 경우에는 유추되는 데이터 형식을 사용하는 대신 `DataReader`의 형식화된 접근자 메서드를 사용할 수 있습니다. 형식화 된 접근자 메서드는 값을 특정 .NET Framework 형식으로 반환 하 여 더 나은 성능을 제공 하므로 추가 형식 변환이 필요 하지 않습니다.  
  
> [!NOTE]
> .NET Framework 데이터 공급자 데이터 형식에 대 한 Null 값은 `DBNull.Value`으로 표시 됩니다.  
  
## <a name="in-this-section"></a>섹션 내용  
 [SQL Server 데이터 형식 매핑](sql-server-data-type-mappings.md)  
 <xref:System.Data.SqlClient>의 유추된 데이터 형식 매핑과 데이터 접근자 메서드 목록을 제공합니다.  
  
 [OLE DB 데이터 형식 매핑](ole-db-data-type-mappings.md)  
 <xref:System.Data.OleDb>의 유추된 데이터 형식 매핑과 데이터 접근자 메서드 목록을 제공합니다.  
  
 [ODBC 데이터 형식 매핑](odbc-data-type-mappings.md)  
 <xref:System.Data.Odbc>의 유추된 데이터 형식 매핑과 데이터 접근자 메서드 목록을 제공합니다.  
  
 [Oracle 데이터 형식 매핑](oracle-data-type-mappings.md)  
 <xref:System.Data.OracleClient>의 유추된 데이터 형식 매핑과 데이터 접근자 메서드 목록을 제공합니다.  
  
 [부동 소수점 숫자](floating-point-numbers.md)  
 개발자가 부동 소수점 숫자를 사용할 때 자주 발생하는 문제에 대해 설명합니다.  
  
## <a name="see-also"></a>참조

- [SQL Server 데이터 형식 및 ADO.NET](./sql/sql-server-data-types.md)
- [매개 변수 및 매개 변수 데이터 형식 구성](configuring-parameters-and-parameter-data-types.md)
- [데이터베이스 스키마 정보 검색](retrieving-database-schema-information.md)
- [공용 형식 시스템](../../../standard/base-types/common-type-system.md)
- [형식 변환](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/t8s7t9bf(v=vs.90))
- [ADO.NET 개요](ado-net-overview.md)
