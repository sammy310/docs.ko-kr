---
description: '자세한 정보: LINQ 및 파일 디렉터리 (Visual Basic)'
title: LINQ 및 파일 디렉터리
ms.date: 07/20/2015
ms.assetid: 159fd5c3-3926-4071-ae78-d8e423287eb7
ms.openlocfilehash: ed7f4151acde51794269e5028820397f9a3bb3f9
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/14/2021
ms.locfileid: "100426766"
---
# <a name="linq-and-file-directories-visual-basic"></a><span data-ttu-id="1db38-103">LINQ 및 파일 디렉터리(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="1db38-103">LINQ and File Directories (Visual Basic)</span></span>

<span data-ttu-id="1db38-104">많은 파일 시스템 작업은 기본적으로 쿼리이므로 LINQ 접근 방식에 적합합니다.</span><span class="sxs-lookup"><span data-stu-id="1db38-104">Many file system operations are essentially queries and are therefore well-suited to the LINQ approach.</span></span>  
  
 <span data-ttu-id="1db38-105">이 섹션에서 쿼리는 비파괴적입니다.</span><span class="sxs-lookup"><span data-stu-id="1db38-105">Note that the queries in this section are non-destructive.</span></span> <span data-ttu-id="1db38-106">쿼리는 원본 파일이나 폴더의 내용을 변경하는 데 사용되지 않으며,</span><span class="sxs-lookup"><span data-stu-id="1db38-106">They are not used to change the contents of the original files or folders.</span></span> <span data-ttu-id="1db38-107">쿼리로 인해 의도하지 않은 결과가 발생하지 않아야 한다는 규칙을 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="1db38-107">This follows the rule that queries should not cause any side-effects.</span></span> <span data-ttu-id="1db38-108">일반적으로 소스 데이터를 수정하는 모든 코드(만들기/업데이트/삭제 작업을 수행하는 쿼리 포함)는 데이터를 쿼리만하는 코드와 별도로 유지되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1db38-108">In general, any code (including queries that perform create / update / delete operators) that modifies source data should be kept separate from the code that just queries the data.</span></span>  
  
 <span data-ttu-id="1db38-109">이 단원에는 다음 항목이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1db38-109">This section contains the following topics:</span></span>  
  
 [<span data-ttu-id="1db38-110">방법: 지정 된 특성 또는 이름으로 파일 쿼리 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="1db38-110">How to: Query for Files with a Specified Attribute or Name (Visual Basic)</span></span>](how-to-query-for-files-with-a-specified-attribute-or-name.md)  
 <span data-ttu-id="1db38-111">하나 이상의 <xref:System.IO.FileInfo> 개체 속성을 검사하여 파일을 검색하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="1db38-111">Shows how to search for files by examining one or more properties of its <xref:System.IO.FileInfo> object.</span></span>  
  
 [<span data-ttu-id="1db38-112">방법: 확장명에 따라 파일 그룹화 (LINQ) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="1db38-112">How to: Group Files by Extension (LINQ) (Visual Basic)</span></span>](how-to-group-files-by-extension-linq.md)  
 <span data-ttu-id="1db38-113">파일 이름 확장명에 따라 <xref:System.IO.FileInfo> 개체의 그룹을 반환하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="1db38-113">Shows how to return groups of <xref:System.IO.FileInfo> object based on their file name extension.</span></span>  
  
 [<span data-ttu-id="1db38-114">방법: 폴더 집합의 총 바이트 수 쿼리 (LINQ) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="1db38-114">How to: Query for the Total Number of Bytes in a Set of Folders (LINQ) (Visual Basic)</span></span>](how-to-query-for-the-total-number-of-bytes-in-a-set-of-folders.md)  
 <span data-ttu-id="1db38-115">지정된 디렉터리 트리에 있는 모든 파일에서 전체 바이트 수를 반환하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="1db38-115">Shows how to return the total number of bytes in all the files in a specified directory tree.</span></span>  
  
 <span data-ttu-id="1db38-116">[방법: 두 폴더의 내용 비교 (LINQ) (Visual Basic)](how-to-compare-the-contents-of-two-folders-linq.md)</span><span class="sxs-lookup"><span data-stu-id="1db38-116">[How to: Compare the Contents of Two Folders (LINQ) (Visual Basic)](how-to-compare-the-contents-of-two-folders-linq.md)s</span></span>  
 <span data-ttu-id="1db38-117">두 개의 지정된 폴더에 있는 모든 파일뿐만 아니라 특정 폴더에만 있는 모든 파일도 반환하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="1db38-117">Shows how to return all the files that are present in two specified folders, and also all the files that are present in one folder but not the other.</span></span>  
  
 [<span data-ttu-id="1db38-118">방법: 디렉터리 트리에서 가장 큰 파일을 하나 이상 쿼리(LINQ)(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="1db38-118">How to: Query for the Largest File or Files in a Directory Tree (LINQ) (Visual Basic)</span></span>](how-to-query-for-the-largest-file-or-files-in-a-directory-tree.md)  
 <span data-ttu-id="1db38-119">디렉터리 트리에서 가장 크거나 가장 작은 파일 또는 지정한 파일 수를 반환하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="1db38-119">Shows how to return the largest or smallest file, or a specified number of files, in a directory tree.</span></span>  
  
 [<span data-ttu-id="1db38-120">방법: 디렉터리 트리에서 중복 파일 쿼리 (LINQ) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="1db38-120">How to: Query for Duplicate Files in a Directory Tree (LINQ) (Visual Basic)</span></span>](how-to-query-for-duplicate-files-in-a-directory-tree-linq.md)  
 <span data-ttu-id="1db38-121">지정된 디렉터리 트리에서 둘 이상의 위치에 나타나는 모든 파일 이름을 그룹화하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="1db38-121">Shows how to group for all file names that occur in more than one location in a specified directory tree.</span></span> <span data-ttu-id="1db38-122">또한 사용자 지정 비교자에 따라 보다 복잡한 비교를 수행하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="1db38-122">Also shows how to perform more complex comparisons based on a custom comparer.</span></span>  
  
 [<span data-ttu-id="1db38-123">폴더에 있는 파일의 내용을 쿼리 하는 방법 (LINQ) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="1db38-123">How to query the contents of files in a folder (LINQ) (Visual Basic)</span></span>](how-to-query-the-contents-of-files-in-a-folder-linq.md)  
 <span data-ttu-id="1db38-124">트리의 폴더를 반복하고, 각 파일을 열고, 파일의 내용을 쿼리하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="1db38-124">Shows how to iterate through folders in a tree, open each file, and query the file's contents.</span></span>  
  
## <a name="comments"></a><span data-ttu-id="1db38-125">주석</span><span class="sxs-lookup"><span data-stu-id="1db38-125">Comments</span></span>  

 <span data-ttu-id="1db38-126">파일 시스템의 내용을 정확하게 나타내고 예외를 정상적으로 처리하는 데이터 소스 만들기와 관련하여 몇 가지 복잡한 부분이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1db38-126">There is some complexity involved in creating a data source that accurately represents the contents of the file system and handles exceptions gracefully.</span></span> <span data-ttu-id="1db38-127">이 섹션의 예제에서는 지정된 루트 폴더와 모든 하위 폴더에 있는 모든 파일을 나타내는 <xref:System.IO.FileInfo> 개체의 스냅샷 컬렉션을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="1db38-127">The examples in this section create a snapshot collection of <xref:System.IO.FileInfo> objects that represents all the files under a specified root folder and all its subfolders.</span></span> <span data-ttu-id="1db38-128">각 <xref:System.IO.FileInfo>의 실제 상태는 쿼리 실행을 시작하고 종료하는 시간 사이에 변경될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1db38-128">The actual state of each <xref:System.IO.FileInfo> may change in the time between when you begin and end executing a query.</span></span> <span data-ttu-id="1db38-129">예를 들어 <xref:System.IO.FileInfo> 개체 목록을 만들어 데이터 소스로 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1db38-129">For example, you can create a list of <xref:System.IO.FileInfo> objects to use as a data source.</span></span> <span data-ttu-id="1db38-130">쿼리에서 `Length` 속성에 액세스하려고 하면 <xref:System.IO.FileInfo> 개체에서 파일 시스템에 액세스하여 `Length`의 값을 업데이트합니다.</span><span class="sxs-lookup"><span data-stu-id="1db38-130">If you try to access the `Length` property in a query, the <xref:System.IO.FileInfo> object will try to access the file system to update the value of `Length`.</span></span> <span data-ttu-id="1db38-131">파일이 더 이상 존재하지 않는 경우 파일 시스템을 직접 쿼리하지 않아도 쿼리에서 <xref:System.IO.FileNotFoundException>을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="1db38-131">If the file no longer exists, you will get a <xref:System.IO.FileNotFoundException> in your query, even though you are not querying the file system directly.</span></span> <span data-ttu-id="1db38-132">이 섹션의 일부 쿼리는 특정한 경우에 이러한 특정 예외를 사용하는 별도의 메서드를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="1db38-132">Some queries in this section use a separate method that consumes these particular exceptions in certain cases.</span></span> <span data-ttu-id="1db38-133">또 다른 옵션은 <xref:System.IO.FileSystemWatcher>를 사용하여 데이터 소스가 동적으로 업데이트되도록 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="1db38-133">Another option is to keep your data source updated dynamically by using the <xref:System.IO.FileSystemWatcher>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1db38-134">참조</span><span class="sxs-lookup"><span data-stu-id="1db38-134">See also</span></span>

- [<span data-ttu-id="1db38-135">LINQ to Objects(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="1db38-135">LINQ to Objects (Visual Basic)</span></span>](linq-to-objects.md)
