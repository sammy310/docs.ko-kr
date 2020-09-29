---
title: 텍스트 파일에서 읽는 방법 - C# 프로그래밍 가이드
description: 파일 클래스에서 정적 메서드를 사용하여 텍스트 파일을 읽는 방법을 알아봅니다. 코드 예제를 살펴보고 사용 가능한 추가 리소스를 확인합니다.
ms.date: 07/20/2015
f1_keywords:
- StreamReader.ReadToEnd
helpviewer_keywords:
- text files, writing to
- reading text files
- reading data, text files
- text files, reading
ms.assetid: 92246c5b-e819-4eea-9370-1a9460e12de3
ms.openlocfilehash: 64ac99ec0a72ba7df120f6732edccf160a351738
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/24/2020
ms.locfileid: "91201839"
---
# <a name="how-to-read-from-a-text-file-c-programming-guide"></a><span data-ttu-id="41c9f-104">텍스트 파일에서 읽는 방법(C# 프로그래밍 가이드)</span><span class="sxs-lookup"><span data-stu-id="41c9f-104">How to read from a text file (C# Programming Guide)</span></span>

<span data-ttu-id="41c9f-105">이 예제에서는 <xref:System.IO.File?displayProperty=nameWithType> 클래스의 정적 메서드 <xref:System.IO.File.ReadAllText%2A> 및 <xref:System.IO.File.ReadAllLines%2A>를 사용하여 텍스트 파일의 내용을 읽습니다.</span><span class="sxs-lookup"><span data-stu-id="41c9f-105">This example reads the contents of a text file by using the static methods <xref:System.IO.File.ReadAllText%2A> and <xref:System.IO.File.ReadAllLines%2A> from the <xref:System.IO.File?displayProperty=nameWithType> class.</span></span>  
  
<span data-ttu-id="41c9f-106"><xref:System.IO.StreamReader>를 사용하는 예제는 [텍스트 파일을 한 번에 한 줄씩 읽는 방법](./how-to-read-a-text-file-one-line-at-a-time.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="41c9f-106">For an example that uses <xref:System.IO.StreamReader>, see [How to read a text file one line at a time](./how-to-read-a-text-file-one-line-at-a-time.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="41c9f-107">이 예제에 사용되는 파일은 [텍스트 파일에 쓰는 방법](./how-to-write-to-a-text-file.md) 항목에서 생성되었습니다.</span><span class="sxs-lookup"><span data-stu-id="41c9f-107">The files that are used in this example are created in the topic [How to write to a text file](./how-to-write-to-a-text-file.md).</span></span>
  
## <a name="example"></a><span data-ttu-id="41c9f-108">예제</span><span class="sxs-lookup"><span data-stu-id="41c9f-108">Example</span></span>  

 [!code-csharp[csFilesandFolders#4](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csFilesAndFolders/CS/FileIteration.cs#4)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="41c9f-109">코드 컴파일</span><span class="sxs-lookup"><span data-stu-id="41c9f-109">Compiling the Code</span></span>  

 <span data-ttu-id="41c9f-110">코드를 복사하고 C# 콘솔 애플리케이션에 붙여넣습니다.</span><span class="sxs-lookup"><span data-stu-id="41c9f-110">Copy the code and paste it into a C# console application.</span></span>  
  
<span data-ttu-id="41c9f-111">[텍스트 파일에 쓰는 방법](./how-to-write-to-a-text-file.md)의 텍스트 파일을 사용하지 않는 경우 `ReadAllText` 및 `ReadAllLines`에 대한 인수를 사용자 컴퓨터의 적절한 경로 및 파일 이름으로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="41c9f-111">If you are not using the text files from [How to write to a text file](./how-to-write-to-a-text-file.md), replace the argument to `ReadAllText` and `ReadAllLines` with the appropriate path and file name on your computer.</span></span>
  
## <a name="robust-programming"></a><span data-ttu-id="41c9f-112">강력한 프로그래밍</span><span class="sxs-lookup"><span data-stu-id="41c9f-112">Robust Programming</span></span>  

 <span data-ttu-id="41c9f-113">다음 조건에서 예외가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="41c9f-113">The following conditions may cause an exception:</span></span>  
  
- <span data-ttu-id="41c9f-114">파일이 없거나 지정된 위치에 없는 경우.</span><span class="sxs-lookup"><span data-stu-id="41c9f-114">The file doesn't exist or doesn't exist at the specified location.</span></span> <span data-ttu-id="41c9f-115">경로와 파일 이름의 철자를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="41c9f-115">Check the path and the spelling of the file name.</span></span>  
  
## <a name="net-security"></a><span data-ttu-id="41c9f-116">.NET 보안</span><span class="sxs-lookup"><span data-stu-id="41c9f-116">.NET Security</span></span>  

 <span data-ttu-id="41c9f-117">파일 이름을 사용하여 파일 내용을 확인하지 마세요.</span><span class="sxs-lookup"><span data-stu-id="41c9f-117">Do not rely on the name of a file to determine the contents of the file.</span></span> <span data-ttu-id="41c9f-118">예를 들어 `myFile.cs` 파일이 C# 소스 파일이 아닐 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="41c9f-118">For example, the file `myFile.cs` might not be a C# source file.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="41c9f-119">참조</span><span class="sxs-lookup"><span data-stu-id="41c9f-119">See also</span></span>

- <xref:System.IO?displayProperty=nameWithType>
- [<span data-ttu-id="41c9f-120">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="41c9f-120">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="41c9f-121">파일 시스템 및 레지스트리(C# 프로그래밍 가이드)</span><span class="sxs-lookup"><span data-stu-id="41c9f-121">File System and the Registry (C# Programming Guide)</span></span>](./index.md)
