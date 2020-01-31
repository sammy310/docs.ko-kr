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
# <a name="how-to-display-dialog-boxes-for-windows-forms"></a><span data-ttu-id="d9d07-102">방법: Windows Forms 대화 상자 표시</span><span class="sxs-lookup"><span data-stu-id="d9d07-102">How to: Display Dialog Boxes for Windows Forms</span></span>
<span data-ttu-id="d9d07-103">응용 프로그램에서 다른 폼을 표시 하는 것과 같은 방법으로 대화 상자를 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="d9d07-103">You display a dialog box in the same way you display any other form in an application.</span></span> <span data-ttu-id="d9d07-104">응용 프로그램이 실행 될 때 시작 폼이 자동으로 로드 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d9d07-104">The startup form loads automatically when the application is run.</span></span> <span data-ttu-id="d9d07-105">응용 프로그램에 두 번째 폼 또는 대화 상자를 표시 하려면 로드 하 고 표시 하는 코드를 작성 합니다.</span><span class="sxs-lookup"><span data-stu-id="d9d07-105">To make a second form or dialog box appear in the application, write code to load and display it.</span></span> <span data-ttu-id="d9d07-106">마찬가지로 폼 이나 대화 상자를 사라지게 하려면 코드를 작성 하 여 언로드하거나 숨깁니다.</span><span class="sxs-lookup"><span data-stu-id="d9d07-106">Similarly, to make the form or dialog box disappear, write code to unload or hide it.</span></span>  
  
### <a name="to-display-a-dialog-box"></a><span data-ttu-id="d9d07-107">대화 상자를 표시 하려면</span><span class="sxs-lookup"><span data-stu-id="d9d07-107">To display a dialog box</span></span>  
  
1. <span data-ttu-id="d9d07-108">대화 상자를 여는 데 사용할 이벤트 처리기로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="d9d07-108">Navigate to the event handler with which you want to open the dialog box.</span></span> <span data-ttu-id="d9d07-109">이는 메뉴 명령을 선택 하거나 단추를 클릭할 때 또는 다른 이벤트가 발생 하는 경우에 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d9d07-109">This can happen when a menu command is selected, when a button is clicked, or when any other event occurs.</span></span>  
  
2. <span data-ttu-id="d9d07-110">이벤트 처리기에서 대화 상자를 여는 코드를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="d9d07-110">In the event handler, add code to open the dialog box.</span></span> <span data-ttu-id="d9d07-111">이 예제에서는 단추 클릭 이벤트를 사용 하 여 대화 상자를 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="d9d07-111">In this example, a button-click event is used to show the dialog box:</span></span>  
  
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
