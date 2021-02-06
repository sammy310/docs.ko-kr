---
description: '자세한 정보: 트랜잭션 작업 커밋됨/초'
title: Transacted Operations Committed Per Second
ms.date: 03/30/2017
ms.assetid: 7318921b-47c4-4c8c-9fdd-41a92061c53f
ms.openlocfilehash: 019906cccc527a032d91eb20328eddbb6d9aada8
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99655086"
---
# <a name="transacted-operations-committed-per-second"></a>Transacted Operations Committed Per Second

카운터 이름: Transacted Operations Committed Per Second  
  
## <a name="description"></a>설명  

 초당 이 서비스에서 커밋된 트랜잭션 작업 수입니다.  
  
 이 카운터는 다음 수식을 사용 하 여 값을 계산 하는 성능 카운터 유형 [PERF_COUNTER_COUNTER](/previous-versions/windows/it-pro/windows-server-2003/cc740048(v=ws.10))입니다.  
  
 (N 1 - N 0 ) / ( (D 1 -D 0 ) / F)
