---
title: '방법: 새로 만든 데이터 파일 읽기 및 쓰기'
description: .NET에서 System.IO.BinaryReader 및 System.IO.BinaryWriter 클래스를 사용하여 새로 생성된 데이터 파일에 읽고 쓰는 방법을 알아봅니다.
ms.date: 01/21/2019
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- streams, reading and writing data
- BinaryReader class, examples
- I/O [.NET], reading data
- I/O [.NET], writing data
- BinaryWriter class, examples
ms.assetid: e209d949-31e8-44ea-8e38-87f9093f3093
ms.openlocfilehash: 236d50260efa66f21db6d0abba6cc5c258a74d8d
ms.sourcegitcommit: 7588b1f16b7608bc6833c05f91ae670c22ef56f8
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/02/2020
ms.locfileid: "93188733"
---
# <a name="how-to-read-and-write-to-a-newly-created-data-file"></a><span data-ttu-id="92af9-103">방법: 새로 만든 데이터 파일 읽기 및 쓰기</span><span class="sxs-lookup"><span data-stu-id="92af9-103">How to: Read and write to a newly created data file</span></span>

<span data-ttu-id="92af9-104"><xref:System.IO.BinaryWriter?displayProperty=nameWithType>와 <xref:System.IO.BinaryReader?displayProperty=nameWithType> 클래스는 문자열이 아닌 데이터를 쓰고 읽는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="92af9-104">The <xref:System.IO.BinaryWriter?displayProperty=nameWithType> and <xref:System.IO.BinaryReader?displayProperty=nameWithType> classes are used for writing and reading data other than character strings.</span></span> <span data-ttu-id="92af9-105">다음 예제에서는 빈 파일 스트림을 만들어서 여기에 데이터를 쓰고 데이터를 읽는 방법을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="92af9-105">The following example shows how to create an empty file stream, write data to it, and read data from it.</span></span>

<span data-ttu-id="92af9-106">이 예제는 현재 디렉터리에 *Test.data* 라는 데이터 파일을 만들고, 연결된 <xref:System.IO.BinaryWriter> 및 <xref:System.IO.BinaryReader> 개체를 만들고, <xref:System.IO.BinaryWriter> 개체를 사용하여 *Test.data* 에 0부터 10까지 정수를 씁니다. 이렇게 하면 파일 포인터가 파일 끝에 옵니다.</span><span class="sxs-lookup"><span data-stu-id="92af9-106">The example creates a data file called *Test.data* in the current directory, creates the associated <xref:System.IO.BinaryWriter> and <xref:System.IO.BinaryReader> objects, and uses the <xref:System.IO.BinaryWriter> object to write the integers 0 through 10 to *Test.data* , which leaves the file pointer at the end of the file.</span></span> <span data-ttu-id="92af9-107"><xref:System.IO.BinaryReader> 개체는 파일 포인터를 다시 원점으로 설정하고, 지정된 내용을 읽습니다.</span><span class="sxs-lookup"><span data-stu-id="92af9-107">The <xref:System.IO.BinaryReader> object then sets the file pointer back to the origin and reads out the specified content.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="92af9-108">현재 디렉터리에 *Test.data* 가 이미 있는 경우, <xref:System.IO.IOException> 예외가 throw됩니다.</span><span class="sxs-lookup"><span data-stu-id="92af9-108">If *Test.data* already exists in the current directory, an <xref:System.IO.IOException> exception is thrown.</span></span> <span data-ttu-id="92af9-109">예외를 throw하지 않고 항상 새 파일을 만들려면 <xref:System.IO.FileMode.CreateNew?displayProperty=nameWithType>보다는 <xref:System.IO.FileMode.Create?displayProperty=nameWithType> 파일 모드 옵션을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="92af9-109">Use the file mode option <xref:System.IO.FileMode.Create?displayProperty=nameWithType> rather than <xref:System.IO.FileMode.CreateNew?displayProperty=nameWithType> to always create a new file without throwing an exception.</span></span>  
  
## <a name="example"></a><span data-ttu-id="92af9-110">예제</span><span class="sxs-lookup"><span data-stu-id="92af9-110">Example</span></span>  
 [!code-csharp[System.IO.BinaryReaderWriter#7](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.IO.BinaryReaderWriter/CS/source6.cs#7)]
 [!code-vb[System.IO.BinaryReaderWriter#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.IO.BinaryReaderWriter/VB/source6.vb#7)]  
  
## <a name="see-also"></a><span data-ttu-id="92af9-111">참조</span><span class="sxs-lookup"><span data-stu-id="92af9-111">See also</span></span>

- <xref:System.IO.BinaryReader>  
- <xref:System.IO.BinaryWriter>  
- <xref:System.IO.FileStream>  
- <xref:System.IO.FileStream.Seek%2A?displayProperty=nameWithType>  
- <xref:System.IO.SeekOrigin>  
- [<span data-ttu-id="92af9-112">방법: 디렉터리 및 파일 열거</span><span class="sxs-lookup"><span data-stu-id="92af9-112">How to: Enumerate directories and files</span></span>](how-to-enumerate-directories-and-files.md)  
- [<span data-ttu-id="92af9-113">방법: 로그 파일 열기 및 추가</span><span class="sxs-lookup"><span data-stu-id="92af9-113">How to: Open and append to a log file</span></span>](how-to-open-and-append-to-a-log-file.md)  
- [<span data-ttu-id="92af9-114">방법: 파일에서 텍스트 읽기</span><span class="sxs-lookup"><span data-stu-id="92af9-114">How to: Read text from a file</span></span>](how-to-read-text-from-a-file.md)  
- [<span data-ttu-id="92af9-115">방법: 파일에 텍스트 쓰기</span><span class="sxs-lookup"><span data-stu-id="92af9-115">How to: Write text to a file</span></span>](how-to-write-text-to-a-file.md)  
- [<span data-ttu-id="92af9-116">방법: 문자열에서 문자 읽기</span><span class="sxs-lookup"><span data-stu-id="92af9-116">How to: Read characters from a string</span></span>](how-to-read-characters-from-a-string.md)  
- [<span data-ttu-id="92af9-117">방법: 문자열에 문자 쓰기</span><span class="sxs-lookup"><span data-stu-id="92af9-117">How to: Write characters to a string</span></span>](how-to-write-characters-to-a-string.md)  
- [<span data-ttu-id="92af9-118">파일 및 스트림 I/O</span><span class="sxs-lookup"><span data-stu-id="92af9-118">File and stream I/O</span></span>](index.md)
