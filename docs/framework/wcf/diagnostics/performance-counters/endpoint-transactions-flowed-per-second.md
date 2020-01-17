---
title: '엔드포인트: Transactions Flowed Per Second'
ms.date: 03/30/2017
ms.assetid: 0f370ff1-a913-450b-bccb-c279ad165b3d
ms.openlocfilehash: 39458dcb6ac033fd5084b5f2e760e0e26c345da7
ms.sourcegitcommit: 5d769956a04b6d68484dd717077fabc191c21da5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/17/2020
ms.locfileid: "76163555"
---
# <a name="endpoint-transactions-flowed-per-second"></a>엔드포인트: Transactions Flowed Per Second
카운터 이름: Transactions Flowed Per Second  
  
## <a name="description"></a>설명  
 이 엔드포인트에서 작업에 적용된 초당 트랜잭션의 수입니다. 엔드포인트에 전송된 메시지에 트랜잭션 ID가 있을 때마다 이 카운터가 증가합니다.  
  
 이 카운터는 다음 수식을 사용 하 여 값을 계산 하는 성능 카운터 유형 [PERF_COUNTER_COUNTER](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2003/cc740048(v=ws.10))입니다.  
  
 (N 1 - N 0 ) / ( (D 1 -D 0 ) / F)
