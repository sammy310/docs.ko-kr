---
title: Transactions Flowed Per Second
ms.date: 03/30/2017
ms.assetid: b9f661e1-576c-48fc-9fdf-91853e0749e8
ms.openlocfilehash: b47219bd58a9b6c4401baa73177928ddca5b6a8b
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96254144"
---
# <a name="transactions-flowed-per-second"></a>Transactions Flowed Per Second

카운터 이름: Transactions Flowed Per Second  
  
## <a name="description"></a>Description  

 이 작업에 적용된 초당 트랜잭션의 수입니다. 작업에 전송된 메시지에 트랜잭션 ID가 있을 때마다 이 카운터가 증가합니다.  
  
 이 카운터는 다음 수식을 사용 하 여 값을 계산 하는 성능 카운터 유형 [PERF_COUNTER_COUNTER](/previous-versions/windows/it-pro/windows-server-2003/cc740048(v=ws.10))입니다.  
  
 (N 1 - N 0 ) / ( (D 1 -D 0 ) / F)
