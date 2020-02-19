---
title: SQL Server 공용 언어 런타임 통합
ms.date: 03/30/2017
ms.assetid: c7a324c4-160d-44c2-b593-641af06eca61
ms.openlocfilehash: 12ae15d72644e314aa694f8d169bc8f45fa284a2
ms.sourcegitcommit: 700ea803fb06c5ce98de017c7f76463ba33ff4a9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/19/2020
ms.locfileid: "77452346"
---
# <a name="sql-server-common-language-runtime-integration"></a>SQL Server 공용 언어 런타임 통합
SQL Server 2005에는 .NET Framework for Microsoft Windows의 CLR(공용 언어 런타임) 구성 요소가 통합되어 있습니다. 따라서 Microsoft Visual Basic .NET 및 Microsoft Visual C#을 비롯하여 모든 .NET Framework 언어를 사용하여 저장 프로시저, 트리거, 사용자 정의 형식, 사용자 정의 함수, 사용자 정의 집계 및 스트리밍 테이블 반환 함수를 작성할 수 있습니다. <xref:Microsoft.SqlServer.Server> 네임스페이스에는 관리 코드에서 Microsoft SQL Server 환경과 상호 작용할 수 있도록 하는 새로운 API(응용 프로그래밍 인터페이스) 집합이 들어 있습니다.  
  
 이 단원에서는 SQL Server CLR(공용 언어 런타임) 통합 및 ADO.NET에 대한 SQL Server in-process 고유의 확장과 관련된 기능 및 동작에 대해 설명합니다.  
  
 이 단원은 SQL Server CLR 통합으로 프로그래밍을 시작하는 데 필요한 정보만 제공하며 모든 정보를 포괄적으로 다루지는 않습니다. 자세한 내용을 보려면 현재 사용하고 있는 SQL Server 버전에 해당하는 SQL Server 온라인 설명서 버전을 참조하세요.  
  
 **SQL Server 설명서**  
  
1. [CLR(공용 언어 런타임) 통합 프로그래밍 개요](/sql/relational-databases/clr-integration/common-language-runtime-clr-integration-programming-concepts)  
  
## <a name="in-this-section"></a>섹션 내용  
 [SQL Server CLR 통합 소개](introduction-to-sql-server-clr-integration.md)  
 SQL Server CLR 통합에 대해 소개합니다. 또한 추가 항목에 대한 링크도 제공합니다.  
  
 [CLR 사용자 정의 함수](clr-user-defined-functions.md)  
 테이블 반환 함수, 스칼라 함수, 사용자 정의 집계 함수 등 여러 가지 종류의 CLR 함수를 구현하고 사용하는 방법에 대해 설명합니다.  
  
 [CLR 사용자 정의 형식](clr-user-defined-types.md)  
 CLR 사용자 정의 형식을 구현하고 사용하는 방법에 대해 설명합니다. 또한 추가 항목에 대한 링크도 제공합니다.  
  
 [CLR 저장 프로시저](clr-stored-procedures.md)  
 CLR 저장 프로시저를 구현하고 사용하는 방법에 대해 설명합니다. 또한 추가 항목에 대한 링크도 제공합니다.  
  
 [CLR 트리거](clr-triggers.md)  
 CLR 트리거를 구현하고 사용하는 방법에 대해 설명합니다. 또한 추가 항목에 대한 링크도 제공합니다.  
  
 [컨텍스트 연결](the-context-connection.md)  
 컨텍스트 연결에 대해 설명합니다.  
  
 [ADO.NET의 SQL Server In-Process별 동작](sql-server-in-process-specific-behavior-of-adonet.md)  
 ADO.NET에 대한 SQL Server in-process 고유의 확장명 및 컨텍스트 연결에 대해 설명합니다. 또한 추가 항목에 대한 링크도 제공합니다.  
  
## <a name="see-also"></a>참고 항목

- [SQL Server 및 ADO.NET](index.md)
- [ADO.NET 개요](../ado-net-overview.md)
