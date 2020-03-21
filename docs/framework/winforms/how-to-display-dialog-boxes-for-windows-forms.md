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
# <a name="how-to-display-dialog-boxes-for-windows-forms"></a><span data-ttu-id="941f9-102">방법: Windows Forms 대화 상자 표시</span><span class="sxs-lookup"><span data-stu-id="941f9-102">How to: Display Dialog Boxes for Windows Forms</span></span>
<span data-ttu-id="941f9-103">응용 프로그램에 다른 양식을 표시하는 것과 동일한 방식으로 대화 상자를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="941f9-103">You display a dialog box in the same way you display any other form in an application.</span></span> <span data-ttu-id="941f9-104">시작 양식은 응용 프로그램을 실행할 때 자동으로 로드됩니다.</span><span class="sxs-lookup"><span data-stu-id="941f9-104">The startup form loads automatically when the application is run.</span></span> <span data-ttu-id="941f9-105">응용 프로그램에 두 번째 양식 또는 대화 상자를 표시하려면 코드를 작성하여 로드하고 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="941f9-105">To make a second form or dialog box appear in the application, write code to load and display it.</span></span> <span data-ttu-id="941f9-106">마찬가지로 양식이나 대화 상자를 사라지게 하려면 코드를 작성하여 언로드하거나 숨깁니다.</span><span class="sxs-lookup"><span data-stu-id="941f9-106">Similarly, to make the form or dialog box disappear, write code to unload or hide it.</span></span>  
  
### <a name="to-display-a-dialog-box"></a><span data-ttu-id="941f9-107">대화 상자를 표시하려면</span><span class="sxs-lookup"><span data-stu-id="941f9-107">To display a dialog box</span></span>  
  
1. <span data-ttu-id="941f9-108">대화 상자를 열려는 이벤트 처리기로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="941f9-108">Navigate to the event handler with which you want to open the dialog box.</span></span> <span data-ttu-id="941f9-109">메뉴 명령을 선택하거나 단추를 클릭할 때 또는 다른 이벤트가 발생할 때 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="941f9-109">This can happen when a menu command is selected, when a button is clicked, or when any other event occurs.</span></span>  
  
2. <span data-ttu-id="941f9-110">이벤트 처리기에서 코드를 추가하여 대화 상자를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="941f9-110">In the event handler, add code to open the dialog box.</span></span> <span data-ttu-id="941f9-111">이 예제에서는 단추 클릭 이벤트가 대화 상자를 표시하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="941f9-111">In this example, a button-click event is used to show the dialog box:</span></span>  
  
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
