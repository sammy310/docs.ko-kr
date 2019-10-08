---
title: '방법: 매개 변수를 사용하는 저장 프로시저 사용'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: b935fd84-cb9c-4205-8c48-658d5db2ec93
ms.openlocfilehash: e9d77cd1dc82e1b103c5f0d9f3f447ed105acaec
ms.sourcegitcommit: eff6adb61852369ab690f3f047818c90580e7eb1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/07/2019
ms.locfileid: "72003251"
---
# <a name="how-to-use-stored-procedures-that-take-parameters"></a><span data-ttu-id="81017-102">방법: 매개 변수를 사용하는 저장 프로시저 사용</span><span class="sxs-lookup"><span data-stu-id="81017-102">How to: Use Stored Procedures that Take Parameters</span></span>
[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]<span data-ttu-id="81017-103">에서는 출력 매개 변수를 참조 매개 변수에 매핑하고 값 형식에 대해 매개 변수를 nullable로 선언합니다.</span><span class="sxs-lookup"><span data-stu-id="81017-103">maps output parameters to reference parameters, and for value types declares the parameter as nullable.</span></span>  
  
 <span data-ttu-id="81017-104">행 집합을 반환 하는 쿼리에서 입력 매개 변수를 사용 하는 방법에 대 한 예는 [How to: 행 집합 @ no__t-0을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="81017-104">For an example of how to use an input parameter in a query that returns a rowset, see [How to: Return Rowsets](how-to-return-rowsets.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="81017-105">예제</span><span class="sxs-lookup"><span data-stu-id="81017-105">Example</span></span>  
 <span data-ttu-id="81017-106">다음 예제에서는 단일 입력 매개 변수(고객 ID)를 사용하여 출력 매개 변수(해당 고객의 총 판매액)를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="81017-106">The following example takes a single input parameter (the customer ID) and returns an out parameter (the total sales for that customer).</span></span>  
  
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
  
## <a name="example"></a><span data-ttu-id="81017-107">예제</span><span class="sxs-lookup"><span data-stu-id="81017-107">Example</span></span>  
 <span data-ttu-id="81017-108">이 저장 프로시저는 다음과 같이 호출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="81017-108">You would call this stored procedure as follows:</span></span>  
  
 [!code-csharp[DLinqSprox#3](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqSprox/cs/Program.cs#3)]
 [!code-vb[DLinqSprox#3](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqSprox/vb/Module1.vb#3)]  
  
## <a name="see-also"></a><span data-ttu-id="81017-109">참조</span><span class="sxs-lookup"><span data-stu-id="81017-109">See also</span></span>

- [<span data-ttu-id="81017-110">저장된 프로시저</span><span class="sxs-lookup"><span data-stu-id="81017-110">Stored Procedures</span></span>](stored-procedures.md)
- [<span data-ttu-id="81017-111">샘플 데이터베이스 다운로드</span><span class="sxs-lookup"><span data-stu-id="81017-111">Downloading Sample Databases</span></span>](downloading-sample-databases.md)
- [<span data-ttu-id="81017-112">Nullable 값 형식 사용</span><span class="sxs-lookup"><span data-stu-id="81017-112">Using Nullable Value Types</span></span>](../../../../../csharp/programming-guide/nullable-types/using-nullable-types.md)
- [<span data-ttu-id="81017-113">Nullable 값 형식</span><span class="sxs-lookup"><span data-stu-id="81017-113">Nullable Value Types</span></span>](../../../../../visual-basic/programming-guide/language-features/data-types/nullable-value-types.md)
