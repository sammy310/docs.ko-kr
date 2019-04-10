---
title: '방법: Windows Forms 컨트롤에 대한 선택키 만들기'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- controls [Windows Forms], access keys
- Button control [Windows Forms], access keys
- dialog box controls [Windows Forms], mnemonics
- access keys [Windows Forms], creating for controls
- mnemonics [Windows Forms], adding to dialog box controls
- mnemonics
- ampersand character in shortcut key
- Windows Forms controls, access keys
- examples [Windows Forms], controls
- Text property [Windows Forms], specifying access keys for controls
- keyboard shortcuts [Windows Forms], creating for controls
- access keys [Windows Forms], Windows Forms
- ALT key
ms.assetid: 4faa0991-28ec-4eca-91db-51dc2cd6a7ac
ms.openlocfilehash: fefd322afb938453ec1ea23e8ff6de9f9ae2a851
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59141637"
---
# <a name="how-to-create-access-keys-for-windows-forms-controls"></a>방법: Windows Forms 컨트롤에 대한 선택키 만들기
*선택키가* 은 메뉴, 메뉴 항목 또는 예: 단추 컨트롤의 레이블 텍스트에 밑줄이 그어진된 문자입니다. 액세스 키가 있는 사용자 수 "단추를 클릭" 미리 정의 된 액세스 키를 사용 하 여 함께에서 ALT 키를 눌러. 예를 들어, 단추 폼을 인쇄 하는 프로시저를 실행 하는 경우 및 해당 `Text` 속성 "Print", "P" 문자로 하면 문자에는 런타임에 단추 텍스트에 밑줄이 표시 된 "P" 전에 앰퍼샌드를 추가 합니다. ALT + P를 눌러 단추와 연결 된 명령을 실행할 수 있습니다. 포커스를 받을 수 있는 컨트롤에 대 한 액세스 키를 사용할 수 없습니다.  
  
### <a name="to-create-an-access-key-for-a-control"></a>컨트롤에 대 한 액세스 키를 만들려면  
  
1.  설정 된 `Text` 앰퍼샌드를 포함 하는 문자열 (&) 문자 바로 가기로 속성입니다.  
  
    ```vb  
    ' Set the letter "P" as an access key.  
    Button1.Text = "&Print"  
    ```  
  
    ```csharp  
    // Set the letter "P" as an access key.  
    button1.Text = "&Print";  
    ```  
  
    ```cpp  
    // Set the letter "P" as an access key.  
    button1->Text = "&Print";  
    ```  
  
    > [!NOTE]
    >  앰퍼샌드 캡션을 액세스 키를 만들지 않고를 넣으려면 두 앰퍼샌드 (& &). 단일 앰퍼샌드 캡션의 나타나고 문자가 없는 밑줄이 표시 되 면 됩니다.  
  
## <a name="see-also"></a>참고자료

- <xref:System.Windows.Forms.Button>
- [방법: Windows Forms 단추 클릭에 응답](how-to-respond-to-windows-forms-button-clicks.md)
- [방법: Windows Forms 컨트롤에서 표시하는 텍스트 설정](how-to-set-the-text-displayed-by-a-windows-forms-control.md)
- [개별 Windows Forms 컨트롤 레이블 지정 및 바로 가기 제공](labeling-individual-windows-forms-controls-and-providing-shortcuts-to-them.md)
