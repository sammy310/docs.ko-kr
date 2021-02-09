---
description: '자세한 정보: 방법: Visual Basic에서 텍스트 파일에서 읽기'
title: '방법: 텍스트 파일에서 읽기'
ms.date: 07/20/2015
helpviewer_keywords:
- extended characters [Visual Basic], reading
- reading text files [Visual Basic]
- reading data, text files
- examples [Visual Basic], reading text files
- text files [Visual Basic], reading
ms.assetid: 735fe9d7-0f7a-4185-ba02-f35e580ec4b8
ms.openlocfilehash: 76f8bbbb7a0064818d324fc6dd9f1f37f7271401
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99797434"
---
# <a name="how-to-read-from-text-files-in-visual-basic"></a><span data-ttu-id="6f6b5-103">방법: Visual Basic에서 텍스트 파일 읽기</span><span class="sxs-lookup"><span data-stu-id="6f6b5-103">How to: Read From Text Files in Visual Basic</span></span>

<span data-ttu-id="6f6b5-104"><xref:Microsoft.VisualBasic.MyServices.FileSystemProxy.ReadAllText%2A> 개체의 `My.Computer.FileSystem` 메서드를 사용하면 텍스트 파일을 읽을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6f6b5-104">The <xref:Microsoft.VisualBasic.MyServices.FileSystemProxy.ReadAllText%2A> method of the `My.Computer.FileSystem` object allows you to read from a text file.</span></span> <span data-ttu-id="6f6b5-105">파일 내용에 ASCII 또는 UTF-8 등의 인코딩이 사용된 경우 파일 인코딩을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6f6b5-105">The file encoding can be specified if the contents of the file use an encoding such as ASCII or UTF-8.</span></span>

<span data-ttu-id="6f6b5-106">확장 문자가 사용된 파일을 읽을 때는 파일 인코딩을 지정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6f6b5-106">If you are reading from a file with extended characters, you will need to specify the file encoding.</span></span>

> [!NOTE]
> <span data-ttu-id="6f6b5-107">파일의 텍스트를 한 번에 한 줄씩 읽으려면 <xref:Microsoft.VisualBasic.MyServices.FileSystemProxy.OpenTextFileReader%2A> 개체의 `My.Computer.FileSystem` 메서드를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="6f6b5-107">To read a file a single line of text at a time, use the <xref:Microsoft.VisualBasic.MyServices.FileSystemProxy.OpenTextFileReader%2A> method of the `My.Computer.FileSystem` object.</span></span> <span data-ttu-id="6f6b5-108">`OpenTextFileReader` 메서드는 <xref:System.IO.StreamReader> 개체를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="6f6b5-108">The `OpenTextFileReader` method returns a <xref:System.IO.StreamReader> object.</span></span> <span data-ttu-id="6f6b5-109"><xref:System.IO.StreamReader.ReadLine%2A> 개체의 `StreamReader` 메서드를 사용하여 파일을 한 번에 한 줄씩 읽을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6f6b5-109">You can use the <xref:System.IO.StreamReader.ReadLine%2A> method of the `StreamReader` object to read a file one line at a time.</span></span> <span data-ttu-id="6f6b5-110"><xref:System.IO.StreamReader.EndOfStream%2A> 개체의 `StreamReader` 메서드를 사용하여 파일의 끝인지 여부를 테스트할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6f6b5-110">You can test for the end of the file using the <xref:System.IO.StreamReader.EndOfStream%2A> method of the `StreamReader` object.</span></span>

## <a name="to-read-from-a-text-file"></a><span data-ttu-id="6f6b5-111">텍스트 파일을 읽으려면</span><span class="sxs-lookup"><span data-stu-id="6f6b5-111">To read from a text file</span></span>

<span data-ttu-id="6f6b5-112">`ReadAllText` 개체의 `My.Computer.FileSystem` 메서드에 경로를 지정하여 텍스트 파일의 내용을 문자열로 읽어옵니다.</span><span class="sxs-lookup"><span data-stu-id="6f6b5-112">Use the `ReadAllText` method of the `My.Computer.FileSystem` object to read the contents of a text file into a string, supplying the path.</span></span> <span data-ttu-id="6f6b5-113">다음 예제에서는 test.txt의 내용을 문자열로 읽어온 다음 그 내용을 메시지 상자에 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="6f6b5-113">The following example reads the contents of test.txt into a string and then displays it in a message box.</span></span>

[!code-vb[VbFileIORead#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbFileIORead/VB/Class1.vb#2)]

### <a name="to-read-from-a-text-file-that-is-encoded"></a><span data-ttu-id="6f6b5-114">인코딩된 텍스트 파일을 읽으려면</span><span class="sxs-lookup"><span data-stu-id="6f6b5-114">To read from a text file that is encoded</span></span>

<span data-ttu-id="6f6b5-115">`ReadAllText` 개체의 `My.Computer.FileSystem` 메서드에 경로와 파일 인코딩 형식을 지정하여 텍스트 파일의 내용을 문자열로 읽어옵니다.</span><span class="sxs-lookup"><span data-stu-id="6f6b5-115">Use the `ReadAllText` method of the `My.Computer.FileSystem` object to read the contents of a text file into a string, supplying the path and file encoding type.</span></span> <span data-ttu-id="6f6b5-116">다음 예제에서는 UTF32 파일인 test.txt의 내용을 문자열로 읽어온 다음 그 내용을 메시지 상자에 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="6f6b5-116">The following example reads the contents of the UTF32 file test.txt into a string and then displays it in a message box.</span></span>

[!code-vb[VbFileIORead#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbFileIORead/VB/Class1.vb#3)]

## <a name="robust-programming"></a><span data-ttu-id="6f6b5-117">강력한 프로그래밍</span><span class="sxs-lookup"><span data-stu-id="6f6b5-117">Robust Programming</span></span>

<span data-ttu-id="6f6b5-118">다음 조건에서 예외가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="6f6b5-118">The following conditions may cause an exception:</span></span>

- <span data-ttu-id="6f6b5-119">길이가 0인 문자열이거나, 공백만 포함하거나, 잘못된 문자를 포함하거나, 경로가 디바이스 경로인 경우와 같은 여러 가지 이유 중 하나로 경로가 올바르지 않은 경우(<xref:System.ArgumentException>)</span><span class="sxs-lookup"><span data-stu-id="6f6b5-119">The path is not valid for one of the following reasons: it is a zero-length string, it contains only white space, it contains invalid characters, or it is a device path (<xref:System.ArgumentException>).</span></span>

- <span data-ttu-id="6f6b5-120">경로가 `Nothing` 이기 때문에 올바르지 않은 경우(<xref:System.ArgumentNullException>)</span><span class="sxs-lookup"><span data-stu-id="6f6b5-120">The path is not valid because it is `Nothing` (<xref:System.ArgumentNullException>).</span></span>

- <span data-ttu-id="6f6b5-121">파일이 없는 경우(<xref:System.IO.FileNotFoundException>)</span><span class="sxs-lookup"><span data-stu-id="6f6b5-121">The file does not exist (<xref:System.IO.FileNotFoundException>).</span></span>

- <span data-ttu-id="6f6b5-122">다른 프로세스에서 파일을 사용 중이거나 I/O 오류가 발생한 경우(<xref:System.IO.IOException>)</span><span class="sxs-lookup"><span data-stu-id="6f6b5-122">The file is in use by another process or an I/O error occurs (<xref:System.IO.IOException>).</span></span>

- <span data-ttu-id="6f6b5-123">경로가 시스템 정의 최대 길이를 초과하는 경우(<xref:System.IO.PathTooLongException>)</span><span class="sxs-lookup"><span data-stu-id="6f6b5-123">The path exceeds the system-defined maximum length (<xref:System.IO.PathTooLongException>).</span></span>

- <span data-ttu-id="6f6b5-124">경로의 파일 이름이나 디렉터리 이름에 콜론(:)이 있거나 이름의 형식이 잘못된 경우(<xref:System.NotSupportedException>)</span><span class="sxs-lookup"><span data-stu-id="6f6b5-124">A file or directory name in the path contains a colon (:) or is in an invalid format (<xref:System.NotSupportedException>).</span></span>

- <span data-ttu-id="6f6b5-125">문자열을 버퍼에 쓰기 위한 메모리가 부족한 경우(<xref:System.OutOfMemoryException>)</span><span class="sxs-lookup"><span data-stu-id="6f6b5-125">There is not enough memory to write the string to buffer (<xref:System.OutOfMemoryException>).</span></span>

- <span data-ttu-id="6f6b5-126">경로를 보는 데 필요한 권한이 사용자에게 없는 경우(<xref:System.Security.SecurityException>)</span><span class="sxs-lookup"><span data-stu-id="6f6b5-126">The user lacks necessary permissions to view the path (<xref:System.Security.SecurityException>).</span></span>

<span data-ttu-id="6f6b5-127">파일 이름을 바탕으로 파일 내용을 판단하면 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6f6b5-127">Do not make decisions about the contents of the file based on the name of the file.</span></span> <span data-ttu-id="6f6b5-128">예를 들어 Form1.vb 파일이 Visual Basic 소스 파일이 아닐 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6f6b5-128">For example, the file Form1.vb may not be a Visual Basic source file.</span></span>

<span data-ttu-id="6f6b5-129">애플리케이션에서 데이터를 사용하기 전에 모든 입력을 확인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6f6b5-129">Verify all inputs before using the data in your application.</span></span> <span data-ttu-id="6f6b5-130">파일의 내용이 예상한 내용과 다를 수 있으며 파일을 읽는 메서드가 실패할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6f6b5-130">The contents of the file may not be what is expected, and methods to read from the file may fail.</span></span>

## <a name="see-also"></a><span data-ttu-id="6f6b5-131">참고 항목</span><span class="sxs-lookup"><span data-stu-id="6f6b5-131">See also</span></span>

- <xref:Microsoft.VisualBasic.FileIO.FileSystem>
- <xref:Microsoft.VisualBasic.FileIO.FileSystem.ReadAllText%2A>
- [<span data-ttu-id="6f6b5-132">파일에서 읽기</span><span class="sxs-lookup"><span data-stu-id="6f6b5-132">Reading from Files</span></span>](reading-from-files.md)
- [<span data-ttu-id="6f6b5-133">방법: 쉼표로 구분된 텍스트 파일에서 읽기</span><span class="sxs-lookup"><span data-stu-id="6f6b5-133">How to: Read From Comma-Delimited Text Files</span></span>](how-to-read-from-comma-delimited-text-files.md)
- [<span data-ttu-id="6f6b5-134">방법: 고정 너비 텍스트 파일에서 읽기</span><span class="sxs-lookup"><span data-stu-id="6f6b5-134">How to: Read From Fixed-width Text Files</span></span>](how-to-read-from-fixed-width-text-files.md)
- [<span data-ttu-id="6f6b5-135">방법: 여러 형식의 텍스트 파일에서 읽기</span><span class="sxs-lookup"><span data-stu-id="6f6b5-135">How to: Read From Text Files with Multiple Formats</span></span>](how-to-read-from-text-files-with-multiple-formats.md)
- [<span data-ttu-id="6f6b5-136">문제 해결: 텍스트 파일 읽기 및 쓰기</span><span class="sxs-lookup"><span data-stu-id="6f6b5-136">Troubleshooting: Reading from and Writing to Text Files</span></span>](troubleshooting-reading-from-and-writing-to-text-files.md)
- [<span data-ttu-id="6f6b5-137">연습: Visual Basic에서 파일과 디렉터리 조작</span><span class="sxs-lookup"><span data-stu-id="6f6b5-137">Walkthrough: Manipulating Files and Directories in Visual Basic</span></span>](walkthrough-manipulating-files-and-directories.md)
- [<span data-ttu-id="6f6b5-138">파일 인코딩</span><span class="sxs-lookup"><span data-stu-id="6f6b5-138">File Encodings</span></span>](file-encodings.md)
