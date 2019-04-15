---
title: 서비스 작업 기간 확인
ms.date: 03/30/2017
ms.assetid: e8a93a2c-2c20-48b3-8986-57e90e9aa908
ms.openlocfilehash: fd7dec5784f50a0613b574822a31202a859b34c6
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/09/2019
ms.locfileid: "59299035"
---
# <a name="determining-service-operation-duration"></a>서비스 작업 기간 확인
분석 추적을 Windows Communication Foundation (WCF) 응용 프로그램에서 사용 하는 경우 서비스 작업에 대 한 실행 기간 이벤트 로그를 검사 하 여 쉽게 확인할 수 있습니다.  이 항목에서는 서비스 작업을 완료하는 데 소요되는 시간을 확인하는 방법을 보여 줍니다.  
  
### <a name="determining-service-operation-execution-duration"></a>서비스 작업 실행 기간 확인  
  
1. 클릭 하 여 이벤트 뷰어를 엽니다 **시작**를 **실행**를 입력 하 고 `eventvwr.exe`입니다.  
  
2. 분석 추적을 활성화 하지 않은 경우 확장 **Applications and Services Logs**를 **Microsoft**하십시오 **Windows**, **응용 프로그램 서버-응용 프로그램** . 선택 **뷰**하십시오 **분석 및 디버그 로그 표시**합니다. 마우스 오른쪽 단추로 클릭 **분석** 선택한 **로그 사용**합니다. 서비스 작업이 실행된 후 추적 내용을 볼 수 있도록 이벤트 뷰어를 열어 둡니다.  
  
3. 서비스 프로젝트 및 해당 서비스와 상호 작용 하는 클라이언트 프로젝트를 포함 하는 WCF 응용 프로그램을 엽니다.  수행 하 여 이러한 응용 프로그램을 만들 수 있습니다 합니다 [초보자를 위한 자습서](../../../../../docs/framework/wcf/getting-started-tutorial.md)합니다.  설치 하는 WCF 샘플에 있는 경우 열 수 있습니다 합니다 [Getting Started](../../../../../docs/framework/wcf/samples/getting-started-sample.md), 자습서에서 만든 완료 된 프로젝트를 포함 하는 합니다.  
  
4. 키를 눌러 서버 응용 프로그램을 실행 **F5**합니다. 마우스 오른쪽 단추로 클릭 하 여 클라이언트 응용 프로그램을 실행 합니다 **클라이언트** 프로젝트를 선택 하 고 **디버그**를 **새 인스턴스 시작**합니다.  
  
5. 이벤트 뷰어에서 분석 로그를 새로 고친 다음 이벤트 ID를 기준으로 이벤트를 정렬합니다.  이벤트 ID를 사용 하 여 이벤트를 검색할 [214-OperationCompleted](../../../../../docs/framework/wcf/diagnostics/etw/214-operationcompleted.md)합니다.  이 이벤트는 완료된 작업과 해당 작업의 기간을 보여 줍니다.  다음 이벤트는 Add 작업의 기간을 보여 줍니다.  
  
    ```Output  
    An OperationInvoker completed the call to the 'Add' method.  The method call duration was '3' ms.  
    ```
