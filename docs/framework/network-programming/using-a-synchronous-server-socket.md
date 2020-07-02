---
title: 동기 서버 소켓 사용
description: 이 예제에서는 연결 요청이 소켓에서 수신될 애플리케이션을 일시 중단하는 .NET Framework의 동기 서버 소켓을 보여 줍니다.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- application protocols, sockets
- synchronous server sockets
- sending data, sockets
- data requests, sockets
- requesting data from Internet, sockets
- server sockets
- receiving data, sockets
- Socket class, synchronous server sockets
- protocols, sockets
- sockets, synchronous server sockets
- Internet, sockets
ms.assetid: d1ce882e-653e-41f5-9289-844ec855b804
ms.openlocfilehash: 9e7d32595f554b32ecc72bbb1f1a469ad5935467
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/08/2020
ms.locfileid: "84502056"
---
# <a name="using-a-synchronous-server-socket"></a><span data-ttu-id="9ea58-103">동기 서버 소켓 사용</span><span class="sxs-lookup"><span data-stu-id="9ea58-103">Using a Synchronous Server Socket</span></span>
<span data-ttu-id="9ea58-104">동기 서버 소켓은 소켓에 연결 요청이 수신될 때까지 애플리케이션 실행을 일시 중단합니다.</span><span class="sxs-lookup"><span data-stu-id="9ea58-104">Synchronous server sockets suspend the execution of the application until a connection request is received on the socket.</span></span> <span data-ttu-id="9ea58-105">동기 서버 소켓은 네트워크를 작업에 많이 사용하는 애플리케이션에 적합하지 않지만 간단한 네트워크 애플리케이션에는 적합할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9ea58-105">Synchronous server sockets are not suitable for applications that make heavy use of the network in their operation, but they can be suitable for simple network applications.</span></span>  
  
 <span data-ttu-id="9ea58-106"><xref:System.Net.Sockets.Socket>이 <xref:System.Net.Sockets.Socket.Bind%2A> 및 <xref:System.Net.Sockets.Socket.Listen%2A> 메서드를 사용하여 엔드포인트에서 수신 대기하도록 설정되면 <xref:System.Net.Sockets.Socket.Accept%2A> 메서드를 사용하여 들어오는 연결 요청을 허용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9ea58-106">After a <xref:System.Net.Sockets.Socket> is set to listen on an endpoint using the <xref:System.Net.Sockets.Socket.Bind%2A> and <xref:System.Net.Sockets.Socket.Listen%2A> methods, it is ready to accept incoming connection requests using the <xref:System.Net.Sockets.Socket.Accept%2A> method.</span></span> <span data-ttu-id="9ea58-107">**Accept** 메서드를 호출하면 연결 요청이 수신될 때까지 애플리케이션이 일시 중단됩니다.</span><span class="sxs-lookup"><span data-stu-id="9ea58-107">The application is suspended until a connection request is received when the **Accept** method is called.</span></span>  
  
 <span data-ttu-id="9ea58-108">연결 요청이 수신되면 **Accept**는 연결 중인 클라이언트와 연결된 새 **Socket** 인스턴스를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="9ea58-108">When a connection request is received, **Accept** returns a new **Socket** instance that is associated with the connecting client.</span></span> <span data-ttu-id="9ea58-109">다음 예제에서는 클라이언트에서 데이터를 읽고 콘솔에 표시한 다음 데이터를 클라이언트에 다시 에코합니다.</span><span class="sxs-lookup"><span data-stu-id="9ea58-109">The following example reads data from the client, displays it on the console, and echoes the data back to the client.</span></span> <span data-ttu-id="9ea58-110">**Socket**은 메시징 프로토콜을 지정하지 않으므로 “\<EOF>” 문자열은 메시지 데이터의 끝을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="9ea58-110">The **Socket** does not specify any messaging protocol, so the string "\<EOF>" marks the end of the message data.</span></span> <span data-ttu-id="9ea58-111">`listener`라는 **Socket**이 초기화되었으며 엔드포인트에 바인딩되었다고 가정합니다.</span><span class="sxs-lookup"><span data-stu-id="9ea58-111">It assumes that a **Socket** named `listener` has been initialized and bound to an endpoint.</span></span>  
  
```vb  
Console.WriteLine("Waiting for a connection...")  
Dim handler As Socket = listener.Accept()  
Dim data As String = Nothing  
  
While True  
    bytes = New Byte(1024) {}  
    Dim bytesRec As Integer = handler.Receive(bytes)  
    data += Encoding.ASCII.GetString(bytes, 0, bytesRec)  
    If data.IndexOf("<EOF>") > - 1 Then  
        Exit While  
    End If  
End While  
  
Console.WriteLine("Text received : {0}", data)  
  
Dim msg As Byte() = Encoding.ASCII.GetBytes(data)  
handler.Send(msg)  
handler.Shutdown(SocketShutdown.Both)  
handler.Close()  
```  
  
```csharp  
Console.WriteLine("Waiting for a connection...");  
Socket handler = listener.Accept();  
String data = null;  
  
while (true) {  
    bytes = new byte[1024];  
    int bytesRec = handler.Receive(bytes);  
    data += Encoding.ASCII.GetString(bytes,0,bytesRec);  
    if (data.IndexOf("<EOF>") > -1) {  
        break;  
    }  
}  
  
Console.WriteLine( "Text received : {0}", data);  
  
byte[] msg = Encoding.ASCII.GetBytes(data);  
handler.Send(msg);  
handler.Shutdown(SocketShutdown.Both);  
handler.Close();  
```  
  
## <a name="see-also"></a><span data-ttu-id="9ea58-112">참조</span><span class="sxs-lookup"><span data-stu-id="9ea58-112">See also</span></span>

- [<span data-ttu-id="9ea58-113">비동기 서버 소켓 사용</span><span class="sxs-lookup"><span data-stu-id="9ea58-113">Using an Asynchronous Server Socket</span></span>](using-an-asynchronous-server-socket.md)
- [<span data-ttu-id="9ea58-114">동기 서버 소켓 예제</span><span class="sxs-lookup"><span data-stu-id="9ea58-114">Synchronous Server Socket Example</span></span>](synchronous-server-socket-example.md)
- [<span data-ttu-id="9ea58-115">소켓으로 수신</span><span class="sxs-lookup"><span data-stu-id="9ea58-115">Listening with Sockets</span></span>](listening-with-sockets.md)
