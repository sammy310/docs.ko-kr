---
title: 진행률 표시줄 컨트롤에 의해 표시되는 값 설정
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ProgressBar control [Windows Forms], setting value displayed
- progress controls [Windows Forms], setting value displayed
ms.assetid: 0e5010ad-1e9a-4271-895e-5a3d24d37a26
ms.openlocfilehash: d295079a96ca19a4e4c98e113a3f3051c6403182
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79141813"
---
# <a name="how-to-set-the-value-displayed-by-the-windows-forms-progressbar-control"></a>방법: Windows Forms ProgressBar 컨트롤에서 표시하는 값 설정
> [!IMPORTANT]
> <xref:System.Windows.Forms.ToolStripProgressBar> 컨트롤은 <xref:System.Windows.Forms.ProgressBar> 컨트롤을 대체하고 여기에 다른 기능을 추가하여 새로 도입된 컨트롤이지만 이전 버전과의 호환성 및 이후 사용 가능성을 고려하여 <xref:System.Windows.Forms.ProgressBar> 컨트롤을 계속 유지하도록 선택할 수 있습니다.  
  
 .NET Framework에서는 <xref:System.Windows.Forms.ProgressBar> 컨트롤 내에 지정된 값을 표시하는 여러 가지 방법을 제공합니다. 어떤 방법을 선택하느냐는 현재 수행 중인 작업 또는 해결 중인 문제에 따라 달라집니다. 다음 표에서는 선택할 수 있는 방법을 보여 주며 있습니다.  
  
|접근 방식|Description|  
|--------------|-----------------|  
|<xref:System.Windows.Forms.ProgressBar> 컨트롤의 값을 직접 설정합니다.|이 방법은 데이터 원본에서 레코드를 읽는 것과 같이 관련된 항목의 합계를 아는 작업에 유용합니다. 또한 값을 한 두 번만 설정해야 하는 경우 이 작업을 쉽게 수행할 수 있습니다. 마지막으로 진행률 표시줄에 표시된 값을 줄여야 하는 경우 이 프로세스를 사용합니다.|  
|고정 <xref:System.Windows.Forms.ProgressBar> 값으로 표시를 늘립니다.|이 방법은 경과 시간 또는 알려진 총값에서 처리된 파일 수와 같이 최소 및 최대 사이의 간단한 개수를 표시하는 경우에 유용합니다.|  
|달라지는 <xref:System.Windows.Forms.ProgressBar> 값으로 디스플레이를 늘립니다.|이 방법은 표시된 값을 여러 번 다른 양으로 변경해야 하는 경우에 유용합니다. 예를 들어 일련의 파일을 디스크에 쓰는 동안 사용되는 하드 디스크 공간의 양을 보여 줄 수 있습니다.|  
  
 진행률 표시줄에 표시되는 값을 설정하는 가장 직접적인 <xref:System.Windows.Forms.ProgressBar.Value%2A> 방법은 속성을 설정하는 것입니다. 이 작업은 디자인 시 또는 런타임에 수행할 수 있습니다.  
  
### <a name="to-set-the-progressbar-value-directly"></a>ProgressBar 값을 직접 설정하려면  
  
1. <xref:System.Windows.Forms.ProgressBar> 컨트롤과 <xref:System.Windows.Forms.ProgressBar.Maximum%2A> 값을 <xref:System.Windows.Forms.ProgressBar.Minimum%2A> 설정합니다.  
  
2. 코드에서 컨트롤의 <xref:System.Windows.Forms.ProgressBar.Value%2A> 속성을 설정한 최소값과 최대값 사이의 정수 값으로 설정합니다.  
  
    > [!NOTE]
    > <xref:System.Windows.Forms.ProgressBar.Minimum%2A> 및 <xref:System.Windows.Forms.ProgressBar.Maximum%2A> <xref:System.ArgumentException> 속성에 <xref:System.Windows.Forms.ProgressBar.Value%2A> 의해 설정된 경계 외부에 속성을 설정하면 컨트롤이 예외를 throw합니다.  
  
     다음 코드 예제에서는 <xref:System.Windows.Forms.ProgressBar> 값을 직접 설정하는 방법을 보여 줍니다. 코드는 데이터 원본에서 레코드를 읽고 데이터 레코드를 읽을 때마다 진행률 표시줄과 레이블을 업데이트합니다. 이 예제에서는 폼에 <xref:System.Windows.Forms.Label> 컨트롤, <xref:System.Windows.Forms.ProgressBar> 컨트롤 및 와 `CustomerRow` `FirstName` `LastName` 필드라는 행이 있는 데이터 테이블이 있어야 합니다.  
  
    ```vb  
    Public Sub CreateNewRecords()  
       ' Sets the progress bar's Maximum property to  
       ' the total number of records to be created.  
       ProgressBar1.Maximum = 20  
  
       ' Creates a new record in the dataset.  
       ' NOTE: The code below will not compile, it merely  
       ' illustrates how the progress bar would be used.  
       Dim anyRow As CustomerRow = DatasetName.ExistingTable.NewRow  
       anyRow.FirstName = "Stephen"  
       anyRow.LastName = "James"  
       ExistingTable.Rows.Add(anyRow)  
  
       ' Increases the value displayed by the progress bar.  
       ProgressBar1.Value += 1  
       ' Updates the label to show that a record was read.  
       Label1.Text = "Records Read = " & ProgressBar1.Value.ToString()  
    End Sub  
    ```  
  
    ```csharp  
    public void createNewRecords()  
    {  
       // Sets the progress bar's Maximum property to  
       // the total number of records to be created.  
       progressBar1.Maximum = 20;  
  
       // Creates a new record in the dataset.  
       // NOTE: The code below will not compile, it merely  
       // illustrates how the progress bar would be used.  
       CustomerRow anyRow = DatasetName.ExistingTable.NewRow();  
       anyRow.FirstName = "Stephen";  
       anyRow.LastName = "James";  
       ExistingTable.Rows.Add(anyRow);  
  
       // Increases the value displayed by the progress bar.  
       progressBar1.Value += 1;  
       // Updates the label to show that a record was read.  
       label1.Text = "Records Read = " + progressBar1.Value.ToString();  
    }  
    ```  
  
     고정 된 간격으로 진행률을 표시하는 경우 값을 설정한 다음 해당 간격으로 <xref:System.Windows.Forms.ProgressBar> 컨트롤값을 늘리는 메서드를 호출할 수 있습니다. 이 기능은 전체의 백분율로 진행률을 측정하지 않는 타이머 및 기타 시나리오에 유용합니다.  
  
### <a name="to-increase-the-progress-bar-by-a-fixed-value"></a>고정값으로 진행률 표시줄을 늘리려면  
  
1. <xref:System.Windows.Forms.ProgressBar> 컨트롤과 <xref:System.Windows.Forms.ProgressBar.Maximum%2A> 값을 <xref:System.Windows.Forms.ProgressBar.Minimum%2A> 설정합니다.  
  
2. 진행률 표시줄의 <xref:System.Windows.Forms.ProgressBar.Step%2A> 표시된 값을 높이기 위해 양을 나타내는 정수로 컨트롤의 속성을 설정합니다.  
  
3. 메서드를 <xref:System.Windows.Forms.ProgressBar.PerformStep%2A> 호출하여 속성에 설정된 양으로 <xref:System.Windows.Forms.ProgressBar.Step%2A> 표시되는 값을 변경합니다.  
  
     다음 코드 예제에서는 진행률 표시줄이 복사 작업에서 파일 수를 유지하는 방법을 보여 줍니다.  
  
     다음 예제에서는 각 파일을 메모리로 읽을 때 진행률 표시줄과 레이블이 업데이트되어 읽은 총 파일을 반영합니다. 이 예제에서는 폼에 <xref:System.Windows.Forms.Label> 컨트롤과 <xref:System.Windows.Forms.ProgressBar> 컨트롤이 있어야 합니다.  
  
    ```vb  
    Public Sub LoadFiles()  
       ' Sets the progress bar's minimum value to a number representing  
       ' no operations complete -- in this case, no files read.  
       ProgressBar1.Minimum = 0  
       ' Sets the progress bar's maximum value to a number representing  
       ' all operations complete -- in this case, all five files read.  
       ProgressBar1.Maximum = 5  
       ' Sets the Step property to amount to increase with each iteration.  
       ' In this case, it will increase by one with every file read.  
       ProgressBar1.Step = 1  
  
       ' Dimensions a counter variable.  
       Dim i As Integer  
       ' Uses a For...Next loop to iterate through the operations to be  
       ' completed. In this case, five files are to be copied into memory,  
       ' so the loop will execute 5 times.  
       For i = 0 To 4  
          ' Insert code to copy a file  
          ProgressBar1.PerformStep()  
          ' Update the label to show that a file was read.  
          Label1.Text = "# of Files Read = " & ProgressBar1.Value.ToString  
       Next i  
    End Sub  
    ```  
  
    ```csharp  
    public void loadFiles()  
    {  
       // Sets the progress bar's minimum value to a number representing  
       // no operations complete -- in this case, no files read.  
       progressBar1.Minimum = 0;  
       // Sets the progress bar's maximum value to a number representing  
       // all operations complete -- in this case, all five files read.  
       progressBar1.Maximum = 5;  
       // Sets the Step property to amount to increase with each iteration.  
       // In this case, it will increase by one with every file read.  
       progressBar1.Step = 1;  
  
       // Uses a for loop to iterate through the operations to be  
       // completed. In this case, five files are to be copied into memory,  
       // so the loop will execute 5 times.  
       for (int i = 0; i <= 4; i++)  
       {  
          // Inserts code to copy a file  
          progressBar1.PerformStep();  
          // Updates the label to show that a file was read.  
          label1.Text = "# of Files Read = " + progressBar1.Value.ToString();  
       }  
    }  
    ```  
  
     마지막으로 각 증가액이 고유 금액이 되도록 진행률 표시줄에 표시되는 값을 늘릴 수 있습니다. 이 기능은 다양한 크기의 파일을 하드 디스크에 쓰거나 전체의 백분율로 진행률을 측정하는 등 일련의 고유한 작업을 추적하는 경우에 유용합니다.  
  
### <a name="to-increase-the-progress-bar-by-a-dynamic-value"></a>동적 값으로 진행률 표시줄을 늘리려면  
  
1. <xref:System.Windows.Forms.ProgressBar> 컨트롤과 <xref:System.Windows.Forms.ProgressBar.Maximum%2A> 값을 <xref:System.Windows.Forms.ProgressBar.Minimum%2A> 설정합니다.  
  
2. 메서드를 <xref:System.Windows.Forms.ProgressBar.Increment%2A> 호출하여 지정한 정수에 의해 표시되는 값을 변경합니다.  
  
     다음 코드 예제에서는 진행률 표시줄에서 복사 작업 중에 사용된 디스크 공간의 양을 계산하는 방법을 보여 줍니다.  
  
     다음 예제에서는 각 파일이 하드 디스크에 기록될 때 사용 가능한 하드 디스크 공간의 양을 반영하도록 진행률 표시줄과 레이블이 업데이트됩니다. 이 예제에서는 폼에 <xref:System.Windows.Forms.Label> 컨트롤과 <xref:System.Windows.Forms.ProgressBar> 컨트롤이 있어야 합니다.  
  
    ```vb  
    Public Sub ReadFiles()  
       ' Sets the progress bar's minimum value to a number
       ' representing the hard disk space before the files are read in.  
       ' You will most likely have to set this using a system call.  
       ' NOTE: The code below is meant to be an example and  
       ' will not compile.  
       ProgressBar1.Minimum = AvailableDiskSpace()  
       ' Sets the progress bar's maximum value to a number
       ' representing the total hard disk space.  
       ' You will most likely have to set this using a system call.  
       ' NOTE: The code below is meant to be an example
       ' and will not compile.  
       ProgressBar1.Maximum = TotalDiskSpace()  
  
       ' Dimension a counter variable.  
       Dim i As Integer  
       ' Uses a For...Next loop to iterate through the operations to be  
       ' completed. In this case, five files are to be written to the disk,  
       ' so it will execute the loop 5 times.  
       For i = 1 To 5  
          ' Insert code to read a file into memory and update file size.  
          ' Increases the progress bar's value based on the size of
          ' the file currently being written.  
          ProgressBar1.Increment(FileSize)  
          ' Updates the label to show available drive space.  
          Label1.Text = "Current Disk Space Used = " &_
          ProgressBar1.Value.ToString()  
       Next i  
    End Sub  
    ```  
  
    ```csharp  
    public void readFiles()  
    {  
       // Sets the progress bar's minimum value to a number
       // representing the hard disk space before the files are read in.  
       // You will most likely have to set this using a system call.  
       // NOTE: The code below is meant to be an example and
       // will not compile.  
       progressBar1.Minimum = AvailableDiskSpace();  
       // Sets the progress bar's maximum value to a number
       // representing the total hard disk space.  
       // You will most likely have to set this using a system call.  
       // NOTE: The code below is meant to be an example
       // and will not compile.  
       progressBar1.Maximum = TotalDiskSpace();  
  
       // Uses a for loop to iterate through the operations to be  
       // completed. In this case, five files are to be written  
       // to the disk, so it will execute the loop 5 times.  
       for (int i = 1; i<= 5; i++)  
       {  
          // Insert code to read a file into memory and update file size.  
          // Increases the progress bar's value based on the size of
          // the file currently being written.  
          progressBar1.Increment(FileSize);  
          // Updates the label to show available drive space.  
          label1.Text = "Current Disk Space Used = " + progressBar1.Value.ToString();  
       }  
    }  
    ```  
  
## <a name="see-also"></a>참고 항목

- <xref:System.Windows.Forms.ProgressBar>
- <xref:System.Windows.Forms.ToolStripProgressBar>
- [ProgressBar 컨트롤 개요](progressbar-control-overview-windows-forms.md)
- [ProgressBar 컨트롤](progressbar-control-windows-forms.md)
