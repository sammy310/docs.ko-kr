---
description: '자세한 정보: Service 성능 카운터'
title: 서비스 성능 카운터
ms.date: 03/30/2017
ms.assetid: 4210f549-31f2-4ea7-99bd-69eaffb98ddf
ms.openlocfilehash: 16f6f2548cf7f92b64264ac606423c69e62cd110
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99686039"
---
# <a name="service-performance-counters"></a>서비스 성능 카운터

서비스 성능 카운터는 서비스 동작을 전반적으로 측정하며 전체 서비스 성능을 진단하는 데 사용할 수 있습니다. 이러한 카운터는 성능 모니터(Perfmon.exe)에서 볼 때 `ServiceModelService 4.0.0.0` 성능 개체 아래에 있습니다. 인스턴스 이름은 다음 패턴으로 지정됩니다.  
  
`ServiceName@ServiceBaseAddress`
  
> [!CAUTION]
> 성능 카운터 인스턴스의 이름 길이에는 제한이 있습니다. WCF (Windows Communication Foundation) 카운터 인스턴스 이름이 최대 길이를 초과 하면 WCF는 인스턴스 이름의 일부를 해시 값으로 바꿉니다.  
  
## <a name="see-also"></a>참고 항목

- [성능 카운터](index.md)
