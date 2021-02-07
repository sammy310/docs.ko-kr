---
description: '자세한 정보: 저장 프로시저를 독점적으로 사용 하 여 작업 사용자 지정'
title: 단독으로 저장 프로시저를 사용하여 작업 사용자 지정
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 441e8ef3-998c-4d12-8825-ce66a178f90f
ms.openlocfilehash: 4ddcc6b4face1abccb502e12617105a734bb5f0b
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99729551"
---
# <a name="customizing-operations-by-using-stored-procedures-exclusively"></a><span data-ttu-id="ca578-103">단독으로 저장 프로시저를 사용하여 작업 사용자 지정</span><span class="sxs-lookup"><span data-stu-id="ca578-103">Customizing Operations by Using Stored Procedures Exclusively</span></span>

<span data-ttu-id="ca578-104">저장 프로시저만을 사용한 데이터 액세스는 일반적인 시나리오입니다.</span><span class="sxs-lookup"><span data-stu-id="ca578-104">Access to data by using only stored procedures is a common scenario.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ca578-105">예제</span><span class="sxs-lookup"><span data-stu-id="ca578-105">Example</span></span>  
  
### <a name="description"></a><span data-ttu-id="ca578-106">설명</span><span class="sxs-lookup"><span data-stu-id="ca578-106">Description</span></span>  

 <span data-ttu-id="ca578-107">저장 프로시저를 [사용 하 여 작업 사용자 지정](customizing-operations-by-using-stored-procedures.md) 에 제공 된 예를 수정할 수 있습니다. 첫 번째 쿼리 (동적 SQL 실행이 발생 하는 경우)를 저장 프로시저를 래핑하는 메서드 호출로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="ca578-107">You can modify the example provided in [Customizing Operations By Using Stored Procedures](customizing-operations-by-using-stored-procedures.md) by replacing even the first query (which causes dynamic SQL execution) with a method call that wraps a stored procedure.</span></span>  
  
 <span data-ttu-id="ca578-108">다음 예제와 같이 `CustomersByCity`는 메서드로 가정합니다.</span><span class="sxs-lookup"><span data-stu-id="ca578-108">Assume `CustomersByCity` is the method, as in the following example.</span></span>  
  
### <a name="code"></a><span data-ttu-id="ca578-109">코드</span><span class="sxs-lookup"><span data-stu-id="ca578-109">Code</span></span>  

 [!code-csharp[DLinqOverrideDefaultSproc#4](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqOverrideDefaultSproc/cs/northwind.cs#4)]
 [!code-vb[DLinqOverrideDefaultSproc#4](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqOverrideDefaultSproc/vb/northwind.vb#4)]  
  
 <span data-ttu-id="ca578-110">다음 코드는 동적 SQL 없이 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="ca578-110">The following code executes without any dynamic SQL.</span></span>  
  
 [!code-csharp[DLinqOverrideDefaultSproc#5](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqOverrideDefaultSproc/cs/Program.cs#5)]
 [!code-vb[DLinqOverrideDefaultSproc#5](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqOverrideDefaultSproc/vb/Module1.vb#5)]  
  
## <a name="see-also"></a><span data-ttu-id="ca578-111">참고 항목</span><span class="sxs-lookup"><span data-stu-id="ca578-111">See also</span></span>

- [<span data-ttu-id="ca578-112">기본 동작 재정의에서 개발자의 책임</span><span class="sxs-lookup"><span data-stu-id="ca578-112">Responsibilities of the Developer In Overriding Default Behavior</span></span>](responsibilities-of-the-developer-in-overriding-default-behavior.md)
