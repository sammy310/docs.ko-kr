---
title: 관리 및 진단
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Communication Foundation, diagnostics
- Windows Communication Foundation, administration
- diagnostics [WCF]
- WCF, diagnostics
- administration [WCF]
- WCF, administration
ms.assetid: 34c81c08-0e0f-4fbc-9ae8-91948640ee43
ms.openlocfilehash: 351d133215343e07e849ad1045eba601dd8cce56
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59092282"
---
# <a name="administration-and-diagnostics"></a>관리 및 진단
Windows Communication Foundation (WCF) 다양 한 응용 프로그램 수명의 여러 단계를 모니터링 하는 데 도움이 되는 기능을 제공 합니다. 예를 들어 구성을 사용하여 배포 시 서비스와 클라이언트를 설정할 수 있습니다. WCF에는 다양 한 응용 프로그램의 성능을 측정할 수 있도록 성능 카운터가 포함 됩니다. 또한 WCF WCF Windows Management Instrumentation (WMI) 공급자를 통해 런타임으로 서비스 검사 데이터를 노출합니다. 응용 프로그램이 실패하거나 실행을 잘못 시작할 때 이벤트 로그를 사용하여 중요한 이벤트가 발생했는지 여부를 확인할 수 있습니다. 메시지 로깅 및 추적을 사용하여 응용 프로그램의 종단 간에 발생한 이벤트를 확인할 수도 있습니다. 이러한 기능에는 개발자와 IT 전문가 모두 제대로 작동 하지 않을 때 WCF 응용 프로그램 문제를 해결 하려면 지원 합니다.  
  
> [!NOTE]
>  특정 세부 정보 없이 오류를 수신 하는 경우 사용 해야 합니다 `includeExceptionDetailInFaults` 특성을 [ \<serviceDebug >](../../../../docs/framework/configure-apps/file-schema/wcf/servicedebug.md) 구성 요소입니다. 이렇게 하면 고급 진단 없이 여러 가지 일반적인 문제를 검색할 수 있는 WCF 클라이언트에 예외 정보를 보내도록 합니다. 자세한 내용은 [Sending and Receiving Faults](../../../../docs/framework/wcf/sending-and-receiving-faults.md)합니다.  
  
## <a name="diagnostics-features-provided-by-wcf"></a>WCF에서 제공하는 진단 기능  
 WCF에는 다음 진단 기능을 제공합니다.  
  
-   종단 간 추적에서는 디버거를 사용하지 않고 응용 프로그램 문제 해결을 위한 계측 데이터를 제공합니다. WCF는 오류 메시지 뿐만 아니라 프로세스 중요 시점에 대 한 추적을 출력 합니다. 여기에는 채널 팩터리 열기 또는 서비스 호스트에서 메시지 보내고 받기 등이 포함될 수 있습니다. 실행 중인 응용 프로그램에서는 해당 진행률을 모니터링하기 위해 추적을 사용할 수 있습니다. 자세한 내용은 참조는 [추적](../../../../docs/framework/wcf/diagnostics/tracing/index.md) 항목입니다. 사용 하는 방법을 추적 응용 프로그램을 디버깅을 이해 하려면 참조는 [응용 프로그램 문제 해결을 사용 하 여 추적](../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md) 항목입니다.  
  
-   메시지 로깅을 사용하면 전송 이전과 이후에 메시지가 어떻게 표시되는지 볼 수 있습니다. 자세한 내용은 참조는 [메시지 로깅](../../../../docs/framework/wcf/diagnostics/message-logging.md) 항목입니다.  
  
-   이벤트 추적은 모든 주요 문제에 대해 이벤트 로그에 이벤트를 기록합니다. 그런 다음 이벤트 뷰어를 사용하여 비정상적인 상태를 검사할 수 있습니다. 자세한 내용은 참조는 [이벤트 로깅](../../../../docs/framework/wcf/diagnostics/event-logging/index.md) 항목입니다.  
  
-   성능 모니터를 통해 노출된 성능 카운터를 통해 사용자는 응용 프로그램과 시스템의 상태를 모니터링할 수 있습니다. 자세한 내용은 참조는 [성능 카운터](../../../../docs/framework/wcf/diagnostics/performance-counters/index.md) 항목입니다.  
  
-   <xref:System.ServiceModel.Configuration> 네임스페이스를 통해 구성 파일을 로드하고 서비스 또는 클라이언트 엔드포인트를 설정할 수 있습니다. 여러 컴퓨터에 업데이트를 배포해야 하는 경우, 다양한 응용 프로그램에 대한 스크립트 변경 사항에 개체 모델을 사용할 수 있습니다. 사용할 수 있습니다는 [Configuration Editor 도구 (SvcConfigEditor.exe)](../../../../docs/framework/wcf/configuration-editor-tool-svcconfigeditor-exe.md) GUI 마법사를 사용 하 여 구성 설정을 편집 합니다. 자세한 내용은 참조는 [응용 프로그램 구성](../../../../docs/framework/wcf/diagnostics/configuring-your-application.md) 항목입니다.  
  
-   WMI를 사용하면 서비스가 컴퓨터에서 수신하는 내용 및 사용 중인 바인딩을 확인할 수 있습니다. 자세한 내용은 참조는 [진단에 대 한 Windows Management Instrumentation를 사용 하 여](../../../../docs/framework/wcf/diagnostics/wmi/index.md) 항목입니다.  
  
 WCF는 또한 쉽게 작성, 배포 및 WCF 응용 프로그램을 관리할 수 있도록 여러 GUI 및 명령줄 도구를 제공 합니다. 자세한 내용은 [Windows Communication Foundation 도구](../../../../docs/framework/wcf/tools.md)합니다. 예를 들어 사용할 수 있습니다 합니다 [Configuration Editor 도구 (SvcConfigEditor.exe)](../../../../docs/framework/wcf/configuration-editor-tool-svcconfigeditor-exe.md) 를 만들고 XML을 직접 편집 하는 대신 마법사를 사용 하는 WCF 구성 설정을 편집 합니다. 사용할 수도 있습니다는 [Service Trace Viewer 도구 (SvcTraceViewer.exe)](../../../../docs/framework/wcf/service-trace-viewer-tool-svctraceviewer-exe.md) 를 보고 하 고 그룹을 진단할 수 있도록 추적 메시지를 필터링, 복구 및 WCF 서비스를 사용 하 여 문제를 확인 합니다.  
  
## <a name="see-also"></a>참고자료

- [애플리케이션 구성](../../../../docs/framework/wcf/diagnostics/configuring-your-application.md)
- [서비스 배포](../../../../docs/framework/wcf/diagnostics/deploying-services.md)
- [예외 참조](../../../../docs/framework/wcf/diagnostics/exceptions-reference/index.md)
- [이벤트 로깅](../../../../docs/framework/wcf/diagnostics/event-logging/index.md)
- [메시지 로깅](../../../../docs/framework/wcf/diagnostics/message-logging.md)
- [Configuration Editor 도구(SvcConfigEditor.exe)](../../../../docs/framework/wcf/configuration-editor-tool-svcconfigeditor-exe.md)
- [Service Trace Viewer 도구(SvcTraceViewer.exe)](../../../../docs/framework/wcf/service-trace-viewer-tool-svctraceviewer-exe.md)
- [ServiceModel 등록 도구](../../../../docs/framework/wcf/diagnostics/servicemodel-registration-tool.md)
- [추적](../../../../docs/framework/wcf/diagnostics/tracing/index.md)
- [진단에 WMI(Windows Management Instrumentation) 사용](../../../../docs/framework/wcf/diagnostics/wmi/index.md)
- [성능 카운터](../../../../docs/framework/wcf/diagnostics/performance-counters/index.md)
- [Windows Communication Foundation 도구](../../../../docs/framework/wcf/tools.md)
