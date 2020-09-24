---
title: 지원되지 않는 기능
ms.date: 03/30/2017
ms.assetid: e480cfb5-697e-42c8-bed5-9264c945c4f9
ms.openlocfilehash: d4fe3d91b80197d962989cd2d3bc9bb2df6e3ffe
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/24/2020
ms.locfileid: "91164157"
---
# <a name="unsupported-functionality"></a><span data-ttu-id="6daf9-102">지원되지 않는 기능</span><span class="sxs-lookup"><span data-stu-id="6daf9-102">Unsupported Functionality</span></span>

<span data-ttu-id="6daf9-103">LINQ to SQL에서 다음 SQL 기능은 기존 CLR(공용 언어 런타임) 및 .NET Framework 구문의 트랜잭션을 통해 노출될 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="6daf9-103">In LINQ to SQL, the following SQL functionality cannot be exposed through translation of existing common language runtime (CLR) and .NET Framework constructs:</span></span>  
  
- `STDDEV`  
  
- `LIKE`  
  
     <span data-ttu-id="6daf9-104">`LIKE`는 직접 변환을 통해 지원되지 않지만 유사한 기능이 <xref:System.Data.Linq.SqlClient.SqlMethods> 클래스에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6daf9-104">Although `LIKE` is not supported through direct translation, similar functionality exists in the <xref:System.Data.Linq.SqlClient.SqlMethods> class.</span></span> <span data-ttu-id="6daf9-105">자세한 내용은 <xref:System.Data.Linq.SqlClient.SqlMethods.Like%2A?displayProperty=nameWithType>를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="6daf9-105">For more information, see <xref:System.Data.Linq.SqlClient.SqlMethods.Like%2A?displayProperty=nameWithType>.</span></span>  
  
- `DATEDIFF`  
  
     <span data-ttu-id="6daf9-106">LINQ to SQL에서는 `DATEDIFF`를 제한적으로 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="6daf9-106">LINQ to SQL has limited support for `DATEDIFF`.</span></span> <span data-ttu-id="6daf9-107">유사한 기능은 <xref:System.Data.Linq.SqlClient.SqlMethods> 클래스에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6daf9-107">Similar functionality exists in the <xref:System.Data.Linq.SqlClient.SqlMethods> class.</span></span>  
  
- `ROUND`  
  
     <span data-ttu-id="6daf9-108">LINQ to SQL에서는 `ROUND`를 제한적으로 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="6daf9-108">LINQ to SQL has limited support for `ROUND`.</span></span> <span data-ttu-id="6daf9-109">자세한 내용은 [System.web 메서드](system-math-methods.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="6daf9-109">For more information, see [System.Math Methods](system-math-methods.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6daf9-110">참고 항목</span><span class="sxs-lookup"><span data-stu-id="6daf9-110">See also</span></span>

- [<span data-ttu-id="6daf9-111">데이터 형식 및 함수</span><span class="sxs-lookup"><span data-stu-id="6daf9-111">Data Types and Functions</span></span>](data-types-and-functions.md)
