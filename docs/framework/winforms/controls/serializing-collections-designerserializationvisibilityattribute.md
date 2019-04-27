---
title: '연습: DesignerSerializationVisibilityAttribute를 사용하여 표준 형식의 컬렉션 직렬화'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- serialization [Windows Forms], collections
- standard types [Windows Forms], collections
- collections [Windows Forms], serializing
- collections [Windows Forms], standard types
ms.assetid: 020c9df4-fdc5-4dae-815a-963ecae5668c
ms.openlocfilehash: c113dcf814a252808ae3232751028947c26821ba
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62012440"
---
# <a name="walkthrough-serializing-collections-of-standard-types-with-the-designerserializationvisibilityattribute"></a>연습: DesignerSerializationVisibilityAttribute를 사용하여 표준 형식의 컬렉션 직렬화

사용자 지정 컨트롤 노출 하는 속성으로 컬렉션 경우도 있습니다. 이 연습을 사용 하는 방법에 설명 합니다 <xref:System.ComponentModel.DesignerSerializationVisibilityAttribute> 디자인 타임에 컬렉션 serialize 되는 방식을 제어 하는 클래스입니다. 적용 된 <xref:System.ComponentModel.DesignerSerializationVisibilityAttribute.Content> 컬렉션 속성에 값을 입력 하면 속성을 serialize 합니다.

 이 항목의 코드를 단일 목록으로 복사하려면 [방법: Designerserializationvisibilityattribute를 사용 하 여 표준 형식의 컬렉션 serialize](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/ms171833(v=vs.120))합니다.

> [!NOTE]
> 표시되는 대화 상자와 메뉴 명령은 활성 설정이나 버전에 따라 도움말에서 설명하는 것과 다를 수 있습니다. 설정을 변경하려면 **도구** 메뉴에서 **설정 가져오기 및 내보내기** 를 선택합니다. 자세한 내용은 [Visual Studio IDE 개인 설정](/visualstudio/ide/personalizing-the-visual-studio-ide)을 참조하세요.

## <a name="prerequisites"></a>전제 조건
 이 연습을 완료하려면 다음 사항이 필요합니다.

- 만들고 Visual Studio를 설치한 컴퓨터에서 Windows Forms 응용 프로그램 프로젝트를 실행 하는 일을 할 수 있는 충분 한 권한입니다.

## <a name="creating-a-control-that-has-a-serializable-collection"></a>직렬화 가능 컬렉션을 포함 하는 컨트롤 만들기
 첫 번째 단계는 컨트롤 속성으로 직렬화 가능 컬렉션을 만드는 것입니다. 사용 하 여이 컬렉션의 콘텐츠를 편집할 수 있습니다 합니다 **컬렉션 편집기**에서 액세스할 수 있는 합니다 **속성** 창입니다.

### <a name="to-create-a-control-with-a-serializable-collection"></a>직렬화 가능 컬렉션을 사용 하 여 컨트롤을 만들려면

1. 라는 Windows 컨트롤 라이브러리 프로젝트를 만듭니다 `SerializationDemoControlLib`합니다. 자세한 내용은 [Windows 컨트롤 라이브러리 템플릿을](https://docs.microsoft.com/previous-versions/kxczf775(v=vs.100))합니다.

2. 이름 바꾸기 `UserControl1` 에 `SerializationDemoControl`입니다. 자세한 내용은 [이름 바꾸기 리팩터링 코드 기호](/visualstudio/ide/reference/rename)합니다.

3. 에 **속성** 창에서 값을 설정 합니다 <xref:System.Windows.Forms.Padding.All%2A?displayProperty=nameWithType> 속성을 `10`입니다.

4. 위치는 <xref:System.Windows.Forms.TextBox> 에서 제어를 `SerializationDemoControl`입니다.

5. <xref:System.Windows.Forms.TextBox> 컨트롤을 선택합니다. 에 **속성** 창에서 다음 속성을 설정 합니다.

    |속성|다음으로 변경|
    |--------------|---------------|
    |**Multiline**|`true`|
    |**도킹**|<xref:System.Windows.Forms.DockStyle.Fill>|
    |**ScrollBars**|<xref:System.Windows.Forms.ScrollBars.Vertical>|
    |**ReadOnly**|`true`|

6. 에 **코드 편집기**, 명명 된 문자열 배열 필드를 선언 `stringsValue` 에서 `SerializationDemoControl`합니다.

     [!code-cpp[System.ComponentModel.DesignerSerializationVisibilityAttribute#4](~/samples/snippets/cpp/VS_Snippets_Winforms/System.ComponentModel.DesignerSerializationVisibilityAttribute/cpp/form1.cpp#4)]
     [!code-csharp[System.ComponentModel.DesignerSerializationVisibilityAttribute#4](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.DesignerSerializationVisibilityAttribute/CS/form1.cs#4)]
     [!code-vb[System.ComponentModel.DesignerSerializationVisibilityAttribute#4](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.DesignerSerializationVisibilityAttribute/VB/form1.vb#4)]

7. 정의 된 `Strings` 속성에는 `SerializationDemoControl`.

> [!NOTE]
> <xref:System.ComponentModel.DesignerSerializationVisibilityAttribute.Content> 값 컬렉션의 serialization을 사용 하도록 설정 하는 데 사용 됩니다.

 [!code-cpp[System.ComponentModel.DesignerSerializationVisibilityAttribute#5](~/samples/snippets/cpp/VS_Snippets_Winforms/System.ComponentModel.DesignerSerializationVisibilityAttribute/cpp/form1.cpp#5)]
 [!code-csharp[System.ComponentModel.DesignerSerializationVisibilityAttribute#5](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.DesignerSerializationVisibilityAttribute/CS/form1.cs#5)]
 [!code-vb[System.ComponentModel.DesignerSerializationVisibilityAttribute#5](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.DesignerSerializationVisibilityAttribute/VB/form1.vb#5)]

1. F5 키를 눌러 프로젝트를 빌드하고 **UserControl 테스트 컨테이너**에서 컨트롤을 실행합니다.

2. 찾을 합니다 `Strings` 속성에는 <xref:System.Windows.Forms.PropertyGrid> 의 **UserControl 테스트 컨테이너**합니다. 클릭는 `Strings` 속성을 다음 줄임표 (![VisualStudioEllipsesButton 스크린 샷](../media/vbellipsesbutton.png "vbEllipsesButton")) 버튼을 클릭 하는 **문자열 컬렉션 편집기**.

3. 여러 문자열을 입력 합니다 **문자열 컬렉션 편집기**합니다. 각 문자열의 끝에서 ENTER 키를 눌러 구분 합니다. 클릭 **확인** 문자열 입력이 완료 되 면 합니다.

> [!NOTE]
> 입력 문자열에 표시 된 <xref:System.Windows.Forms.TextBox> 의 `SerializationDemoControl`합니다.

## <a name="serializing-a-collection-property"></a>컬렉션 속성을 직렬화 하는 작업

컨트롤의 serialization 동작을 테스트 하려면 폼에 배치할을 사용 하 여 컬렉션의 콘텐츠를 변경 합니다 **컬렉션 편집기**합니다. 특별 한 디자이너 파일을 확인 하 여 serialized 컬렉션 상태를 확인할 수는 **Windows Forms 디자이너** 에서 코드를 생성 합니다.

### <a name="to-serialize-a-collection"></a>컬렉션 serialize

1. Windows 응용 프로그램 프로젝트를 솔루션에 추가 합니다. 프로젝트 이름을 `SerializationDemoControlTest`로 지정합니다.

2. 에 **도구 상자**, 라는 탭을 찾으려면 **SerializationDemoControlLib 구성 요소**합니다. 이 탭에서 찾을 수 있습니다는 `SerializationDemoControl`합니다. 자세한 내용은 [연습: 사용자 지정 구성 요소를 사용 하 여 도구 상자에 자동으로 채우기](walkthrough-automatically-populating-the-toolbox-with-custom-components.md)합니다.

3. 위치는 `SerializationDemoControl` 양식의 합니다.

4. 찾을 합니다 `Strings` 속성에는 **속성** 창입니다. 클릭는 `Strings` 속성을 다음 줄임표 (![VisualStudioEllipsesButton 스크린 샷](../media/vbellipsesbutton.png "vbEllipsesButton")) 버튼을 클릭 하는 **문자열 컬렉션 편집기**.

5. 여러 문자열을 입력 합니다 **문자열 컬렉션 편집기**합니다. 각 문자열의 끝에서 ENTER 키를 눌러 구분 합니다. 클릭 **확인** 문자열 입력이 완료 되 면 합니다.

> [!NOTE]
> 입력 문자열에 표시 된 <xref:System.Windows.Forms.TextBox> 의 `SerializationDemoControl`합니다.

1. **솔루션 탐색기**에서 **모든 파일 표시** 단추를 클릭합니다.

2. 엽니다는 **Form1** 노드. 아래 호출 파일 이기 **Form1.Designer.cs** 하거나 **Form1.Designer.vb**합니다. 이 파일은 파일에는 **Windows Forms 디자이너** 폼과 해당 자식 컨트롤의 디자인 타임 상태를 나타내는 코드를 내보냅니다. **코드 편집기**에서 이 파일을 엽니다.

3. 라는 영역을 엽니다 **Windows Form 디자이너에서 코드 생성** 레이블이 지정 된 섹션을 찾습니다 **serializationDemoControl1**합니다. 이 레이블 아래에 있는 컨트롤의 serialize 된 상태를 나타내는 코드입니다. 5 단계에서 입력 문자열에 대 한 할당에 표시 된 `Strings` 속성입니다. C# 및 Visual Basic의 경우 다음 코드 예제에서는 볼 수 있는 것은 문자열 "red", "주황색" 및 "노란색"를 입력 하는 경우 비슷한 코드를 보여 줍니다.

    ```csharp
    this.serializationDemoControl1.Strings = new string[] {
            "red",
            "orange",
            "yellow"};
    ```

    ```vb
    Me.serializationDemoControl1.Strings = New String() {"red", "orange", "yellow"}
    ```

4. 에 **코드 편집기**의 값을 변경 합니다 <xref:System.ComponentModel.DesignerSerializationVisibilityAttribute> 에 `Strings` 속성을 <xref:System.ComponentModel.DesignerSerializationVisibility.Hidden>.

    ```csharp
    [DesignerSerializationVisibility(DesignerSerializationVisibility.Hidden)]
    ```

    ```vb
    <DesignerSerializationVisibility(DesignerSerializationVisibility.Hidden)> _
    ```

5. 3-4 단계를 반복 고 솔루션을 다시 작성 합니다.

> [!NOTE]
> 이 경우에 **Windows Forms 디자이너** 대 한 할당이 내보냅니다는 `Strings` 속성입니다.

## <a name="next-steps"></a>다음 단계

표준 형식의 컬렉션을 직렬화 하는 방법을 알고, 디자인 타임 환경에 사용자 지정 컨트롤을 보다 강력 하 게 통합 하는 것이 좋습니다. 다음 항목에는 사용자 지정 컨트롤의 디자인 타임 통합을 개선 하는 방법을 설명 합니다.

- [디자인 타임 아키텍처](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/c5z9s1h4(v=vs.120))

- [Windows Forms 컨트롤의 특성](attributes-in-windows-forms-controls.md)

- [디자이너 Serialization 개요](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/ms171834(v=vs.120))

- [연습: Visual Studio 디자인 타임 기능을 활용 하는 Windows Forms 컨트롤 만들기](creating-a-wf-control-design-time-features.md)

## <a name="see-also"></a>참고자료

- <xref:System.ComponentModel.DesignerSerializationVisibilityAttribute>
- [디자이너 Serialization 개요](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/ms171834(v=vs.120))
- [방법: Designerserializationvisibilityattribute를 사용 하 여 표준 형식의 컬렉션 serialize](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/ms171833(v=vs.120))
- [연습: 사용자 지정 구성 요소를 사용 하 여 도구 상자에 자동으로 채우기](walkthrough-automatically-populating-the-toolbox-with-custom-components.md)
