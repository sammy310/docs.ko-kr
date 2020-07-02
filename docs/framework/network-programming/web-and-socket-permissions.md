---
title: 웹 및 소켓 사용 권한
description: WebPermission 및 SocketPermission 클래스가 .NET Framework의 System.Net 네임스페이스 사용에 관한 인터넷 보안을 제공하는 방법에 대해 알아봅니다.
ms.date: 03/30/2017
helpviewer_keywords:
- Networking
- positions [.NET Framework], accepting
- sockets, permissions
- network, permissions
- Internet, permissions
- Network Resources
- SocketPermission class, about SocketPermission class
- positions [.NET Framework], connecting
- WebPermission class, about WebPermission class
- permissions [.NET Framework], sockets
- security [.NET Framework], Internet
- positions [.NET Framework], granting
ms.assetid: d51ad8cb-03ae-4a51-bfcd-cfcf6b98afa9
ms.openlocfilehash: 08ae360e8097f7281631da2a3f9846994dfbf5b6
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/08/2020
ms.locfileid: "84501900"
---
# <a name="web-and-socket-permissions"></a><span data-ttu-id="ff2b8-103">웹 및 소켓 사용 권한</span><span class="sxs-lookup"><span data-stu-id="ff2b8-103">Web and Socket Permissions</span></span>
<span data-ttu-id="ff2b8-104"><xref:System.Net> 네임스페이스를 사용하는 애플리케이션에 대한 인터넷 보안은 <xref:System.Net.WebPermission> 및 <xref:System.Net.SocketPermission> 클래스에서 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="ff2b8-104">Internet security for applications using the <xref:System.Net> namespace is provided by the <xref:System.Net.WebPermission> and <xref:System.Net.SocketPermission> classes.</span></span> <span data-ttu-id="ff2b8-105">**WebPermission** 클래스는 URI의 데이터를 요청하거나 인터넷에 URI를 제공하는 애플리케이션의 권한을 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="ff2b8-105">The **WebPermission** class controls an application's right to request data from a URI or to serve a URI to the Internet.</span></span> <span data-ttu-id="ff2b8-106">**SocketPermission** 클래스는 <xref:System.Net.Sockets.Socket>을 사용하여 로컬 포트에서 데이터를 허용하거나 호스트, 포트 번호 및 전송 프로토콜에 따라 다른 주소에서 전송 프로토콜을 사용하여 원격 디바이스에 연결하는 애플리케이션의 권한을 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="ff2b8-106">The **SocketPermission** class controls an application's right to use a <xref:System.Net.Sockets.Socket> to accept data on a local port or to contact remote devices using a transport protocol at another address, based on the host, port number, and transport protocol of the socket.</span></span>  
  
 <span data-ttu-id="ff2b8-107">사용하는 권한 클래스는 애플리케이션 유형에 따라 달라집니다.</span><span class="sxs-lookup"><span data-stu-id="ff2b8-107">Which permission class you use depends on your application type.</span></span> <span data-ttu-id="ff2b8-108"><xref:System.Net.WebRequest> 및 해당 하위 항목을 사용하는 애플리케이션은 **WebPermission** 클래스를 사용하여 권한을 관리해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ff2b8-108">Applications that use <xref:System.Net.WebRequest> and its descendants should use the **WebPermission** class to manage permissions.</span></span> <span data-ttu-id="ff2b8-109">소켓 수준 액세스를 사용하는 애플리케이션은 **SocketPermission** 클래스를 사용하여 권한을 관리해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ff2b8-109">Applications that use socket-level access should use the **SocketPermission** class to manage permissions.</span></span>  
  
 <span data-ttu-id="ff2b8-110">**WebPermission** 및 **SocketPermission**은 두 개의 권한인 허용과 연결을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="ff2b8-110">**WebPermission** and **SocketPermission** define two permissions: accept and connect.</span></span> <span data-ttu-id="ff2b8-111">허용은 다른 파티에서 들어오는 연결에 응답하는 권한을 애플리케이션에 부여합니다.</span><span class="sxs-lookup"><span data-stu-id="ff2b8-111">Accept grants the application the right to answer an incoming connection from another party.</span></span> <span data-ttu-id="ff2b8-112">연결은 다른 파티에 대한 연결을 시작하는 권한을 애플리케이션에 부여합니다.</span><span class="sxs-lookup"><span data-stu-id="ff2b8-112">Connect grants the application the right to initiate a connection to another party.</span></span>  
  
 <span data-ttu-id="ff2b8-113">**SocketPermission** 인스턴스의 경우 허용은 애플리케이션이 로컬 전송 주소에서 들어오는 연결을 허용할 수 있음을 의미하고, 연결은 애플리케이션이 일부 원격(또는 로컬) 전송 주소에 연결할 수 있음을 의미합니다.</span><span class="sxs-lookup"><span data-stu-id="ff2b8-113">For **SocketPermission** instances, accept means that an application can accept incoming connections on a local transport address; connect means that an application can connect to some remote (or local) transport address.</span></span>  
  
 <span data-ttu-id="ff2b8-114">**WebPermission** 인스턴스의 경우 허용은 애플리케이션이 **WebPermission**에 의해 제어되는 URI을 전 세계에 내보낼 수 있음을 의미합니다. 연결은 애플리케이션이 원격 또는 로컬 여부에 관계없이 해당 URI에 액세스할 수 있음을 의미합니다.</span><span class="sxs-lookup"><span data-stu-id="ff2b8-114">For **WebPermission** instances, accept means that an application can export the URI controlled by the **WebPermission** to the world; connect means that an application can access that URI (whether it is remote or local).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ff2b8-115">참조</span><span class="sxs-lookup"><span data-stu-id="ff2b8-115">See also</span></span>

- [<span data-ttu-id="ff2b8-116">보안</span><span class="sxs-lookup"><span data-stu-id="ff2b8-116">Security</span></span>](../../standard/security/index.md)
- [<span data-ttu-id="ff2b8-117">네트워크 프로그래밍의 보안</span><span class="sxs-lookup"><span data-stu-id="ff2b8-117">Security in Network Programming</span></span>](security-in-network-programming.md)
