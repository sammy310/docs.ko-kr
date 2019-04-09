---
title: 인스턴스
ms.date: 03/30/2017
ms.assetid: c8cf3460-0ca1-4411-8262-e9ecaf7f0a31
ms.openlocfilehash: 668cfb3026b9ab7259665f5e53873a512b1e2238
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59118991"
---
# <a name="instances"></a>인스턴스
카운터 이름: 인스턴스입니다.  
  
## <a name="description"></a>설명  
 현재 서비스에 포함된 인스턴스 컨텍스트 수입니다.  
  
 대체로 인스턴스 컨텍스트 수는 인스턴스 수와 같습니다. 그러나 다음 시나리오는 이 규칙의 예외입니다.  
  
-   서비스 메서드가 명시적으로 <xref:System.ServiceModel.Dispatcher.IInstanceProvider.ReleaseInstance%2A> 메서드를 호출합니다.  
  
-   <xref:System.ServiceModel.ReleaseInstanceMode>가 <xref:System.ServiceModel.OperationBehaviorAttribute> 인스턴스에 적용됩니다.  
  
## <a name="see-also"></a>참고자료

- <xref:System.ServiceModel.OperationBehaviorAttribute>
