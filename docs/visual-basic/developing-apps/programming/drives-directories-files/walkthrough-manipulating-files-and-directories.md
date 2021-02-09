---
description: '자세한 정보: 연습: Visual Basic에서 파일과 디렉터리 조작'
title: 파일 및 디렉터리 조작
ms.date: 07/20/2015
helpviewer_keywords:
- files [Visual Basic], reading text
- reading files [Visual Basic], text
- I/O [Visual Basic], walkthroughs
- text, writing to files
- text, reading from files
- reading text from files [Visual Basic], walkthroughs
- Visual Basic code, file access
- files [Visual Basic], writing text
- I/O [Visual Basic], writing text to files
- file access, walkthroughs
- writing to files [Visual Basic], walkthroughs
- I/O [Visual Basic], reading text from files
ms.assetid: cae77565-9f78-4e46-8e42-eb2f9f8e1ffd
ms.openlocfilehash: 315635ee43ee4d4956fc35b7f9bc635b374646f8
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99775385"
---
# <a name="walkthrough-manipulating-files-and-directories-in-visual-basic"></a><span data-ttu-id="478c8-103">연습: Visual Basic에서 파일과 디렉터리 조작</span><span class="sxs-lookup"><span data-stu-id="478c8-103">Walkthrough: Manipulating Files and Directories in Visual Basic</span></span>

<span data-ttu-id="478c8-104">이 연습에서는 Visual Basic에서 파일 I/O의 기본 개념을 소개합니다.</span><span class="sxs-lookup"><span data-stu-id="478c8-104">This walkthrough provides an introduction to the fundamentals of file I/O in Visual Basic.</span></span> <span data-ttu-id="478c8-105">디렉터리에 텍스트 파일을 나열하고 검사하는 작은 애플리케이션을 만드는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="478c8-105">It describes how to create a small application that lists and examines text files in a directory.</span></span> <span data-ttu-id="478c8-106">선택한 각 텍스트 파일에 대해 애플리케이션은 파일 특성 및 내용의 첫 줄을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="478c8-106">For each selected text file, the application provides file attributes and the first line of content.</span></span> <span data-ttu-id="478c8-107">로그 파일에 정보를 기록하는 옵션이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="478c8-107">There is an option to write information to a log file.</span></span>  
  
 <span data-ttu-id="478c8-108">이 연습에서는 Visual Basic에서 사용 가능한 `My.Computer.FileSystem Object`의 멤버를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="478c8-108">This walkthrough uses members of the `My.Computer.FileSystem Object`, which are available in Visual Basic.</span></span> <span data-ttu-id="478c8-109">자세한 내용은 <xref:Microsoft.VisualBasic.FileIO.FileSystem> 을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="478c8-109">See <xref:Microsoft.VisualBasic.FileIO.FileSystem> for more information.</span></span> <span data-ttu-id="478c8-110">연습의 끝 부분에서 <xref:System.IO> 네임스페이스의 클래스를 사용하는 동등한 예제가 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="478c8-110">At the end of the walkthrough, an equivalent example is provided that uses classes from the <xref:System.IO> namespace.</span></span>  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
### <a name="to-create-the-project"></a><span data-ttu-id="478c8-111">프로젝트를 만들려면</span><span class="sxs-lookup"><span data-stu-id="478c8-111">To create the project</span></span>  
  
1. <span data-ttu-id="478c8-112">**파일** 메뉴에서 **새 프로젝트** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="478c8-112">On the **File** menu, click **New Project**.</span></span>  
  
     <span data-ttu-id="478c8-113">**새 프로젝트** 대화 상자가 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="478c8-113">The **New Project** dialog box appears.</span></span>  
  
2. <span data-ttu-id="478c8-114">**설치된 템플릿** 창에서 **Visual Basic** 을 확장한 다음 **Windows** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="478c8-114">In the **Installed Templates** pane, expand **Visual Basic**, and then click **Windows**.</span></span> <span data-ttu-id="478c8-115">**템플릿** 창 가운데에서 **Windows Forms 애플리케이션** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="478c8-115">In the **Templates** pane in the middle, click **Windows Forms Application**.</span></span>  
  
3. <span data-ttu-id="478c8-116">**이름** 상자에 `FileExplorer`를 입력하여 프로젝트 이름을 설정한 다음 **확인** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="478c8-116">In the **Name** box, type `FileExplorer` to set the project name, and then click **OK**.</span></span>  
  
     <span data-ttu-id="478c8-117">Visual Studio에서 **솔루션 탐색기** 에 프로젝트를 추가합니다. 그러면 Windows Forms 디자이너가 열립니다.</span><span class="sxs-lookup"><span data-stu-id="478c8-117">Visual Studio adds the project to **Solution Explorer**, and the Windows Forms Designer opens.</span></span>  
  
4. <span data-ttu-id="478c8-118">다음 표의 컨트롤을 양식에 추가하고 속성의 해당 값을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="478c8-118">Add the controls in the following table to the form, and set the corresponding values for their properties.</span></span>  
  
    |<span data-ttu-id="478c8-119">제어</span><span class="sxs-lookup"><span data-stu-id="478c8-119">Control</span></span>|<span data-ttu-id="478c8-120">속성</span><span class="sxs-lookup"><span data-stu-id="478c8-120">Property</span></span>|<span data-ttu-id="478c8-121">값</span><span class="sxs-lookup"><span data-stu-id="478c8-121">Value</span></span>|  
    |-------------|--------------|-----------|  
    |<span data-ttu-id="478c8-122">**ListBox**</span><span class="sxs-lookup"><span data-stu-id="478c8-122">**ListBox**</span></span>|<span data-ttu-id="478c8-123">**이름**</span><span class="sxs-lookup"><span data-stu-id="478c8-123">**Name**</span></span>|`filesListBox`|  
    |<span data-ttu-id="478c8-124">**단추**</span><span class="sxs-lookup"><span data-stu-id="478c8-124">**Button**</span></span>|<span data-ttu-id="478c8-125">**이름**</span><span class="sxs-lookup"><span data-stu-id="478c8-125">**Name**</span></span><br /><br /> <span data-ttu-id="478c8-126">**Text**</span><span class="sxs-lookup"><span data-stu-id="478c8-126">**Text**</span></span>|`browseButton`<br /><br /> <span data-ttu-id="478c8-127">**찾아보기**</span><span class="sxs-lookup"><span data-stu-id="478c8-127">**Browse**</span></span>|  
    |<span data-ttu-id="478c8-128">**단추**</span><span class="sxs-lookup"><span data-stu-id="478c8-128">**Button**</span></span>|<span data-ttu-id="478c8-129">**이름**</span><span class="sxs-lookup"><span data-stu-id="478c8-129">**Name**</span></span><br /><br /> <span data-ttu-id="478c8-130">**Text**</span><span class="sxs-lookup"><span data-stu-id="478c8-130">**Text**</span></span>|`examineButton`<br /><br /> <span data-ttu-id="478c8-131">**검사**</span><span class="sxs-lookup"><span data-stu-id="478c8-131">**Examine**</span></span>|  
    |<span data-ttu-id="478c8-132">**CheckBox**</span><span class="sxs-lookup"><span data-stu-id="478c8-132">**CheckBox**</span></span>|<span data-ttu-id="478c8-133">**이름**</span><span class="sxs-lookup"><span data-stu-id="478c8-133">**Name**</span></span><br /><br /> <span data-ttu-id="478c8-134">**Text**</span><span class="sxs-lookup"><span data-stu-id="478c8-134">**Text**</span></span>|`saveCheckBox`<br /><br /> <span data-ttu-id="478c8-135">**결과 저장**</span><span class="sxs-lookup"><span data-stu-id="478c8-135">**Save Results**</span></span>|  
    |<span data-ttu-id="478c8-136">**FolderBrowserDialog**</span><span class="sxs-lookup"><span data-stu-id="478c8-136">**FolderBrowserDialog**</span></span>|<span data-ttu-id="478c8-137">**이름**</span><span class="sxs-lookup"><span data-stu-id="478c8-137">**Name**</span></span>|`FolderBrowserDialog1`|  
  
### <a name="to-select-a-folder-and-list-files-in-a-folder"></a><span data-ttu-id="478c8-138">폴더를 선택하고 폴더에 파일을 나열하려면</span><span class="sxs-lookup"><span data-stu-id="478c8-138">To select a folder, and list files in a folder</span></span>  
  
1. <span data-ttu-id="478c8-139">양식의 컨트롤을 두 번 클릭하여 `browseButton`에 대한 `Click` 이벤트 처리기를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="478c8-139">Create a `Click` event handler for `browseButton` by double-clicking the control on the form.</span></span> <span data-ttu-id="478c8-140">코드 편집기가 열립니다.</span><span class="sxs-lookup"><span data-stu-id="478c8-140">The Code Editor opens.</span></span>  
  
2. <span data-ttu-id="478c8-141">다음 코드를 `Click` 이벤트 처리기에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="478c8-141">Add the following code to the `Click` event handler.</span></span>  
  
     [!code-vb[VbVbcnMyFileSystem#103](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnMyFileSystem/VB/class2.vb#103)]  
  
     <span data-ttu-id="478c8-142">`FolderBrowserDialog1.ShowDialog` 호출은 **폴더 찾아보기** 대화 상자를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="478c8-142">The `FolderBrowserDialog1.ShowDialog` call opens the **Browse For Folder** dialog box.</span></span> <span data-ttu-id="478c8-143">사용자가 **확인** 을 클릭하면 <xref:System.Windows.Forms.FolderBrowserDialog.SelectedPath%2A> 속성이 `ListFiles` 메서드로 인수에 전송됩니다. 다음 단계에서 이 메서드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="478c8-143">After the user clicks **OK**, the <xref:System.Windows.Forms.FolderBrowserDialog.SelectedPath%2A> property is sent as an argument to the `ListFiles` method, which is added in the next step.</span></span>  
  
3. <span data-ttu-id="478c8-144">다음 `ListFiles` 메서드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="478c8-144">Add the following `ListFiles` method.</span></span>  
  
     [!code-vb[VbVbcnMyFileSystem#104](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnMyFileSystem/VB/class2.vb#104)]  
  
     <span data-ttu-id="478c8-145">이 코드는 먼저 **ListBox** 를 지웁니다.</span><span class="sxs-lookup"><span data-stu-id="478c8-145">This code first clears the **ListBox**.</span></span>  
  
     <span data-ttu-id="478c8-146"><xref:Microsoft.VisualBasic.FileIO.FileSystem.GetFiles%2A> 메서드는 디렉터리에 있는 각 파일에 대해 나하씩 문자열 컬렉션을 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="478c8-146">The <xref:Microsoft.VisualBasic.FileIO.FileSystem.GetFiles%2A> method then retrieves a collection of strings, one for each file in the directory.</span></span> <span data-ttu-id="478c8-147">`GetFiles` 메서드는 특정 패턴과 일치하는 파일을 검색하기 위해 패턴 인수를 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="478c8-147">The `GetFiles` method accepts a search pattern argument to retrieve files that match a particular pattern.</span></span> <span data-ttu-id="478c8-148">이 예제에서는 확장명이 .txt인 파일만 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="478c8-148">In this example, only files that have the extension .txt are returned.</span></span>  
  
     <span data-ttu-id="478c8-149">`GetFiles` 메서드에 의해 반환되는 문자열은 **ListBox** 에 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="478c8-149">The strings that are returned by the `GetFiles` method are then added to the **ListBox**.</span></span>  
  
4. <span data-ttu-id="478c8-150">애플리케이션을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="478c8-150">Run the application.</span></span> <span data-ttu-id="478c8-151">**찾아보기** 단추를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="478c8-151">Click the **Browse** button.</span></span> <span data-ttu-id="478c8-152">**폴더 찾아보기** 대화 상자에서 .txt 파일이 있는 폴더로 이동하여 폴더를 선택하고 **확인** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="478c8-152">In the **Browse For Folder** dialog box, browse to a folder that contains .txt files, and then select the folder and click **OK**.</span></span>  
  
     <span data-ttu-id="478c8-153">`ListBox`에는 선택한 폴더에 있는 .txt 파일의 목록이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="478c8-153">The `ListBox` contains a list of .txt files in the selected folder.</span></span>  
  
5. <span data-ttu-id="478c8-154">애플리케이션 실행을 중지합니다.</span><span class="sxs-lookup"><span data-stu-id="478c8-154">Stop running the application.</span></span>  
  
### <a name="to-obtain-attributes-of-a-file-and-content-from-a-text-file"></a><span data-ttu-id="478c8-155">파일의 특성을 및 텍스트 파일의 내용을 가져오려면</span><span class="sxs-lookup"><span data-stu-id="478c8-155">To obtain attributes of a file, and content from a text file</span></span>  
  
1. <span data-ttu-id="478c8-156">양식의 컨트롤을 두 번 클릭하여 `examineButton`에 대한 `Click` 이벤트 처리기를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="478c8-156">Create a `Click` event handler for `examineButton` by double-clicking the control on the form.</span></span>  
  
2. <span data-ttu-id="478c8-157">다음 코드를 `Click` 이벤트 처리기에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="478c8-157">Add the following code to the `Click` event handler.</span></span>  
  
     [!code-vb[VbVbcnMyFileSystem#105](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnMyFileSystem/VB/class2.vb#105)]  
  
     <span data-ttu-id="478c8-158">이 코드는 항목이 `ListBox`에서 선택되었는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="478c8-158">The code verifies that an item is selected in the `ListBox`.</span></span> <span data-ttu-id="478c8-159">그런 다음 `ListBox`에서 파일 경로 항목을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="478c8-159">It then obtains the file path entry from the `ListBox`.</span></span> <span data-ttu-id="478c8-160"><xref:Microsoft.VisualBasic.FileIO.FileSystem.FileExists%2A> 메서드는 파일이 아직 있는지를 확인하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="478c8-160">The <xref:Microsoft.VisualBasic.FileIO.FileSystem.FileExists%2A> method is used to check whether the file still exists.</span></span>  
  
     <span data-ttu-id="478c8-161">파일 경로가 인수로서 `GetTextForOutput` 메서드로 전송됩니다. 이 메서드는 다음 단계에서 추가되어,</span><span class="sxs-lookup"><span data-stu-id="478c8-161">The file path is sent as an argument to the `GetTextForOutput` method, which is added in the next step.</span></span> <span data-ttu-id="478c8-162">파일 정보를 포함하는 문자열을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="478c8-162">This method returns a string that contains file information.</span></span> <span data-ttu-id="478c8-163">파일 정보는 **MessageBox** 에 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="478c8-163">The file information appears in a **MessageBox**.</span></span>  
  
3. <span data-ttu-id="478c8-164">다음 `GetTextForOutput` 메서드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="478c8-164">Add the following `GetTextForOutput` method.</span></span>  
  
     [!code-vb[VbVbcnMyFileSystem#107](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnMyFileSystem/VB/class2.vb#107)]  
  
     <span data-ttu-id="478c8-165">이 코드는 <xref:Microsoft.VisualBasic.FileIO.FileSystem.GetFileInfo%2A> 메서드를 사용하여 파일 매개 변수를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="478c8-165">The code uses the <xref:Microsoft.VisualBasic.FileIO.FileSystem.GetFileInfo%2A> method to obtain file parameters.</span></span> <span data-ttu-id="478c8-166">파일 매개 변수는 <xref:System.Text.StringBuilder>에 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="478c8-166">The file parameters are added to a <xref:System.Text.StringBuilder>.</span></span>  
  
     <span data-ttu-id="478c8-167"><xref:Microsoft.VisualBasic.FileIO.FileSystem.OpenTextFileReader%2A> 메서드는 파일 내용을 <xref:System.IO.StreamReader>로 읽어들입니다.</span><span class="sxs-lookup"><span data-stu-id="478c8-167">The <xref:Microsoft.VisualBasic.FileIO.FileSystem.OpenTextFileReader%2A> method reads the file contents into a <xref:System.IO.StreamReader>.</span></span> <span data-ttu-id="478c8-168">내용의 첫 번째 줄을 `StreamReader`에서 가져와 `StringBuilder`에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="478c8-168">The first line of the contents is obtained from the `StreamReader` and is added to the `StringBuilder`.</span></span>  
  
4. <span data-ttu-id="478c8-169">애플리케이션을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="478c8-169">Run the application.</span></span> <span data-ttu-id="478c8-170">**찾아보기** 를 클릭하고 .txt 파일이 포함된 폴더로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="478c8-170">Click **Browse**, and browse to a folder that contains .txt files.</span></span> <span data-ttu-id="478c8-171">**확인** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="478c8-171">Click **OK**.</span></span>  
  
     <span data-ttu-id="478c8-172">`ListBox`에서 파일을 선택하고 **검사** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="478c8-172">Select a file in the `ListBox`, and then click **Examine**.</span></span> <span data-ttu-id="478c8-173">`MessageBox`에 파일 정보가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="478c8-173">A `MessageBox` shows the file information.</span></span>  
  
5. <span data-ttu-id="478c8-174">애플리케이션 실행을 중지합니다.</span><span class="sxs-lookup"><span data-stu-id="478c8-174">Stop running the application.</span></span>  
  
### <a name="to-add-a-log-entry"></a><span data-ttu-id="478c8-175">로그 항목을 추가하려면</span><span class="sxs-lookup"><span data-stu-id="478c8-175">To add a log entry</span></span>  
  
1. <span data-ttu-id="478c8-176">다음 코드를 `examineButton_Click` 이벤트 처리기의 끝에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="478c8-176">Add the following code to the end of the `examineButton_Click` event handler.</span></span>  
  
     [!code-vb[VbVbcnMyFileSystem#106](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnMyFileSystem/VB/class2.vb#106)]  
  
     <span data-ttu-id="478c8-177">이 코드는 선택한 파일과 동일한 디렉터리에 로그 파일을 저장하도록 로그 파일 경로를 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="478c8-177">The code sets the log file path to put the log file in the same directory as that of the selected file.</span></span> <span data-ttu-id="478c8-178">로그 항목의 텍스트는 파일 정보 뒤에 현재 날짜 및 시간으로 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="478c8-178">The text of the log entry is set to the current date and time followed by the file information.</span></span>  
  
     <span data-ttu-id="478c8-179">`append` 인수가 `True`로 설정된 <xref:Microsoft.VisualBasic.FileIO.FileSystem.WriteAllText%2A> 메서드를 사용하여 로그 항목을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="478c8-179">The <xref:Microsoft.VisualBasic.FileIO.FileSystem.WriteAllText%2A> method, with the `append` argument set to `True`, is used to create the log entry.</span></span>  
  
2. <span data-ttu-id="478c8-180">애플리케이션을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="478c8-180">Run the application.</span></span> <span data-ttu-id="478c8-181">텍스트 파일로 이동하고, `ListBox`에서 선택하고, **결과 저장** 확인란을 선택한 다음 **검사** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="478c8-181">Browse to a text file, select it in the `ListBox`, select the **Save Results** check box, and then click **Examine**.</span></span> <span data-ttu-id="478c8-182">로그 항목이 `log.txt` 파일에 기록되었는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="478c8-182">Verify that the log entry is written to the `log.txt` file.</span></span>  
  
3. <span data-ttu-id="478c8-183">애플리케이션 실행을 중지합니다.</span><span class="sxs-lookup"><span data-stu-id="478c8-183">Stop running the application.</span></span>  
  
### <a name="to-use-the-current-directory"></a><span data-ttu-id="478c8-184">현재 디렉터리를 사용하려면</span><span class="sxs-lookup"><span data-stu-id="478c8-184">To use the current directory</span></span>  
  
1. <span data-ttu-id="478c8-185">양식을 두 번 클릭하여 `Form1_Load`에 대한 이벤트 처리기를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="478c8-185">Create an event handler for `Form1_Load` by double-clicking the form.</span></span>  
  
2. <span data-ttu-id="478c8-186">다음 코드를 이벤트 처리기에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="478c8-186">Add the following code to the event handler.</span></span>  
  
     [!code-vb[VbVbcnMyFileSystem#102](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnMyFileSystem/VB/class2.vb#102)]  
  
     <span data-ttu-id="478c8-187">이 코드는 폴더 브라우저의 기본 디렉터리를 현재 디렉터리로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="478c8-187">This code sets the default directory of the folder browser to the current directory.</span></span>  
  
3. <span data-ttu-id="478c8-188">애플리케이션을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="478c8-188">Run the application.</span></span> <span data-ttu-id="478c8-189">**찾아보기** 를 처음 클릭하면 **폴더 찾아보기** 대화 상자가 현재 디렉터리로 열립니다.</span><span class="sxs-lookup"><span data-stu-id="478c8-189">When you click **Browse** the first time, the **Browse For Folder** dialog box opens to the current directory.</span></span>  
  
4. <span data-ttu-id="478c8-190">애플리케이션 실행을 중지합니다.</span><span class="sxs-lookup"><span data-stu-id="478c8-190">Stop running the application.</span></span>  
  
### <a name="to-selectively-enable-controls"></a><span data-ttu-id="478c8-191">선택적으로 컨트롤을 사용하도록 설정하려면</span><span class="sxs-lookup"><span data-stu-id="478c8-191">To selectively enable controls</span></span>  
  
1. <span data-ttu-id="478c8-192">다음 `SetEnabled` 메서드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="478c8-192">Add the following `SetEnabled` method.</span></span>  
  
     [!code-vb[VbVbcnMyFileSystem#108](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnMyFileSystem/VB/class2.vb#108)]  
  
     <span data-ttu-id="478c8-193">`ListBox`에서 항목이 선택되었는지에 따라 `SetEnabled` 메서드는 컨트롤의 사용 여부를 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="478c8-193">The `SetEnabled` method enables or disables controls depending on whether an item is selected in the `ListBox`.</span></span>  
  
2. <span data-ttu-id="478c8-194">양식의 `ListBox` 컨트롤을 두 번 클릭하여 `filesListBox`에 대한 `SelectedIndexChanged` 이벤트 처리기를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="478c8-194">Create a `SelectedIndexChanged` event handler for `filesListBox` by double-clicking the `ListBox` control on the form.</span></span>  
  
3. <span data-ttu-id="478c8-195">새 `filesListBox_SelectedIndexChanged` 이벤트 처리기에서 `SetEnabled`에 호출을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="478c8-195">Add a call to `SetEnabled` in the new `filesListBox_SelectedIndexChanged` event handler.</span></span>  
  
4. <span data-ttu-id="478c8-196">`browseButton_Click` 이벤트 처리기의 끝에서 `SetEnabled`에 호출을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="478c8-196">Add a call to `SetEnabled` at the end of the `browseButton_Click` event handler.</span></span>  
  
5. <span data-ttu-id="478c8-197">`Form1_Load` 이벤트 처리기의 끝에서 `SetEnabled`에 호출을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="478c8-197">Add a call to `SetEnabled` at the end of the `Form1_Load` event handler.</span></span>  
  
6. <span data-ttu-id="478c8-198">애플리케이션을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="478c8-198">Run the application.</span></span> <span data-ttu-id="478c8-199">`ListBox`에서 항목을 선택하지 않으면 **결과 저장** 확인란 및 **검사** 단추가 활성화되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="478c8-199">The **Save Results** check box and the **Examine** button are disabled if an item is not selected in the `ListBox`.</span></span>  
  
## <a name="full-example-using-mycomputerfilesystem"></a><span data-ttu-id="478c8-200">My.Computer.FileSystem을 사용하는 전체 예제</span><span class="sxs-lookup"><span data-stu-id="478c8-200">Full example using My.Computer.FileSystem</span></span>  

 <span data-ttu-id="478c8-201">다음은 전체 예제입니다.</span><span class="sxs-lookup"><span data-stu-id="478c8-201">Following is the complete example.</span></span>  
  
 [!code-vb[VbVbcnMyFileSystem#101](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnMyFileSystem/VB/class2.vb#101)]  
  
## <a name="full-example-using-systemio"></a><span data-ttu-id="478c8-202">System.IO를 사용하는 전체 예제</span><span class="sxs-lookup"><span data-stu-id="478c8-202">Full example using System.IO</span></span>  

 <span data-ttu-id="478c8-203">동등한 다음 예제에서는 `My.Computer.FileSystem` 개체를 사용하는 대신 <xref:System.IO> 네임스페이스의 클래스를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="478c8-203">The following equivalent example uses classes from the <xref:System.IO> namespace instead of using `My.Computer.FileSystem` objects.</span></span>  
  
 [!code-vb[VbVbcnMyFileSystem#111](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnMyFileSystem/VB/class3.vb#111)]  
  
## <a name="see-also"></a><span data-ttu-id="478c8-204">참고 항목</span><span class="sxs-lookup"><span data-stu-id="478c8-204">See also</span></span>

- <xref:System.IO>
- <xref:Microsoft.VisualBasic.FileIO.FileSystem>
- <xref:Microsoft.VisualBasic.FileIO.FileSystem.CurrentDirectory%2A>
- [<span data-ttu-id="478c8-205">연습: .NET Framework 메서드를 사용하여 파일 조작</span><span class="sxs-lookup"><span data-stu-id="478c8-205">Walkthrough: Manipulating Files by Using .NET Framework Methods</span></span>](walkthrough-manipulating-files-by-using-net-framework-methods.md)
