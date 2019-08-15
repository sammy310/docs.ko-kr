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
ms.openlocfilehash: 01bed04483702ba2e62162b675aa1138bc1b0e01
ms.sourcegitcommit: cf9515122fce716bcfb6618ba366e39b5a2eb81e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/15/2019
ms.locfileid: "69039516"
---
# <a name="how-to-create-access-keys-for-windows-forms-controls-using-the-designer"></a>방법: 디자이너를 사용하여 Windows Forms 컨트롤에 대한 선택키 만들기
*선택 키는* 메뉴, 메뉴 항목 또는 단추와 같은 컨트롤의 레이블 텍스트에서 밑줄 친 문자입니다. 사용자가 미리 정의 된 액세스 키와 함께 ALT 키를 눌러 단추를 "클릭" 할 수 있습니다. 예를 들어 단추가 폼을 인쇄 하는 프로시저를 실행 하는 경우 해당 `Text` 속성을 "print"로 설정 하면 문자 "p" 앞에 앰퍼샌드 (&)를 추가 하면 런타임에 단추 텍스트에서 문자 "p"가 밑줄로 표시 됩니다. 사용자는 ALT + P를 눌러 단추와 연결 된 명령을 실행할 수 있습니다. 포커스를 받을 수 없는 컨트롤에는 선택 키를 사용할 수 없습니다.

## <a name="to-create-an-access-key-for-a-control"></a>컨트롤에 대 한 선택 키를 만들려면

1. **속성** 창에서 액세스 키가 될 `Text` 문자 앞에 앰퍼샌드 (&)를 포함 하는 문자열로 속성을 설정 합니다. 예를 들어 문자 "P"를 선택 키로 설정 하려면 표 형태로 **& 인쇄** 를 입력 합니다.

## <a name="see-also"></a>참고자료

- <xref:System.Windows.Forms.Button>
- [방법: Windows Forms 단추 클릭에 응답](how-to-respond-to-windows-forms-button-clicks.md)
- [방법: Windows Forms 컨트롤에 표시 되는 텍스트 설정](how-to-set-the-text-displayed-by-a-windows-forms-control.md)
- [개별 Windows Forms 컨트롤 레이블 지정 및 바로 가기 제공](labeling-individual-windows-forms-controls-and-providing-shortcuts-to-them.md)
