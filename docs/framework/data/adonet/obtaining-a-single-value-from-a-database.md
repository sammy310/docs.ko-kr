---
title: 데이터베이스에서 단일 값 가져오기
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: b38526cd-a62a-48cb-822a-e91dfa68e02d
ms.openlocfilehash: 5eb81fd2a64f06f1252f71e251e58df568e7407c
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61772075"
---
# <a name="obtaining-a-single-value-from-a-database"></a><span data-ttu-id="125db-102">데이터베이스에서 단일 값 가져오기</span><span class="sxs-lookup"><span data-stu-id="125db-102">Obtaining a Single Value from a Database</span></span>
<span data-ttu-id="125db-103">테이블이나 데이터 스트림 형식보다는 단순히 단일 값인 데이터베이스 정보를 반환해야 하는 경우가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="125db-103">You may need to return database information that is simply a single value rather than in the form of a table or data stream.</span></span> <span data-ttu-id="125db-104">COUNT와 같은 집계 함수의 결과 반환 하려는 하는 예를 들어 (\*), price 또는 AVG(Quantity) 합니다.</span><span class="sxs-lookup"><span data-stu-id="125db-104">For example, you may want to return the result of an aggregate function such as COUNT(\*), SUM(Price), or AVG(Quantity).</span></span> <span data-ttu-id="125db-105">합니다 **명령** 개체를 사용 하 여 단일 값을 반환 하는 기능을 제공 합니다 **ExecuteScalar** 메서드.</span><span class="sxs-lookup"><span data-stu-id="125db-105">The **Command** object provides the capability to return single values using the **ExecuteScalar** method.</span></span> <span data-ttu-id="125db-106">합니다 **ExecuteScalar** 메서드는 스칼라 값을 결과 집합의 첫 번째 행의 첫 번째 열 값으로 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="125db-106">The **ExecuteScalar** method returns, as a scalar value, the value of the first column of the first row of the result set.</span></span>  
  
 <span data-ttu-id="125db-107">다음 코드 예제에서는 <xref:System.Data.SqlClient.SqlCommand>를 사용하여 데이터베이스에 새 값을 삽입합니다.</span><span class="sxs-lookup"><span data-stu-id="125db-107">The following code example inserts a new value in the database using a <xref:System.Data.SqlClient.SqlCommand>.</span></span> <span data-ttu-id="125db-108">여기서 <xref:System.Data.SqlClient.SqlCommand.ExecuteScalar%2A> 메서드는 삽입된 레코드의 ID 열 값을 반환하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="125db-108">The <xref:System.Data.SqlClient.SqlCommand.ExecuteScalar%2A> method is used to return the identity column value for the inserted record.</span></span>  
  
 [!code-csharp[DataWorks SqlCommand.ExecuteScalar#1](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks SqlCommand.ExecuteScalar/CS/source.cs#1)]
 [!code-vb[DataWorks SqlCommand.ExecuteScalar#1](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks SqlCommand.ExecuteScalar/VB/source.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="125db-109">참고자료</span><span class="sxs-lookup"><span data-stu-id="125db-109">See also</span></span>

- [<span data-ttu-id="125db-110">명령 및 매개 변수</span><span class="sxs-lookup"><span data-stu-id="125db-110">Commands and Parameters</span></span>](../../../../docs/framework/data/adonet/commands-and-parameters.md)
- [<span data-ttu-id="125db-111">명령 실행</span><span class="sxs-lookup"><span data-stu-id="125db-111">Executing a Command</span></span>](../../../../docs/framework/data/adonet/executing-a-command.md)
- [<span data-ttu-id="125db-112">DbConnection, DbCommand 및 DbException</span><span class="sxs-lookup"><span data-stu-id="125db-112">DbConnection, DbCommand and DbException</span></span>](../../../../docs/framework/data/adonet/dbconnection-dbcommand-and-dbexception.md)
- [<span data-ttu-id="125db-113">ADO.NET 관리되는 공급자 및 데이터 집합 개발자 센터</span><span class="sxs-lookup"><span data-stu-id="125db-113">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
