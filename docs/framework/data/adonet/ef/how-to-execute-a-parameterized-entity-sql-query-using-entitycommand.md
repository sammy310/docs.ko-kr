---
title: '방법: EntityCommand를 사용하여 매개 변수가 있는 Entity SQL 쿼리 실행'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: e93fea43-7e03-4d7d-9fee-2517b8b88cba
ms.openlocfilehash: aa750ef088ee045c8d1045b2509d8fc4bde014ce
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/10/2019
ms.locfileid: "70854632"
---
# <a name="how-to-execute-a-parameterized-entity-sql-query-using-entitycommand"></a><span data-ttu-id="822b3-102">방법: EntityCommand를 사용하여 매개 변수가 있는 Entity SQL 쿼리 실행</span><span class="sxs-lookup"><span data-stu-id="822b3-102">How to: Execute a Parameterized Entity SQL Query Using EntityCommand</span></span>
<span data-ttu-id="822b3-103">이 항목에서는 <xref:System.Data.EntityClient.EntityCommand> 개체를 사용 하 [!INCLUDE[esql](../../../../../includes/esql-md.md)] 여 매개 변수가 있는 쿼리를 실행 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="822b3-103">This topic shows how to execute an [!INCLUDE[esql](../../../../../includes/esql-md.md)] query that has parameters by using an <xref:System.Data.EntityClient.EntityCommand> object.</span></span>  
  
### <a name="to-run-the-code-in-this-example"></a><span data-ttu-id="822b3-104">이 예제의 코드를 실행하려면</span><span class="sxs-lookup"><span data-stu-id="822b3-104">To run the code in this example</span></span>  
  
1. <span data-ttu-id="822b3-105">프로젝트에 [AdventureWorks Sales 모델](https://github.com/Microsoft/sql-server-samples/releases/tag/adventureworks) 을 추가 하 고 Entity Framework를 사용 하도록 프로젝트를 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="822b3-105">Add the [AdventureWorks Sales Model](https://github.com/Microsoft/sql-server-samples/releases/tag/adventureworks) to your project and configure your project to use the Entity Framework.</span></span> <span data-ttu-id="822b3-106">자세한 내용은 [방법: 엔터티 데이터 모델 마법사](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb738677(v=vs.100))를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="822b3-106">For more information, see [How to: Use the Entity Data Model Wizard](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb738677(v=vs.100)).</span></span>  
  
2. <span data-ttu-id="822b3-107">애플리케이션의 코드 페이지에서 다음 `using` 문(Visual Basic에서는 `Imports`)을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="822b3-107">In the code page for your application, add the following `using` statements (`Imports` in Visual Basic):</span></span>  
  
     [!code-csharp[DP EntityServices Concepts#Namespaces](../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/source.cs#namespaces)]
     [!code-vb[DP EntityServices Concepts#Namespaces](../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp entityservices concepts/vb/source.vb#namespaces)]  
  
## <a name="example"></a><span data-ttu-id="822b3-108">예제</span><span class="sxs-lookup"><span data-stu-id="822b3-108">Example</span></span>  
 <span data-ttu-id="822b3-109">다음 예제에서는 두 개의 매개 변수가 있는 쿼리 문자열을 생성하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="822b3-109">The following example shows how to construct a query string with two parameters.</span></span> <span data-ttu-id="822b3-110">그런 다음 <xref:System.Data.EntityClient.EntityCommand>를 만들고 두 매개 변수를 이 <xref:System.Data.EntityClient.EntityParameter>의 <xref:System.Data.EntityClient.EntityCommand> 컬렉션에 추가한 후 `Contact` 항목 컬렉션을 반복합니다.</span><span class="sxs-lookup"><span data-stu-id="822b3-110">It then creates an <xref:System.Data.EntityClient.EntityCommand>, adds two parameters to the <xref:System.Data.EntityClient.EntityParameter> collection of that <xref:System.Data.EntityClient.EntityCommand>, and iterates through the collection of `Contact` items.</span></span>  
  
 [!code-csharp[DP EntityServices Concepts#ParameterizedQueryWithEntityCommand](../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/source.cs#parameterizedquerywithentitycommand)]
 [!code-vb[DP EntityServices Concepts#ParameterizedQueryWithEntityCommand](../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp entityservices concepts/vb/source.vb#parameterizedquerywithentitycommand)]  
  
## <a name="see-also"></a><span data-ttu-id="822b3-111">참고자료</span><span class="sxs-lookup"><span data-stu-id="822b3-111">See also</span></span>

- <span data-ttu-id="822b3-112">[방법: 매개 변수가 있는 쿼리 실행](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb738521(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="822b3-112">[How to: Execute a Parameterized Query](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb738521(v=vs.100))</span></span>
- [<span data-ttu-id="822b3-113">Entity SQL 언어</span><span class="sxs-lookup"><span data-stu-id="822b3-113">Entity SQL Language</span></span>](./language-reference/entity-sql-language.md)
