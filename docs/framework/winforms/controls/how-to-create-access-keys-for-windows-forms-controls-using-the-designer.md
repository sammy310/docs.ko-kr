---
title: '방법: 디자이너를 사용하여 Windows Forms 컨트롤에 대한 선택키 만들기'
ms.date: 03/30/2017
helpviewer_keywords:
- controls [Windows Forms], access keys
- Button control [Windows Forms], access keys
- dialog box controls [Windows Forms], mnemonics
- access keys [Windows Forms], creating for controls
- mnemonics [Windows Forms], adding to dialog box controls
- ampersand character in shortcut key
- Windows Forms controls, access keys
- examples [Windows Forms], controls
- Text property [Windows Forms], specifying access keys for controls
- keyboard shortcuts [Windows Forms], creating for controls
- access keys [Windows Forms], Windows Forms
- ALT key
ms.assetid: 4c374c4c-4ca9-4a68-ac96-9dc3ab0f518a
ms.openlocfilehash: 410fc0134046c5fa7e05bfcd38ce6818244a0a54
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59307875"
---
# <a name="how-to-create-access-keys-for-windows-forms-controls-using-the-designer"></a>방법: 디자이너를 사용하여 Windows Forms 컨트롤에 대한 선택키 만들기
*선택키가* 은 메뉴, 메뉴 항목 또는 예: 단추 컨트롤의 레이블 텍스트에 밑줄이 그어진된 문자입니다. 사용자를가 단추를 미리 정의 된 액세스 키를 사용 하 여 함께에서 ALT 키를 눌러 "클릭" 수 있습니다. 예를 들어, 단추 폼을 인쇄 하는 프로시저를 실행 하는 경우 및 해당 `Text` "Print" 추가 앰퍼샌드 (&) "P" 하면 문자에 밑줄을 표시 "P" 단추 텍스트의 런타임 시 문자 앞에 속성을 설정 합니다. ALT + P를 눌러 단추와 연결 된 명령을 실행할 수 있습니다. 포커스를 받을 수 있는 컨트롤에 대 한 액세스 키를 사용할 수 없습니다.  
  
> [!NOTE]
>  표시되는 대화 상자와 메뉴 명령은 활성 설정이나 버전에 따라 도움말에서 설명하는 것과 다를 수 있습니다. 설정을 변경하려면 **도구** 메뉴에서 **설정 가져오기 및 내보내기** 를 선택합니다. 자세한 내용은 [Visual Studio IDE 개인 설정](/visualstudio/ide/personalizing-the-visual-studio-ide)을 참조하세요.  
  
### <a name="to-create-an-access-key-for-a-control"></a>컨트롤에 대 한 액세스 키를 만들려면  
  
1. 에 **속성** 창에서 `Text` 속성 앰퍼샌드를 포함 하는 문자열 (&) 앞에 대 한 액세스 키가 됩니다. 예를 들어, 입력을 설정 하려면 문자 "P" 액세스 키로 **인쇄 및** 모눈에 있습니다.  
  
## <a name="see-also"></a>참고자료

- <xref:System.Windows.Forms.Button>
- [방법: Windows Forms 단추 클릭에 응답](how-to-respond-to-windows-forms-button-clicks.md)
- [방법: 설정 하 여 표시 되는 텍스트는 Windows Forms 컨트롤](how-to-set-the-text-displayed-by-a-windows-forms-control.md)
- [개별 Windows Forms 컨트롤 레이블 지정 및 바로 가기 제공](labeling-individual-windows-forms-controls-and-providing-shortcuts-to-them.md)
