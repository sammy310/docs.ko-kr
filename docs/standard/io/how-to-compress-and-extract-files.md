---
title: '방법: 파일 압축 및 추출'
ms.date: 01/14/2019
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- I/O [.NET Framework], compression
- compression
- compress files
ms.assetid: e9876165-3c60-4c84-a272-513e47acf579
ms.openlocfilehash: 6345b467e9ade085a38de6dc9758b1bd99d1ae62
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/07/2020
ms.locfileid: "75708104"
---
# <a name="how-to-compress-and-extract-files"></a><span data-ttu-id="292a0-102">방법: 파일 압축 및 추출</span><span class="sxs-lookup"><span data-stu-id="292a0-102">How to: Compress and extract files</span></span>

<span data-ttu-id="292a0-103"><xref:System.IO.Compression> 네임스페이스는 파일 및 스트림을 압축하고 압축을 푸는 다음 형식을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="292a0-103">The <xref:System.IO.Compression> namespace contains the following types for compressing and decompressing files and streams.</span></span> <span data-ttu-id="292a0-104">또한 이러한 형식을 사용하여 압축된 파일의 내용을 읽고 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="292a0-104">You can also use these types to read and modify the contents of a compressed file.</span></span>

- <xref:System.IO.Compression.ZipFile>
- <xref:System.IO.Compression.ZipArchive>
- <xref:System.IO.Compression.ZipArchiveEntry>
- <xref:System.IO.Compression.DeflateStream>
- <xref:System.IO.Compression.GZipStream>

<span data-ttu-id="292a0-105">다음 예제에서는 압축된 파일로 수행할 수 있는 일부 작업을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="292a0-105">The following examples show some of the operations you can perform with compressed files.</span></span>

## <a name="example-1-create-and-extract-a-zip-file"></a><span data-ttu-id="292a0-106">예제 1: .zip 파일 만들기 및 추출</span><span class="sxs-lookup"><span data-stu-id="292a0-106">Example 1: Create and extract a .zip file</span></span>

<span data-ttu-id="292a0-107">다음 예제에서는 <xref:System.IO.Compression.ZipFile> 클래스를 사용하여 압축된 *.zip* 파일을 만들고 추출하는 방법을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="292a0-107">The following example shows how to create and extract a compressed *.zip* file by using the <xref:System.IO.Compression.ZipFile> class.</span></span> <span data-ttu-id="292a0-108">이 예제는 폴더의 콘텐츠를 새로운 *.zip* 파일로 압축한 다음, zip을 새 폴더에 추출합니다.</span><span class="sxs-lookup"><span data-stu-id="292a0-108">The example compresses the contents of a folder into a new *.zip* file, and then extracts the zip to a new folder.</span></span> 

<span data-ttu-id="292a0-109">샘플을 실행하려면 프로그램 폴더에 *start* 폴더를 만들어서 zip 파일로 채웁니다.</span><span class="sxs-lookup"><span data-stu-id="292a0-109">To run the sample, create a *start* folder in your program folder and populate it with files to zip.</span></span> 

<span data-ttu-id="292a0-110">"'ZipFile' 이름이 현재 컨텍스트에 없습니다."라는 빌드 오류가 발생하면 `System.IO.Compression.FileSystem` 어셈블리에 대한 참조를 프로젝트에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="292a0-110">If you get the build error "The name 'ZipFile' does not exist in the current context," add a reference to the `System.IO.Compression.FileSystem` assembly to your project.</span></span>

[!code-csharp[System.IO.Compression.ZipFile#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.io.compression.zipfile/cs/program1.cs#1)]
[!code-vb[System.IO.Compression.ZipFile#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.io.compression.zipfile/vb/program1.vb#1)]

## <a name="example-2-extract-specific-file-extensions"></a><span data-ttu-id="292a0-111">예제 2: 특정 파일 확장명 추출</span><span class="sxs-lookup"><span data-stu-id="292a0-111">Example 2: Extract specific file extensions</span></span>

<span data-ttu-id="292a0-112">다음 예제는 기존 *.zip* 파일의 콘텐츠를 반복하고 확장명이 *.txt*인 파일을 추출합니다.</span><span class="sxs-lookup"><span data-stu-id="292a0-112">The next example iterates through the contents of an existing *.zip* file and extracts files that have a *.txt* extension.</span></span> <span data-ttu-id="292a0-113"><xref:System.IO.Compression.ZipArchive> 클래스를 사용하여 zip에 액세스하고 <xref:System.IO.Compression.ZipArchiveEntry> 클래스를 사용하여 개별 항목을 검사합니다.</span><span class="sxs-lookup"><span data-stu-id="292a0-113">It uses the <xref:System.IO.Compression.ZipArchive> class to access the zip, and the <xref:System.IO.Compression.ZipArchiveEntry> class to inspect the individual entries.</span></span> <span data-ttu-id="292a0-114"><xref:System.IO.Compression.ZipArchiveEntry> 개체의 <xref:System.IO.Compression.ZipFileExtensions.ExtractToFile%2A> 확장 메서드는 <xref:System.IO.Compression.ZipFileExtensions?displayProperty=nameWithType> 클래스에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="292a0-114">The extension method <xref:System.IO.Compression.ZipFileExtensions.ExtractToFile%2A> for the <xref:System.IO.Compression.ZipArchiveEntry> object is available in the <xref:System.IO.Compression.ZipFileExtensions?displayProperty=nameWithType> class.</span></span> 

<span data-ttu-id="292a0-115">샘플을 실행하려면 *result.zip*이라는 *.zip* 파일을 프로그램 폴더에 둡니다.</span><span class="sxs-lookup"><span data-stu-id="292a0-115">To run the sample, place a *.zip* file called *result.zip* in your program folder.</span></span> <span data-ttu-id="292a0-116">메시지가 표시되면 추출할 폴더 이름을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="292a0-116">When prompted, provide a folder name to extract to.</span></span> 

<span data-ttu-id="292a0-117">"'ZipFile' 이름이 현재 컨텍스트에 없습니다."라는 빌드 오류가 발생하면 `System.IO.Compression.FileSystem` 어셈블리에 대한 참조를 프로젝트에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="292a0-117">If you get the build error "The name 'ZipFile' does not exist in the current context," add a reference to the `System.IO.Compression.FileSystem` assembly to your project.</span></span>

<span data-ttu-id="292a0-118">"'ZipArchive' 형식이 참조되지 않은 어셈블리에 정의되었습니다."라는 오류가 발생하면 `System.IO.Compression` 어셈블리에 대한 참조를 프로젝트에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="292a0-118">If you get the error "The type 'ZipArchive' is defined in an assembly that is not referenced," add a reference to the `System.IO.Compression` assembly to your project.</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="292a0-119">파일 압축을 풀 때는 압축을 풀 디렉터리에서 이스케이프할 수 있는 악성 파일 경로를 찾아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="292a0-119">When unzipping files, you must look for malicious file paths, which can escape out of the directory you unzip into.</span></span> <span data-ttu-id="292a0-120">이를 경로 통과 공격이라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="292a0-120">This is known as a path traversal attack.</span></span> <span data-ttu-id="292a0-121">다음 예제는 악성 파일 경로를 확인하는 방법과 안전하게 압축을 푸는 방법을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="292a0-121">The following example demonstrates how to check for malicious file paths and provides a safe way to unzip.</span></span>

[!code-csharp[System.IO.Compression.ZipArchive#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.io.compression.ziparchive/cs/program1.cs#1)]
[!code-vb[System.IO.Compression.ZipArchive#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.io.compression.ziparchive/vb/program1.vb#1)]

## <a name="example-3-add-a-file-to-an-existing-zip"></a><span data-ttu-id="292a0-122">예제 3: 기존 zip에 파일 추가</span><span class="sxs-lookup"><span data-stu-id="292a0-122">Example 3: Add a file to an existing zip</span></span>

<span data-ttu-id="292a0-123">다음 예제는 <xref:System.IO.Compression.ZipArchive> 클래스를 사용하여 기존 *.zip* 파일에 액세스하고 파일을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="292a0-123">The following example uses the <xref:System.IO.Compression.ZipArchive> class to access an existing *.zip* file, and adds a file to it.</span></span> <span data-ttu-id="292a0-124">새 파일은 기존 .zip 파일에 추가할 때 압축됩니다.</span><span class="sxs-lookup"><span data-stu-id="292a0-124">The new file gets compressed when you add it to the existing zip.</span></span>

[!code-csharp[System.IO.Compression.ZipArchiveMode#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.io.compression.ziparchivemode/cs/program1.cs#1)]
[!code-vb[System.IO.Compression.ZipArchiveMode#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.io.compression.ziparchivemode/vb/program1.vb#1)]

## <a name="example-4-compress-and-decompress-gz-files"></a><span data-ttu-id="292a0-125">예제 4: .gz 파일 압축 및 압축 풀기</span><span class="sxs-lookup"><span data-stu-id="292a0-125">Example 4: Compress and decompress .gz files</span></span>

<span data-ttu-id="292a0-126"><xref:System.IO.Compression.GZipStream> 및 <xref:System.IO.Compression.DeflateStream> 클래스를 사용하여 데이터를 압축하거나 압축을 풀 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="292a0-126">You can also use the <xref:System.IO.Compression.GZipStream> and <xref:System.IO.Compression.DeflateStream> classes to compress and decompress data.</span></span> <span data-ttu-id="292a0-127">동일한 압축 알고리즘을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="292a0-127">They use the same compression algorithm.</span></span> <span data-ttu-id="292a0-128">*.gz* 파일에 기록된 <xref:System.IO.Compression.GZipStream> 개체의 압축은 많은 일반적인 도구를 사용하여 풀 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="292a0-128">You can decompress <xref:System.IO.Compression.GZipStream> objects that are written to a *.gz* file by using many common tools.</span></span> <span data-ttu-id="292a0-129">다음 예제에서는 <xref:System.IO.Compression.GZipStream> 클래스를 사용하여 파일의 디렉터리를 압축하고 압축을 푸는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="292a0-129">The following example shows how to compress and decompress a directory of files by using the <xref:System.IO.Compression.GZipStream> class:</span></span>

[!code-csharp[IO.Compression.GZip1#1](../../../samples/snippets/csharp/VS_Snippets_CLR/IO.Compression.GZip1/CS/gziptest.cs#1)]
[!code-vb[IO.Compression.GZip1#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/IO.Compression.GZip1/VB/gziptest.vb#1)]

## <a name="see-also"></a><span data-ttu-id="292a0-130">참조</span><span class="sxs-lookup"><span data-stu-id="292a0-130">See also</span></span>

- <xref:System.IO.Compression.ZipArchive>  
- <xref:System.IO.Compression.ZipFile>  
- <xref:System.IO.Compression.ZipArchiveEntry>  
- <xref:System.IO.Compression.DeflateStream>  
- <xref:System.IO.Compression.GZipStream>  
- [<span data-ttu-id="292a0-131">파일 및 스트림 I/O</span><span class="sxs-lookup"><span data-stu-id="292a0-131">File and stream I/O</span></span>](../../../docs/standard/io/index.md)
