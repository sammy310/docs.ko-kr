---
title: SQL 생성
ms.date: 03/30/2017
ms.assetid: 0e16aa02-d458-4418-a765-58b42aad9315
ms.openlocfilehash: 2c18e88967fcba2b8414bfc171412eba908002b3
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/04/2019
ms.locfileid: "70248409"
---
# <a name="sql-generation"></a>SQL 생성
[!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)]의 공급자를 작성할 때 [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] 명령 트리를 특정 데이터베이스가 이해할 수 있는 SQL(예: SQL Server의 경우 Transact-SQL, Oracle의 경우 PL/SQL)로 변환해야 합니다. 이 단원에서는 [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] 공급자에 대한 SQL 생성 구성 요소(SELECT 쿼리의 경우)를 개발하는 방법을 살펴봅니다. Insert, update 및 delete 쿼리에 대 한 자세한 내용은 [수정 SQL 생성](modification-sql-generation.md)을 참조 하십시오.  
  
 이 단원을 이해하려면 [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] 및 ADO.NET 공급자 모델에 대해 잘 알고 있어야 합니다. 또한 명령 트리와 <xref:System.Data.Common.CommandTrees.DbExpression>도 이해해야 합니다.  
  
## <a name="the-role-of-the-sql-generation-module"></a>SQL 생성 모듈의 역할  
 [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] 공급자의 SQL 생성 모듈은 지정된 쿼리 명령 트리를 SQL:1999 규격 데이터베이스를 대상으로 하는 단일 SQL SELECT 문으로 변환합니다. 생성된 SQL에는 중첩 쿼리가 가능한 한 적게 포함되어야 합니다. SQL 생성 모듈은 출력 쿼리 명령 트리를 단순화하지 않아야 합니다. [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)]는 조인을 제거하고 연속 필터 노드를 축소하는 등의 작업을 통해 이를 수행합니다.  
  
 <xref:System.Data.Common.DbProviderServices> 클래스는 <xref:System.Data.Common.DbCommand>로 명령 트리를 변환하기 위해 SQL 생성 계층에 액세스할 수 있는 시작점입니다.  
  
## <a name="in-this-section"></a>섹션 내용  
 [명령 트리의 모양](the-shape-of-the-command-trees.md)  
  
 [명령 트리에서 SQL 생성 - 최선의 방법](generating-sql-from-command-trees-best-practices.md)  
  
 [샘플 공급자의 SQL 생성](sql-generation-in-the-sample-provider.md)  
  
## <a name="see-also"></a>참고자료

- [Entity Framework 데이터 공급자 작성](writing-an-ef-data-provider.md)
