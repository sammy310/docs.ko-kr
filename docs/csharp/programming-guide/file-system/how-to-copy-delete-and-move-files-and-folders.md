---
title: 파일 및 폴더를 복사, 삭제, 이동하는 방법 - C# 프로그래밍 가이드
ms.date: 07/20/2015
helpviewer_keywords:
- I/O [C#]
ms.assetid: 62e52cd7-9597-4e4a-acf9-1315f5cdbf05
ms.openlocfilehash: 662f0ab3b9e69aa8bfb0085f42f577b850029e4d
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/14/2020
ms.locfileid: "75712275"
---
# <a name="how-to-copy-delete-and-move-files-and-folders-c-programming-guide"></a><span data-ttu-id="500cb-102">파일 및 폴더를 복사, 삭제, 이동하는 방법(C# 프로그래밍 가이드)</span><span class="sxs-lookup"><span data-stu-id="500cb-102">How to copy, delete, and move files and folders (C# Programming Guide)</span></span>
<span data-ttu-id="500cb-103">다음 예제에서는 <xref:System.IO?displayProperty=nameWithType> 네임스페이스의 <xref:System.IO.File?displayProperty=nameWithType>, <xref:System.IO.Directory?displayProperty=nameWithType>, <xref:System.IO.FileInfo?displayProperty=nameWithType>, <xref:System.IO.DirectoryInfo?displayProperty=nameWithType> 클래스를 사용하여 파일과 폴더를 동기 방식으로 복사, 이동 및 삭제하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="500cb-103">The following examples show how to copy, move, and delete files and folders in a synchronous manner by using the <xref:System.IO.File?displayProperty=nameWithType>, <xref:System.IO.Directory?displayProperty=nameWithType>, <xref:System.IO.FileInfo?displayProperty=nameWithType>, and <xref:System.IO.DirectoryInfo?displayProperty=nameWithType> classes from the <xref:System.IO?displayProperty=nameWithType> namespace.</span></span> <span data-ttu-id="500cb-104">이러한 예제는 진행률 표시줄이나 다른 사용자 인터페이스를 제공하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="500cb-104">These examples do not provide a progress bar or any other user interface.</span></span> <span data-ttu-id="500cb-105">표준 진행률 대화 상자를 제공하려는 경우 [파일 작업에 대한 진행률 대화 상자를 제공하는 방법](how-to-provide-a-progress-dialog-box-for-file-operations.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="500cb-105">If you want to provide a standard progress dialog box, see [How to provide a progress dialog box for file operations](how-to-provide-a-progress-dialog-box-for-file-operations.md).</span></span>  
  
 <span data-ttu-id="500cb-106"><xref:System.IO.FileSystemWatcher?displayProperty=nameWithType>를 사용하여 여러 파일에 대해 작업할 때 진행률을 계산할 수 있는 이벤트를 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="500cb-106">Use <xref:System.IO.FileSystemWatcher?displayProperty=nameWithType> to provide events that will enable you to calculate the progress when operating on multiple files.</span></span> <span data-ttu-id="500cb-107">또 다른 방법은 플랫폼 호출을 사용하여 Windows Shell에서 적절한 파일 관련 메서드를 호출하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="500cb-107">Another approach is to use platform invoke to call the relevant file-related methods in the Windows Shell.</span></span> <span data-ttu-id="500cb-108">이러한 파일 작업을 비동기적으로 수행하는 방법에 대한 자세한 내용은 [비동기 파일 I/O](../../../standard/io/asynchronous-file-i-o.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="500cb-108">For information about how to perform these file operations asynchronously, see [Asynchronous File I/O](../../../standard/io/asynchronous-file-i-o.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="500cb-109">예제</span><span class="sxs-lookup"><span data-stu-id="500cb-109">Example</span></span>  
 <span data-ttu-id="500cb-110">다음 예제에서는 파일 및 디렉터리를 복사하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="500cb-110">The following example shows how to copy files and directories.</span></span>  
  
 [!code-csharp[csFilesandFolders#7](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csFilesAndFolders/CS/FileIteration.cs#7)]  
  
## <a name="example"></a><span data-ttu-id="500cb-111">예제</span><span class="sxs-lookup"><span data-stu-id="500cb-111">Example</span></span>  
 <span data-ttu-id="500cb-112">다음 예제에서는 파일 및 디렉터리를 이동하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="500cb-112">The following example shows how to move files and directories.</span></span>  
  
 [!code-csharp[csFilesandFolders#8](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csFilesAndFolders/CS/FileIteration.cs#8)]  
  
## <a name="example"></a><span data-ttu-id="500cb-113">예제</span><span class="sxs-lookup"><span data-stu-id="500cb-113">Example</span></span>  
 <span data-ttu-id="500cb-114">다음 예제에서는 파일 및 디렉터리를 삭제하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="500cb-114">The following example shows how to delete files and directories.</span></span>  
  
 [!code-csharp[csFilesandFolders#9](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csFilesAndFolders/CS/FileIteration.cs#9)]  
  
## <a name="see-also"></a><span data-ttu-id="500cb-115">참고 항목</span><span class="sxs-lookup"><span data-stu-id="500cb-115">See also</span></span>

- <xref:System.IO?displayProperty=nameWithType>
- [<span data-ttu-id="500cb-116">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="500cb-116">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="500cb-117">파일 시스템 및 레지스트리(C# 프로그래밍 가이드)</span><span class="sxs-lookup"><span data-stu-id="500cb-117">File System and the Registry (C# Programming Guide)</span></span>](index.md)
- [<span data-ttu-id="500cb-118">파일 작업에 진행률 대화 상자를 제공하는 방법</span><span class="sxs-lookup"><span data-stu-id="500cb-118">How to provide a progress dialog box for file operations</span></span>](how-to-provide-a-progress-dialog-box-for-file-operations.md)
- [<span data-ttu-id="500cb-119">파일 및 스트림 I/O</span><span class="sxs-lookup"><span data-stu-id="500cb-119">File and Stream I/O</span></span>](../../../standard/io/index.md)
- [<span data-ttu-id="500cb-120">공통적인 I/O 작업</span><span class="sxs-lookup"><span data-stu-id="500cb-120">Common I/O Tasks</span></span>](../../../standard/io/common-i-o-tasks.md)
