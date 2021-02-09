---
description: '자세한 정보: 방법: Visual Basic에서 파일 삭제'
title: '방법: 파일 삭제'
ms.date: 07/20/2015
helpviewer_keywords:
- Delete method [Visual Basic]
- files [Visual Basic], deleting
- files [Visual Basic], manipulating
- File object
ms.assetid: 4b721769-3e45-4be7-b7fe-b08dc4141b44
ms.openlocfilehash: 49bfe2e4a0d9114e2f653ae14dab303e35e2dfeb
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99797577"
---
# <a name="how-to-delete-a-file-in-visual-basic"></a><span data-ttu-id="8c35b-103">방법: Visual Basic에서 파일 삭제</span><span class="sxs-lookup"><span data-stu-id="8c35b-103">How to: Delete a File in Visual Basic</span></span>

<span data-ttu-id="8c35b-104">`My.Computer.FileSystem` 개체의 `DeleteFile` 메서드를 사용하면 파일을 삭제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8c35b-104">The `DeleteFile` method of the `My.Computer.FileSystem` object allows you to delete a file.</span></span> <span data-ttu-id="8c35b-105">삭제된 파일을 **휴지통** 으로 보낼지 여부, 사용자에게 파일 삭제를 확인하는 메시지를 표시할지 여부, 사용자가 작업을 취소할 때 수행할 작업 등의 옵션이 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="8c35b-105">Among the options it offers are: whether to send the deleted file to the **Recycle Bin**, whether to ask the user to confirm that the file should be deleted, and what to do when the user cancels the operation.</span></span>  
  
### <a name="to-delete-a-text-file"></a><span data-ttu-id="8c35b-106">텍스트 파일을 삭제하려면</span><span class="sxs-lookup"><span data-stu-id="8c35b-106">To delete a text file</span></span>  
  
- <span data-ttu-id="8c35b-107">`DeleteFile` 메서드를 사용하여 파일을 삭제합니다.</span><span class="sxs-lookup"><span data-stu-id="8c35b-107">Use the `DeleteFile` method to delete the file.</span></span> <span data-ttu-id="8c35b-108">다음 코드에서는 `test.txt`라는 파일을 삭제하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="8c35b-108">The following code demonstrates how to delete the file named `test.txt`.</span></span>  
  
     [!code-vb[VbVbcnMyFileSystem#22](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnMyFileSystem/VB/Class1.vb#22)]  
  
### <a name="to-delete-a-text-file-and-ask-the-user-to-confirm-that-the-file-should-be-deleted"></a><span data-ttu-id="8c35b-109">텍스트 파일을 삭제하고 사용자에게 파일 삭제를 확인하는 메시지를 표시하려면</span><span class="sxs-lookup"><span data-stu-id="8c35b-109">To delete a text file and ask the user to confirm that the file should be deleted</span></span>  
  
- <span data-ttu-id="8c35b-110">`showUI`를 `AllDialogs`로 설정하여 `DeleteFile` 메서드를 통해 파일을 삭제합니다.</span><span class="sxs-lookup"><span data-stu-id="8c35b-110">Use the `DeleteFile` method to delete the file, setting `showUI` to `AllDialogs`.</span></span> <span data-ttu-id="8c35b-111">다음 코드에서는 `test.txt`라는 파일을 삭제하고 사용자가 파일 삭제를 확인할 수 있도록 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="8c35b-111">The following code demonstrates how to delete the file named `test.txt` and allow the user to confirm that the file should be deleted.</span></span>  
  
     [!code-vb[VbFileIOMisc#9](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbFileIOMisc/VB/Class1.vb#9)]  
  
### <a name="to-delete-a-text-file-and-send-it-to-the-recycle-bin"></a><span data-ttu-id="8c35b-112">텍스트 파일을 삭제하고 휴지통으로 보내려면</span><span class="sxs-lookup"><span data-stu-id="8c35b-112">To delete a text file and send it to the Recycle Bin</span></span>  
  
- <span data-ttu-id="8c35b-113">`recycle` 매개 변수에 대해 `SendToRecycleBin`을 지정하여 `DeleteFile` 메서드를 통해 파일을 삭제합니다.</span><span class="sxs-lookup"><span data-stu-id="8c35b-113">Use the `DeleteFile` method to delete the file, specifying `SendToRecycleBin` for the `recycle` parameter.</span></span> <span data-ttu-id="8c35b-114">다음 코드에서는 `test.txt`라는 파일을 삭제하고 **휴지통** 으로 보내는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="8c35b-114">The following code demonstrates how to delete the file named `test.txt` and send it to the **Recycle Bin**.</span></span>  
  
     [!code-vb[VbFileIOMisc#10](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbFileIOMisc/VB/Class1.vb#10)]  
  
## <a name="robust-programming"></a><span data-ttu-id="8c35b-115">강력한 프로그래밍</span><span class="sxs-lookup"><span data-stu-id="8c35b-115">Robust Programming</span></span>  

 <span data-ttu-id="8c35b-116">다음 조건에서 예외가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="8c35b-116">The following conditions may cause an exception:</span></span>  
  
- <span data-ttu-id="8c35b-117">길이가 0인 문자열이거나, 공백만 포함하거나, 잘못된 문자를 포함하거나, 경로가 디바이스 경로인 경우(\\\\.\\로 시작됨)와 같은 여러 가지 이유 중 하나로 경로가 올바르지 않은 경우(<xref:System.ArgumentException>)</span><span class="sxs-lookup"><span data-stu-id="8c35b-117">The path is not valid for one of the following reasons: it is a zero-length string, it contains only white space, it contains invalid characters, or it is a device path (starts with \\\\.\\) (<xref:System.ArgumentException>).</span></span>  
  
- <span data-ttu-id="8c35b-118">경로가 `Nothing` 이기 때문에 올바르지 않은 경우(<xref:System.ArgumentNullException>)</span><span class="sxs-lookup"><span data-stu-id="8c35b-118">The path is not valid because it is `Nothing` (<xref:System.ArgumentNullException>).</span></span>  
  
- <span data-ttu-id="8c35b-119">경로가 시스템 정의 최대 길이를 초과하는 경우(<xref:System.IO.PathTooLongException>)</span><span class="sxs-lookup"><span data-stu-id="8c35b-119">The path exceeds the system-defined maximum length (<xref:System.IO.PathTooLongException>).</span></span>  
  
- <span data-ttu-id="8c35b-120">경로의 파일 이름이나 폴더 이름에 콜론(:)이 있거나 이름의 형식이 잘못된 경우(<xref:System.NotSupportedException>)</span><span class="sxs-lookup"><span data-stu-id="8c35b-120">A file or folder name in the path contains a colon (:) or is in an invalid format (<xref:System.NotSupportedException>).</span></span>  
  
- <span data-ttu-id="8c35b-121">파일을 사용 중인 경우(<xref:System.IO.IOException>)</span><span class="sxs-lookup"><span data-stu-id="8c35b-121">The file is in use (<xref:System.IO.IOException>).</span></span>  
  
- <span data-ttu-id="8c35b-122">경로를 보는 데 필요한 권한이 사용자에게 없는 경우(<xref:System.Security.SecurityException>)</span><span class="sxs-lookup"><span data-stu-id="8c35b-122">The user lacks necessary permissions to view the path (<xref:System.Security.SecurityException>).</span></span>  
  
- <span data-ttu-id="8c35b-123">파일이 없는 경우(<xref:System.IO.FileNotFoundException>)</span><span class="sxs-lookup"><span data-stu-id="8c35b-123">The file does not exist (<xref:System.IO.FileNotFoundException>).</span></span>  
  
- <span data-ttu-id="8c35b-124">사용자에게 파일을 삭제할 수 있는 권한이 없거나 파일이 읽기 전용인 경우(<xref:System.UnauthorizedAccessException>)</span><span class="sxs-lookup"><span data-stu-id="8c35b-124">The user does not have permission to delete the file, or the file is read-only (<xref:System.UnauthorizedAccessException>).</span></span>  
  
- <span data-ttu-id="8c35b-125">사용자에게 충분한 권한이 없는 부분 신뢰 상황인 경우(<xref:System.Security.SecurityException>)</span><span class="sxs-lookup"><span data-stu-id="8c35b-125">A partial-trust situation exists in which the user does not have sufficient permissions (<xref:System.Security.SecurityException>).</span></span>  
  
- <span data-ttu-id="8c35b-126">사용자가 작업을 취소하고 `onUserCancel`이 `ThrowException`으로 설정된 경우(<xref:System.OperationCanceledException>)</span><span class="sxs-lookup"><span data-stu-id="8c35b-126">The user cancelled the operation and `onUserCancel` is set to `ThrowException` (<xref:System.OperationCanceledException>).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8c35b-127">참고 항목</span><span class="sxs-lookup"><span data-stu-id="8c35b-127">See also</span></span>

- <xref:Microsoft.VisualBasic.FileIO.UICancelOption>
- <xref:Microsoft.VisualBasic.FileIO.FileSystem>
- <xref:Microsoft.VisualBasic.FileIO.UIOption>
- <xref:Microsoft.VisualBasic.FileIO.RecycleOption>
- [<span data-ttu-id="8c35b-128">방법: 디렉터리의 파일 컬렉션 가져오기</span><span class="sxs-lookup"><span data-stu-id="8c35b-128">How to: Get the Collection of Files in a Directory</span></span>](how-to-get-the-collection-of-files-in-a-directory.md)
