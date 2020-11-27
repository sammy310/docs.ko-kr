---
title: '엔드포인트: Calls Failed Per Second'
ms.date: 03/30/2017
ms.assetid: bcbe9da4-c8dd-4e27-b630-11611adc7580
ms.openlocfilehash: 0aeafa3d273ae22d9bbfe5e3edbac80c6e4851bd
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96271255"
---
# <a name="endpoint-calls-failed-per-second"></a>엔드포인트: Calls Failed Per Second

카운터 이름: Calls Failed Per Second  
  
## <a name="description"></a>Description  

 처리되지 않은 예외가 있고 초당 이 엔드포인트에서 받은 호출 수입니다.  
  
 이 카운터는 다음 수식을 사용 하 여 값을 계산 하는 성능 카운터 유형 [PERF_COUNTER_COUNTER](/previous-versions/windows/it-pro/windows-server-2003/cc740048(v=ws.10))입니다.  
  
 (N 1 - N 0 ) / ( (D 1 -D 0 ) / F)  
  
 이 카운터는 이 엔드포인트에서 처리되지 않은 예외가 발생할 때마다 증가됩니다.  
  
## <a name="see-also"></a>참고 항목

- [계약 및 서비스에서 오류 지정 및 처리](../../specifying-and-handling-faults-in-contracts-and-services.md)
