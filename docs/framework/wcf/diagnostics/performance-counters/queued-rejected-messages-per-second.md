---
description: '자세히 알아보기: 초당 거부 된 지연 메시지 수'
title: Queued Rejected Messages Per Second
ms.date: 03/30/2017
ms.assetid: 77ea9aa3-b9e2-4a1d-a65e-5ca115ba0567
ms.openlocfilehash: d0d227a26a49921449786d2c9f885fac13a82bde
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99744073"
---
# <a name="queued-rejected-messages-per-second"></a>Queued Rejected Messages Per Second

카운터 이름: Queued Messages Rejected Per Second  
  
## <a name="description"></a>설명  

 초당 이 서비스에 대기 중인 전송에 의해 거부된 메시지의 수입니다.  
  
 이 카운터는 다음 수식을 사용 하 여 값을 계산 하는 성능 카운터 유형 [PERF_COUNTER_COUNTER](/previous-versions/windows/it-pro/windows-server-2003/cc740048(v=ws.10))입니다.  
  
 (N 1 - N 0 ) / ( (D 1 -D 0 ) / F)
