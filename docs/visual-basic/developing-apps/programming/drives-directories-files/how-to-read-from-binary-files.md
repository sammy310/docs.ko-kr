---
description: '자세한 정보: 방법: Visual Basic의 이진 파일에서 읽기'
title: '방법: 이진 파일에서 읽기'
ms.date: 07/20/2015
helpviewer_keywords:
- binary files [Visual Basic], reading from
- I/O [Visual Basic], reading from binary files
- ReadAllBytes method [Visual Basic], reading from binary files
- My.Computer.FileSystem object, reading from binary files
ms.assetid: d2b1269e-24b6-42e0-9414-ae708db282d8
ms.openlocfilehash: 0d522c6f55c0ef2e39437ba732040afdf5113d7a
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99797512"
---
# <a name="how-to-read-from-binary-files-in-visual-basic"></a><span data-ttu-id="e47ac-103">방법: Visual Basic에서 이진 파일 읽기</span><span class="sxs-lookup"><span data-stu-id="e47ac-103">How to: Read From Binary Files in Visual Basic</span></span>

<span data-ttu-id="e47ac-104">`My.Computer.FileSystem` 개체는 이진 파일을 읽기 위한 `ReadAllBytes` 메서드를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="e47ac-104">The `My.Computer.FileSystem` object provides the `ReadAllBytes` method for reading from binary files.</span></span>  
  
### <a name="to-read-from-a-binary-file"></a><span data-ttu-id="e47ac-105">이진 파일을 읽으려면</span><span class="sxs-lookup"><span data-stu-id="e47ac-105">To read from a binary file</span></span>  
  
- <span data-ttu-id="e47ac-106">파일 내용을 바이트 배열로 반환하는 `ReadAllBytes` 메서드를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="e47ac-106">Use the `ReadAllBytes` method, which returns the contents of a file as a byte array.</span></span> <span data-ttu-id="e47ac-107">이 예제에서는 `C:/Documents and Settings/selfportrait.jpg` 파일에서 읽습니다.</span><span class="sxs-lookup"><span data-stu-id="e47ac-107">This example reads from the file `C:/Documents and Settings/selfportrait.jpg`.</span></span>  
  
     [!code-vb[VbVbcnMyFileSystem#78](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnMyFileSystem/VB/Class1.vb#78)]  
  
- <span data-ttu-id="e47ac-108">큰 이진 파일의 경우 <xref:System.IO.FileStream> 개체의 <xref:System.IO.FileStream.Read%2A> 메서드를 사용하여 파일에서 한 번에 지정된 양만큼만 읽을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e47ac-108">For large binary files, you can use the <xref:System.IO.FileStream.Read%2A> method of the <xref:System.IO.FileStream> object to read from the file only a specified amount at a time.</span></span> <span data-ttu-id="e47ac-109">그런 다음 각 읽기 작업에 대해 메모리에 로드되는 파일 크기를 제한할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e47ac-109">You can then limit how much of the file is loaded into memory for each read operation.</span></span> <span data-ttu-id="e47ac-110">다음 코드 예제에서는 파일을 복사하고, 호출자가 읽기 작업당 메모리로 읽어오는 파일 크기를 지정할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="e47ac-110">The following code example copies a file and allows the caller to specify how much of the file is read into memory per read operation.</span></span>  
  
     [!code-vb[VbVbcnMyFileSystem#91](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnMyFileSystem/VB/Class1.vb#91)]  
  
## <a name="robust-programming"></a><span data-ttu-id="e47ac-111">강력한 프로그래밍</span><span class="sxs-lookup"><span data-stu-id="e47ac-111">Robust Programming</span></span>  

 <span data-ttu-id="e47ac-112">다음 조건에서는 예외가 throw될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e47ac-112">The following conditions may cause an exception to be thrown:</span></span>  
  
- <span data-ttu-id="e47ac-113">길이가 0인 문자열이거나, 공백만 포함하거나, 잘못된 문자를 포함하거나, 경로가 디바이스 경로인 경우와 같은 여러 가지 이유 중 하나로 경로가 올바르지 않은 경우(<xref:System.ArgumentException>)</span><span class="sxs-lookup"><span data-stu-id="e47ac-113">The path is not valid for one of the following reasons: it is a zero-length string, it contains only white space, it contains invalid characters, or it is a device path (<xref:System.ArgumentException>).</span></span>  
  
- <span data-ttu-id="e47ac-114">경로가 `Nothing` 이기 때문에 올바르지 않은 경우(<xref:System.ArgumentNullException>)</span><span class="sxs-lookup"><span data-stu-id="e47ac-114">The path is not valid because it is `Nothing` (<xref:System.ArgumentNullException>).</span></span>  
  
- <span data-ttu-id="e47ac-115">파일이 없는 경우(<xref:System.IO.FileNotFoundException>)</span><span class="sxs-lookup"><span data-stu-id="e47ac-115">The file does not exist (<xref:System.IO.FileNotFoundException>).</span></span>  
  
- <span data-ttu-id="e47ac-116">다른 프로세스에서 파일을 사용 중이거나 I/O 오류가 발생한 경우(<xref:System.IO.IOException>)</span><span class="sxs-lookup"><span data-stu-id="e47ac-116">The file is in use by another process, or an I/O error occurs (<xref:System.IO.IOException>).</span></span>  
  
- <span data-ttu-id="e47ac-117">경로가 시스템 정의 최대 길이를 초과하는 경우(<xref:System.IO.PathTooLongException>)</span><span class="sxs-lookup"><span data-stu-id="e47ac-117">The path exceeds the system-defined maximum length (<xref:System.IO.PathTooLongException>).</span></span>  
  
- <span data-ttu-id="e47ac-118">경로의 파일 이름이나 디렉터리 이름에 콜론(:)이 있거나 이름의 형식이 잘못된 경우(<xref:System.NotSupportedException>)</span><span class="sxs-lookup"><span data-stu-id="e47ac-118">A file or directory name in the path contains a colon (:) or is in an invalid format (<xref:System.NotSupportedException>).</span></span>  
  
- <span data-ttu-id="e47ac-119">문자열을 버퍼에 쓰기 위한 메모리가 부족한 경우(<xref:System.OutOfMemoryException>)</span><span class="sxs-lookup"><span data-stu-id="e47ac-119">There is not enough memory to write the string to buffer (<xref:System.OutOfMemoryException>).</span></span>  
  
- <span data-ttu-id="e47ac-120">경로를 보는 데 필요한 권한이 사용자에게 없는 경우(<xref:System.Security.SecurityException>)</span><span class="sxs-lookup"><span data-stu-id="e47ac-120">The user lacks necessary permissions to view the path (<xref:System.Security.SecurityException>).</span></span>  
  
 <span data-ttu-id="e47ac-121">파일 이름을 바탕으로 파일 내용을 판단하면 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e47ac-121">Do not make decisions about the contents of the file based on the name of the file.</span></span> <span data-ttu-id="e47ac-122">예를 들어 Form1.vb 파일이 Visual Basic 소스 파일이 아닐 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e47ac-122">For example, the file Form1.vb may not be a Visual Basic source file.</span></span>  
  
 <span data-ttu-id="e47ac-123">애플리케이션에서 데이터를 사용하기 전에 모든 입력을 확인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e47ac-123">Verify all inputs before using the data in your application.</span></span> <span data-ttu-id="e47ac-124">파일의 내용이 예상한 내용과 다를 수 있으며 파일을 읽는 메서드가 실패할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e47ac-124">The contents of the file may not be what is expected, and methods to read from the file may fail.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e47ac-125">참고 항목</span><span class="sxs-lookup"><span data-stu-id="e47ac-125">See also</span></span>

- <xref:Microsoft.VisualBasic.FileIO.FileSystem.ReadAllBytes%2A>
- <xref:Microsoft.VisualBasic.FileIO.FileSystem.WriteAllBytes%2A>
- [<span data-ttu-id="e47ac-126">파일에서 읽기</span><span class="sxs-lookup"><span data-stu-id="e47ac-126">Reading from Files</span></span>](reading-from-files.md)
- [<span data-ttu-id="e47ac-127">방법: 여러 형식의 텍스트 파일에서 읽기</span><span class="sxs-lookup"><span data-stu-id="e47ac-127">How to: Read From Text Files with Multiple Formats</span></span>](how-to-read-from-text-files-with-multiple-formats.md)
- [<span data-ttu-id="e47ac-128">데이터를 클립보드에 저장하고 클립보드에서 읽기</span><span class="sxs-lookup"><span data-stu-id="e47ac-128">Storing Data to and Reading from the Clipboard</span></span>](../computer-resources/storing-data-to-and-reading-from-the-clipboard.md)
