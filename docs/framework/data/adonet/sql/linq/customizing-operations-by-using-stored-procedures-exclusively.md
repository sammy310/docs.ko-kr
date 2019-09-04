---
title: 단독으로 저장 프로시저를 사용하여 작업 사용자 지정
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 441e8ef3-998c-4d12-8825-ce66a178f90f
ms.openlocfilehash: a242ecdc774d67721aee640e75847317c1b815d6
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/04/2019
ms.locfileid: "70247543"
---
# <a name="customizing-operations-by-using-stored-procedures-exclusively"></a><span data-ttu-id="41569-102">단독으로 저장 프로시저를 사용하여 작업 사용자 지정</span><span class="sxs-lookup"><span data-stu-id="41569-102">Customizing Operations by Using Stored Procedures Exclusively</span></span>
<span data-ttu-id="41569-103">저장 프로시저만을 사용한 데이터 액세스는 일반적인 시나리오입니다.</span><span class="sxs-lookup"><span data-stu-id="41569-103">Access to data by using only stored procedures is a common scenario.</span></span>  
  
## <a name="example"></a><span data-ttu-id="41569-104">예제</span><span class="sxs-lookup"><span data-stu-id="41569-104">Example</span></span>  
  
### <a name="description"></a><span data-ttu-id="41569-105">설명</span><span class="sxs-lookup"><span data-stu-id="41569-105">Description</span></span>  
 <span data-ttu-id="41569-106">저장 프로시저를 [사용 하 여 작업 사용자 지정](customizing-operations-by-using-stored-procedures.md) 에 제공 된 예를 수정할 수 있습니다. 첫 번째 쿼리 (동적 SQL 실행이 발생 하는 경우)를 저장 프로시저를 래핑하는 메서드 호출로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="41569-106">You can modify the example provided in [Customizing Operations By Using Stored Procedures](customizing-operations-by-using-stored-procedures.md) by replacing even the first query (which causes dynamic SQL execution) with a method call that wraps a stored procedure.</span></span>  
  
 <span data-ttu-id="41569-107">다음 예제와 같이 `CustomersByCity`는 메서드로 가정합니다.</span><span class="sxs-lookup"><span data-stu-id="41569-107">Assume `CustomersByCity` is the method, as in the following example.</span></span>  
  
### <a name="code"></a><span data-ttu-id="41569-108">코드</span><span class="sxs-lookup"><span data-stu-id="41569-108">Code</span></span>  
 [!code-csharp[DLinqOverrideDefaultSproc#4](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqOverrideDefaultSproc/cs/northwind.cs#4)]
 [!code-vb[DLinqOverrideDefaultSproc#4](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqOverrideDefaultSproc/vb/northwind.vb#4)]  
  
 <span data-ttu-id="41569-109">다음 코드는 동적 SQL 없이 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="41569-109">The following code executes without any dynamic SQL.</span></span>  
  
 [!code-csharp[DLinqOverrideDefaultSproc#5](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqOverrideDefaultSproc/cs/Program.cs#5)]
 [!code-vb[DLinqOverrideDefaultSproc#5](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqOverrideDefaultSproc/vb/Module1.vb#5)]  
  
## <a name="see-also"></a><span data-ttu-id="41569-110">참고자료</span><span class="sxs-lookup"><span data-stu-id="41569-110">See also</span></span>

- [<span data-ttu-id="41569-111">기본 동작 재정의에서 개발자의 책임</span><span class="sxs-lookup"><span data-stu-id="41569-111">Responsibilities of the Developer In Overriding Default Behavior</span></span>](responsibilities-of-the-developer-in-overriding-default-behavior.md)
