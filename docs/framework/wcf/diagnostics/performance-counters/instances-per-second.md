---
description: '다음에 대 한 자세한 정보: 인스턴스 수/초'
title: Instances Per Second
ms.date: 03/30/2017
ms.assetid: 74579397-1058-4278-80cf-2d00854a480f
ms.openlocfilehash: cfcdd85bef8b1873101c1bbb63ce40bd161a97f4
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99655307"
---
# <a name="instances-per-second"></a>Instances Per Second

카운터 이름: Instances Created Per Second  
  
## <a name="description"></a>설명  

 초당 만들어진 총 서비스 인스턴스 수입니다.  
  
 이 카운터는 다음 수식을 사용 하 여 값을 계산 하는 성능 카운터 유형 [PERF_COUNTER_COUNTER](/previous-versions/windows/it-pro/windows-server-2003/cc740048(v=ws.10))입니다.  
  
 (N 1 - N 0 ) / ( (D 1 -D 0 ) / F)
