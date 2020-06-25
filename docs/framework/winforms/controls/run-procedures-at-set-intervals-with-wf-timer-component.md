---
title: Timer 구성 요소를 사용 하 여 설정 된 간격 마다 프로시저 실행
description: Windows Form Timer 구성 요소를 사용 하 여 설정 된 간격으로 또는 설정 된 시간 간격이 경과할 때 프로시저를 실행 하는 방법을 알아봅니다.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- examples [Windows Forms], timers
- timers [Windows Forms], event intervals
- initialization [Windows Forms], Timer components
- timers [Windows Forms], Windows-based
- Timer component [Windows Forms], initializing
- procedures [Windows Forms], specific time intervals
ms.assetid: 8025247a-2de4-4d86-b8ab-a8cb8aeab2ea
ms.openlocfilehash: 6847819fcec98d01d38b8e44604a259f06be7c02
ms.sourcegitcommit: dc2feef0794cf41dbac1451a13b8183258566c0e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/24/2020
ms.locfileid: "85325767"
---
# <a name="how-to-run-procedures-at-set-intervals-with-the-windows-forms-timer-component"></a><span data-ttu-id="b288f-103">방법: Windows Forms Timer 구성 요소를 사용하여 설정된 간격으로 프로시저 실행</span><span class="sxs-lookup"><span data-stu-id="b288f-103">How to: Run Procedures at Set Intervals with the Windows Forms Timer Component</span></span>
<span data-ttu-id="b288f-104">루프가 완료될 때까지 특정 시간 간격으로 실행되거나 설정된 시간 간격이 경과할 때 실행되는 프로시저를 만들려는 경우도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b288f-104">You might sometimes want to create a procedure that runs at specific time intervals until a loop has finished or that runs when a set time interval has elapsed.</span></span> <span data-ttu-id="b288f-105"><xref:System.Windows.Forms.Timer> 구성 요소는 이러한 프로시저를 가능하게 합니다.</span><span class="sxs-lookup"><span data-stu-id="b288f-105">The <xref:System.Windows.Forms.Timer> component makes such a procedure possible.</span></span>  
  
 <span data-ttu-id="b288f-106">이 구성 요소는 Windows Forms 환경에 맞게 설계되었습니다.</span><span class="sxs-lookup"><span data-stu-id="b288f-106">This component is designed for a Windows Forms environment.</span></span> <span data-ttu-id="b288f-107">서버 환경에 적합한 타이머가 필요한 경우 [서버 기반 타이머 소개](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/tb9yt5e6(v=vs.90))를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="b288f-107">If you need a timer that is suitable for a server environment, see [Introduction to Server-Based Timers](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/tb9yt5e6(v=vs.90)).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="b288f-108"><xref:System.Windows.Forms.Timer> 구성 요소를 사용하는 경우 몇 가지 제한 사항이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b288f-108">There are some limitations when using the <xref:System.Windows.Forms.Timer> component.</span></span> <span data-ttu-id="b288f-109">자세한 내용은 [Windows Forms Timer Component의 Interval 속성의 제한 사항](limitations-of-the-timer-component-interval-property.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="b288f-109">For more information, see [Limitations of the Windows Forms Timer Component's Interval Property](limitations-of-the-timer-component-interval-property.md).</span></span>  
  
## <a name="to-run-a-procedure-at-set-intervals-with-the-timer-component"></a><span data-ttu-id="b288f-110">Timer 구성 요소를 사용하여 설정된 간격마다 프로시저를 실행하려면</span><span class="sxs-lookup"><span data-stu-id="b288f-110">To run a procedure at set intervals with the Timer component</span></span>  
  
1. <span data-ttu-id="b288f-111">폼에 <xref:System.Windows.Forms.Timer>를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="b288f-111">Add a <xref:System.Windows.Forms.Timer> to your form.</span></span> <span data-ttu-id="b288f-112">이 작업을 프로그래밍 방식으로 수행하는 방법은 다음 예제 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="b288f-112">See the following Example section for an illustration of how to do this programmatically.</span></span> <span data-ttu-id="b288f-113">또한 Visual Studio는 폼에 구성 요소를 추가할 수 있도록 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="b288f-113">Visual Studio also has support for adding components to a form.</span></span> <span data-ttu-id="b288f-114">또한 [방법: Windows Forms 사용자 인터페이스 없이 컨트롤 추가](how-to-add-controls-without-a-user-interface-to-windows-forms.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="b288f-114">Also see [How to: Add Controls Without a User Interface to Windows Forms](how-to-add-controls-without-a-user-interface-to-windows-forms.md).</span></span>  
  
2. <span data-ttu-id="b288f-115">타이머에 대한 <xref:System.Windows.Forms.Timer.Interval%2A> 속성(밀리초)을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="b288f-115">Set the <xref:System.Windows.Forms.Timer.Interval%2A> property (in milliseconds) for the timer.</span></span> <span data-ttu-id="b288f-116">이 속성은 프로시저가 다시 실행되기까지 남은 시간을 결정합니다.</span><span class="sxs-lookup"><span data-stu-id="b288f-116">This property determines how much time will pass before the procedure is run again.</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="b288f-117">타이머 이벤트가 자주 발생할수록 이벤트에 응답하는 데 더 많은 프로세서 시간이 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="b288f-117">The more often a timer event occurs, the more processor time is used in responding to the event.</span></span> <span data-ttu-id="b288f-118">이 경우 전반적인 성능이 느려질 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b288f-118">This can slow down overall performance.</span></span> <span data-ttu-id="b288f-119">필요 이상으로 작은 간격을 설정하지 마세요.</span><span class="sxs-lookup"><span data-stu-id="b288f-119">Do not set a smaller interval than you need.</span></span>  
  
3. <span data-ttu-id="b288f-120"><xref:System.Windows.Forms.Timer.Tick> 이벤트 처리기에서 적절한 코드를 작성합니다.</span><span class="sxs-lookup"><span data-stu-id="b288f-120">Write appropriate code in the <xref:System.Windows.Forms.Timer.Tick> event handler.</span></span> <span data-ttu-id="b288f-121">이 이벤트에서 작성하는 코드는 <xref:System.Windows.Forms.Timer.Interval%2A> 속성에 지정된 간격마다 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="b288f-121">The code you write in this event will run at the interval specified in the <xref:System.Windows.Forms.Timer.Interval%2A> property.</span></span>  
  
4. <span data-ttu-id="b288f-122"><xref:System.Windows.Forms.Timer.Enabled%2A> 속성을 `true`로 설정하여 타이머를 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="b288f-122">Set the <xref:System.Windows.Forms.Timer.Enabled%2A> property to `true` to start the timer.</span></span> <span data-ttu-id="b288f-123"><xref:System.Windows.Forms.Timer.Tick> 이벤트 발생이 시작되고 설정된 간격마다 프로시저를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="b288f-123">The <xref:System.Windows.Forms.Timer.Tick> event will begin to occur, running your procedure at the set interval.</span></span>  
  
5. <span data-ttu-id="b288f-124">적절한 시간에 <xref:System.Windows.Forms.Timer.Enabled%2A> 속성을 `false`로 설정하여 프로시저가 다시 실행되지 않도록 중지합니다.</span><span class="sxs-lookup"><span data-stu-id="b288f-124">At the appropriate time, set the <xref:System.Windows.Forms.Timer.Enabled%2A> property to `false` to stop the procedure from running again.</span></span> <span data-ttu-id="b288f-125">간격을로 설정 하면 `0` 타이머가 중지 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b288f-125">Setting the interval to `0` does not cause the timer to stop.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b288f-126">예제</span><span class="sxs-lookup"><span data-stu-id="b288f-126">Example</span></span>  
 <span data-ttu-id="b288f-127">이 첫 번째 코드 예제에서는 1초 증분으로 시간을 추적합니다.</span><span class="sxs-lookup"><span data-stu-id="b288f-127">This first code example tracks the time of day in one-second increments.</span></span> <span data-ttu-id="b288f-128">폼의 <xref:System.Windows.Forms.Button>, <xref:System.Windows.Forms.Label> 및 <xref:System.Windows.Forms.Timer> 구성 요소를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="b288f-128">It uses a <xref:System.Windows.Forms.Button>, a <xref:System.Windows.Forms.Label>, and a <xref:System.Windows.Forms.Timer> component on a form.</span></span> <span data-ttu-id="b288f-129"><xref:System.Windows.Forms.Timer.Interval%2A> 속성은 1000(1초와 같음)으로 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="b288f-129">The <xref:System.Windows.Forms.Timer.Interval%2A> property is set to 1000 (equal to one second).</span></span> <span data-ttu-id="b288f-130"><xref:System.Windows.Forms.Timer.Tick> 이벤트에서 레이블의 캡션은 현재 시간으로 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="b288f-130">In the <xref:System.Windows.Forms.Timer.Tick> event, the label's caption is set to the current time.</span></span> <span data-ttu-id="b288f-131">단추를 클릭하면 <xref:System.Windows.Forms.Timer.Enabled%2A> 속성이 `false`로 설정되어 타이머가 레이블 캡션 업데이트를 중지합니다.</span><span class="sxs-lookup"><span data-stu-id="b288f-131">When the button is clicked, the <xref:System.Windows.Forms.Timer.Enabled%2A> property is set to `false`, stopping the timer from updating the label's caption.</span></span> <span data-ttu-id="b288f-132">다음 코드 예제를 사용 하려면 <xref:System.Windows.Forms.Button> 라는 컨트롤, 이라는 컨트롤 `Button1` <xref:System.Windows.Forms.Timer> `Timer1` 및 <xref:System.Windows.Forms.Label> 이라는 `Label1` 컨트롤이 있는 폼이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b288f-132">The following code example requires that you have a form with a <xref:System.Windows.Forms.Button> control named `Button1`, a <xref:System.Windows.Forms.Timer> control named `Timer1`, and a <xref:System.Windows.Forms.Label> control named `Label1`.</span></span>  
  
```vb  
Private Sub InitializeTimer()  
   ' Run this procedure in an appropriate event.  
   ' Set to 1 second.  
   Timer1.Interval = 1000  
   ' Enable timer.  
   Timer1.Enabled = True  
   Button1.Text = "Enabled"  
End Sub  
x  
Private Sub Timer1_Tick(ByVal Sender As Object, ByVal e As EventArgs) Handles Timer1.Tick  
' Set the caption to the current time.  
   Label1.Text = DateTime.Now  
End Sub  
  
Private Sub Button1_Click(ByVal sender As System.Object, ByVal e As System.EventArgs) Handles Button1.Click  
      If Button1.Text = "Stop" Then  
         Button1.Text = "Start"  
         Timer1.Enabled = False  
      Else  
         Button1.Text = "Stop"  
         Timer1.Enabled = True  
      End If  
End Sub  
```  
  
```csharp  
private void InitializeTimer()  
{  
    // Call this procedure when the application starts.  
    // Set to 1 second.  
    Timer1.Interval = 1000;  
    Timer1.Tick += new EventHandler(Timer1_Tick);  
  
    // Enable timer.  
    Timer1.Enabled = true;  
  
    Button1.Text = "Stop";  
    Button1.Click += new EventHandler(Button1_Click);  
}  
  
private void Timer1_Tick(object Sender, EventArgs e)
{  
   // Set the caption to the current time.  
   Label1.Text = DateTime.Now.ToString();  
}  
  
private void Button1_Click(object sender, EventArgs e)  
{  
  if ( Button1.Text == "Stop" )  
  {  
    Button1.Text = "Start";  
    Timer1.Enabled = false;  
  }  
  else  
  {  
    Button1.Text = "Stop";  
    Timer1.Enabled = true;  
  }  
}  
```  
  
```cpp  
private:  
   void InitializeTimer()  
   {  
      // Run this procedure in an appropriate event.  
      // Set to 1 second.  
      timer1->Interval = 1000;  
      // Enable timer.  
      timer1->Enabled = true;  
      this->timer1->Tick += gcnew System::EventHandler(this,
                               &Form1::timer1_Tick);  
  
      button1->Text = S"Stop";  
      this->button1->Click += gcnew System::EventHandler(this,
                               &Form1::button1_Click);  
   }  
  
   void timer1_Tick(System::Object ^ sender,  
      System::EventArgs ^ e)  
   {  
      // Set the caption to the current time.  
      label1->Text = DateTime::Now.ToString();  
   }  
  
   void button1_Click(System::Object ^ sender,  
      System::EventArgs ^ e)  
   {  
      if ( button1->Text == "Stop" )  
      {  
         button1->Text = "Start";  
         timer1->Enabled = false;  
      }  
      else  
      {  
         button1->Text = "Stop";  
         timer1->Enabled = true;  
      }  
   }  
```  
  
## <a name="example"></a><span data-ttu-id="b288f-133">예제</span><span class="sxs-lookup"><span data-stu-id="b288f-133">Example</span></span>  
 <span data-ttu-id="b288f-134">이 두 번째 코드 예제는 루프가 완료될 때까지 600밀리초마다 프로시저를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="b288f-134">This second code example runs a procedure every 600 milliseconds until a loop has finished.</span></span> <span data-ttu-id="b288f-135">다음 코드 예제를 사용 하려면 <xref:System.Windows.Forms.Button> 라는 컨트롤, 이라는 컨트롤 `Button1` <xref:System.Windows.Forms.Timer> `Timer1` 및 <xref:System.Windows.Forms.Label> 이라는 `Label1` 컨트롤이 있는 폼이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b288f-135">The following code example requires that you have a form with a <xref:System.Windows.Forms.Button> control named `Button1`, a <xref:System.Windows.Forms.Timer> control named `Timer1`, and a <xref:System.Windows.Forms.Label> control named `Label1`.</span></span>  
  
```vb  
' This variable will be the loop counter.  
Private counter As Integer  
  
Private Sub InitializeTimer()  
   ' Run this procedure in an appropriate event.  
   counter = 0  
   Timer1.Interval = 600  
   Timer1.Enabled = True  
End Sub  
  
Private Sub Timer1_Tick(ByVal sender As Object, ByVal e As System.EventArgs) Handles Timer1.Tick  
   If counter => 10 Then  
      ' Exit loop code.  
      Timer1.Enabled = False  
      counter = 0  
   Else  
      ' Run your procedure here.  
      ' Increment counter.  
      counter = counter + 1  
      Label1.Text = "Procedures Run: " & counter.ToString  
   End If  
End Sub  
```  
  
```csharp  
// This variable will be the loop counter.  
private int counter;  
  
private void InitializeTimer()  
{  
   // Run this procedure in an appropriate event.  
   counter = 0;  
   timer1.Interval = 600;  
   timer1.Enabled = true;  
   // Hook up timer's tick event handler.  
   this.timer1.Tick += new System.EventHandler(this.timer1_Tick);  
}  
  
private void timer1_Tick(object sender, System.EventArgs e)
{  
   if (counter >= 10)
   {  
      // Exit loop code.  
      timer1.Enabled = false;  
      counter = 0;  
   }  
   else  
   {  
      // Run your procedure here.  
      // Increment counter.  
      counter = counter + 1;  
      label1.Text = "Procedures Run: " + counter.ToString();  
      }  
}  
```  
  
```cpp  
private:  
   int counter;  
  
   void InitializeTimer()  
   {  
      // Run this procedure in an appropriate event.  
      counter = 0;  
      timer1->Interval = 600;  
      timer1->Enabled = true;  
      // Hook up timer's tick event handler.  
      this->timer1->Tick += gcnew System::EventHandler(this, &Form1::timer1_Tick);  
   }  
  
   void timer1_Tick(System::Object ^ sender,  
      System::EventArgs ^ e)  
   {  
      if (counter >= 10)
      {  
         // Exit loop code.  
         timer1->Enabled = false;  
         counter = 0;  
      }  
      else  
      {  
         // Run your procedure here.  
         // Increment counter.  
         counter = counter + 1;  
         label1->Text = String::Concat("Procedures Run: ",  
            counter.ToString());  
      }  
   }  
```  
  
## <a name="see-also"></a><span data-ttu-id="b288f-136">참조</span><span class="sxs-lookup"><span data-stu-id="b288f-136">See also</span></span>

- <xref:System.Windows.Forms.Timer>
- [<span data-ttu-id="b288f-137">Timer 구성 요소</span><span class="sxs-lookup"><span data-stu-id="b288f-137">Timer Component</span></span>](timer-component-windows-forms.md)
- [<span data-ttu-id="b288f-138">Timer 구성 요소 개요</span><span class="sxs-lookup"><span data-stu-id="b288f-138">Timer Component Overview</span></span>](timer-component-overview-windows-forms.md)
