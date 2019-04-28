---
title: '방법: Windows Forms FolderBrowserDialog 구성 요소를 사용하여 폴더 선택'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- directories [Windows Forms], choosing
- FolderBrowserDialog component [Windows Forms], choosing directories
- folders [Windows Forms], selecting
- folders [Windows Forms], choosing
- directories [Windows Forms], selecting
ms.assetid: 4593670e-7c7d-4661-b46b-4ffb63258adb
ms.openlocfilehash: 050af6d10faec3dd09998349dcf96e96ea0f9201
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61746927"
---
# <a name="how-to-choose-folders-with-the-windows-forms-folderbrowserdialog-component"></a>방법: Windows Forms FolderBrowserDialog 구성 요소를 사용하여 폴더 선택
종종 Windows 애플리케이션을 만드는 경우 파일 집합을 저장하기 위해 사용자에게 폴더를 선택하도록 요구하는 메시지를 매우 빈번하게 표시해야 합니다. Windows Forms <xref:System.Windows.Forms.FolderBrowserDialog> 구성 요소를 사용 하면 쉽게이 작업을 수행할 수 있습니다.  
  
### <a name="to-choose-folders-with-the-folderbrowserdialog-component"></a>Windows Forms FolderBrowserDialog 구성 요소를 사용하여 폴더를 선택하려면  
  
1. 프로시저에서 확인 합니다 <xref:System.Windows.Forms.FolderBrowserDialog> 구성 요소의 <xref:System.Windows.Forms.Form.DialogResult%2A> 속성을 대화 상자를 닫은 방법을 참조 하 고 값을 가져옵니다 합니다 <xref:System.Windows.Forms.FolderBrowserDialog> 구성 요소의 <xref:System.Windows.Forms.FolderBrowserDialog.SelectedPath%2A> 속성입니다.  
  
2. 대화 상자의 트리 보기에서 표시 되는 집합 최상위 폴더를 해야 하는 경우 설정 합니다 <xref:System.Windows.Forms.FolderBrowserDialog.RootFolder%2A> 의 멤버를 사용 하는 속성을 <xref:System.Environment.SpecialFolder> 열거형입니다.  
  
3. 또한 설정할 수는 <xref:System.Windows.Forms.FolderBrowserDialog.Description%2A> 폴더 브라우저 트리 보기의 맨 위에 표시 되는 텍스트 문자열을 지정 하는 속성입니다.  
  
     아래 예제에서는 <xref:System.Windows.Forms.FolderBrowserDialog> 구성 요소를 사용 하 때 Visual Studio에서 프로젝트를 만들에 저장할 폴더를 선택 하 라는 메시지가 표시 되는 폴더를 선택 합니다. 이 예제에서는 폴더 이름을 그러면에 표시 됩니다는 <xref:System.Windows.Forms.TextBox> 폼에서 컨트롤입니다. 편집 가능한 영역을 같은 위치를 배치 하는 것이 좋습니다는 <xref:System.Windows.Forms.TextBox> 컨트롤을 사용자 오류 또는 다른 문제가 발생할 경우 해당 선택을 편집할 수 있도록 합니다. 이 예에서는 가정 된 폼을 <xref:System.Windows.Forms.FolderBrowserDialog> 구성 요소 및 <xref:System.Windows.Forms.TextBox> 제어 합니다.  
  
    ```vb  
    Public Sub ChooseFolder()  
        If FolderBrowserDialog1.ShowDialog() = DialogResult.OK Then  
            TextBox1.Text = FolderBrowserDialog1.SelectedPath  
        End If  
    End Sub  
    ```  
  
    ```csharp  
    public void ChooseFolder()  
    {  
        if (folderBrowserDialog1.ShowDialog() == DialogResult.OK)   
        {  
            textBox1.Text = folderBrowserDialog1.SelectedPath;  
        }  
    }  
    ```  
  
    ```cpp  
    public:  
       void ChooseFolder()  
       {  
          if (folderBrowserDialog1->ShowDialog() == DialogResult::OK)  
          {  
             textBox1->Text = folderBrowserDialog1->SelectedPath;  
          }  
       }  
    ```  
  
    > [!IMPORTANT]
    >  이 클래스를 사용 하려면 어셈블리 권한 수준에서 부여한 필요 합니다 <xref:System.Security.Permissions.FileIOPermissionAttribute.PathDiscovery%2A> 일부인 속성의는 <xref:System.Security.Permissions.FileIOPermissionAccess> 열거형입니다. 부분 신뢰 컨텍스트에서 실행하는 경우 프로세스가 권한 부족으로 인해 예외를 throw할 수 있습니다. 자세한 내용은 [코드 액세스 보안 기본 사항](../../misc/code-access-security-basics.md)을 참조하세요.  
  
 파일을 저장 하는 방법에 대 한 자세한 내용은 [방법: SaveFileDialog 구성 요소를 사용 하 여 파일 저장](how-to-save-files-using-the-savefiledialog-component.md)합니다.  
  
## <a name="see-also"></a>참고자료

- <xref:System.Windows.Forms.FolderBrowserDialog>
- [FolderBrowserDialog 구성 요소 개요(Windows Forms)](folderbrowserdialog-component-overview-windows-forms.md)
- [FolderBrowserDialog 구성 요소](folderbrowserdialog-component-windows-forms.md)
