---
title: 소켓
description: Winsock32 API에서 제공하는 관리 코드 버전의 소켓 서비스인 .NET Framework Socket 클래스에 대해 알아봅니다.
ms.date: 03/30/2017
helpviewer_keywords:
- application protocols, sockets
- sending data, sockets
- data requests, sockets
- Windows Sockets
- sockets, about sockets
- Socket class, about Socket class
- sockets
- requesting data from Internet, sockets
- network, sockets
- receiving data, sockets
- protocols, sockets
- Internet, sockets
ms.assetid: 10d22735-bd37-42c1-a2be-c1932f979a7d
ms.openlocfilehash: e00d04164f7ce5251b7f30b5abd16c14643f6862
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96263128"
---
# <a name="sockets"></a><span data-ttu-id="9f9aa-103">소켓</span><span class="sxs-lookup"><span data-stu-id="9f9aa-103">Sockets</span></span>

<span data-ttu-id="9f9aa-104"><xref:System.Net.Sockets> 네임스페이스에는 Windows 소켓 인터페이스의 관리되는 구현이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="9f9aa-104">The <xref:System.Net.Sockets> namespace contains a managed implementation of the Windows Sockets interface.</span></span> <span data-ttu-id="9f9aa-105"><xref:System.Net> 네임스페이스에 있는 다른 모든 네트워크 액세스 클래스는 이 소켓 구현 위에 구축됩니다.</span><span class="sxs-lookup"><span data-stu-id="9f9aa-105">All other network-access classes in the <xref:System.Net> namespace are built on top of this implementation of sockets.</span></span>  
  
 <span data-ttu-id="9f9aa-106">.NET Framework <xref:System.Net.Sockets.Socket> 클래스는 Winsock32 API에서 제공하는 소켓 서비스의 관리 코드 버전입니다.</span><span class="sxs-lookup"><span data-stu-id="9f9aa-106">The .NET Framework <xref:System.Net.Sockets.Socket> class is a managed-code version of the socket services provided by the Winsock32 API.</span></span> <span data-ttu-id="9f9aa-107">대부분의 경우 **Socket** 클래스 메서드는 단순히 데이터를 해당하는 네이티브 Win32 항목으로 마샬링하고 필요한 모든 보안 검사를 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="9f9aa-107">In most cases, the **Socket** class methods simply marshal data into their native Win32 counterparts and handle any necessary security checks.</span></span>  
  
 <span data-ttu-id="9f9aa-108">**Socket** 클래스는 동기 및 비동기의 두 가지 기본 모드를 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="9f9aa-108">The **Socket** class supports two basic modes, synchronous and asynchronous.</span></span> <span data-ttu-id="9f9aa-109">동기 모드에서 네트워크 작업을 수행하는 함수 호출(예: <xref:System.Net.Sockets.Socket.Send%2A> 및 <xref:System.Net.Sockets.Socket.Receive%2A>)은 작업이 완료될 때까지 기다린 후 제어를 호출하는 프로그램에 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="9f9aa-109">In synchronous mode, calls to functions that perform network operations (such as <xref:System.Net.Sockets.Socket.Send%2A> and <xref:System.Net.Sockets.Socket.Receive%2A>) wait until the operation completes before returning control to the calling program.</span></span> <span data-ttu-id="9f9aa-110">비동기 모드에서는 이러한 호출이 즉시 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="9f9aa-110">In asynchronous mode, these calls return immediately.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9f9aa-111">참조</span><span class="sxs-lookup"><span data-stu-id="9f9aa-111">See also</span></span>

- [<span data-ttu-id="9f9aa-112">방법: 소켓 만들기</span><span class="sxs-lookup"><span data-stu-id="9f9aa-112">How to: Create a Socket</span></span>](how-to-create-a-socket.md)

- [<span data-ttu-id="9f9aa-113">애플리케이션 프로토콜 사용</span><span class="sxs-lookup"><span data-stu-id="9f9aa-113">Using Application Protocols</span></span>](using-application-protocols.md)
