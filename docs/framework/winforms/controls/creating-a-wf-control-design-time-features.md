---
title: Visual Studio 디자인 타임 기능을 활용 하는 컨트롤 만들기
description: 디자인 타임 기능을 활용 하는 Windows Forms에서 사용자 지정 컨트롤에 대 한 사용자 지정 디자이너를 만드는 방법에 대해 알아봅니다.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Windows Forms controls, creating
- design-time functionality [Windows Forms], Windows Forms
- DocumentDesigner class [Windows Forms]
- walkthroughs [Windows Forms], controls
ms.assetid: 6f487c59-cb38-4afa-ad2e-95edacb1d626
author: jillre
ms.author: jillfra
manager: jillfra
ms.openlocfilehash: 03c04578ecb01b689f58d41a46eef5793fb1182c
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/01/2020
ms.locfileid: "85613912"
---
# <a name="walkthrough-create-a-control-that-takes-advantage-of-design-time-features"></a>연습: 디자인 타임 기능을 활용 하는 컨트롤 만들기

연결 된 사용자 지정 디자이너를 작성 하 여 사용자 지정 컨트롤에 대 한 디자인 타임 환경을 향상 시킬 수 있습니다.

이 문서에서는 사용자 지정 컨트롤에 대 한 사용자 지정 디자이너를 만드는 방법을 보여 줍니다. `MarqueeControl`이라는 형식과 연결 된 디자이너 클래스를 구현 `MarqueeControlRootDesigner` 합니다.

이 `MarqueeControl` 형식은 애니메이션 광원 및 깜박이는 텍스트를 포함 하는 극장 움직이는 텍스트와 비슷한 표시를 구현 합니다.

이 컨트롤의 디자이너는 디자인 환경과 상호 작용 하 여 사용자 지정 디자인 타임 환경을 제공 합니다. 사용자 지정 디자이너를 사용 하 여 `MarqueeControl` 애니메이션 조명 및 깜박이는 텍스트가 포함 된 사용자 지정 구현을 여러 조합으로 조합할 수 있습니다. 다른 Windows Forms 컨트롤과 마찬가지로 폼에서 어셈블된 컨트롤을 사용할 수 있습니다.

이 연습을 완료 하면 사용자 지정 컨트롤은 다음과 같이 표시 됩니다.

![텍스트 및 시작 및 중지 단추를 표시 하는 앱입니다.](./media/creating-a-wf-control-design-time-features/demo-marquee-control.gif)

전체 코드 목록은 [방법: 디자인 타임 기능을 활용 하는 Windows Forms 컨트롤 만들기](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/307hck25(v=vs.120))를 참조 하세요.

## <a name="prerequisites"></a>전제 조건

이 연습을 완료 하려면 Visual Studio가 필요 합니다.

## <a name="create-the-project"></a>프로젝트를 만듭니다.

첫 번째 단계에서는 애플리케이션 프로젝트를 만듭니다. 이 프로젝트를 사용 하 여 사용자 지정 컨트롤을 호스트 하는 응용 프로그램을 빌드합니다.

Visual Studio에서 새 Windows Forms 응용 프로그램 프로젝트를 만들고 이름을 **MarqueeControlTest**로 표시 합니다.

## <a name="create-the-control-library-project"></a>컨트롤 라이브러리 프로젝트 만들기

1. Windows Forms 컨트롤 라이브러리 프로젝트를 솔루션에 추가 합니다. 프로젝트 이름을 **MarqueeControlLibrary**로 합니다.

2. **솔루션 탐색기**를 사용 하 여 선택한 언어에 따라 이름이 "UserControl1.cs" 또는 "UserControl1" 인 원본 파일을 삭제 하 여 프로젝트의 기본 컨트롤을 삭제 합니다.

3. <xref:System.Windows.Forms.UserControl>프로젝트에 새 항목을 추가 `MarqueeControlLibrary` 합니다. 새 소스 파일에 **MarqueeControl**의 기본 이름을 지정 합니다.

4. **솔루션 탐색기**를 사용 하 여 프로젝트에 새 폴더를 만듭니다 `MarqueeControlLibrary` .

5. **디자인** 폴더를 마우스 오른쪽 단추로 클릭 하 고 새 클래스를 추가 합니다. 이름을 **MarqueeControlRootDesigner**로 합니다.

6. 이 참조를 프로젝트에 추가 하려면 System.web 어셈블리의 형식을 사용 해야 합니다. `MarqueeControlLibrary`

## <a name="reference-the-custom-control-project"></a>사용자 지정 컨트롤 프로젝트 참조

프로젝트를 사용 하 여 `MarqueeControlTest` 사용자 지정 컨트롤을 테스트 합니다. 프로젝트에 프로젝트 참조를 추가할 때 테스트 프로젝트가 사용자 지정 컨트롤을 인식 합니다 `MarqueeControlLibrary` .

프로젝트에서 `MarqueeControlTest` 어셈블리에 대 한 프로젝트 참조를 추가 `MarqueeControlLibrary` 합니다. 어셈블리를 직접 참조 하는 대신 **참조 추가** 대화 상자의 **프로젝트** 탭을 사용 해야 `MarqueeControlLibrary` 합니다.

## <a name="define-a-custom-control-and-its-custom-designer"></a>사용자 지정 컨트롤 및 사용자 지정 디자이너 정의

사용자 지정 컨트롤은 클래스에서 파생 됩니다 <xref:System.Windows.Forms.UserControl> . 이를 통해 컨트롤에 다른 컨트롤을 포함 하 고 컨트롤에 많은 기본 기능을 제공 합니다.

사용자 지정 컨트롤에는 연결 된 사용자 지정 디자이너가 포함 됩니다. 이렇게 하면 사용자 지정 컨트롤에 맞게 특별히 조정 된 고유한 디자인 환경을 만들 수 있습니다.

클래스를 사용 하 여 컨트롤을 해당 디자이너와 연결 합니다 <xref:System.ComponentModel.DesignerAttribute> . 사용자 지정 컨트롤의 전체 디자인 타임 동작을 개발 하는 중 이므로 사용자 지정 디자이너는 인터페이스를 구현 합니다 <xref:System.ComponentModel.Design.IRootDesigner> .

### <a name="to-define-a-custom-control-and-its-custom-designer"></a>사용자 지정 컨트롤 및 사용자 지정 디자이너를 정의 하려면

1. `MarqueeControl` **코드 편집기**에서 소스 파일을 엽니다. 파일의 맨 위에 다음 네임 스페이스를 가져옵니다.

     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#220](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueecontrol.cs#220)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#220](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueecontrol.vb#220)]

2. <xref:System.ComponentModel.DesignerAttribute>클래스 선언에를 추가 합니다 `MarqueeControl` . 이렇게 하면 사용자 지정 컨트롤이 해당 디자이너에 연결 됩니다.

     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#240](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueecontrol.cs#240)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#240](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueecontrol.vb#240)]

3. `MarqueeControlRootDesigner` **코드 편집기**에서 소스 파일을 엽니다. 파일의 맨 위에 다음 네임 스페이스를 가져옵니다.

     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#520](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueecontrolrootdesigner.cs#520)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#520](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueecontrolrootdesigner.vb#520)]

4. `MarqueeControlRootDesigner`클래스에서 상속 하도록의 선언을 변경 합니다 <xref:System.Windows.Forms.Design.DocumentDesigner> . <xref:System.ComponentModel.ToolboxItemFilterAttribute> **도구 상자**를 사용 하 여 디자이너 상호 작용을 지정 하려면를 적용 합니다.

   > [!NOTE]
   > 클래스에 대 한 정의가 `MarqueeControlRootDesigner` MarqueeControlLibrary 라는 네임 스페이스에 포함 되었습니다. 이 선언은 디자인 관련 형식에 대해 예약 된 특수 네임 스페이스에 디자이너를 배치 합니다.

     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#530](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueecontrolrootdesigner.cs#530)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#530](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueecontrolrootdesigner.vb#530)]

5. 클래스에 대 한 생성자를 정의 `MarqueeControlRootDesigner` 합니다. <xref:System.Diagnostics.Trace.WriteLine%2A>생성자 본문에 문을 삽입 합니다. 이는 디버깅에 유용 합니다.

     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#540](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueecontrolrootdesigner.cs#540)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#540](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueecontrolrootdesigner.vb#540)]

## <a name="create-an-instance-of-your-custom-control"></a>사용자 지정 컨트롤의 인스턴스 만들기

1. <xref:System.Windows.Forms.UserControl>프로젝트에 새 항목을 추가 `MarqueeControlTest` 합니다. 새 소스 파일에 **DemoMarqueeControl**의 기본 이름을 지정 합니다.

2. `DemoMarqueeControl` **코드 편집기**에서 파일을 엽니다. 파일 맨 위에서 `MarqueeControlLibrary` 네임 스페이스를 가져옵니다.

   ```vb
   Imports MarqueeControlLibrary
   ```

   ```csharp
   using MarqueeControlLibrary;
   ```

3. `DemoMarqueeControl`클래스에서 상속 하도록의 선언을 변경 합니다 `MarqueeControl` .

4. 프로젝트를 빌드합니다.

5. Windows Forms 디자이너에서 Form1을 엽니다.

6. **도구 상자** 에서 **MarqueeControlTest 구성 요소** 탭을 찾아 엽니다. 를 `DemoMarqueeControl` **도구 상자** 에서 폼으로 끌어옵니다.

7. 프로젝트를 빌드합니다.

## <a name="set-up-the-project-for-design-time-debugging"></a>디자인 타임 디버깅을 위한 프로젝트 설정

사용자 지정 디자인 타임 환경을 개발 하는 경우에는 컨트롤과 구성 요소를 디버깅 해야 합니다. 디자인 타임에 디버깅을 허용 하도록 프로젝트를 설정 하는 간단한 방법이 있습니다. 자세한 내용은 [연습: 디자인 타임에 사용자 지정 Windows Forms 컨트롤 디버그](walkthrough-debugging-custom-windows-forms-controls-at-design-time.md)를 참조 하세요.

1. 프로젝트를 마우스 오른쪽 단추로 클릭 `MarqueeControlLibrary` 하 고 **속성**을 선택 합니다.

2. **MarqueeControlLibrary 속성 페이지** 대화 상자에서 **디버그** 페이지를 선택 합니다.

3. **시작 작업** 섹션에서 **시작 외부 프로그램**을 선택 합니다. Visual studio의 개별 인스턴스를 디버깅 하 게 되므로 visual studio IDE를 찾아보려면 줄임표 ( ![ Visual studio 속성 창의 줄임표 단추 (...)) 단추를 클릭 합니다 ](./media/visual-studio-ellipsis-button.png) . 실행 파일의 이름은 devenv.exe 이며,를 기본 위치에 설치한 경우 해당 경로는 *% ProgramFiles (x86)% \ Microsoft Visual Studio\2019 \\ \<edition>\Common7\IDE\devenv.exe*입니다.

4. **확인**을 선택하여 대화 상자를 닫습니다.

5. MarqueeControlLibrary 프로젝트를 마우스 오른쪽 단추로 클릭 하 고 **시작 프로젝트로 설정** 을 선택 하 여이 디버깅 구성을 사용 하도록 설정 합니다.

## <a name="checkpoint"></a>검사점

이제 사용자 지정 컨트롤의 디자인 타임 동작을 디버그할 준비가 되었습니다. 디버깅 환경이 올바르게 설정 된 것으로 확인 되 면 사용자 지정 컨트롤과 사용자 지정 디자이너 간의 연결을 테스트 합니다.

### <a name="to-test-the-debugging-environment-and-the-designer-association"></a>디버깅 환경 및 디자이너 연결을 테스트 하려면

1. **코드 편집기** 에서 MarqueeControlRootDesigner 소스 파일을 열고 문에 중단점을 설정 <xref:System.Diagnostics.Trace.WriteLine%2A> 합니다.

2. **F5** 키를 눌러 디버깅 세션을 시작 합니다.

   Visual Studio의 새 인스턴스가 만들어집니다.

3. Visual Studio의 새 인스턴스에서 MarqueeControlTest 솔루션을 엽니다. **파일** 메뉴에서 **최근 프로젝트** 를 선택 하 여 솔루션을 쉽게 찾을 수 있습니다. MarqueeControlTest 솔루션 파일이 가장 최근에 사용 된 파일로 나열 됩니다.

4. `DemoMarqueeControl`디자이너에서를 엽니다.

   Visual Studio의 디버깅 인스턴스는 중단점에서 포커스를 가져오고 실행을 중지 합니다. **F5** 키를 눌러 디버깅 세션을 계속 합니다.

이 시점에서 모든 항목은 사용자 지정 컨트롤 및 이와 관련 된 사용자 지정 디자이너를 개발 하 고 디버그할 수 있도록 준비 되어 있습니다. 이 문서의 나머지 부분에서는 컨트롤 및 디자이너의 기능 구현에 대 한 세부 정보를 집중적으로 설명 합니다.

## <a name="implement-the-custom-control"></a>사용자 지정 컨트롤 구현

는 `MarqueeControl` <xref:System.Windows.Forms.UserControl> 약간의 사용자 지정을 포함 하는입니다. 이는 `Start` 움직이는 텍스트 애니메이션을 시작 하는와 애니메이션을 중지 하는 라는 두 개의 메서드를 노출 합니다. `Stop` 는 `MarqueeControl` 인터페이스를 구현 하는 자식 컨트롤을 포함 하므로를 `IMarqueeWidget` `Start` `Stop` `StartMarquee` `StopMarquee` 구현 하는 각 자식 컨트롤에서 각 자식 컨트롤을 열거 하 고 및 메서드를 각각 호출 `IMarqueeWidget` 합니다.

및 컨트롤의 모양은 `MarqueeBorder` `MarqueeText` 레이아웃에 따라 달라 지므로 메서드를 재정의 하 `MarqueeControl` <xref:System.Windows.Forms.Control.OnLayout%2A> 고 <xref:System.Windows.Forms.Control.PerformLayout%2A> 이 형식의 자식 컨트롤에 대해를 호출 합니다.

사용자 지정의 범위입니다 `MarqueeControl` . 런타임 기능은 및 컨트롤에서 구현 되며 `MarqueeBorder` `MarqueeText` 디자인 타임 기능은 및 클래스에 의해 구현 됩니다 `MarqueeBorderDesigner` `MarqueeControlRootDesigner` .

### <a name="to-implement-your-custom-control"></a>사용자 지정 컨트롤을 구현 하려면

1. `MarqueeControl` **코드 편집기**에서 소스 파일을 엽니다. `Start`및 메서드를 구현 `Stop` 합니다.

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#260](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueecontrol.cs#260)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#260](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueecontrol.vb#260)]

2. <xref:System.Windows.Forms.Control.OnLayout%2A> 메서드를 재정의합니다.

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#270](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueecontrol.cs#270)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#270](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueecontrol.vb#270)]

## <a name="create-a-child-control-for-your-custom-control"></a>사용자 지정 컨트롤에 대 한 자식 컨트롤을 만듭니다.

는 `MarqueeControl` 컨트롤 및 컨트롤과 같은 두 가지 종류의 자식 컨트롤을 호스팅합니다 `MarqueeBorder` `MarqueeText` .

- `MarqueeBorder`:이 컨트롤은 가장자리 주위에 "광원" 테두리를 그립니다. 광원은 순서 대로 깜박이 므로 테두리를 중심으로 이동 하는 것 처럼 보입니다. 광원의 속도는 라는 속성에 의해 제어 됩니다 `UpdatePeriod` . 다른 여러 사용자 지정 속성은 컨트롤의 모양에 대 한 다른 측면을 결정 합니다. 및 라는 두 메서드 `StartMarquee` `StopMarquee` 는 애니메이션이 시작 되 고 중지 되는 시기를 제어 합니다.

- `MarqueeText`:이 컨트롤은 깜박이는 문자열을 그립니다. 컨트롤과 마찬가지로 `MarqueeBorder` 텍스트가 깜박이는 속도는 속성에 의해 제어 됩니다 `UpdatePeriod` . 컨트롤에는 컨트롤과 `MarqueeText` `StartMarquee` 공통적인 및 `StopMarquee` 메서드도 있습니다 `MarqueeBorder` .

디자인 타임에를 `MarqueeControlRootDesigner` 사용 하면 이러한 두 컨트롤 형식을 모든 조합으로에 추가할 수 있습니다 `MarqueeControl` .

두 컨트롤의 공통 기능은 이라는 인터페이스로 팩터링 됩니다 `IMarqueeWidget` . 이렇게 하면에서 `MarqueeControl` 움직이는 텍스트와 관련 된 자식 컨트롤을 검색 하 고 특수 한 처리를 제공할 수 있습니다.

정기 애니메이션 기능을 구현 하려면 <xref:System.ComponentModel.BackgroundWorker> 네임 스페이스의 개체를 사용 합니다 <xref:System.ComponentModel?displayProperty=nameWithType> . <xref:System.Windows.Forms.Timer>개체를 사용할 수 있지만 많은 개체가 있을 경우 `IMarqueeWidget` 단일 UI 스레드가 애니메이션을 유지 하지 못할 수 있습니다.

### <a name="to-create-a-child-control-for-your-custom-control"></a>사용자 지정 컨트롤에 대 한 자식 컨트롤을 만들려면

1. 프로젝트에 새 클래스 항목을 추가 `MarqueeControlLibrary` 합니다. 새 소스 파일에 "IMarqueeWidget"의 기본 이름을 지정 합니다.

2. `IMarqueeWidget` **코드 편집기** 에서 소스 파일을 열고 선언을에서로 변경 합니다 `class` `interface` .

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#2](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/imarqueewidget.cs#2)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#2](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/imarqueewidget.vb#2)]

3. 다음 코드를 인터페이스에 추가 `IMarqueeWidget` 하 여 두 개의 메서드와 marquee 애니메이션을 조작 하는 속성을 노출 합니다.

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#3](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/imarqueewidget.cs#3)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#3](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/imarqueewidget.vb#3)]

4. 프로젝트에 새 **사용자 지정 컨트롤** 항목을 추가 `MarqueeControlLibrary` 합니다. 새 소스 파일에 "MarqueeText"의 기본 이름을 지정 합니다.

5. <xref:System.ComponentModel.BackgroundWorker>구성 요소를 **도구 상자** 에서 컨트롤로 끌어 옵니다 `MarqueeText` . 이 구성 요소는 `MarqueeText` 컨트롤을 비동기적으로 업데이트 하는 것을 허용 합니다.

6. **속성** 창에서 <xref:System.ComponentModel.BackgroundWorker> 구성 요소의 `WorkerReportsProgress` 및 <xref:System.ComponentModel.BackgroundWorker.WorkerSupportsCancellation%2A> 속성을 **true**로 설정 합니다. 이러한 설정을 통해 <xref:System.ComponentModel.BackgroundWorker> 구성 요소가 정기적으로 이벤트를 발생 시키고 <xref:System.ComponentModel.BackgroundWorker.ProgressChanged> 비동기 업데이트를 취소할 수 있습니다.

   자세한 내용은 [BackgroundWorker 구성 요소](backgroundworker-component.md)를 참조 하세요.

7. `MarqueeText` **코드 편집기**에서 소스 파일을 엽니다. 파일의 맨 위에 다음 네임 스페이스를 가져옵니다.

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#120](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueetext.cs#120)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#120](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueetext.vb#120)]

8. 인터페이스를 구현 하기 위해 `MarqueeText` 및에서 상속 하도록의 선언을 변경 합니다 <xref:System.Windows.Forms.Label> `IMarqueeWidget` .

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#130](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueetext.cs#130)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#130](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueetext.vb#130)]

9. 노출 된 속성에 해당 하는 인스턴스 변수를 선언 하 고 생성자에서 초기화 합니다. `isLit`필드는 속성에 지정 된 색으로 텍스트를 그릴지 여부를 결정 `LightColor` 합니다.

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#140](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueetext.cs#140)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#140](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueetext.vb#140)]

10. `IMarqueeWidget` 인터페이스를 구현합니다.

    `StartMarquee`및 `StopMarquee` 메서드는 <xref:System.ComponentModel.BackgroundWorker> 구성 요소의 <xref:System.ComponentModel.BackgroundWorker.RunWorkerAsync%2A> 및 메서드를 호출 하 여 애니메이션을 <xref:System.ComponentModel.BackgroundWorker.CancelAsync%2A> 시작 및 중지 합니다.

    <xref:System.ComponentModel.CategoryAttribute.Category%2A>및 <xref:System.ComponentModel.BrowsableAttribute.Browsable%2A> 특성은 속성에 적용 `UpdatePeriod` 되므로 "움직이는 텍스트" 라는 속성 창의 사용자 지정 섹션에 표시 됩니다.

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#150](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueetext.cs#150)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#150](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueetext.vb#150)]

11. 속성 접근자를 구현 합니다. 클라이언트에 및 라는 두 가지 속성을 `LightColor` 노출 `DarkColor` 합니다. <xref:System.ComponentModel.CategoryAttribute.Category%2A>및 <xref:System.ComponentModel.BrowsableAttribute.Browsable%2A> 특성은 이러한 속성에 적용 되므로 "움직이는 텍스트" 라는 속성 창의 사용자 지정 섹션에 속성이 표시 됩니다.

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#160](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueetext.cs#160)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#160](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueetext.vb#160)]

12. 구성 요소의 및 이벤트에 대 한 처리기를 구현 <xref:System.ComponentModel.BackgroundWorker> <xref:System.ComponentModel.BackgroundWorker.DoWork> <xref:System.ComponentModel.BackgroundWorker.ProgressChanged> 합니다.

    <xref:System.ComponentModel.BackgroundWorker.DoWork>가를 `UpdatePeriod` <xref:System.ComponentModel.BackgroundWorker.ProgressChanged> 호출 하 여 코드에서 애니메이션을 중지할 때까지 이벤트 처리기는에서 지정 된 시간 (밀리초) 동안 대기 하 고 이벤트를 발생 시킵니다 <xref:System.ComponentModel.BackgroundWorker.CancelAsync%2A> .

    <xref:System.ComponentModel.BackgroundWorker.ProgressChanged>이벤트 처리기는 밝은 상태와 어두운 상태 사이에서 텍스트를 전환 하 여 깜빡이는 모양을 제공 합니다.

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#180](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueetext.cs#180)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#180](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueetext.vb#180)]

13. 애니메이션을 <xref:System.Windows.Forms.Control.OnPaint%2A> 사용 하도록 설정 하려면 메서드를 재정의 합니다.

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#170](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueetext.cs#170)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#170](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueetext.vb#170)]

14. **F6** 키를 눌러 솔루션을 빌드합니다.

## <a name="create-the-marqueeborder-child-control"></a>MarqueeBorder 자식 컨트롤 만들기

컨트롤은 `MarqueeBorder` 컨트롤 보다 약간 더 정교 합니다 `MarqueeText` . 이 클래스에는 더 많은 속성이 있으며 메서드의 애니메이션은 <xref:System.Windows.Forms.Control.OnPaint%2A> 더 복잡 합니다. 원칙적으로는 컨트롤과 매우 유사 `MarqueeText` 합니다.

컨트롤은 `MarqueeBorder` 자식 컨트롤을 가질 수 있으므로 이벤트를 인식 해야 <xref:System.Windows.Forms.Control.Layout> 합니다.

### <a name="to-create-the-marqueeborder-control"></a>MarqueeBorder 컨트롤을 만들려면

1. 프로젝트에 새 **사용자 지정 컨트롤** 항목을 추가 `MarqueeControlLibrary` 합니다. 새 소스 파일에 "MarqueeBorder"의 기본 이름을 지정 합니다.

2. <xref:System.ComponentModel.BackgroundWorker>구성 요소를 **도구 상자** 에서 컨트롤로 끌어 옵니다 `MarqueeBorder` . 이 구성 요소는 `MarqueeBorder` 컨트롤을 비동기적으로 업데이트 하는 것을 허용 합니다.

3. **속성** 창에서 <xref:System.ComponentModel.BackgroundWorker> 구성 요소의 `WorkerReportsProgress` 및 <xref:System.ComponentModel.BackgroundWorker.WorkerSupportsCancellation%2A> 속성을 **true**로 설정 합니다. 이러한 설정을 통해 <xref:System.ComponentModel.BackgroundWorker> 구성 요소가 정기적으로 이벤트를 발생 시키고 <xref:System.ComponentModel.BackgroundWorker.ProgressChanged> 비동기 업데이트를 취소할 수 있습니다. 자세한 내용은 [BackgroundWorker 구성 요소](backgroundworker-component.md)를 참조 하세요.

4. **속성** 창에서 **이벤트** 단추를 선택 합니다. 및 이벤트에 대 한 처리기를 연결 <xref:System.ComponentModel.BackgroundWorker.DoWork> <xref:System.ComponentModel.BackgroundWorker.ProgressChanged> 합니다.

5. `MarqueeBorder` **코드 편집기**에서 소스 파일을 엽니다. 파일의 맨 위에 다음 네임 스페이스를 가져옵니다.

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#20](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueeborder.cs#20)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#20](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueeborder.vb#20)]

6. 를 `MarqueeBorder` 상속 하 고 인터페이스를 구현 하려면의 선언을 변경 합니다 <xref:System.Windows.Forms.Panel> `IMarqueeWidget` .

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#30](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueeborder.cs#30)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#30](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueeborder.vb#30)]

7. 컨트롤의 상태를 관리 하는 두 개의 열거형을 선언 합니다 `MarqueeBorder` . `MarqueeSpinDirection` 즉, 조명이 테두리 주위에 "회전" 하는 방향을 결정 하 고는 `MarqueeLightShape` 광원의 모양 (사각형 또는 원형)을 결정 합니다. 이러한 선언을 클래스 선언 앞에 추가 `MarqueeBorder` 합니다.

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#97](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueeborder.cs#97)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#97](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueeborder.vb#97)]

8. 노출 된 속성에 해당 하는 인스턴스 변수를 선언 하 고 생성자에서 초기화 합니다.

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#40](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueeborder.cs#40)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#40](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueeborder.vb#40)]

9. `IMarqueeWidget` 인터페이스를 구현합니다.

    `StartMarquee`및 `StopMarquee` 메서드는 <xref:System.ComponentModel.BackgroundWorker> 구성 요소의 <xref:System.ComponentModel.BackgroundWorker.RunWorkerAsync%2A> 및 메서드를 호출 하 여 애니메이션을 <xref:System.ComponentModel.BackgroundWorker.CancelAsync%2A> 시작 및 중지 합니다.

    컨트롤은 `MarqueeBorder` 자식 컨트롤을 포함할 수 있기 때문에 `StartMarquee` 메서드는 모든 자식 컨트롤을 열거 하 고를 `StartMarquee` 구현 하는 컨트롤에 대해를 호출 합니다 `IMarqueeWidget` . `StopMarquee`메서드에는 비슷한 구현이 있습니다.

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#50](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueeborder.cs#50)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#50](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueeborder.vb#50)]

10. 속성 접근자를 구현 합니다. 컨트롤에는 `MarqueeBorder` 모양을 제어 하는 여러 속성이 있습니다.

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#60](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueeborder.cs#60)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#60](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueeborder.vb#60)]

11. 구성 요소의 및 이벤트에 대 한 처리기를 구현 <xref:System.ComponentModel.BackgroundWorker> <xref:System.ComponentModel.BackgroundWorker.DoWork> <xref:System.ComponentModel.BackgroundWorker.ProgressChanged> 합니다.

    <xref:System.ComponentModel.BackgroundWorker.DoWork>가를 `UpdatePeriod` <xref:System.ComponentModel.BackgroundWorker.ProgressChanged> 호출 하 여 코드에서 애니메이션을 중지할 때까지 이벤트 처리기는에서 지정 된 시간 (밀리초) 동안 대기 하 고 이벤트를 발생 시킵니다 <xref:System.ComponentModel.BackgroundWorker.CancelAsync%2A> .

    <xref:System.ComponentModel.BackgroundWorker.ProgressChanged>이벤트 처리기는 다른 조명의 밝은/어둡게 상태를 결정 하는 "기본" 조명의 위치를 증가 시키고 메서드를 호출 하 여 컨트롤이 자신을 다시 <xref:System.Windows.Forms.Control.Refresh%2A> 그립니다.

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#90](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueeborder.cs#90)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#90](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueeborder.vb#90)]

12. 도우미 메서드인 및를 구현 `IsLit` `DrawLight` 합니다.

    `IsLit`메서드는 지정 된 위치의 광원 색을 결정 합니다. "Lit" 인 광원은 속성에 지정 된 색으로 그려지고 `LightColor` , "짙은" 광원은 속성에 지정 된 색으로 그려집니다 `DarkColor` .

    `DrawLight`메서드는 적절 한 색, 모양 및 위치를 사용 하 여 조명을 그립니다.

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#80](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueeborder.cs#80)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#80](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueeborder.vb#80)]

13. <xref:System.Windows.Forms.Control.OnLayout%2A> 및 <xref:System.Windows.Forms.Control.OnPaint%2A> 메서드를 재정의합니다.

    <xref:System.Windows.Forms.Control.OnPaint%2A>메서드는 컨트롤의 가장자리를 따라 조명을 그립니다 `MarqueeBorder` .

    메서드는 <xref:System.Windows.Forms.Control.OnPaint%2A> 컨트롤의 크기에 따라 달라 지므로 `MarqueeBorder` 레이아웃이 변경 될 때마다이 메서드를 호출 해야 합니다. 이를 위해서는를 재정의 하 <xref:System.Windows.Forms.Control.OnLayout%2A> 고를 호출 <xref:System.Windows.Forms.Control.Refresh%2A> 합니다.

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#70](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueeborder.cs#70)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#70](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueeborder.vb#70)]

## <a name="create-a-custom-designer-to-shadow-and-filter-properties"></a>사용자 지정 디자이너를 만들어 속성을 숨기 고 필터링 합니다.

`MarqueeControlRootDesigner`클래스는 루트 디자이너에 대 한 구현을 제공 합니다. 에서 작동 하는이 디자이너 외에도 `MarqueeControl` 컨트롤에 특별히 연결 된 사용자 지정 디자이너가 필요 `MarqueeBorder` 합니다. 이 디자이너는 사용자 지정 루트 디자이너의 컨텍스트에 적합 한 사용자 지정 동작을 제공 합니다.

특히은 `MarqueeBorderDesigner` `MarqueeBorder` 디자인 환경과의 상호 작용을 변경 하 여 컨트롤의 특정 속성을 "숨기" 고 필터링 합니다.

구성 요소의 속성 접근자에 대 한 호출을 가로채는 "숨김" 이라고 합니다. 이를 통해 디자이너는 사용자가 설정한 값을 추적 하 고 필요에 따라 디자인 되는 구성 요소에 해당 값을 전달할 수 있습니다.

이 예제에서 <xref:System.Windows.Forms.Control.Visible%2A> 및 속성은 <xref:System.Windows.Forms.Control.Enabled%2A> 에 의해 숨겨집니다 `MarqueeBorderDesigner` . 그러면 사용자가 `MarqueeBorder` 디자인 타임에 컨트롤을 숨기 거 나 사용 하지 않도록 설정할 수 없습니다.

디자이너는 속성을 추가 하 고 제거할 수도 있습니다. 이 예제에서는 <xref:System.Windows.Forms.Control.Padding%2A> `MarqueeBorder` 컨트롤에서 속성에 지정 된 조명의 크기에 따라 프로그래밍 방식으로 안쪽 여백을 설정 하므로 디자인 타임에 속성이 제거 됩니다 `LightSize` .

의 기본 클래스는 `MarqueeBorderDesigner` <xref:System.ComponentModel.Design.ComponentDesigner> 디자인 타임에 컨트롤에 의해 노출 되는 특성, 속성 및 이벤트를 변경할 수 있는 메서드를 포함 하는입니다.

- <xref:System.ComponentModel.Design.ComponentDesigner.PreFilterProperties%2A>

- <xref:System.ComponentModel.Design.ComponentDesigner.PostFilterProperties%2A>

- <xref:System.ComponentModel.Design.ComponentDesigner.PreFilterAttributes%2A>

- <xref:System.ComponentModel.Design.ComponentDesigner.PostFilterAttributes%2A>

- <xref:System.ComponentModel.Design.ComponentDesigner.PreFilterEvents%2A>

- <xref:System.ComponentModel.Design.ComponentDesigner.PostFilterEvents%2A>

이러한 메서드를 사용 하 여 구성 요소의 공용 인터페이스를 변경 하는 경우 다음 규칙을 따릅니다.

- 메서드에만 항목 추가 또는 제거 `PreFilter`

- 메서드의 기존 항목만 수정 `PostFilter`

- 항상 메서드에서 기본 구현을 먼저 호출 합니다. `PreFilter`

- 메서드의 마지막 기본 구현을 항상 호출 합니다. `PostFilter`

이러한 규칙을 준수 하면 디자인 타임 환경의 모든 디자이너에서 디자인 중인 모든 구성 요소를 일관 되 게 볼 수 있습니다.

<xref:System.ComponentModel.Design.ComponentDesigner>클래스는 숨겨진 속성의 값을 관리 하기 위한 사전을 제공 하므로 특정 인스턴스 변수를 만들 필요가 없습니다.

### <a name="to-create-a-custom-designer-to-shadow-and-filter-properties"></a>속성을 숨기고 필터링 하기 위한 사용자 지정 디자이너를 만들려면

1. **디자인** 폴더를 마우스 오른쪽 단추로 클릭 하 고 새 클래스를 추가 합니다. 원본 파일에 **MarqueeBorderDesigner**의 기본 이름을 지정 합니다.

2. **코드 편집기**에서 MarqueeBorderDesigner 원본 파일을 엽니다. 파일의 맨 위에 다음 네임 스페이스를 가져옵니다.

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#420](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueeborderdesigner.cs#420)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#420](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueeborderdesigner.vb#420)]

3. 의 선언을 `MarqueeBorderDesigner` 에서 상속 하도록 변경 <xref:System.Windows.Forms.Design.ParentControlDesigner> 합니다.

    컨트롤은 `MarqueeBorder` 자식 컨트롤을 포함할 수 있으므로는 `MarqueeBorderDesigner` <xref:System.Windows.Forms.Design.ParentControlDesigner> 부모-자식 상호 작용을 처리 하는에서 상속 됩니다.

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#430](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueeborderdesigner.cs#430)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#430](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueeborderdesigner.vb#430)]

4. 의 기본 구현을 재정의 <xref:System.ComponentModel.Design.ComponentDesigner.PreFilterProperties%2A> 합니다.

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#450](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueeborderdesigner.cs#450)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#450](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueeborderdesigner.vb#450)]

5. <xref:System.Windows.Forms.Control.Enabled%2A> 및 <xref:System.Windows.Forms.Control.Visible%2A> 속성을 구현합니다. 이러한 구현은 컨트롤의 속성을 숨깁니다.

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#440](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueeborderdesigner.cs#440)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#440](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueeborderdesigner.vb#440)]

## <a name="handle-component-changes"></a>구성 요소 변경 내용 처리

`MarqueeControlRootDesigner`클래스는 인스턴스에 대 한 사용자 지정 디자인 타임 환경을 제공 합니다 `MarqueeControl` . 대부분의 디자인 타임 기능은 클래스에서 상속 됩니다 <xref:System.Windows.Forms.Design.DocumentDesigner> . 코드는 구성 요소 변경 내용 처리 및 디자이너 동사 추가와 같은 두 가지 특정 사용자 지정을 구현 합니다.

사용자가 `MarqueeControl` 인스턴스를 디자인할 때 루트 디자이너는 `MarqueeControl` 및 해당 자식 컨트롤에 대 한 변경 내용을 추적 합니다. 디자인 타임 환경은 <xref:System.ComponentModel.Design.IComponentChangeService> 구성 요소 상태에 대 한 변경 내용을 추적 하는 데 편리한 서비스인를 제공 합니다.

메서드를 사용 하 여 환경을 쿼리하여이 서비스에 대 한 참조를 가져옵니다 <xref:System.ComponentModel.Design.ComponentDesigner.GetService%2A> . 쿼리가 성공 하면 디자이너는 이벤트에 대 한 처리기를 연결 <xref:System.ComponentModel.Design.IComponentChangeService.ComponentChanged> 하 고 디자인 타임에 일관 된 상태를 유지 하는 데 필요한 모든 작업을 수행할 수 있습니다.

클래스의 경우에 `MarqueeControlRootDesigner` <xref:System.Windows.Forms.Control.Refresh%2A> 포함 된 각 개체에 대해 메서드를 호출 합니다 `IMarqueeWidget` `MarqueeControl` . 이렇게 하면 `IMarqueeWidget` 해당 부모와 같은 속성이 변경 될 때 개체 자체가 적절히 다시 그려집니다 <xref:System.Windows.Forms.Control.Size%2A> .

### <a name="to-handle-component-changes"></a>구성 요소 변경을 처리 하려면

1. `MarqueeControlRootDesigner` **코드 편집기** 에서 소스 파일을 열고 메서드를 재정의 <xref:System.Windows.Forms.Design.DocumentDesigner.Initialize%2A> 합니다. 의 기본 구현을 호출 <xref:System.Windows.Forms.Design.DocumentDesigner.Initialize%2A> 하 고를 쿼리 <xref:System.ComponentModel.Design.IComponentChangeService> 합니다.

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#580](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueecontrolrootdesigner.cs#580)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#580](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueecontrolrootdesigner.vb#580)]

2. <xref:System.ComponentModel.Design.IComponentChangeService.OnComponentChanged%2A>이벤트 처리기를 구현 합니다. 전송 구성 요소의 형식을 테스트 하 고, 인 경우 `IMarqueeWidget` 해당 메서드를 호출 <xref:System.Windows.Forms.Control.Refresh%2A> 합니다.

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#560](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueecontrolrootdesigner.cs#560)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#560](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueecontrolrootdesigner.vb#560)]

## <a name="add-designer-verbs-to-your-custom-designer"></a>사용자 지정 디자이너에 디자이너 동사 추가

디자이너 동사는 이벤트 처리기에 연결된 메뉴 명령입니다. 디자인 타임에 디자이너 동사가 구성 요소의 바로 가기 메뉴에 추가 됩니다. 자세한 내용은 <xref:System.ComponentModel.Design.DesignerVerb>를 참조하세요.

디자이너에는 **테스트 실행** 및 **테스트 중지**라는 두 개의 디자이너 동사를 추가 합니다. 이러한 동사를 사용 하 여 디자인 타임에의 런타임 동작을 볼 수 있습니다 `MarqueeControl` . 이러한 동사는에 추가 됩니다 `MarqueeControlRootDesigner` .

**테스트 실행** 이 호출 되 면 동사 이벤트 처리기가에서 메서드를 호출 합니다 `StartMarquee` `MarqueeControl` . **테스트 중지** 가 호출 되 면 동사 이벤트 처리기가에서 메서드를 호출 합니다 `StopMarquee` `MarqueeControl` . `StartMarquee`및 `StopMarquee` 메서드는를 구현 하는 포함 된 컨트롤에서 이러한 메서드를 호출 하 여 `IMarqueeWidget` 포함 된 `IMarqueeWidget` 컨트롤도 테스트에 참여 하 게 됩니다.

### <a name="to-add-designer-verbs-to-your-custom-designers"></a>사용자 지정 디자이너에 디자이너 동사를 추가 하려면

1. 클래스에서 `MarqueeControlRootDesigner` 및 라는 이벤트 처리기를 추가 `OnVerbRunTest` `OnVerbStopTest` 합니다.

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#570](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueecontrolrootdesigner.cs#570)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#570](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueecontrolrootdesigner.vb#570)]

2. 이러한 이벤트 처리기를 해당 디자이너 동사에 연결 합니다. `MarqueeControlRootDesigner`<xref:System.ComponentModel.Design.DesignerVerbCollection>기본 클래스에서를 상속 합니다. 새 개체 두 개를 만들고 <xref:System.ComponentModel.Design.DesignerVerb> 메서드에서이 컬렉션에 추가 합니다 <xref:System.Windows.Forms.Design.DocumentDesigner.Initialize%2A> .

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#590](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueecontrolrootdesigner.cs#590)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#590](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueecontrolrootdesigner.vb#590)]

## <a name="create-a-custom-uitypeeditor"></a>사용자 지정 UITypeEditor 만들기

사용자에 대 한 사용자 지정 디자인 타임 환경을 만들 때 속성 창와 사용자 지정 상호 작용을 만드는 것이 좋습니다. 를 만들어이를 수행할 수 있습니다 <xref:System.Drawing.Design.UITypeEditor> .

`MarqueeBorder`컨트롤은 속성 창의 여러 속성을 노출 합니다. 이러한 속성 중 두 개 `MarqueeSpinDirection` `MarqueeLightShape` 는 열거형으로 표현 됩니다. UI 형식 편집기를 사용 하는 방법을 보여 주기 위해 `MarqueeLightShape` 속성에는 연결 된 <xref:System.Drawing.Design.UITypeEditor> 클래스가 포함 됩니다.

### <a name="to-create-a-custom-ui-type-editor"></a>사용자 지정 UI 형식 편집기를 만들려면

1. `MarqueeBorder` **코드 편집기**에서 소스 파일을 엽니다.

2. 클래스의 정의에서 `MarqueeBorder` `LightShapeEditor` 에서 파생 되는 이라는 클래스를 선언 합니다 <xref:System.Drawing.Design.UITypeEditor> .

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#96](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueeborder.cs#96)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#96](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueeborder.vb#96)]

3. <xref:System.Windows.Forms.Design.IWindowsFormsEditorService>라는 인스턴스 변수를 선언 `editorService` 합니다.

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#92](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueeborder.cs#92)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#92](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueeborder.vb#92)]

4. <xref:System.Drawing.Design.UITypeEditor.GetEditStyle%2A> 메서드를 재정의합니다. 이 구현에서는 <xref:System.Drawing.Design.UITypeEditorEditStyle.DropDown> 을 표시 하는 방법을 디자인 환경에 알려 주는를 반환 합니다 `LightShapeEditor` .

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#93](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueeborder.cs#93)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#93](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueeborder.vb#93)]

5. <xref:System.Drawing.Design.UITypeEditor.EditValue%2A> 메서드를 재정의합니다. 이 구현은 디자인 환경에서 개체를 쿼리 <xref:System.Windows.Forms.Design.IWindowsFormsEditorService> 합니다. 성공 하면이 생성 `LightShapeSelectionControl` 됩니다. <xref:System.Windows.Forms.Design.IWindowsFormsEditorService.DropDownControl%2A>메서드를 호출 하 여를 시작 `LightShapeEditor` 합니다. 이 호출의 반환 값은 디자인 환경으로 반환 됩니다.

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#94](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueeborder.cs#94)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#94](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueeborder.vb#94)]

## <a name="create-a-view-control-for-your-custom-uitypeeditor"></a>사용자 지정 UITypeEditor에 대 한 뷰 컨트롤 만들기

`MarqueeLightShape`속성은 두 가지 유형의 조명 모양 `Square` 및를 지원 `Circle` 합니다. 속성 창에서 이러한 값을 그래픽으로 표시 하는 용도로만 사용 되는 사용자 지정 컨트롤을 만듭니다. 에서이 사용자 지정 컨트롤을 사용 <xref:System.Drawing.Design.UITypeEditor> 하 여 속성 창와 상호 작용할 수 있습니다.

### <a name="to-create-a-view-control-for-your-custom-ui-type-editor"></a>사용자 지정 UI 형식 편집기에 대 한 뷰 컨트롤을 만들려면

1. <xref:System.Windows.Forms.UserControl>프로젝트에 새 항목을 추가 `MarqueeControlLibrary` 합니다. 새 소스 파일에 **LightShapeSelectionControl**의 기본 이름을 지정 합니다.

2. <xref:System.Windows.Forms.Panel> **도구 상자** 에서 두 컨트롤을로 끌어 옵니다 `LightShapeSelectionControl` . 및로 이름을로 `squarePanel` `circlePanel` 합니다. 나란히 정렬 합니다. <xref:System.Windows.Forms.Control.Size%2A>두 컨트롤의 속성을 <xref:System.Windows.Forms.Panel> **(60, 60)** 로 설정 합니다. <xref:System.Windows.Forms.Control.Location%2A>컨트롤의 속성을 `squarePanel` **(8, 10)** 로 설정 합니다. <xref:System.Windows.Forms.Control.Location%2A>컨트롤의 속성을 `circlePanel` **(80, 10)** 로 설정 합니다. 마지막으로 <xref:System.Windows.Forms.Control.Size%2A> 의 속성을 `LightShapeSelectionControl` **(150, 80)** 로 설정 합니다.

3. `LightShapeSelectionControl` **코드 편집기**에서 소스 파일을 엽니다. 파일 맨 위에서 <xref:System.Windows.Forms.Design?displayProperty=nameWithType> 네임 스페이스를 가져옵니다.

   ```vb
   Imports System.Windows.Forms.Design
   ```

   ```csharp
   using System.Windows.Forms.Design;
   ```

4. <xref:System.Windows.Forms.Control.Click>및 컨트롤에 대 한 이벤트 처리기를 구현 `squarePanel` `circlePanel` 합니다. 이러한 메서드 <xref:System.Windows.Forms.Design.IWindowsFormsEditorService.CloseDropDown%2A> 는를 호출 하 여 사용자 지정 <xref:System.Drawing.Design.UITypeEditor> 편집 세션을 종료 합니다.

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#390](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/lightshapeselectioncontrol.cs#390)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#390](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/lightshapeselectioncontrol.vb#390)]

5. <xref:System.Windows.Forms.Design.IWindowsFormsEditorService>라는 인스턴스 변수를 선언 `editorService` 합니다.

   ```vb
   Private editorService As IWindowsFormsEditorService
   ```

   ```csharp
   private IWindowsFormsEditorService editorService;
   ```

6. `MarqueeLightShape`라는 인스턴스 변수를 선언 `lightShapeValue` 합니다.

     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#330](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/lightshapeselectioncontrol.cs#330)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#330](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/lightshapeselectioncontrol.vb#330)]

7. 생성자에서 `LightShapeSelectionControl` <xref:System.Windows.Forms.Control.Click> 이벤트 처리기를 `squarePanel` 및 컨트롤의 이벤트에 연결 `circlePanel` <xref:System.Windows.Forms.Control.Click> 합니다. 또한 `MarqueeLightShape` 디자인 환경에서 필드에 값을 할당 하는 생성자 오버 로드를 정의 합니다 `lightShapeValue` .

     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#340](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/lightshapeselectioncontrol.cs#340)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#340](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/lightshapeselectioncontrol.vb#340)]

8. <xref:System.ComponentModel.Component.Dispose%2A>메서드에서 <xref:System.Windows.Forms.Control.Click> 이벤트 처리기를 분리 합니다.

     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#350](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/lightshapeselectioncontrol.cs#350)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#350](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/lightshapeselectioncontrol.vb#350)]

9. **솔루션 탐색기**에서 **모든 파일 표시** 단추를 클릭합니다. LightShapeSelectionControl.Designer.cs 또는 LightShapeSelectionControl 파일을 열고 메서드의 기본 정의를 제거 합니다. <xref:System.ComponentModel.Component.Dispose%2A>

10. `LightShape` 속성을 구현합니다.

     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#360](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/lightshapeselectioncontrol.cs#360)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#360](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/lightshapeselectioncontrol.vb#360)]

11. <xref:System.Windows.Forms.Control.OnPaint%2A> 메서드를 재정의합니다. 이 구현에서는 채워진 사각형 및 원을 그립니다. 또한 한 도형 둘레에 테두리를 그리면 선택한 값이 강조 표시 됩니다.

     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#380](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/lightshapeselectioncontrol.cs#380)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#380](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/lightshapeselectioncontrol.vb#380)]

## <a name="test-your-custom-control-in-the-designer"></a>디자이너에서 사용자 지정 컨트롤 테스트

이제 프로젝트를 빌드할 수 있습니다 `MarqueeControlLibrary` . 클래스에서 상속 하 `MarqueeControl` 고 폼에서 사용 하는 컨트롤을 만들어 구현을 테스트 합니다.

### <a name="to-create-a-custom-marqueecontrol-implementation"></a>사용자 지정 MarqueeControl 구현을 만들려면

1. Windows Forms 디자이너에서 `DemoMarqueeControl`을 엽니다. 그러면 형식의 인스턴스가 만들어지고 `DemoMarqueeControl` 형식의 인스턴스에 표시 됩니다 `MarqueeControlRootDesigner` .

2. **도구 상자**에서 **MarqueeControlLibrary 구성 요소** 탭을 엽니다. `MarqueeBorder`및 `MarqueeText` 컨트롤을 선택할 수 있는 것을 볼 수 있습니다.

3. 컨트롤의 인스턴스를 디자인 화면으로 끌어 옵니다 `MarqueeBorder` `DemoMarqueeControl` . 이 `MarqueeBorder` 컨트롤을 부모 컨트롤에 도킹 합니다.

4. 컨트롤의 인스턴스를 디자인 화면으로 끌어 옵니다 `MarqueeText` `DemoMarqueeControl` .

5. 솔루션을 빌드합니다.

6. 를 마우스 오른쪽 단추로 클릭 하 `DemoMarqueeControl` 고 바로 가기 메뉴에서 **테스트 실행** 옵션을 선택 하 여 애니메이션을 시작 합니다. **테스트 중지** 를 클릭 하 여 애니메이션을 중지 합니다.

7. 디자인 뷰에서 **Form1**을 엽니다.

8. 폼에 컨트롤 두 개를 추가 <xref:System.Windows.Forms.Button> 합니다. 및의 이름을로 `startButton` `stopButton` 변경 하 고 <xref:System.Windows.Forms.Control.Text%2A> 속성 값을 **시작** 및 **중지**로 각각 변경 합니다.

9. <xref:System.Windows.Forms.Control.Click>두 컨트롤에 대 한 이벤트 처리기를 구현 <xref:System.Windows.Forms.Button> 합니다.

10. **도구 상자**에서 **MarqueeControlTest 구성 요소** 탭을 엽니다. 선택할 수 있는이 표시 됩니다 `DemoMarqueeControl` .

11. 인스턴스를 `DemoMarqueeControl` **Form1** 디자인 화면으로 끌어옵니다.

12. <xref:System.Windows.Forms.Control.Click>이벤트 처리기에서의 및 메서드를 호출 합니다 `Start` `Stop` `DemoMarqueeControl` .

    ```vb
    Private Sub startButton_Click(sender As Object, e As System.EventArgs)
        Me.demoMarqueeControl1.Start()
    End Sub 'startButton_Click

    Private Sub stopButton_Click(sender As Object, e As System.EventArgs)
    Me.demoMarqueeControl1.Stop()
    End Sub 'stopButton_Click
    ```

    ```csharp
    private void startButton_Click(object sender, System.EventArgs e)
    {
        this.demoMarqueeControl1.Start();
    }

    private void stopButton_Click(object sender, System.EventArgs e)
    {
        this.demoMarqueeControl1.Stop();
    }
    ```

13. 프로젝트를 `MarqueeControlTest` 시작 프로젝트로 설정 하 고 실행 합니다. 를 표시 하는 양식이 표시 됩니다 `DemoMarqueeControl` . **시작** 단추를 선택 하 여 애니메이션을 시작 합니다. 깜박이는 텍스트가 표시 되 고 테두리 주위에서 조명이 이동 합니다.

## <a name="next-steps"></a>다음 단계

에서는 `MarqueeControlLibrary` 사용자 지정 컨트롤 및 관련 디자이너의 간단한 구현을 보여 줍니다. 이 샘플은 여러 가지 방법으로 더 정교 하 게 만들 수 있습니다.

- 디자이너에서의 속성 값을 변경 합니다 `DemoMarqueeControl` . 컨트롤을 추가 하 `MarqueBorder` 고 부모 인스턴스 내에 도킹 하 여 중첩 된 효과를 만듭니다. 및 광원 관련 속성에 대해 다양 한 설정을 사용 하 여 실험 합니다 `UpdatePeriod` .

- 의 고유한 구현을 작성 `IMarqueeWidget` 합니다. 예를 들어, 여러 이미지를 사용 하 여 깜박이는 "neon sign" 또는 애니메이션 기호를 만들 수 있습니다.

- 디자인 타임 환경을 추가로 사용자 지정 합니다. 및 보다 더 많은 속성을 숨길 <xref:System.Windows.Forms.Control.Enabled%2A> 수 <xref:System.Windows.Forms.Control.Visible%2A> 있으며 새 속성을 추가할 수 있습니다. 자식 컨트롤 도킹과 같은 일반적인 작업을 단순화 하기 위해 새 디자이너 동사를 추가 합니다.

- 라이선스를 사용 `MarqueeControl` 합니다.

- 컨트롤이 serialize 되는 방법 및 컨트롤이 생성 되는 방식을 제어 합니다. 자세한 내용은 [동적 소스 코드 생성 및 컴파일](../../reflection-and-codedom/dynamic-source-code-generation-and-compilation.md)을 참조 하세요.

## <a name="see-also"></a>참고 항목

- <xref:System.Windows.Forms.UserControl>
- <xref:System.Windows.Forms.Design.ParentControlDesigner>
- <xref:System.Windows.Forms.Design.DocumentDesigner>
- <xref:System.ComponentModel.Design.IRootDesigner>
- <xref:System.ComponentModel.Design.DesignerVerb>
- <xref:System.Drawing.Design.UITypeEditor>
- <xref:System.ComponentModel.BackgroundWorker>
