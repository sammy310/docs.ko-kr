---
title: '연습: 디자인 타임에 사용자 지정 Windows Forms 컨트롤 디버깅'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- debugging [Visual Studio], walkthroughs
- custom controls [Windows Forms], walkthroughs
- visual editors
- debugging [Visual Studio], Windows Forms
- custom controls [Windows Forms], debugging
- designers
- controls [Windows Forms], debugging
- walkthroughs [Windows Forms], debugging
- design-time debugging
ms.assetid: 1fd83ccd-3798-42fc-85a3-6cba99467387
ms.openlocfilehash: 9bd3f822e5a1f8572ebb7f5991abccde904150b8
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/09/2019
ms.locfileid: "57717832"
---
# <a name="walkthrough-debugging-custom-windows-forms-controls-at-design-time"></a>연습: 디자인 타임에 사용자 지정 Windows Forms 컨트롤 디버깅
사용자 지정 컨트롤을 만들려면 확인할 수 있습니다 종종 해당 디자인 타임 동작을 디버그 하는 데 필요한 합니다. 사용자 지정 컨트롤에 대 한 사용자 지정 디자이너를 제작 하는 경우 특히 그렇습니다. 세부 정보를 참조 하세요. [연습: Visual Studio 디자인 타임 기능을 활용 하는 컨트롤을 Forms는 Windows 만들기](creating-a-wf-control-design-time-features.md)합니다.  
  
 다른.NET Framework 클래스를 디버그할 때 처럼 Visual Studio를 사용 하 여 사용자 지정 컨트롤을 디버그할 수 있습니다. 차이점은 사용자 지정 컨트롤의 코드를 실행 하는 Visual Studio의 개별 인스턴스를 디버깅 합니다.  
  
 이 연습에서 설명하는 작업은 다음과 같습니다.  
  
-   사용자 지정 컨트롤을 호스트 하는 Windows Forms 프로젝트 만들기  
  
-   컨트롤 라이브러리 프로젝트 만들기  
  
-   사용자 지정 컨트롤에 속성 추가  
  
-   호스트 형식에 사용자 지정 컨트롤 추가  
  
-   디자인 타임 디버깅에 대 한 프로젝트 설정  
  
-   디자인 타임에 사용자 지정 컨트롤 디버깅  
  
 작업을 완료 하는 경우에 사용자 지정 컨트롤의 디자인 타임 동작을 디버깅 하는 데 필요한 작업을 이해를 해야 합니다.  
  
> [!NOTE]
>  표시되는 대화 상자와 메뉴 명령은 활성 설정이나 버전에 따라 도움말에서 설명하는 것과 다를 수 있습니다. 설정을 변경하려면 **도구** 메뉴에서 **설정 가져오기 및 내보내기** 를 선택합니다. 자세한 내용은 [Visual Studio IDE 개인 설정](/visualstudio/ide/personalizing-the-visual-studio-ide)을 참조하세요.  
  
## <a name="creating-the-project"></a>프로젝트 만들기  
 첫 번째 단계는 응용 프로그램 프로젝트를 만드는 것입니다. 사용자 지정 컨트롤을 호스팅하는 응용 프로그램을 빌드하려면이 프로젝트를 사용 합니다.  
  
#### <a name="to-create-the-project"></a>프로젝트를 만들려면  
  
-   "DebuggingExample" 라는 Windows 응용 프로그램 프로젝트를 만듭니다 (**파일** > **새로 만들기** > **프로젝트**  >  **Visual C#** 나 **Visual Basic** > **클래식 데스크톱** > **Windows Forms 응용 프로그램**).  
  
## <a name="creating-a-control-library-project"></a>컨트롤 라이브러리 프로젝트 만들기  
 다음 단계는 컨트롤 라이브러리 프로젝트를 만들고 사용자 지정 컨트롤을 설정 하는 것입니다.  
  
#### <a name="to-create-the-control-library-project"></a>컨트롤 라이브러리 프로젝트를 만들려면  
  
1.  추가 된 **Windows 컨트롤 라이브러리** 프로젝트를 솔루션입니다.  
  
2.  새 **UserControl** DebugControlLibrary 프로젝트 항목입니다. 자세한 내용은 [방법: 새 프로젝트 항목 추가](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/w0572c5b(v=vs.100))합니다. 새 소스 파일 "DebugControl"의 기본 이름을 지정 합니다.  
  
3.  사용 하는 **솔루션 탐색기**, 프로젝트의 기본 컨트롤의 기본 이름 사용 하 여 코드 파일을 삭제 하 여 삭제 "`UserControl1`". 자세한 내용은 [방법: 제거, 삭제 및 항목을 제외](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/0ebzhwsk(v=vs.100))합니다.  
  
4.  솔루션을 빌드합니다.  
  
## <a name="checkpoint"></a>검사점  
 이 시점에서 사용자 지정 컨트롤을 볼 수는 합니다 **도구 상자**합니다.  
  
#### <a name="to-check-your-progress"></a>진행률을 확인 하려면  
  
-   라는 새 탭을 찾습니다 **DebugControlLibrary 구성 요소** 클릭 하 여 선택 합니다. 열리는 컨트롤으로 나열 표시 됩니다 **DebugControl** 그 옆에 있는 기본 아이콘을 사용 하 여 합니다.  
  
## <a name="adding-a-property-to-your-custom-control"></a>사용자 지정 컨트롤에 속성 추가  
 디자인 타임에 사용자 지정 컨트롤의 코드 실행 되 고 있는지를 보여 주기 위해 속성을 추가 하 고 속성을 구현 하는 코드에 중단점을 설정 합니다.  
  
#### <a name="to-add-a-property-to-your-custom-control"></a>사용자 지정 컨트롤에 속성을 추가 하려면  
  
1.  오픈 **DebugControl** 에 **코드 편집기**합니다. 클래스 정의에 다음 코드를 추가 합니다.  
  
    ```vb  
    Private demoStringValue As String = Nothing  
    <BrowsableAttribute(true)>  
    Public Property DemoString() As String  
  
        Get  
            Return Me.demoStringValue  
        End Get  
  
        Set(ByVal value As String)  
            Me.demoStringValue = value  
        End Set  
  
    End Property  
    ```  
  
    ```csharp  
    private string demoStringValue = null;  
    [Browsable(true)]  
    public string DemoString  
    {  
        get  
        {  
            return this.demoStringValue;  
        }  
        set  
        {  
            demoStringValue = value;  
        }  
    }  
    ```  
  
2.  솔루션을 빌드합니다.  
  
## <a name="adding-your-custom-control-to-the-host-form"></a>호스트 형식에 사용자 지정 컨트롤 추가  
 사용자 지정 컨트롤의 디자인 타임 동작을 디버깅 하려면 호스트 양식의 사용자 지정 컨트롤 클래스의 인스턴스를 배치 됩니다.  
  
#### <a name="to-add-your-custom-control-to-the-host-form"></a>호스트 폼에 사용자 지정 컨트롤을 추가 하려면  
  
1.  "DebuggingExample" 프로젝트에서의 Form1을 엽니다는 **Windows Forms 디자이너**합니다.  
  
2.  에 **도구 상자**를 엽니다는 **DebugControlLibrary 구성 요소** 끌어서 탭을 **DebugControl** 폼에 인스턴스.  
  
3.  찾을 합니다 `DemoString` 에서 사용자 지정 속성을 **속성** 창입니다. 참고 다른 속성과 마찬가지로 해당 값을 변경할 수 있습니다. 또한를 `DemoString` 속성을 선택 하면 속성의 설명 문자열의 맨 아래에 표시 되는 **속성** 창입니다.  
  
## <a name="setting-up-the-project-for-design-time-debugging"></a>디자인 타임 디버깅에 대 한 프로젝트 설정  
 사용자 지정 컨트롤의 디자인 타임 동작을 디버깅 하려면 사용자 지정 컨트롤의 코드를 실행 하는 Visual Studio의 개별 인스턴스를 디버깅 합니다.  
  
#### <a name="to-set-up-the-project-for-design-time-debugging"></a>디자인 타임 디버깅을 위해 프로젝트를 설정 하려면  
  
1.  마우스 오른쪽 단추로 클릭 합니다 **DebugControlLibrary** 프로젝트에 **솔루션 탐색기** 선택한 **속성**합니다.  
  
2.  에 **DebugControlLibrary** 속성 시트를 선택 합니다 **디버그** 탭 합니다.  
  
     에 **시작 작업** 섹션에서 **시작 외부 프로그램**합니다. 해야 줄임표 하므로 별도 인스턴스, Visual Studio의 디버깅 (![VisualStudioEllipsesButton 스크린 샷](../media/vbellipsesbutton.png "vbEllipsesButton")) 클릭 하 여 Visual Studio IDE에 대 한 검색 합니다. 실행 파일의 이름은 **devenv.exe**, 되며 해당 경로 %programfiles%\Microsoft Visual Studio 9.0\Common7\IDE\devenv.exe 기본 위치에 설치한 경우.  
  
3.  **확인** 을 클릭하여 대화 상자를 닫습니다.  
  
4.  마우스 오른쪽 단추로 클릭 합니다 **DebugControlLibrary** 프로젝트를 마우스 **시작 프로젝트로 설정** 디버깅이 구성을 사용 하도록 설정 합니다.  
  
## <a name="debugging-your-custom-control-at-design-time"></a>디자인 타임에 사용자 지정 컨트롤 디버깅  
 이제 디자인 모드로 실행 될 때 사용자 지정 컨트롤을 디버그할 준비가 되었습니다. 디버깅 세션을 시작 하면 Visual Studio의 새 인스턴스를 만들어지고 "DebuggingExample" 솔루션을 로드 하는 데 사용할 수 있습니다. Form1에서 열면 합니다 **Forms 디자이너**, 사용자 지정 컨트롤 인스턴스에 만들어지고 실행이 시작 됩니다.  
  
#### <a name="to-debug-your-custom-control-at-design-time"></a>디자인 타임에 사용자 지정 컨트롤을 디버깅 하려면  
  
1.  열기를 **DebugControl** 소스 파일을 **코드 편집기** 중단점을 설정 하 고는 `Set` 의 접근자는 `DemoString` 속성.  
  
2.  F5 키를 눌러 디버깅 세션을 시작 합니다. Visual Studio의 새 인스턴스를 만들어짐을 note 합니다. 두 가지 방법으로 인스턴스를 구분할 수 있습니다.  
  
    -   디버깅 인스턴스 라는 단어가 포함 **실행** 제목 표시줄에 있는  
  
    -   디버깅 인스턴스를 **시작** 단추를 해당 **디버그** 사용 하지 않도록 설정 하는 도구 모음  
  
     중단점은 디버깅 인스턴스에서 설정 됩니다.  
  
3.  Visual Studio의 새 인스턴스를 "DebuggingExample" 솔루션을 엽니다. 선택 하 여 솔루션을 쉽게 찾을 수 있습니다 **최근에 사용한 프로젝트** 에서 합니다 **파일** 메뉴. "DebuggingExample.sln" 솔루션 파일을 최근에 사용 된 파일으로 표시 됩니다.  
  
4.  Form1을 엽니다는 **Forms 디자이너** 선택 합니다 **DebugControl** 제어 합니다.  
  
5.  `DemoString` 속성 값을 변경합니다. 변경 내용을 커밋하면, Visual Studio의 디버깅 인스턴스 포커스를 획득 하 고 실행이 중단점에서 중지 되는 note 합니다. 속성 접근자를 통해 단일 단계 수와 마찬가지로 다른 코드입니다.  
  
6.  Visual Studio의 호스트 인스턴스를 해제 하거나 클릭 하 여 마쳤으면 디버깅 세션을 종료할 수 있습니다 합니다 **디버깅 중지** 디버깅 인스턴스에서 단추입니다.  
  
## <a name="next-steps"></a>다음 단계  
 이제는 사용자 지정 컨트롤 디자인 타임에 디버그할 수 있는 Visual Studio IDE를 사용 하 여 컨트롤의 상호 작용을 확장 하기 위한 많은 기능이 있습니다.  
  
-   사용할 수는 <xref:System.ComponentModel.Component.DesignMode%2A> 의 속성을 <xref:System.ComponentModel.Component> 디자인 타임에만 실행 하는 코드를 작성 하는 클래스입니다. 자세한 내용은 <xref:System.ComponentModel.Component.DesignMode%2A>를 참조하세요.  
  
-   일부의 특성이 컨트롤의 디자이너를 사용 하 여 사용자 지정 컨트롤의 상호 작용을 조작 하는 속성에 적용할 수 있습니다. 이러한 특성을 찾을 수 있습니다는 <xref:System.ComponentModel?displayProperty=nameWithType> 네임 스페이스입니다.  
  
-   사용자 지정 컨트롤에 대 한 사용자 지정 디자이너를 작성할 수 있습니다. Visual Studio에서 노출 하는 확장 가능한 디자이너 인프라를 사용 하 여 디자인 환경을 완전히 제어할 수 있습니다. 세부 정보를 참조 하세요. [연습: Visual Studio 디자인 타임 기능을 활용 하는 컨트롤을 Forms는 Windows 만들기](creating-a-wf-control-design-time-features.md)합니다.  
  
## <a name="see-also"></a>참고자료
- [연습: Visual Studio 디자인 타임 기능을 활용 하는 Windows Forms 컨트롤 만들기](creating-a-wf-control-design-time-features.md)
- [방법: 디자인 타임 서비스에 액세스](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/ms171822(v=vs.120))
- [방법: Windows Forms에서 디자인 타임 지원 액세스](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/ms171827(v=vs.120))
