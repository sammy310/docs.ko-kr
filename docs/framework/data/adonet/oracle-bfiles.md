---
title: Oracle BFILE
ms.date: 03/30/2017
ms.assetid: 341bbf84-4734-4d44-8723-ccedee954e21
ms.openlocfilehash: 5bb9f7e67016cf4b1d467935fe302ab4a40edbfa
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59304469"
---
# <a name="oracle-bfiles"></a>Oracle BFILE
.NET Framework Data Provider for Oracle에는 Oracle <xref:System.Data.OracleClient.OracleBFile> 데이터 형식 작업에 사용되는 <xref:System.Data.OracleClient.OracleType.BFile> 클래스가 포함되어 있습니다.  
  
 Oracle **BFILE** 데이터 형식은 Oracle **LOB** 4gb의 최대 크기를 사용 하 여 이진 데이터에 대 한 참조를 포함 하는 데이터 형식입니다. Oracle **BFILE** 다른 Oracle에서 다릅니다 **LOB** 서버의 대신 운영 체제의 물리적 파일에 데이터가 저장 되는 데이터 형식입니다. 유의 합니다 **BFILE** 데이터 형식은 데이터에 대 한 읽기 전용 액세스를 제공 합니다.  
  
 다른 특성을 **BFILE** 구별 되는 데이터 형식을 **LOB** 기원후는:  
  
-   구조화되지 않은 데이터를 포함합니다.  
  
-   서버측 청크를 지원합니다.  
  
-   참조 복사 의미를 사용합니다. 예를 들어 복사 작업을 수행 하는 **BFILE**만 합니다 **BFILE** (즉, 파일에 대 한 참조) 로케이터 복사 됩니다. 파일의 데이터는 복사되지 않습니다.  
  
 합니다 **BFILE** 크기가 큰 Lob를 참조 하는 것에 대 한 데이터 형식을 사용 해야 하므로 데이터베이스에 저장 하기에 적합 하지 합니다. 더 많은 클라이언트, 서버 및 통신 오버 헤드가 수반 됩니다는 **BFILE** 데이터 형식에 비해 합니다 **LOB** 데이터 형식. 것이 더 효율적 액세스 하는 **BFILE** 적은 양의 데이터를 획득 해야 하는 경우. 반면에 전체 개체를 가져와야 하는 경우에는 데이터베이스 상주 LOB에 액세스 하는 것이 효율적입니다.  
  
 NULL이 아닌 각 **OracleBFile** 개체가 기본 물리적 파일의 위치를 정의 하는 두 엔터티를 사용 하 여 연결 합니다.  
  
1. 파일 시스템의 디렉터리에 대한 데이터베이스 별칭인 Oracle DIRECTORY 개체입니다.  
  
2. DIRECTORY 개체와 연관된 디렉터리에 위치하는 원본 파일 이름입니다.  
  
## <a name="example"></a>예제  
 다음 C# 예제를 만드는 방법을 보여 줍니다.는 **BFILE** 다음의 형태로 검색 하 고 Oracle 테이블에 **OracleBFile** 개체입니다. 예제를 사용 하 여는 <xref:System.Data.OracleClient.OracleDataReader> 개체 및 **OracleBFile** **Seek** 하 고 **읽기** 메서드. 이 샘플을 사용 하려면 먼저 만들어야 라는 디렉터리를 참고 "c:\\\bfiles"와 "MyFile.jpg" Oracle 서버에 명명 된 파일입니다.  
  
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
  
## <a name="see-also"></a>참고자료

- [Oracle 및 ADO.NET](../../../../docs/framework/data/adonet/oracle-and-adonet.md)
- [ADO.NET 관리되는 공급자 및 데이터 집합 개발자 센터](https://go.microsoft.com/fwlink/?LinkId=217917)
