---
title: 파일 시스템 및 레지스트리 - C# 프로그래밍 가이드
ms.date: 07/20/2015
helpviewer_keywords:
- file system [C#]
- registry [C#]
- files [C#]
ms.assetid: 0f2511cf-2b02-4b41-b001-b1754677c38f
ms.openlocfilehash: f160df456f1a3437e11de2d3660d158ae4d4bb67
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/15/2020
ms.locfileid: "75900571"
---
# <a name="file-system-and-the-registry-c-programming-guide"></a><span data-ttu-id="0abd7-102">파일 시스템 및 레지스트리(C# 프로그래밍 가이드)</span><span class="sxs-lookup"><span data-stu-id="0abd7-102">File system and the registry (C# Programming Guide)</span></span>

<span data-ttu-id="0abd7-103">다음 문서들은 C# 및 .NET를 사용하여 파일, 폴더 및 레지스트리에서 다양한 기본 작업을 수행하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="0abd7-103">The following articles show how to use C# and .NET to perform various basic operations on files, folders, and the registry.</span></span>

## <a name="in-this-section"></a><span data-ttu-id="0abd7-104">섹션 내용</span><span class="sxs-lookup"><span data-stu-id="0abd7-104">In this section</span></span>

|<span data-ttu-id="0abd7-105">**제목**</span><span class="sxs-lookup"><span data-stu-id="0abd7-105">**Title**</span></span>|<span data-ttu-id="0abd7-106">**설명**</span><span class="sxs-lookup"><span data-stu-id="0abd7-106">**Description**</span></span>|
|---------------|---------------------|
|[<span data-ttu-id="0abd7-107">디렉터리 트리를 반복하는 방법</span><span class="sxs-lookup"><span data-stu-id="0abd7-107">How to iterate through a directory tree</span></span>](how-to-iterate-through-a-directory-tree.md)|<span data-ttu-id="0abd7-108">디렉터리 트리를 수동으로 반복하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="0abd7-108">Shows how to manually iterate through a directory tree.</span></span>|
|[<span data-ttu-id="0abd7-109">파일, 폴더 및 드라이브에 대한 정보를 가져오는 방법</span><span class="sxs-lookup"><span data-stu-id="0abd7-109">How to get information about files, folders, and drives</span></span>](how-to-get-information-about-files-folders-and-drives.md)|<span data-ttu-id="0abd7-110">파일, 폴더 및 드라이브에 대한 생성 시간 및 크기와 같은 정보를 검색하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="0abd7-110">Shows how to retrieve information such as creation times and size, about files, folders and drives.</span></span>|
|[<span data-ttu-id="0abd7-111">파일 또는 폴더를 만드는 방법</span><span class="sxs-lookup"><span data-stu-id="0abd7-111">How to create a file or folder</span></span>](how-to-create-a-file-or-folder.md)|<span data-ttu-id="0abd7-112">새 파일 또는 폴더를 만드는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="0abd7-112">Shows how to create a new file or folder.</span></span>|
|[<span data-ttu-id="0abd7-113">파일 및 폴더를 복사, 삭제, 이동하는 방법(C# 프로그래밍 가이드)</span><span class="sxs-lookup"><span data-stu-id="0abd7-113">How to copy, delete, and move files and folders (C# Programming Guide)</span></span>](how-to-copy-delete-and-move-files-and-folders.md)|<span data-ttu-id="0abd7-114">파일 및 폴더를 복사, 삭제 및 이동하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="0abd7-114">Shows how to copy, delete and move files and folders.</span></span>|
|[<span data-ttu-id="0abd7-115">파일 작업에 진행률 대화 상자를 제공하는 방법</span><span class="sxs-lookup"><span data-stu-id="0abd7-115">How to provide a progress dialog box for file operations</span></span>](how-to-provide-a-progress-dialog-box-for-file-operations.md)|<span data-ttu-id="0abd7-116">특정 파일 작업에 대한 표준 Windows 진행률 대화 상자를 표시하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="0abd7-116">Shows how to display a standard Windows progress dialog for certain file operations.</span></span>|
|[<span data-ttu-id="0abd7-117">텍스트 파일에 쓰는 방법</span><span class="sxs-lookup"><span data-stu-id="0abd7-117">How to write to a text file</span></span>](how-to-write-to-a-text-file.md)|<span data-ttu-id="0abd7-118">텍스트 파일에 쓰는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="0abd7-118">Shows how to write to a text file.</span></span>|
|[<span data-ttu-id="0abd7-119">텍스트 파일에서 읽는 방법</span><span class="sxs-lookup"><span data-stu-id="0abd7-119">How to read from a text file</span></span>](how-to-read-from-a-text-file.md)|<span data-ttu-id="0abd7-120">텍스트 파일에서 읽는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="0abd7-120">Shows how to read from a text file.</span></span>|
|[<span data-ttu-id="0abd7-121">텍스트 파일을 한 번에 한 줄씩 읽는 방법</span><span class="sxs-lookup"><span data-stu-id="0abd7-121">How to read a text file one line at a time</span></span>](how-to-read-a-text-file-one-line-at-a-time.md)|<span data-ttu-id="0abd7-122">한 번에 하나씩 파일에서 텍스트를 검색하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="0abd7-122">Shows how to retrieve text from a file one line at a time.</span></span>|
|[<span data-ttu-id="0abd7-123">레지스트리에 키를 만드는 방법</span><span class="sxs-lookup"><span data-stu-id="0abd7-123">How to create a key in the registry</span></span>](how-to-create-a-key-in-the-registry.md)|<span data-ttu-id="0abd7-124">시스템 레지스트리에 키를 작성하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="0abd7-124">Shows how to write a key to the system registry.</span></span>|

## <a name="related-sections"></a><span data-ttu-id="0abd7-125">관련 단원</span><span class="sxs-lookup"><span data-stu-id="0abd7-125">Related sections</span></span>

- [<span data-ttu-id="0abd7-126">파일 및 스트림 I/O</span><span class="sxs-lookup"><span data-stu-id="0abd7-126">File and Stream I/O</span></span>](../../../standard/io/index.md)
- [<span data-ttu-id="0abd7-127">파일 및 폴더를 복사, 삭제, 이동하는 방법(C# 프로그래밍 가이드)</span><span class="sxs-lookup"><span data-stu-id="0abd7-127">How to copy, delete, and move files and folders (C# Programming Guide)</span></span>](how-to-copy-delete-and-move-files-and-folders.md)
- [<span data-ttu-id="0abd7-128">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="0abd7-128">C# Programming Guide</span></span>](../index.md)
- <xref:System.IO?displayProperty=nameWithType>
