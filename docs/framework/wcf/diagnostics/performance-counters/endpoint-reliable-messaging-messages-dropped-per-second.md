---
title: '엔드포인트: Reliable Messaging Messages Dropped Per Second'
ms.date: 03/30/2017
ms.assetid: ea3c4fc0-1e0f-4863-8879-57bc6c113018
ms.openlocfilehash: 7dc52caea0233953dd72e77e4d662083f4a370e4
ms.sourcegitcommit: 5d769956a04b6d68484dd717077fabc191c21da5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/17/2020
ms.locfileid: "76164049"
---
# <a name="endpoint-reliable-messaging-messages-dropped-per-second"></a>엔드포인트: Reliable Messaging Messages Dropped Per Second
카운터 이름: Reliable Messaging Sessions Dropped Per Second.  
  
## <a name="description"></a>설명  
 이 엔드포인트에서 삭제된 신뢰할 수 있는 메시징 메시지의 초당 총 수입니다.  
  
 이 카운터는 다음 수식을 사용 하 여 값을 계산 하는 성능 카운터 유형 [PERF_COUNTER_COUNTER](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2003/cc740048(v=ws.10))입니다.  
  
 (N 1 - N 0 ) / ( (D 1 -D 0 ) / F)
