---
description: SQL Server Compact 및 LINQ to SQL에 대해 자세히 알아보세요.
title: SQL Server Compact 및 LINQ to SQL
ms.date: 03/30/2017
ms.assetid: 59022359-a5a2-4c42-9a6a-5c0259c3ad17
ms.openlocfilehash: ae7965db1685d7682b643662df8fb1c1376a7154
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99803713"
---
# <a name="sql-server-compact-and-linq-to-sql"></a>SQL Server Compact 및 LINQ to SQL

SQL Server Compact는 Visual Studio와 함께 설치 되는 기본 데이터베이스입니다. 자세한 내용은 [SQL Server Compact 사용 (Visual Studio)](/previous-versions/visualstudio/visual-studio-2012/aa983321(v=vs.110))을 참조 하세요.  
  
 이 항목에서는 사용, 구성, 기능 집합 및 지원 범위의 주요 차이점에 대해 간략하게 설명 합니다 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] .  
  
## <a name="characteristics-of-sql-server-compact-in-relation-to-linq-to-sql"></a>LINQ to SQL과 관련된 SQL Server Compact의 특성  

 기본적으로 SQL Server Compact는 모든 Visual Studio 버전에 대해 설치 되므로에서 사용할 수 있도록 개발 컴퓨터에서 사용할 수 있습니다 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] . 그러나 SQL Server Compact를 사용 하는 응용 프로그램의 배포는 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] SQL Server 응용 프로그램의 경우와 다릅니다. SQL Server Compact는 .NET Framework의 일부가 아니므로 애플리케이션과 함께 패키지하거나 Microsoft 사이트에서 별도로 다운로드해야 합니다.  
  
 다음 특성에 주의합니다.  
  
- SQL Server Compact는 데이터베이스 파일(.sdf 확장명)에 대해 직접 사용할 수 있는 DLL로 패키지됩니다.  
  
- SQL Server Compact는 클라이언트 응용 프로그램과 동일한 프로세스에서 실행됩니다. 따라서 SQL Server Compact과의 통신 효율성이 SQL Server와의 통신 보다 훨씬 더 높을 수 있습니다. 반면, SQL Server Compact에서는 관리 코드와 비관리 코드 간에 상호 운용성이 요구되므로 부수적인 비용이 발생합니다.  
  
- SQL Server Compact DLL의 크기가 너무 작습니다. 이로 인해 전체 애플리케이션 크기가 줄어듭니다.  
  
- [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] 런타임 및 SQLMetal 명령줄 도구에서 SQL Server Compact를 지원합니다.  
  
- 개체 관계형 디자이너에서 SQL Server Compact를 지원 하지 않습니다.  
  
## <a name="feature-set"></a>기능 집합  

 SQL Server Compact 기능 집합은 응용 프로그램에 영향을 줄 수 있는 다음과 같은 방법으로 SQL Server 기능 집합 보다 훨씬 더 간단 합니다 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] .  
  
- SQL Server Compact에서는 저장 프로시저나 뷰를 지원하지 않습니다.  
  
- SQL Server Compact에서는 데이터 형식 및 SQL 함수의 하위 집합만 지원합니다.  
  
- SQL Server Compact에서는 SQL 구문의 하위 집합만 지원합니다.  
  
- SQL Server Compact에서는 최소한의 최적화 프로그램을 제공하므로 일부 쿼리의 시간이 초과될 수 있습니다.  
  
- SQL Server Compact는 부분 신뢰를 지원하지 않습니다.  
  
## <a name="see-also"></a>참고 항목

- [참조](reference.md)
