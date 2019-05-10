---
title: System.Math 메서드
ms.date: 03/30/2017
ms.assetid: 0f299521-6f41-4720-bd70-67c93fc50948
ms.openlocfilehash: 5200f31bd319bad49651c3096e1c1364a8003377
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/28/2019
ms.locfileid: "64613780"
---
# <a name="systemmath-methods"></a>System.Math 메서드
[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]에서는 다음 <xref:System.Math> 메서드를 지원하지 않습니다.  
  
- <xref:System.Math.DivRem%28System.Int32%2CSystem.Int32%2CSystem.Int32%40%29?displayProperty=nameWithType>  
  
- <xref:System.Math.DivRem%28System.Int64%2CSystem.Int64%2CSystem.Int64%40%29?displayProperty=nameWithType>  
  
- <xref:System.Math.IEEERemainder%28System.Double%2CSystem.Double%29?displayProperty=nameWithType>  
  
## <a name="differences-from-net"></a>.NET과의 차이점  
 .NET Framework의 반올림 구문은 SQL Server와 다릅니다. 합니다 <xref:System.Math.Round%2A> .NET Framework의 메서드가 수행 *Banker rounding*,.5 끝나는 숫자는 반올림 하려면 여기서는 아니라 가장 가까운 짝수 대신 다음 높은 자리를 합니다. 예를 들어 2.5는 2가 되고 3.5는 4가 됩니다. 이 방법은 많은 데이터 트랜잭션에서 값이 높아질수록 발생할 수 있는 체계적 오차를 방지할 수 있습니다.  
  
 SQL에서 `ROUND` 함수는 항상 0 이상의 정수 값으로 반올림됩니다. 따라서 2.5의 경우 .NET Framework에서는 2가 되는데 반해 SQL에서는 3이 됩니다.  
  
 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]은 SQL `ROUND` 구문을 따르며 은행원의 반올림을 사용하지 않습니다.  
  
## <a name="see-also"></a>참고자료

- [데이터 형식 및 함수](../../../../../../docs/framework/data/adonet/sql/linq/data-types-and-functions.md)
