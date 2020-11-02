---
title: '방법: 디렉터리 및 파일 열거'
description: .NET에서 배열보다 더 나은 성능을 제공할 수 있는 열거 가능한 컬렉션을 사용하여 디렉터리와 파일을 열거하는 방법을 알아봅니다.
ms.date: 12/27/2018
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- I/O [.NET], enumerating directories and files
ms.assetid: 86b69a08-3bfa-4e5f-b4e1-3b7cb8478215
ms.openlocfilehash: 7a757fc97fd934f02592264c3a495c3efc435fd5
ms.sourcegitcommit: 7588b1f16b7608bc6833c05f91ae670c22ef56f8
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/02/2020
ms.locfileid: "93187894"
---
# <a name="how-to-enumerate-directories-and-files"></a><span data-ttu-id="637dc-103">방법: 디렉터리 및 파일 열거</span><span class="sxs-lookup"><span data-stu-id="637dc-103">How to: Enumerate directories and files</span></span>
<span data-ttu-id="637dc-104">열거 가능한 컬렉션은 대규모의 디렉터리 및 파일 컬렉션으로 작업할 때 배열보다 나은 성능을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="637dc-104">Enumerable collections provide better performance than arrays when you work with large collections of directories and files.</span></span> <span data-ttu-id="637dc-105">디렉터리 및 파일을 열거하려면 디렉터리, 파일 이름이나 해당 <xref:System.IO.DirectoryInfo>, <xref:System.IO.FileInfo> 또는 <xref:System.IO.FileSystemInfo> 개체의 열거할 수 있는 컬렉션을 반환하는 메서드를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="637dc-105">To enumerate directories and files, use methods that return an enumerable collection of directory or file names, or their <xref:System.IO.DirectoryInfo>, <xref:System.IO.FileInfo>, or <xref:System.IO.FileSystemInfo> objects.</span></span>  
  
<span data-ttu-id="637dc-106">디렉터리 또는 파일의 이름만 검색하고 반환하려면 <xref:System.IO.Directory> 클래스의 열거 메서드를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="637dc-106">If you want to search and return only the names of directories or files, use the enumeration methods of the <xref:System.IO.Directory> class.</span></span> <span data-ttu-id="637dc-107">디렉터리 또는 파일의 다른 속성을 검색하고 반환하려면 <xref:System.IO.DirectoryInfo> 및 <xref:System.IO.FileSystemInfo> 클래스를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="637dc-107">If you want to search and return other properties of directories or files, use the <xref:System.IO.DirectoryInfo> and <xref:System.IO.FileSystemInfo> classes.</span></span>  
  
<span data-ttu-id="637dc-108">이러한 메서드의 열거 가능한 컬렉션은 <xref:System.Collections.Generic.List%601>과 같은 컬렉션 클래스의 생성자에 대한 <xref:System.Collections.Generic.IEnumerable%601> 매개 변수로 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="637dc-108">You can use enumerable collections from these methods as the <xref:System.Collections.Generic.IEnumerable%601> parameter for constructors of collection classes like <xref:System.Collections.Generic.List%601>.</span></span>  
  
<span data-ttu-id="637dc-109">다음 표에는 열거 가능한 파일 및 디렉터리 컬렉션을 반환하는 메서드가 요약되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="637dc-109">The following table summarizes the methods that return enumerable collections of files and directories:</span></span>  
  
|<span data-ttu-id="637dc-110">검색 및 반환하려면</span><span class="sxs-lookup"><span data-stu-id="637dc-110">To search and return</span></span>|<span data-ttu-id="637dc-111">메서드 사용</span><span class="sxs-lookup"><span data-stu-id="637dc-111">Use method</span></span>|  
|------------------|-------------------------------------|-------------------|  
|<span data-ttu-id="637dc-112">디렉터리 이름</span><span class="sxs-lookup"><span data-stu-id="637dc-112">Directory names</span></span>|<xref:System.IO.Directory.EnumerateDirectories%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="637dc-113">디렉터리 정보(<xref:System.IO.DirectoryInfo>)</span><span class="sxs-lookup"><span data-stu-id="637dc-113">Directory information (<xref:System.IO.DirectoryInfo>)</span></span>|<xref:System.IO.DirectoryInfo.EnumerateDirectories%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="637dc-114">파일 이름</span><span class="sxs-lookup"><span data-stu-id="637dc-114">File names</span></span>|<xref:System.IO.Directory.EnumerateFiles%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="637dc-115">파일 정보(<xref:System.IO.FileInfo>)</span><span class="sxs-lookup"><span data-stu-id="637dc-115">File information (<xref:System.IO.FileInfo>)</span></span>|<xref:System.IO.DirectoryInfo.EnumerateFiles%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="637dc-116">파일 시스템 항목 이름</span><span class="sxs-lookup"><span data-stu-id="637dc-116">File system entry names</span></span>|<xref:System.IO.Directory.EnumerateFileSystemEntries%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="637dc-117">파일 시스템 항목 정보(<xref:System.IO.FileSystemInfo>)</span><span class="sxs-lookup"><span data-stu-id="637dc-117">File system entry information (<xref:System.IO.FileSystemInfo>)</span></span>|<xref:System.IO.DirectoryInfo.EnumerateFileSystemInfos%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="637dc-118">디렉터리 및 파일 이름</span><span class="sxs-lookup"><span data-stu-id="637dc-118">Directory and file names</span></span> |<xref:System.IO.Directory.EnumerateFileSystemEntries%2A?displayProperty=nameWithType>|  

> [!NOTE]
> <span data-ttu-id="637dc-119">선택적 <xref:System.IO.SearchOption> 열거형의 <xref:System.IO.SearchOption.AllDirectories> 옵션을 사용하면 부모 디렉터리의 하위 디렉터리에 있는 모든 파일을 즉시 열거할 수 있지만, <xref:System.UnauthorizedAccessException> 오류로 인해 열거가 불완전할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="637dc-119">Although you can immediately enumerate all the files in the subdirectories of a parent directory by using the <xref:System.IO.SearchOption.AllDirectories> option of the optional <xref:System.IO.SearchOption> enumeration, <xref:System.UnauthorizedAccessException> errors may make the enumeration incomplete.</span></span> <span data-ttu-id="637dc-120">먼저 디렉터리를 열거한 다음, 파일을 열거하면 이러한 예외를 catch할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="637dc-120">You can catch these exceptions by first enumerating directories and then enumerating files.</span></span>  
  
## <a name="examples-use-the-directory-class"></a><span data-ttu-id="637dc-121">예: 디렉터리 클래스 사용</span><span class="sxs-lookup"><span data-stu-id="637dc-121">Examples: Use the Directory class</span></span>  
  
<span data-ttu-id="637dc-122">다음 예제에서는 <xref:System.IO.Directory.EnumerateDirectories%28System.String%29?displayProperty=nameWithType> 메서드를 사용하여 지정된 경로의 최상위 디렉터리 이름 목록을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="637dc-122">The following example uses the <xref:System.IO.Directory.EnumerateDirectories%28System.String%29?displayProperty=nameWithType> method to get a list of the top-level directory names in a specified path.</span></span>  

[!code-csharp[System.IO.EnumDirs1#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.io.enumdirs1/cs/program.cs#1)]
[!code-vb[System.IO.EnumDirs1#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.io.enumdirs1/vb/program.vb#1)]  

<span data-ttu-id="637dc-123">다음 예제에서는 <xref:System.IO.Directory.EnumerateFiles%28System.String%2CSystem.String%2CSystem.IO.SearchOption%29?displayProperty=nameWithType> 메서드를 사용하여 특정 패턴과 일치하는 디렉터리 및 하위 디렉터리의 모든 파일 이름을 재귀적으로 열거합니다.</span><span class="sxs-lookup"><span data-stu-id="637dc-123">The following example uses the <xref:System.IO.Directory.EnumerateFiles%28System.String%2CSystem.String%2CSystem.IO.SearchOption%29?displayProperty=nameWithType> method to recursively enumerate all file names in a directory and subdirectories that match a certain pattern.</span></span> <span data-ttu-id="637dc-124">그런 다음, 각 파일의 각 줄을 읽고 해당 파일 이름 및 경로가 있는 지정된 문자열이 포함된 줄을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="637dc-124">It then reads each line of each file and displays the lines that contain a specified string, with their filenames and paths.</span></span>

[!code-csharp[System.IO.Directory.EnumerateFiles#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.io.directory.enumeratefiles/cs/program.cs#1)]
[!code-vb[System.IO.Directory.EnumerateFiles#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.io.directory.enumeratefiles/vb/program.vb#1)]  
  
## <a name="examples-use-the-directoryinfo-class"></a><span data-ttu-id="637dc-125">예: DirectoryInfo 클래스 사용</span><span class="sxs-lookup"><span data-stu-id="637dc-125">Examples: Use the DirectoryInfo class</span></span>  
  
<span data-ttu-id="637dc-126">다음 예제에서는 <xref:System.IO.DirectoryInfo.EnumerateDirectories%2A?displayProperty=nameWithType> 메서드를 사용하여 <xref:System.IO.FileSystemInfo.CreationTimeUtc>가 특정 <xref:System.DateTime> 값보다 이전인 최상위 디렉터리의 컬렉션을 나열합니다.</span><span class="sxs-lookup"><span data-stu-id="637dc-126">The following example uses the <xref:System.IO.DirectoryInfo.EnumerateDirectories%2A?displayProperty=nameWithType> method to list a collection of top-level directories whose <xref:System.IO.FileSystemInfo.CreationTimeUtc> is earlier than a certain <xref:System.DateTime> value.</span></span>  

[!code-csharp[System.IO.DirectoryInfo.EnumDirs#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.io.directoryinfo.enumdirs/cs/program.cs)]
[!code-vb[System.IO.DirectoryInfo.EnumDirs#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.io.directoryinfo.enumdirs/vb/module1.vb)]  
  
<span data-ttu-id="637dc-127">다음 예제에서는 <xref:System.IO.DirectoryInfo.EnumerateFiles%2A?displayProperty=nameWithType> 메서드를 사용하여 <xref:System.IO.FileInfo.Length>가 10MB를 초과하는 모든 파일을 나열합니다.</span><span class="sxs-lookup"><span data-stu-id="637dc-127">The following example uses the <xref:System.IO.DirectoryInfo.EnumerateFiles%2A?displayProperty=nameWithType> method to list all files whose <xref:System.IO.FileInfo.Length> exceeds 10MB.</span></span> <span data-ttu-id="637dc-128">이 예제는 먼저 최상위 디렉터리를 열거하여 가능한 권한 없는 액세스 예외를 catch하고 파일을 열거합니다.</span><span class="sxs-lookup"><span data-stu-id="637dc-128">This example first enumerates the top-level directories, to catch possible unauthorized access exceptions, and then enumerates the files.</span></span>  

[!code-csharp[System.IO.DirectoryInfo.EnumerateDirectories#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.io.directoryinfo.enumeratedirectories/cs/program.cs#1)]
[!code-vb[System.IO.DirectoryInfo.EnumerateDirectories#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.io.directoryinfo.enumeratedirectories/vb/program.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="637dc-129">참조</span><span class="sxs-lookup"><span data-stu-id="637dc-129">See also</span></span>

- [<span data-ttu-id="637dc-130">파일 및 스트림 I/O</span><span class="sxs-lookup"><span data-stu-id="637dc-130">File and stream I/O</span></span>](index.md)
