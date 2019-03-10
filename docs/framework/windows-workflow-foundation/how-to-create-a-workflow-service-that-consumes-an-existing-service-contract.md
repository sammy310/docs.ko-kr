---
title: '방법: 기존 서비스 계약을 사용 하는 워크플로 서비스 만들기'
ms.date: 03/30/2017
ms.assetid: 11d11b59-acc4-48bf-8e4b-e97b516aa0a9
ms.openlocfilehash: 57babf216821665613da053f972ff25488418b7d
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/09/2019
ms.locfileid: "57705066"
---
# <a name="how-to-create-a-workflow-service-that-consumes-an-existing-service-contract"></a>방법: 기존 서비스 계약을 사용 하는 워크플로 서비스 만들기
[!INCLUDE[net_v45](../../../includes/net-v45-md.md)]는 계약 중심 워크플로 개발의 형태로 웹 서비스와 워크플로 간에 보다 우수한 통합 성능을 제공합니다. 계약 중심 워크플로 개발 도구를 사용하면 코드에서 계약을 먼저 디자인할 수 있습니다. 그러면 이 도구는 계약의 작업을 위해 도구 상자에 활동 템플릿을 자동으로 생성합니다.  
  
> [!NOTE]
>  이 항목에서는 계약 중심 워크플로 서비스를 만들기 위한 단계별 지침을 제공합니다. 계약 중심 워크플로 서비스 개발에 대 한 자세한 내용은 참조 하세요. [계약 중심 워크플로 서비스 개발](contract-first-workflow-service-development.md)합니다.  
  
### <a name="creating-the-workflow-project"></a>워크플로 프로젝트 만들기  
  
1.  Visual Studio에서 선택 **파일**하십시오 **새 프로젝트**합니다. 선택 합니다 **WCF** 노드에서 **C#** 에서 노드를 **템플릿** 트리에서 선택한를 **WCF 워크플로 서비스 응용 프로그램** 템플릿입니다.  
  
2.  새 프로젝트의 이름을 `ContractFirst` 누릅니다 **확인**합니다.  
  
### <a name="creating-the-service-contract"></a>서비스 계약 만들기  
  
1.  프로젝트를 마우스 오른쪽 단추로 클릭 **솔루션 탐색기** 선택한 **추가**, **새 항목...** . 선택 된 **코드** 왼쪽의 노드 및 **클래스** 오른쪽에서 템플릿. 새 클래스 이름을 `IBookService` 누릅니다 **확인**합니다.  
  
2.  표시되는 코드 창의 맨 위에서 `System.Servicemodel`에 Using 문을 추가합니다.  
  
    ```  
    using System.ServiceModel;  
    ```  
  
3.  샘플 클래스 정의를 다음과 같은 인터페이스 정의로 변경합니다.  
  
    ```  
    [ServiceContract]  
        public interface IBookService  
        {  
            [OperationContract]  
            void Buy(string bookName);  
  
            [OperationContract(IsOneWay=true)]  
            void Checkout();  
        }  
    ```  
  
4.  키를 눌러 프로젝트를 빌드할 **Ctrl + Shift + B**합니다.  
  
### <a name="importing-the-service-contract"></a>서비스 계약 가져오기  
  
1.  프로젝트를 마우스 오른쪽 단추로 클릭 **솔루션 탐색기** 선택한 **서비스 계약 가져오기**합니다. 아래  **\<현재 프로젝트 >**, 모든 하위 노드를 열고 선택한 **IBookService**합니다. **확인**을 클릭합니다.  
  
2.  작업이 성공적으로 완료되었음을 알리는 대화 상자가 열리고 프로젝트가 빌드된 후 생성된 활동이 도구 상자에 나타납니다. **확인**을 클릭합니다.  
  
3.  키를 눌러 프로젝트를 빌드할 **Ctrl + Shift + B**, 가져온된 활동이 도구 상자에 표시 되도록 합니다.  
  
4.  **솔루션 탐색기**에서 Service1.xamlx를 엽니다. 워크플로 서비스가 디자이너에 표시됩니다.  
  
5.  선택 된 **시퀀스** 활동입니다. 속성 창에서 클릭 된 **...** 단추는 **ImplementedContract** 속성입니다. 에 **형식 컬렉션 편집기** 창이 나타나면 클릭 합니다 **형식** 드롭다운에서 선택한를 **형식 찾아보기...** 항목입니다. 에 **형식 찾아보기 및 선택.Net** 대화 상자 아래에 있는  **\<현재 프로젝트 >** 을 모든 하위 노드를 열고 선택 **IBookService**합니다. **확인**을 클릭합니다. 에 **형식 컬렉션 편집기** 대화 상자에서 클릭 **확인**합니다.  
  
6.  선택 하 고 삭제 합니다 **ReceiveRequest** 하 고 **SendResponse** 활동입니다.  
  
7.  도구 상자에서 끌어를 **Buy_ReceiveAndSendReply** 및 **Checkout_Receive** 활동을 놓으면 합니다 **순차 서비스** 활동입니다.
