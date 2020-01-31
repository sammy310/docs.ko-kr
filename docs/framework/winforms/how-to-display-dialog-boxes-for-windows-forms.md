---
title: '방법: 대화 상자 표시'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- Windows Forms, displaying
- Windows Forms dialog boxes [Windows Forms], displaying
- Windows Forms, calling one form from another
- dialog boxes [Windows Forms], displaying for Windows Forms
ms.assetid: aaac1b38-c651-495a-8d3d-5a9bfb32fee3
ms.openlocfilehash: dd04a06eaa0dd7583ef2f72edb4cffa99aaaa60c
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/24/2020
ms.locfileid: "76739466"
---
# <a name="how-to-display-dialog-boxes-for-windows-forms"></a>방법: Windows Forms 대화 상자 표시
응용 프로그램에서 다른 폼을 표시 하는 것과 같은 방법으로 대화 상자를 표시 합니다. 응용 프로그램이 실행 될 때 시작 폼이 자동으로 로드 됩니다. 응용 프로그램에 두 번째 폼 또는 대화 상자를 표시 하려면 로드 하 고 표시 하는 코드를 작성 합니다. 마찬가지로 폼 이나 대화 상자를 사라지게 하려면 코드를 작성 하 여 언로드하거나 숨깁니다.  
  
### <a name="to-display-a-dialog-box"></a>대화 상자를 표시 하려면  
  
1. 대화 상자를 여는 데 사용할 이벤트 처리기로 이동 합니다. 이는 메뉴 명령을 선택 하거나 단추를 클릭할 때 또는 다른 이벤트가 발생 하는 경우에 발생할 수 있습니다.  
  
2. 이벤트 처리기에서 대화 상자를 여는 코드를 추가 합니다. 이 예제에서는 단추 클릭 이벤트를 사용 하 여 대화 상자를 표시 합니다.  
  
    ```vb  
    Private Sub Button1_Click(ByVal sender As System.Object, ByVal e As System.EventArgs) Handles Button1.Click  
       Dim dlg1 as new Form()  
       dlg1.ShowDialog()  
    End Sub  
    ```  
  
    ```csharp  
    private void button1_Click(object sender, System.EventArgs e)   
    {  
       Form dlg1 = new Form();  
       dlg1.ShowDialog();  
    }  
    ```  
  
    ```cpp  
    private:   
      void button1_Click(System::Object ^ sender,  
        System::EventArgs ^ e)  
      {  
        Form ^ dlg1 = gcnew Form();  
        dlg1->ShowDialog();  
      }  
    ```
