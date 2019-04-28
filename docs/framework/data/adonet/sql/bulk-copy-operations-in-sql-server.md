---
title: SQL Server에서 대량 복사 작업
ms.date: 03/30/2017
ms.assetid: 83a7a0d2-8018-4354-97b9-0b1d99f8342b
ms.openlocfilehash: 086b3b997cf0915be7cfa603a651eb412d52e985
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61878646"
---
# <a name="bulk-copy-operations-in-sql-server"></a>SQL Server에서 대량 복사 작업
Microsoft SQL Server 명명 된 인기 있는 명령줄 유틸리티를 포함 **bcp** 에 대 한 신속 하 게 대량으로 SQL Server 데이터베이스의 테이블이 나 뷰로 큰 파일을 복사 합니다. <xref:System.Data.SqlClient.SqlBulkCopy> 클래스를 사용하면 이와 유사한 기능을 제공하는 관리 코드 솔루션을 작성할 수 있습니다. INSERT 문 같은 다른 방법으로도 SQL Server 테이블에 데이터를 로드할 수 있지만 <xref:System.Data.SqlClient.SqlBulkCopy>는 다른 방법에 비해 성능이 크게 뛰어납니다.  
  
 <xref:System.Data.SqlClient.SqlBulkCopy> 클래스를 사용하면 SQL Server 테이블에만 데이터를 쓸 수 있습니다. 그러나 데이터 소스가 SQL Server로 제한되어 있지 않으므로 데이터를 <xref:System.Data.DataTable> 인스턴스로 로드하거나 <xref:System.Data.IDataReader> 인스턴스를 사용하여 읽을 수 있으면 모든 데이터 소스를 사용할 수 있습니다.  
  
 <xref:System.Data.SqlClient.SqlBulkCopy> 클래스를 사용하면 다음을 수행할 수 있습니다.  
  
- 단일 대량 복사 작업  
  
- 여러 대량 복사 작업  
  
- 트랜잭션 내에서의 대량 복사 작업  
  
> [!NOTE]
>  .NET Framework 1.1 또는 이전 버전을 사용 하는 경우 (지원 하지 않는 합니다 <xref:System.Data.SqlClient.SqlBulkCopy> 클래스), SQL Server TRANSACT-SQL을 실행할 수 있습니다 **BULK INSERT** 문을 사용 하 여는 <xref:System.Data.SqlClient.SqlCommand> 개체입니다.  
  
## <a name="in-this-section"></a>섹션 내용  
 [대량 복사 예제 설정](../../../../../docs/framework/data/adonet/sql/bulk-copy-example-setup.md)  
 대량 복사 예제에 사용된 테이블에 대해 설명하고 AdventureWorks 데이터베이스에 테이블을 만들기 위한 SQL 스크립트를 제공합니다.  
  
 [단일 대량 복사 작업](../../../../../docs/framework/data/adonet/sql/single-bulk-copy-operations.md)  
 <xref:System.Data.SqlClient.SqlBulkCopy> 클래스를 사용하여 SQL Server 인스턴스에서 데이터의 단일 대량 복사 작업을 수행하는 방법과 Transact-SQL 문과 <xref:System.Data.SqlClient.SqlCommand> 클래스를 사용하여 대량 복사 작업을 수행하는 방법을 설명합니다.  
  
 [여러 개의 대량 복사 작업](../../../../../docs/framework/data/adonet/sql/multiple-bulk-copy-operations.md)  
 <xref:System.Data.SqlClient.SqlBulkCopy> 클래스를 사용하여 SQL Server 인스턴스에서 데이터의 여러 대량 복사 작업을 수행하는 방법을 설명합니다.  
  
 [트랜잭션 및 대량 복사 작업](../../../../../docs/framework/data/adonet/sql/transaction-and-bulk-copy-operations.md)  
 트랜잭션 내에서 대량 복사 작업을 수행하는 방법과 트랜잭션을 커밋하거나 롤백하는 방법을 설명합니다.  
  
## <a name="see-also"></a>참고자료

- [SQL Server 및 ADO.NET](../../../../../docs/framework/data/adonet/sql/index.md)
- [ADO.NET 관리되는 공급자 및 데이터 집합 개발자 센터](https://go.microsoft.com/fwlink/?LinkId=217917)
