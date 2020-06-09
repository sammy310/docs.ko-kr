---
title: '방법: 워크플로 애플리케이션에서 서비스 액세스'
ms.date: 03/30/2017
ms.assetid: 925ef8ea-5550-4c9d-bb7b-209e20c280ad
ms.openlocfilehash: 2ce79b726b623c2a25bf14065682e685455ca575
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/09/2020
ms.locfileid: "84597243"
---
# <a name="how-to-access-a-service-from-a-workflow-application"></a>방법: 워크플로 애플리케이션에서 서비스 액세스
이 항목에서는 워크플로 콘솔 애플리케이션에서 워크플로 서비스를 호출하는 방법에 대해 설명합니다. 이 [는 방법: 메시징 작업을 사용 하 여 워크플로 서비스 만들기](how-to-create-a-workflow-service-with-messaging-activities.md) 항목의 완료에 따라 달라 집니다. 이 항목에서는 워크플로 응용 프로그램에서 워크플로 서비스를 호출 하는 방법에 대해 설명 하지만, 워크플로 응용 프로그램에서 WCF (Windows Communication Foundation) 서비스를 호출 하는 데 동일한 메서드를 사용할 수 있습니다.

### <a name="create-a-workflow-console-application-project"></a>워크플로 콘솔 애플리케이션 프로젝트 만들기

1. Visual Studio 2012를 시작 합니다.

2. [방법: 메시징 작업을 사용 하 여 워크플로 서비스 만들기](how-to-create-a-workflow-service-with-messaging-activities.md) 항목에서 만든 MyWFService 프로젝트를 로드 합니다.

3. **솔루션 탐색기** 에서 **MyWFService** 솔루션을 마우스 오른쪽 단추로 클릭 하 고 **추가**, **새 프로젝트**를 차례로 선택 합니다. **설치 된 템플릿** 에서 **워크플로** 를 선택 하 고 프로젝트 형식 목록에서 워크플로 **콘솔 응용 프로그램** 을 선택 합니다. 다음 그림과 같이 프로젝트 이름을 MyWFClient로 지정하고 기본 위치를 사용합니다.

     ![새 프로젝트 추가 대화 상자](./media/how-to-access-a-service-from-a-workflow-application/add-new-project-dialog.jpg)

     **확인** 단추를 클릭 하 여 **새 프로젝트 추가 대화 상자**를 닫습니다.

4. 프로젝트가 만들어진 후 디자이너에서 Workflow1.xaml 파일이 열립니다. **도구 상자 탭을** 클릭 하 여 도구 상자를 열고 (아직 열려 있지 않은 경우) 압정을 클릭 하 여 도구 상자 창을 열어 둡니다.

5. **Ctrl** + **F5** 를 눌러 서비스를 빌드하고 시작 합니다. 이전과 마찬가지로 ASP.NET Development Server가 시작되고 Internet Explorer에 WCF 도움말 페이지가 표시됩니다. 이 페이지의 URI는 다음 단계에서도 사용됩니다.

     ![WCF 도움말 페이지 및 URI를 표시 하는 IE](./media/how-to-access-a-service-from-a-workflow-application/ie-wcf-help-page-uri.jpg)

6. **솔루션 탐색기** 에서 **MyWFClient** 프로젝트를 마우스 오른쪽 단추로 클릭 하 **Add**고  >  **서비스 참조**추가를 선택 합니다. **검색** 단추를 클릭 하 여 서비스에 대 한 현재 솔루션을 검색 합니다. 서비스 목록에서 Service1.xamlx 옆에 있는 삼각형을 클릭합니다. Service1 옆에 있는 삼각형을 클릭하여 Service1 서비스에 의해 구현되는 계약을 나열합니다. **서비스** 목록에서 **Service1** 노드를 확장 합니다. 다음 그림과 같이 **작업** 목록에 Echo 작업이 표시 됩니다.

     ![서비스 참조 추가 대화 상자](./media/how-to-access-a-service-from-a-workflow-application/add-service-reference.jpg)

     기본 네임 스페이스를 유지 하 고 **확인** 을 클릭 하 여 **서비스 참조 추가** 대화 상자를 닫습니다. 다음 대화 상자가 표시됩니다.

     ![서비스 참조 추가 알림 대화 상자](./media/how-to-access-a-service-from-a-workflow-application/add-service-reference-dialog.jpg)

     **확인** 을 클릭 하 여 대화 상자를 닫습니다. 그런 다음 Ctrl+Shift+B를 눌러 솔루션을 빌드합니다. 도구 상자에서 **MyWFClient**라는 새 섹션이 추가 되었습니다. 다음 그림과 같이 이 섹션을 확장하고 추가된 Echo 작업을 확인합니다.

     ![도구 상자의 Echo 활동](./media/how-to-access-a-service-from-a-workflow-application/echo-activity-toolbox.jpg)

7. 디자이너 화면으로 <xref:System.Activities.Statements.Sequence> 작업을 끌어서 놓습니다. 도구 상자의 **제어 흐름** 섹션 아래에 있습니다.

8. 활동에 포커스가 있는 상태에서 <xref:System.Activities.Statements.Sequence> **변수** 링크를 클릭 하 고 라는 문자열 변수를 추가 `inString` 합니다. `"Hello, world"` `outString` 다음 다이어그램에 표시 된 것 처럼 라는 문자열 변수를 비롯 하 여 변수에 기본값을 지정 합니다.

     ![InString 변수 추가](./media/how-to-access-a-service-from-a-workflow-application/add-instring-variable.jpg)

9. **Echo** 활동을로 끌어 놓습니다 <xref:System.Activities.Statements.Sequence> . 속성 창에서 `inMsg` 인수를 `inString` `outMsg` 다음 그림과 같이 변수에 바인딩하고 인수를 `outString` 변수에 바인딩합니다. 그러면 `inString` 변수의 값이 작업에 전달되고 반환 값이 `outString` 변수에 추가됩니다.

     ![변수에 인수 바인딩](./media/how-to-access-a-service-from-a-workflow-application/bind-arguments-variables.jpg)

10. 서비스 호출에서 반환 된 문자열을 표시 하는 **WriteLine** 활동을 **Echo** 활동 아래로 끌어서 놓습니다. **WriteLine** 활동은 도구 상자의 **기본 형식** 노드에 있습니다. Writeline 활동 **Text** 의 **WriteLine** `outString` `outString` 텍스트 상자에를 **WriteLine** 입력 하 여 writeline 활동의 text 인수를 변수에 바인딩합니다. 그러면 워크플로가 다음 그림과 같이 표시됩니다.

     ![완료된 클라이언트 워크플로](./media/how-to-access-a-service-from-a-workflow-application/complete-client-workflow.jpg)

11. MyWFService 솔루션을 마우스 오른쪽 단추로 클릭 하 고 **시작 프로젝트 설정**...을 선택 합니다. **여러 시작 프로젝트** 라디오 단추를 선택 하 고 다음 그림과 같이 **작업** 열의 각 프로젝트에 대해 **시작** 을 선택 합니다.

     ![시작 프로젝트 옵션](./media/how-to-access-a-service-from-a-workflow-application/startup-project-options.jpg)

12. Ctrl+F5를 눌러 서비스와 클라이언트를 둘 다 시작합니다. ASP.NET 개발 서버은 서비스를 호스팅하고, Internet Explorer는 WCF 도움말 페이지를 표시 하 고, 클라이언트 워크플로 응용 프로그램은 콘솔 창에서 시작 되며 서비스에서 반환 된 문자열을 표시 합니다 ("Hello, 세계").

## <a name="see-also"></a>참고 항목

- [워크플로 서비스](workflow-services.md)
- [방법: 메시징 활동을 사용하여 워크플로 서비스 만들기](how-to-create-a-workflow-service-with-messaging-activities.md)
- [웹 프로젝트의 워크플로에서 WCF 서비스 사용](https://docs.microsoft.com/archive/blogs/endpoint/how-to-consume-a-wcf-service-from-a-wf4-workflow)
