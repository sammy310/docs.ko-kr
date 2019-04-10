---
title: '작업 1: 새 Windows Presentation Foundation 애플리케이션 만들기'
ms.date: 03/30/2017
ms.assetid: 270eaeba-9492-4532-af9f-403ce5c9935b
ms.openlocfilehash: dae523714862ed36d36e65b51be62acff9b17f51
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59193403"
---
# <a name="task-1-create-a-new-windows-presentation-foundation-application"></a>작업 1: 새 Windows Presentation Foundation 애플리케이션 만들기
이 태스크에서는 빈 Windows Presentation Foundation (WPF) 응용 프로그램을 WPF 응용 프로그램에 대 한 Visual Studio 템플릿을 사용 하 여 만들고 적절 한 참조를 추가 [!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)] 워크플로 어셈블리입니다.  
  
### <a name="to-create-the-wpf-application-project"></a>WPF 응용 프로그램 프로젝트를 만들려면  
  
1.  Visual Studio를 열고 고는 **파일** 메뉴에서 **새로 만들기**를 클릭 하 고 **프로젝트**.  
  
2.  에 **새 프로젝트** 대화 상자 중 하나를 선택 합니다 **Visual C#**  또는 **Visual Basic** 에서 **설치 된 템플릿** 왼쪽 창 쪽 상자입니다. 사용자가 선택한 언어로 나타나지 않으면 아래를 봅니다 **다른 언어**합니다.  
  
3.  선택 **Windows** 에 **설치 된 템플릿** 창입니다.  
  
4.  위쪽 창에 있는지를 확인 (기본값) **.NET Framework 4** 드롭다운 목록 상자에서 선택한 다음 선택 되었습니다 **WPF 응용 프로그램**합니다.  
  
5.  프로젝트의 이름을 설정 **HostingApplication** 창의 맨 아래에 있습니다.  
  
6.  솔루션 이름으로 설정할 **RehostingTheDesigner**합니다.  
  
7.  클릭 **확인** 응용 프로그램 프로젝트를 만듭니다. Visual Studio 응용 프로그램에 대 한 기본 WPF UI를 만들고 적절 한 XAML 및 코드 숨김 파일을 포함 합니다.  
  
8.  에 대 한 참조를 추가 **WorkflowModel** 어셈블리입니다. 이렇게 하려면 **솔루션 탐색기**를 마우스 오른쪽 단추로 클릭 합니다 **HostingApplication** 프로젝트를 마우스 **참조 추가**합니다.  
  
9. 에 **참조 추가** 대화 상자에서 클릭 합니다 **.NET** 탭, CTRL 키를 누른 하 고, 다음 어셈블리를 선택 하 고 클릭 **확인**:  
  
    -   System.Activities  
  
    -   System.Activities.Presentation  
  
    -   System.Activities.Core.Presentation  
  
10. **확인**을 클릭합니다.  
  
11. 참조 [작업 2: 워크플로 디자이너 호스트](task-2-host-the-workflow-designer.md) 을 workflow designer 디자인 캔버스를 호스트 하는 방법을 알아봅니다.  
  
## <a name="see-also"></a>참고자료

- [Workflow Designer 재호스팅](rehosting-the-workflow-designer.md)
- [작업 2: 워크플로 디자이너 호스트](task-2-host-the-workflow-designer.md)
