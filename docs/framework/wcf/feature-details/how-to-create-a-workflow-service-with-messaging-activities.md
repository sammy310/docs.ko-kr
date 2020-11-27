---
title: '방법: 메시징 활동을 사용하여 워크플로 서비스 만들기'
ms.date: 03/30/2017
ms.assetid: 53d094e2-6901-4aa1-88b8-024b27ccf78b
ms.openlocfilehash: 21d08d9c3c78cc8774d038018703ffb0c7ceb1fe
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96286320"
---
# <a name="how-to-create-a-workflow-service-with-messaging-activities"></a>방법: 메시징 활동을 사용하여 워크플로 서비스 만들기

이 항목에서는 메시징 작업을 사용하여 간단한 워크플로 서비스를 만드는 방법을 보여 줍니다. 이 항목에서는 서비스가 메시징 작업만으로 구성된 워크플로 서비스를 만드는 방법에 중점을 둡니다. 실제 서비스의 워크플로에는 다른 많은 작업이 포함되어 있습니다. 이 항목의 서비스에서는 문자열을 받아서 호출자에게 반환하는 Echo라는 하나의 작업을 구현합니다. 이 항목은 시리즈로 된 두 항목 중 첫 번째 항목입니다. 다음 항목 [방법: 워크플로 응용 프로그램에서 서비스 액세스](how-to-access-a-service-from-a-workflow-application.md) 에서는이 항목에서 만든 서비스를 호출할 수 있는 워크플로 응용 프로그램을 만드는 방법을 설명 합니다.  
  
### <a name="to-create-a-workflow-service-project"></a>워크플로 서비스 프로젝트를 만들려면  
  
1. Visual Studio 2012를 시작 합니다.  
  
2. **파일** 메뉴를 클릭 하 고 **새로 만들기** 를 선택한 다음 **프로젝트** 를 클릭 하 여 **새 프로젝트 대화 상자** 를 표시 합니다. 설치 된 템플릿 목록에서 **워크플로** 를 선택 하 고 프로젝트 형식 목록에서 **WCF 워크플로 서비스 응용 프로그램** 을 선택 합니다. 프로젝트의 이름을 `MyWFService` 로 하 고 다음 그림과 같이 기본 위치를 사용 합니다.  
  
     **확인** 단추를 클릭 하 여 **새 프로젝트 대화 상자** 를 닫습니다.  
  
3. 프로젝트가 생성되면 다음 그림과 같이 Service1.xamlx 파일이 디자이너에서 열립니다.  
  
     ![디자이너에서 open .xamlx 파일을 보여 주는 스크린샷](./media/how-to-create-a-workflow-service-with-messaging-activities/default-workflow-service.jpg)  
  
     **순차 서비스** 라는 레이블이 지정 된 활동을 마우스 오른쪽 단추로 클릭 하 고 **삭제** 를 선택 합니다.  
  
### <a name="to-implement-the-workflow-service"></a>워크플로 서비스를 구현하려면  
  
1. 화면 왼쪽에 있는 **도구 상자** 탭을 선택 하 여 도구 상자를 표시 하 고 압정을 클릭 하 여 창을 계속 열어 둡니다. 다음 그림과 같이 도구 상자의 **메시징** 섹션을 확장 하 여 메시징 활동 및 메시징 활동 템플릿을 표시 합니다.  
  
     ![메시징 섹션이 확장 된 도구 상자를 보여 주는 스크린샷](./media/how-to-create-a-workflow-service-with-messaging-activities/toolbox-messaging-section.jpg)  
  
2. **ReceiveAndSendReply** 템플릿을 workflow designer로 끌어 놓습니다. 그러면 <xref:System.Activities.Statements.Sequence> 다음 그림에 표시 된 것 처럼 **Receive** 작업이 적용 된 후 작업이 생성 <xref:System.ServiceModel.Activities.SendReply> 됩니다.  
  
     ![ReceiveAndSendReply 템플릿을 보여 주는 스크린샷](./media/how-to-create-a-workflow-service-with-messaging-activities/receiveandsendreply-template.jpg)  
  
     <xref:System.ServiceModel.Activities.SendReply> 작업의 <xref:System.ServiceModel.Activities.SendReply.Request%2A> 속성이 `Receive` 작업이 회신하는 <xref:System.ServiceModel.Activities.Receive> 작업의 이름인 <xref:System.ServiceModel.Activities.SendReply>로 설정됩니다.  
  
3. <xref:System.ServiceModel.Activities.Receive>활동 유형에 서 `Echo` **OperationName** 이라는 레이블이 지정 된 텍스트 상자에 입력 합니다. 그러면 서비스가 구현하는 작업의 이름이 정의됩니다.  
  
     ![작업 이름을 지정할 위치를 보여 주는 스크린샷](./media/how-to-create-a-workflow-service-with-messaging-activities/define-operation-name.jpg)  
  
4. 활동을 <xref:System.ServiceModel.Activities.Receive> 선택한 상태에서 **보기** 메뉴를 클릭 하 고 **속성 창** 을 선택 하 여 속성 창을 아직 열지 않은 경우 엽니다. **속성 창** 에서 **CanCreateInstance** 가 표시 될 때까지 아래로 스크롤하고 다음 그림과 같이 확인란을 클릭 합니다. 이렇게 설정하면 메시지를 받을 때 필요한 경우 워크플로 서비스 호스트가 서비스의 새 인스턴스를 만들 수 있습니다.  
  
     ![CanCreateInstance 속성을 보여 주는 스크린샷](./media/how-to-create-a-workflow-service-with-messaging-activities/cancreateinstance-property.jpg)  
  
5. 활동을 선택 <xref:System.Activities.Statements.Sequence> 하 고 디자이너의 왼쪽 아래 모서리에 있는 **변수** 단추를 클릭 합니다. 그러면 변수 편집기가 표시됩니다. 변수 **만들기** 링크를 클릭 하 여 작업에 전송 된 문자열을 저장 하는 변수를 추가 합니다. 다음 그림과 같이 변수의 이름을로 `msg` 설정 하 고 **변수** 형식을 String으로 설정 합니다.  
  
     ![변수를 추가 하는 방법을 보여 주는 스크린샷](./media/how-to-create-a-workflow-service-with-messaging-activities/add-variable-msg-string.jpg)  
  
     **변수 단추를** 다시 클릭 하 여 변수 편집기를 닫습니다.  
  
6. **정의 ...** 를 클릭 합니다. 활동의 **콘텐츠** 텍스트 상자에 링크 <xref:System.ServiceModel.Activities.Receive> 하 여 **콘텐츠 정의** 대화 상자를 표시 합니다. 다음 그림과 같이 **매개 변수** 라디오 단추를 선택 하 고 **새 매개 변수 추가** 링크를 클릭 한 다음 이름 입력란에를 입력 하 `inMsg` 고 **형식** 드롭다운 목록 상자에서 **문자열** 을 선택 하 고 **name** `msg` **할당 대상** 텍스트 상자에을 입력 합니다.  
  
     ![매개 변수 콘텐츠를 추가 하는 것을 보여 주는 스크린샷](./media/how-to-create-a-workflow-service-with-messaging-activities/adding-parameters-content.jpg)  
  
     그러면 받기 작업이 문자열 매개 변수를 받고 데이터가 `msg` 변수에 바인딩되도록 지정됩니다. **확인** 을 클릭 하 여 **콘텐츠 정의** 대화 상자를 닫습니다.  
  
7. 활동의 **콘텐츠** 상자에서 **정의 ...** 링크를 클릭 <xref:System.ServiceModel.Activities.SendReply> 하 여 **콘텐츠 정의** 대화 상자를 표시 합니다. 다음 그림과 같이 **매개 변수** 라디오 단추를 선택 하 고, **새 매개 변수 추가** 링크를 클릭 하 고, 이름 텍스트 상자에를 입력 하 고, `outMsg` **형식** 드롭다운 목록 상자에서 문자열을 선택 하 고, **name** **String** `msg` **값** 텍스트 상자에서 문자열을 선택 합니다.  
  
     ![OutMsg 매개 변수를 추가 하는 방법을 보여 주는 스크린샷](./media/how-to-create-a-workflow-service-with-messaging-activities/outmsg-parameters-content.jpg)  
  
     그러면 <xref:System.ServiceModel.Activities.SendReply> 작업이 메시지 또는 메시지 계약 형식을 보내고 데이터가 `msg` 변수에 바인딩되도록 지정됩니다. 이 작업이 <xref:System.ServiceModel.Activities.SendReply> 작업이므로 이는 이 작업이 클라이언트에 다시 보내는 메시지를 채우는 데 `msg`의 데이터가 사용됨을 의미합니다. **확인** 을 클릭 하 여 **콘텐츠 정의** 대화 상자를 닫습니다.  
  
8. **빌드** 메뉴를 클릭 하 고 **솔루션 빌드** 를 선택 하 여 솔루션을 저장 하 고 빌드합니다.  
  
## <a name="configure-the-workflow-service-project"></a>워크플로 서비스 프로젝트 구성  

 워크플로 서비스가 완료되었으므로 이 단원에서는 워크플로 서비스 솔루션을 손쉽게 호스팅하고 실행할 수 있도록 구성하는 방법에 대해 설명합니다. 이 솔루션은 ASP.NET Development Server를 사용하여 서비스를 호스팅합니다.  
  
#### <a name="to-set-project-start-up-options"></a>프로젝트 시작 옵션을 설정하려면  
  
1. **솔루션 탐색기** 에서 **MyWFService** 을 마우스 오른쪽 단추로 클릭 하 고 **속성** 을 선택 하 여 **프로젝트 속성** 대화 상자를 표시 합니다.  
  
2. **웹** 탭을 선택 하 고 **시작 작업** 아래에서 **특정 페이지** 를 선택 하 고 `Service1.xamlx` 다음 그림과 같이 텍스트 상자에을 입력 합니다.  
  
     ![프로젝트 속성 대화 상자를 보여 주는 스크린샷](./media/how-to-create-a-workflow-service-with-messaging-activities/project-properties-dialog.jpg)  
  
     그러면 ASP.NET Development Server에서 Service1.xamlx에 정의된 서비스가 호스팅됩니다.  
  
3. Ctrl+F5를 눌러 서비스를 시작합니다. 그러면 다음 그림과 같이 바탕 화면의 오른쪽 아래에 ASP.NET Development Server 아이콘이 표시됩니다.  
  
     ![ASP.NET Developer Server 아이콘을 보여 주는 스크린샷](./media/how-to-create-a-workflow-service-with-messaging-activities/asp-net-dev-server-icon.jpg)  
  
     또한 Internet Explorer에 서비스에 대한 WCF 서비스 도움말 페이지가 표시됩니다.  
  
     ![WCF 서비스 도움말 페이지를 보여 주는 스크린샷](./media/how-to-create-a-workflow-service-with-messaging-activities/wcf-service-help-page.jpg)  
  
4. [방법: 워크플로 응용 프로그램에서 서비스 액세스](how-to-access-a-service-from-a-workflow-application.md) 항목을 계속 진행 하 여이 서비스를 호출 하는 워크플로 클라이언트를 만듭니다.  
  
## <a name="see-also"></a>참고 항목

- [워크플로 서비스](workflow-services.md)
- [워크플로 서비스 호스팅 개요](hosting-workflow-services-overview.md)
- [메시징 활동](messaging-activities.md)
