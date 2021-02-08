---
description: '자세한 정보: 초당 중단 된 트랜잭션 작업'
title: Transacted Operations Aborted Per Second
ms.date: 03/30/2017
ms.assetid: 19fc993f-2b3d-4898-852e-3b98ec2153a5
ms.openlocfilehash: de130c18e065e48ed7ac18442b2bc5f82c2f6861
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99771199"
---
# <a name="transacted-operations-aborted-per-second"></a>Transacted Operations Aborted Per Second

카운터 이름: Transacted Operations Aborted Per Second  
  
## <a name="description"></a>설명  

 초당 이 서비스에서 중단된 트랜잭션 작업 수입니다.  
  
 이 카운터는 다음 수식을 사용 하 여 값을 계산 하는 성능 카운터 유형 [PERF_COUNTER_COUNTER](/previous-versions/windows/it-pro/windows-server-2003/cc740048(v=ws.10))입니다.  
  
 (N 1 - N 0 ) / ( (D 1 -D 0 ) / F)
