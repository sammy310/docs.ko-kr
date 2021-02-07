---
description: '자세히 알아보기: 방법: Navigate 연산자를 사용 하 여 관계 탐색'
title: '방법: 탐색 연산자로 관계 탐색'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 79996d2d-9b03-4a9d-82cc-7c5e7c2ad93d
ms.openlocfilehash: ff419a959c2ec895a238d37caeedcf1f06812050
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99697532"
---
# <a name="how-to-navigate-relationships-with-the-navigate-operator"></a><span data-ttu-id="1457e-103">방법: 탐색 연산자로 관계 탐색</span><span class="sxs-lookup"><span data-stu-id="1457e-103">How to: Navigate Relationships with the Navigate Operator</span></span>

<span data-ttu-id="1457e-104">이 항목에서는 <xref:System.Data.EntityClient.EntityCommand> 개체를 사용하여 개념적 모델에 대해 명령을 실행하는 방법과 <xref:System.Data.Metadata.Edm.RefType>를 사용하여 <xref:System.Data.EntityClient.EntityDataReader> 결과를 검색하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="1457e-104">This topic shows how to execute a command against a conceptual model by using an <xref:System.Data.EntityClient.EntityCommand> object, and how to retrieve the <xref:System.Data.Metadata.Edm.RefType> results by using an <xref:System.Data.EntityClient.EntityDataReader>.</span></span>  
  
### <a name="to-run-the-code-in-this-example"></a><span data-ttu-id="1457e-105">이 예제의 코드를 실행하려면</span><span class="sxs-lookup"><span data-stu-id="1457e-105">To run the code in this example</span></span>  
  
1. <span data-ttu-id="1457e-106">프로젝트에 [AdventureWorks Sales 모델](https://github.com/Microsoft/sql-server-samples/releases/tag/adventureworks) 을 추가 하 고 Entity Framework를 사용 하도록 프로젝트를 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="1457e-106">Add the [AdventureWorks Sales Model](https://github.com/Microsoft/sql-server-samples/releases/tag/adventureworks) to your project and configure your project to use the Entity Framework.</span></span> <span data-ttu-id="1457e-107">자세한 내용은 [방법: 엔터티 데이터 모델 마법사 사용](/previous-versions/dotnet/netframework-4.0/bb738677(v=vs.100))을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="1457e-107">For more information, see [How to: Use the Entity Data Model Wizard](/previous-versions/dotnet/netframework-4.0/bb738677(v=vs.100)).</span></span>  
  
2. <span data-ttu-id="1457e-108">애플리케이션의 코드 페이지에서 다음 `using` 문(Visual Basic에서는 `Imports`)을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="1457e-108">In the code page for your application, add the following `using` statements (`Imports` in Visual Basic):</span></span>  
  
     [!code-csharp[DP EntityServices Concepts#Namespaces](../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/source.cs#namespaces)]
     [!code-vb[DP EntityServices Concepts#Namespaces](../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp entityservices concepts/vb/source.vb#namespaces)]  
  
## <a name="example"></a><span data-ttu-id="1457e-109">예제</span><span class="sxs-lookup"><span data-stu-id="1457e-109">Example</span></span>  

 <span data-ttu-id="1457e-110">다음 예에서는 Navigate 연산자를 사용 하 여에서 관계를 탐색 하는 방법을 보여 줍니다 [!INCLUDE[esql](../../../../../includes/esql-md.md)] . [](./language-reference/navigate-entity-sql.md)</span><span class="sxs-lookup"><span data-stu-id="1457e-110">The following example shows how to navigate relationships in [!INCLUDE[esql](../../../../../includes/esql-md.md)] by using the [NAVIGATE](./language-reference/navigate-entity-sql.md) operator.</span></span> <span data-ttu-id="1457e-111">`Navigate`연산자는 엔터티 인스턴스, 관계 형식, 관계 끝 및 관계 시작과 같은 매개 변수를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="1457e-111">The `Navigate` operator takes the following parameters: an instance of an entity, the relationship type, the end of the relationship, and the beginning of the relationship.</span></span> <span data-ttu-id="1457e-112">필요에 따라 엔터티의 인스턴스와 관계 유형만 연산자에 전달할 수 있습니다 `Navigate` .</span><span class="sxs-lookup"><span data-stu-id="1457e-112">Optionally, you can pass only an instance of an entity and the relationship type to the `Navigate` operator.</span></span>  
  
 [!code-csharp[DP EntityServices Concepts#NavigateWithNavOperatorWithEntityCommand](../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/source.cs#navigatewithnavoperatorwithentitycommand)]
 [!code-vb[DP EntityServices Concepts#NavigateWithNavOperatorWithEntityCommand](../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp entityservices concepts/vb/source.vb#navigatewithnavoperatorwithentitycommand)]  
  
## <a name="see-also"></a><span data-ttu-id="1457e-113">참고 항목</span><span class="sxs-lookup"><span data-stu-id="1457e-113">See also</span></span>

- [<span data-ttu-id="1457e-114">Entity Framework용 EntityClient 공급자</span><span class="sxs-lookup"><span data-stu-id="1457e-114">EntityClient Provider for the Entity Framework</span></span>](entityclient-provider-for-the-entity-framework.md)
- [<span data-ttu-id="1457e-115">Entity SQL 언어</span><span class="sxs-lookup"><span data-stu-id="1457e-115">Entity SQL Language</span></span>](./language-reference/entity-sql-language.md)
