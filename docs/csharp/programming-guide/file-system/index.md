---
title: 파일 시스템 및 레지스트리 - C# 프로그래밍 가이드
ms.date: 07/20/2015
helpviewer_keywords:
- file system [C#]
- registry [C#]
- files [C#]
ms.assetid: 0f2511cf-2b02-4b41-b001-b1754677c38f
ms.openlocfilehash: 2540c816a102a7f11f1f103b993194cccf0f4688
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/07/2020
ms.locfileid: "75704523"
---
# <a name="file-system-and-the-registry-c-programming-guide"></a><span data-ttu-id="78d2b-102">파일 시스템 및 레지스트리(C# 프로그래밍 가이드)</span><span class="sxs-lookup"><span data-stu-id="78d2b-102">File System and the Registry (C# Programming Guide)</span></span>
<span data-ttu-id="78d2b-103">다음 항목에서는 C# 및 .NET Framework를 사용하여 파일, 폴더 및 레지스트리에 대한 다양한 기본 작업을 수행하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="78d2b-103">The following topics show how to use C# and the .NET Framework to perform various basic operations on files, folders, and the Registry.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="78d2b-104">섹션 내용</span><span class="sxs-lookup"><span data-stu-id="78d2b-104">In This Section</span></span>  
  
|<span data-ttu-id="78d2b-105">**제목**</span><span class="sxs-lookup"><span data-stu-id="78d2b-105">**Title**</span></span>|<span data-ttu-id="78d2b-106">**설명**</span><span class="sxs-lookup"><span data-stu-id="78d2b-106">**Description**</span></span>|  
|---------------|---------------------|  
|[<span data-ttu-id="78d2b-107">디렉터리 트리를 반복하는 방법</span><span class="sxs-lookup"><span data-stu-id="78d2b-107">How to iterate through a directory tree</span></span>](./how-to-iterate-through-a-directory-tree.md)|<span data-ttu-id="78d2b-108">디렉터리 트리를 수동으로 반복하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="78d2b-108">Shows how to manually iterate through a directory tree.</span></span>|  
|[<span data-ttu-id="78d2b-109">파일, 폴더 및 드라이브에 대한 정보를 가져오는 방법</span><span class="sxs-lookup"><span data-stu-id="78d2b-109">How to get information about files, folders, and drives</span></span>](./how-to-get-information-about-files-folders-and-drives.md)|<span data-ttu-id="78d2b-110">파일, 폴더 및 드라이브에 대한 생성 시간 및 크기와 같은 정보를 검색하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="78d2b-110">Shows how to retrieve information such as creation times and size, about files, folders and drives.</span></span>|  
|[<span data-ttu-id="78d2b-111">파일 또는 폴더를 만드는 방법</span><span class="sxs-lookup"><span data-stu-id="78d2b-111">How to create a file or folder</span></span>](./how-to-create-a-file-or-folder.md)|<span data-ttu-id="78d2b-112">새 파일 또는 폴더를 만드는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="78d2b-112">Shows how to create a new file or folder.</span></span>|  
|[<span data-ttu-id="78d2b-113">파일 및 폴더를 복사, 삭제, 이동하는 방법(C# 프로그래밍 가이드)</span><span class="sxs-lookup"><span data-stu-id="78d2b-113">How to copy, delete, and move files and folders (C# Programming Guide)</span></span>](./how-to-copy-delete-and-move-files-and-folders.md)|<span data-ttu-id="78d2b-114">파일 및 폴더를 복사, 삭제 및 이동하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="78d2b-114">Shows how to copy, delete and move files and folders.</span></span>|  
|[<span data-ttu-id="78d2b-115">파일 작업에 진행률 대화 상자를 제공하는 방법</span><span class="sxs-lookup"><span data-stu-id="78d2b-115">How to provide a progress dialog box for file operations</span></span>](./how-to-provide-a-progress-dialog-box-for-file-operations.md)|<span data-ttu-id="78d2b-116">특정 파일 작업에 대한 표준 Windows 진행률 대화 상자를 표시하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="78d2b-116">Shows how to display a standard Windows progress dialog for certain file operations.</span></span>|  
|[<span data-ttu-id="78d2b-117">텍스트 파일에 쓰는 방법</span><span class="sxs-lookup"><span data-stu-id="78d2b-117">How to write to a text file</span></span>](./how-to-write-to-a-text-file.md)|<span data-ttu-id="78d2b-118">텍스트 파일에 쓰는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="78d2b-118">Shows how to write to a text file.</span></span>|  
|[<span data-ttu-id="78d2b-119">텍스트 파일에서 읽는 방법</span><span class="sxs-lookup"><span data-stu-id="78d2b-119">How to read from a text file</span></span>](./how-to-read-from-a-text-file.md)|<span data-ttu-id="78d2b-120">텍스트 파일에서 읽는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="78d2b-120">Shows how to read from a text file.</span></span>|  
|[<span data-ttu-id="78d2b-121">텍스트 파일을 한 번에 한 줄씩 읽는 방법</span><span class="sxs-lookup"><span data-stu-id="78d2b-121">How to read a text file one line at a time</span></span>](./how-to-read-a-text-file-one-line-at-a-time.md)|<span data-ttu-id="78d2b-122">한 번에 하나씩 파일에서 텍스트를 검색하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="78d2b-122">Shows how to retrieve text from a file one line at a time.</span></span>|  
|[<span data-ttu-id="78d2b-123">레지스트리에 키를 만드는 방법</span><span class="sxs-lookup"><span data-stu-id="78d2b-123">How to create a key in the registry</span></span>](./how-to-create-a-key-in-the-registry.md)|<span data-ttu-id="78d2b-124">시스템 레지스트리에 키를 작성하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="78d2b-124">Shows how to write a key to the system registry.</span></span>|  
  
## <a name="related-sections"></a><span data-ttu-id="78d2b-125">관련 단원</span><span class="sxs-lookup"><span data-stu-id="78d2b-125">Related Sections</span></span>  
 [<span data-ttu-id="78d2b-126">파일 및 스트림 I/O</span><span class="sxs-lookup"><span data-stu-id="78d2b-126">File and Stream I/O</span></span>](../../../standard/io/index.md)  
  
 [<span data-ttu-id="78d2b-127">파일 및 폴더를 복사, 삭제, 이동하는 방법(C# 프로그래밍 가이드)</span><span class="sxs-lookup"><span data-stu-id="78d2b-127">How to copy, delete, and move files and folders (C# Programming Guide)</span></span>](./how-to-copy-delete-and-move-files-and-folders.md)
  
 [<span data-ttu-id="78d2b-128">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="78d2b-128">C# Programming Guide</span></span>](../index.md)  
  
 [<span data-ttu-id="78d2b-129">파일, 폴더 및 드라이브</span><span class="sxs-lookup"><span data-stu-id="78d2b-129">Files, Folders and Drives</span></span>](./index.md)  
  
 <xref:System.IO?displayProperty=nameWithType>
