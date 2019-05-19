---
title: ADO.NET에서 Side-by-Side 실행
ms.date: 03/30/2017
ms.assetid: 9f9ba96d-9f89-4f65-bb2f-6860879f4393
ms.openlocfilehash: d20d8e81d76284509d6fe733e4f283a9ab39cb00
ms.sourcegitcommit: c4e9d05644c9cb89de5ce6002723de107ea2e2c4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/19/2019
ms.locfileid: "65877087"
---
# <a name="side-by-side-execution-in-adonet"></a>ADO.NET에서 Side-by-Side 실행
.NET Framework의 side-by-side-실행 응용 프로그램 컴파일된 버전을 사용 하 여 설치 하는.NET Framework의 여러 버전이 있는지 확인 하는 컴퓨터에서 응용 프로그램을 실행할 수 있다는 점입니다. Side-by-side-실행을 구성 하는 방법에 대 한 자세한 내용은 참조 하세요. [Side-by-side-실행](../../../../docs/framework/deployment/side-by-side-execution.md)합니다.  
  
 한 버전의.NET Framework를 사용 하 여 컴파일된 응용 프로그램을 다른 버전의.NET Framework에서 실행할 수 있습니다. 그러나.NET Framework의 설치 된 각 버전에 대 한 응용 프로그램의 버전을 컴파일할 개별적으로 실행 하는 것이 좋습니다. 두 시나리오에서 ADO.NET 응용 프로그램의 이전 버전과 호환성을 이후 버전과 호환성에 영향을 줄 수 있는 릴리스 간의 변경 내용을 파악 해야 합니다.  
  
## <a name="forward-compatibility-and-backward-compatibility"></a>다음 버전 및 이전 버전과의 호환성  
 이후 버전과 호환성 응용 프로그램 이전 버전의.NET Framework를 사용 하 여 컴파일할 수 있는.NET Framework의 이후 버전에서 성공적으로 계속 실행 됩니다 않았음을 의미 합니다. .NET Framework 버전 1.1 용으로 작성 하는 ADO.NET 코드는 이후 버전과 호환입니다.  
  
 이전 버전과 호환성 응용 프로그램을 최신 버전의.NET Framework에 대해 컴파일되는 이전 버전의 기능 손실 없이.NET Framework에서 계속 실행 않았음을 의미 합니다. 물론, 새 버전의.NET Framework에 도입 된 기능에 대 한 사례 되지 않습니다.  
  
## <a name="the-net-framework-data-provider-for-odbc"></a>.NET Framework Data Provider for ODBC  
 버전 1.1에서.NET Framework Data Provider for ODBC 사용 하 여 시작 (<xref:System.Data.Odbc>).NET Framework의 일부로 포함 됩니다. ODBC 데이터 공급자가 사용할 수 있는.NET Framework 버전 1.0 개발자 웹 사이트에서 다운로드할 합니다 [Data Access and Storage Developer Center](https://go.microsoft.com/fwlink/?linkid=4173)합니다. 다운로드 한.NET Framework Data Provider for ODBC에 대 한 네임 스페이스가 **Microsoft.Data.Odbc**합니다.  
  
 ODBC 날짜에 대 한 네임 스페이스를 업데이트 해야.NET Framework 버전 1.0 데이터 원본에 연결 하려면 ODBC 데이터 공급자를 사용 하는 개발 된 응용 프로그램이 있고.NET Framework 버전 1.1 이상 버전에서 해당 응용 프로그램을 실행 하려는 경우 공급자를 **System.Data.Odbc**합니다. 그런 다음 다시 컴파일해야 해당.NET Framework의 최신 버전에 대 한 합니다.  
  
 ODBC 데이터 공급자를 다운로드 하 고 설치 해야 데이터 원본에 연결 하려면 ODBC 데이터 공급자를 사용 하는.NET Framework 버전 2.0 이상이 개발 된 응용 프로그램이 있고.NET Framework 버전 1.0에서 해당 응용 프로그램을 실행 하려는 경우 .NET Framework 버전 1.0 시스템입니다. 그런 다음 ODBC 데이터 공급자에 대 한 네임 스페이스를 변경 해야 합니다 **Microsoft.Data.Odbc**,.NET Framework 버전 1.0에 대 한 응용 프로그램을 다시 컴파일해야 합니다.  
  
## <a name="the-net-framework-data-provider-for-oracle"></a>.NET Framework Data Provider for Oracle  
 버전 1.1에서.NET Framework Data Provider for Oracle 사용 하 여 시작 (<xref:System.Data.OracleClient>).NET Framework의 일부로 포함 됩니다. 데이터 공급자가 사용할 수 있는.NET Framework 버전 1.0 개발자 웹 사이트에서 다운로드할 합니다 [Data Access and Storage Developer Center](https://go.microsoft.com/fwlink/?linkid=4173)합니다.  
  
 데이터 공급자를 다운로드 하 고는.NE에 설치 해야 데이터 원본에 연결할 데이터 공급자를 사용 하는.NET Framework 버전 2.0 이상이 개발 된 응용 프로그램이 있고.NET Framework 버전 1.0에서 해당 응용 프로그램을 실행 하려는 경우 T Framework 버전 1.0 시스템입니다.  
  
## <a name="code-access-security"></a>코드 액세스 보안  
 .NET Framework 버전 1.0에서에서.NET Framework 데이터 공급자 (<xref:System.Data.SqlClient>, <xref:System.Data.OleDb>)는 FullTrust 권한으로 실행 해야 합니다. FullTrust 권한 하면 더 적은 노력으로 영역에는.NET Framework 버전 1.0의.NET Framework 데이터 공급자를 사용 하려는 모든 시도 <xref:System.Security.SecurityException>합니다.  
  
 그러나.NET Framework 버전 2.0 부터는.NET Framework 데이터 공급자의 모든 사용할 수 있습니다 부분적으로 신뢰할 수 있는 영역에서. 또한.NET Framework 버전 1.1에서에서.NET Framework 데이터 공급자에 새로운 보안 기능이 추가 되었습니다. 이 기능으로 특정 보안 영역에서 사용할 수 있는 연결 문자열을 제한할 수 있습니다. 뿐만 아니라 특정 보안 영역에 대해 빈 암호 사용을 비활성화할 수도 있습니다. 자세한 내용은 [Code Access Security and ADO.NET](../../../../docs/framework/data/adonet/code-access-security.md)을 참조하세요.  
  
 .NET Framework의 각 설치에 별도 Security.config 파일에 있으므로는 보안 설정 사용 하 여 호환성 문제가 없습니다. 그러나.NET Framework 버전 1.1에에서 포함 된 이상 ADO.NET의 추가 보안 기능에 따라 응용 프로그램 버전 1.0 시스템에 배포할 수 없습니다.  
  
## <a name="sqlcommand-execution"></a>SqlCommand 실행  
 서.NET Framework 버전 1.1부터는 <xref:System.Data.SqlClient.SqlCommand.ExecuteReader%2A> 명령을 실행 하는 데이터 원본 변경 되었습니다.  
  
 .NET framework 버전 1.0 <xref:System.Data.SqlClient.SqlCommand.ExecuteReader%2A> 의 컨텍스트에서 모든 명령을 실행 합니다 **sp_executesql** 저장 프로시저입니다. 따라서 연결 상태에 영향을 주는 SET NOCOUNT ON과 같은 명령은 현재 명령의 실행에만 적용됩니다. 연결 상태는 연결이 열려 있는 동안 실행되는 모든 후속 명령에 대해 수정되지 않습니다.  
  
 .NET framework 버전 1.1 이상 <xref:System.Data.SqlClient.SqlCommand.ExecuteReader%2A> 의 컨텍스트에서 명령을 실행 합니다 **sp_executesql** 명령 매개 변수를 포함 하면 성능상 이점이 있는 경우 저장 프로시저입니다. 따라서 연결 상태에 영향을 주는 명령이 매개 변수가 없는 명령에 포함된 경우 연결이 열려 있는 동안 실행되는 모든 후속 명령의 연결 상태가 수정됩니다.  
  
 <xref:System.Data.SqlClient.SqlCommand.ExecuteReader%2A> 호출에서 다음 배치 명령을 실행할 수 있습니다.  
  
```sql
SET NOCOUNT ON;  
SELECT * FROM dbo.Customers;  
```  
  
 .NET Framework 버전 1.1 이상에서 NOCOUNT ON 연결이 열려 있는 동안 실행 되는 모든 후속 명령에 대 한 유지 됩니다. .NET framework 버전 1.0에서 NOCOUNT가 on만으로 현재 명령 실행 합니다.  
  
 동작에 의존 하는 경우이 변경의 응용 프로그램 및 이전 버전과 호환성 영향을 줄 수 <xref:System.Data.SqlClient.SqlCommand.ExecuteReader%2A> .NET Framework의 버전에 대 한 합니다.  
  
 .NET Framework의 이전 및 이후 버전에서 실행 되는 응용 프로그램의 경우 반드시 동작에서 실행 중인 버전에 관계 없이 동일 하도록 코드를 작성할 수 있습니다. 명령을 통해 모든 후속 명령에 대한 연결 상태가 수정되도록 하려면 <xref:System.Data.SqlClient.SqlCommand.ExecuteNonQuery%2A>를 사용하여 명령을 실행하는 것이 좋습니다. 명령을 통해 모든 후속 명령에 대한 연결이 수정되지 않도록 하려면 명령에 연결 상태를 다시 설정하는 명령을 포함하는 것이 좋습니다. 예를 들어:  
  
```sql
SET NOCOUNT ON;  
SELECT * FROM dbo.Customers;  
SET NOCOUNT OFF;  
```  
  
## <a name="see-also"></a>참고자료

- [ADO.NET 개요](../../../../docs/framework/data/adonet/ado-net-overview.md)
- [ADO.NET에서 데이터 검색 및 수정](../../../../docs/framework/data/adonet/retrieving-and-modifying-data.md)
- [ADO.NET 관리되는 공급자 및 데이터 집합 개발자 센터](https://go.microsoft.com/fwlink/?LinkId=217917)
