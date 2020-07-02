---
title: TCP 서비스 사용
description: TcpClient 클래스는 세부 정보를 추상화하여 TCP를 사용해 데이터를 요청하고 수신하는 소켓을 만듭니다. .NET Framework 스트림 처리를 사용하여 데이터를 읽고 씁니다.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- requesting data from Internet, TCP
- receiving data, TCP
- TcpClient class, about TcpClient class
- data requests, TCP
- application protocols, TCP
- network resources, TCP
- sending data, TCP
- TCP
- protocols, TCP
- Internet, TCP
ms.assetid: d2811830-3bcb-495c-b82d-cda9cf919aad
ms.openlocfilehash: 329701e8f11ca7f87c40ee8b2cc6a337435242b5
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/08/2020
ms.locfileid: "84501965"
---
# <a name="using-tcp-services"></a><span data-ttu-id="cb07a-104">TCP 서비스 사용</span><span class="sxs-lookup"><span data-stu-id="cb07a-104">Using TCP Services</span></span>

<span data-ttu-id="cb07a-105"><xref:System.Net.Sockets.TcpClient> 클래스는 TCP를 사용하여 인터넷 리소스의 데이터를 요청합니다.</span><span class="sxs-lookup"><span data-stu-id="cb07a-105">The <xref:System.Net.Sockets.TcpClient> class requests data from an Internet resource using TCP.</span></span> <span data-ttu-id="cb07a-106">**TcpClient**의 메서드 및 속성은 TCP를 사용하여 데이터를 요청 및 수신하는 <xref:System.Net.Sockets.Socket>을 만들기 위한 세부 정보를 추상화합니다.</span><span class="sxs-lookup"><span data-stu-id="cb07a-106">The methods and properties of **TcpClient** abstract the details for creating a <xref:System.Net.Sockets.Socket> for requesting and receiving data using TCP.</span></span> <span data-ttu-id="cb07a-107">원격 디바이스에 대한 연결은 스트림으로 표현되므로 .NET Framework 스트림 처리 기법을 사용하여 데이터를 읽고 쓸 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cb07a-107">Because the connection to the remote device is represented as a stream, data can be read and written with .NET Framework stream-handling techniques.</span></span>

<span data-ttu-id="cb07a-108">TCP 프로토콜은 원격 엔드포인트에 연결한 후 해당 연결을 사용하여 데이터 패킷을 주고받습니다.</span><span class="sxs-lookup"><span data-stu-id="cb07a-108">The TCP protocol establishes a connection with a remote endpoint and then uses that connection to send and receive data packets.</span></span> <span data-ttu-id="cb07a-109">TCP는 데이터 패킷이 엔드포인트로 전송되고 도착 시 올바른 순서로 어셈블되도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="cb07a-109">TCP is responsible for ensuring that data packets are sent to the endpoint and assembled in the correct order when they arrive.</span></span>

<span data-ttu-id="cb07a-110">TCP 연결을 설정하려면 필요한 서비스를 호스트하는 네트워크 디바이스의 주소를 알고 있어야 하고 서비스가 통신에 사용하는 TCP 포트를 알고 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="cb07a-110">To establish a TCP connection, you must know the address of the network device hosting the service you need and you must know the TCP port that the service uses to communicate.</span></span> <span data-ttu-id="cb07a-111">IANA(Internet Assigned Numbers Authority)는 공통 서비스의 포트 번호를 정의합니다([서비스 이름 및 전송 프로토콜 포트 번호 레지스트리](https://www.iana.org/assignments/service-names-port-numbers/service-names-port-numbers.xhtml) 참조).</span><span class="sxs-lookup"><span data-stu-id="cb07a-111">The Internet Assigned Numbers Authority (Iana) defines port numbers for common services (see [Service Name and Transport Protocol Port Number Registry](https://www.iana.org/assignments/service-names-port-numbers/service-names-port-numbers.xhtml)).</span></span> <span data-ttu-id="cb07a-112">Iana 목록에 없는 서비스에는 1,024~65,535 범위의 포트 번호를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cb07a-112">Services not on the Iana list can have port numbers in the range 1,024 to 65,535.</span></span>

<span data-ttu-id="cb07a-113">다음 예제에서는 TCP 포트 13에서 시간 서버에 연결하도록 **TcpClient**를 설정하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="cb07a-113">The following example demonstrates setting up a **TcpClient** to connect to a time server on TCP port 13:</span></span>

```vb
Imports System.Net.Sockets
Imports System.Text

Public Class TcpTimeClient
    Private const portNum As Integer = 13
    Private const hostName As String = "host.contoso.com"

    ' Entry point  that delegates to C-style main Private Function.
    Public Overloads Shared Sub Main()
        System.Environment.ExitCode = _
            Main(System.Environment.GetCommandLineArgs())
    End Sub

    Overloads Public Shared Function Main(args As String()) As Integer
        Try
            Dim client As New TcpClient(hostName, portNum)

            Dim ns As NetworkStream = client.GetStream()

            Dim bytes(1024) As Byte
            Dim bytesRead As Integer = ns.Read(bytes, 0, bytes.Length)

            Console.WriteLine(Encoding.ASCII.GetString(bytes, 0, bytesRead))

        Catch e As Exception
            Console.WriteLine(e.ToString())
        End Try

        client.Close()

        Return 0
    End Function
End Class
```

```csharp
using System;
using System.Net.Sockets;
using System.Text;

public class TcpTimeClient
{
    private const int portNum = 13;
    private const string hostName = "host.contoso.com";

    public static int Main(String[] args)
    {
        try
        {
            var client = new TcpClient(hostName, portNum);

            NetworkStream ns = client.GetStream();

            byte[] bytes = new byte[1024];
            int bytesRead = ns.Read(bytes, 0, bytes.Length);

            Console.WriteLine(Encoding.ASCII.GetString(bytes,0,bytesRead));

            client.Close();

        }
        catch (Exception e)
        {
            Console.WriteLine(e.ToString());
        }

        return 0;
    }
}
```

<span data-ttu-id="cb07a-114"><xref:System.Net.Sockets.TcpListener>는 TCP 포트에서 들어오는 요청을 모니터링한 다음 클라이언트에 대한 연결을 관리하는 **Socket** 또는 **TcpClient**를 만드는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="cb07a-114"><xref:System.Net.Sockets.TcpListener> is used to monitor a TCP port for incoming requests and then create either a **Socket** or a **TcpClient** that manages the connection to the client.</span></span> <span data-ttu-id="cb07a-115"><xref:System.Net.Sockets.TcpListener.Start%2A> 메서드는 수신 대기를 사용하도록 설정하고, <xref:System.Net.Sockets.TcpListener.Stop%2A> 메서드는 포트에서 수신 대기를 사용하지 않도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="cb07a-115">The <xref:System.Net.Sockets.TcpListener.Start%2A> method enables listening, and the <xref:System.Net.Sockets.TcpListener.Stop%2A> method disables listening on the port.</span></span> <span data-ttu-id="cb07a-116"><xref:System.Net.Sockets.TcpListener.AcceptTcpClient%2A> 메서드는 들어오는 연결 요청을 허용하고 **TcpClient**를 만들어 요청을 처리하며, <xref:System.Net.Sockets.TcpListener.AcceptSocket%2A> 메서드는 들어오는 연결 요청을 허용하고 **Socket**을 만들어 요청을 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="cb07a-116">The <xref:System.Net.Sockets.TcpListener.AcceptTcpClient%2A> method accepts incoming connection requests and creates a **TcpClient** to handle the request, and the <xref:System.Net.Sockets.TcpListener.AcceptSocket%2A> method accepts incoming connection requests and creates a **Socket** to handle the request.</span></span>

<span data-ttu-id="cb07a-117">다음 예제에서는 **TcpListener**를 사용해서 네트워크 시간 서버를 만들어 TCP 포트 13을 모니터링하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="cb07a-117">The following example demonstrates creating a network time server using a **TcpListener** to monitor TCP port 13.</span></span> <span data-ttu-id="cb07a-118">들어오는 연결 요청이 허용되면 시간 서버가 호스트 서버의 현재 날짜 및 시간을 사용하여 응답합니다.</span><span class="sxs-lookup"><span data-stu-id="cb07a-118">When an incoming connection request is accepted, the time server responds with the current date and time from the host server.</span></span>

```vb
Imports System.Net
Imports System.Net.Sockets
Imports System.Text

Public Class TcpTimeServer

    Private const portNum As Integer = 13

    ' Entry point that delegates to C-style main Private Function.
    Public Overloads Shared Sub Main()
        System.Environment.ExitCode = _
            Main(System.Environment.GetCommandLineArgs())
    End Sub

    Overloads Public Shared Function Main(args As String()) As Integer
        Dim done As Boolean = False

        Dim listener As New TcpListener(IPAddress.Any, portNum)

        listener.Start()

        While Not done
            Console.Write("Waiting for connection...")
            Dim client As TcpClient = listener.AcceptTcpClient()

            Console.WriteLine("Connection accepted.")
            Dim ns As NetworkStream = client.GetStream()

            Dim byteTime As Byte() = _
                Encoding.ASCII.GetBytes(DateTime.Now.ToString())

            Try
                ns.Write(byteTime, 0, byteTime.Length)
                ns.Close()
                client.Close()
            Catch e As Exception
                Console.WriteLine(e.ToString())
            End Try
        End While

        listener.Stop()

        Return 0
    End Function
End Class
```

```csharp
using System;
using System.Net;
using System.Net.Sockets;
using System.Text;

public class TcpTimeServer
{

    private const int portNum = 13;

    public static int Main(String[] args)
    {
        bool done = false;

        var listener = new TcpListener(IPAddress.Any, portNum);

        listener.Start();

        while (!done)
        {
            Console.Write("Waiting for connection...");
            TcpClient client = listener.AcceptTcpClient();

            Console.WriteLine("Connection accepted.");
            NetworkStream ns = client.GetStream();

            byte[] byteTime = Encoding.ASCII.GetBytes(DateTime.Now.ToString());

            try
            {
                ns.Write(byteTime, 0, byteTime.Length);
                ns.Close();
                client.Close();
            }
            catch (Exception e)
            {
                Console.WriteLine(e.ToString());
            }
        }

        listener.Stop();

        return 0;
    }

}
```
