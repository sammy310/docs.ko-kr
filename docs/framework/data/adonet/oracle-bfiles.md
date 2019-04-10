---
title: Oracle BFILE
ms.date: 03/30/2017
ms.assetid: 341bbf84-4734-4d44-8723-ccedee954e21
ms.openlocfilehash: 07a7f28e08ed43672e94151cd9de88301069e1ec
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59142391"
---
# <a name="oracle-bfiles"></a><span data-ttu-id="41edd-102">Oracle BFILE</span><span class="sxs-lookup"><span data-stu-id="41edd-102">Oracle BFILEs</span></span>
<span data-ttu-id="41edd-103">.NET Framework Data Provider for Oracle에는 Oracle <xref:System.Data.OracleClient.OracleBFile> 데이터 형식 작업에 사용되는 <xref:System.Data.OracleClient.OracleType.BFile> 클래스가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="41edd-103">The .NET Framework Data Provider for Oracle includes the <xref:System.Data.OracleClient.OracleBFile> class, which is used to work with the Oracle <xref:System.Data.OracleClient.OracleType.BFile> data type.</span></span>  
  
 <span data-ttu-id="41edd-104">Oracle **BFILE** 데이터 형식은 Oracle **LOB** 4gb의 최대 크기를 사용 하 여 이진 데이터에 대 한 참조를 포함 하는 데이터 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="41edd-104">The Oracle **BFILE** data type is an Oracle **LOB** data type that contains a reference to binary data with a maximum size of 4 gigabytes.</span></span> <span data-ttu-id="41edd-105">Oracle **BFILE** 다른 Oracle에서 다릅니다 **LOB** 서버의 대신 운영 체제의 물리적 파일에 데이터가 저장 되는 데이터 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="41edd-105">An Oracle **BFILE** differs from other Oracle **LOB** data types in that its data is stored in a physical file in the operating system instead of on the server.</span></span> <span data-ttu-id="41edd-106">유의 합니다 **BFILE** 데이터 형식은 데이터에 대 한 읽기 전용 액세스를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="41edd-106">Note that the **BFILE** data type provides read-only access to data.</span></span>  
  
 <span data-ttu-id="41edd-107">다른 특성을 **BFILE** 구별 되는 데이터 형식을 **LOB** 기원후는:</span><span class="sxs-lookup"><span data-stu-id="41edd-107">Other characteristics of a **BFILE** data type that distinguish it from a **LOB** data type are that it:</span></span>  
  
-   <span data-ttu-id="41edd-108">구조화되지 않은 데이터를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="41edd-108">Contains unstructured data.</span></span>  
  
-   <span data-ttu-id="41edd-109">서버측 청크를 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="41edd-109">Supports server-side chunking.</span></span>  
  
-   <span data-ttu-id="41edd-110">참조 복사 의미를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="41edd-110">Uses reference copy semantics.</span></span> <span data-ttu-id="41edd-111">예를 들어 복사 작업을 수행 하는 **BFILE**만 합니다 **BFILE** (즉, 파일에 대 한 참조) 로케이터 복사 됩니다.</span><span class="sxs-lookup"><span data-stu-id="41edd-111">For example, if you perform a copy operation on a **BFILE**, only the **BFILE** locator (which is a reference to the file) is copied.</span></span> <span data-ttu-id="41edd-112">파일의 데이터는 복사되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="41edd-112">The data in the file is not copied.</span></span>  
  
 <span data-ttu-id="41edd-113">합니다 **BFILE** 크기가 큰 Lob를 참조 하는 것에 대 한 데이터 형식을 사용 해야 하므로 데이터베이스에 저장 하기에 적합 하지 합니다.</span><span class="sxs-lookup"><span data-stu-id="41edd-113">The **BFILE** data type should be used for referencing LOBs that are large in size, and therefore, not practical to store in the database.</span></span> <span data-ttu-id="41edd-114">더 많은 클라이언트, 서버 및 통신 오버 헤드가 수반 됩니다는 **BFILE** 데이터 형식에 비해 합니다 **LOB** 데이터 형식.</span><span class="sxs-lookup"><span data-stu-id="41edd-114">More client, server, and communication overhead is involved when using a **BFILE** data type compared with the **LOB** data type.</span></span> <span data-ttu-id="41edd-115">것이 더 효율적 액세스 하는 **BFILE** 적은 양의 데이터를 획득 해야 하는 경우.</span><span class="sxs-lookup"><span data-stu-id="41edd-115">It is more efficient to access a **BFILE** if you only need to obtain a small amount of data.</span></span> <span data-ttu-id="41edd-116">반면에 전체 개체를 가져와야 하는 경우에는 데이터베이스 상주 LOB에 액세스 하는 것이 효율적입니다.</span><span class="sxs-lookup"><span data-stu-id="41edd-116">It is more efficient to access database-resident LOBs if you need to obtain the entire object.</span></span>  
  
 <span data-ttu-id="41edd-117">NULL이 아닌 각 **OracleBFile** 개체가 기본 물리적 파일의 위치를 정의 하는 두 엔터티를 사용 하 여 연결 합니다.</span><span class="sxs-lookup"><span data-stu-id="41edd-117">Each non-NULL **OracleBFile** object is associated with two entities that define the location of the underlying physical file:</span></span>  
  
1.  <span data-ttu-id="41edd-118">파일 시스템의 디렉터리에 대한 데이터베이스 별칭인 Oracle DIRECTORY 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="41edd-118">An Oracle DIRECTORY object, which is a database alias for a directory in the file system, and</span></span>  
  
2.  <span data-ttu-id="41edd-119">DIRECTORY 개체와 연관된 디렉터리에 위치하는 원본 파일 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="41edd-119">The file name of the underlying physical file, which is located in the directory associated with the DIRECTORY object.</span></span>  
  
## <a name="example"></a><span data-ttu-id="41edd-120">예제</span><span class="sxs-lookup"><span data-stu-id="41edd-120">Example</span></span>  
 <span data-ttu-id="41edd-121">다음 C# 예제를 만드는 방법을 보여 줍니다.는 **BFILE** 다음의 형태로 검색 하 고 Oracle 테이블에 **OracleBFile** 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="41edd-121">The following C# example demonstrates how you can create a **BFILE** in an Oracle table and then retrieve it in the form of an **OracleBFile** object.</span></span> <span data-ttu-id="41edd-122">예제를 사용 하 여는 <xref:System.Data.OracleClient.OracleDataReader> 개체 및 **OracleBFile** **Seek** 하 고 **읽기** 메서드.</span><span class="sxs-lookup"><span data-stu-id="41edd-122">The example demonstrates using the <xref:System.Data.OracleClient.OracleDataReader> object and the **OracleBFile** **Seek** and **Read** methods.</span></span> <span data-ttu-id="41edd-123">이 샘플을 사용 하려면 먼저 만들어야 라는 디렉터리를 참고 "c:\\\bfiles"와 "MyFile.jpg" Oracle 서버에 명명 된 파일입니다.</span><span class="sxs-lookup"><span data-stu-id="41edd-123">Note that in order to use this sample, you must first create a directory named "c:\\\bfiles" and file named "MyFile.jpg" on the Oracle server.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="41edd-124">참고자료</span><span class="sxs-lookup"><span data-stu-id="41edd-124">See also</span></span>

- [<span data-ttu-id="41edd-125">Oracle 및 ADO.NET</span><span class="sxs-lookup"><span data-stu-id="41edd-125">Oracle and ADO.NET</span></span>](../../../../docs/framework/data/adonet/oracle-and-adonet.md)
- [<span data-ttu-id="41edd-126">ADO.NET 관리되는 공급자 및 데이터 집합 개발자 센터</span><span class="sxs-lookup"><span data-stu-id="41edd-126">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
