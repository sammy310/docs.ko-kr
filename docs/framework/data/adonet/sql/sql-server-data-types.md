---
title: SQL Server 데이터 형식 및 ADO.NET
titleSuffix: ''
ms.date: 03/30/2017
ms.assetid: 81b43550-23e8-43bb-b460-7eb8ac825c33
ms.openlocfilehash: db4618ac624ea8401cab682a8c21d8f23c253d05
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/24/2020
ms.locfileid: "91155460"
---
# <a name="sql-server-data-types-and-adonet"></a>SQL Server 데이터 형식 및 ADO.NET

SQL Server와 .NET Framework는 서로 다른 형식 시스템을 기반으로 하기 때문에 데이터가 손실될 가능성이 있습니다. .NET Framework Data Provider for SQL Server(<xref:System.Data.SqlClient>)에서는 데이터 무결성을 유지하기 위해 SQL Server 데이터로 작업할 때 형식화된 접근자 메서드를 제공합니다. 사용자는 <xref:System.Data.SqlDbType> 클래스의 열거형을 사용하여 <xref:System.Data.SqlClient.SqlParameter> 데이터 형식을 지정할 수 있습니다.  
  
 SQL Server와 .NET Framework 데이터 형식 간의 데이터 형식 매핑을 설명 하는 테이블 및 자세한 내용은 [SQL Server 데이터 형식 매핑](../sql-server-data-type-mappings.md)을 참조 하세요.  
  
 SQL Server 2008에서는 날짜 및 시간, 구조화, 반구조화, 비구조화 데이터를 사용해야 할 비즈니스 요구 사항에 맞게 설계된 새로운 데이터 형식을 소개합니다. 이 내용은 SQL Server 2008 온라인 설명서에 문서화되어 있습니다.  
  
 애플리케이션에서 사용할 수 있는 SQL Server 데이터 형식은 사용 중인 SQL Server의 버전에 따라 달라집니다. 자세한 내용은 다음 표에서 해당되는 SQL Server 온라인 설명서 버전을 참조하세요.  
  
 **SQL Server 설명서**  
  
1. [데이터 형식(Transact-SQL)](/sql/t-sql/data-types/data-types-transact-sql)  
  
## <a name="in-this-section"></a>섹션 내용  

 [SqlType 및 DataSet](sqltypes-and-the-dataset.md)  
 `DataSet`의 `SqlTypes`에 대한 형식 지원에 대해 설명합니다.  
  
 [Null 값 처리](handling-null-values.md)  
 null 값과 값이 세 개인 논리로 작업하는 방법에 대해 설명합니다.  
  
 [GUID 및 uniqueidentifier 값 비교](comparing-guid-and-uniqueidentifier-values.md)  
 SQL Server 및 .NET Framework에서 GUID 및 uniqueidentifier 값으로 작업하는 방법을 보여 줍니다.  
  
 [날짜 및 시간 데이터](date-and-time-data.md)  
 SQL Server 2008에서 도입된 새 날짜 및 시간 데이터 형식을 사용하는 방법을 설명합니다.  
  
 [큰 UDT](large-udts.md)  
 SQL Server 2008에 도입된 큰 값의 UDT에서 데이터를 검색하는 방법을 보여 줍니다.  
  
 [SQL Server의 XML 데이터](xml-data-in-sql-server.md)  
 SQL Server에서 검색된 XML 데이터를 사용하는 방법을 설명합니다.  
  
## <a name="reference"></a>참조  

 <xref:System.Data.DataSet>  
 `DataSet` 클래스와 모든 해당 멤버에 대해 설명합니다.  
  
 <xref:System.Data.SqlTypes>  
 `SqlTypes` 네임스페이스와 모든 해당 멤버에 대해 설명합니다.  
  
 <xref:System.Data.SqlDbType>  
 `SqlDbType` 열거형과 모든 해당 멤버에 대해 설명합니다.  
  
 <xref:System.Data.DbType>  
 `DbType` 열거형과 모든 해당 멤버에 대해 설명합니다.  
  
## <a name="see-also"></a>참고 항목

- [SQL Server 데이터 형식 매핑](../sql-server-data-type-mappings.md)
- [매개 변수 및 매개 변수 데이터 형식 구성](../configuring-parameters-and-parameter-data-types.md)
- [테이블 반환 매개 변수](table-valued-parameters.md)
- [이진 및 대량 값 데이터 SQL Server](sql-server-binary-and-large-value-data.md)
- [ADO.NET 개요](../ado-net-overview.md)
