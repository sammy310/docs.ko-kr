---
title: '방법: 상속 선택 대화 상자를 사용하여 양식 상속'
ms.date: 03/30/2017
helpviewer_keywords:
- inheritance [Windows Forms], forms
- Inheritance Picker dialog box
- inherited forms [Windows Forms], creating
ms.assetid: 969b4c04-12aa-4297-93a2-0ae747447823
ms.openlocfilehash: 5ae1c236835141b10bc704cd39f55de6e3e974b0
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61723127"
---
# <a name="how-to-inherit-forms-using-the-inheritance-picker-dialog-box"></a>방법: 상속 선택 대화 상자를 사용하여 양식 상속
양식이나 다른 개체를 상속하는 가장 쉬운 방법은 **상속 선택** 대화 상자를 사용하는 것입니다. 이 대화 상자에서는 다른 솔루션에서 이미 만든 코드 또는 UI(사용자 인터페이스)를 활용할 수 있습니다.  
  
> [!NOTE]
>  **상속 선택** 대화 상자를 통해 양식에서 상속하려면 해당 양식이 포함된 프로젝트가 실행 파일 또는 DLL로 빌드되었어야 합니다. 프로젝트를 빌드하려면 **빌드** 메뉴에서 **솔루션 빌드**를 선택합니다.  
>   
>  표시되는 대화 상자와 메뉴 명령은 활성 설정이나 버전에 따라 도움말에서 설명하는 것과 다를 수 있습니다. 설정을 변경하려면 **도구** 메뉴에서 **설정 가져오기 및 내보내기** 를 선택합니다. 자세한 내용은 [Visual Studio IDE 개인 설정](/visualstudio/ide/personalizing-the-visual-studio-ide)을 참조하세요.  
  
### <a name="to-create-a-windows-form-inherited-from-an-existing-form-by-using-the-inheritance-picker"></a>상속 선택을 사용하여 기존 폼에서 상속된 Windows Form을 만들려면  
  
1. **프로젝트** 메뉴에서 **Windows Form 추가**를 선택합니다.  
  
     **새 항목 추가** 대화 상자가 열립니다.  
  
2. 검색을 **상속 된 폼** searchbox 또는 클릭 하 여 템플릿을 **Windows Forms** 범주를 선택 하 고 이름에 **이름** 상자입니다. **추가** 단추를 클릭하여 계속합니다.  
  
     **상속 선택** 대화 상자가 열립니다. 현재 프로젝트에 이미 양식이 포함되어 있는 경우 **상속 선택** 대화 상자에 표시됩니다.  
  
3. 다른 어셈블리의 양식에서 상속하려면 **찾아보기** 단추를 클릭합니다.  
  
4. **상속받을 구성 요소를 포함하는 파일을 선택하세요.** 대화 상자 내에서 원하는 양식이나 모듈이 포함된 프로젝트로 이동합니다.  
  
5. .exe 또는 .dll 파일의 이름을 클릭하여 선택하고 **열기** 단추를 클릭합니다.  
  
     그러면 구성 요소와 구성 요소가 있는 프로젝트가 나열된 **상속 선택** 대화 상자로 돌아갑니다.  
  
6. 구성 요소를 선택합니다.  
  
     **솔루션 탐색기**에서 구성 요소가 프로젝트에 추가됩니다. UI가 있는 경우 상속 된 양식의 일부인 컨트롤 문자 모양으로 표시 됩니다 (![스크린샷 Visual Basic 상속 기호.](./media/how-to-inherit-forms-using-the-inheritance-picker-dialog-box/visual-basic-inheritance-glyph.gif))를 선택 하면 컨트롤에는 보안 수준을 나타내는 테두리가 포함을 슈퍼 클래스로 지정 된 형식입니다. 다른 보안 수준에 해당하는 동작은 아래 표에 나열되어 있습니다.  
  
    |컨트롤의 보안 수준|디자이너 및 코드 편집기를 통해 상속된 폼과 사용할 수 있는 상호 작용|  
    |-------------------------------|--------------------------------------------------------------------------------|  
    |Public|크기 조정 핸들이 있는 표준 테두리: 컨트롤의 크기를 조정하고 이동할 수 있습니다. 컨트롤을 선언한 클래스에서 내부적으로 및 다른 클래스에서 외부적으로 컨트롤에 액세스할 수 있습니다.|  
    |보호됨|크기 조정 핸들이 있는 표준 테두리: 컨트롤의 크기를 조정하고 이동할 수 있습니다. 컨트롤을 선언한 클래스 및 부모 클래스에서 상속된 모든 클래스에서 내부적으로 액세스할 수 있지만 외부 클래스에서는 액세스할 수 없습니다.|  
    |Protected Internal(Visual Basic에서는 Protected Friend)|크기 조정 핸들이 있는 표준 테두리: 컨트롤의 크기를 조정하고 이동할 수 있습니다. 컨트롤을 선언한 클래스, 부모 클래스에서 상속된 모든 클래스 및 컨트롤을 포함하는 어셈블리의 다른 멤버에서 내부적으로 액세스할 수 있습니다.|  
    |Internal(Visual Basic에서는 Friend)|크기 조정 핸들이 양식에 표시되지 않고 **속성** 창에 속성이 표시된 표준 테두리입니다. 그러나 컨트롤의 모든 측면은 읽기 전용으로 간주됩니다. 컨트롤을 이동 또는 크기 조정하거나 해당 속성을 변경할 수 없습니다. 컨트롤이 그룹 상자와 같은 다른 컨트롤의 컨테이너인 경우 해당 컨트롤이 public인 경우에도 새로운 컨트롤을 추가할 수 없고 기존 컨트롤을 제거할 수도 없습니다. 컨트롤이 포함된 어셈블리의 다른 멤버만 컨트롤에 액세스할 수 있습니다.|  
    |Private|크기 조정 핸들이 양식에 표시되지 않고 **속성** 창에 속성이 표시된 표준 테두리입니다. 그러나 컨트롤의 모든 측면은 읽기 전용으로 간주됩니다. 컨트롤을 이동 또는 크기 조정하거나 해당 속성을 변경할 수 없습니다. 컨트롤이 그룹 상자와 같은 다른 컨트롤의 컨테이너인 경우 해당 컨트롤이 public인 경우에도 새로운 컨트롤을 추가할 수 없고 기존 컨트롤을 제거할 수도 없습니다. 컨트롤을 선언한 클래스만 컨트롤에 액세스할 수 있습니다.|  
  
     기본 양식의 모양을 변경하는 방법에 대한 자세한 내용은 [기본 양식의 모양 수정 효과](effects-of-modifying-base-form-appearance.md)를 참조하세요.  
  
    > [!NOTE]
    >  Windows Forms의 표준 컨트롤 및 구성 요소와 상속된 컨트롤 및 구성 요소를 결합하는 경우 z 순서와 충돌이 발생할 수 있습니다. z 순서를 수정하여 이 문제를 해결할 수 있습니다. 이렇게 하려면 **형식** 메뉴를 클릭하고 **순서**를 가리킨 다음 **맨 앞으로 가져오기** 또는 **맨 뒤로 보내기**를 클릭합니다. 컨트롤의 z 순서에 대 한 자세한 내용은 참조 하세요. [방법: Windows Forms에서 개체 계층화](../controls/how-to-layer-objects-on-windows-forms.md)합니다.  
  
## <a name="see-also"></a>참고자료

- [Inherits 문](~/docs/visual-basic/language-reference/statements/inherits-statement.md)
- [using](~/docs/csharp/language-reference/keywords/using.md)
- [기본 폼의 모양 수정 효과](effects-of-modifying-base-form-appearance.md)
- [Windows Forms 시각적 개체 상속](windows-forms-visual-inheritance.md)
