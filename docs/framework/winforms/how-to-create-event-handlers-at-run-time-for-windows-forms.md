---
title: '방법: 런타임에 이벤트 처리기 만들기'
description: Visual Studio에서 Windows Forms 디자이너를 사용 하 여 런타임에 이벤트 처리기를 만드는 방법을 알아봅니다. 이 작업을 통해 런타임에 이벤트 처리기를 연결할 수 있습니다.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- Windows Forms, event handling
- event handlers [Windows Forms], creating
- run time [Windows Forms], creating event handlers at
- examples [Windows Forms], event handling
- Button control [Windows Forms], event handlers
ms.assetid: 2e7c9e1a-61fe-444d-8113-3c5bacf1c8cb
ms.openlocfilehash: 857076c46377b3276154d9b193d4bbe51841828f
ms.sourcegitcommit: dc2feef0794cf41dbac1451a13b8183258566c0e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/24/2020
ms.locfileid: "85325810"
---
# <a name="how-to-create-event-handlers-at-run-time-for-windows-forms"></a><span data-ttu-id="3b3c4-104">방법: 런타임 시 Windows Forms의 이벤트 처리기 만들기</span><span class="sxs-lookup"><span data-stu-id="3b3c4-104">How to: Create Event Handlers at Run Time for Windows Forms</span></span>

<span data-ttu-id="3b3c4-105">Visual Studio에서 Windows Forms 디자이너 사용 하 여 이벤트를 만드는 것 외에도 런타임에 이벤트 처리기를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3b3c4-105">In addition to creating events using the Windows Forms Designer in Visual Studio, you can also create an event handler at run time.</span></span> <span data-ttu-id="3b3c4-106">이렇게 하면 프로그램이 처음 시작될 때 이벤트 처리기를 연결하는 대신 런타임에 코드를 사용하여 조건에 따라 이벤트 처리기를 연결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3b3c4-106">This action allows you to connect event handlers based on conditions in code at run time as opposed to having them connected when the program initially starts.</span></span>

## <a name="create-an-event-handler-at-run-time"></a><span data-ttu-id="3b3c4-107">런타임에 이벤트 처리기 만들기</span><span class="sxs-lookup"><span data-stu-id="3b3c4-107">Create an event handler at run time</span></span>

1. <span data-ttu-id="3b3c4-108">이벤트 처리기를 추가 하려는 폼을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="3b3c4-108">Open the form that you want to add an event handler to.</span></span>

2. <span data-ttu-id="3b3c4-109">처리할 이벤트의 메서드 시그니처가 있는 양식에 메서드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="3b3c4-109">Add a method to your form with the method signature for the event that you want to handle.</span></span>

     <span data-ttu-id="3b3c4-110">예를 들어, 컨트롤의 이벤트를 처리 하는 경우 <xref:System.Windows.Forms.Control.Click> <xref:System.Windows.Forms.Button> 다음과 같은 메서드를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="3b3c4-110">For example, if you were handling the <xref:System.Windows.Forms.Control.Click> event of a <xref:System.Windows.Forms.Button> control, you would create a method such as the following:</span></span>

    ```vb
    Private Sub Button1_Click(ByVal sender As Object, ByVal e As EventArgs)
       ' Add event handler code here.
    End Sub
    ```

    ```csharp
    private void button1_Click(object sender, System.EventArgs e)
    {
    // Add event handler code here.
    }
    ```

    ```cpp
    private:
       void button1_Click(System::Object ^ sender,
          System::EventArgs ^ e)
       {
          // Add event handler code here.
       }
    ```

3. <span data-ttu-id="3b3c4-111">애플리케이션에 적합한 코드를 이벤트 처리기에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="3b3c4-111">Add code to the event handler as appropriate to your application.</span></span>

4. <span data-ttu-id="3b3c4-112">이벤트 처리기를 만들 양식 또는 컨트롤을 결정합니다.</span><span class="sxs-lookup"><span data-stu-id="3b3c4-112">Determine which form or control you want to create an event handler for.</span></span>

5. <span data-ttu-id="3b3c4-113">양식의 클래스에 있는 메서드에 이벤트를 처리할 이벤트 처리기를 지정하는 코드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="3b3c4-113">In a method within your form's class, add code that specifies the event handler to handle the event.</span></span> <span data-ttu-id="3b3c4-114">예를 들어 다음 코드는 이벤트 처리기가 `button1_Click` <xref:System.Windows.Forms.Control.Click> 컨트롤의 이벤트를 처리 하도록 지정 합니다 <xref:System.Windows.Forms.Button> .</span><span class="sxs-lookup"><span data-stu-id="3b3c4-114">For example, the following code specifies the event handler `button1_Click` handles the <xref:System.Windows.Forms.Control.Click> event of a <xref:System.Windows.Forms.Button> control:</span></span>

    ```vb
    AddHandler Button1.Click, AddressOf Button1_Click
    ```

    ```csharp
    button1.Click += new EventHandler(button1_Click);
    ```

    ```cpp
    button1->Click += gcnew System::EventHandler(this, &Form1::button1_Click);
    ```

     <span data-ttu-id="3b3c4-115"><xref:System.ComponentModel.EventHandlerList.AddHandler%2A>위의 Visual Basic 코드에 설명 된 메서드는 단추에 대 한 click 이벤트 처리기를 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="3b3c4-115">The <xref:System.ComponentModel.EventHandlerList.AddHandler%2A> method demonstrated in the Visual Basic code above establishes a click event handler for the button.</span></span>

## <a name="see-also"></a><span data-ttu-id="3b3c4-116">참조</span><span class="sxs-lookup"><span data-stu-id="3b3c4-116">See also</span></span>

- [<span data-ttu-id="3b3c4-117">Windows Forms에서 이벤트 처리기 만들기</span><span class="sxs-lookup"><span data-stu-id="3b3c4-117">Creating Event Handlers in Windows Forms</span></span>](creating-event-handlers-in-windows-forms.md)
- [<span data-ttu-id="3b3c4-118">이벤트 처리기 개요</span><span class="sxs-lookup"><span data-stu-id="3b3c4-118">Event Handlers Overview</span></span>](event-handlers-overview-windows-forms.md)
- [<span data-ttu-id="3b3c4-119">Visual Basic에서 상속된 이벤트 처리기 관련 문제 해결</span><span class="sxs-lookup"><span data-stu-id="3b3c4-119">Troubleshooting Inherited Event Handlers in Visual Basic</span></span>](../../visual-basic/programming-guide/language-features/events/troubleshooting-inherited-event-handlers.md)
