---
title: 지원되지 않는 기능
ms.date: 03/30/2017
ms.assetid: e480cfb5-697e-42c8-bed5-9264c945c4f9
ms.openlocfilehash: 18a1a8f33a9360b4299648bcd329f4c5f2e7de88
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61917560"
---
# <a name="unsupported-functionality"></a>지원되지 않는 기능
LINQ to SQL에서 다음 SQL 기능은 기존 CLR(공용 언어 런타임) 및 .NET Framework 구문의 트랜잭션을 통해 노출될 수 없습니다.  
  
-   `STDDEV`  
  
-   `LIKE`  
  
     `LIKE`는 직접 변환을 통해 지원되지 않지만 유사한 기능이 <xref:System.Data.Linq.SqlClient.SqlMethods> 클래스에 있습니다. 자세한 내용은 <xref:System.Data.Linq.SqlClient.SqlMethods.Like%2A?displayProperty=nameWithType>을 참조하세요.  
  
-   `DATEDIFF`  
  
     LINQ to SQL에서는 `DATEDIFF`를 제한적으로 지원합니다. 유사한 기능은 <xref:System.Data.Linq.SqlClient.SqlMethods> 클래스에 있습니다.  
  
-   `ROUND`  
  
     LINQ to SQL에서는 `ROUND`를 제한적으로 지원합니다. 자세한 내용은 [System.Math 메서드](system-math-methods.md)합니다.  
  
## <a name="see-also"></a>참고자료

- [데이터 형식 및 함수](data-types-and-functions.md)
