---
description: SQL Server 스키마 컬렉션에 대해 자세히 알아보세요.
title: SQL Server 스키마 컬렉션
ms.date: 03/30/2017
ms.assetid: c6403cc3-d78b-4f85-bab1-ada7a3446ec5
ms.openlocfilehash: 0299daada77b6968a0b1f875956da7bd2a221322
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99718670"
---
# <a name="sql-server-schema-collections"></a>SQL Server 스키마 컬렉션

Microsoft .NET Framework Data Provider for SQL Server는 공통 스키마 컬렉션뿐만 아니라 다른 스키마 컬렉션도 추가적으로 지원합니다. 지원되는 스키마 컬렉션은 현재 사용하고 있는 SQL Sever 버전에 따라 조금씩 다를 수 있습니다. 지원되는 스키마 컬렉션 목록을 확인하려면 **GetSchema** 메서드를 인수 없이 호출하거나 “MetaDataCollections”라는 스키마 컬렉션 이름을 사용하여 호출합니다. 그러면 지원되는 스키마 컬렉션의 목록, 각자 지원하는 제약 조건 수 및 사용하는 식별자 부분 수가 포함된 <xref:System.Data.DataTable>이 반환됩니다.  
  
## <a name="databases"></a>데이터베이스  
  
|ColumnName|DataType|설명|  
|----------------|--------------|-----------------|  
|database_name|String|데이터베이스의 이름입니다.|  
|dbid|Int16|데이터베이스 ID입니다.|  
|create_date|DateTime|데이터베이스를 만든 날짜입니다.|  
  
## <a name="foreign-keys"></a>외래 키  
  
|ColumnName|DataType|Description|  
|----------------|--------------|-----------------|  
|CONSTRAINT_CATALOG|String|제약 조건이 속하는 카탈로그입니다.|  
|CONSTRAINT_SCHEMA|String|제약 조건을 포함하는 스키마입니다.|  
|CONSTRAINT_NAME|String|이름.|  
|TABLE_CATALOG|String|제약 조건이 속하는 테이블 이름입니다.|  
|TABLE_SCHEMA|String|해당 테이블을 포함하는 스키마입니다.|  
|TABLE_NAME|String|테이블 이름|  
|CONSTRAINT_TYPE|String|제약 조건의 유형입니다. "FOREIGN KEY"만 허용됩니다.|  
|IS_DEFERRABLE|String|제약 조건의 지연 가능 여부를 지정합니다. NO를 반환합니다.|  
|INITIALLY_DEFERRED|String|제약 조건의 초기 지연 가능 여부를 지정합니다. NO를 반환합니다.|  
  
## <a name="indexes"></a>인덱스  
  
|ColumnName|DataType|설명|  
|----------------|--------------|-----------------|  
|constraint_catalog|String|인덱스가 속하는 카탈로그입니다.|  
|constraint_schema|String|해당 인덱스를 포함하는 스키마입니다.|  
|constraint_name|String|인덱스의 이름입니다.|  
|table_catalog|String|인덱스가 연결되는 테이블 이름입니다.|  
|table_schema|String|인덱스가 연결되는 테이블을 포함하는 스키마입니다.|  
|table_name|String|테이블 이름입니다.|  
|index_name|String|인덱스 이름입니다.|  
  
### <a name="indexes-sql-server-2008"></a>Indexes(SQL Server 2008)  

 .NET Framework 버전 3.5 SP1 및 SQL Server 2008부터는 새로운 공간 유형, 파일 스트림 및 스파스 열을 지원하도록 Indexes 스키마 컬렉션에 다음과 같은 열이 추가되었습니다. 이러한 열은 이전 버전의 .NET Framework 및 SQL Server에서는 지원되지 않습니다.  
  
|ColumnName|DataType|설명|  
|----------------|--------------|-----------------|  
|type_desc|String|인덱스 형식은 다음 중 하나입니다.<br /><br /> -   HEAP<br />-   CLUSTERED<br />-   NONCLUSTERED<br />-   XML<br />-   SPATIAL|  
  
## <a name="indexcolumns"></a>IndexColumns  
  
|ColumnName|DataType|설명|  
|----------------|--------------|-----------------|  
|constraint_catalog|String|인덱스가 속하는 카탈로그입니다.|  
|constraint_schema|String|해당 인덱스를 포함하는 스키마입니다.|  
|constraint_name|String|인덱스의 이름입니다.|  
|table_catalog|String|인덱스가 연결되는 테이블 이름입니다.|  
|table_schema|String|인덱스가 연결되는 테이블을 포함하는 스키마입니다.|  
|table_name|String|테이블 이름입니다.|  
|column_name|String|인덱스가 연결되는 ColumnName입니다.|  
|ordinal_position|Int32|열의 서수 위치입니다.|  
|KeyType|Byte|개체의 형식입니다.|  
|index_name|String|인덱스 이름입니다.|  
  
## <a name="procedures"></a>프로시저  
  
|ColumnName|DataType|설명|  
|----------------|--------------|-----------------|  
|SPECIFIC_CATALOG|String|카탈로그의 특정 이름입니다.|  
|SPECIFIC_SCHEMA|String|스키마의 특정 이름입니다.|  
|SPECIFIC_NAME|String|카탈로그의 특정 이름입니다.|  
|ROUTINE_CATALOG|String|저장 프로시저가 속하는 카탈로그입니다.|  
|ROUTINE_SCHEMA|String|저장 프로시저를 포함하는 스키마입니다.|  
|ROUTINE_NAME|String|저장 프로시저의 이름입니다.|  
|ROUTINE_TYPE|String|저장 프로시저에 대해서는 PROCEDURE를 반환하고 함수에 대해서는 FUNCTION을 반환합니다.|  
|CREATED|DateTime|프로시저가 만들어진 시간입니다.|  
|LAST_ALTERED|DateTime|프로시저가 마지막으로 수정된 시간입니다.|  
  
## <a name="procedure-parameters"></a>프로시저 매개 변수  
  
|ColumnName|DataType|설명|  
|----------------|--------------|-----------------|  
|SPECIFIC_CATALOG|String|이 항목이 매개 변수인 프로시저의 카탈로그 이름입니다.|  
|SPECIFIC_SCHEMA|String|이 매개 변수가 속하는 프로시저가 포함된 스키마입니다.|  
|SPECIFIC_NAME|String|이 매개 변수가 속하는 프로시저의 이름입니다.|  
|ORDINAL_POSITION|Int32|1에서 시작하는 매개 변수의 서수 위치입니다. 프로시저의 반환 값인 경우 0입니다.|  
|PARAMETER_MODE|String|입력 매개 변수인 경우에는 IN, 출력 매개 변수인 경우에는 OUT, 입/출력 매개 변수인 경우에는 INOUT을 반환합니다.|  
|IS_RESULT|String|함수인 프로시저의 결과를 나타내는 경우 YES를 반환합니다. 그렇지 않은 경우에는 NO를 반환합니다.|  
|AS_LOCATOR|String|로케이터로 선언된 경우에는 YES를 반환합니다. 그렇지 않은 경우에는 NO를 반환합니다.|  
|PARAMETER_NAME|String|매개 변수의 이름입니다. 이 이름이 함수의 반환 값에 해당되는 경우에는 NULL이 됩니다.|  
|DATA_TYPE|String|시스템 제공 데이터 형식입니다.|  
|CHARACTER_MAXIMUM_LENGTH|Int32|이진 데이터 형식 또는 문자 데이터 형식의 최대 길이를 문자 단위로 표시한 것입니다. 다른 데이터 형식에 대해서는 NULL을 반환합니다.|  
|CHARACTER_OCTET_LENGTH|Int32|이진 데이터 형식 또는 문자 데이터 형식의 최대 길이를 바이트 단위로 표시한 것입니다. 다른 데이터 형식에 대해서는 NULL을 반환합니다.|  
|COLLATION_CATALOG|String|매개 변수의 데이터 정렬에 대한 카탈로그 이름입니다. 문자 형식 중 하나가 아닌 경우에는 NULL이 반환됩니다.|  
|COLLATION_SCHEMA|String|항상 NULL을 반환합니다.|  
|COLLATION_NAME|String|매개 변수의 데이터 정렬 이름입니다. 문자 형식 중 하나가 아닌 경우에는 NULL이 반환됩니다.|  
|CHARACTER_SET_CATALOG|String|매개 변수의 문자 집합 카탈로그 이름입니다. 문자 형식 중 하나가 아닌 경우에는 NULL이 반환됩니다.|  
|CHARACTER_SET_SCHEMA|String|항상 NULL을 반환합니다.|  
|CHARACTER_SET_NAME|String|매개 변수의 문자 집합 이름입니다. 문자 형식 중 하나가 아닌 경우에는 NULL이 반환됩니다.|  
|NUMERIC_PRECISION|Byte|근사 숫자 데이터, 정확한 숫자 데이터, 정수 데이터 또는 통화 데이터의 전체 자릿수입니다. 다른 데이터 형식에 대해서는 NULL을 반환합니다.|  
|NUMERIC_PRECISION_RADIX|Int16|근사 숫자 데이터, 정확한 숫자 데이터, 정수 데이터 또는 통화 데이터의 전체 자릿수 기수입니다. 다른 데이터 형식에 대해서는 NULL을 반환합니다.|  
|NUMERIC_SCALE|Int32|근사 숫자 데이터, 정확한 숫자 데이터, 정수 데이터 또는 통화 데이터의 소수 자릿수입니다. 다른 데이터 형식에 대해서는 NULL을 반환합니다.|  
|DATETIME_PRECISION|Int16|매개 변수 형식이 datetime 또는 smalldatetime이면 소수로 나타낸 시간(초)의 정밀도입니다. 다른 데이터 형식에 대해서는 NULL을 반환합니다.|  
|INTERVAL_TYPE|String|NULL 나중에 SQL Server에서 사용하도록 예약되었습니다.|  
|INTERVAL_PRECISION|Int16|NULL 나중에 SQL Server에서 사용하도록 예약되었습니다.|  
  
## <a name="tables"></a>테이블  
  
|ColumnName|DataType|Description|  
|----------------|--------------|-----------------|  
|TABLE_CATALOG|String|테이블의 카탈로그입니다.|  
|TABLE_SCHEMA|String|해당 테이블을 포함하는 스키마입니다.|  
|TABLE_NAME|String|테이블 이름입니다.|  
|TABLE_TYPE|String|테이블 유형입니다. VIEW 또는 BASE TABLE이 될 수 있습니다.|  
  
## <a name="columns"></a>열  
  
|ColumnName|DataType|Description|  
|----------------|--------------|-----------------|  
|TABLE_CATALOG|String|테이블의 카탈로그입니다.|  
|TABLE_SCHEMA|String|해당 테이블을 포함하는 스키마입니다.|  
|TABLE_NAME|String|테이블 이름입니다.|  
|COLUMN_NAME|String|열 이름입니다.|  
|ORDINAL_POSITION|Int32|열 ID입니다.|  
|COLUMN_DEFAULT|String|열 기본값입니다.|  
|IS_NULLABLE|String|열의 NULL 허용 여부입니다. 이 열에서 NULL을 허용하는 경우 YES를 반환합니다. 그렇지 않으면 No가 반환됩니다.|  
|DATA_TYPE|String|시스템 제공 데이터 형식입니다.|  
|CHARACTER_MAXIMUM_LENGTH|Int32 - Sql8, Int16 - Sql7|이진 데이터, 문자 데이터 또는 텍스트와 이미지 데이터의 최대 길이(문자)입니다. 다른 데이터 형식에 대해서는 NULL이 반환됩니다.|  
|CHARACTER_OCTET_LENGTH|Int32 - SQL8, Int16 - Sql7|이진 데이터, 문자 데이터 또는 텍스트와 이미지 데이터의 최대 길이(바이트)입니다. 다른 데이터 형식에 대해서는 NULL이 반환됩니다.|  
|NUMERIC_PRECISION|부호 없는 바이트|근사 숫자 데이터, 정확한 숫자 데이터, 정수 데이터 또는 통화 데이터의 전체 자릿수입니다. 다른 데이터 형식에 대해서는 NULL이 반환됩니다.|  
|NUMERIC_PRECISION_RADIX|Int16|근사 숫자 데이터, 정확한 숫자 데이터, 정수 데이터 또는 통화 데이터의 전체 자릿수 기수입니다. 다른 데이터 형식에 대해서는 NULL이 반환됩니다.|  
|NUMERIC_SCALE|Int32|근사 숫자 데이터, 정확한 숫자 데이터, 정수 데이터 또는 통화 데이터의 소수 자릿수입니다. 다른 데이터 형식에 대해서는 NULL이 반환됩니다.|  
|DATETIME_PRECISION|Int16|datetime 및 SQL-92 interval 데이터 형식에 대한 하위 형식 코드입니다. 다른 데이터 형식에 대해서는 NULL이 반환됩니다.|  
|CHARACTER_SET_CATALOG|String|열이 문자 데이터 또는 텍스트 데이터 형식이면 문자 집합이 있는 데이터베이스를 나타내는 master가 반환됩니다. 다른 데이터 형식에 대해서는 NULL이 반환됩니다.|  
|CHARACTER_SET_SCHEMA|String|항상 NULL을 반환합니다.|  
|CHARACTER_SET_NAME|String|이 열이 문자 데이터 또는 텍스트 데이터 형식인 경우 문자 집합에 대해 고유 이름을 반환합니다. 다른 데이터 형식에 대해서는 NULL이 반환됩니다.|  
|COLLATION_CATALOG|String|열이 문자 데이터 또는 텍스트 데이터 형식이면 정렬이 정의된 데이터베이스를 나타내는 master를 반환합니다. 그렇지 않은 경우 이 열은 NULL입니다.|  
  
### <a name="columns-sql-server-2008"></a>Columns(SQL Server 2008)  

 .NET Framework 버전 3.5 SP1 및 SQL Server 2008부터는 새로운 공간 유형, 파일 스트림 및 스파스 열을 지원하도록 Columns 스키마 컬렉션에 다음과 같은 열이 추가되었습니다. 이러한 열은 이전 버전의 .NET Framework 및 SQL Server에서는 지원되지 않습니다.  
  
|ColumnName|DataType|설명|  
|----------------|--------------|-----------------|  
|IS_FILESTREAM|String|열에 FILESTREAM 특성이 있으면 YES입니다.<br /><br /> 열에 FILESTREAM 특성이 없으면 NO입니다.|  
|IS_SPARSE|String|열이 스파스 열이면 YES입니다.<br /><br /> 열이 스파스 열이 아니면 NO입니다.|  
|IS_COLUMN_SET|String|열이 열 집합 열이면 YES입니다.<br /><br /> 열이 열 집합 열이 아니면 NO입니다.|  
  
### <a name="allcolumns-sql-server-2008"></a>AllColumns(SQL Server 2008)  

 .NET Framework 버전 3.5 SP1 및 SQL Server 2008부터는 스파스 열을 지원하도록 AllColumns 스키마 컬렉션이 추가되었습니다. AllColumns는 이전 버전의 .NET Framework 및 SQL Server에서는 지원되지 않습니다.  
  
 AllColumns는 제한 및 결과 DataTable 스키마가 Columns 스키마 컬렉션과 동일합니다. 유일한 차이점은 Columns 스키마 컬렉션에는 포함되어 있지 않은 열 집합 열이 AllColumns에는 있다는 것입니다. 다음 표에서는 이러한 열에 대해 설명합니다.  
  
|ColumnName|DataType|Description|  
|----------------|--------------|-----------------|  
|TABLE_CATALOG|String|테이블의 카탈로그입니다.|  
|TABLE_SCHEMA|String|해당 테이블을 포함하는 스키마입니다.|  
|TABLE_NAME|String|테이블 이름입니다.|  
|COLUMN_NAME|String|열 이름입니다.|  
|ORDINAL_POSITION|Int32|열 ID입니다.|  
|COLUMN_DEFAULT|String|열 기본값입니다.|  
|IS_NULLABLE|String|열의 NULL 허용 여부입니다. 이 열에서 NULL을 허용하는 경우 YES를 반환합니다. 허용하지 않는 경우에는 NO가 반환됩니다.|  
|DATA_TYPE|String|시스템 제공 데이터 형식입니다.|  
|CHARACTER_MAXIMUM_LENGTH|Int32|이진 데이터, 문자 데이터 또는 텍스트와 이미지 데이터의 최대 길이(문자)입니다. 다른 데이터 형식에 대해서는 NULL이 반환됩니다.|  
|CHARACTER_OCTET_LENGTH|Int32|이진 데이터, 문자 데이터 또는 텍스트와 이미지 데이터의 최대 길이(바이트)입니다. 다른 데이터 형식에 대해서는 NULL이 반환됩니다.|  
|NUMERIC_PRECISION|부호 없는 바이트|근사 숫자 데이터, 정확한 숫자 데이터, 정수 데이터 또는 통화 데이터의 전체 자릿수입니다. 다른 데이터 형식에 대해서는 NULL이 반환됩니다.|  
|NUMERIC_PRECISION_RADIX|Int16|근사 숫자 데이터, 정확한 숫자 데이터, 정수 데이터 또는 통화 데이터의 전체 자릿수 기수입니다. 다른 데이터 형식에 대해서는 NULL이 반환됩니다.|  
|NUMERIC_SCALE|Int32|근사 숫자 데이터, 정확한 숫자 데이터, 정수 데이터 또는 통화 데이터의 소수 자릿수입니다. 다른 데이터 형식에 대해서는 NULL이 반환됩니다.|  
|DATETIME_PRECISION|Int16|datetime 및 SQL-92 interval 데이터 형식에 대한 하위 형식 코드입니다. 다른 데이터 형식에 대해서는 NULL이 반환됩니다.|  
|CHARACTER_SET_CATALOG|String|열이 문자 데이터 또는 텍스트 데이터 형식이면 문자 집합이 있는 데이터베이스를 나타내는 master가 반환됩니다. 다른 데이터 형식에 대해서는 NULL이 반환됩니다.|  
|CHARACTER_SET_SCHEMA|String|항상 NULL을 반환합니다.|  
|CHARACTER_SET_NAME|String|이 열이 문자 데이터 또는 텍스트 데이터 형식인 경우 문자 집합에 대해 고유 이름을 반환합니다. 다른 데이터 형식에 대해서는 NULL이 반환됩니다.|  
|COLLATION_CATALOG|String|열이 문자 데이터 또는 텍스트 데이터 형식이면 정렬이 정의된 데이터베이스를 나타내는 master를 반환합니다. 그렇지 않은 경우 이 열은 NULL입니다.|  
|IS_FILESTREAM|String|열에 FILESTREAM 특성이 있으면 YES입니다.<br /><br /> 열에 FILESTREAM 특성이 없으면 NO입니다.|  
|IS_SPARSE|String|열이 스파스 열이면 YES입니다.<br /><br /> 열이 스파스 열이 아니면 NO입니다.|  
|IS_COLUMN_SET|String|열이 열 집합 열이면 YES입니다.<br /><br /> 열이 열 집합 열이 아니면 NO입니다.|  
  
### <a name="columnsetcolumns-sql-server-2008"></a>ColumnSetColumns(SQL Server 2008)  

 .NET Framework 버전 3.5 SP1 및 SQL Server 2008부터는 스파스 열을 지원하도록 ColumnSetColumns 스키마 컬렉션이 추가되었습니다. ColumnSetColumns는 이전 버전의 .NET Framework 및 SQL Server에서는 지원되지 않습니다. ColumnSetColumns 스키마 컬렉션은 열 집합에 포함된 모든 열의 스키마를 반환합니다. 다음 표에서는 이러한 열에 대해 설명합니다.  
  
|ColumnName|DataType|Description|  
|----------------|--------------|-----------------|  
|TABLE_CATALOG|String|테이블의 카탈로그입니다.|  
|TABLE_SCHEMA|String|해당 테이블을 포함하는 스키마입니다.|  
|TABLE_NAME|String|테이블 이름입니다.|  
|COLUMN_NAME|String|열 이름입니다.|  
|ORDINAL_POSITION|Int32|열 ID입니다.|  
|COLUMN_DEFAULT|String|열 기본값입니다.|  
|IS_NULLABLE|String|열의 NULL 허용 여부입니다. 이 열에서 NULL을 허용하는 경우 YES를 반환합니다. 허용하지 않는 경우에는 NO가 반환됩니다.|  
|DATA_TYPE|String|시스템 제공 데이터 형식입니다.|  
|CHARACTER_MAXIMUM_LENGTH|Int32|이진 데이터, 문자 데이터 또는 텍스트와 이미지 데이터의 최대 길이(문자)입니다. 다른 데이터 형식에 대해서는 NULL이 반환됩니다.|  
|CHARACTER_OCTET_LENGTH|Int32|이진 데이터, 문자 데이터 또는 텍스트와 이미지 데이터의 최대 길이(바이트)입니다. 다른 데이터 형식에 대해서는 NULL이 반환됩니다.|  
|NUMERIC_PRECISION|부호 없는 바이트|근사 숫자 데이터, 정확한 숫자 데이터, 정수 데이터 또는 통화 데이터의 전체 자릿수입니다. 다른 데이터 형식에 대해서는 NULL이 반환됩니다.|  
|NUMERIC_PRECISION_RADIX|Int16|근사 숫자 데이터, 정확한 숫자 데이터, 정수 데이터 또는 통화 데이터의 전체 자릿수 기수입니다. 다른 데이터 형식에 대해서는 NULL이 반환됩니다.|  
|NUMERIC_SCALE|Int32|근사 숫자 데이터, 정확한 숫자 데이터, 정수 데이터 또는 통화 데이터의 소수 자릿수입니다. 다른 데이터 형식에 대해서는 NULL이 반환됩니다.|  
|DATETIME_PRECISION|Int16|datetime 및 SQL-92 interval 데이터 형식에 대한 하위 형식 코드입니다. 다른 데이터 형식에 대해서는 NULL이 반환됩니다.|  
|CHARACTER_SET_CATALOG|String|열이 문자 데이터 또는 텍스트 데이터 형식이면 문자 집합이 있는 데이터베이스를 나타내는 master가 반환됩니다. 다른 데이터 형식에 대해서는 NULL이 반환됩니다.|  
|CHARACTER_SET_SCHEMA|String|항상 NULL을 반환합니다.|  
|CHARACTER_SET_NAME|String|이 열이 문자 데이터 또는 텍스트 데이터 형식인 경우 문자 집합에 대해 고유 이름을 반환합니다. 다른 데이터 형식에 대해서는 NULL이 반환됩니다.|  
|COLLATION_CATALOG|String|열이 문자 데이터 또는 텍스트 데이터 형식이면 정렬이 정의된 데이터베이스를 나타내는 master를 반환합니다. 그렇지 않은 경우 이 열은 NULL입니다.|  
|IS_FILESTREAM|String|열에 FILESTREAM 특성이 있으면 YES입니다.<br /><br /> 열에 FILESTREAM 특성이 없으면 NO입니다.|  
|IS_SPARSE|String|열이 스파스 열이면 YES입니다.<br /><br /> 열이 스파스 열이 아니면 NO입니다.|  
|IS_COLUMN_SET|String|열이 열 집합 열이면 YES입니다.<br /><br /> 열이 열 집합 열이 아니면 NO입니다.|  
  
## <a name="users"></a>사용자  
  
|ColumnName|DataType|설명|  
|----------------|--------------|-----------------|  
|uid|Int16|해당 데이터베이스에서 고유한 사용자 ID입니다. 데이터베이스 소유자는 1입니다.|  
|사용자_이름|String|이 데이터베이스에 고유한 사용자 이름 및 그룹 이름입니다.|  
|createdate|DateTime|계정이 추가된 날짜입니다.|  
|updatedate|DateTime|계정을 마지막으로 변경한 날짜입니다.|  
  
## <a name="views"></a>보기  
  
|ColumnName|DataType|Description|  
|----------------|--------------|-----------------|  
|TABLE_CATALOG|String|뷰의 카탈로그입니다.|  
|TABLE_SCHEMA|String|해당 뷰를 포함하는 스키마입니다.|  
|TABLE_NAME|String|뷰 이름입니다.|  
|CHECK_OPTION|String|WITH CHECK OPTION의 유형입니다. 원래 뷰를 WITH CHECK OPTION을 사용하여 만든 경우 Is CASCADE입니다. 그렇지 않으면 NONE이 반환됩니다.|  
|IS_UPDATABLE|String|뷰를 업데이트할 수 있는지 여부를 지정합니다. 항상 NO를 반환합니다.|  
  
## <a name="viewcolumns"></a>ViewColumns  
  
|ColumnName|DataType|Description|  
|----------------|--------------|-----------------|  
|VIEW_CATALOG|String|뷰의 카탈로그입니다.|  
|VIEW_SCHEMA|String|해당 뷰를 포함하는 스키마입니다.|  
|VIEW_NAME|String|뷰 이름입니다.|  
|TABLE_CATALOG|String|이 뷰와 연관된 테이블의 카탈로그입니다.|  
|TABLE_SCHEMA|String|이 뷰와 연관된 테이블을 포함하는 스키마입니다.|  
|TABLE_NAME|String|뷰와 연관된 테이블의 이름입니다. 기본 테이블입니다.|  
|COLUMN_NAME|String|열 이름입니다.|  
  
## <a name="userdefinedtypes"></a>UserDefinedTypes  
  
|ColumnName|DataType|설명|  
|----------------|--------------|-----------------|  
|assembly_name|String|어셈블리의 파일 이름입니다.|  
|udt_name|String|어셈블리의 클래스 이름입니다.|  
|version_major|Object|주 버전 번호입니다.|  
|version_minor|Object|보조 버전 번호입니다.|  
|version_build|Object|빌드 번호입니다.|  
|version_revision|Object|수정 번호입니다.|  
|culture_info|Object|이 UDT와 연관된 문화권 정보입니다.|  
|public_key|Object|이 어셈블리에서 사용되는 공개 키입니다.|  
|is_fixed_length|부울|형식 길이가 항상 max_length와 같은지 여부를 지정합니다.|  
|max_length|Int16|형식의 최대 길이(바이트)입니다.|  
|Create_Date|DateTime|어셈블리가 만들어져 등록된 날짜입니다.|  
|Permission_set_desc|String|어셈블리의 권한 집합/보안 수준 이름입니다.|  
  
## <a name="see-also"></a>참조

- [데이터베이스 스키마 정보 검색](retrieving-database-schema-information.md)
- [ADO.NET 개요](ado-net-overview.md)
