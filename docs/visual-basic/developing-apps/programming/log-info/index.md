---
title: 응용 프로그램의 정보 기록
ms.date: 07/20/2015
helpviewer_keywords:
- Log object
- My.Log object
- applications [Visual Basic], logging information from
- logging
- My.Application.Log object
- examples [Visual Basic], logging application information
ms.assetid: 8bf4f047-22d6-48d6-aec5-93b98ad5b8e8
ms.openlocfilehash: 43738b2d654435532a98654cbc40af134d43f02c
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/04/2020
ms.locfileid: "84410025"
---
# <a name="logging-information-from-the-application-visual-basic"></a>애플리케이션의 정보 기록(Visual Basic)

이 섹션에는 `My.Application.Log` 또는 `My.Log` 개체를 사용하여 애플리케이션의 정보를 기록하는 방법과 애플리케이션의 로깅 기능을 확장하는 방법을 설명하는 항목이 포함되어 있습니다.  
  
 `Log` 개체는 애플리케이션의 로그 수신기에 정보를 쓰기 위한 메서드를 제공하고, `Log` 개체의 고급 `TraceSource` 속성은 자세한 구성 정보를 제공합니다. `Log` 개체는 애플리케이션의 구성 파일에서 구성됩니다.  
  
 `My.Log` 개체는 ASP.NET 애플리케이션에만 사용할 수 있습니다. 클라이언트 애플리케이션의 경우 `My.Application.Log`를 사용합니다. 자세한 내용은 <xref:Microsoft.VisualBasic.Logging.Log>를 참조하세요.  
  
## <a name="tasks"></a>작업  
  
|대상|참조 항목|  
|--------|---------|  
|애플리케이션의 로그에 이벤트 정보를 씁니다.|[방법: 로그 메시지 쓰기](how-to-write-log-messages.md)|  
|애플리케이션의 로그에 예외 정보를 씁니다.|[방법: 로그 예외](how-to-log-exceptions.md)|  
|애플리케이션을 시작 및 종료할 때 애플리케이션의 로그에 추적 정보를 씁니다.|[방법: 애플리케이션이 시작 또는 종료될 때 메시지 기록](how-to-log-messages-when-the-application-starts-or-shuts-down.md)|  
|텍스트 파일에 정보를 쓰도록 `My.Application.Log`를 구성합니다.|[방법: 텍스트 파일에 이벤트 정보 쓰기](how-to-write-event-information-to-a-text-file.md)|  
|이벤트 로그에 정보를 쓰도록 `My.Application.Log`를 구성합니다.|[방법: 애플리케이션 이벤트 로그에 쓰기](how-to-write-to-an-application-event-log.md)|  
|`My.Application.Log`가 정보를 쓰는 위치를 변경합니다.|[연습: My.Application.Log가 정보를 기록하는 위치 변경](walkthrough-changing-where-my-application-log-writes-information.md)|  
|`My.Application.Log`가 정보를 쓰는 위치를 확인합니다.|[연습: My.Application.Log가 정보를 기록하는 위치 확인](walkthrough-determining-where-my-application-log-writes-information.md)|  
|`My.Application.Log`에 대한 사용자 지정 로그 수신기를 만듭니다.|[연습: 사용자 지정 로그 수신기 만들기](walkthrough-creating-custom-log-listeners.md)|  
|`My.Application.Log` 로그의 출력을 필터링합니다.|[연습: My.Application.Log 출력 필터링](walkthrough-filtering-my-application-log-output.md)|  
  
## <a name="see-also"></a>참조

- <xref:Microsoft.VisualBasic.Logging.Log?displayProperty=nameWithType>
- [애플리케이션 로그 작업](working-with-application-logs.md)
- [문제 해결: 로그 수신기](troubleshooting-log-listeners.md)
