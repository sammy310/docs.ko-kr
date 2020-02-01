---
title: 메시지 큐(MSMQ) 설치
ms.date: 03/30/2017
ms.assetid: 7ddcd497-3e04-427e-bc04-3610ad98b01e
ms.openlocfilehash: 8ecbd07adfb6bfb4e9898f9b8508809480d17e16
ms.sourcegitcommit: cdf5084648bf5e77970cbfeaa23f1cab3e6e234e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/01/2020
ms.locfileid: "76921097"
---
# <a name="installing-message-queuing-msmq"></a>메시지 큐(MSMQ) 설치
다음 절차에서는 메시지 큐 4.0 및 메시지 큐 3.0을 설치하는 방법을 보여 줍니다.  
  
> [!NOTE]
> 메시지 큐 4.0은 Windows XP 및 Windows Server 2003에서 사용할 수 없습니다.  
  
#### <a name="to-install-message-queuing-40-on-windows-server-2008-or-windows-server-2008-r2"></a>Windows Server 2008 또는 Windows Server 2008 R2에 메시지 큐 4.0을 설치하려면  
  
1. 서버 관리자에서 **기능**을 클릭 합니다.  
  
2. 오른쪽 창의 **기능 요약**에서 **기능 추가**를 클릭 합니다.  
  
3. 결과 창에서 **메시지 큐**를 확장 합니다.  
  
4. **메시지 큐 서비스**를 확장 합니다.  
  
5. **디렉터리 서비스 통합** (도메인에 가입 된 컴퓨터의 경우)을 클릭 한 다음 **HTTP 지원**을 클릭 합니다.  
  
6. **다음**을 클릭 한 후 **설치**를 클릭 합니다.  
  
#### <a name="to-install-message-queuing-40-on-windows-7-or-windows-vista"></a>Windows 7 또는 Windows Vista에 메시지 큐 4.0을 설치하려면  
  
1. **제어판**을 엽니다.  
  
2. **프로그램** 을 클릭 하 고 **프로그램 및 기능**에서 **Windows 기능 사용/사용 안 함**을 클릭 합니다.  
  
3. Microsoft Message Queue(MSMQ) Server, Microsoft Message Queue(MSMQ) Server Core를 차례로 확장하고 다음 메시지 큐 기능의 확인란을 선택하여 설치합니다.  
  
    - MSMQ Active Directory 도메인 서비스 통합(도메인에 연결된 컴퓨터의 경우)  
  
    - MSMQ HTTP 지원  
  
4. **확인**을 클릭합니다.  
  
5. 컴퓨터를 다시 시작할지 묻는 메시지가 표시 되 면 **확인** 을 클릭 하 여 설치를 완료 합니다.  
  
#### <a name="to-install-message-queuing-30-on-windows-xp-and-windows-server-2003"></a>Windows XP 및 Windows Server 2003에 메시지 큐 3.0을 설치하려면  
  
1. **제어판**을 엽니다.  
  
2. **프로그램 추가/제거** 를 클릭 한 다음 **Windows 구성 요소 추가**를 클릭 합니다.  
  
3. 메시지 큐를 선택 하 고 **세부 정보**를 클릭 합니다.  
  
    > [!NOTE]
    > Windows Server 2003를 실행 하는 경우 응용 프로그램 서버를 선택 하 여 메시지 큐에 액세스 합니다.  
  
4. MSMQ HTTP 지원 옵션이 자세히 페이지에 선택되어 있는지 확인합니다.  
  
5. **확인** 을 클릭 하 여 세부 정보 페이지를 종료 하 고 **다음**을 클릭 합니다. 설치를 완료합니다.  
  
6. 컴퓨터를 다시 시작할지 묻는 메시지가 표시 되 면 **확인** 을 클릭 하 여 설치를 완료 합니다.  
  
## <a name="see-also"></a>참조

- [설치 지침](../../../../docs/framework/wcf/samples/set-up-instructions.md)
