---
title: '방법: 문자열에 문자 쓰기'
ms.date: 01/21/2019
dev_langs:
- csharp
- vb
helpviewer_keywords:
- data streams, writing characters to string
- writing characters to strings
- streams, writing characters to strings
- I/O [.NET], writing characters to strings
ms.assetid: 1222cbeb-0760-44bf-9888-914a2a37174b
ms.openlocfilehash: d4a6bbc77a9feb16293fc88e1598d124d8d2d75d
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/18/2020
ms.locfileid: "94829728"
---
# <a name="how-to-write-characters-to-a-string"></a><span data-ttu-id="a36bf-102">방법: 문자열에 문자 쓰기</span><span class="sxs-lookup"><span data-stu-id="a36bf-102">How to: Write characters to a string</span></span>

<span data-ttu-id="a36bf-103">다음 코드 예제는 동기식 또는 비동기식으로 문자 배열에서 문자열로 문자를 씁니다.</span><span class="sxs-lookup"><span data-stu-id="a36bf-103">The following code examples write characters synchronously or asynchronously from a character array into a string.</span></span>  
  
## <a name="example-write-characters-synchronously-in-a-console-app"></a><span data-ttu-id="a36bf-104">예: 콘솔 앱에서 동기식으로 문자 쓰기</span><span class="sxs-lookup"><span data-stu-id="a36bf-104">Example: Write characters synchronously in a console app</span></span>  
 <span data-ttu-id="a36bf-105">다음 예제에서는 <xref:System.IO.StringWriter>를 사용하여 동기식으로 <xref:System.Text.StringBuilder> 개체에 문자 5개를 씁니다.</span><span class="sxs-lookup"><span data-stu-id="a36bf-105">The following example uses a <xref:System.IO.StringWriter> to write five characters synchronously to a <xref:System.Text.StringBuilder> object.</span></span>
  
 [!code-csharp[Conceptual.StringBuilder#9](../../../samples/snippets/csharp/VS_Snippets_CLR/Conceptual.StringBuilder/cs/example2.cs#9)]
 [!code-vb[Conceptual.StringBuilder#9](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Conceptual.StringBuilder/vb/example2.vb#9)]  
  
## <a name="example-write-characters-asynchronously-in-a-wpf-app"></a><span data-ttu-id="a36bf-106">예: WPF 앱에서 문자를 비동기식으로 쓰기</span><span class="sxs-lookup"><span data-stu-id="a36bf-106">Example: Write characters asynchronously in a WPF app</span></span>
 <span data-ttu-id="a36bf-107">다음 예제는 WPF 앱의 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="a36bf-107">The next example is the code behind a WPF app.</span></span> <span data-ttu-id="a36bf-108">창 로드 시, 이 예제는 <xref:System.Windows.Controls.TextBox> 컨트롤에서 모든 문자를 비동기식으로 읽고 배열에 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="a36bf-108">On window load, the example asynchronously reads all characters from a <xref:System.Windows.Controls.TextBox> control and stores them in an array.</span></span> <span data-ttu-id="a36bf-109">그런 다음, 각 문자 또는 공백 문자를 <xref:System.Windows.Controls.TextBlock> 컨트롤의 별도 라인에 비동기식으로 씁니다.</span><span class="sxs-lookup"><span data-stu-id="a36bf-109">It then asynchronously writes each letter or white-space character to a separate line of a <xref:System.Windows.Controls.TextBlock> control.</span></span>  
  
 [!code-csharp[StreamReaderWriter](../../../samples/snippets/csharp/VS_Snippets_Wpf/StringReaderWriter/MainWindow.xaml.cs)]
 [!code-vb[StreamReaderWriter](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/StringReaderWriter/MainWindow.xaml.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="a36bf-110">참조</span><span class="sxs-lookup"><span data-stu-id="a36bf-110">See also</span></span>

- <xref:System.IO.StringWriter>  
- <xref:System.IO.StringWriter.Write%2A?displayProperty=nameWithType>  
- <xref:System.Text.StringBuilder>  
- [<span data-ttu-id="a36bf-111">파일 및 스트림 I/O</span><span class="sxs-lookup"><span data-stu-id="a36bf-111">File and stream I/O</span></span>](index.md)  
- [<span data-ttu-id="a36bf-112">비동기 파일 I/O</span><span class="sxs-lookup"><span data-stu-id="a36bf-112">Asynchronous file I/O</span></span>](asynchronous-file-i-o.md)  
- [<span data-ttu-id="a36bf-113">방법: 디렉터리 및 파일 열거</span><span class="sxs-lookup"><span data-stu-id="a36bf-113">How to: Enumerate directories and files</span></span>](how-to-enumerate-directories-and-files.md)  
- [<span data-ttu-id="a36bf-114">방법: 새로 만든 데이터 파일 읽기 및 쓰기</span><span class="sxs-lookup"><span data-stu-id="a36bf-114">How to: Read and write to a newly created data file</span></span>](how-to-read-and-write-to-a-newly-created-data-file.md)  
- [<span data-ttu-id="a36bf-115">방법: 로그 파일 열기 및 추가</span><span class="sxs-lookup"><span data-stu-id="a36bf-115">How to: Open and append to a log file</span></span>](how-to-open-and-append-to-a-log-file.md)  
- [<span data-ttu-id="a36bf-116">방법: 파일에서 텍스트 읽기</span><span class="sxs-lookup"><span data-stu-id="a36bf-116">How to: Read text from a file</span></span>](how-to-read-text-from-a-file.md)  
- [<span data-ttu-id="a36bf-117">방법: 파일에 텍스트 쓰기</span><span class="sxs-lookup"><span data-stu-id="a36bf-117">How to: Write text to a file</span></span>](how-to-write-text-to-a-file.md)  
- [<span data-ttu-id="a36bf-118">방법: 문자열에서 문자 읽기</span><span class="sxs-lookup"><span data-stu-id="a36bf-118">How to: Read characters from a string</span></span>](how-to-read-characters-from-a-string.md)
