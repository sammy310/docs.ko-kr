---
title: '방법: 데이터베이스에 연결'
description: DataContext를 사용 하 여 LINQ to SQL에서 데이터베이스에 연결 하는 방법에 대해 알아봅니다. DataContext를 사용 하 여 데이터베이스에 연결 하 고 행을 가져오려면 다음 예제를 참조 하세요.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: c33d74b3-530d-421b-a121-96786dd263a5
ms.openlocfilehash: c3320a598cb8407ab584530c615c2e5ef0de53c8
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/02/2020
ms.locfileid: "84286406"
---
# <a name="how-to-connect-to-a-database"></a><span data-ttu-id="8df3b-104">방법: 데이터베이스에 연결</span><span class="sxs-lookup"><span data-stu-id="8df3b-104">How to: Connect to a Database</span></span>
<span data-ttu-id="8df3b-105"><xref:System.Data.Linq.DataContext>는 데이터베이스에 연결하여 개체를 검색하고 변경 내용을 데이터베이스로 다시 전송하는 주 통로입니다.</span><span class="sxs-lookup"><span data-stu-id="8df3b-105">The <xref:System.Data.Linq.DataContext> is the main conduit by which you connect to a database, retrieve objects from it, and submit changes back to it.</span></span> <span data-ttu-id="8df3b-106">ADO.NET를 사용 하는 것 처럼를 사용 <xref:System.Data.Linq.DataContext> <xref:System.Data.SqlClient.SqlConnection> 합니다.</span><span class="sxs-lookup"><span data-stu-id="8df3b-106">You use the <xref:System.Data.Linq.DataContext> just as you would use an ADO.NET <xref:System.Data.SqlClient.SqlConnection>.</span></span> <span data-ttu-id="8df3b-107">실제로 <xref:System.Data.Linq.DataContext>는 사용자가 지정한 연결 또는 연결 문자열을 통해 초기화됩니다.</span><span class="sxs-lookup"><span data-stu-id="8df3b-107">In fact, the <xref:System.Data.Linq.DataContext> is initialized with a connection or connection string that you supply.</span></span> <span data-ttu-id="8df3b-108">자세한 내용은 [DataContext 메서드 (O/R 디자이너)](/visualstudio/data-tools/datacontext-methods-o-r-designer)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="8df3b-108">For more information, see [DataContext Methods (O/R Designer)](/visualstudio/data-tools/datacontext-methods-o-r-designer).</span></span>  
  
 <span data-ttu-id="8df3b-109"><xref:System.Data.Linq.DataContext>의 용도는 개체에 대한 요청을 데이터베이스에 적용할 수 있는 SQL 쿼리로 변환한 다음 결과 외의 개체를 어셈블하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="8df3b-109">The purpose of the <xref:System.Data.Linq.DataContext> is to translate your requests for objects into SQL queries to be made against the database, and then to assemble objects out of the results.</span></span> <span data-ttu-id="8df3b-110">에서는 <xref:System.Data.Linq.DataContext> 표준 쿼리 연산자와 같은 연산자 패턴 (예: 및)을 구현 하 여 LINQ (통합 언어 쿼리)를 사용할 수 있습니다 `Where` `Select` .</span><span class="sxs-lookup"><span data-stu-id="8df3b-110">The <xref:System.Data.Linq.DataContext> enables Language-Integrated Query (LINQ) by implementing the same operator pattern as the Standard Query Operators, such as `Where` and `Select`.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="8df3b-111">보안 연결을 유지 관리하는 것이 가장 중요합니다.</span><span class="sxs-lookup"><span data-stu-id="8df3b-111">Maintaining a secure connection is of the highest importance.</span></span> <span data-ttu-id="8df3b-112">자세한 내용은 [LINQ to SQL의 보안](security-in-linq-to-sql.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="8df3b-112">For more information, see [Security in LINQ to SQL](security-in-linq-to-sql.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="8df3b-113">예제</span><span class="sxs-lookup"><span data-stu-id="8df3b-113">Example</span></span>  
 <span data-ttu-id="8df3b-114">다음 예제에서는 <xref:System.Data.Linq.DataContext>를 사용하여 Northwind 샘플 데이터베이스에 연결한 다음 도시가 London인 고객의 행을 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="8df3b-114">In the following example, the <xref:System.Data.Linq.DataContext> is used to connect to the Northwind sample database and to retrieve rows of customers whose city is London.</span></span>  
  
 [!code-csharp[DLinqCommunicatingWithDatabase#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqCommunicatingWithDatabase/cs/Program.cs#1)]
 [!code-vb[DLinqCommunicatingWithDatabase#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqCommunicatingWithDatabase/vb/Module1.vb#1)]  
  
 <span data-ttu-id="8df3b-115">각 데이터베이스 테이블은 해당 테이블을 식별할 수 있는 엔터티 클래스를 사용하여 `Table` 메서드를 통해 사용할 수 있는 <xref:System.Data.Linq.DataContext.GetTable%2A> 컬렉션으로 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="8df3b-115">Each database table is represented as a `Table` collection available by way of the <xref:System.Data.Linq.DataContext.GetTable%2A> method, by using the entity class to identify it.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8df3b-116">예제</span><span class="sxs-lookup"><span data-stu-id="8df3b-116">Example</span></span>  
 <span data-ttu-id="8df3b-117">가장 좋은 방법은 기본 <xref:System.Data.Linq.DataContext> 클래스와 <xref:System.Data.Linq.DataContext> 메서드를 사용하는 대신 강력한 형식의 <xref:System.Data.Linq.DataContext.GetTable%2A>를 선언하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="8df3b-117">Best practice is to declare a strongly typed <xref:System.Data.Linq.DataContext> instead of relying on the basic <xref:System.Data.Linq.DataContext> class and the <xref:System.Data.Linq.DataContext.GetTable%2A> method.</span></span> <span data-ttu-id="8df3b-118">강력한 형식의 <xref:System.Data.Linq.DataContext>에서는 다음 예제와 같이 `Table` 컬렉션을 컨텍스트의 멤버로 선언합니다.</span><span class="sxs-lookup"><span data-stu-id="8df3b-118">A strongly typed <xref:System.Data.Linq.DataContext> declares all `Table` collections as members of the context, as in the following example.</span></span>  
  
 [!code-csharp[DLinqCommunicatingWithDatabase#2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqCommunicatingWithDatabase/cs/Program.cs#2)]
 [!code-vb[DLinqCommunicatingWithDatabase#2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqCommunicatingWithDatabase/vb/Module1.vb#2)]  
  
 <span data-ttu-id="8df3b-119">그런 다음 London에 있는 고객에 대한 쿼리를 다음과 같이 더 간단하게 표현할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8df3b-119">You can then express the query for customers from London more simply as:</span></span>  
  
 [!code-csharp[DLinqCommunicatingWithDatabase#5](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqCommunicatingWithDatabase/cs/Program.cs#5)]
 [!code-vb[DLinqCommunicatingWithDatabase#5](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqCommunicatingWithDatabase/vb/Module1.vb#5)]  
  
## <a name="see-also"></a><span data-ttu-id="8df3b-120">참고 항목</span><span class="sxs-lookup"><span data-stu-id="8df3b-120">See also</span></span>

- [<span data-ttu-id="8df3b-121">데이터베이스와 통신</span><span class="sxs-lookup"><span data-stu-id="8df3b-121">Communicating with the Database</span></span>](communicating-with-the-database.md)
