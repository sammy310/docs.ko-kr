---
title: 다른 이벤트 로그에서 이미 이 이름으로 소스를 등록했습니다.
ms.date: 07/20/2015
ms.assetid: e6f5cd95-bb3f-4845-84fb-ae623a9bd44e
ms.openlocfilehash: 333c28036e2d1b7514c7370b98ff70a6d195a9dd
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/23/2020
ms.locfileid: "91058393"
---
# <a name="another-event-log-has-already-registered-a-source-with-this-name"></a>다른 이벤트 로그에서 이미 이 이름으로 소스를 등록했습니다.

지정한 소스가 다른 이벤트 로그와 함께 등록되어 있는 이벤트 로그에 항목을 쓰려고 했습니다.  
  
 구성 요소가 로그에 항목을 쓰기 전에 <xref:System.Diagnostics.EventLog.Source%2A> 구성 요소 인스턴스의 <xref:System.Diagnostics.EventLog> 속성을 설정해야 합니다. 이때 시스템에서 구성 요소가 쓰고 있는 이벤트 로그에 지정한 소스가 등록되어 있는지 확인하고 필요한 경우 <xref:System.Diagnostics.EventLog.CreateEventSource%2A> 를 호출합니다.  
  
## <a name="to-correct-this-error"></a>이 오류를 해결하려면  
  
1. 소스와 <xref:System.Diagnostics.EventLog.DeleteEventSource%2A> 또는 <xref:System.Diagnostics.EventLog.DeleteEventSource%2A> 메서드를 사용하는 첫 번째 로그의 연결을 제거합니다.  
  
2. 새 로그에 소스를 등록합니다.  
  
## <a name="see-also"></a>참조

- [내 응용 프로그램 .Log](xref:Microsoft.VisualBasic.ApplicationServices.ApplicationBase.Log)
