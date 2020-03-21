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
# <a name="how-to-set-the-value-displayed-by-the-windows-forms-progressbar-control"></a><span data-ttu-id="ce641-102">방법: Windows Forms ProgressBar 컨트롤에서 표시하는 값 설정</span><span class="sxs-lookup"><span data-stu-id="ce641-102">How to: Set the Value Displayed by the Windows Forms ProgressBar Control</span></span>
> [!IMPORTANT]
> <span data-ttu-id="ce641-103"><xref:System.Windows.Forms.ToolStripProgressBar> 컨트롤은 <xref:System.Windows.Forms.ProgressBar> 컨트롤을 대체하고 여기에 다른 기능을 추가하여 새로 도입된 컨트롤이지만 이전 버전과의 호환성 및 이후 사용 가능성을 고려하여 <xref:System.Windows.Forms.ProgressBar> 컨트롤을 계속 유지하도록 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ce641-103">The <xref:System.Windows.Forms.ToolStripProgressBar> control replaces and adds functionality to the <xref:System.Windows.Forms.ProgressBar> control; however, the <xref:System.Windows.Forms.ProgressBar> control is retained for both backward compatibility and future use, if you choose.</span></span>  
  
 <span data-ttu-id="ce641-104">.NET Framework에서는 <xref:System.Windows.Forms.ProgressBar> 컨트롤 내에 지정된 값을 표시하는 여러 가지 방법을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="ce641-104">The .NET Framework gives you several different ways to display a given value within the <xref:System.Windows.Forms.ProgressBar> control.</span></span> <span data-ttu-id="ce641-105">어떤 방법을 선택하느냐는 현재 수행 중인 작업 또는 해결 중인 문제에 따라 달라집니다.</span><span class="sxs-lookup"><span data-stu-id="ce641-105">Which approach you choose will depend on the task at hand or the problem you are solving.</span></span> <span data-ttu-id="ce641-106">다음 표에서는 선택할 수 있는 방법을 보여 주며 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ce641-106">The following table shows the approaches you can choose.</span></span>  
  
|<span data-ttu-id="ce641-107">접근 방식</span><span class="sxs-lookup"><span data-stu-id="ce641-107">Approach</span></span>|<span data-ttu-id="ce641-108">Description</span><span class="sxs-lookup"><span data-stu-id="ce641-108">Description</span></span>|  
|--------------|-----------------|  
|<span data-ttu-id="ce641-109"><xref:System.Windows.Forms.ProgressBar> 컨트롤의 값을 직접 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="ce641-109">Set the value of the <xref:System.Windows.Forms.ProgressBar> control directly.</span></span>|<span data-ttu-id="ce641-110">이 방법은 데이터 원본에서 레코드를 읽는 것과 같이 관련된 항목의 합계를 아는 작업에 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="ce641-110">This approach is useful for tasks where you know the total of the item measured that will be involved, such as reading records from a data source.</span></span> <span data-ttu-id="ce641-111">또한 값을 한 두 번만 설정해야 하는 경우 이 작업을 쉽게 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ce641-111">Additionally, if you only need to set the value once or twice, this is an easy way to do it.</span></span> <span data-ttu-id="ce641-112">마지막으로 진행률 표시줄에 표시된 값을 줄여야 하는 경우 이 프로세스를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="ce641-112">Finally, use this process if you need to decrease the value displayed by the progress bar.</span></span>|  
|<span data-ttu-id="ce641-113">고정 <xref:System.Windows.Forms.ProgressBar> 값으로 표시를 늘립니다.</span><span class="sxs-lookup"><span data-stu-id="ce641-113">Increase the <xref:System.Windows.Forms.ProgressBar> display by a fixed value.</span></span>|<span data-ttu-id="ce641-114">이 방법은 경과 시간 또는 알려진 총값에서 처리된 파일 수와 같이 최소 및 최대 사이의 간단한 개수를 표시하는 경우에 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="ce641-114">This approach is useful when you are displaying a simple count between the minimum and maximum, such as elapsed time or the number of files that have been processed out of a known total.</span></span>|  
|<span data-ttu-id="ce641-115">달라지는 <xref:System.Windows.Forms.ProgressBar> 값으로 디스플레이를 늘립니다.</span><span class="sxs-lookup"><span data-stu-id="ce641-115">Increase the <xref:System.Windows.Forms.ProgressBar> display by a value that varies.</span></span>|<span data-ttu-id="ce641-116">이 방법은 표시된 값을 여러 번 다른 양으로 변경해야 하는 경우에 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="ce641-116">This approach is useful when you need to change the displayed value a number of times in different amounts.</span></span> <span data-ttu-id="ce641-117">예를 들어 일련의 파일을 디스크에 쓰는 동안 사용되는 하드 디스크 공간의 양을 보여 줄 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ce641-117">An example would be showing the amount of hard-disk space being consumed while writing a series of files to the disk.</span></span>|  
  
 <span data-ttu-id="ce641-118">진행률 표시줄에 표시되는 값을 설정하는 가장 직접적인 <xref:System.Windows.Forms.ProgressBar.Value%2A> 방법은 속성을 설정하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="ce641-118">The most direct way to set the value displayed by a progress bar is by setting the <xref:System.Windows.Forms.ProgressBar.Value%2A> property.</span></span> <span data-ttu-id="ce641-119">이 작업은 디자인 시 또는 런타임에 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ce641-119">This can be done either at design time or at run time.</span></span>  
  
### <a name="to-set-the-progressbar-value-directly"></a><span data-ttu-id="ce641-120">ProgressBar 값을 직접 설정하려면</span><span class="sxs-lookup"><span data-stu-id="ce641-120">To set the ProgressBar value directly</span></span>  
  
1. <span data-ttu-id="ce641-121"><xref:System.Windows.Forms.ProgressBar> 컨트롤과 <xref:System.Windows.Forms.ProgressBar.Maximum%2A> 값을 <xref:System.Windows.Forms.ProgressBar.Minimum%2A> 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="ce641-121">Set the <xref:System.Windows.Forms.ProgressBar> control's <xref:System.Windows.Forms.ProgressBar.Minimum%2A> and <xref:System.Windows.Forms.ProgressBar.Maximum%2A> values.</span></span>  
  
2. <span data-ttu-id="ce641-122">코드에서 컨트롤의 <xref:System.Windows.Forms.ProgressBar.Value%2A> 속성을 설정한 최소값과 최대값 사이의 정수 값으로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="ce641-122">In code, set the control's <xref:System.Windows.Forms.ProgressBar.Value%2A> property to an integer value between the minimum and maximum values you have established.</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="ce641-123"><xref:System.Windows.Forms.ProgressBar.Minimum%2A> 및 <xref:System.Windows.Forms.ProgressBar.Maximum%2A> <xref:System.ArgumentException> 속성에 <xref:System.Windows.Forms.ProgressBar.Value%2A> 의해 설정된 경계 외부에 속성을 설정하면 컨트롤이 예외를 throw합니다.</span><span class="sxs-lookup"><span data-stu-id="ce641-123">If you set the <xref:System.Windows.Forms.ProgressBar.Value%2A> property outside the boundaries established by the <xref:System.Windows.Forms.ProgressBar.Minimum%2A> and <xref:System.Windows.Forms.ProgressBar.Maximum%2A> properties, the control throws an <xref:System.ArgumentException> exception.</span></span>  
  
     <span data-ttu-id="ce641-124">다음 코드 예제에서는 <xref:System.Windows.Forms.ProgressBar> 값을 직접 설정하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="ce641-124">The following code example illustrates how to set the <xref:System.Windows.Forms.ProgressBar> value directly.</span></span> <span data-ttu-id="ce641-125">코드는 데이터 원본에서 레코드를 읽고 데이터 레코드를 읽을 때마다 진행률 표시줄과 레이블을 업데이트합니다.</span><span class="sxs-lookup"><span data-stu-id="ce641-125">The code reads records from a data source and updates the progress bar and label every time a data record is read.</span></span> <span data-ttu-id="ce641-126">이 예제에서는 폼에 <xref:System.Windows.Forms.Label> 컨트롤, <xref:System.Windows.Forms.ProgressBar> 컨트롤 및 와 `CustomerRow` `FirstName` `LastName` 필드라는 행이 있는 데이터 테이블이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ce641-126">This example requires that your form has a <xref:System.Windows.Forms.Label> control, a <xref:System.Windows.Forms.ProgressBar> control, and a data table with a row called `CustomerRow` with `FirstName` and `LastName` fields.</span></span>  
  
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
  
     고정 된 간격으로 진행률을 표시하는 경우 값을 설정한 다음 해당 간격으로 <xref:System.Windows.Forms.ProgressBar> 컨트롤값을 늘리는 메서드를 호출할 수 있습니다. <span data-ttu-id="ce641-128">이 기능은 전체의 백분율로 진행률을 측정하지 않는 타이머 및 기타 시나리오에 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="ce641-128">This is useful for timers and other scenarios where you are not measuring progress as a percentage of the whole.</span></span>  
  
### <a name="to-increase-the-progress-bar-by-a-fixed-value"></a><span data-ttu-id="ce641-129">고정값으로 진행률 표시줄을 늘리려면</span><span class="sxs-lookup"><span data-stu-id="ce641-129">To increase the progress bar by a fixed value</span></span>  
  
1. <span data-ttu-id="ce641-130"><xref:System.Windows.Forms.ProgressBar> 컨트롤과 <xref:System.Windows.Forms.ProgressBar.Maximum%2A> 값을 <xref:System.Windows.Forms.ProgressBar.Minimum%2A> 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="ce641-130">Set the <xref:System.Windows.Forms.ProgressBar> control's <xref:System.Windows.Forms.ProgressBar.Minimum%2A> and <xref:System.Windows.Forms.ProgressBar.Maximum%2A> values.</span></span>  
  
2. <span data-ttu-id="ce641-131">진행률 표시줄의 <xref:System.Windows.Forms.ProgressBar.Step%2A> 표시된 값을 높이기 위해 양을 나타내는 정수로 컨트롤의 속성을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="ce641-131">Set the control's <xref:System.Windows.Forms.ProgressBar.Step%2A> property to an integer representing the amount to increase the progress bar's displayed value.</span></span>  
  
3. <span data-ttu-id="ce641-132">메서드를 <xref:System.Windows.Forms.ProgressBar.PerformStep%2A> 호출하여 속성에 설정된 양으로 <xref:System.Windows.Forms.ProgressBar.Step%2A> 표시되는 값을 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="ce641-132">Call the <xref:System.Windows.Forms.ProgressBar.PerformStep%2A> method to change the value displayed by the amount set in the <xref:System.Windows.Forms.ProgressBar.Step%2A> property.</span></span>  
  
     <span data-ttu-id="ce641-133">다음 코드 예제에서는 진행률 표시줄이 복사 작업에서 파일 수를 유지하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="ce641-133">The following code example illustrates how a progress bar can maintain a count of the files in a copy operation.</span></span>  
  
     <span data-ttu-id="ce641-134">다음 예제에서는 각 파일을 메모리로 읽을 때 진행률 표시줄과 레이블이 업데이트되어 읽은 총 파일을 반영합니다.</span><span class="sxs-lookup"><span data-stu-id="ce641-134">In the following example, as each file is read into memory, the progress bar and label are updated to reflect the total files read.</span></span> <span data-ttu-id="ce641-135">이 예제에서는 폼에 <xref:System.Windows.Forms.Label> 컨트롤과 <xref:System.Windows.Forms.ProgressBar> 컨트롤이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ce641-135">This example requires that your form has a <xref:System.Windows.Forms.Label> control and a <xref:System.Windows.Forms.ProgressBar> control.</span></span>  
  
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
  
     마지막으로 각 증가액이 고유 금액이 되도록 진행률 표시줄에 표시되는 값을 늘릴 수 있습니다. <span data-ttu-id="ce641-137">이 기능은 다양한 크기의 파일을 하드 디스크에 쓰거나 전체의 백분율로 진행률을 측정하는 등 일련의 고유한 작업을 추적하는 경우에 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="ce641-137">This is useful when you are keeping track of a series of unique operations, such as writing files of different sizes to a hard disk, or measuring progress as a percentage of the whole.</span></span>  
  
### <a name="to-increase-the-progress-bar-by-a-dynamic-value"></a><span data-ttu-id="ce641-138">동적 값으로 진행률 표시줄을 늘리려면</span><span class="sxs-lookup"><span data-stu-id="ce641-138">To increase the progress bar by a dynamic value</span></span>  
  
1. <span data-ttu-id="ce641-139"><xref:System.Windows.Forms.ProgressBar> 컨트롤과 <xref:System.Windows.Forms.ProgressBar.Maximum%2A> 값을 <xref:System.Windows.Forms.ProgressBar.Minimum%2A> 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="ce641-139">Set the <xref:System.Windows.Forms.ProgressBar> control's <xref:System.Windows.Forms.ProgressBar.Minimum%2A> and <xref:System.Windows.Forms.ProgressBar.Maximum%2A> values.</span></span>  
  
2. <span data-ttu-id="ce641-140">메서드를 <xref:System.Windows.Forms.ProgressBar.Increment%2A> 호출하여 지정한 정수에 의해 표시되는 값을 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="ce641-140">Call the <xref:System.Windows.Forms.ProgressBar.Increment%2A> method to change the value displayed by an integer you specify.</span></span>  
  
     <span data-ttu-id="ce641-141">다음 코드 예제에서는 진행률 표시줄에서 복사 작업 중에 사용된 디스크 공간의 양을 계산하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="ce641-141">The following code example illustrates how a progress bar can calculate how much disk space has been used during a copy operation.</span></span>  
  
     <span data-ttu-id="ce641-142">다음 예제에서는 각 파일이 하드 디스크에 기록될 때 사용 가능한 하드 디스크 공간의 양을 반영하도록 진행률 표시줄과 레이블이 업데이트됩니다.</span><span class="sxs-lookup"><span data-stu-id="ce641-142">In the following example, as each file is written to the hard disk, the progress bar and label are updated to reflect the amount of hard-disk space available.</span></span> <span data-ttu-id="ce641-143">이 예제에서는 폼에 <xref:System.Windows.Forms.Label> 컨트롤과 <xref:System.Windows.Forms.ProgressBar> 컨트롤이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ce641-143">This example requires that your form has a <xref:System.Windows.Forms.Label> control and a <xref:System.Windows.Forms.ProgressBar> control.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="ce641-144">참고 항목</span><span class="sxs-lookup"><span data-stu-id="ce641-144">See also</span></span>

- <xref:System.Windows.Forms.ProgressBar>
- <xref:System.Windows.Forms.ToolStripProgressBar>
- [<span data-ttu-id="ce641-145">ProgressBar 컨트롤 개요</span><span class="sxs-lookup"><span data-stu-id="ce641-145">ProgressBar Control Overview</span></span>](progressbar-control-overview-windows-forms.md)
- [<span data-ttu-id="ce641-146">ProgressBar 컨트롤</span><span class="sxs-lookup"><span data-stu-id="ce641-146">ProgressBar Control</span></span>](progressbar-control-windows-forms.md)
