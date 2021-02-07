---
description: '자세한 정보: 서비스: 초당 이동 하는 트랜잭션 수'
title: '서비스: Transactions Flowed Per Second'
ms.date: 03/30/2017
ms.assetid: ec72eb49-2942-4811-91df-d6e5dad81fd8
ms.openlocfilehash: aae78853272b46a97ce25a710039661f36bf7079
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99759499"
---
# <a name="service-transactions-flowed-per-second"></a>서비스: Transactions Flowed Per Second

카운터 이름: Transactions Flowed Per Second  
  
## <a name="description"></a>설명  

 이 서비스에서 작업에 적용된 초당 트랜잭션 수입니다.  
  
 이 카운터는 다음 수식을 사용 하 여 값을 계산 하는 성능 카운터 유형 [PERF_COUNTER_COUNTER](/previous-versions/windows/it-pro/windows-server-2003/cc740048(v=ws.10))입니다.  
  
 (N 1 - N 0 ) / ( (D 1 -D 0 ) / F)
