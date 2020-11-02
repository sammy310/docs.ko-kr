---
title: 스트림 작성
ms.date: 01/21/2019
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- streams, base streams
- I/O [.NET], composing streams
- Stream class, composing streams
- base streams
- streams, backing stores
ms.assetid: da761658-a535-4f26-a452-b30df47f73d5
ms.openlocfilehash: 93295c1d70f510ef563abc3a191d6690b1174fa8
ms.sourcegitcommit: 7588b1f16b7608bc6833c05f91ae670c22ef56f8
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/02/2020
ms.locfileid: "93188577"
---
# <a name="compose-streams"></a><span data-ttu-id="36a7d-102">스트림 작성</span><span class="sxs-lookup"><span data-stu-id="36a7d-102">Compose streams</span></span>
<span data-ttu-id="36a7d-103">백업 저장소( *backing store* )는 디스크 또는 메모리와 같은 스토리지 매체입니다.</span><span class="sxs-lookup"><span data-stu-id="36a7d-103">A *backing store* is a storage medium, such as a disk or memory.</span></span> <span data-ttu-id="36a7d-104">다양한 각 백업 저장소는 <xref:System.IO.Stream> 클래스의 구현으로 고유한 스트림을 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="36a7d-104">Each different backing store implements its own stream as an implementation of the <xref:System.IO.Stream> class.</span></span>

<span data-ttu-id="36a7d-105">각 스트림 유형은 지정된 백업 저장소에 유입 또는 유출되는 바이트를 읽고 씁니다.</span><span class="sxs-lookup"><span data-stu-id="36a7d-105">Each stream type reads and writes bytes from and to its given backing store.</span></span> <span data-ttu-id="36a7d-106">백업 저장소에 연결되는 스트림을 기본 스트림( *base stream* )이라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="36a7d-106">Streams that connect to backing stores are called *base streams* .</span></span> <span data-ttu-id="36a7d-107">기본 스트림에는 스트림을 백업 저장소에 연결하는 데 필요한 매개 변수가 포함된 생성자가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="36a7d-107">Base streams have constructors with the parameters necessary to connect the stream to the backing store.</span></span> <span data-ttu-id="36a7d-108">예를 들어 <xref:System.IO.FileStream>에는 프로세스가 경로 매개 변수를 지정하는 생성자가 있으며, 이것은 프로세스가 파일을 공유하는 방법을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="36a7d-108">For example, <xref:System.IO.FileStream> has constructors that specify a path parameter, which specifies how the file will be shared by processes.</span></span>  

<span data-ttu-id="36a7d-109"><xref:System.IO> 클래스 디자인은 간소화된 스트림 컴퍼지션을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="36a7d-109">The design of the <xref:System.IO> classes provides simplified stream composition.</span></span> <span data-ttu-id="36a7d-110">원하는 기능을 제공하는 하나 이상의 통과 스트림에 기본 스트림을 연결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="36a7d-110">You can attach base streams to one or more pass-through streams that provide the functionality you want.</span></span> <span data-ttu-id="36a7d-111">체인 끝에 reader 또는 writer를 연결할 수 있기 때문에 기본 형식을 쉽게 읽거나 쓸 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="36a7d-111">You can attach a reader or writer to the end of the chain, so the preferred types can be read or written easily.</span></span>  

<span data-ttu-id="36a7d-112">다음 코드 예제에서는 *MyFile.txt* 를 버퍼링하기 위해 기존 *MyFile.txt* 를 바탕으로 **FileStream** 을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="36a7d-112">The following code examples create a **FileStream** around the existing *MyFile.txt* in order to buffer *MyFile.txt* .</span></span> <span data-ttu-id="36a7d-113">**FileStream** 은 기본적으로 버퍼링됩니다.</span><span class="sxs-lookup"><span data-stu-id="36a7d-113">Note that **FileStreams** are buffered by default.</span></span>

>[!IMPORTANT]
><span data-ttu-id="36a7d-114">예제에서는 *MyFile.txt* 파일이 앱과 동일한 폴더에 이미 존재한다고 가정합니다.</span><span class="sxs-lookup"><span data-stu-id="36a7d-114">The examples assume that a file named *MyFile.txt* already exists in the same folder as the app.</span></span>  

## <a name="example-use-streamreader"></a><span data-ttu-id="36a7d-115">예: StreamReader 사용</span><span class="sxs-lookup"><span data-stu-id="36a7d-115">Example: Use StreamReader</span></span>
<span data-ttu-id="36a7d-116">다음 예제에서는 생성자 인수로 **StreamReader** 에 전달되는 **FileStream** 에서 문자를 읽는 <xref:System.IO.StreamReader>를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="36a7d-116">The following example creates a <xref:System.IO.StreamReader> to read characters from the **FileStream** , which is passed to the **StreamReader** as its constructor argument.</span></span> <span data-ttu-id="36a7d-117"><xref:System.IO.StreamReader.ReadLine%2A?displayProperty=nameWithType>은 <xref:System.IO.StreamReader.Peek%2A?displayProperty=nameWithType>에서 더 이상 문자를 찾지 못할 때까지 읽습니다.</span><span class="sxs-lookup"><span data-stu-id="36a7d-117"><xref:System.IO.StreamReader.ReadLine%2A?displayProperty=nameWithType> then reads until <xref:System.IO.StreamReader.Peek%2A?displayProperty=nameWithType> finds no more characters.</span></span>  
  
 [!code-csharp[System.IO.StreamReader#20](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.IO.StreamReader/CS/source2.cs#20)]
 [!code-vb[System.IO.StreamReader#20](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.IO.StreamReader/VB/source2.vb#20)]  
  
## <a name="example-use-binaryreader"></a><span data-ttu-id="36a7d-118">예: BinaryReader 사용</span><span class="sxs-lookup"><span data-stu-id="36a7d-118">Example: Use BinaryReader</span></span>
<span data-ttu-id="36a7d-119">다음 예제에서는 생성자 인수로 **BinaryReader** 에 전달되는 **FileStream** 에서 바이트를 읽는 <xref:System.IO.BinaryReader>를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="36a7d-119">The following example creates a <xref:System.IO.BinaryReader> to read bytes from the **FileStream** , which is passed to the **BinaryReader** as its constructor argument.</span></span> <span data-ttu-id="36a7d-120"><xref:System.IO.BinaryReader.ReadByte%2A>는 <xref:System.IO.BinaryReader.PeekChar%2A>에서 더 이상 바이트를 찾지 못할 때까지 읽습니다.</span><span class="sxs-lookup"><span data-stu-id="36a7d-120"><xref:System.IO.BinaryReader.ReadByte%2A> then reads until <xref:System.IO.BinaryReader.PeekChar%2A> finds no more bytes.</span></span>  
  
 [!code-csharp[System.IO.StreamReader#21](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.IO.StreamReader/CS/source3.cs#21)]
 [!code-vb[System.IO.StreamReader#21](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.IO.StreamReader/VB/source3.vb#21)]  
  
## <a name="see-also"></a><span data-ttu-id="36a7d-121">참조</span><span class="sxs-lookup"><span data-stu-id="36a7d-121">See also</span></span>

- <xref:System.IO.StreamReader>
- <xref:System.IO.StreamReader.ReadLine%2A?displayProperty=nameWithType>
- <xref:System.IO.StreamReader.Peek%2A?displayProperty=nameWithType>
- <xref:System.IO.FileStream>
- <xref:System.IO.BinaryReader>
- <xref:System.IO.BinaryReader.ReadByte%2A?displayProperty=nameWithType>
- <xref:System.IO.BinaryReader.PeekChar%2A?displayProperty=nameWithType>
