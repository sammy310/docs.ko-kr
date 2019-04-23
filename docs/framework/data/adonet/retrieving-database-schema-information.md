---
title: 데이터베이스 스키마 정보 검색
ms.date: 03/30/2017
ms.assetid: 79038d52-f122-4fd4-9bfb-aaa22d6a114b
ms.openlocfilehash: 885d3c9ad61c9099c960ddb0c0f77fa8a98dbefa
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59133707"
---
# <a name="retrieving-database-schema-information"></a>데이터베이스 스키마 정보 검색
데이터베이스에서 스키마 정보를 가져오려면 스키마 검색 프로세스를 사용합니다. 스키마 검색을 사용 하면 응용 프로그램을 관리 되는 공급자 찾아 라고도 데이터베이스 스키마에 대 한 정보 반환을 요청 *메타 데이터*, 지정된 된 데이터베이스입니다. 테이블, 열 및 저장 프로시저 같은 다양한 데이터베이스 스키마 요소는 스키마 컬렉션을 통해 노출됩니다. 각 스키마 컬렉션에는 사용하는 공급자와 관련된 다양한 스키마 정보가 들어 있습니다.  
  
 각.NET Framework 관리 공급자 구현 합니다 **GetSchema** 에서 메서드는 **연결** 에서 반환 되는 스키마 정보와 클래스는 **GetSchema**형태로 제공 되는 메서드를 <xref:System.Data.DataTable>입니다. 합니다 **GetSchema** 메서드는 스키마 컬렉션이 반환 되도록 지정 하 고 반환 되는 정보의 양을 제한에 대 한 선택적 매개 변수를 제공 하는 오버 로드 된 메서드입니다.  
  
 OLE DB, ODBC, Oracle 및 SqlClient에 대 한.NET Framework 데이터 공급자를 제공 된 **GetSchemaTable** 의 열 메타 데이터를 설명 하는 DataTable을 반환 하는 메서드는 **DataReader**합니다.  
  
 또한 .NET Framework Data Provider for OLE DB에서는 <xref:System.Data.OleDb.OleDbConnection.GetOleDbSchemaTable%2A> 개체의 <xref:System.Data.OleDb.OleDbConnection> 메서드를 사용하여 스키마 정보를 노출합니다. 인수로 **GetOleDbSchemaTable** 사용을 <xref:System.Data.OleDb.OleDbSchemaGuid> 반환할 스키마 정보를 식별 하 고 반환 된 열에 대 한 제한 배열을 합니다. **GetOleDbSchemaTable** 반환을 <xref:System.Data.DataTable> 요청한 스키마 정보로 채워집니다.  
  
## <a name="in-this-section"></a>섹션 내용  
 [GetSchema 및 Schema 컬렉션](../../../../docs/framework/data/adonet/getschema-and-schema-collections.md)  
 에 대해 설명 합니다 **GetSchema** 메서드와 사용할 수 있는 방법을 검색 하 고 데이터베이스에서 스키마 정보를 제한 합니다.  
  
 스키마 제한  
 사용 하 여 사용할 수 있는 스키마 제한을 설명 합니다 **GetSchema**합니다.  
  
 [공통 스키마 컬렉션](../../../../docs/framework/data/adonet/common-schema-collections.md)  
 모든 .NET Framework 관리 공급자에서 지원하는 모든 공통 스키마 컬렉션에 대해 설명합니다.  
  
 [SQL Server 스키마 컬렉션](../../../../docs/framework/data/adonet/sql-server-schema-collections.md)  
 .NET Framework Provider for SQL Server에서 지원하는 스키마 컬렉션에 대해 설명합니다.  
  
 [Oracle 스키마 컬렉션](../../../../docs/framework/data/adonet/oracle-schema-collections.md)  
 .NET Framework Provider for Oracle에서 지원하는 스키마 컬렉션에 대해 설명합니다.  
  
 [ODBC 스키마 컬렉션](../../../../docs/framework/data/adonet/odbc-schema-collections.md)  
 ODBC 드라이버의 스키마 컬렉션에 대해 설명합니다.  
  
 [OLE DB 스키마 컬렉션](../../../../docs/framework/data/adonet/ole-db-schema-collections.md)  
 OLE DB 공급자의 스키마 컬렉션에 대해 설명합니다.  
  
## <a name="reference"></a>참조  
 <xref:System.Data.Common.DbConnection.GetSchema%2A>  
 에 대해 설명 합니다 **GetSchema** 메서드를 <xref:System.Data.Common.DbConnection> 클래스.  
  
 <xref:System.Data.Odbc.OdbcConnection.GetSchema%2A>  
 에 대해 설명 합니다 **GetSchema** 메서드를 <xref:System.Data.Odbc.OdbcConnection> 클래스.  
  
 <xref:System.Data.OleDb.OleDbConnection.GetSchema%2A>  
 에 대해 설명 합니다 **GetSchema** 메서드를 <xref:System.Data.OleDb.OleDbConnection> 클래스.  
  
 <xref:System.Data.OracleClient.OracleConnection.GetSchema%2A>  
 에 대해 설명 합니다 **GetSchema** 메서드를 <xref:System.Data.OracleClient.OracleConnection> 클래스.  
  
 <xref:System.Data.SqlClient.SqlConnection.GetSchema%2A>  
 에 대해 설명 합니다 **GetSchema** 메서드를 <xref:System.Data.SqlClient.SqlConnection> 클래스.  
  
 <xref:System.Data.Common.DbDataReader.GetSchemaTable%2A>  
 에 대해 설명 합니다 **GetSchemaTable** 메서드를 <xref:System.Data.Common.DbDataReader> 클래스.  
  
 <xref:System.Data.Odbc.OdbcDataReader.GetSchemaTable%2A>  
 에 대해 설명 합니다 **GetSchemaTable** 메서드를 <xref:System.Data.Odbc.OdbcDataReader> 클래스.  
  
 <xref:System.Data.OleDb.OleDbDataReader.GetSchemaTable%2A>  
 에 대해 설명 합니다 **GetSchemaTable** 메서드를 <xref:System.Data.OleDb.OleDbDataReader> 클래스.  
  
 <xref:System.Data.OracleClient.OracleDataReader.GetSchemaTable%2A>  
 에 대해 설명 합니다 **GetSchemaTable** 메서드를 <xref:System.Data.OracleClient.OracleDataReader> 클래스.  
  
 <xref:System.Data.SqlClient.SqlDataReader.GetSchemaTable%2A>  
 에 대해 설명 합니다 **GetSchemaTable** 메서드를 <xref:System.Data.SqlClient.SqlDataReader> 클래스.  
  
## <a name="see-also"></a>참고자료

- [ADO.NET에서 데이터 검색 및 수정](../../../../docs/framework/data/adonet/retrieving-and-modifying-data.md)
- [ADO.NET 관리되는 공급자 및 데이터 집합 개발자 센터](https://go.microsoft.com/fwlink/?LinkId=217917)
