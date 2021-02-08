---
description: '자세한 정보: 방법: 매개 변수를 사용 하는 저장 프로시저 사용'
title: '방법: 매개 변수를 사용하는 저장 프로시저 사용'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: b935fd84-cb9c-4205-8c48-658d5db2ec93
ms.openlocfilehash: eaa2e9c602e2e6baae82648a4237d1098e89896a
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99785798"
---
# <a name="how-to-use-stored-procedures-that-take-parameters"></a><span data-ttu-id="9ae79-103">방법: 매개 변수를 사용하는 저장 프로시저 사용</span><span class="sxs-lookup"><span data-stu-id="9ae79-103">How to: Use Stored Procedures that Take Parameters</span></span>

[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]<span data-ttu-id="9ae79-104">에서는 출력 매개 변수를 참조 매개 변수에 매핑하고 값 형식에 대해 매개 변수를 nullable로 선언합니다.</span><span class="sxs-lookup"><span data-stu-id="9ae79-104">maps output parameters to reference parameters, and for value types declares the parameter as nullable.</span></span>  
  
 <span data-ttu-id="9ae79-105">행 집합을 반환 하는 쿼리에서 입력 매개 변수를 사용 하는 방법에 대 한 예제는 [방법: 행 집합 반환](how-to-return-rowsets.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="9ae79-105">For an example of how to use an input parameter in a query that returns a rowset, see [How to: Return Rowsets](how-to-return-rowsets.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="9ae79-106">예제</span><span class="sxs-lookup"><span data-stu-id="9ae79-106">Example</span></span>  

 <span data-ttu-id="9ae79-107">다음 예제에서는 단일 입력 매개 변수(고객 ID)를 사용하여 출력 매개 변수(해당 고객의 총 판매액)를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="9ae79-107">The following example takes a single input parameter (the customer ID) and returns an out parameter (the total sales for that customer).</span></span>  
  
```sql
CREATE PROCEDURE [dbo].[CustOrderTotal]
@CustomerID nchar(5),  
@TotalSales money OUTPUT  
AS  
SELECT @TotalSales = SUM(OD.UNITPRICE*(1-OD.DISCOUNT) * OD.QUANTITY)  
FROM ORDERS O, "ORDER DETAILS" OD  
where O.CUSTOMERID = @CustomerID AND O.ORDERID = OD.ORDERID  
```  
  
 [!code-csharp[DLinqSprox#2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqSprox/cs/northwind-sprox.cs#2)]
 [!code-vb[DLinqSprox#2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqSprox/vb/northwind-sprox.vb#2)]  
  
## <a name="example"></a><span data-ttu-id="9ae79-108">예제</span><span class="sxs-lookup"><span data-stu-id="9ae79-108">Example</span></span>  

 <span data-ttu-id="9ae79-109">이 저장 프로시저는 다음과 같이 호출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9ae79-109">You would call this stored procedure as follows:</span></span>  
  
 [!code-csharp[DLinqSprox#3](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqSprox/cs/Program.cs#3)]
 [!code-vb[DLinqSprox#3](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqSprox/vb/Module1.vb#3)]  
  
## <a name="see-also"></a><span data-ttu-id="9ae79-110">참고 항목</span><span class="sxs-lookup"><span data-stu-id="9ae79-110">See also</span></span>

- [<span data-ttu-id="9ae79-111">저장 프로시저</span><span class="sxs-lookup"><span data-stu-id="9ae79-111">Stored Procedures</span></span>](stored-procedures.md)
- [<span data-ttu-id="9ae79-112">샘플 데이터베이스 다운로드</span><span class="sxs-lookup"><span data-stu-id="9ae79-112">Downloading Sample Databases</span></span>](downloading-sample-databases.md)
- [<span data-ttu-id="9ae79-113">Nullable 값 형식 (c #)</span><span class="sxs-lookup"><span data-stu-id="9ae79-113">Nullable Value Types (C#)</span></span>](../../../../../csharp/language-reference/builtin-types/nullable-value-types.md)
- [<span data-ttu-id="9ae79-114">Nullable 값 형식(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="9ae79-114">Nullable Value Types (Visual Basic)</span></span>](../../../../../visual-basic/programming-guide/language-features/data-types/nullable-value-types.md)
