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
ms.openlocfilehash: 3625080c7c322e297a9de92e4f95a40c0caf3e72
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79181969"
---
# <a name="how-to-display-dialog-boxes-for-windows-forms"></a>방법: Windows Forms 대화 상자 표시
응용 프로그램에 다른 양식을 표시하는 것과 동일한 방식으로 대화 상자를 표시합니다. 시작 양식은 응용 프로그램을 실행할 때 자동으로 로드됩니다. 응용 프로그램에 두 번째 양식 또는 대화 상자를 표시하려면 코드를 작성하여 로드하고 표시합니다. 마찬가지로 양식이나 대화 상자를 사라지게 하려면 코드를 작성하여 언로드하거나 숨깁니다.  
  
### <a name="to-display-a-dialog-box"></a>대화 상자를 표시하려면  
  
1. 대화 상자를 열려는 이벤트 처리기로 이동합니다. 메뉴 명령을 선택하거나 단추를 클릭할 때 또는 다른 이벤트가 발생할 때 발생할 수 있습니다.  
  
2. 이벤트 처리기에서 코드를 추가하여 대화 상자를 엽니다. 이 예제에서는 단추 클릭 이벤트가 대화 상자를 표시하는 데 사용됩니다.  
  
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
