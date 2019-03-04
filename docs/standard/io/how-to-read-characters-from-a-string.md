---
title: '방법: 문자열에서 문자 읽기'
ms.date: 01/21/2019
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- reading characters from strings
- data streams, reading characters from string
- I/O [.NET Framework], reading characters from strings
- reading data, strings
- streams, reading characters from string
ms.assetid: 27ea5e52-6db8-42d8-980a-50bcfc7fd270
author: mairaw
ms.author: mairaw
ms.openlocfilehash: e890e4172e645e9919ea88ec5835aaed7432c0c6
ms.sourcegitcommit: bd28ff1e312eaba9718c4f7ea272c2d4781a7cac
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/26/2019
ms.locfileid: "56835202"
---
# <a name="how-to-read-characters-from-a-string"></a><span data-ttu-id="d0e7d-102">방법: 문자열에서 문자 읽기</span><span class="sxs-lookup"><span data-stu-id="d0e7d-102">How to: Read characters from a string</span></span>
<span data-ttu-id="d0e7d-103">다음 코드 예제는 문자열에서 동기식 또는 비동기식으로 문자를 읽는 방법을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="d0e7d-103">The following code examples show how to read characters synchronously or asynchronously from a string.</span></span>  
  
## <a name="example-read-characters-synchronously"></a><span data-ttu-id="d0e7d-104">예제: 동기식으로 문자 읽기</span><span class="sxs-lookup"><span data-stu-id="d0e7d-104">Example: Read characters synchronously</span></span> 
 <span data-ttu-id="d0e7d-105">이 예제에서는 문자열에서 동기식으로 13자를 읽고, 배열에 저장하고, 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="d0e7d-105">This example reads 13 characters synchronously from a string, stores them in an array, and displays them.</span></span> <span data-ttu-id="d0e7d-106">그런 다음, 문자열의 나머지 문자를 읽고, 6번째 요소에서 시작하는 배열에 저장하고, 배열의 콘텐츠를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="d0e7d-106">The example then reads the rest of the characters in the string, stores them in the array starting at the sixth element, and displays the contents of the array.</span></span>  
  
 [!code-csharp[Conceptual.StringReader#1](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.stringreader/cs/source.cs#1)]
 [!code-vb[Conceptual.StringReader#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.stringreader/vb/source.vb#1)]  
  
## <a name="example-read-characters-asynchronously"></a><span data-ttu-id="d0e7d-107">예제: 비동기식으로 문자 읽기</span><span class="sxs-lookup"><span data-stu-id="d0e7d-107">Example: Read characters asynchronously</span></span>  
 <span data-ttu-id="d0e7d-108">다음 예제는 WPF 앱의 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="d0e7d-108">The next example is the code behind a WPF app.</span></span> <span data-ttu-id="d0e7d-109">창 로드 시, 이 예제는 <xref:System.Windows.Controls.TextBox> 컨트롤에서 모든 문자를 비동기식으로 읽고 배열에 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="d0e7d-109">On window load, the example asynchronously reads all characters from a <xref:System.Windows.Controls.TextBox> control and stores them in an array.</span></span> <span data-ttu-id="d0e7d-110">그런 다음, 각 문자 또는 공백 문자를 <xref:System.Windows.Controls.TextBlock> 컨트롤의 별도 라인에 비동기식으로 씁니다.</span><span class="sxs-lookup"><span data-stu-id="d0e7d-110">It then asynchronously writes each letter or white-space character to a separate line of a <xref:System.Windows.Controls.TextBlock> control.</span></span>  
  
 [!code-csharp[Conceptual.StringReader#2](../../../samples/snippets/csharp/VS_Snippets_Wpf/StringReaderWriter/MainWindow.xaml.cs)]
 [!code-vb[Conceptual.StringReader#2](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/StringReaderWriter/MainWindow.xaml.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="d0e7d-111">참고 항목</span><span class="sxs-lookup"><span data-stu-id="d0e7d-111">See also</span></span>

- <xref:System.IO.StringReader>  
- <xref:System.IO.StringReader.Read%2A?displayProperty=nameWithType>  
- [<span data-ttu-id="d0e7d-112">비동기 파일 I/O</span><span class="sxs-lookup"><span data-stu-id="d0e7d-112">Asynchronous file I/O</span></span>](../../../docs/standard/io/asynchronous-file-i-o.md)  
- <span data-ttu-id="d0e7d-113">[방법: 디렉터리 목록 만들기](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/5cf8zcfh(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="d0e7d-113">[How to: Create a directory listing](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/5cf8zcfh(v=vs.100))</span></span>  
- [<span data-ttu-id="d0e7d-114">방법: 새로 만든 데이터 파일 읽기 및 쓰기</span><span class="sxs-lookup"><span data-stu-id="d0e7d-114">How to: Read and write to a newly created data file</span></span>](../../../docs/standard/io/how-to-read-and-write-to-a-newly-created-data-file.md)  
- [<span data-ttu-id="d0e7d-115">방법: 로그 파일 열기 및 추가</span><span class="sxs-lookup"><span data-stu-id="d0e7d-115">How to: Open and append to a log file</span></span>](../../../docs/standard/io/how-to-open-and-append-to-a-log-file.md)  
- [<span data-ttu-id="d0e7d-116">방법: 파일에서 텍스트 읽기</span><span class="sxs-lookup"><span data-stu-id="d0e7d-116">How to: Read text from a file</span></span>](../../../docs/standard/io/how-to-read-text-from-a-file.md)  
- [<span data-ttu-id="d0e7d-117">방법: 파일에 텍스트 쓰기</span><span class="sxs-lookup"><span data-stu-id="d0e7d-117">How to: Write text to a file</span></span>](../../../docs/standard/io/how-to-write-text-to-a-file.md)  
- [<span data-ttu-id="d0e7d-118">방법: 문자열에 문자 쓰기</span><span class="sxs-lookup"><span data-stu-id="d0e7d-118">How to: Write characters to a string</span></span>](../../../docs/standard/io/how-to-write-characters-to-a-string.md)  
- [<span data-ttu-id="d0e7d-119">파일 및 스트림 I/O</span><span class="sxs-lookup"><span data-stu-id="d0e7d-119">File and stream I/O</span></span>](../../../docs/standard/io/index.md)
