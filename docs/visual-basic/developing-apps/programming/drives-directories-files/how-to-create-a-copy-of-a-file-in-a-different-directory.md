---
description: '자세한 정보: 방법: Visual Basic에서 다른 디렉터리에 파일의 복사본 만들기'
title: '방법: 다른 디렉터리에 파일의 복사본 만들기'
ms.date: 07/20/2015
helpviewer_keywords:
- My.Computer.FileSystem.CopyFile method, copying files [Visual Basic]
- files [Visual Basic], copying
- CopyFile method [Visual Basic], copying files in Visual Basic
- I/O [Visual Basic], copying files
ms.assetid: 88e2145c-d414-45a5-ad03-6f5d58ecca26
ms.openlocfilehash: 128a813ec3e5c759d5320d59a1e83f9d66af3bbd
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99797642"
---
# <a name="how-to-create-a-copy-of-a-file-in-a-different-directory-in-visual-basic"></a><span data-ttu-id="a0343-103">방법: Visual Basic에서 다른 디렉터리에 파일의 복사본 만들기</span><span class="sxs-lookup"><span data-stu-id="a0343-103">How to: Create a Copy of a File in a Different Directory in Visual Basic</span></span>

<span data-ttu-id="a0343-104">`My.Computer.FileSystem.CopyFile` 메서드를 사용하면 파일을 복사할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a0343-104">The `My.Computer.FileSystem.CopyFile` method allows you to copy files.</span></span> <span data-ttu-id="a0343-105">해당 매개 변수를 통해 기존 파일을 덮어쓰고, 파일 이름을 바꾸고, 작업의 진행률을 표시하고, 사용자가 작업을 취소할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a0343-105">Its parameters provide the ability to overwrite existing files, rename the file, show the progress of the operation, and allow the user to cancel the operation.</span></span>  
  
### <a name="to-copy-a-text-file-to-another-folder"></a><span data-ttu-id="a0343-106">텍스트 파일을 다른 폴더로 복사하려면</span><span class="sxs-lookup"><span data-stu-id="a0343-106">To copy a text file to another folder</span></span>  
  
- <span data-ttu-id="a0343-107">원본 파일과 대상 디렉터리를 지정해서 `CopyFile` 메서드를 사용하여 파일을 복사합니다.</span><span class="sxs-lookup"><span data-stu-id="a0343-107">Use the `CopyFile` method to copy a file, specifying a source file and the target directory.</span></span> <span data-ttu-id="a0343-108">`overwrite` 매개 변수를 사용하면 기존 파일을 덮어쓸지 여부를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a0343-108">The `overwrite` parameter allows you to specify whether or not to overwrite existing files.</span></span> <span data-ttu-id="a0343-109">다음 코드 예제에서는 `CopyFile`을 사용하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="a0343-109">The following code examples demonstrate how to use `CopyFile`.</span></span>  
  
     [!code-vb[VbFileIOMisc#24](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbFileIOMisc/VB/Class1.vb#24)]  
  
## <a name="robust-programming"></a><span data-ttu-id="a0343-110">강력한 프로그래밍</span><span class="sxs-lookup"><span data-stu-id="a0343-110">Robust Programming</span></span>  

 <span data-ttu-id="a0343-111">다음 조건에서는 예외가 throw될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a0343-111">The following conditions may cause an exception to be thrown:</span></span>  
  
- <span data-ttu-id="a0343-112">길이가 0인 문자열이거나, 공백만 포함하거나, 잘못된 문자를 포함하거나, 경로가 디바이스 경로인 경우(\\\\.\\로 시작됨)와 같은 여러 가지 이유 중 하나로 경로가 올바르지 않은 경우(<xref:System.ArgumentException>)</span><span class="sxs-lookup"><span data-stu-id="a0343-112">The path is not valid for one of the following reasons: it is a zero-length string, it contains only white space, it contains invalid characters, or it is a device path (starts with \\\\.\\) (<xref:System.ArgumentException>).</span></span>  
  
- <span data-ttu-id="a0343-113">시스템이 절대 경로를 검색할 수 없는 경우(<xref:System.ArgumentException>)</span><span class="sxs-lookup"><span data-stu-id="a0343-113">The system could not retrieve the absolute path (<xref:System.ArgumentException>).</span></span>  
  
- <span data-ttu-id="a0343-114">경로가 `Nothing` 이기 때문에 올바르지 않은 경우(<xref:System.ArgumentNullException>)</span><span class="sxs-lookup"><span data-stu-id="a0343-114">The path is not valid because it is `Nothing` (<xref:System.ArgumentNullException>).</span></span>  
  
- <span data-ttu-id="a0343-115">소스 파일이 잘못되었거나 없는 경우(<xref:System.IO.FileNotFoundException>)</span><span class="sxs-lookup"><span data-stu-id="a0343-115">The source file is not valid or does not exist (<xref:System.IO.FileNotFoundException>).</span></span>  
  
- <span data-ttu-id="a0343-116">조합된 경로가 기존 디렉터리를 가리키는 경우(<xref:System.IO.IOException>)</span><span class="sxs-lookup"><span data-stu-id="a0343-116">The combined path points to an existing directory (<xref:System.IO.IOException>).</span></span>  
  
- <span data-ttu-id="a0343-117">대상 파일이 있고 `overwrite`가 `False`로 설정된 경우(<xref:System.IO.IOException>)</span><span class="sxs-lookup"><span data-stu-id="a0343-117">The destination file exists and `overwrite` is set to `False` (<xref:System.IO.IOException>).</span></span>  
  
- <span data-ttu-id="a0343-118">사용자에게 파일에 액세스할 수 있는 권한이 없는 경우(<xref:System.IO.IOException>)</span><span class="sxs-lookup"><span data-stu-id="a0343-118">The user does not have sufficient permissions to access the file (<xref:System.IO.IOException>).</span></span>  
  
- <span data-ttu-id="a0343-119">대상 폴더에 있는 동일한 이름의 파일이 사용 중인 경우 (<xref:System.IO.IOException>)</span><span class="sxs-lookup"><span data-stu-id="a0343-119">A file in the target folder with the same name is in use (<xref:System.IO.IOException>).</span></span>  
  
- <span data-ttu-id="a0343-120">경로의 파일 이름이나 폴더 이름에 콜론(:)이 있거나 이름의 형식이 잘못된 경우(<xref:System.NotSupportedException>)</span><span class="sxs-lookup"><span data-stu-id="a0343-120">A file or folder name in the path contains a colon (:) or is in an invalid format (<xref:System.NotSupportedException>).</span></span>  
  
- <span data-ttu-id="a0343-121">`ShowUI`가 `True`로 설정되고, `onUserCancel`이 `ThrowException`으로 설정되고, 사용자가 작업을 취소한 경우(<xref:System.OperationCanceledException>)</span><span class="sxs-lookup"><span data-stu-id="a0343-121">`ShowUI` is set to `True`, `onUserCancel` is set to `ThrowException`, and the user has cancelled the operation (<xref:System.OperationCanceledException>).</span></span>  
  
- <span data-ttu-id="a0343-122">`ShowUI`가 `True`로 설정되고, `onUserCancel`이 `ThrowException`으로 설정되고, 지정하지 않은 I/O 오류가 발생하는 경우(<xref:System.OperationCanceledException>)</span><span class="sxs-lookup"><span data-stu-id="a0343-122">`ShowUI` is set to `True`, `onUserCancel` is set to `ThrowException`, and an unspecified I/O error occurs (<xref:System.OperationCanceledException>).</span></span>  
  
- <span data-ttu-id="a0343-123">경로가 시스템 정의 최대 길이를 초과하는 경우(<xref:System.IO.PathTooLongException>)</span><span class="sxs-lookup"><span data-stu-id="a0343-123">The path exceeds the system-defined maximum length (<xref:System.IO.PathTooLongException>).</span></span>  
  
- <span data-ttu-id="a0343-124">사용자에게 필요한 권한이 없는 경우(<xref:System.UnauthorizedAccessException>)</span><span class="sxs-lookup"><span data-stu-id="a0343-124">The user does not have required permission (<xref:System.UnauthorizedAccessException>).</span></span>  
  
- <span data-ttu-id="a0343-125">경로를 보는 데 필요한 권한이 사용자에게 없는 경우(<xref:System.Security.SecurityException>)</span><span class="sxs-lookup"><span data-stu-id="a0343-125">The user lacks necessary permissions to view the path (<xref:System.Security.SecurityException>).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a0343-126">참고 항목</span><span class="sxs-lookup"><span data-stu-id="a0343-126">See also</span></span>

- <xref:Microsoft.VisualBasic.FileIO.FileSystem>
- <xref:Microsoft.VisualBasic.FileIO.FileSystem.CopyFile%2A>
- <xref:Microsoft.VisualBasic.FileIO.UICancelOption>
- [<span data-ttu-id="a0343-127">방법: 특정 패턴의 파일을 디렉터리로 복사</span><span class="sxs-lookup"><span data-stu-id="a0343-127">How to: Copy Files with a Specific Pattern to a Directory</span></span>](how-to-copy-files-with-a-specific-pattern-to-a-directory.md)
- [<span data-ttu-id="a0343-128">방법: 동일한 디렉터리에 파일의 복사본 만들기</span><span class="sxs-lookup"><span data-stu-id="a0343-128">How to: Create a Copy of a File in the Same Directory</span></span>](how-to-create-a-copy-of-a-file-in-the-same-directory.md)
- [<span data-ttu-id="a0343-129">방법: 디렉터리를 다른 디렉터리에 복사</span><span class="sxs-lookup"><span data-stu-id="a0343-129">How to: Copy a Directory to Another Directory</span></span>](how-to-copy-a-directory-to-another-directory.md)
- [<span data-ttu-id="a0343-130">방법: 파일 이름 바꾸기</span><span class="sxs-lookup"><span data-stu-id="a0343-130">How to: Rename a File</span></span>](how-to-rename-a-file.md)
