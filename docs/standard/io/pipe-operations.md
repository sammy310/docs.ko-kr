---
title: .NET의 파이프 작업
description: .NET의 파이프 작업에 대해 알아봅니다. 파이프는 프로세스 간 통신을 위한 수단을 제공합니다. 파이프에는 익명 파이프와 명명된 파이프의 두 종류가 있습니다.
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- pipes [.NET]
- pipe operations [.NET]
- interprocess communication [.NET], pipes
- I/O [.NET], pipes
ms.assetid: 7b964ebd-7a4f-4d28-8194-7841f9e4c702
ms.openlocfilehash: 8d954d55e07a7cbb2b09843afe7f45b1ff5abcc7
ms.sourcegitcommit: 7588b1f16b7608bc6833c05f91ae670c22ef56f8
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/02/2020
ms.locfileid: "93188863"
---
# <a name="pipe-operations-in-net"></a><span data-ttu-id="f4402-105">.NET의 파이프 작업</span><span class="sxs-lookup"><span data-stu-id="f4402-105">Pipe Operations in .NET</span></span>
<span data-ttu-id="f4402-106">파이프는 프로세스 간 통신을 위한 수단을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="f4402-106">Pipes provide a means for interprocess communication.</span></span> <span data-ttu-id="f4402-107">파이프에는 다음과 같이 두 가지 유형이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f4402-107">There are two types of pipes:</span></span>  
  
- <span data-ttu-id="f4402-108">익명 파이프</span><span class="sxs-lookup"><span data-stu-id="f4402-108">Anonymous pipes.</span></span>  
  
     <span data-ttu-id="f4402-109">익명 파이프는 로컬 컴퓨터에서 프로세스 간 통신을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="f4402-109">Anonymous pipes provide interprocess communication on a local computer.</span></span> <span data-ttu-id="f4402-110">익명 파이프에는 명명된 파이프보다 적은 오버헤드가 필요하지만 그만큼 제한된 서비스를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="f4402-110">Anonymous pipes require less overhead than named pipes but offer limited services.</span></span> <span data-ttu-id="f4402-111">익명 파이프는 단방향이므로 네트워크에서 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="f4402-111">Anonymous pipes are one-way and cannot be used over a network.</span></span> <span data-ttu-id="f4402-112">익명 파이프는 단일 서버 인스턴스만 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="f4402-112">They support only a single server instance.</span></span> <span data-ttu-id="f4402-113">익명 파이프는 스레드 간 통신 또는 자식 프로세스가 생성될 때 자식 프로세스에 파이프 핸들을 쉽게 전달할 수 있는 부모와 자식 프로세스 간 통신에 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="f4402-113">Anonymous pipes are useful for communication between threads, or between parent and child processes where the pipe handles can be easily passed to the child process when it is created.</span></span>  
  
     <span data-ttu-id="f4402-114">.NET에서는 <xref:System.IO.Pipes.AnonymousPipeServerStream> 및 <xref:System.IO.Pipes.AnonymousPipeClientStream> 클래스를 사용하여 익명 파이프를 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="f4402-114">In .NET, you implement anonymous pipes by using the <xref:System.IO.Pipes.AnonymousPipeServerStream> and <xref:System.IO.Pipes.AnonymousPipeClientStream> classes.</span></span>  
  
     <span data-ttu-id="f4402-115">[방법: 로컬 프로세스 간 통신에 익명 파이프 사용](how-to-use-anonymous-pipes-for-local-interprocess-communication.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f4402-115">See [How to: Use Anonymous Pipes for Local Interprocess Communication](how-to-use-anonymous-pipes-for-local-interprocess-communication.md).</span></span>  
  
- <span data-ttu-id="f4402-116">명명된 파이프</span><span class="sxs-lookup"><span data-stu-id="f4402-116">Named pipes.</span></span>  
  
     <span data-ttu-id="f4402-117">명명된 파이프는 파이프 서버와 하나 이상의 파이프 클라이언트 간의 프로세스 간 통신을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="f4402-117">Named pipes provide interprocess communication between a pipe server and one or more pipe clients.</span></span> <span data-ttu-id="f4402-118">명명된 파이프는 단방향 또는 양방향일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f4402-118">Named pipes can be one-way or duplex.</span></span> <span data-ttu-id="f4402-119">명명된 파이프는 메시지 기반 통신을 지원하며, 명명된 파이프를 통해 여러 클라이언트가 동일한 파이프 이름을 사용하여 서버 프로세스에 동시에 연결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f4402-119">They support message-based communication and allow multiple clients to connect simultaneously to the server process using the same pipe name.</span></span> <span data-ttu-id="f4402-120">명명된 파이프는 가장을 지원함으로써 연결 프로세스가 원격 서버에서 고유한 권한을 사용할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="f4402-120">Named pipes also support impersonation, which enables connecting processes to use their own permissions on remote servers.</span></span>  
  
     <span data-ttu-id="f4402-121">.NET에서는 <xref:System.IO.Pipes.NamedPipeServerStream> 및 <xref:System.IO.Pipes.NamedPipeClientStream> 클래스를 사용하여 명명된 파이프를 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="f4402-121">In .NET, you implement named pipes by using the <xref:System.IO.Pipes.NamedPipeServerStream> and <xref:System.IO.Pipes.NamedPipeClientStream> classes.</span></span>  
  
     <span data-ttu-id="f4402-122">[방법: 네트워크 프로세스 간 통신에 명명된 파이프 사용](how-to-use-named-pipes-for-network-interprocess-communication.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f4402-122">See [How to: Use Named Pipes for Network Interprocess Communication](how-to-use-named-pipes-for-network-interprocess-communication.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f4402-123">참조</span><span class="sxs-lookup"><span data-stu-id="f4402-123">See also</span></span>

- [<span data-ttu-id="f4402-124">파일 및 스트림 I/O</span><span class="sxs-lookup"><span data-stu-id="f4402-124">File and Stream I/O</span></span>](index.md)
- [<span data-ttu-id="f4402-125">방법: 로컬 프로세스 간 통신에 익명 파이프 사용</span><span class="sxs-lookup"><span data-stu-id="f4402-125">How to: Use Anonymous Pipes for Local Interprocess Communication</span></span>](how-to-use-anonymous-pipes-for-local-interprocess-communication.md)
- [<span data-ttu-id="f4402-126">방법: 네트워크 프로세스 간 통신에 명명된 파이프 사용</span><span class="sxs-lookup"><span data-stu-id="f4402-126">How to: Use Named Pipes for Network Interprocess Communication</span></span>](how-to-use-named-pipes-for-network-interprocess-communication.md)
