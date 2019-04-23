---
title: '방법: OpenFileDialog 구성 요소를 사용 하 여 열려 있는 파일'
ms.date: 02/11/2019
dev_langs:
- csharp
- vb
helpviewer_keywords:
- OpenFileDialog component [Windows Forms], opening files
- OpenFile method [Windows Forms], OpenFileDialog component
- files [Windows Forms], opening with OpenFileDialog component
ms.assetid: 9d88367a-cc21-4ffd-be74-89fd63767d35
ms.openlocfilehash: 7f4e96f1714a182647665f12e29d38f2b8037478
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59159109"
---
# <a name="how-to-open-files-with-the-openfiledialog"></a><span data-ttu-id="eed12-102">방법: OpenFileDialog 사용 하 여 열려 있는 파일</span><span class="sxs-lookup"><span data-stu-id="eed12-102">How to: Open files with the OpenFileDialog</span></span> 

<span data-ttu-id="eed12-103"><xref:System.Windows.Forms.OpenFileDialog?displayProperty=nameWithType> 구성 요소 찾아보기 및 파일을 선택 하는 Windows 대화 상자가 열립니다.</span><span class="sxs-lookup"><span data-stu-id="eed12-103">The <xref:System.Windows.Forms.OpenFileDialog?displayProperty=nameWithType> component opens the Windows dialog box for browsing and selecting files.</span></span> <span data-ttu-id="eed12-104">열고 선택한 파일 읽기를 사용할 수 있습니다 합니다 <xref:System.Windows.Forms.OpenFileDialog.OpenFile%2A?displayProperty=nameWithType> 메서드를의 인스턴스를 만들 것인지를 <xref:System.IO.StreamReader?displayProperty=nameWithType> 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="eed12-104">To open and read the selected files, you can use the <xref:System.Windows.Forms.OpenFileDialog.OpenFile%2A?displayProperty=nameWithType> method, or create an instance of the <xref:System.IO.StreamReader?displayProperty=nameWithType> class.</span></span> <span data-ttu-id="eed12-105">다음 예제에서는 두 가지 방법을 모두 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="eed12-105">The following examples show both approaches.</span></span> 

<span data-ttu-id="eed12-106">.NET framework에서 가져오거나 설정할 합니다 <xref:System.Windows.Forms.FileDialog.FileName%2A> 속성을 권한 부여 수준이 필요 하 여는 <xref:System.Security.Permissions.FileIOPermission?displayProperty=nameWithType> 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="eed12-106">In .NET Framework, to get or set the <xref:System.Windows.Forms.FileDialog.FileName%2A> property requires a privilege level granted by the <xref:System.Security.Permissions.FileIOPermission?displayProperty=nameWithType> class.</span></span> <span data-ttu-id="eed12-107">예제 실행을 <xref:System.Security.Permissions.FileIOPermission> 권한으로 확인 하 고 부분 신뢰 컨텍스트에서 실행 하는 경우 권한이 부족 하 여 예외를 throw 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eed12-107">The examples run a <xref:System.Security.Permissions.FileIOPermission> permission check, and can throw an exception due to insufficient privileges if run in a partial-trust context.</span></span> <span data-ttu-id="eed12-108">자세한 내용은 [코드 액세스 보안 기본 사항](../../misc/code-access-security-basics.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="eed12-108">For more information, see [Code access security basics](../../misc/code-access-security-basics.md).</span></span>

<span data-ttu-id="eed12-109">빌드하고에서.NET Framework 앱으로 이러한 예제를 실행할 수 있습니다는 C# 또는 Visual Basic 명령줄입니다.</span><span class="sxs-lookup"><span data-stu-id="eed12-109">You can build and run these examples as .NET Framework apps from the C# or Visual Basic command line.</span></span> <span data-ttu-id="eed12-110">자세한 내용은 [csc.exe를 사용한 명령줄 빌드](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md) 하거나 [명령줄에서 빌드](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="eed12-110">For more information, see [Command-line building with csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md) or [Build from the command line](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md).</span></span> 

<span data-ttu-id="eed12-111">.NET Core 3.0 부터는 수 또한 빌드 및 실행 예제에서는.NET Core 앱을 Windows로.NET Core Windows Forms에 있는 폴더에서  *\<폴더 이름 >.csproj* 프로젝트 파일입니다.</span><span class="sxs-lookup"><span data-stu-id="eed12-111">Starting with .NET Core 3.0, you can also build and run the examples as Windows .NET Core apps from a folder that has a .NET Core Windows Forms *\<folder name>.csproj* project file.</span></span> 

## <a name="example-read-a-file-as-a-stream-with-streamreader"></a><span data-ttu-id="eed12-112">예제: StreamReader 사용 하 여 스트림으로 파일 읽기</span><span class="sxs-lookup"><span data-stu-id="eed12-112">Example: Read a file as a stream with StreamReader</span></span>  
  
<span data-ttu-id="eed12-113">다음 예제에서는 Windows Forms <xref:System.Windows.Forms.Button> 컨트롤의 <xref:System.Windows.Forms.Control.Click> 열려는 이벤트 처리기를 <xref:System.Windows.Forms.OpenFileDialog> 사용 하 여는 <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> 메서드.</span><span class="sxs-lookup"><span data-stu-id="eed12-113">The following example uses the Windows Forms <xref:System.Windows.Forms.Button> control's <xref:System.Windows.Forms.Control.Click> event handler to open the <xref:System.Windows.Forms.OpenFileDialog> with the <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> method.</span></span> <span data-ttu-id="eed12-114">사용자 파일을 선택 하 고 선택 후 **확인**의 인스턴스는 <xref:System.IO.StreamReader> 클래스 파일을 읽고 해당 내용이 양식의 텍스트 상자에 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="eed12-114">After the user chooses a file and selects **OK**, an instance of the <xref:System.IO.StreamReader> class reads the file and displays its contents in the form's text box.</span></span> <span data-ttu-id="eed12-115">파일 스트림에서 읽는 방법에 대 한 자세한 내용은 참조 하세요. <xref:System.IO.FileStream.BeginRead%2A?displayProperty=nameWithType> 고 <xref:System.IO.FileStream.Read%2A?displayProperty=nameWithType>입니다.</span><span class="sxs-lookup"><span data-stu-id="eed12-115">For more information about reading from file streams, see <xref:System.IO.FileStream.BeginRead%2A?displayProperty=nameWithType> and <xref:System.IO.FileStream.Read%2A?displayProperty=nameWithType>.</span></span>  

 [!code-csharp[OpenFileDialog#1](~/samples/snippets/winforms/open-files/example1/cs/Form1.cs)]
 [!code-vb[OpenFileDialog#1](~/samples/snippets/winforms/open-files/example1/vb/Form1.vb)]  

## <a name="example-open-a-file-from-a-filtered-selection-with-openfile"></a><span data-ttu-id="eed12-116">예제: OpenFile 사용 하 여 필터링 된 선택 영역에서 파일 열기</span><span class="sxs-lookup"><span data-stu-id="eed12-116">Example: Open a file from a filtered selection with OpenFile</span></span> 

<span data-ttu-id="eed12-117">다음 예제에서는 합니다 <xref:System.Windows.Forms.Button> 컨트롤의 <xref:System.Windows.Forms.Control.Click> 열려는 이벤트 처리기는 <xref:System.Windows.Forms.OpenFileDialog> 텍스트 파일만 표시 하는 필터를 사용 하 여 합니다.</span><span class="sxs-lookup"><span data-stu-id="eed12-117">The following example uses the <xref:System.Windows.Forms.Button> control's <xref:System.Windows.Forms.Control.Click> event handler to open the <xref:System.Windows.Forms.OpenFileDialog> with a filter that shows only text files.</span></span> <span data-ttu-id="eed12-118">사용자는 텍스트 파일을 선택 하 고 선택 후 **확인**, <xref:System.Windows.Forms.OpenFileDialog.OpenFile%2A> 메서드를 사용 하는 파일을 메모장에서 엽니다.</span><span class="sxs-lookup"><span data-stu-id="eed12-118">After the user chooses a text file and selects **OK**, the <xref:System.Windows.Forms.OpenFileDialog.OpenFile%2A> method is used to open the file in Notepad.</span></span>

 [!code-csharp[OpenFileDialog#2](~/samples/snippets/winforms/open-files/example2/cs/Form1.cs)]
 [!code-vb[OpenFileDialog#2](~/samples/snippets/winforms/open-files/example2/vb/Form1.vb)]  

## <a name="see-also"></a><span data-ttu-id="eed12-119">참고자료</span><span class="sxs-lookup"><span data-stu-id="eed12-119">See also</span></span>

- <xref:System.Windows.Forms.OpenFileDialog>
- [<span data-ttu-id="eed12-120">OpenFileDialog 구성 요소</span><span class="sxs-lookup"><span data-stu-id="eed12-120">OpenFileDialog component</span></span>](openfiledialog-component-windows-forms.md)
