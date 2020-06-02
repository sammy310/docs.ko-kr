---
title: 데이터베이스에서 단일 값 가져오기
description: ADO.NET에서 단일 값을 반환 하는 방법에 대해 알아봅니다. 이 예제 코드는 삽입 된 레코드에 대 한 id 열 값을 반환 합니다.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: b38526cd-a62a-48cb-822a-e91dfa68e02d
ms.openlocfilehash: a6f268f72f8b8a09ae48ba3cad6254323cb95a20
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/02/2020
ms.locfileid: "84286704"
---
# <a name="obtaining-a-single-value-from-a-database"></a><span data-ttu-id="e5f59-104">데이터베이스에서 단일 값 가져오기</span><span class="sxs-lookup"><span data-stu-id="e5f59-104">Obtaining a Single Value from a Database</span></span>
<span data-ttu-id="e5f59-105">테이블이나 데이터 스트림 형식보다는 단순히 단일 값인 데이터베이스 정보를 반환해야 하는 경우가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e5f59-105">You may need to return database information that is simply a single value rather than in the form of a table or data stream.</span></span> <span data-ttu-id="e5f59-106">예를 들어 COUNT ( \* ), SUM (Price) 또는 AVG (Quantity)와 같은 집계 함수의 결과를 반환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e5f59-106">For example, you may want to return the result of an aggregate function such as COUNT(\*), SUM(Price), or AVG(Quantity).</span></span> <span data-ttu-id="e5f59-107">**Command** 개체는 **ExecuteScalar** 메서드를 사용 하 여 단일 값을 반환 하는 기능을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="e5f59-107">The **Command** object provides the capability to return single values using the **ExecuteScalar** method.</span></span> <span data-ttu-id="e5f59-108">**ExecuteScalar** 메서드는 결과 집합에서 첫 번째 행의 첫 번째 열 값을 스칼라 값으로 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="e5f59-108">The **ExecuteScalar** method returns, as a scalar value, the value of the first column of the first row of the result set.</span></span>  
  
 <span data-ttu-id="e5f59-109">다음 코드 예제에서는 <xref:System.Data.SqlClient.SqlCommand>를 사용하여 데이터베이스에 새 값을 삽입합니다.</span><span class="sxs-lookup"><span data-stu-id="e5f59-109">The following code example inserts a new value in the database using a <xref:System.Data.SqlClient.SqlCommand>.</span></span> <span data-ttu-id="e5f59-110">여기서 <xref:System.Data.SqlClient.SqlCommand.ExecuteScalar%2A> 메서드는 삽입된 레코드의 ID 열 값을 반환하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="e5f59-110">The <xref:System.Data.SqlClient.SqlCommand.ExecuteScalar%2A> method is used to return the identity column value for the inserted record.</span></span>  
  
 [!code-csharp[DataWorks SqlCommand.ExecuteScalar#1](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks SqlCommand.ExecuteScalar/CS/source.cs#1)]
 [!code-vb[DataWorks SqlCommand.ExecuteScalar#1](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks SqlCommand.ExecuteScalar/VB/source.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="e5f59-111">참고 항목</span><span class="sxs-lookup"><span data-stu-id="e5f59-111">See also</span></span>

- [<span data-ttu-id="e5f59-112">명령 및 매개 변수</span><span class="sxs-lookup"><span data-stu-id="e5f59-112">Commands and Parameters</span></span>](commands-and-parameters.md)
- [<span data-ttu-id="e5f59-113">명령 실행</span><span class="sxs-lookup"><span data-stu-id="e5f59-113">Executing a Command</span></span>](executing-a-command.md)
- [<span data-ttu-id="e5f59-114">DbConnection, DbCommand 및 DbException</span><span class="sxs-lookup"><span data-stu-id="e5f59-114">DbConnection, DbCommand and DbException</span></span>](dbconnection-dbcommand-and-dbexception.md)
- [<span data-ttu-id="e5f59-115">ADO.NET 개요</span><span class="sxs-lookup"><span data-stu-id="e5f59-115">ADO.NET Overview</span></span>](ado-net-overview.md)
