---
description: '자세한 정보: 초당 대기 중인 포이즌 메시지 수'
title: Queued Poison Messages Per Second
ms.date: 03/30/2017
ms.assetid: d193fdd1-02f1-44a0-906e-f632a8f574c3
ms.openlocfilehash: 3240974445debf86ff17187e4c6762b39610bd46
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99744086"
---
# <a name="queued-poison-messages-per-second"></a>Queued Poison Messages Per Second

카운터 이름: Queued Poison Messages Per Second  
  
## <a name="description"></a>설명  

 1초 동안 이 서비스에 대기 중인 전송에 의해 포이즌으로 표시된 메시지 수입니다.  
  
 이 카운터는 다음 수식을 사용 하 여 값을 계산 하는 성능 카운터 유형 [PERF_COUNTER_COUNTER](/previous-versions/windows/it-pro/windows-server-2003/cc740048(v=ws.10))입니다.  
  
 (N 1 - N 0 ) / ( (D 1 -D 0 ) / F)
