---
ms.openlocfilehash: 8c8e87c885c99d28aa9a7a5d5a2b48c80d40d7db
ms.sourcegitcommit: 0802ac583585110022beb6af8ea0b39188b77c43
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/25/2020
ms.locfileid: "96032162"
---
### <a name="ziparchiveentry-no-longer-handles-archives-with-inconsistent-entry-sizes"></a><span data-ttu-id="3fb11-101">ZipArchiveEntry가 더 이상 일치하지 않는 항목 크기의 아카이브를 처리하지 않음</span><span class="sxs-lookup"><span data-stu-id="3fb11-101">ZipArchiveEntry no longer handles archives with inconsistent entry sizes</span></span>

<span data-ttu-id="3fb11-102">Zip 보관 파일은 중앙 디렉터리 및 로컬 헤더에 압축 크기와 압축되지 않은 크기를 모두 나열합니다.</span><span class="sxs-lookup"><span data-stu-id="3fb11-102">Zip archives list both compressed size and uncompressed size in the central directory and local header.</span></span>  <span data-ttu-id="3fb11-103">항목 데이터 자체도 크기를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="3fb11-103">The entry data itself also indicates its size.</span></span>  <span data-ttu-id="3fb11-104">.NET Core 2.2 버전 이하에서는 이러한 값에 대해 일관성을 검사하지 않았습니다.</span><span class="sxs-lookup"><span data-stu-id="3fb11-104">In .NET Core 2.2 and earlier versions, these values were never checked for consistency.</span></span> <span data-ttu-id="3fb11-105">.NET Core 3.0부터는 검사됩니다.</span><span class="sxs-lookup"><span data-stu-id="3fb11-105">Starting with .NET Core 3.0, they now are.</span></span>

#### <a name="change-description"></a><span data-ttu-id="3fb11-106">변경 내용 설명</span><span class="sxs-lookup"><span data-stu-id="3fb11-106">Change description</span></span>

<span data-ttu-id="3fb11-107">.Net Core 2.2 버전 이하에서는 로컬 헤더가 zip 파일의 중앙 헤더와 일치하지 않는 경우에도 <xref:System.IO.Compression.ZipArchiveEntry.Open?displayProperty=nameWithType>이 성공합니다.</span><span class="sxs-lookup"><span data-stu-id="3fb11-107">In .NET Core 2.2 and earlier versions, <xref:System.IO.Compression.ZipArchiveEntry.Open?displayProperty=nameWithType> succeeds even if the local header disagrees with the central header of the zip file.</span></span> <span data-ttu-id="3fb11-108">데이터는 압축된 스트림의 끝에 도달할 때까지 압축이 풀립니다. 이는 해당 길이가 중앙 디렉터리/로컬 헤더에 나열된 압축되지 않은 파일 크기를 초과하는 경우에도 마찬가지입니다.</span><span class="sxs-lookup"><span data-stu-id="3fb11-108">Data is decompressed until the end of the compressed stream is reached, even if its length exceeds the uncompressed file size listed in the central directory/local header.</span></span>

<span data-ttu-id="3fb11-109">.Net Core 3.0부터 <xref:System.IO.Compression.ZipArchiveEntry.Open?displayProperty=nameWithType> 메서드는 로컬 헤더 및 중앙 헤더에서 항목의 압축된 크기와 압축되지 않은 크기가 일치하는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="3fb11-109">Starting with .NET Core 3.0, the <xref:System.IO.Compression.ZipArchiveEntry.Open?displayProperty=nameWithType> method checks that local header and central header agree on compressed and uncompressed sizes of an entry.</span></span>  <span data-ttu-id="3fb11-110">보관 파일의 로컬 헤더 및/또는 데이터 설명자가 zip 파일의 중앙 디렉터리와 일치하지 않는 크기를 나열하는 경우 메서드가 <xref:System.IO.InvalidDataException>을 throw합니다.</span><span class="sxs-lookup"><span data-stu-id="3fb11-110">If they do not, the method throws an <xref:System.IO.InvalidDataException> if the archive's local header and/or data descriptor list sizes that disagree with the central directory of the zip file.</span></span> <span data-ttu-id="3fb11-111">항목을 읽을 때 압축 해제된 데이터가 헤더에 나열된 압축되지 않은 파일 크기로 잘립니다.</span><span class="sxs-lookup"><span data-stu-id="3fb11-111">When reading an entry, decompressed data is truncated to the uncompressed file size listed in the header.</span></span>

<span data-ttu-id="3fb11-112">이러한 변경은 <xref:System.IO.Compression.ZipArchiveEntry>가 해당 데이터의 크기를 정확하게 표시하고 해당 양의 데이터만 읽도록 하기 위함입니다.</span><span class="sxs-lookup"><span data-stu-id="3fb11-112">This change was made to ensure that a <xref:System.IO.Compression.ZipArchiveEntry> correctly represents the size of its data and that only that amount of data is read.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="3fb11-113">도입된 버전</span><span class="sxs-lookup"><span data-stu-id="3fb11-113">Version introduced</span></span>

<span data-ttu-id="3fb11-114">3.0</span><span class="sxs-lookup"><span data-stu-id="3fb11-114">3.0</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="3fb11-115">권장 조치</span><span class="sxs-lookup"><span data-stu-id="3fb11-115">Recommended action</span></span>

<span data-ttu-id="3fb11-116">이러한 문제가 발생하는 zip 보관 파일을 다시 패키지합니다.</span><span class="sxs-lookup"><span data-stu-id="3fb11-116">Repackage any zip archive that exhibits these problems.</span></span>

#### <a name="category"></a><span data-ttu-id="3fb11-117">범주</span><span class="sxs-lookup"><span data-stu-id="3fb11-117">Category</span></span>

<span data-ttu-id="3fb11-118">CoreFx</span><span class="sxs-lookup"><span data-stu-id="3fb11-118">CoreFx</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="3fb11-119">영향을 받는 API</span><span class="sxs-lookup"><span data-stu-id="3fb11-119">Affected APIs</span></span>

- <xref:System.IO.Compression.ZipArchiveEntry.Open?displayProperty=nameWithType>
- <xref:System.IO.Compression.ZipFileExtensions.ExtractToDirectory%2A?displayProperty=nameWithType>
- <xref:System.IO.Compression.ZipFileExtensions.ExtractToFile%2A?displayProperty=nameWithType>
- <xref:System.IO.Compression.ZipFile.ExtractToDirectory%2A?displayProperty=nameWithType>

<!--

#### Affected APIs

`M:System.IO.Compression.ZipArchiveEntry.Open`
`Overload:System.IO.Compression.ZipFileExtensions.ExtractToDirectory%2A`
`Overload:System.IO.Compression.ZipFileExtensions.ExtractToFile%2A`
`Overload:System.IO.Compression.ZipFile.ExtractToDirectory%2A`

-->
