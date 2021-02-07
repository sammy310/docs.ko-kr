---
description: '자세히 알아보기: 초당 삭제 된 메시지 큐'
title: Queue Dropped Messages Per Second
ms.date: 03/30/2017
ms.assetid: 74540f52-8762-4147-b5ba-e171180515a3
ms.openlocfilehash: e5959b76795514dec03d6ae4d08ac248994777fa
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99759551"
---
# <a name="queue-dropped-messages-per-second"></a>Queue Dropped Messages Per Second

카운터 이름: Queued Messages Dropped Per Second  
  
## <a name="description"></a>설명  

 초당 이 서비스에 대기 중인 전송에서 손실된 메시지 수입니다.  
  
 이 카운터는 다음 수식을 사용 하 여 값을 계산 하는 성능 카운터 유형 [PERF_COUNTER_COUNTER](/previous-versions/windows/it-pro/windows-server-2003/cc740048(v=ws.10))입니다.  
  
 (N 1 - N 0 ) / ( (D 1 -D 0 ) / F)
