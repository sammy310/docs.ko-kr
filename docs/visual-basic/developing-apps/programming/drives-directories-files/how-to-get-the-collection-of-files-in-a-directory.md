---
description: '자세한 정보: 방법: Visual Basic에서 디렉터리의 파일 컬렉션 가져오기'
title: '방법: 디렉터리의 파일 컬렉션 가져오기'
ms.date: 07/20/2015
helpviewer_keywords:
- folders, working with
- files [Visual Basic], accessing
ms.assetid: 6c8ba7e8-dd37-4853-92bf-762b67c98160
ms.openlocfilehash: bd799390c0ad0868f51387ba12e8612fe8948297
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99797538"
---
# <a name="how-to-get-the-collection-of-files-in-a-directory-in-visual-basic"></a><span data-ttu-id="ea0cf-103">방법: Visual Basic에서 디렉터리의 파일 컬렉션 가져오기</span><span class="sxs-lookup"><span data-stu-id="ea0cf-103">How to: Get the Collection of Files in a Directory in Visual Basic</span></span>

<span data-ttu-id="ea0cf-104"><xref:Microsoft.VisualBasic.FileIO.FileSystem.GetFiles%2A?displayProperty=nameWithType> 메서드의 오버로드는 디렉터리 내의 파일 이름을 나타내는 문자열의 읽기 전용 컬렉션을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="ea0cf-104">The overloads of the <xref:Microsoft.VisualBasic.FileIO.FileSystem.GetFiles%2A?displayProperty=nameWithType> method return a read-only collection of strings representing the names of the files within a directory:</span></span>  
  
- <span data-ttu-id="ea0cf-105">하위 디렉터리를 검색하지 않고 지정된 디렉터리에서 단순 파일 검색을 수행하려면 <xref:Microsoft.VisualBasic.FileIO.FileSystem.GetFiles%28System.String%29> 오버로드를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="ea0cf-105">Use the <xref:Microsoft.VisualBasic.FileIO.FileSystem.GetFiles%28System.String%29> overload for a simple file search in a specified directory, without searching subdirectories.</span></span>  
  
- <span data-ttu-id="ea0cf-106">검색을 위한 추가 옵션을 지정하려면 <xref:Microsoft.VisualBasic.FileIO.FileSystem.GetFiles(System.String,Microsoft.VisualBasic.FileIO.SearchOption,System.String[])> 오버로드를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="ea0cf-106">Use the <xref:Microsoft.VisualBasic.FileIO.FileSystem.GetFiles(System.String,Microsoft.VisualBasic.FileIO.SearchOption,System.String[])> overload to specify additional options for your search.</span></span> <span data-ttu-id="ea0cf-107">`wildCards` 매개 변수를 사용하면 검색 패턴을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ea0cf-107">You can use the `wildCards` parameter to specify a search pattern.</span></span> <span data-ttu-id="ea0cf-108">검색에 하위 디렉터리를 포함하려면 `searchType` 매개 변수를 <xref:Microsoft.VisualBasic.FileIO.SearchOption.SearchAllSubDirectories?displayProperty=nameWithType>로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="ea0cf-108">To include subdirectories in the search, set the `searchType` parameter to <xref:Microsoft.VisualBasic.FileIO.SearchOption.SearchAllSubDirectories?displayProperty=nameWithType>.</span></span>  
  
 <span data-ttu-id="ea0cf-109">지정한 패턴과 일치하는 파일이 없으면 빈 컬렉션이 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="ea0cf-109">An empty collection is returned if no files matching the specified pattern are found.</span></span>  
  
### <a name="to-list-files-in-a-directory"></a><span data-ttu-id="ea0cf-110">디렉터리의 파일을 나열하려면</span><span class="sxs-lookup"><span data-stu-id="ea0cf-110">To list files in a directory</span></span>  
  
- <span data-ttu-id="ea0cf-111"><xref:Microsoft.VisualBasic.FileIO.FileSystem.GetFiles%2A?displayProperty=nameWithType> 메서드 오버로드 중 하나를 사용하고 `directory` 매개 변수에서 검색할 디렉터리의 이름과 경로를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="ea0cf-111">Use one of the <xref:Microsoft.VisualBasic.FileIO.FileSystem.GetFiles%2A?displayProperty=nameWithType> method overloads, supplying the name and path of the directory to search in the `directory` parameter.</span></span> <span data-ttu-id="ea0cf-112">다음 예제에서는 디렉터리의 모든 파일을 반환하여 `ListBox1`에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="ea0cf-112">The following example returns all files in the directory and adds them to `ListBox1`.</span></span>  
  
     [!code-vb[VbVbcnMyFileSystem#32](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnMyFileSystem/VB/Class1.vb#32)]  
  
## <a name="robust-programming"></a><span data-ttu-id="ea0cf-113">강력한 프로그래밍</span><span class="sxs-lookup"><span data-stu-id="ea0cf-113">Robust Programming</span></span>  

 <span data-ttu-id="ea0cf-114">다음 조건에서 예외가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="ea0cf-114">The following conditions may cause an exception:</span></span>  
  
- <span data-ttu-id="ea0cf-115">길이가 0인 문자열이거나, 공백만 포함하거나, 잘못된 문자를 포함하거나, 경로가 디바이스 경로인 경우(\\\\.\\로 시작됨)와 같은 여러 가지 이유 중 하나로 경로가 올바르지 않은 경우(<xref:System.ArgumentException>)</span><span class="sxs-lookup"><span data-stu-id="ea0cf-115">The path is not valid for one of the following reasons: it is a zero-length string, it contains only white space, it contains invalid characters, or it is a device path (starts with \\\\.\\) (<xref:System.ArgumentException>).</span></span>  
  
- <span data-ttu-id="ea0cf-116">경로가 `Nothing` 이기 때문에 올바르지 않은 경우(<xref:System.ArgumentNullException>)</span><span class="sxs-lookup"><span data-stu-id="ea0cf-116">The path is not valid because it is `Nothing` (<xref:System.ArgumentNullException>).</span></span>  
  
- <span data-ttu-id="ea0cf-117">`directory`가 없는 경우(<xref:System.IO.DirectoryNotFoundException>)</span><span class="sxs-lookup"><span data-stu-id="ea0cf-117">`directory` does not exist (<xref:System.IO.DirectoryNotFoundException>).</span></span>  
  
- <span data-ttu-id="ea0cf-118">`directory`가 기존 파일을 가리키는 경우(<xref:System.IO.IOException>)</span><span class="sxs-lookup"><span data-stu-id="ea0cf-118">`directory` points to an existing file (<xref:System.IO.IOException>).</span></span>  
  
- <span data-ttu-id="ea0cf-119">경로가 시스템 정의 최대 길이를 초과하는 경우(<xref:System.IO.PathTooLongException>)</span><span class="sxs-lookup"><span data-stu-id="ea0cf-119">The path exceeds the system-defined maximum length (<xref:System.IO.PathTooLongException>).</span></span>  
  
- <span data-ttu-id="ea0cf-120">경로의 파일 이름이나 디렉터리 이름에 콜론(:)이 있거나 이름의 형식이 잘못된 경우(<xref:System.NotSupportedException>)</span><span class="sxs-lookup"><span data-stu-id="ea0cf-120">A file or directory name in the path contains a colon (:) or is in an invalid format (<xref:System.NotSupportedException>).</span></span>  
  
- <span data-ttu-id="ea0cf-121">경로를 보는 데 필요한 권한이 사용자에게 없는 경우(<xref:System.Security.SecurityException>)</span><span class="sxs-lookup"><span data-stu-id="ea0cf-121">The user lacks necessary permissions to view the path (<xref:System.Security.SecurityException>).</span></span>  
  
- <span data-ttu-id="ea0cf-122">사용자에게 필요한 권한이 없는 경우(<xref:System.UnauthorizedAccessException>)</span><span class="sxs-lookup"><span data-stu-id="ea0cf-122">The user lacks necessary permissions (<xref:System.UnauthorizedAccessException>).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ea0cf-123">참고 항목</span><span class="sxs-lookup"><span data-stu-id="ea0cf-123">See also</span></span>

- <xref:Microsoft.VisualBasic.FileIO.FileSystem.GetFiles%2A>
- [<span data-ttu-id="ea0cf-124">방법: 특정 패턴의 파일 찾기</span><span class="sxs-lookup"><span data-stu-id="ea0cf-124">How to: Find Files with a Specific Pattern</span></span>](how-to-find-files-with-a-specific-pattern.md)
- [<span data-ttu-id="ea0cf-125">방법: 특정 패턴의 하위 디렉터리 찾기</span><span class="sxs-lookup"><span data-stu-id="ea0cf-125">How to: Find Subdirectories with a Specific Pattern</span></span>](how-to-find-subdirectories-with-a-specific-pattern.md)
