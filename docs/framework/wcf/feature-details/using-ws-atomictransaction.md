---
title: WS-AtomicTransaction 사용
ms.date: 03/30/2017
helpviewer_keywords:
- WS-AT protocol [WCF]
ms.assetid: 04a4c200-0af0-4c5d-a3d9-87cb7339e054
ms.openlocfilehash: 71090efbb096bc3b7b3d6bcf40ff496b78ac6252
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/09/2020
ms.locfileid: "84600687"
---
# <a name="using-ws-atomictransaction"></a><span data-ttu-id="7242a-102">WS-AtomicTransaction 사용</span><span class="sxs-lookup"><span data-stu-id="7242a-102">Using WS-AtomicTransaction</span></span>
<span data-ttu-id="7242a-103">WS-AT(WS-AtomicTransaction)는 상호 운용 가능 트랜잭션 프로토콜입니다.</span><span class="sxs-lookup"><span data-stu-id="7242a-103">WS-AtomicTransaction (WS-AT) is an interoperable transaction protocol.</span></span> <span data-ttu-id="7242a-104">이 프로토콜을 사용하면 웹 서비스 메시지를 통해 분산 트랜잭션 흐름을 만들 수 있고 유형이 다른 트랜잭션 인프라 간에 상호 운용이 가능한 방식으로 이를 조정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7242a-104">It enables you to flow distributed transactions by using Web service messages, and coordinate in an interoperable manner between heterogeneous transaction infrastructures.</span></span> <span data-ttu-id="7242a-105">그리고 WS-AT에서는 2단계의 커밋 프로토콜을 사용하여 분산 애플리케이션, 트랜잭션 관리자 및 리소스 관리자 간의 원자 단위 결과를 도출합니다.</span><span class="sxs-lookup"><span data-stu-id="7242a-105">WS-AT uses the two-phase commit protocol to drive an atomic outcome between distributed applications, transaction managers, and resource managers.</span></span>  
  
 <span data-ttu-id="7242a-106">WCF (WS-AT 구현 Windows Communication Foundation)는 MSDTC (Microsoft DTC(Distributed Transaction Coordinator)) 트랜잭션 관리자에 기본 제공 되는 프로토콜 서비스를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="7242a-106">The WS-AT implementation Windows Communication Foundation (WCF) provides includes a protocol service built into the Microsoft Distributed Transaction Coordinator (MSDTC) transaction manager.</span></span> <span data-ttu-id="7242a-107">WCF 응용 프로그램은 WS-AT를 사용 하 여 타사 기술을 사용 하 여 작성 된 상호 운용 가능한 웹 서비스를 포함 하 여 다른 응용 프로그램으로 트랜잭션을 이동할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7242a-107">Using WS-AT, WCF applications can flow transactions to other applications, including interoperable Web services built using third-party technology.</span></span>  
  
 <span data-ttu-id="7242a-108">클라이언트 애플리케이션과 서버 애플리케이션 간에 트랜잭션이 진행될 때, 사용되는 트랜잭션 프로토콜은 클라이언트에서 선택한 엔드포인트에서 서버를 통해 노출된 바인딩에 의해 결정됩니다.</span><span class="sxs-lookup"><span data-stu-id="7242a-108">When flowing a transaction between a client application and a server application, the transaction protocol used is determined by the binding that the server exposes on the endpoint the client selected.</span></span> <span data-ttu-id="7242a-109">일부 WCF 시스템 제공 바인딩은 기본적으로 `OleTransactions` 프로토콜을 트랜잭션 전파 형식으로 지정 하는 것이 고, 다른 하나는 기본적으로 ws-at를 지정 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="7242a-109">Some WCF system-provided bindings default to specifying the `OleTransactions` protocol as the transaction propagation format, while others default to specifying WS-AT.</span></span> <span data-ttu-id="7242a-110">제공된 바인딩 내의 트랜잭션 프로토콜 선택은 프로그래밍 방식으로 수정할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7242a-110">You can also programmatically modify the choice of transaction protocol inside a given binding.</span></span>  
  
 <span data-ttu-id="7242a-111">프로토콜 선택에 따라 다음 사항이 결정됩니다.</span><span class="sxs-lookup"><span data-stu-id="7242a-111">The choice of protocol influences:</span></span>  
  
- <span data-ttu-id="7242a-112">클라이언트에서 서버로 트랜잭션을 하는 데 사용되는 메시지 헤더의 형식</span><span class="sxs-lookup"><span data-stu-id="7242a-112">The format of the message headers used to flow the transaction from client to server.</span></span>  
  
- <span data-ttu-id="7242a-113">트랜잭션 결과를 확인하기 위해 클라이언트의 트랜잭션 관리자와 서버의 트랜잭션 사이에서 2단계 커밋 프로토콜을 실행하는 데 사용되는 네트워크 프로토콜</span><span class="sxs-lookup"><span data-stu-id="7242a-113">The network protocol used to run the two-phase commit protocol between the client's transaction manager and the server's transaction, in order to resolve the outcome of the transaction.</span></span>  
  
 <span data-ttu-id="7242a-114">서버와 클라이언트가 WCF를 사용 하 여 작성 된 경우에는 WS-AT를 사용할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="7242a-114">If the server and client are written using WCF, you do not need to use WS-AT.</span></span> <span data-ttu-id="7242a-115">대신 활성화된 `NetTcpBinding` 특성을 가진 `TransactionFlow`의 기본 설정을 사용할 수 있습니다. 여기에는 `OleTransactions` 프로토콜이 대신 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="7242a-115">Instead, you can use the default settings of `NetTcpBinding` with the `TransactionFlow` attribute enabled, which will use the `OleTransactions` protocol instead.</span></span> <span data-ttu-id="7242a-116">자세한 내용은 [\<netTcpBinding>](../../configure-apps/file-schema/wcf/nettcpbinding.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="7242a-116">For more information, see [\<netTcpBinding>](../../configure-apps/file-schema/wcf/nettcpbinding.md).</span></span> <span data-ttu-id="7242a-117">타사 기술을 기반으로 구축한 웹 서비스로 트랜잭션을 이동하는 경우에는 WS-AT를 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7242a-117">Otherwise, if you are flowing transactions to Web services built on third-party technologies, you must use WS-AT.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7242a-118">참고 항목</span><span class="sxs-lookup"><span data-stu-id="7242a-118">See also</span></span>

- [<span data-ttu-id="7242a-119">WS-Atomic Transaction 지원 구성</span><span class="sxs-lookup"><span data-stu-id="7242a-119">Configuring WS-Atomic Transaction Support</span></span>](configuring-ws-atomic-transaction-support.md)
