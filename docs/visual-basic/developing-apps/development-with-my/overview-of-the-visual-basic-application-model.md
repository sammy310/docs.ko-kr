---
title: Visual Basic 애플리케이션 모델 개요
ms.date: 07/20/2015
helpviewer_keywords:
- My.Application object [Visual Basic], Visual Basic application model
- Visual Basic application model
ms.assetid: 17538984-84fe-43c9-82c8-724c9529fe8b
ms.openlocfilehash: aa47304cf2bded93bdb95ffe7dfa35bb37d9a643
ms.sourcegitcommit: f348c84443380a1959294cdf12babcb804cfa987
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/12/2019
ms.locfileid: "73976468"
---
# <a name="overview-of-the-visual-basic-application-model"></a>Visual Basic 애플리케이션 모델 개요

Visual Basic Windows Forms 응용 프로그램의 동작을 제어 하기 위한 잘 정의 된 모델 Visual Basic 응용 프로그램 모델을 제공 합니다. 이 모델에는 처리 되지 않은 예외를 catch 하는 이벤트 뿐만 아니라 응용 프로그램의 시작 및 종료를 처리 하는 이벤트가 포함 됩니다. 또한 단일 인스턴스 응용 프로그램을 개발할 수 있도록 지원 합니다. 응용 프로그램 모델은 확장 가능 하므로 더 많은 제어가 필요한 개발자는 재정의 가능한 메서드를 사용자 지정할 수 있습니다.  
  
## <a name="uses-for-the-application-model"></a>응용 프로그램 모델에 사용  

 일반적인 응용 프로그램은 시작 되 고 종료 될 때 작업을 수행 해야 합니다. 예를 들어 시작할 때 응용 프로그램은 시작 화면을 표시 하 고, 데이터베이스 연결을 설정 하 고, 저장 된 상태를 로드 하는 등의 작업을 수행할 수 있습니다. 응용 프로그램이 종료 되 면 데이터베이스 연결을 닫고 현재 상태를 저장할 수 있습니다. 또한 응용 프로그램은 처리 되지 않은 예외와 같이 응용 프로그램이 예기치 않게 종료 될 때 특정 코드를 실행할 수 있습니다.  
  
 Visual Basic 응용 프로그램 모델을 사용 하면 *단일 인스턴스* 응용 프로그램을 쉽게 만들 수 있습니다. 단일 인스턴스 애플리케이션을 하는 일반적인 애플리케이션에서 애플리케이션의 인스턴스 하나만 실행할 수 있습니다 번 다릅니다. 단일 인스턴스 응용 프로그램의 다른 인스턴스를 시작 하려고 하면 `StartupNextInstance` 이벤트를 사용 하 여 원래 인스턴스가 다른 시작 시도가 수행 되었음을 알리는 메시지가 표시 됩니다. 알림은 후속 인스턴스의 명령줄 인수를 포함 합니다. 그런 다음 응용 프로그램의 후속 인스턴스는 초기화가 발생 하기 전에 닫힙니다.  
  
 단일 인스턴스 응용 프로그램이 시작 되 고 응용 프로그램의 첫 번째 인스턴스인지 또는 후속 인스턴스인지를 확인 합니다.  
  
- 첫 번째 인스턴스이면 정상적으로 시작 합니다.  
  
- 첫 번째 인스턴스가 실행 되는 동안 응용 프로그램을 시작할 때마다 다른 동작이 발생 합니다. 이후 시도는 첫 번째 인스턴스에 명령줄 인수를 알린 다음 즉시 종료 됩니다. 첫 번째 인스턴스는 `StartupNextInstance` 이벤트를 처리 하 여 후속 인스턴스의 명령줄 인수를 확인 하 고 계속 실행 합니다.  
  
     다음 다이어그램에서는 후속 인스턴스가 첫 번째 인스턴스를 신호로 알리는 방법을 보여 줍니다.  
  
     ![단일 인스턴스 응용 프로그램 이미지를 표시 하는 다이어그램입니다.](./media/overview-of-the-visual-basic-application-model/single-instance-application.gif)  
  
 `StartupNextInstance` 이벤트를 처리 하 여 단일 인스턴스 응용 프로그램이 동작 하는 방식을 제어할 수 있습니다. 예를 들어 Microsoft Outlook은 일반적으로 단일 인스턴스 응용 프로그램으로 실행 됩니다. Outlook이 실행 중이 고 Outlook을 다시 시작 하려고 하면 원래 인스턴스로 포커스가 이동 하지만 다른 인스턴스는 열리지 않습니다.  
  
## <a name="events-in-the-application-model"></a>응용 프로그램 모델의 이벤트  

 응용 프로그램 모델에 있는 이벤트는 다음과 같습니다.  
  
- **응용 프로그램 시작**. 응용 프로그램은 시작 될 때 <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.Startup> 이벤트를 발생 시킵니다. 이 이벤트를 처리 하 여 기본 폼이 로드 되기 전에 응용 프로그램을 초기화 하는 코드를 추가할 수 있습니다. 또한 `Startup` 이벤트는 원하는 경우 시작 프로세스의 해당 단계에서 응용 프로그램의 실행을 취소 하는 데 제공 됩니다.  
  
     응용 프로그램 시작 코드가 실행 되는 동안 시작 화면을 표시 하도록 응용 프로그램을 구성할 수 있습니다. 기본적으로 응용 프로그램 모델은 `/nosplash` 또는 `-nosplash` 명령줄 인수를 사용 하는 경우 시작 화면을 표시 하지 않습니다.  
  
- **단일 인스턴스 응용 프로그램**. <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.StartupNextInstance> 이벤트는 단일 인스턴스 응용 프로그램의 후속 인스턴스가 시작 될 때 발생 합니다. 이 이벤트는 후속 인스턴스의 명령줄 인수를 전달 합니다.  
  
- **처리 되지 않은 예외**입니다. 응용 프로그램이 처리 되지 않은 예외를 발견 하면 <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.UnhandledException> 이벤트를 발생 시킵니다. 해당 이벤트에 대 한 처리기는 예외를 검사 하 고 실행을 계속할지 여부를 결정할 수 있습니다.  
  
     경우에 따라 `UnhandledException` 이벤트는 발생 하지 않습니다. 자세한 내용은 <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.UnhandledException>를 참조하세요.  
  
- **네트워크 연결 변경** 컴퓨터의 네트워크 가용성이 변경 되 면 응용 프로그램에서 <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.NetworkAvailabilityChanged> 이벤트를 발생 시킵니다.  
  
     경우에 따라 `NetworkAvailabilityChanged` 이벤트는 발생 하지 않습니다. 자세한 내용은 <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.NetworkAvailabilityChanged>를 참조하세요.  
  
- **응용 프로그램이 종료**되었습니다. 응용 프로그램이 종료 되려고 할 때 신호를 보내는 <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.Shutdown> 이벤트를 제공 합니다. 이 이벤트 처리기에서 응용 프로그램이 수행 해야 하는 작업 (예: 닫기 및 저장)이 완료 되었는지 확인할 수 있습니다. 기본 폼이 닫힐 때 종료 하도록 응용 프로그램을 구성 하거나 모든 양식이 닫힐 때만 종료할 수 있습니다.  
  
## <a name="availability"></a>가용성  

 기본적으로 Visual Basic 응용 프로그램 모델은 Windows Forms 프로젝트에 사용할 수 있습니다. 응용 프로그램에서 다른 시작 개체를 사용 하도록 구성 하거나 사용자 지정 `Sub Main`를 사용 하 여 응용 프로그램 코드를 시작 하는 경우, 해당 개체 또는 클래스가 <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase> 클래스의 구현을 제공 하 여 응용 프로그램 모델을 사용 해야 할 수 있습니다. 시작 개체를 변경 하는 방법에 대 한 자세한 내용은 [응용 프로그램 페이지, 프로젝트 디자이너 (Visual Basic)](/visualstudio/ide/reference/application-page-project-designer-visual-basic)를 참조 하세요.  
  
## <a name="see-also"></a>참조

- <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase>
- <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.Startup>
- <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.StartupNextInstance>
- <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.UnhandledException>
- <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.Shutdown>
- <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.NetworkAvailabilityChanged>
- <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase>
- [Visual Basic 애플리케이션 모델 확장](../../../visual-basic/developing-apps/customizing-extending-my/extending-the-visual-basic-application-model.md)
