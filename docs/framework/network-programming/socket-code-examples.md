---
title: 소켓 코드 예제
description: 다음 예제를 통해 Socket 클래스를 사용하여 클라이언트에서 네트워크 서비스에 연결하는 방법 및 클라이언트의 연결을 수신 대기할 서버로 사용하는 방법을 알아봅니다.
ms.date: 03/30/2017
helpviewer_keywords:
- application protocols, sockets
- sending data, sockets
- Socket class, asynchronous server sockets
- data requests, sockets
- requesting data from Internet, sockets
- server sockets
- sockets, code examples
- receiving data, sockets
- protocols, sockets
- Internet, sockets
- client sockets
ms.assetid: f3fc7533-6956-42c6-bbc3-73e5a221027d
ms.openlocfilehash: 0a0911a779ed3d4938ad7ff57f048c176cf677fb
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/08/2020
ms.locfileid: "84502160"
---
# <a name="socket-code-examples"></a><span data-ttu-id="33488-103">소켓 코드 예제</span><span class="sxs-lookup"><span data-stu-id="33488-103">Socket Code Examples</span></span>
<span data-ttu-id="33488-104">다음 코드 예제에서는 <xref:System.Net.Sockets.Socket> 클래스를 원격 네트워크 서비스에 연결할 클라이언트 및 원격 클라이언트의 연결을 수신 대기할 서버로 사용하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="33488-104">The following code examples demonstrate how to use the <xref:System.Net.Sockets.Socket> class as a client to connect to remote network services and as a server to listen for connections from remote clients.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="33488-105">섹션 내용</span><span class="sxs-lookup"><span data-stu-id="33488-105">In This Section</span></span>  
 [<span data-ttu-id="33488-106">동기 클라이언트 소켓 예제</span><span class="sxs-lookup"><span data-stu-id="33488-106">Synchronous Client Socket Example</span></span>](synchronous-client-socket-example.md)  
 <span data-ttu-id="33488-107">서버에 연결하고 서버에서 반환된 데이터를 표시하는 동기 <xref:System.Net.Sockets.Socket> 클라이언트를 구현하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="33488-107">Shows how to implement a synchronous <xref:System.Net.Sockets.Socket> client that connects to a server and displays the data returned from the server.</span></span>  
  
 [<span data-ttu-id="33488-108">동기 서버 소켓 예제</span><span class="sxs-lookup"><span data-stu-id="33488-108">Synchronous Server Socket Example</span></span>](synchronous-server-socket-example.md)  
 <span data-ttu-id="33488-109">클라이언트의 연결을 수락하고 클라이언트에서 받은 데이터를 다시 에코하는 동기 <xref:System.Net.Sockets.Socket> 서버를 구현하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="33488-109">Shows how to implement a synchronous <xref:System.Net.Sockets.Socket> server that accepts connections from a client and echoes back the data received from the client.</span></span>  
  
 [<span data-ttu-id="33488-110">비동기 클라이언트 소켓 예제</span><span class="sxs-lookup"><span data-stu-id="33488-110">Asynchronous Client Socket Example</span></span>](asynchronous-client-socket-example.md)  
 <span data-ttu-id="33488-111">서버에 연결하고 서버에서 반환된 데이터를 표시하는 비동기 <xref:System.Net.Sockets.Socket> 클라이언트를 구현하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="33488-111">Shows how to implement an asynchronous <xref:System.Net.Sockets.Socket> client that connects to a server and displays the data returned from the server.</span></span>  
  
 [<span data-ttu-id="33488-112">비동기 서버 소켓 예제</span><span class="sxs-lookup"><span data-stu-id="33488-112">Asynchronous Server Socket Example</span></span>](asynchronous-server-socket-example.md)  
 <span data-ttu-id="33488-113">클라이언트의 연결을 수락하고 클라이언트에서 받은 데이터를 다시 에코하는 비동기 <xref:System.Net.Sockets.Socket> 서버를 구현하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="33488-113">Shows how to implement an asynchronous <xref:System.Net.Sockets.Socket> server that accepts connections from a client and echoes back the data received from the client.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="33488-114">관련 단원</span><span class="sxs-lookup"><span data-stu-id="33488-114">Related Sections</span></span>  
 [<span data-ttu-id="33488-115">소켓</span><span class="sxs-lookup"><span data-stu-id="33488-115">Sockets</span></span>](sockets.md)  
 <span data-ttu-id="33488-116"><xref:System.Net.Sockets> 네임스페이스 및 <xref:System.Net.Sockets.Socket> 클래스에 대한 기본 정보를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="33488-116">Provides basic information about the <xref:System.Net.Sockets> namespace and the <xref:System.Net.Sockets.Socket> class.</span></span>  
  
 [<span data-ttu-id="33488-117">네트워크 프로그래밍의 보안</span><span class="sxs-lookup"><span data-stu-id="33488-117">Security in Network Programming</span></span>](security-in-network-programming.md)  
 <span data-ttu-id="33488-118">표준 인터넷 보안 및 인증 기술을 사용하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="33488-118">Describes how to use standard Internet security and authentication techniques.</span></span>
