---
description: '다음에 대 한 자세한 정보: System.web 메서드'
title: System.Math 메서드
ms.date: 03/30/2017
ms.assetid: 0f299521-6f41-4720-bd70-67c93fc50948
ms.openlocfilehash: e97e0a16b6eafdb57f4aaf72d62788e6657afbdc
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99681346"
---
# <a name="systemmath-methods"></a><span data-ttu-id="2db8e-103">System.Math 메서드</span><span class="sxs-lookup"><span data-stu-id="2db8e-103">System.Math Methods</span></span>

[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]<span data-ttu-id="2db8e-104">에서는 다음 <xref:System.Math> 메서드를 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="2db8e-104">does not support the following <xref:System.Math> methods.</span></span>  
  
- <xref:System.Math.DivRem%28System.Int32%2CSystem.Int32%2CSystem.Int32%40%29?displayProperty=nameWithType>  
  
- <xref:System.Math.DivRem%28System.Int64%2CSystem.Int64%2CSystem.Int64%40%29?displayProperty=nameWithType>  
  
- <xref:System.Math.IEEERemainder%28System.Double%2CSystem.Double%29?displayProperty=nameWithType>  
  
## <a name="differences-from-net"></a><span data-ttu-id="2db8e-105">.NET과의 차이점</span><span class="sxs-lookup"><span data-stu-id="2db8e-105">Differences from .NET</span></span>  

 <span data-ttu-id="2db8e-106">.NET Framework의 반올림 구문은 SQL Server와 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="2db8e-106">The .NET Framework has different rounding semantics from SQL Server.</span></span> <span data-ttu-id="2db8e-107"><xref:System.Math.Round%2A>.NET Framework의 메서드는 *은행원의 반올림* 을 수행 합니다. 여기서 0.5로 끝나는 숫자는 다음으로 큰 숫자가 아닌 가장 가까운 짝수로 반올림 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2db8e-107">The <xref:System.Math.Round%2A> method in the .NET Framework performs *Banker's rounding*, where numbers that ends in .5 round to the nearest even digit instead of to the next higher digit.</span></span> <span data-ttu-id="2db8e-108">예를 들어 2.5는 2가 되고 3.5는 4가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2db8e-108">For example, 2.5 rounds to 2, while 3.5 rounds to 4.</span></span> <span data-ttu-id="2db8e-109">이 방법은 많은 데이터 트랜잭션에서 값이 높아질수록 발생할 수 있는 체계적 오차를 방지할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2db8e-109">(This technique helps avoid systematic bias toward higher values in large data transactions.)</span></span>  
  
 <span data-ttu-id="2db8e-110">SQL에서 `ROUND` 함수는 항상 0 이상의 정수 값으로 반올림됩니다.</span><span class="sxs-lookup"><span data-stu-id="2db8e-110">In SQL, the `ROUND` function instead always rounds away from 0.</span></span> <span data-ttu-id="2db8e-111">따라서 2.5의 경우 .NET Framework에서는 2가 되는데 반해 SQL에서는 3이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2db8e-111">Therefore 2.5 rounds to 3, contrasted with its rounding to 2 in the .NET Framework.</span></span>  
  
 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]<span data-ttu-id="2db8e-112">은 SQL `ROUND` 구문을 따르며 은행원의 반올림을 사용하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="2db8e-112">passes through to the SQL `ROUND` semantics and does not try to implement Banker's rounding.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2db8e-113">참고 항목</span><span class="sxs-lookup"><span data-stu-id="2db8e-113">See also</span></span>

- [<span data-ttu-id="2db8e-114">데이터 형식 및 함수</span><span class="sxs-lookup"><span data-stu-id="2db8e-114">Data Types and Functions</span></span>](data-types-and-functions.md)
