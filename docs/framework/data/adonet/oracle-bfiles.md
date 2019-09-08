---
title: Oracle BFILE
ms.date: 03/30/2017
ms.assetid: 341bbf84-4734-4d44-8723-ccedee954e21
ms.openlocfilehash: 214140bb8fcf43154b014ea3db609d355a27af7c
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/07/2019
ms.locfileid: "70794633"
---
# <a name="oracle-bfiles"></a><span data-ttu-id="64611-102">Oracle BFILE</span><span class="sxs-lookup"><span data-stu-id="64611-102">Oracle BFILEs</span></span>
<span data-ttu-id="64611-103">.NET Framework Data Provider for Oracle에는 Oracle <xref:System.Data.OracleClient.OracleBFile> 데이터 형식 작업에 사용되는 <xref:System.Data.OracleClient.OracleType.BFile> 클래스가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="64611-103">The .NET Framework Data Provider for Oracle includes the <xref:System.Data.OracleClient.OracleBFile> class, which is used to work with the Oracle <xref:System.Data.OracleClient.OracleType.BFile> data type.</span></span>  
  
 <span data-ttu-id="64611-104">Oracle **BFILE** 데이터 형식은 최대 크기가 4gb 인 이진 데이터에 대 한 참조를 포함 하는 oracle **LOB** 데이터 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="64611-104">The Oracle **BFILE** data type is an Oracle **LOB** data type that contains a reference to binary data with a maximum size of 4 gigabytes.</span></span> <span data-ttu-id="64611-105">Oracle **BFILE** 은 해당 데이터가 서버가 아닌 운영 체제의 물리적 파일에 저장 된다는 점에서 다른 oracle **LOB** 데이터 형식과 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="64611-105">An Oracle **BFILE** differs from other Oracle **LOB** data types in that its data is stored in a physical file in the operating system instead of on the server.</span></span> <span data-ttu-id="64611-106">**BFILE** 데이터 형식은 데이터에 대 한 읽기 전용 액세스를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="64611-106">Note that the **BFILE** data type provides read-only access to data.</span></span>  
  
 <span data-ttu-id="64611-107">**LOB** 데이터 형식과 구별 되는 **BFILE** 데이터 형식의 다른 특성은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="64611-107">Other characteristics of a **BFILE** data type that distinguish it from a **LOB** data type are that it:</span></span>  
  
- <span data-ttu-id="64611-108">구조화되지 않은 데이터를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="64611-108">Contains unstructured data.</span></span>  
  
- <span data-ttu-id="64611-109">서버측 청크를 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="64611-109">Supports server-side chunking.</span></span>  
  
- <span data-ttu-id="64611-110">참조 복사 의미를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="64611-110">Uses reference copy semantics.</span></span> <span data-ttu-id="64611-111">예를 들어 **bfile**에서 복사 작업을 수행 하는 경우 파일에 대 한 참조 인 **bfile** 로케이터만 복사 됩니다.</span><span class="sxs-lookup"><span data-stu-id="64611-111">For example, if you perform a copy operation on a **BFILE**, only the **BFILE** locator (which is a reference to the file) is copied.</span></span> <span data-ttu-id="64611-112">파일의 데이터는 복사되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="64611-112">The data in the file is not copied.</span></span>  
  
 <span data-ttu-id="64611-113">**BFILE** 데이터 형식은 크기가 큰 lob를 참조 하는 데 사용 해야 하므로 데이터베이스에 저장 하는 것은 실용적이 지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="64611-113">The **BFILE** data type should be used for referencing LOBs that are large in size, and therefore, not practical to store in the database.</span></span> <span data-ttu-id="64611-114">**LOB** 데이터 형식과 비교 하 여 **BFILE** 데이터 형식을 사용 하는 경우 더 많은 클라이언트, 서버 및 통신 오버 헤드가 수반 됩니다.</span><span class="sxs-lookup"><span data-stu-id="64611-114">More client, server, and communication overhead is involved when using a **BFILE** data type compared with the **LOB** data type.</span></span> <span data-ttu-id="64611-115">적은 양의 데이터를 가져와야 하는 경우에는 **BFILE** 에 액세스 하는 것이 더 효율적입니다.</span><span class="sxs-lookup"><span data-stu-id="64611-115">It is more efficient to access a **BFILE** if you only need to obtain a small amount of data.</span></span> <span data-ttu-id="64611-116">반면에 전체 개체를 가져와야 하는 경우에는 데이터베이스 상주 LOB에 액세스 하는 것이 효율적입니다.</span><span class="sxs-lookup"><span data-stu-id="64611-116">It is more efficient to access database-resident LOBs if you need to obtain the entire object.</span></span>  
  
 <span data-ttu-id="64611-117">NULL이 아닌 각 **OracleBFile** 개체는 기본 실제 파일의 위치를 정의 하는 두 개의 엔터티와 연결 됩니다.</span><span class="sxs-lookup"><span data-stu-id="64611-117">Each non-NULL **OracleBFile** object is associated with two entities that define the location of the underlying physical file:</span></span>  
  
1. <span data-ttu-id="64611-118">파일 시스템의 디렉터리에 대한 데이터베이스 별칭인 Oracle DIRECTORY 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="64611-118">An Oracle DIRECTORY object, which is a database alias for a directory in the file system, and</span></span>  
  
2. <span data-ttu-id="64611-119">DIRECTORY 개체와 연관된 디렉터리에 위치하는 원본 파일 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="64611-119">The file name of the underlying physical file, which is located in the directory associated with the DIRECTORY object.</span></span>  
  
## <a name="example"></a><span data-ttu-id="64611-120">예제</span><span class="sxs-lookup"><span data-stu-id="64611-120">Example</span></span>  
 <span data-ttu-id="64611-121">다음 C# 예에서는 Oracle 테이블에 **BFILE** 을 만든 다음 **OracleBFile** 개체의 형식으로 검색 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="64611-121">The following C# example demonstrates how you can create a **BFILE** in an Oracle table and then retrieve it in the form of an **OracleBFile** object.</span></span> <span data-ttu-id="64611-122"><xref:System.Data.OracleClient.OracleDataReader> 이 예제에서는 개체와 **OracleBFile** **Seek** 및 **Read** 메서드를 사용 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="64611-122">The example demonstrates using the <xref:System.Data.OracleClient.OracleDataReader> object and the **OracleBFile** **Seek** and **Read** methods.</span></span> <span data-ttu-id="64611-123">이 샘플을 사용 하려면 먼저 Oracle 서버에 "c:\\\bfiles" 라는 디렉터리와 "MyFile. .jpg" 라는 파일을 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="64611-123">Note that in order to use this sample, you must first create a directory named "c:\\\bfiles" and file named "MyFile.jpg" on the Oracle server.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="64611-124">참고자료</span><span class="sxs-lookup"><span data-stu-id="64611-124">See also</span></span>

- [<span data-ttu-id="64611-125">Oracle 및 ADO.NET</span><span class="sxs-lookup"><span data-stu-id="64611-125">Oracle and ADO.NET</span></span>](oracle-and-adonet.md)
- [<span data-ttu-id="64611-126">ADO.NET 개요</span><span class="sxs-lookup"><span data-stu-id="64611-126">ADO.NET Overview</span></span>](ado-net-overview.md)
