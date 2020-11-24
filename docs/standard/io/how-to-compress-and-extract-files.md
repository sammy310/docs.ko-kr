---
title: '방법: 파일 압축 및 추출'
description: System.IO.Compression을 사용하여 파일을 압축하고 추출합니다. ZipFile, ZipArchive, ZipArchiveEntry, DeflateStream 및 GZipStream을 사용하는 예제를 참조하세요.
ms.date: 01/14/2019
dev_langs:
- csharp
- vb
helpviewer_keywords:
- I/O [.NET], compression
- compression
- compress files
ms.assetid: e9876165-3c60-4c84-a272-513e47acf579
ms.openlocfilehash: a1077c7277e0aa54e3c8883cfc27d93926485b8e
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/18/2020
ms.locfileid: "94830859"
---
# <a name="how-to-compress-and-extract-files"></a><span data-ttu-id="8acbd-104">방법: 파일 압축 및 추출</span><span class="sxs-lookup"><span data-stu-id="8acbd-104">How to: Compress and extract files</span></span>

<span data-ttu-id="8acbd-105"><xref:System.IO.Compression> 네임스페이스는 파일 및 스트림을 압축하고 압축을 푸는 다음 형식을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="8acbd-105">The <xref:System.IO.Compression> namespace contains the following types for compressing and decompressing files and streams.</span></span> <span data-ttu-id="8acbd-106">또한 이러한 형식을 사용하여 압축된 파일의 내용을 읽고 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8acbd-106">You can also use these types to read and modify the contents of a compressed file.</span></span>

- <xref:System.IO.Compression.ZipFile>
- <xref:System.IO.Compression.ZipArchive>
- <xref:System.IO.Compression.ZipArchiveEntry>
- <xref:System.IO.Compression.DeflateStream>
- <xref:System.IO.Compression.GZipStream>

<span data-ttu-id="8acbd-107">다음 예제에서는 압축된 파일로 수행할 수 있는 일부 작업을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="8acbd-107">The following examples show some of the operations you can perform with compressed files.</span></span> <span data-ttu-id="8acbd-108">이러한 예제를 수행하려면 다음 NuGet 패키지를 프로젝트에 추가해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8acbd-108">These examples require the following NuGet packages to be added to your project:</span></span>

- [<span data-ttu-id="8acbd-109">System.IO.Compression</span><span class="sxs-lookup"><span data-stu-id="8acbd-109">System.IO.Compression</span></span>](https://www.nuget.org/packages/System.IO.Compression)
- [<span data-ttu-id="8acbd-110">System.IO.Compression.ZipFile</span><span class="sxs-lookup"><span data-stu-id="8acbd-110">System.IO.Compression.ZipFile</span></span>](https://www.nuget.org/packages/System.IO.Compression.ZipFile)

<span data-ttu-id="8acbd-111">.NET Framework를 사용하는 경우 다음 두 라이브러리에 대한 참조를 프로젝트에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="8acbd-111">If you're using .NET Framework, add references to these two libraries to your project:</span></span>

- `System.IO.Compression`
- `System.IO.Compression.FileSystem`

## <a name="example-1-create-and-extract-a-zip-file"></a><span data-ttu-id="8acbd-112">예제 1: .zip 파일 만들기 및 추출</span><span class="sxs-lookup"><span data-stu-id="8acbd-112">Example 1: Create and extract a .zip file</span></span>

<span data-ttu-id="8acbd-113">다음 예제에서는 <xref:System.IO.Compression.ZipFile> 클래스를 사용하여 압축된 *.zip* 파일을 만들고 추출하는 방법을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="8acbd-113">The following example shows how to create and extract a compressed *.zip* file by using the <xref:System.IO.Compression.ZipFile> class.</span></span> <span data-ttu-id="8acbd-114">이 예제는 폴더의 콘텐츠를 새로운 *.zip* 파일로 압축한 다음, zip을 새 폴더에 추출합니다.</span><span class="sxs-lookup"><span data-stu-id="8acbd-114">The example compresses the contents of a folder into a new *.zip* file, and then extracts the zip to a new folder.</span></span>

<span data-ttu-id="8acbd-115">샘플을 실행하려면 프로그램 폴더에 *start* 폴더를 만들어서 zip 파일로 채웁니다.</span><span class="sxs-lookup"><span data-stu-id="8acbd-115">To run the sample, create a *start* folder in your program folder and populate it with files to zip.</span></span>

[!code-csharp[System.IO.Compression.ZipFile#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.io.compression.zipfile/cs/program1.cs#1)]
[!code-vb[System.IO.Compression.ZipFile#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.io.compression.zipfile/vb/program1.vb#1)]

## <a name="example-2-extract-specific-file-extensions"></a><span data-ttu-id="8acbd-116">예제 2: 특정 파일 확장명 추출</span><span class="sxs-lookup"><span data-stu-id="8acbd-116">Example 2: Extract specific file extensions</span></span>

<span data-ttu-id="8acbd-117">다음 예제는 기존 *.zip* 파일의 콘텐츠를 반복하고 확장명이 *.txt* 인 파일을 추출합니다.</span><span class="sxs-lookup"><span data-stu-id="8acbd-117">The next example iterates through the contents of an existing *.zip* file and extracts files that have a *.txt* extension.</span></span> <span data-ttu-id="8acbd-118"><xref:System.IO.Compression.ZipArchive> 클래스를 사용하여 zip에 액세스하고 <xref:System.IO.Compression.ZipArchiveEntry> 클래스를 사용하여 개별 항목을 검사합니다.</span><span class="sxs-lookup"><span data-stu-id="8acbd-118">It uses the <xref:System.IO.Compression.ZipArchive> class to access the zip, and the <xref:System.IO.Compression.ZipArchiveEntry> class to inspect the individual entries.</span></span> <span data-ttu-id="8acbd-119"><xref:System.IO.Compression.ZipArchiveEntry> 개체의 <xref:System.IO.Compression.ZipFileExtensions.ExtractToFile%2A> 확장 메서드는 <xref:System.IO.Compression.ZipFileExtensions?displayProperty=nameWithType> 클래스에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8acbd-119">The extension method <xref:System.IO.Compression.ZipFileExtensions.ExtractToFile%2A> for the <xref:System.IO.Compression.ZipArchiveEntry> object is available in the <xref:System.IO.Compression.ZipFileExtensions?displayProperty=nameWithType> class.</span></span>

<span data-ttu-id="8acbd-120">샘플을 실행하려면 *result.zip* 이라는 *.zip* 파일을 프로그램 폴더에 둡니다.</span><span class="sxs-lookup"><span data-stu-id="8acbd-120">To run the sample, place a *.zip* file called *result.zip* in your program folder.</span></span> <span data-ttu-id="8acbd-121">메시지가 표시되면 추출할 폴더 이름을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="8acbd-121">When prompted, provide a folder name to extract to.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="8acbd-122">파일 압축을 풀 때는 압축을 풀 디렉터리에서 이스케이프할 수 있는 악성 파일 경로를 찾아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8acbd-122">When unzipping files, you must look for malicious file paths, which can escape out of the directory you unzip into.</span></span> <span data-ttu-id="8acbd-123">이를 경로 통과 공격이라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="8acbd-123">This is known as a path traversal attack.</span></span> <span data-ttu-id="8acbd-124">다음 예제는 악성 파일 경로를 확인하는 방법과 안전하게 압축을 푸는 방법을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="8acbd-124">The following example demonstrates how to check for malicious file paths and provides a safe way to unzip.</span></span>

[!code-csharp[System.IO.Compression.ZipArchive#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.io.compression.ziparchive/cs/program1.cs#1)]
[!code-vb[System.IO.Compression.ZipArchive#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.io.compression.ziparchive/vb/program1.vb#1)]

## <a name="example-3-add-a-file-to-an-existing-zip"></a><span data-ttu-id="8acbd-125">예제 3: 기존 zip에 파일 추가</span><span class="sxs-lookup"><span data-stu-id="8acbd-125">Example 3: Add a file to an existing zip</span></span>

<span data-ttu-id="8acbd-126">다음 예제는 <xref:System.IO.Compression.ZipArchive> 클래스를 사용하여 기존 *.zip* 파일에 액세스하고 파일을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="8acbd-126">The following example uses the <xref:System.IO.Compression.ZipArchive> class to access an existing *.zip* file, and adds a file to it.</span></span> <span data-ttu-id="8acbd-127">새 파일은 기존 .zip 파일에 추가할 때 압축됩니다.</span><span class="sxs-lookup"><span data-stu-id="8acbd-127">The new file gets compressed when you add it to the existing zip.</span></span>

[!code-csharp[System.IO.Compression.ZipArchiveMode#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.io.compression.ziparchivemode/cs/program1.cs#1)]
[!code-vb[System.IO.Compression.ZipArchiveMode#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.io.compression.ziparchivemode/vb/program1.vb#1)]

## <a name="example-4-compress-and-decompress-gz-files"></a><span data-ttu-id="8acbd-128">예제 4: .gz 파일 압축 및 압축 풀기</span><span class="sxs-lookup"><span data-stu-id="8acbd-128">Example 4: Compress and decompress .gz files</span></span>

<span data-ttu-id="8acbd-129"><xref:System.IO.Compression.GZipStream> 및 <xref:System.IO.Compression.DeflateStream> 클래스를 사용하여 데이터를 압축하거나 압축을 풀 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8acbd-129">You can also use the <xref:System.IO.Compression.GZipStream> and <xref:System.IO.Compression.DeflateStream> classes to compress and decompress data.</span></span> <span data-ttu-id="8acbd-130">동일한 압축 알고리즘을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="8acbd-130">They use the same compression algorithm.</span></span> <span data-ttu-id="8acbd-131">*.gz* 파일에 기록된 <xref:System.IO.Compression.GZipStream> 개체의 압축은 많은 일반적인 도구를 사용하여 풀 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8acbd-131">You can decompress <xref:System.IO.Compression.GZipStream> objects that are written to a *.gz* file by using many common tools.</span></span> <span data-ttu-id="8acbd-132">다음 예제에서는 <xref:System.IO.Compression.GZipStream> 클래스를 사용하여 파일의 디렉터리를 압축하고 압축을 푸는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="8acbd-132">The following example shows how to compress and decompress a directory of files by using the <xref:System.IO.Compression.GZipStream> class:</span></span>

[!code-csharp[IO.Compression.GZip1#1](../../../samples/snippets/csharp/VS_Snippets_CLR/IO.Compression.GZip1/CS/gziptest.cs#1)]
[!code-vb[IO.Compression.GZip1#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/IO.Compression.GZip1/VB/gziptest.vb#1)]

## <a name="see-also"></a><span data-ttu-id="8acbd-133">참조</span><span class="sxs-lookup"><span data-stu-id="8acbd-133">See also</span></span>

- <xref:System.IO.Compression.ZipArchive>  
- <xref:System.IO.Compression.ZipFile>  
- <xref:System.IO.Compression.ZipArchiveEntry>  
- <xref:System.IO.Compression.DeflateStream>  
- <xref:System.IO.Compression.GZipStream>  
- [<span data-ttu-id="8acbd-134">파일 및 스트림 I/O</span><span class="sxs-lookup"><span data-stu-id="8acbd-134">File and stream I/O</span></span>](index.md)
