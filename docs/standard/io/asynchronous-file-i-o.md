---
title: 비동기 파일 I/O
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- streams, synchronous streams
- asynchronous I/O
- synchronous I/O
- streams, asynchronous streams
- I/O [.NET Framework], asynchronous I/O
- Stream class, synchronous I/O
- data streams, asynchronous streams
- Stream class, asynchronous I/O
- multiple I/O requests
- data streams, synchronous streams
ms.assetid: dbdd55e7-d6b9-4f9e-8abb-ab0edd4457f7
ms.openlocfilehash: 66e7d01f37a1119b9d2076a9131aa40f26d15625
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/15/2020
ms.locfileid: "75708193"
---
# <a name="asynchronous-file-io"></a><span data-ttu-id="3a342-102">비동기 파일 I/O</span><span class="sxs-lookup"><span data-stu-id="3a342-102">Asynchronous File I/O</span></span>

<span data-ttu-id="3a342-103">비동기 작업을 사용하면 주 스레드를 차단하지 않고 리소스 집중형 I/O 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3a342-103">Asynchronous operations enable you to perform resource-intensive I/O operations without blocking the main thread.</span></span> <span data-ttu-id="3a342-104">이 성능 고려 사항은 시간이 걸리는 스트림 작업이 UI 스레드를 차단하여 앱이 작동하지 않는 것처럼 보일 수 있는 Windows 8.x 스토어 앱 또는 데스크톱 앱에서 특히 중요합니다.</span><span class="sxs-lookup"><span data-stu-id="3a342-104">This performance consideration is particularly important in a Windows 8.x Store app or desktop app where a time-consuming stream operation can block the UI thread and make your app appear as if it is not working.</span></span>

<span data-ttu-id="3a342-105">.NET Framework 4.5부터 I/O 형식은 비동기 메서드를 포함하여 비동기 작업을 단순화합니다.</span><span class="sxs-lookup"><span data-stu-id="3a342-105">Starting with the .NET Framework 4.5, the I/O types include async methods to simplify asynchronous operations.</span></span> <span data-ttu-id="3a342-106">비동기 메서드의 이름에는 `Async` 가 포함합니다(예: <xref:System.IO.Stream.ReadAsync%2A>, <xref:System.IO.Stream.WriteAsync%2A>, <xref:System.IO.Stream.CopyToAsync%2A>, <xref:System.IO.Stream.FlushAsync%2A>, <xref:System.IO.TextReader.ReadLineAsync%2A>및 <xref:System.IO.TextReader.ReadToEndAsync%2A>).</span><span class="sxs-lookup"><span data-stu-id="3a342-106">An async method contains `Async` in its name, such as <xref:System.IO.Stream.ReadAsync%2A>, <xref:System.IO.Stream.WriteAsync%2A>, <xref:System.IO.Stream.CopyToAsync%2A>, <xref:System.IO.Stream.FlushAsync%2A>, <xref:System.IO.TextReader.ReadLineAsync%2A>, and <xref:System.IO.TextReader.ReadToEndAsync%2A>.</span></span> <span data-ttu-id="3a342-107">이러한 비동기 메서드는 스트림 클래스(예: <xref:System.IO.Stream>, <xref:System.IO.FileStream>및 <xref:System.IO.MemoryStream>)에 구현되거나, 스트림에서 읽거나 스트림에 쓰는 데 사용되는 클래스(예: <xref:System.IO.TextReader> 및 <xref:System.IO.TextWriter>)에 구현됩니다.</span><span class="sxs-lookup"><span data-stu-id="3a342-107">These async methods are implemented on stream classes, such as <xref:System.IO.Stream>, <xref:System.IO.FileStream>, and <xref:System.IO.MemoryStream>, and on classes that are used for reading from or writing to streams, such <xref:System.IO.TextReader> and <xref:System.IO.TextWriter>.</span></span>

<span data-ttu-id="3a342-108">.NET Framework 4 및 이전 버전에서 비동기 I/O 작업을 구현하려면 <xref:System.IO.Stream.BeginRead%2A> 및 <xref:System.IO.Stream.EndRead%2A> 와 같은 메서드를 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3a342-108">In the .NET Framework 4 and earlier versions, you have to use methods such as <xref:System.IO.Stream.BeginRead%2A> and <xref:System.IO.Stream.EndRead%2A> to implement asynchronous I/O operations.</span></span> <span data-ttu-id="3a342-109">이러한 메서드는 여전히 .NET Framework 4.5에서 사용하여 레거시 코드를 지원할 수 있지만, 비동기 메서드는 비동기 I/O 작업을 보다 쉽게 구현하도록 도와줍니다.</span><span class="sxs-lookup"><span data-stu-id="3a342-109">These methods are still available in the .NET Framework 4.5 to support legacy code; however, the async methods help you implement asynchronous I/O operations more easily.</span></span>

<span data-ttu-id="3a342-110">C# 및 Visual Basic에는 각각 비동기 프로그래밍을 위한 다음 두 개의 키워드가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3a342-110">C# and Visual Basic each have two keywords for asynchronous programming:</span></span>

- <span data-ttu-id="3a342-111">비동기 작업을 포함하는 메서드를 표시하는 데 사용되는`Async` (Visual Basic) 또는 `async` (C#) 한정자.</span><span class="sxs-lookup"><span data-stu-id="3a342-111">`Async` (Visual Basic) or `async` (C#) modifier, which is used to mark a method that contains an asynchronous operation.</span></span>

- <span data-ttu-id="3a342-112">비동기 메서드의 결과에 적용되는`Await` (Visual Basic) 또는 `await` (C#) 연산자.</span><span class="sxs-lookup"><span data-stu-id="3a342-112">`Await` (Visual Basic) or `await` (C#) operator, which is applied to the result of an async method.</span></span>

<span data-ttu-id="3a342-113">비동기 I/O 작업을 구현하려면 다음 예제와 같이 이러한 키워드를 비동기 메서드와 함께 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="3a342-113">To implement asynchronous I/O operations, use these keywords in conjunction with the async methods, as shown in the following examples.</span></span> <span data-ttu-id="3a342-114">자세한 내용은 [async 및 await를 사용한 비동기 프로그래밍(C#)](../../csharp/programming-guide/concepts/async/index.md) 또는 [Async 및 Await를 사용한 비동기 프로그래밍(Visual Basic)](../../visual-basic/programming-guide/concepts/async/index.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="3a342-114">For more information, see [Asynchronous programming with async and await (C#)](../../csharp/programming-guide/concepts/async/index.md) or [Asynchronous Programming with Async and Await (Visual Basic)](../../visual-basic/programming-guide/concepts/async/index.md).</span></span>

<span data-ttu-id="3a342-115">다음 예제에서는 두 가지 <xref:System.IO.FileStream> 개체를 사용하여 한 디렉터리에서 다른 디렉터리로 파일을 비동기적으로 복사하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="3a342-115">The following example demonstrates how to use two <xref:System.IO.FileStream> objects to copy files asynchronously from one directory to another.</span></span> <span data-ttu-id="3a342-116"><xref:System.Web.UI.WebControls.Button.Click> 컨트롤에 대한 <xref:System.Windows.Controls.Button> 이벤트 처리기는 비동기 메서드를 호출하므로 `async` 한정자로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="3a342-116">Notice that the <xref:System.Web.UI.WebControls.Button.Click> event handler for the <xref:System.Windows.Controls.Button> control is marked with the `async` modifier because it calls an asynchronous method.</span></span>

[!code-csharp[Asynchronous_File_IO_async#1](../../../samples/snippets/csharp/VS_Snippets_CLR/Asynchronous_File_IO_async/cs/example.cs#1)]
[!code-vb[Asynchronous_File_IO_async#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Asynchronous_File_IO_async/vb/example.vb#1)]

<span data-ttu-id="3a342-117">다음 예제는 이전과 유사하지만, <xref:System.IO.StreamReader> 및 <xref:System.IO.StreamWriter> 개체를 사용하여 텍스트 파일의 내용을 비동기적으로 읽고 씁니다.</span><span class="sxs-lookup"><span data-stu-id="3a342-117">The next example is similar to the previous one but uses <xref:System.IO.StreamReader> and <xref:System.IO.StreamWriter> objects to read and write the contents of a text file asynchronously.</span></span>

[!code-csharp[Asynchronous_File_IO_async#2](../../../samples/snippets/csharp/VS_Snippets_CLR/Asynchronous_File_IO_async/cs/example2.cs#2)]
[!code-vb[Asynchronous_File_IO_async#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Asynchronous_File_IO_async/vb/example2.vb#2)]

<span data-ttu-id="3a342-118">다음 예제에서는 Windows 8.x 스토어 앱에서 파일을 <xref:System.IO.Stream>(으)로 열고 <xref:System.IO.StreamReader> 클래스의 인스턴스를 사용하여 해당 내용을 읽는 데 사용되는 코드 숨김 파일 및 XAML 파일을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="3a342-118">The next example shows the code-behind file and the XAML file that are used to open a file as a <xref:System.IO.Stream> in a Windows 8.x Store app, and read its contents by using an instance of the <xref:System.IO.StreamReader> class.</span></span> <span data-ttu-id="3a342-119">비동기 메서드를 사용하여 파일을 스트림으로 열고 해당 내용을 읽습니다.</span><span class="sxs-lookup"><span data-stu-id="3a342-119">It uses asynchronous methods to open the file as a stream and to read its contents.</span></span>

[!code-csharp[System.IO.WindowsRuntimeStorageExtensions#2](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.io.windowsruntimestorageextensions/cs/blankpage.xaml.cs#2)]
[!code-vb[System.IO.WindowsRuntimeStorageExtensions#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.io.windowsruntimestorageextensions/vb/blankpage.xaml.vb#2)]

[!code-xaml[System.IO.WindowsRuntimeStorageExtensions#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.io.windowsruntimestorageextensions/cs/blankpage.xaml#1)]

## <a name="see-also"></a><span data-ttu-id="3a342-120">참고 항목</span><span class="sxs-lookup"><span data-stu-id="3a342-120">See also</span></span>

- <xref:System.IO.Stream>
- [<span data-ttu-id="3a342-121">파일 및 스트림 I/O</span><span class="sxs-lookup"><span data-stu-id="3a342-121">File and Stream I/O</span></span>](index.md)
- [<span data-ttu-id="3a342-122">async 및 await를 사용한 비동기 프로그래밍(C#)</span><span class="sxs-lookup"><span data-stu-id="3a342-122">Asynchronous programming with async and await (C#)</span></span>](../../csharp/programming-guide/concepts/async/index.md)
- [<span data-ttu-id="3a342-123">Async 및 Await를 사용한 비동기 프로그래밍(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="3a342-123">Asynchronous Programming with Async and Await (Visual Basic)</span></span>](../../visual-basic/programming-guide/concepts/async/index.md)
