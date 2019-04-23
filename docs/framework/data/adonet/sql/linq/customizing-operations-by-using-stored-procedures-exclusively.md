---
title: 단독으로 저장 프로시저를 사용하여 작업 사용자 지정
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 441e8ef3-998c-4d12-8825-ce66a178f90f
ms.openlocfilehash: 61230ffc5cd055ee64de9d519cdfb4d76c856ca3
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59128650"
---
# <a name="customizing-operations-by-using-stored-procedures-exclusively"></a><span data-ttu-id="08fa4-102">단독으로 저장 프로시저를 사용하여 작업 사용자 지정</span><span class="sxs-lookup"><span data-stu-id="08fa4-102">Customizing Operations by Using Stored Procedures Exclusively</span></span>
<span data-ttu-id="08fa4-103">저장 프로시저만을 사용한 데이터 액세스는 일반적인 시나리오입니다.</span><span class="sxs-lookup"><span data-stu-id="08fa4-103">Access to data by using only stored procedures is a common scenario.</span></span>  
  
## <a name="example"></a><span data-ttu-id="08fa4-104">예제</span><span class="sxs-lookup"><span data-stu-id="08fa4-104">Example</span></span>  
  
### <a name="description"></a><span data-ttu-id="08fa4-105">설명</span><span class="sxs-lookup"><span data-stu-id="08fa4-105">Description</span></span>  
 <span data-ttu-id="08fa4-106">제공 하는 예제를 수정할 수 있습니다 [사용자 지정 작업에서 사용 하 여 저장 프로시저](../../../../../../docs/framework/data/adonet/sql/linq/customizing-operations-by-using-stored-procedures.md) (그러면, 동적 SQL을 실행) 첫 번째 쿼리도 저장된 프로시저를 래핑하는 메서드 호출으로 대체 하 여 합니다.</span><span class="sxs-lookup"><span data-stu-id="08fa4-106">You can modify the example provided in [Customizing Operations By Using Stored Procedures](../../../../../../docs/framework/data/adonet/sql/linq/customizing-operations-by-using-stored-procedures.md) by replacing even the first query (which causes dynamic SQL execution) with a method call that wraps a stored procedure.</span></span>  
  
 <span data-ttu-id="08fa4-107">다음 예제와 같이 `CustomersByCity`는 메서드로 가정합니다.</span><span class="sxs-lookup"><span data-stu-id="08fa4-107">Assume `CustomersByCity` is the method, as in the following example.</span></span>  
  
### <a name="code"></a><span data-ttu-id="08fa4-108">코드</span><span class="sxs-lookup"><span data-stu-id="08fa4-108">Code</span></span>  
 [!code-csharp[DLinqOverrideDefaultSproc#4](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqOverrideDefaultSproc/cs/northwind.cs#4)]
 [!code-vb[DLinqOverrideDefaultSproc#4](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqOverrideDefaultSproc/vb/northwind.vb#4)]  
  
 <span data-ttu-id="08fa4-109">다음 코드는 동적 SQL 없이 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="08fa4-109">The following code executes without any dynamic SQL.</span></span>  
  
 [!code-csharp[DLinqOverrideDefaultSproc#5](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqOverrideDefaultSproc/cs/Program.cs#5)]
 [!code-vb[DLinqOverrideDefaultSproc#5](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqOverrideDefaultSproc/vb/Module1.vb#5)]  
  
## <a name="see-also"></a><span data-ttu-id="08fa4-110">참고자료</span><span class="sxs-lookup"><span data-stu-id="08fa4-110">See also</span></span>

- [<span data-ttu-id="08fa4-111">기본 동작 재정의에서 개발자의 책임</span><span class="sxs-lookup"><span data-stu-id="08fa4-111">Responsibilities of the Developer In Overriding Default Behavior</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/responsibilities-of-the-developer-in-overriding-default-behavior.md)
