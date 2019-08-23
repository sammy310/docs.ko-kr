---
title: '방법: 데이터베이스에 연결'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: c33d74b3-530d-421b-a121-96786dd263a5
ms.openlocfilehash: ebf630c08714a2e5162ba072f88b7fbdef7ca0f4
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/22/2019
ms.locfileid: "69964056"
---
# <a name="how-to-connect-to-a-database"></a><span data-ttu-id="77b11-102">방법: 데이터베이스에 연결</span><span class="sxs-lookup"><span data-stu-id="77b11-102">How to: Connect to a Database</span></span>
<span data-ttu-id="77b11-103"><xref:System.Data.Linq.DataContext>는 데이터베이스에 연결하여 개체를 검색하고 변경 내용을 데이터베이스로 다시 전송하는 주 통로입니다.</span><span class="sxs-lookup"><span data-stu-id="77b11-103">The <xref:System.Data.Linq.DataContext> is the main conduit by which you connect to a database, retrieve objects from it, and submit changes back to it.</span></span> <span data-ttu-id="77b11-104"><xref:System.Data.Linq.DataContext> ADO.NET<xref:System.Data.SqlClient.SqlConnection>를 사용 하는 것 처럼를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="77b11-104">You use the <xref:System.Data.Linq.DataContext> just as you would use an ADO.NET <xref:System.Data.SqlClient.SqlConnection>.</span></span> <span data-ttu-id="77b11-105">실제로 <xref:System.Data.Linq.DataContext>는 사용자가 지정한 연결 또는 연결 문자열을 통해 초기화됩니다.</span><span class="sxs-lookup"><span data-stu-id="77b11-105">In fact, the <xref:System.Data.Linq.DataContext> is initialized with a connection or connection string that you supply.</span></span> <span data-ttu-id="77b11-106">자세한 내용은 [DataContext 메서드 (O/R 디자이너)](/visualstudio/data-tools/datacontext-methods-o-r-designer)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="77b11-106">For more information, see [DataContext Methods (O/R Designer)](/visualstudio/data-tools/datacontext-methods-o-r-designer).</span></span>  
  
 <span data-ttu-id="77b11-107"><xref:System.Data.Linq.DataContext>의 용도는 개체에 대한 요청을 데이터베이스에 적용할 수 있는 SQL 쿼리로 변환한 다음 결과 외의 개체를 어셈블하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="77b11-107">The purpose of the <xref:System.Data.Linq.DataContext> is to translate your requests for objects into SQL queries to be made against the database, and then to assemble objects out of the results.</span></span> <span data-ttu-id="77b11-108"><xref:System.Data.Linq.DataContext>에서는 [!INCLUDE[vbteclinqext](../../../../../../includes/vbteclinqext-md.md)] 및 `Where` 등의 표준 쿼리 연산자와 같은 동일한 연산자 패턴을 구현하여 `Select`를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="77b11-108">The <xref:System.Data.Linq.DataContext> enables [!INCLUDE[vbteclinqext](../../../../../../includes/vbteclinqext-md.md)] by implementing the same operator pattern as the Standard Query Operators, such as `Where` and `Select`.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="77b11-109">보안 연결을 유지 관리하는 것이 가장 중요합니다.</span><span class="sxs-lookup"><span data-stu-id="77b11-109">Maintaining a secure connection is of the highest importance.</span></span> <span data-ttu-id="77b11-110">자세한 내용은 [LINQ to SQL의 보안](../../../../../../docs/framework/data/adonet/sql/linq/security-in-linq-to-sql.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="77b11-110">For more information, see [Security in LINQ to SQL](../../../../../../docs/framework/data/adonet/sql/linq/security-in-linq-to-sql.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="77b11-111">예제</span><span class="sxs-lookup"><span data-stu-id="77b11-111">Example</span></span>  
 <span data-ttu-id="77b11-112">다음 예제에서는 <xref:System.Data.Linq.DataContext>를 사용하여 Northwind 샘플 데이터베이스에 연결한 다음 도시가 London인 고객의 행을 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="77b11-112">In the following example, the <xref:System.Data.Linq.DataContext> is used to connect to the Northwind sample database and to retrieve rows of customers whose city is London.</span></span>  
  
 [!code-csharp[DLinqCommunicatingWithDatabase#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqCommunicatingWithDatabase/cs/Program.cs#1)]
 [!code-vb[DLinqCommunicatingWithDatabase#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqCommunicatingWithDatabase/vb/Module1.vb#1)]  
  
 <span data-ttu-id="77b11-113">각 데이터베이스 테이블은 해당 테이블을 식별할 수 있는 엔터티 클래스를 사용하여 `Table` 메서드를 통해 사용할 수 있는 <xref:System.Data.Linq.DataContext.GetTable%2A> 컬렉션으로 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="77b11-113">Each database table is represented as a `Table` collection available by way of the <xref:System.Data.Linq.DataContext.GetTable%2A> method, by using the entity class to identify it.</span></span>  
  
## <a name="example"></a><span data-ttu-id="77b11-114">예제</span><span class="sxs-lookup"><span data-stu-id="77b11-114">Example</span></span>  
 <span data-ttu-id="77b11-115">가장 좋은 방법은 기본 <xref:System.Data.Linq.DataContext> 클래스와 <xref:System.Data.Linq.DataContext> 메서드를 사용하는 대신 강력한 형식의 <xref:System.Data.Linq.DataContext.GetTable%2A>를 선언하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="77b11-115">Best practice is to declare a strongly typed <xref:System.Data.Linq.DataContext> instead of relying on the basic <xref:System.Data.Linq.DataContext> class and the <xref:System.Data.Linq.DataContext.GetTable%2A> method.</span></span> <span data-ttu-id="77b11-116">강력한 형식의 <xref:System.Data.Linq.DataContext>에서는 다음 예제와 같이 `Table` 컬렉션을 컨텍스트의 멤버로 선언합니다.</span><span class="sxs-lookup"><span data-stu-id="77b11-116">A strongly typed <xref:System.Data.Linq.DataContext> declares all `Table` collections as members of the context, as in the following example.</span></span>  
  
 [!code-csharp[DLinqCommunicatingWithDatabase#2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqCommunicatingWithDatabase/cs/Program.cs#2)]
 [!code-vb[DLinqCommunicatingWithDatabase#2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqCommunicatingWithDatabase/vb/Module1.vb#2)]  
  
 <span data-ttu-id="77b11-117">그런 다음 London에 있는 고객에 대한 쿼리를 다음과 같이 더 간단하게 표현할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="77b11-117">You can then express the query for customers from London more simply as:</span></span>  
  
 [!code-csharp[DLinqCommunicatingWithDatabase#5](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqCommunicatingWithDatabase/cs/Program.cs#5)]
 [!code-vb[DLinqCommunicatingWithDatabase#5](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqCommunicatingWithDatabase/vb/Module1.vb#5)]  
  
## <a name="see-also"></a><span data-ttu-id="77b11-118">참고자료</span><span class="sxs-lookup"><span data-stu-id="77b11-118">See also</span></span>

- [<span data-ttu-id="77b11-119">데이터베이스와 통신</span><span class="sxs-lookup"><span data-stu-id="77b11-119">Communicating with the Database</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/communicating-with-the-database.md)
