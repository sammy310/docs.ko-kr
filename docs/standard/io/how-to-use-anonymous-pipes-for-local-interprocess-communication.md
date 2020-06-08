---
title: '방법: 로컬 프로세스 간 통신에 익명 파이프 사용'
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- anonymous pipes [.NET Framework]
- parent-child communication [.NET Framework]
- pipes [.NET Framework]
- one-way communication [.NET Framework]
- local computer communication [.NET Framework], pipes
ms.assetid: e7773c77-c646-4a01-8a96-a003d59fc4c9
ms.openlocfilehash: 9962471697888041e98e38dd5f7feaecc306894d
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/02/2020
ms.locfileid: "84291788"
---
# <a name="how-to-use-anonymous-pipes-for-local-interprocess-communication"></a><span data-ttu-id="444e8-102">방법: 로컬 프로세스 간 통신에 익명 파이프 사용</span><span class="sxs-lookup"><span data-stu-id="444e8-102">How to: Use Anonymous Pipes for Local Interprocess Communication</span></span>
<span data-ttu-id="444e8-103">익명 파이프는 로컬 컴퓨터에서 프로세스 간 통신을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="444e8-103">Anonymous pipes provide interprocess communication on a local computer.</span></span> <span data-ttu-id="444e8-104">명명된 파이프보다 적은 기능을 제공하지만 오버로드를 더 적게 필요로 합니다.</span><span class="sxs-lookup"><span data-stu-id="444e8-104">They offer less functionality than named pipes, but also require less overhead.</span></span> <span data-ttu-id="444e8-105">익명 파이프를 사용하면 로컬 컴퓨터에서 프로세스 간 통신을 더욱 쉽게 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="444e8-105">You can use anonymous pipes to make interprocess communication on a local computer easier.</span></span> <span data-ttu-id="444e8-106">네트워크를 통한 통신에는 익명 파이프를 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="444e8-106">You cannot use anonymous pipes for communication over a network.</span></span>  
  
 <span data-ttu-id="444e8-107">익명 파이프를 구현하려면, <xref:System.IO.Pipes.AnonymousPipeServerStream> 및 <xref:System.IO.Pipes.AnonymousPipeClientStream> 클래스를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="444e8-107">To implement anonymous pipes, use the <xref:System.IO.Pipes.AnonymousPipeServerStream> and <xref:System.IO.Pipes.AnonymousPipeClientStream> classes.</span></span>  
  
## <a name="example"></a><span data-ttu-id="444e8-108">예제</span><span class="sxs-lookup"><span data-stu-id="444e8-108">Example</span></span>  
 <span data-ttu-id="444e8-109">다음 예제는 익명 파이프를 사용하여 부모 프로세스에서 자식 프로세스로 문자열을 보내는 방법을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="444e8-109">The following example demonstrates a way to send a string from a parent process to a child process using anonymous pipes.</span></span> <span data-ttu-id="444e8-110">이 예제는 <xref:System.IO.Pipes.PipeDirection.Out>의 <xref:System.IO.Pipes.PipeDirection> 값을 사용하여 부모 프로세스에서 <xref:System.IO.Pipes.AnonymousPipeServerStream> 개체를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="444e8-110">This example creates an <xref:System.IO.Pipes.AnonymousPipeServerStream> object in a parent process with a <xref:System.IO.Pipes.PipeDirection> value of <xref:System.IO.Pipes.PipeDirection.Out>.</span></span> <span data-ttu-id="444e8-111">그런 다음, 부모 프로세스는 클라이언트 핸들을 사용하여 <xref:System.IO.Pipes.AnonymousPipeClientStream> 개체를 생성함으로써 자식 프로세스를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="444e8-111">The parent process then creates a child process by using a client handle to create an <xref:System.IO.Pipes.AnonymousPipeClientStream> object.</span></span> <span data-ttu-id="444e8-112">자식 프로세스에는 <xref:System.IO.Pipes.PipeDirection.In>의 <xref:System.IO.Pipes.PipeDirection> 값이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="444e8-112">The child process has a <xref:System.IO.Pipes.PipeDirection> value of <xref:System.IO.Pipes.PipeDirection.In>.</span></span>  
  
 <span data-ttu-id="444e8-113">그런 다음, 부모 프로세스는 사용자가 제공한 문자열을 자식 프로세스로 보냅니다.</span><span class="sxs-lookup"><span data-stu-id="444e8-113">The parent process then sends a user-supplied string to the child process.</span></span> <span data-ttu-id="444e8-114">문자열이 자식 프로세스의 콘솔에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="444e8-114">The string is displayed to the console in the child process.</span></span>  
  
 <span data-ttu-id="444e8-115">다음 예제는 서버 프로세스를 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="444e8-115">The following example shows the server process.</span></span>  
  
 [!code-cpp[System.IO.Pipes.AnonymousPipeServerStream_Sample#01](../../../samples/snippets/cpp/VS_Snippets_CLR_System/system.IO.Pipes.AnonymousPipeServerStream_Sample/cpp/program.cpp#01)]
 [!code-csharp[System.IO.Pipes.AnonymousPipeServerStream_Sample#01](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.IO.Pipes.AnonymousPipeServerStream_Sample/cs/Program.cs#01)]
 [!code-vb[System.IO.Pipes.AnonymousPipeServerStream_Sample#01](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.IO.Pipes.AnonymousPipeServerStream_Sample/vb/program.vb#01)]  

[!INCLUDE [localized code comments](../../../includes/code-comments-loc.md)]
  
## <a name="example"></a><span data-ttu-id="444e8-116">예제</span><span class="sxs-lookup"><span data-stu-id="444e8-116">Example</span></span>  
 <span data-ttu-id="444e8-117">다음 예제는 클라이언트 프로세스를 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="444e8-117">The following example shows the client process.</span></span> <span data-ttu-id="444e8-118">서버 프로세스는 클라이언트 프로세스를 시작하고 해당 프로세스에 클라이언트 핸들을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="444e8-118">The server process starts the client process and gives that process a client handle.</span></span> <span data-ttu-id="444e8-119">클라이언트 코드의 결과 실행 파일 이름은 `pipeClient.exe`이어야 하며 서버 프로세스를 실행하기 전에 서버 실행 파일과 동일한 디렉터리로 복사해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="444e8-119">The resulting executable from the client code should be named `pipeClient.exe` and be copied to the same directory as the server executable before running the server process.</span></span>  
  
 [!code-cpp[System.IO.Pipes.AnonymousPipeClientStream_Sample#01](../../../samples/snippets/cpp/VS_Snippets_CLR_System/system.IO.Pipes.AnonymousPipeClientStream_Sample/cpp/program.cpp#01)]
 [!code-csharp[System.IO.Pipes.AnonymousPipeClientStream_Sample#01](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.IO.Pipes.AnonymousPipeClientStream_Sample/cs/Program.cs#01)]
 [!code-vb[System.IO.Pipes.AnonymousPipeClientStream_Sample#01](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.IO.Pipes.AnonymousPipeClientStream_Sample/vb/program.vb#01)]  
  
## <a name="see-also"></a><span data-ttu-id="444e8-120">참고 항목</span><span class="sxs-lookup"><span data-stu-id="444e8-120">See also</span></span>

- [<span data-ttu-id="444e8-121">파이프</span><span class="sxs-lookup"><span data-stu-id="444e8-121">Pipes</span></span>](pipe-operations.md)
- [<span data-ttu-id="444e8-122">방법: 네트워크 프로세스 간 통신에 명명된 파이프 사용</span><span class="sxs-lookup"><span data-stu-id="444e8-122">How to: Use Named Pipes for Network Interprocess Communication</span></span>](how-to-use-named-pipes-for-network-interprocess-communication.md)
