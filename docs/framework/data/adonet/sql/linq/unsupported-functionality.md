---
description: '자세한 정보: 지원 되지 않는 기능'
title: 지원되지 않는 기능
ms.date: 03/30/2017
ms.assetid: e480cfb5-697e-42c8-bed5-9264c945c4f9
ms.openlocfilehash: 5c44dd4aad2d2ee4ec5e00ce42f4de9400cea478
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99680891"
---
# <a name="unsupported-functionality"></a>지원되지 않는 기능

LINQ to SQL에서 다음 SQL 기능은 기존 CLR(공용 언어 런타임) 및 .NET Framework 구문의 트랜잭션을 통해 노출될 수 없습니다.  
  
- `STDDEV`  
  
- `LIKE`  
  
     `LIKE`는 직접 변환을 통해 지원되지 않지만 유사한 기능이 <xref:System.Data.Linq.SqlClient.SqlMethods> 클래스에 있습니다. 자세한 내용은 <xref:System.Data.Linq.SqlClient.SqlMethods.Like%2A?displayProperty=nameWithType>를 참조하세요.  
  
- `DATEDIFF`  
  
     LINQ to SQL에서는 `DATEDIFF`를 제한적으로 지원합니다. 유사한 기능은 <xref:System.Data.Linq.SqlClient.SqlMethods> 클래스에 있습니다.  
  
- `ROUND`  
  
     LINQ to SQL에서는 `ROUND`를 제한적으로 지원합니다. 자세한 내용은 [System.web 메서드](system-math-methods.md)를 참조 하세요.  
  
## <a name="see-also"></a>참고 항목

- [데이터 형식 및 함수](data-types-and-functions.md)
