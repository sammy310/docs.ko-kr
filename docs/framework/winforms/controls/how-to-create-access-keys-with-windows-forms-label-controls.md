---
title: '방법: Windows Forms Label 컨트롤을 사용하여 선택키 만들기'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- controls [Windows Forms], access keys
- dialog box controls [Windows Forms], mnemonics
- access keys [Windows Forms], creating for controls
- Label control [Windows Forms], creating access keys
- mnemonics [Windows Forms], adding to dialog box controls
- mnemonics
- Windows Forms controls, access keys
- UseMnemonic property [Windows Forms], Label control
- keyboard shortcuts [Windows Forms], creating for controls
- access keys [Windows Forms], Windows Forms
ms.assetid: 5ee8f823-80be-4a4f-96a4-412671e2e306
ms.openlocfilehash: ffe4bf6fb29e82b04938e2ba9a2d9d21e5eabcde
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61747110"
---
# <a name="how-to-create-access-keys-with-windows-forms-label-controls"></a>방법: Windows Forms Label 컨트롤을 사용하여 선택키 만들기
Windows Forms <xref:System.Windows.Forms.Label> 다른 컨트롤에 대 한 액세스 키를 정의 하려면 컨트롤을 사용할 수 있습니다. Label 컨트롤의 액세스 키를 정의할 때 사용자 ALT 키와 탭 순서에서 오는 컨트롤에 포커스를 이동 하도록 지정 하는 문자를 누를 수 있습니다. 레이블 포커스를 받을 수 없습니다 때문에 포커스가 탭 순서의 다음 컨트롤로 자동으로 이동 합니다. 이 기술을 사용 하 여 액세스 키 텍스트 상자, 콤보 상자, 목록 상자 및 데이터 표를 할당 합니다.  
  
### <a name="to-assign-an-access-key-to-a-control-with-a-label"></a>레이블 컨트롤에 액세스 키를 할당 하려면  
  
1. 레이블을 먼저 그린 하 한 다음 다른 컨트롤을 그립니다.  
  
     또는  
  
     순서에 관계 없이 컨트롤을 그리고 설정 된 <xref:System.Windows.Forms.Control.TabIndex%2A> 다른 컨트롤 보다 1 작은 레이블의 속성입니다.  
  
2. 레이블 설정 <xref:System.Windows.Forms.Label.UseMnemonic%2A> 속성을 `true`입니다.  
  
3. 앰퍼샌드 (&) 레이블의에서 <xref:System.Windows.Forms.Label.Text%2A> 레이블에 대 한 액세스 키를 할당 하는 속성. 자세한 내용은 [만드는 액세스 키에 대 한 Windows Forms 컨트롤](how-to-create-access-keys-for-windows-forms-controls.md)합니다.  
  
    > [!NOTE]
    >  액세스 키를 만드는 데 사용할 하는 것이 아니라 레이블 컨트롤에서 앰퍼샌드를 표시 하려고 합니다. 이 데이터는 앰퍼샌드를 포함 하는 위치 레코드 집합에서 필드 레이블 컨트롤을 바인딩하는 경우 발생할 수 있습니다. 앰퍼샌드 레이블 컨트롤에 표시할 설정 합니다 <xref:System.Windows.Forms.Label.UseMnemonic%2A> 속성을 `false`입니다. 앰퍼샌드를 표시 하 고 액세스 키를 갖게 하려는 경우 설정 합니다 <xref:System.Windows.Forms.Label.UseMnemonic%2A> 속성을 `true` 하나의 앰퍼샌드를 사용 하 여 액세스 키를 보여 주고 (&) 및 앰퍼샌드를 앰퍼샌드를 두 번 표시할입니다.  
  
    ```vb  
    Label1.UseMnemonic = True  
    Label1.Text = "&Print"  
    Label2.UseMnemonic = True  
    Label2.Text = "&Copy && Paste"  
    ```  
  
    ```csharp  
    label1.UseMnemonic = true;  
    label1.Text = "&Print";  
    label2.UseMnemonic = true;  
    label2.Text = "&Copy && Paste";  
    ```  
  
    ```cpp  
    label1->UseMnemonic = true;  
    label1->Text = "&Print";  
    label2->UseMnemonic = true;  
    label2->Text = "&Copy && Paste";  
    ```  
  
## <a name="see-also"></a>참고자료

- [방법: 내용에 맞게 Windows Forms Label 컨트롤 크기 조정](how-to-size-a-windows-forms-label-control-to-fit-its-contents.md)
- [Label 컨트롤 개요](label-control-overview-windows-forms.md)
- [레이블 컨트롤](label-control-windows-forms.md)
