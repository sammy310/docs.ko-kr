---
title: Oracle BFILE
ms.date: 03/30/2017
ms.assetid: 341bbf84-4734-4d44-8723-ccedee954e21
ms.openlocfilehash: 40060a7ea8576e08140d972072d086606d640366
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79149442"
---
# <a name="oracle-bfiles"></a>Oracle BFILE
.NET Framework Data Provider for Oracle에는 Oracle <xref:System.Data.OracleClient.OracleBFile> 데이터 형식 작업에 사용되는 <xref:System.Data.OracleClient.OracleType.BFile> 클래스가 포함되어 있습니다.  
  
 Oracle **BFILE** 데이터 형식은 최대 크기 4기가바이트의 이진 데이터에 대한 참조를 포함하는 Oracle **LOB** 데이터 유형입니다. Oracle **BFILE은** 데이터가 서버가 아닌 운영 체제의 실제 파일에 저장된다는 점에서 다른 Oracle **LOB** 데이터 형식과 다릅니다. **BFILE** 데이터 형식은 데이터에 대한 읽기 전용 액세스를 제공합니다.  
  
 **LOB** 데이터 형식과 구별되는 **BFILE** 데이터 형식의 다른 특성은 다음과 같습니다.  
  
- 구조화되지 않은 데이터를 포함합니다.  
  
- 서버 측 청크를 지원합니다.  
  
- 참조 복사 의미 체계를 사용합니다. 예를 들어 **BFILE에서**복사 작업을 수행하는 경우 **BFILE** 로케이터(파일에 대한 참조)만 복사됩니다. 파일의 데이터는 복사되지 않습니다.  
  
 **BFILE** 데이터 형식은 크기가 크므로 데이터베이스에 저장하는 것이 실용적이지 않은 LOB를 참조하는 데 사용해야 합니다. **LOB** 데이터 형식과 비교하여 **BFILE** 데이터 형식을 사용할 때 더 많은 클라이언트, 서버 및 통신 오버헤드가 관련됩니다. 소량의 데이터만 가져와야 하는 경우 **BFILE에** 액세스하는 것이 더 효율적입니다. 반면에 전체 개체를 가져와야 하는 경우에는 데이터베이스 상주 LOB에 액세스 하는 것이 효율적입니다.  
  
 NULL이 아닌 각 **개체는** 기본 물리적 파일의 위치를 정의하는 두 엔터티와 연결됩니다.  
  
1. 오라클 디렉터리 개체( 파일 시스템의 디렉터리에 대한 데이터베이스 별칭) 및  
  
2. DIRECTORY 개체와 연결된 디렉터리에 있는 기본 물리적 파일의 파일 이름입니다.  
  
## <a name="example"></a>예제  
 다음 C# 예제에서는 Oracle 테이블에서 **BFILE을** 만든 다음 **OracleBFile** 개체의 형태로 검색하는 방법을 보여 줍니다. 이 예제에서는 <xref:System.Data.OracleClient.OracleDataReader> 개체 및 **OracleBFile** **검색** 및 **읽기** 메서드를 사용 하 여 보여 줍니다. 이 샘플을 사용하려면 먼저 Oracle 서버에서 "c:\\\bfiles"라는 디렉터리와 "MyFile.jpg"라는 파일을 만들어야 합니다.  
  
```csharp  
using System;  
using System.IO;  
using System.Data;  
using System.Data.OracleClient;  
  
public class Sample  
{  
   public static void Main(string[] args)  
   {  
      OracleConnection connection = new OracleConnection(  
        "Data Source=Oracle8i;Integrated Security=yes");  
      connection.Open();  
  
      OracleCommand command = connection.CreateCommand();  
      command.CommandText =
        "CREATE or REPLACE DIRECTORY MyDir as 'c:\\bfiles'";  
      command.ExecuteNonQuery();  
      command.CommandText =
        "DROP TABLE MyBFileTable";  
      try {  
        command.ExecuteNonQuery();  
      }  
      catch {  
      }  
      command.CommandText =
        "CREATE TABLE MyBFileTable(col1 number, col2 BFILE)";  
      command.ExecuteNonQuery();  
      command.CommandText =
        "INSERT INTO MyBFileTable values ('2', BFILENAME('MyDir', " +  
        "'MyFile.jpg'))";  
      command.ExecuteNonQuery();  
      command.CommandText = "SELECT * FROM MyBFileTable";  
  
        byte[] buffer = new byte[100];  
  
      OracleDataReader reader = command.ExecuteReader();  
      using (reader) {  
          if (reader.Read()) {  
                OracleBFile bFile = reader.GetOracleBFile(1);  
                using (bFile) {  
                  bFile.Seek(0, SeekOrigin.Begin);  
                  bFile.Read(buffer, 0, 100);  
              }  
          }  
      }  
  
      connection.Close();  
   }  
  
}  
```  
  
## <a name="see-also"></a>참고 항목

- [Oracle 및 ADO.NET](oracle-and-adonet.md)
- [ADO.NET 개요](ado-net-overview.md)
