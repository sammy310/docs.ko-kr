---
title: '방법: 파일에서 텍스트 읽기'
ms.date: 01/03/2019
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- streams, reading text from files
- reading text files
- reading data, text files
- data streams, reading text from files
- I/O [.NET Framework], reading text from files
ms.assetid: ed180baa-dfc6-4c69-a725-46e87edafb27
ms.openlocfilehash: 8676e5f0acd0646b4854df7dde060ec15548ec3e
ms.sourcegitcommit: 00aa62e2f469c2272a457b04e66b4cc3c97a800b
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/28/2020
ms.locfileid: "78155726"
---
# <a name="how-to-read-text-from-a-file"></a><span data-ttu-id="2504d-102">방법: 파일에서 텍스트 읽기</span><span class="sxs-lookup"><span data-stu-id="2504d-102">How to: Read text from a file</span></span>
<span data-ttu-id="2504d-103">다음 예제에서는 데스크톱 응용 프로그램용 .NET을 사용하여 텍스트 파일에서 텍스트를 동기 또는 비동기적으로 읽는 방법을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="2504d-103">The following examples show how to read text synchronously and asynchronously from a text file using .NET for desktop apps.</span></span> <span data-ttu-id="2504d-104">두 예제에서는 <xref:System.IO.StreamReader> 클래스의 인스턴스를 만들 때 파일의 상대 또는 절대 경로를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="2504d-104">In both examples, when you create the instance of the <xref:System.IO.StreamReader> class, you provide the relative or absolute path to the file.</span></span>
  
> [!NOTE]
> <span data-ttu-id="2504d-105">Windows 런타임에서는 파일을 읽고 파일에 쓰는 다양한 스트림 형식을 제공하기 때문에 이러한 코드 예제는 UWP(유니버설 Windows 플랫폼) 앱 개발에는 적용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="2504d-105">These code examples do not apply to developing for Universal Windows (UWP) apps, because the Windows Runtime provides different stream types for reading and writing to files.</span></span> <span data-ttu-id="2504d-106">UWP 앱에서 파일의 텍스트를 읽는 방법을 보여주는 예제는 [빠른 시작: 파일 읽기 및 쓰기](https://docs.microsoft.com/previous-versions/windows/apps/hh758325(v=win.10))를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="2504d-106">For an example that shows how to read text from a file in a UWP app, see [Quickstart: Reading and writing files](https://docs.microsoft.com/previous-versions/windows/apps/hh758325(v=win.10)).</span></span> <span data-ttu-id="2504d-107">.NET Framework 스트림과 Windows 런타임 스트림 간의 변환 방법을 보여주는 예제는 [방법: .NET Framework 스트림과 Windows 런타임 스트림 간 변환](../../../docs/standard/io/how-to-convert-between-dotnet-streams-and-winrt-streams.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="2504d-107">For examples that show how to convert between .NET Framework streams and Windows Runtime streams, see [How to: Convert between .NET Framework streams and Windows Runtime streams](../../../docs/standard/io/how-to-convert-between-dotnet-streams-and-winrt-streams.md).</span></span>  
  
## <a name="example-synchronous-read-in-a-console-app"></a><span data-ttu-id="2504d-108">예: 콘솔 앱 내에서 동기식 읽기</span><span class="sxs-lookup"><span data-stu-id="2504d-108">Example: Synchronous read in a console app</span></span>  
<span data-ttu-id="2504d-109">다음 예제에서는 콘솔 앱 내에서 동기식 읽기 작업을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="2504d-109">The following example shows a synchronous read operation within a console app.</span></span> <span data-ttu-id="2504d-110">이 예제에서는 스트림 판독기를 사용하여 텍스트 파일을 열고 콘텐츠를 문자열로 복사한 다음, 콘솔에 문자열을 출력합니다.</span><span class="sxs-lookup"><span data-stu-id="2504d-110">This example opens the text file using a stream reader, copies the contents to a string, and outputs the string to the console.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="2504d-111">이 예제에서는 *TestFile.txt* 파일이 앱과 동일한 폴더에 이미 존재한다고 가정합니다.</span><span class="sxs-lookup"><span data-stu-id="2504d-111">The example assumes that a file named *TestFile.txt* already exists in the same folder as the app.</span></span>  

 [!code-csharp[Conceptual.BasicIO.TextFiles#3](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.basicio.textfiles/cs/source3.cs#3)]
 [!code-vb[Conceptual.BasicIO.TextFiles#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.basicio.textfiles/vb/source3.vb#3)]  
  
## <a name="example-asynchronous-read-in-a-wpf-app"></a><span data-ttu-id="2504d-112">예: WPF 앱에서 비동기식 읽기</span><span class="sxs-lookup"><span data-stu-id="2504d-112">Example: Asynchronous read in a WPF app</span></span>
 <span data-ttu-id="2504d-113">다음 예제에서는 WPF(Windows Presentation Foundation) 앱에서 비동기식 읽기 작업을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="2504d-113">The following example shows an asynchronous read operation in a Windows Presentation Foundation (WPF) app.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="2504d-114">이 예제에서는 *TestFile.txt* 파일이 앱과 동일한 폴더에 이미 존재한다고 가정합니다.</span><span class="sxs-lookup"><span data-stu-id="2504d-114">The example assumes that a file named *TestFile.txt* already exists in the same folder as the app.</span></span>  

 [!code-csharp[TextFiles](../../../samples/snippets/csharp/VS_Snippets_Wpf/TextFiles/MainWindow.xaml.cs)]
 [!code-vb[TextFiles](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TextFiles/MainWindow.xaml.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="2504d-115">참조</span><span class="sxs-lookup"><span data-stu-id="2504d-115">See also</span></span>

- <xref:System.IO.StreamReader>  
- <xref:System.IO.File.OpenText%2A?displayProperty=nameWithType>  
- <xref:System.IO.StreamReader.ReadLine%2A?displayProperty=nameWithType>  
- [<span data-ttu-id="2504d-116">비동기 파일 I/O</span><span class="sxs-lookup"><span data-stu-id="2504d-116">Asynchronous file I/O</span></span>](../../../docs/standard/io/asynchronous-file-i-o.md)  
- <span data-ttu-id="2504d-117">[방법: 디렉터리 목록 만들기](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/5cf8zcfh(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="2504d-117">[How to: Create a directory listing](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/5cf8zcfh(v=vs.100))</span></span>  
- [<span data-ttu-id="2504d-118">빠른 시작: 파일 읽기 및 쓰기</span><span class="sxs-lookup"><span data-stu-id="2504d-118">Quickstart: Reading and writing files</span></span>](https://docs.microsoft.com/previous-versions/windows/apps/hh758325%28v=win.10%29)  
- [<span data-ttu-id="2504d-119">방법: .NET Framework 스트림과 Windows 런타임 스트림 간 변환</span><span class="sxs-lookup"><span data-stu-id="2504d-119">How to: Convert between .NET Framework streams and Windows Runtime streams</span></span>](../../../docs/standard/io/how-to-convert-between-dotnet-streams-and-winrt-streams.md)  
- [<span data-ttu-id="2504d-120">방법: 새로 만든 데이터 파일 읽기 및 쓰기</span><span class="sxs-lookup"><span data-stu-id="2504d-120">How to: Read and write to a newly created data file</span></span>](../../../docs/standard/io/how-to-read-and-write-to-a-newly-created-data-file.md)  
- [<span data-ttu-id="2504d-121">방법: 로그 파일 열기 및 추가</span><span class="sxs-lookup"><span data-stu-id="2504d-121">How to: Open and append to a log file</span></span>](../../../docs/standard/io/how-to-open-and-append-to-a-log-file.md)  
- [<span data-ttu-id="2504d-122">방법: 파일에 텍스트 쓰기</span><span class="sxs-lookup"><span data-stu-id="2504d-122">How to: Write text to a file</span></span>](../../../docs/standard/io/how-to-write-text-to-a-file.md)  
- [<span data-ttu-id="2504d-123">방법: 문자열에서 문자 읽기</span><span class="sxs-lookup"><span data-stu-id="2504d-123">How to: Read characters from a string</span></span>](../../../docs/standard/io/how-to-read-characters-from-a-string.md)  
- [<span data-ttu-id="2504d-124">방법: 문자열에 문자 쓰기</span><span class="sxs-lookup"><span data-stu-id="2504d-124">How to: Write characters to a string</span></span>](../../../docs/standard/io/how-to-write-characters-to-a-string.md)  
- [<span data-ttu-id="2504d-125">파일 및 스트림 I/O</span><span class="sxs-lookup"><span data-stu-id="2504d-125">File and stream I/O</span></span>](../../../docs/standard/io/index.md)
