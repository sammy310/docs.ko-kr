---
title: '방법: PrimitiveType 결과를 반환하는 쿼리 실행'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 7139d585-4034-4dfa-916f-2120a8b72792
ms.openlocfilehash: ef212b31e9a7eda5adb037ff2b91f298ae6e948e
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/15/2020
ms.locfileid: "90546759"
---
# <a name="how-to-execute-a-query-that-returns-primitivetype-results"></a><span data-ttu-id="10b4c-102">방법: PrimitiveType 결과를 반환하는 쿼리 실행</span><span class="sxs-lookup"><span data-stu-id="10b4c-102">How to: Execute a Query that Returns PrimitiveType Results</span></span>
<span data-ttu-id="10b4c-103">이 항목에서는 <xref:System.Data.EntityClient.EntityCommand>를 사용하여 개념적 모델에 대해 명령을 실행하는 방법과 <xref:System.Data.Metadata.Edm.PrimitiveType>를 사용하여 <xref:System.Data.EntityClient.EntityDataReader> 결과를 검색하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="10b4c-103">This topic shows how to execute a command against a conceptual model by using an <xref:System.Data.EntityClient.EntityCommand>, and how to retrieve the <xref:System.Data.Metadata.Edm.PrimitiveType> results by using an <xref:System.Data.EntityClient.EntityDataReader>.</span></span>  
  
### <a name="to-run-the-code-in-this-example"></a><span data-ttu-id="10b4c-104">이 예제의 코드를 실행하려면</span><span class="sxs-lookup"><span data-stu-id="10b4c-104">To run the code in this example</span></span>  
  
1. <span data-ttu-id="10b4c-105">프로젝트에 [AdventureWorks Sales 모델](https://github.com/Microsoft/sql-server-samples/releases/tag/adventureworks) 을 추가 하 고 Entity Framework를 사용 하도록 프로젝트를 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="10b4c-105">Add the [AdventureWorks Sales Model](https://github.com/Microsoft/sql-server-samples/releases/tag/adventureworks) to your project and configure your project to use the Entity Framework.</span></span> <span data-ttu-id="10b4c-106">자세한 내용은 [방법: 엔터티 데이터 모델 마법사 사용](/previous-versions/dotnet/netframework-4.0/bb738677(v=vs.100))을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="10b4c-106">For more information, see [How to: Use the Entity Data Model Wizard](/previous-versions/dotnet/netframework-4.0/bb738677(v=vs.100)).</span></span>  
  
2. <span data-ttu-id="10b4c-107">애플리케이션의 코드 페이지에서 다음 `using` 문(Visual Basic에서는 `Imports`)을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="10b4c-107">In the code page for your application, add the following `using` statements (`Imports` in Visual Basic):</span></span>  
  
     [!code-csharp[DP EntityServices Concepts#Namespaces](../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/source.cs#namespaces)]
     [!code-vb[DP EntityServices Concepts#Namespaces](../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp entityservices concepts/vb/source.vb#namespaces)]  
  
## <a name="example"></a><span data-ttu-id="10b4c-108">예제</span><span class="sxs-lookup"><span data-stu-id="10b4c-108">Example</span></span>  
 <span data-ttu-id="10b4c-109">이 예제에서는 <xref:System.Data.Metadata.Edm.PrimitiveType> 결과를 반환하는 쿼리를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="10b4c-109">This example executes a query that returns a <xref:System.Data.Metadata.Edm.PrimitiveType> result.</span></span> <span data-ttu-id="10b4c-110">다음 쿼리를 `ExecutePrimitiveTypeQuery` 함수에 인수로 전달하면 이 함수는 모든 `Products`의 평균 가격을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="10b4c-110">If you pass the following query as an argument to the `ExecutePrimitiveTypeQuery` function, the function displays the average list price of all `Products`:</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#EDM_AVG](../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#edm_avg)]  
  
 <span data-ttu-id="10b4c-111">다음과 같은 매개 변수가 있는 쿼리를 전달하는 경우 <xref:System.Data.EntityClient.EntityParameter> 개체를 <xref:System.Data.EntityClient.EntityCommand.Parameters%2A> 개체의 <xref:System.Data.EntityClient.EntityCommand> 속성에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="10b4c-111">If you pass a parameterized query, like the following, <xref:System.Data.EntityClient.EntityParameter> objects to the <xref:System.Data.EntityClient.EntityCommand.Parameters%2A> property on the <xref:System.Data.EntityClient.EntityCommand> object.</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#CASE_WHEN_THEN_ELSE](../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#case_when_then_else)]  
  
 [!code-csharp[DP EntityServices Concepts#eSQLPrimitiveTypes](../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/source.cs#esqlprimitivetypes)]
 [!code-vb[DP EntityServices Concepts#eSQLPrimitiveTypes](../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp entityservices concepts/vb/source.vb#esqlprimitivetypes)]  
  
## <a name="see-also"></a><span data-ttu-id="10b4c-112">참조</span><span class="sxs-lookup"><span data-stu-id="10b4c-112">See also</span></span>

- [<span data-ttu-id="10b4c-113">엔터티 SQL 참조</span><span class="sxs-lookup"><span data-stu-id="10b4c-113">Entity SQL Reference</span></span>](./language-reference/entity-sql-reference.md)
- [<span data-ttu-id="10b4c-114">Entity Framework용 EntityClient 공급자</span><span class="sxs-lookup"><span data-stu-id="10b4c-114">EntityClient Provider for the Entity Framework</span></span>](entityclient-provider-for-the-entity-framework.md)
