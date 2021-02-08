---
description: '자세한 정보: 저장 프로시저를 사용 하 여 데이터 수정'
title: 저장 프로시저로 데이터 수정
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 7d8e9a46-1af6-4a02-bf61-969d77ae07e0
ms.openlocfilehash: 66a4aa9577c71605bde0152a142a65dfa81a31d7
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99786227"
---
# <a name="modifying-data-with-stored-procedures"></a><span data-ttu-id="05794-103">저장 프로시저로 데이터 수정</span><span class="sxs-lookup"><span data-stu-id="05794-103">Modifying Data with Stored Procedures</span></span>

<span data-ttu-id="05794-104">저장 프로시저는 입력 매개 변수로 데이터를 받아들이고 출력 매개 변수, 결과 집합 또는 반환 값으로 데이터를 반환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="05794-104">Stored procedures can accept data as input parameters and can return data as output parameters, result sets, or return values.</span></span> <span data-ttu-id="05794-105">다음 샘플에서는 ADO.NET에서 입력 매개 변수, 출력 매개 변수 및 반환 값을 보내고 받는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="05794-105">The sample below illustrates how ADO.NET sends and receives input parameters, output parameters, and return values.</span></span> <span data-ttu-id="05794-106">이 예제에서는 기본 키 열이 SQL Server 데이터베이스의 ID 열인 테이블에 새 레코드를 삽입합니다.</span><span class="sxs-lookup"><span data-stu-id="05794-106">The example inserts a new record into a table where the primary key column is an identity column in a SQL Server database.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="05794-107">SQL Server 저장 프로시저를 사용 하 여를 사용 하 여 데이터를 편집 하거나 삭제 하는 경우 <xref:System.Data.SqlClient.SqlDataAdapter> 저장 프로시저 정의에 SET NOCOUNT ON을 사용 하지 않아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="05794-107">If you are using SQL Server stored procedures to edit or delete data using a <xref:System.Data.SqlClient.SqlDataAdapter>, make sure that you do not use SET NOCOUNT ON in the stored procedure definition.</span></span> <span data-ttu-id="05794-108">사용할 경우에는 영향을 받는 행 수가 0으로 반환되어 `DataAdapter`가 동시성 충돌로 해석됩니다.</span><span class="sxs-lookup"><span data-stu-id="05794-108">This causes the rows affected count returned to be zero, which the `DataAdapter` interprets as a concurrency conflict.</span></span> <span data-ttu-id="05794-109">이 경우 <xref:System.Data.DBConcurrencyException>이 throw됩니다.</span><span class="sxs-lookup"><span data-stu-id="05794-109">In this event, a <xref:System.Data.DBConcurrencyException> will be thrown.</span></span>  
  
## <a name="example"></a><span data-ttu-id="05794-110">예제</span><span class="sxs-lookup"><span data-stu-id="05794-110">Example</span></span>  

 <span data-ttu-id="05794-111">이 예제는 다음 저장 프로시저를 사용하여 **Northwind** **Categories** 테이블에 새 범주를 삽입합니다.</span><span class="sxs-lookup"><span data-stu-id="05794-111">The sample uses the following stored procedure to insert a new category into the **Northwind** **Categories** table.</span></span> <span data-ttu-id="05794-112">저장 프로시저는 **CategoryName** 열의 값을 입력 매개 변수로 받아 SCOPE_IDENTITY() 함수를 사용하여 ID 필드인 **CategoryID** 의 새 값을 검색한 다음 이를 출력 매개 변수로 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="05794-112">The stored procedure takes the value in the **CategoryName** column as an input parameter and uses the SCOPE_IDENTITY() function to retrieve the new value of the identity field, **CategoryID**, and return it in an output parameter.</span></span> <span data-ttu-id="05794-113">RETURN 문은 @ 함수를 사용 하 여 @ROWCOUNT 삽입 된 행의 수를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="05794-113">The RETURN statement uses the @@ROWCOUNT function to return the number of rows inserted.</span></span>  
  
```sql
CREATE PROCEDURE dbo.InsertCategory  
  @CategoryName nvarchar(15),  
  @Identity int OUT  
AS  
INSERT INTO Categories (CategoryName) VALUES(@CategoryName)  
SET @Identity = SCOPE_IDENTITY()  
RETURN @@ROWCOUNT  
```  
  
 <span data-ttu-id="05794-114">다음 코드 예제에서는 위의 `InsertCategory` 저장 프로시저를 <xref:System.Data.SqlClient.SqlDataAdapter.InsertCommand%2A>의 <xref:System.Data.SqlClient.SqlDataAdapter>에 대한 소스로 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="05794-114">The following code example uses the `InsertCategory` stored procedure shown above as the source for the <xref:System.Data.SqlClient.SqlDataAdapter.InsertCommand%2A> of the <xref:System.Data.SqlClient.SqlDataAdapter>.</span></span> <span data-ttu-id="05794-115">`@Identity`의 <xref:System.Data.DataSet> 메서드를 호출하면 데이터베이스에 레코드가 삽입된 후 `Update` 출력 매개 변수가 <xref:System.Data.SqlClient.SqlDataAdapter>에 반영됩니다.</span><span class="sxs-lookup"><span data-stu-id="05794-115">The `@Identity` output parameter will be reflected in the <xref:System.Data.DataSet> after the record has been inserted into the database when the `Update` method of the <xref:System.Data.SqlClient.SqlDataAdapter> is called.</span></span> <span data-ttu-id="05794-116">이 코드는 반환 값도 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="05794-116">The code also retrieves the return value.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="05794-117">을 사용 하는 경우 <xref:System.Data.OleDb.OleDbDataAdapter> <xref:System.Data.ParameterDirection> 다른 매개 변수 앞에 **ReturnValue** 의를 사용 하 여 매개 변수를 지정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="05794-117">When using the <xref:System.Data.OleDb.OleDbDataAdapter>, you must specify parameters with a <xref:System.Data.ParameterDirection> of **ReturnValue** before the other parameters.</span></span>  
  
 [!code-csharp[DataWorks SqlClient.SprocIdentityReturn#1](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks SqlClient.SprocIdentityReturn/CS/source.cs#1)]
 [!code-vb[DataWorks SqlClient.SprocIdentityReturn#1](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks SqlClient.SprocIdentityReturn/VB/source.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="05794-118">참고 항목</span><span class="sxs-lookup"><span data-stu-id="05794-118">See also</span></span>

- [<span data-ttu-id="05794-119">ADO.NET에서 데이터 검색 및 수정</span><span class="sxs-lookup"><span data-stu-id="05794-119">Retrieving and Modifying Data in ADO.NET</span></span>](retrieving-and-modifying-data.md)
- [<span data-ttu-id="05794-120">DataAdapters 및 DataReaders</span><span class="sxs-lookup"><span data-stu-id="05794-120">DataAdapters and DataReaders</span></span>](dataadapters-and-datareaders.md)
- [<span data-ttu-id="05794-121">명령 실행</span><span class="sxs-lookup"><span data-stu-id="05794-121">Executing a Command</span></span>](executing-a-command.md)
- [<span data-ttu-id="05794-122">ADO.NET 개요</span><span class="sxs-lookup"><span data-stu-id="05794-122">ADO.NET Overview</span></span>](ado-net-overview.md)
