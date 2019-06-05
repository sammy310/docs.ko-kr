---
title: '방법: Windows Form에 단순 바인딩된 컨트롤 만들기'
ms.date: 03/30/2017
helpviewer_keywords:
- data binding [Windows Forms], simple data binding
- Windows Forms controls, data binding
ms.assetid: 3bcaded8-0f1a-4cc0-8830-f59be253bf4e
ms.openlocfilehash: 5c92b7bfd5026b0569397dc05cca216fbdab0753
ms.sourcegitcommit: d8ebe0ee198f5d38387a80ba50f395386779334f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/05/2019
ms.locfileid: "66689311"
---
# <a name="how-to-create-a-simple-bound-control-on-a-windows-form"></a>방법: Windows Form에 단순 바인딩된 컨트롤 만들기

사용 하 여 *단순 바인딩*, 컨트롤에서 데이터 집합 테이블에서 열 값과 같은 단일 데이터 요소를 표시할 수 있습니다. 컨트롤의 모든 속성을 데이터 값에 간단한 바인딩할 수 있습니다.

> [!NOTE]
> 표시되는 대화 상자와 메뉴 명령은 활성 설정이나 버전에 따라 도움말에서 설명하는 것과 다를 수 있습니다. 설정을 변경하려면 **도구** 메뉴에서 **설정 가져오기 및 내보내기** 를 선택합니다. 자세한 내용은 [Visual Studio IDE 개인 설정](/visualstudio/ide/personalizing-the-visual-studio-ide)을 참조하세요.

### <a name="to-simple-bind-a-control"></a>단순 컨트롤을 바인딩

1. 데이터 소스에 연결합니다. 자세한 내용은 [데이터 원본에 연결할](../data/adonet/connecting-to-a-data-source.md)합니다.

2. 폼에서 컨트롤을 선택 하 고 표시 합니다 **속성** 창입니다.

3. 확장 된 **(DataBindings)** 속성입니다.

     아래에 있는 대부분의 바인딩된 속성이 표시 됩니다는 **(DataBindings)** 속성입니다. 예를 들어, 대부분의 컨트롤에서에서의 **텍스트** 속성은 가장 자주 바인딩됩니다.

4. 않으려면 속성 바인딩이 아닙니다. 일반적으로 바인딩된 속성 중 하나를 클릭 합니다 **줄임표** 단추 (![의 줄임표 단추 (...)의 Visual Studio 속성 창에서](./media/how-to-create-a-simple-bound-control-on-a-windows-form/visual-studio-ellipsis-button.png))에 **( 고급)** 상자를 표시 합니다 **서식 지정 및 고급 바인딩** 해당 컨트롤에 대 한 속성의 전체 목록 사용 하 여 대화 상자.

5. 아래의 드롭다운 화살표를 클릭 하 고 바인딩 속성을 선택 **바인딩**합니다.

     사용 가능한 데이터 소스 목록이 표시됩니다.

6. 원하는 단일 데이터 요소를 찾을 때까지 바인딩할 데이터 소스를 확장합니다. 예를 들어 데이터 집합의 테이블에서 열 값에 바인딩할 경우 데이터 집합 이름을 확장하고 나서 테이블을 이름을 확장하여 열 이름을 표시합니다.

7. 바인딩할 요소 이름을 클릭합니다.

8. 작업할 경우는 **서식 지정 및 고급 바인딩** 대화 상자, 클릭 **확인** 돌아가려면 합니다 **속성** 창.

9. 컨트롤의 추가 속성을 바인딩할 경우 3 ~ 7 단계를 반복 합니다.

    > [!NOTE]
    > 있기 때문에 단순 바인딩된 컨트롤에는 하나의 데이터 요소만 표시, 전형적인 Windows Form을 단순 바인딩된 컨트롤에서 탐색 논리를 포함 하도록 합니다.

## <a name="see-also"></a>참고자료

- <xref:System.Windows.Forms.Binding>
- [Windows Forms 데이터 바인딩](windows-forms-data-binding.md)
- [데이터 바인딩 및 Windows Forms](data-binding-and-windows-forms.md)
