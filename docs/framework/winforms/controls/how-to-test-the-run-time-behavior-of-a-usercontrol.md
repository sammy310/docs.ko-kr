---
title: '방법: UserControl의 런타임 동작 테스트'
ms.date: 03/30/2017
helpviewer_keywords:
- UserControl class [Windows Forms], testing
- user controls [Windows Forms], testing
- composite controls [Windows Forms], testing
- UserControl Test Container
- UserControl class [Windows Forms], run-time behavior
ms.assetid: 4e4d5c49-1346-40ac-9d96-40211b573583
ms.openlocfilehash: 15b37c71e6643b588c0378510965a9a3e7cb56e9
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59321772"
---
# <a name="how-to-test-the-run-time-behavior-of-a-usercontrol"></a>방법: UserControl의 런타임 동작 테스트
개발 하는 경우는 <xref:System.Windows.Forms.UserControl>, 해당 런타임 동작을 테스트 해야 합니다. 별도 Windows 기반 응용 프로그램 프로젝트를 만들고 테스트 폼에서 컨트롤을 배치할 수 있지만이 절차를 편리 하 게 아닙니다. 빠르고 쉽게 방법을 사용 하는 것은 **UserControl 테스트 컨테이너** Visual Studio에서 제공 합니다. 이 테스트 컨테이너는 Windows 컨트롤 라이브러리 프로젝트에서 직접 시작합니다.  
  
> [!IMPORTANT]
>  로드 테스트 컨테이너에 대 한 프로그램 <xref:System.Windows.Forms.UserControl>를 컨트롤에는 하나 이상의 공용 생성자가 있어야 합니다.  
  
> [!NOTE]
>  표시되는 대화 상자와 메뉴 명령은 활성 설정이나 버전에 따라 도움말에서 설명하는 것과 다를 수 있습니다. 설정을 변경하려면 **도구** 메뉴에서 **설정 가져오기 및 내보내기** 를 선택합니다. 자세한 내용은 [Visual Studio IDE 개인 설정](/visualstudio/ide/personalizing-the-visual-studio-ide)을 참조하세요.  
  
> [!NOTE]
>  시각적 개체 C++ 컨트롤을 사용 하 여 테스트할 수 없습니다 합니다 **UserControl 테스트 컨테이너**합니다.  
  
### <a name="to-test-the-run-time-behavior-of-a-usercontrol"></a>UserControl의 런타임 동작을 테스트 하려면  
  
1. 라는 Windows 컨트롤 라이브러리 프로젝트를 만듭니다 **컨트롤**합니다. 자세한 내용은 참조 하세요 [Windows 컨트롤 라이브러리 템플릿을](https://docs.microsoft.com/previous-versions/kxczf775(v=vs.100))합니다.  
  
2. 에 **Windows Forms 디자이너**를 끌어를 <xref:System.Windows.Forms.Label> 에서 제어를 **도구 상자** 컨트롤의 디자인 화면으로 합니다.  
  
3. F5 키를 눌러 프로젝트를 빌드 및 실행 하는 **UserControl 테스트 컨테이너**합니다. 테스트 컨테이너에 표시 하 <xref:System.Windows.Forms.UserControl> 에 **미리 보기** 창.  
  
4. 선택는 <xref:System.Windows.Forms.Control.BackColor%2A> 에 표시 되는 속성을 <xref:System.Windows.Forms.PropertyGrid> 컨트롤의 오른쪽에는 **미리 보기** 창. 해당 값을 변경할 `ControlDark`합니다. 컨트롤 어두운 색으로 변경 되는지 관찰 합니다. 다른 속성 값을 변경 하 고 컨트롤에 대 한 효과 관찰 합니다.  
  
5. 클릭 합니다 **사용자 정의 컨트롤 전체 도킹** 아래 확인란 합니다 **미리 보기** 창입니다. 컨트롤의 창에 맞게 크기가 조정 됩니다 있는지 확인 합니다. 테스트 컨테이너 크기를 조정 하 고 컨트롤의 창 크기 조정 되는 관찰 합니다.  
  
6. 테스트 컨테이너를 닫습니다.  
  
7. 다른 사용자 정의 컨트롤을 추가 합니다 **컨트롤** 프로젝트입니다. 자세한 내용은 [방법: 프로젝트에 기존 항목 추가](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/9f4t9t92(v=vs.100))합니다.  
  
8. 에 **Windows Forms 디자이너**를 끌어를 <xref:System.Windows.Forms.Button> 에서 제어를 **도구 상자** 컨트롤의 디자인 화면으로 합니다.  
  
9. F5 키를 눌러 프로젝트를 빌드 및 테스트 컨테이너를 실행 합니다.  
  
10. 클릭 합니다 **사용자 정의 컨트롤 선택** <xref:System.Windows.Forms.ComboBox> 두 개의 사용자 정의 컨트롤을 전환 하 합니다.  
  
## <a name="testing-user-controls-from-another-project"></a>다른 프로젝트에서 사용자 정의 컨트롤 테스트  
 현재 프로젝트의 테스트 컨테이너에서 다른 프로젝트에서 사용자 정의 컨트롤을 테스트할 수 있습니다.  
  
#### <a name="to-test-user-controls-from-another-project"></a>다른 프로젝트에서 사용자 정의 컨트롤을 테스트 하려면  
  
1. 라는 Windows 컨트롤 라이브러리 프로젝트를 만듭니다 **TestContainerExample2**합니다. 자세한 내용은 참조 하세요 [Windows 컨트롤 라이브러리 템플릿을](https://docs.microsoft.com/previous-versions/kxczf775(v=vs.100))합니다.  
  
2. 에 **Windows Forms 디자이너**를 끌어를 <xref:System.Windows.Forms.RadioButton> 에서 제어를 **도구 상자** 컨트롤의 디자인 화면으로 합니다.  
  
3. F5 키를 눌러 프로젝트를 빌드 및 테스트 컨테이너를 실행 합니다. 테스트 컨테이너에 표시 하 <xref:System.Windows.Forms.UserControl> 에 **미리 보기** 창.  
  
4. 클릭 합니다 **부하** 단추입니다.  
  
5. 에 **엽니다** 대화 상자에서 **컨트롤**이전 절차에서 만든.dll입니다. 선택 **컨트롤**.dll 및 클릭 합니다 **오픈** 사용자 정의 컨트롤을 로드 하려면 단추를  
  
6. 사용 합니다 **사용자 정의 컨트롤을 선택** <xref:System.Windows.Forms.ComboBox> 에서 두 개의 사용자 정의 컨트롤을 전환 하는 **컨트롤** 프로젝트입니다.  
  
## <a name="see-also"></a>참고자료

- <xref:System.Windows.Forms.UserControl>
- [방법: 복합 컨트롤 제작](how-to-author-composite-controls.md)
- [연습: Visual Basic에서 합성 컨트롤 제작](walkthrough-authoring-a-composite-control-with-visual-basic.md)
- [연습: 시각적 개체를 사용 하 여 복합 컨트롤 제작C#](walkthrough-authoring-a-composite-control-with-visual-csharp.md)
- [사용자 정의 컨트롤 디자이너](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/183c3hth(v=vs.100))
