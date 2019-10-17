---
title: '엔드포인트: Calls Failed Per Second'
ms.date: 03/30/2017
ms.assetid: bcbe9da4-c8dd-4e27-b630-11611adc7580
ms.openlocfilehash: 9634f8a170bb2fae2f15c3f00dcabb95d512c74e
ms.sourcegitcommit: 628e8147ca10187488e6407dab4c4e6ebe0cac47
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/15/2019
ms.locfileid: "72321454"
---
# <a name="endpoint-calls-failed-per-second"></a>엔드포인트: Calls Failed Per Second
카운터 이름: Calls Failed Per Second  
  
## <a name="description"></a>설명  
 처리되지 않은 예외가 있고 초당 이 엔드포인트에서 받은 호출 수입니다.  
  
 이 카운터는 다음 수식을 사용 하 여 값을 계산 하는 성능 카운터 형식 [PERF_COUNTER_COUNTER](https://go.microsoft.com/fwlink/?LinkID=94649)입니다.  
  
 (N 1 - N 0 ) / ( (D 1 -D 0 ) / F)  
  
 이 카운터는 이 엔드포인트에서 처리되지 않은 예외가 발생할 때마다 증가됩니다.  
  
## <a name="see-also"></a>참조

- [계약 및 서비스에서 오류 지정 및 처리](../../specifying-and-handling-faults-in-contracts-and-services.md)
