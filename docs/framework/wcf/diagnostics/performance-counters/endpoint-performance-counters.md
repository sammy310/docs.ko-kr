---
description: '자세한 정보: 끝점 성능 카운터'
title: 엔드포인트 성능 카운터
ms.date: 03/30/2017
ms.assetid: 7d44d576-bd4e-453b-8b76-a818ce90b806
ms.openlocfilehash: 60cd94d5d954c87f4b37469688ee809a13fa3cb4
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99771238"
---
# <a name="endpoint-performance-counters"></a>엔드포인트 성능 카운터

엔드포인트 성능 카운터는 엔드포인트가 메시지를 수신하는 방식을 나타내는 데이터를 저장합니다. 이러한 카운터는 성능 모니터에서 볼 때 `ServiceModelEndpoint 4.0.0.0` 성능 개체 아래에 있습니다. 인스턴스 이름은 다음 패턴으로 지정됩니다.  
  
`(ServiceName).(ContractName)@(endpoint listener address)`  
  
 데이터는 개별 작업을 위해 수집된 데이터와 비슷하지만 엔드포인트에서만 집계됩니다.  
  
> [!CAUTION]
> 성능 카운터 인스턴스의 이름 길이에는 제한이 있습니다. WCF (Windows Communication Foundation) 카운터 인스턴스 이름이 최대 길이를 초과 하면 WCF는 인스턴스 이름의 일부를 해시 값으로 바꿉니다.  
  
## <a name="see-also"></a>참고 항목

- [성능 카운터](index.md)
