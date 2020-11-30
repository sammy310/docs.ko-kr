---
title: TCP-UDP
description: TcpClient, TcpListener 및 UdpClient 클래스 TCP 및 UDP 서비스를 처리하는 방법에 대해 알아봅니다. .NET Framework에서 데이터 전송의 세부 정보를 처리합니다.
ms.date: 03/30/2017
helpviewer_keywords:
- protocols, TCP/UDP
- network resources, TCP/UDP
- sending data, TCP/UDP
- TCP/UDP
- TcpClient class, about TcpClient class
- application protocols, TCP/UDP
- receiving data, TCP/UDP
- TcpListener class, about TcpListener class
- Socket class, about Socket class
- UDP
- data requests, TCP/UDP
- requesting data from Internet, TCP/UDP
- Internet, TCP/UDP
ms.assetid: df29b4b0-49e8-4923-82b9-13150dfc40f5
ms.openlocfilehash: b5b8b5cb3ce38fcff9115b2f9acf23fc5a970adf
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96239448"
---
# <a name="tcp-udp"></a><span data-ttu-id="d0302-103">TCP-UDP</span><span class="sxs-lookup"><span data-stu-id="d0302-103">TCP-UDP</span></span>

<span data-ttu-id="d0302-104">애플리케이션은 <xref:System.Net.Sockets.TcpClient>, <xref:System.Net.Sockets.TcpListener> 및 <xref:System.Net.Sockets.UdpClient> 클래스와 함께 TCP(Transmission Control Protocol) 및 UDP(User Datagram Protocol) 서비스를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d0302-104">Applications can use Transmission Control Protocol (TCP) and User Datagram Protocol (UDP) services with the <xref:System.Net.Sockets.TcpClient>, <xref:System.Net.Sockets.TcpListener>, and <xref:System.Net.Sockets.UdpClient> classes.</span></span> <span data-ttu-id="d0302-105">이러한 프로토콜 클래스는 <xref:System.Net.Sockets.Socket?displayProperty=nameWithType> 클래스를 기반으로 빌드되며 데이터 전송의 세부 사항을 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="d0302-105">These protocol classes are built on top of the <xref:System.Net.Sockets.Socket?displayProperty=nameWithType> class and take care of the details of transferring data.</span></span>  
  
 <span data-ttu-id="d0302-106">프로토콜 클래스는 **Socket** 클래스의 동기 메서드를 사용하여 상태 정보를 유지 관리하거나 프로토콜 관련 소켓 설정의 세부 정보를 알아야 하는 오버헤드 없이 네트워크 서비스에 대한 쉽고 간단한 액세스를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="d0302-106">The protocol classes use the synchronous methods of the **Socket** class to provide simple and straightforward access to network services without the overhead of maintaining state information or knowing the details of setting up protocol-specific sockets.</span></span> <span data-ttu-id="d0302-107">비동기 **Socket** 메서드를 사용하려면 <xref:System.Net.Sockets.NetworkStream> 클래스에서 제공하는 비동기 메서드를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d0302-107">To use asynchronous **Socket** methods, you can use the asynchronous methods supplied by the <xref:System.Net.Sockets.NetworkStream> class.</span></span> <span data-ttu-id="d0302-108">프로토콜 클래스에 의해 노출되지 않는 **Socket** 클래스의 기능에 액세스하려면 **Socket** 클래스를 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d0302-108">To access features of the **Socket** class not exposed by the protocol classes, you must use the **Socket** class.</span></span>  
  
 <span data-ttu-id="d0302-109">**TcpClient** 및 **TcpListener** 는 **NetworkStream** 클래스를 사용하여 네트워크를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="d0302-109">**TcpClient** and **TcpListener** represent the network using the **NetworkStream** class.</span></span> <span data-ttu-id="d0302-110"><xref:System.Net.Sockets.TcpClient.GetStream%2A> 메서드를 사용하여 네트워크 스트림을 반환한 다음 스트림의 <xref:System.Net.Sockets.NetworkStream.Read%2A> 및 <xref:System.Net.Sockets.NetworkStream.Write%2A> 메서드를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="d0302-110">You use the <xref:System.Net.Sockets.TcpClient.GetStream%2A> method to return the network stream, and then call the stream's <xref:System.Net.Sockets.NetworkStream.Read%2A> and <xref:System.Net.Sockets.NetworkStream.Write%2A> methods.</span></span> <span data-ttu-id="d0302-111">**NetworkStream** 은 프로토콜 클래스의 기본 소켓을 소유하지 않으므로 닫아도 소켓에 영향을 주지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d0302-111">The **NetworkStream** does not own the protocol classes' underlying socket, so closing it does not affect the socket.</span></span>  
  
 <span data-ttu-id="d0302-112">**UdpClient** 클래스는 바이트 배열을 사용하여 UDP 데이터그램을 보유합니다.</span><span class="sxs-lookup"><span data-stu-id="d0302-112">The **UdpClient** class uses an array of bytes to hold the UDP datagram.</span></span> <span data-ttu-id="d0302-113"><xref:System.Net.Sockets.UdpClient.Send%2A> 메서드를 사용하여 네트워크에 데이터를 보내고 <xref:System.Net.Sockets.UdpClient.Receive%2A> 메서드를 사용하여 들어오는 데이터그램을 받습니다.</span><span class="sxs-lookup"><span data-stu-id="d0302-113">You use the <xref:System.Net.Sockets.UdpClient.Send%2A> method to send the data to the network and the <xref:System.Net.Sockets.UdpClient.Receive%2A> method to receive an incoming datagram.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d0302-114">참조</span><span class="sxs-lookup"><span data-stu-id="d0302-114">See also</span></span>

- [<span data-ttu-id="d0302-115">TCP 서비스 사용</span><span class="sxs-lookup"><span data-stu-id="d0302-115">Using TCP Services</span></span>](using-tcp-services.md)
- [<span data-ttu-id="d0302-116">UDP 서비스 사용</span><span class="sxs-lookup"><span data-stu-id="d0302-116">Using UDP Services</span></span>](using-udp-services.md)
- [<span data-ttu-id="d0302-117">네트워크에서 스트림 사용</span><span class="sxs-lookup"><span data-stu-id="d0302-117">Using Streams on the Network</span></span>](using-streams-on-the-network.md)
- [<span data-ttu-id="d0302-118">비동기 서버 소켓 사용</span><span class="sxs-lookup"><span data-stu-id="d0302-118">Using an Asynchronous Server Socket</span></span>](using-an-asynchronous-server-socket.md)
- [<span data-ttu-id="d0302-119">비동기 클라이언트 소켓 사용</span><span class="sxs-lookup"><span data-stu-id="d0302-119">Using an Asynchronous Client Socket</span></span>](using-an-asynchronous-client-socket.md)
- [<span data-ttu-id="d0302-120">애플리케이션 프로토콜 사용</span><span class="sxs-lookup"><span data-stu-id="d0302-120">Using Application Protocols</span></span>](using-application-protocols.md)
