---
title: EventLogSource에 지정된 소스 이름이 EventLogName에 지정된 로그가 아닌 로그에 등록되었습니다.
ms.date: 07/20/2015
ms.assetid: 7317e100-098b-408d-86e5-7c74cf8558c7
ms.openlocfilehash: da9f1756909d1c37e28f2dde62a7f8a73bb19f37
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/15/2020
ms.locfileid: "90555642"
---
# <a name="source-name-specified-in-eventlogsource-is-registered-to-a-log-other-than-that-specified-in-eventlogname"></a>EventLogSource에 지정된 소스 이름이 EventLogName에 지정된 로그가 아닌 로그에 등록되었습니다.
`EventLog` 에서 다른 로그에 등록된 소스를 참조하려고 합니다. 이벤트 로그에 항목을 쓰는 경우 <xref:System.Diagnostics.EventLog.Source%2A> 속성을 지정해야 합니다. <xref:System.Diagnostics.EventLog.Source%2A> 속성은 구성 요소를 항목의 유효한 소스로 이벤트 로그에 등록합니다. 단일 소스는 한 번에 하나의 이벤트 로그에만 연결되고 항목을 쓸 수 있습니다.  
  
 기본적으로 구성 요소를 유효한 소스로 먼저 등록하지 않고 항목을 쓰려고 하면 시스템이 자동으로 <xref:System.Diagnostics.EventLog.Source%2A> 속성의 값을 소스 문자열로 사용하여 이벤트 로그에 소스를 등록합니다.  
  
## <a name="to-correct-this-error"></a>이 오류를 해결하려면  
  
- 소스가 올바른 로그에 등록되었는지 확인합니다. 이렇게 하려면 <xref:System.Diagnostics.EventLog.CreateEventSource%2A> 메서드 또는 해당 오버로드 중 하나를 사용하여 이벤트 로그에 구성 요소를 고유하게 식별하는 문자열을 지정합니다.  
  
## <a name="see-also"></a>참조

- [이벤트 로그 관리](/previous-versions/visualstudio/visual-studio-2008/4f69axw4(v=vs.90))
- [이벤트 로그 참조](/previous-versions/visualstudio/visual-studio-2008/k43k9z2a(v=vs.90))
- [방법: 응용 프로그램을 이벤트 로그 항목의 소스로 추가](/previous-versions/visualstudio/visual-studio-2008/xz73e171(v=vs.90))
- [방법: 이벤트 소스 제거](/previous-versions/visualstudio/visual-studio-2008/k57466fc(v=vs.90))
