---
title: 컨트롤에 스레드 안전 호출
ms.date: 02/19/2019
dev_langs:
- csharp
- vb
f1_keywords:
- EHInvalidOperation.WinForms.IllegalCrossThreadCall
helpviewer_keywords:
- thread safety [Windows Forms], calling controls [Windows Forms]
- calling controls [Windows Forms], thread safety [Windows Forms]
- CheckForIllegalCrossThreadCalls property [Windows Forms]
- Windows Forms controls [Windows Forms], multithreading
- BackgroundWorker class [Windows Forms], examples
- threading [Windows Forms], cross-thread calls
- controls [Windows Forms], multithreading
ms.assetid: 138f38b6-1099-4fd5-910c-390b41cbad35
ms.openlocfilehash: 365b1acb693b9ff2be603a3e659ed8d846a7696a
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79142006"
---
# <a name="how-to-make-thread-safe-calls-to-windows-forms-controls"></a>방법: Windows Forms 컨트롤에 스레드 안전 호출

멀티스레딩을 사용하면 Windows Forms 앱의 성능이 향상될 수 있지만 Windows Forms 컨트롤에 대한 액세스는 본질적으로 스레드에서 안전하지 않습니다. 멀티스레딩은 코드를 매우 심각하고 복잡한 버그에 노출시킬 수 있습니다. 컨트롤을 조작하는 두 개 이상의 스레드는 컨트롤을 일관되지 않은 상태로 만들 수 있으며 경합 조건, 교착 상태 및 정지 또는 중단으로 이어질 수 있습니다. 앱에서 다중 스레딩을 구현하는 경우 스레드 에서 안전한 방식으로 스레드 간 컨트롤을 호출해야 합니다. 자세한 내용은 [관리되는 스레딩 모범 사례를](../../../standard/threading/managed-threading-best-practices.md)참조하십시오.

해당 컨트롤을 만들지 않은 스레드에서 Windows Forms 컨트롤을 안전하게 호출하는 방법에는 두 가지가 있습니다. 메서드를 <xref:System.Windows.Forms.Control.Invoke%2A?displayProperty=fullName> 사용하여 주 스레드에서 만든 대리자를 호출할 수 있으며, 이 대리자는 컨트롤을 호출합니다. 또는 이벤트 기반 <xref:System.ComponentModel.BackgroundWorker?displayProperty=nameWithType>모델을 사용하여 백그라운드 스레드에서 수행된 작업을 결과 보고와 구분하는 을 구현할 수 있습니다.

## <a name="unsafe-cross-thread-calls"></a>안전하지 않은 스레드 간 호출

컨트롤을 만들지 않은 스레드에서 직접 컨트롤을 호출하는 것은 안전하지 않습니다. 다음 코드 코드 조각은 컨트롤에 대한 <xref:System.Windows.Forms.TextBox?displayProperty=nameWithType> 안전하지 않은 호출을 보여 줍니다. 이벤트 `Button1_Click` 처리기는 `WriteTextUnsafe` 주 스레드의 <xref:System.Windows.Forms.TextBox.Text%2A?displayProperty=nameWithType> 속성을 직접 설정하는 새 스레드를 만듭니다.

```csharp
private void Button1_Click(object sender, EventArgs e)
{
    thread2 = new Thread(new ThreadStart(WriteTextUnsafe));
    thread2.Start();
}
private void WriteTextUnsafe()
{
    textBox1.Text = "This text was set unsafely.";
}
```

```vb
Private Sub Button1_Click(ByVal sender As Object, e As EventArgs) Handles Button1.Click
    Thread2 = New Thread(New ThreadStart(AddressOf WriteTextUnsafe))
    Thread2.Start()
End Sub

Private Sub WriteTextUnsafe()
    TextBox1.Text = "This text was set unsafely."
End Sub
```

Visual Studio 디버거는 스레드 간 작업이 유효하지 않은 메시지와 함께 발생시켜 이러한 안전하지 않은 스레드 호출을 <xref:System.InvalidOperationException> 검색합니다. ** 생성된 스레드가 아닌 스레드에서 액세스한 ""를 제어합니다.** <xref:System.InvalidOperationException> Visual Studio 디버깅 중에 안전하지 않은 스레드 간 호출에 대해 항상 발생하며 앱 런타임에 발생할 수 있습니다. 문제를 해결해야 하지만 속성을 로 설정하여 예외를 <xref:System.Windows.Forms.Control.CheckForIllegalCrossThreadCalls%2A?displayProperty=nameWithType> 비활성화할 `false`수 있습니다.

## <a name="safe-cross-thread-calls"></a>안전한 스레드 간 호출

다음 코드 예제에서는 Windows Forms 컨트롤을 만들지 않은 스레드에서 Windows Forms 컨트롤을 안전하게 호출하는 두 가지 방법을 보여 줍니다.

1. 컨트롤을 호출 하는 주 스레드에서 대리자를 호출 하는 <xref:System.Windows.Forms.Control.Invoke%2A?displayProperty=fullName> 메서드입니다.
2. 이벤트 <xref:System.ComponentModel.BackgroundWorker?displayProperty=nameWithType> 기반 모델을 제공하는 구성 요소입니다.

두 예제 모두 백그라운드 스레드가 1초 동안 절전 모드로 이동하여 해당 스레드에서 수행중인 작업을 시뮬레이션합니다.

이러한 예제를 C# 또는 Visual Basic 명령줄에서 .NET Framework 앱으로 빌드하고 실행할 수 있습니다. 자세한 내용은 [csc.exe를 가진 명령줄 건물](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md) 또는 [명령줄에서 빌드(Visual Basic)를](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md)참조하십시오.

.NET Core 3.0부터 .NET Core 양식 * \<폴더 이름>.csproj* 프로젝트 파일이 있는 폴더에서 Windows .NET Core 앱으로 예제를 빌드하고 실행할 수도 있습니다.

## <a name="example-use-the-invoke-method-with-a-delegate"></a>예: 대리자를 사용하여 호출 메서드사용

다음 예제에서는 Windows Forms 컨트롤에 대한 스레드 안전 호출을 보장하기 위한 패턴을 보여 줍니다. 컨트롤의 <xref:System.Windows.Forms.Control.InvokeRequired%2A?displayProperty=fullName> 생성 스레드 ID를 호출 스레드 ID와 비교하는 속성을 쿼리합니다. 스레드 아이디가 동일한 경우 컨트롤을 직접 호출합니다. 스레드 ID가 다른 경우 주 <xref:System.Windows.Forms.Control.Invoke%2A?displayProperty=nameWithType> 스레드의 대리자를 사용하여 메서드를 호출하여 컨트롤을 실제로 호출합니다.

을 `SafeCallDelegate` 사용하면 <xref:System.Windows.Forms.TextBox> 컨트롤의 <xref:System.Windows.Forms.TextBox.Text%2A> 속성을 설정할 수 있습니다. 메서드는 `WriteTextSafe` 을 <xref:System.Windows.Forms.Control.InvokeRequired%2A>쿼리합니다. <xref:System.Windows.Forms.Control.InvokeRequired%2A> 반환하는 `true` `WriteTextSafe` 경우 `SafeCallDelegate` 메서드를 <xref:System.Windows.Forms.Control.Invoke%2A> 전달하여 컨트롤에 대한 실제 호출을 만듭니다. <xref:System.Windows.Forms.Control.InvokeRequired%2A> 반환하는 `false` `WriteTextSafe` 경우 <xref:System.Windows.Forms.TextBox.Text%2A?displayProperty=nameWithType> 직접 설정합니다. 이벤트 `Button1_Click` 처리기는 새 스레드를 `WriteTextSafe` 만들고 메서드를 실행합니다.

 [!code-csharp[ThreadSafeCalls#1](~/samples/snippets/winforms/thread-safe/example1/cs/Form1.cs)]
 [!code-vb[ThreadSafeCalls#1](~/samples/snippets/winforms/thread-safe/example1/vb/Form1.vb)]  

## <a name="example-use-a-backgroundworker-event-handler"></a>예: 백그라운드 워커 이벤트 처리기 사용

다중 스레딩을 구현하는 쉬운 <xref:System.ComponentModel.BackgroundWorker?displayProperty=nameWithType> 방법은 이벤트 기반 모델을 사용하는 구성 요소를 사용하는 것입니다. 백그라운드 스레드는 <xref:System.ComponentModel.BackgroundWorker.DoWork?displayProperty=nameWithType> 주 스레드와 상호 작용하지 않는 이벤트를 실행합니다. 주 스레드는 <xref:System.ComponentModel.BackgroundWorker.ProgressChanged?displayProperty=nameWithType> 및 <xref:System.ComponentModel.BackgroundWorker.RunWorkerCompleted?displayProperty=nameWithType> 이벤트 처리기를 실행하여 주 스레드의 컨트롤을 호출할 수 있습니다.

을 사용하여 <xref:System.ComponentModel.BackgroundWorker>스레드 안전 호출을 수행하려면 백그라운드 스레드에서 메서드를 만들어 작업을 <xref:System.ComponentModel.BackgroundWorker.DoWork> 수행하고 이벤트에 바인딩합니다. 기본 스레드에 다른 메서드를 만들어 백그라운드 작업의 결과를 보고하고 <xref:System.ComponentModel.BackgroundWorker.ProgressChanged> <xref:System.ComponentModel.BackgroundWorker.RunWorkerCompleted> 또는 이벤트에 바인딩합니다. 백그라운드 스레드를 시작하려면 를 호출합니다. <xref:System.ComponentModel.BackgroundWorker.RunWorkerAsync%2A?displayProperty=nameWithType>

이 예제에서는 <xref:System.ComponentModel.BackgroundWorker.RunWorkerCompleted> 이벤트 처리기를 <xref:System.Windows.Forms.TextBox> 사용하여 <xref:System.Windows.Forms.TextBox.Text%2A> 컨트롤의 속성을 설정합니다. <xref:System.ComponentModel.BackgroundWorker.ProgressChanged> 이벤트를 사용하는 예제는 을 <xref:System.ComponentModel.BackgroundWorker>참조하십시오.

 [!code-csharp[ThreadSafeCalls#2](~/samples/snippets/winforms/thread-safe/example2/cs/Form1.cs)]
 [!code-vb[ThreadSafeCalls#2](~/samples/snippets/winforms/thread-safe/example2/vb/Form1.vb)]  

## <a name="see-also"></a>참고 항목

- <xref:System.ComponentModel.BackgroundWorker>
- [방법: 백그라운드에서 작업 실행](how-to-run-an-operation-in-the-background.md)
- [방법: 백그라운드 작업을 사용하는 양식 구현](how-to-implement-a-form-that-uses-a-background-operation.md)
- [.NET 프레임워크를 통해 사용자 지정 Windows 양식 컨트롤 개발](developing-custom-windows-forms-controls.md)
