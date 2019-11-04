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
author: jillre
ms.author: jillfra
manager: jillfra
ms.openlocfilehash: be6c913c43e3559806bc9f38a9c3152b544e4c07
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/03/2019
ms.locfileid: "73455530"
---
# <a name="how-to-test-the-run-time-behavior-of-a-usercontrol"></a>방법: UserControl의 런타임 동작 테스트

<xref:System.Windows.Forms.UserControl>를 개발 하는 경우 런타임 동작을 테스트 해야 합니다. 별도의 Windows 기반 응용 프로그램 프로젝트를 만들고 테스트 폼에 컨트롤을 저장할 수 있지만이 절차는 불편할 수 있습니다. 빠르고 쉬운 방법은 Visual Studio에서 제공 하는 **UserControl 테스트 컨테이너** 를 사용 하는 것입니다. 이 테스트 컨테이너는 Windows 컨트롤 라이브러리 프로젝트에서 직접 시작 됩니다.

> [!IMPORTANT]
> 테스트 컨테이너가 <xref:System.Windows.Forms.UserControl>를 로드 하려면 컨트롤에 하나 이상의 public 생성자가 있어야 합니다.

> [!NOTE]
> C++ **UserControl 테스트 컨테이너**를 사용 하 여 시각적 컨트롤을 테스트할 수 없습니다.

## <a name="test-the-run-time-behavior-of-a-usercontrol"></a>UserControl의 런타임 동작 테스트

1. Visual Studio에서 Windows 컨트롤 라이브러리 프로젝트를 만들고 이름을 **TestContainerExample**로 표시 합니다.

2. **Windows Forms 디자이너**에서 **도구 상자** 의 <xref:System.Windows.Forms.Label> 컨트롤을 컨트롤의 디자인 화면으로 끌어 옵니다.

3. <kbd>F5</kbd> 키를 눌러 프로젝트를 빌드하고 **UserControl 테스트 컨테이너**를 실행 합니다. **미리 보기** 창에 <xref:System.Windows.Forms.UserControl>와 함께 테스트 컨테이너가 표시 됩니다.

4. **미리 보기** 창 오른쪽의 <xref:System.Windows.Forms.PropertyGrid> 컨트롤에 표시 되는 <xref:System.Windows.Forms.Control.BackColor%2A> 속성을 선택 합니다. 해당 값을 **Controldark**값으로 변경 합니다. 컨트롤이 짙은 색으로 변경 되는지 확인 합니다. 다른 속성 값을 변경 하 고 컨트롤에 미치는 영향을 관찰 합니다.

5. **미리 보기** 창 아래에서 **사용자 정의 컨트롤 채우기** 확인란을 클릭 합니다. 창에 맞게 컨트롤의 크기가 조정 되는지 확인 합니다. 테스트 컨테이너의 크기를 조정 하 고 창을 사용 하 여 컨트롤의 크기가 조정 되는지 확인 합니다.

6. 테스트 컨테이너를 닫습니다.

7. **TestContainerExample** 프로젝트에 다른 사용자 정의 컨트롤을 추가 합니다.

8. **Windows Forms 디자이너**에서 **도구 상자** 의 <xref:System.Windows.Forms.Button> 컨트롤을 컨트롤의 디자인 화면으로 끌어 옵니다.

9. <kbd>F5</kbd> 키를 눌러 프로젝트를 빌드하고 테스트 컨테이너를 실행 합니다.

10. **사용자 컨트롤 선택** <xref:System.Windows.Forms.ComboBox> 클릭 하 여 두 사용자 정의 컨트롤 사이를 전환 합니다.

## <a name="test-user-controls-from-another-project"></a>다른 프로젝트에서 사용자 정의 컨트롤 테스트

현재 프로젝트의 테스트 컨테이너에 있는 다른 프로젝트에서 사용자 정의 컨트롤을 테스트할 수 있습니다.

1. Visual Studio에서 Windows 컨트롤 라이브러리 프로젝트를 만들고 이름을 **TestContainerExample2**로 표시 합니다.

2. **Windows Forms 디자이너**에서 **도구 상자** 의 <xref:System.Windows.Forms.RadioButton> 컨트롤을 컨트롤의 디자인 화면으로 끌어 옵니다.

3. <kbd>F5</kbd> 키를 눌러 프로젝트를 빌드하고 테스트 컨테이너를 실행 합니다. **미리 보기** 창에 <xref:System.Windows.Forms.UserControl>와 함께 테스트 컨테이너가 표시 됩니다.

4. **로드** 단추를 클릭 합니다.

5. **열기** 대화 상자에서 이전 절차에서 빌드한 *TestContainerExample*로 이동 합니다. *TestContainerExample* 를 선택 하 고 **열기** 단추를 클릭 하 여 사용자 정의 컨트롤을 로드 합니다.

6. **사용자 정의 컨트롤** <xref:System.Windows.Forms.ComboBox>를 사용 하 여 **TestContainerExample** 프로젝트에서 두 사용자 컨트롤 간을 전환할 수 있습니다.

## <a name="see-also"></a>참조

- <xref:System.Windows.Forms.UserControl>
- [방법: 복합 컨트롤 작성](how-to-author-composite-controls.md)
- [연습: 합성 컨트롤 제작](walkthrough-authoring-a-composite-control-with-visual-csharp.md)
- [사용자 정의 컨트롤 디자이너](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/183c3hth(v=vs.100))
