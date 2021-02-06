---
description: '다음에 대 한 자세한 정보: 인스턴스'
title: 인스턴스
ms.date: 03/30/2017
ms.assetid: c8cf3460-0ca1-4411-8262-e9ecaf7f0a31
ms.openlocfilehash: 9cd602164816a419b481ff600a7537593d4f500e
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99655268"
---
# <a name="instances"></a>인스턴스

카운터 이름: Instances  
  
## <a name="description"></a>설명  

 현재 서비스에 포함된 인스턴스 컨텍스트 수입니다.  
  
 대체로 인스턴스 컨텍스트 수는 인스턴스 수와 같습니다. 그러나 다음 시나리오는 이 규칙의 예외입니다.  
  
- 서비스 메서드가 명시적으로 <xref:System.ServiceModel.Dispatcher.IInstanceProvider.ReleaseInstance%2A> 메서드를 호출합니다.  
  
- <xref:System.ServiceModel.ReleaseInstanceMode>가 <xref:System.ServiceModel.OperationBehaviorAttribute> 인스턴스에 적용됩니다.  
  
## <a name="see-also"></a>참고 항목

- <xref:System.ServiceModel.OperationBehaviorAttribute>
