---
title: '방법: 스칼라 반환 사용자 정의 함수 사용'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 714e252f-c053-4bbb-b1f3-924111cd4d97
ms.openlocfilehash: dfe82fd50eb3eedeaff9082a4288901f72197795
ms.sourcegitcommit: eff6adb61852369ab690f3f047818c90580e7eb1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/07/2019
ms.locfileid: "72003229"
---
# <a name="how-to-use-scalar-valued-user-defined-functions"></a><span data-ttu-id="e9a42-102">방법: 스칼라 반환 사용자 정의 함수 사용</span><span class="sxs-lookup"><span data-stu-id="e9a42-102">How to: Use Scalar-Valued User-Defined Functions</span></span>
<span data-ttu-id="e9a42-103"><xref:System.Data.Linq.Mapping.FunctionAttribute> 특성을 사용하여 클래스에 정의된 클라이언트 메서드를 사용자 정의 함수에 매핑할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e9a42-103">You can map a client method defined on a class to a user-defined function by using the <xref:System.Data.Linq.Mapping.FunctionAttribute> attribute.</span></span> <span data-ttu-id="e9a42-104">메서드 본문에서는 메서드 호출 목적을 캡처하는 식을 생성하여 해당 식을 변환 및 실행을 위해 <xref:System.Data.Linq.DataContext>로 전달합니다.</span><span class="sxs-lookup"><span data-stu-id="e9a42-104">Note that the body of the method constructs an expression that captures the intent of the method call, and passes that expression to the <xref:System.Data.Linq.DataContext> for translation and execution.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="e9a42-105">함수를 쿼리 외부에서 호출한 경우에만 직접 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="e9a42-105">Direct execution occurs only if the function is called outside a query.</span></span> <span data-ttu-id="e9a42-106">자세한 내용은 [방법: 사용자 정의 함수 인라인 @ no__t-0을 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="e9a42-106">For more information, see [How to: Call User-Defined Functions Inline](how-to-call-user-defined-functions-inline.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="e9a42-107">예제</span><span class="sxs-lookup"><span data-stu-id="e9a42-107">Example</span></span>  
 <span data-ttu-id="e9a42-108">다음 SQL 코드에서는 스칼라 반환 사용자 정의 함수인 `ReverseCustName()`을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="e9a42-108">The following SQL code presents a scalar-valued user-defined function `ReverseCustName()`.</span></span>  
  
```sql  
CREATE FUNCTION ReverseCustName(@string varchar(100))  
RETURNS varchar(100)  
AS  
BEGIN  
    DECLARE @custName varchar(100)  
    -- Implementation left as exercise for users.  
    RETURN @custName  
END  
```  
  
 <span data-ttu-id="e9a42-109">사용자는 이 코드에 대해 다음과 같은 클라이언트 메서드를 매핑할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e9a42-109">You would map a client method such as the following for this code:</span></span>  
  
 [!code-csharp[DLinqUDFS#3](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqUDFS/cs/northwind-tfunc.cs#3)]
 [!code-vb[DLinqUDFS#3](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqUDFS/vb/northwind-tfunc.vb#3)]  
  
## <a name="see-also"></a><span data-ttu-id="e9a42-110">참조</span><span class="sxs-lookup"><span data-stu-id="e9a42-110">See also</span></span>

- [<span data-ttu-id="e9a42-111">사용자 정의 함수</span><span class="sxs-lookup"><span data-stu-id="e9a42-111">User-Defined Functions</span></span>](user-defined-functions.md)
