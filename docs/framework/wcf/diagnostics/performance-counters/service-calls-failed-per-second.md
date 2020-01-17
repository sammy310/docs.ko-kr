---
title: '서비스: Calls Failed Per Second'
ms.date: 03/30/2017
ms.assetid: 5a2c7939-107d-4f0c-b43c-e02e079e8a9d
ms.openlocfilehash: e165348a71101b21fa66bd4907c43335b1e476e4
ms.sourcegitcommit: 5d769956a04b6d68484dd717077fabc191c21da5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/17/2020
ms.locfileid: "76163984"
---
# <a name="service-calls-failed-per-second"></a>서비스: Calls Failed Per Second
카운터 이름: Calls Failed Per Second  
  
## <a name="description"></a>설명  
 초당 이 서비스에서 받은, 처리되지 않은 예외가 있는 호출 수입니다.  
  
 이 카운터는 다음 수식을 사용 하 여 값을 계산 하는 성능 카운터 유형 [PERF_COUNTER_COUNTER](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2003/cc740048(v=ws.10))입니다.  
  
 (N 1 - N 0 ) / ( (D 1 -D 0 ) / F)  
  
 관리 코드에서 오류 조건이 발생하면 예외가 throw됩니다.  
  
 관리 코드에서 오류 조건이 발생하면 예외가 throw됩니다.  
  
 이 서비스에 처리되지 않은 예외가 있을 때마다 이 카운터가 증가합니다.  
  
## <a name="see-also"></a>참조

- [계약 및 서비스에서 오류 지정 및 처리](../../specifying-and-handling-faults-in-contracts-and-services.md)
