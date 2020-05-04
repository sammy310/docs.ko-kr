---
title: Visual Basic 애플리케이션 모델 개요
ms.date: 07/20/2015
helpviewer_keywords:
- My.Application object [Visual Basic], Visual Basic application model
- Visual Basic application model
ms.assetid: 17538984-84fe-43c9-82c8-724c9529fe8b
ms.openlocfilehash: aa47304cf2bded93bdb95ffe7dfa35bb37d9a643
ms.sourcegitcommit: f348c84443380a1959294cdf12babcb804cfa987
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/12/2019
ms.locfileid: "73976468"
---
# <a name="overview-of-the-visual-basic-application-model"></a>Visual Basic 애플리케이션 모델 개요

Visual Basic는 Windows Forms 애플리케이션의 동작을 제어하기 위한 잘 정의된 모델인 Visual Basic 애플리케이션 모델을 제공합니다. 이 모델에는 처리되지 않은 예외를 catch하는 이벤트뿐만 아니라 애플리케이션의 시작 및 종료를 처리하는 이벤트가 포함됩니다. 또한 단일 인스턴스 애플리케이션 개발도 지원합니다. 애플리케이션 모델은 확장 가능하므로 더 많은 제어가 필요한 개발자는 재정의 가능한 메서드를 사용자 지정할 수 있습니다.  
  
## <a name="uses-for-the-application-model"></a>애플리케이션 모델 용도  

 일반적인 애플리케이션은 시작하고 종료할 때 작업을 수행해야 합니다. 예를 들어 애플리케이션은 시작할 때 시작 화면을 표시하고, 데이터베이스 연결을 설정하고, 저장된 상태를 로드하는 등의 작업을 수행할 수 있습니다. 애플리케이션은 종료할 때 데이터베이스 연결을 닫고 현재 상태를 저장할 수 있습니다. 또한 애플리케이션은 처리되지 않은 예외와 같이 애플리케이션이 예기치 않게 종료될 때 특정 코드를 실행할 수 있습니다.  
  
 Visual Basic 애플리케이션 모델을 사용하면 *단일 인스턴스* 애플리케이션을 쉽게 만들 수 있습니다. 단일 인스턴스 애플리케이션을 하는 일반적인 애플리케이션에서 애플리케이션의 인스턴스 하나만 실행할 수 있습니다 번 다릅니다. 단일 인스턴스 애플리케이션의 다른 인스턴스를 시작하려고 하면 `StartupNextInstance` 이벤트를 통해 원래 인스턴스에 다른 시작 시도가 실행되었음을 알리는 메시지가 표시됩니다. 이 알림에는 후속 인스턴스의 명령줄 인수가 포함됩니다. 그러면 애플리케이션의 후속 인스턴스는 초기화가 발생하기 전에 닫힙니다.  
  
 단일 인스턴스 애플리케이션은 시작하면서 애플리케이션의 첫 번째 인스턴스인지 또는 후속 인스턴스인지를 확인합니다.  
  
- 첫 번째 인스턴스일 경우 정상적으로 시작합니다.  
  
- 첫 번째 인스턴스가 실행되는 동안 애플리케이션을 시작하려는 각 후속 시도마다 매우 다른 동작이 발생합니다. 후속 시도는 첫 번째 인스턴스에 명령줄 인수를 알린 다음 즉시 종료됩니다. 첫 번째 인스턴스는 `StartupNextInstance` 이벤트를 처리하여 후속 인스턴스의 명령줄 인수를 확인하고 계속 실행됩니다.  
  
     다음 다이어그램에서는 후속 인스턴스가 첫 번째 인스턴스에 알림을 보내는 방법을 보여 줍니다.  
  
     ![단일 인스턴스 애플리케이션 이미지를 표시하는 다이어그램.](./media/overview-of-the-visual-basic-application-model/single-instance-application.gif)  
  
 `StartupNextInstance` 이벤트를 처리하여 단일 인스턴스 애플리케이션이 동작하는 방식을 제어할 수 있습니다. 예를 들어 Microsoft Outlook은 일반적으로 단일 인스턴스 애플리케이션으로 실행됩니다. Outlook이 실행 중일 때 Outlook을 다시 시작하려고 하면 포커스가 원래 인스턴스로 이동하지만 다른 인스턴스는 열리지 않습니다.  
  
## <a name="events-in-the-application-model"></a>애플리케이션 모델 이벤트  

 애플리케이션 모델에서 발생할 수 있는 이벤트는 다음과 같습니다.  
  
- **애플리케이션 시작**. 애플리케이션은 시작할 때 <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.Startup> 이벤트를 발생시킵니다. 이 이벤트를 처리하여 기본 폼이 로드되기 전에 애플리케이션을 초기화하는 코드를 추가할 수 있습니다. 또한 `Startup` 이벤트는 원하는 경우 시작 프로세스의 해당 단계에서 애플리케이션의 실행을 취소하는 데에도 사용됩니다.  
  
     애플리케이션 시작 코드가 실행되는 동안 시작 화면을 표시하도록 애플리케이션을 구성할 수 있습니다. 기본적으로 애플리케이션 모델은 `/nosplash` 또는 `-nosplash` 명령줄 인수를 사용하는 경우 시작 화면을 표시하지 않습니다.  
  
- **단일 인스턴스 응용 프로그램**. <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.StartupNextInstance> 이벤트는 단일 인스턴스 애플리케이션의 후속 인스턴스가 시작할 때 발생합니다. 이 이벤트는 후속 인스턴스의 명령줄 인수를 전달합니다.  
  
- **처리되지 않은 예외**. 애플리케이션은 처리되지 않은 예외가 발생하면 <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.UnhandledException> 이벤트를 발생시킵니다. 이 이벤트에 대한 처리기는 예외를 검사하고 실행을 계속할지 여부를 결정할 수 있습니다.  
  
     경우에 따라 `UnhandledException` 이벤트가 발생하지 않을 수 있습니다. 자세한 내용은 <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.UnhandledException>를 참조하세요.  
  
- **네트워크 연결 변경**. 컴퓨터의 네트워크 가용성이 변경되면 애플리케이션이 <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.NetworkAvailabilityChanged> 이벤트를 발생시킵니다.  
  
     경우에 따라 `NetworkAvailabilityChanged` 이벤트가 발생하지 않을 수 있습니다. 자세한 내용은 <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.NetworkAvailabilityChanged>를 참조하세요.  
  
- **애플리케이션 종료**. 애플리케이션은 종료 시 신호를 보내는 <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.Shutdown> 이벤트를 제공합니다. 이 이벤트 처리기에서 애플리케이션이 수행해야 하는 작업(예: 닫기 및 저장)이 완료되었는지 확인할 수 있습니다. 기본 폼이 닫힐 때 종료하도록 또는 모든 폼이 닫힐 때만 종료하도록 애플리케이션을 구성할 수 있습니다.  
  
## <a name="availability"></a>가용성  

 기본적으로 Visual Basic 애플리케이션 모델은 Windows Forms 프로젝트에 사용할 수 있습니다. 다른 시작 개체를 사용하도록 애플리케이션을 구성하거나 사용자 지정 `Sub Main`를 사용하여 애플리케이션 코드를 시작하는 경우 애플리케이션 모델을 사용하려면 해당 개체 또는 클래스가 <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase> 클래스의 구현을 제공해야 할 수 있습니다. 시작 개체를 변경하는 방법에 대한 자세한 내용은 [애플리케이션 페이지, 프로젝트 디자이너(Visual Basic)](/visualstudio/ide/reference/application-page-project-designer-visual-basic)를 참조하세요.  
  
## <a name="see-also"></a>참조

- <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase>
- <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.Startup>
- <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.StartupNextInstance>
- <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.UnhandledException>
- <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.Shutdown>
- <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.NetworkAvailabilityChanged>
- <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase>
- [Visual Basic 애플리케이션 모델 확장](../../../visual-basic/developing-apps/customizing-extending-my/extending-the-visual-basic-application-model.md)
