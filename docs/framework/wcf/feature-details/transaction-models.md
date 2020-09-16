---
title: 트랜잭션 모델
ms.date: 03/30/2017
ms.assetid: 48a8bc1b-128b-4cf1-a421-8cc73223c340
ms.openlocfilehash: 2d3d0631c47506e7bd99d90ed49a1fdc76cc7a59
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/15/2020
ms.locfileid: "90556826"
---
# <a name="transaction-models"></a><span data-ttu-id="96b3f-102">트랜잭션 모델</span><span class="sxs-lookup"><span data-stu-id="96b3f-102">Transaction Models</span></span>
<span data-ttu-id="96b3f-103">이 항목에서는 트랜잭션 프로그래밍 모델 및 Microsoft가 제공하는 인프라 구성 요소 간의 관계에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="96b3f-103">This topic describes the relationship between the transaction programming models and the infrastructure components Microsoft provides.</span></span>  
  
 <span data-ttu-id="96b3f-104">WCF (Windows Communication Foundation)에서 트랜잭션을 사용 하는 경우 서로 다른 트랜잭션 모델 중에서 선택 하는 것은 아니지만, 통합 및 일관 된 모델의 여러 계층에서 작동 한다는 것을 이해 하는 것이 중요 합니다.</span><span class="sxs-lookup"><span data-stu-id="96b3f-104">When using transactions in Windows Communication Foundation (WCF), it is important to understand that you are not selecting between different transactional models, but rather operating at different layers of an integrated and consistent model.</span></span>  
  
 <span data-ttu-id="96b3f-105">다음 단원에서는 세 가지 기본 트랜잭션 구성 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="96b3f-105">The following sections describe the three primary transaction components.</span></span>  
  
## <a name="windows-communication-foundation-transactions"></a><span data-ttu-id="96b3f-106">Windows Communication Foundation 트랜잭션</span><span class="sxs-lookup"><span data-stu-id="96b3f-106">Windows Communication Foundation Transactions</span></span>  
 <span data-ttu-id="96b3f-107">WCF의 트랜잭션 지원을 통해 트랜잭션 서비스를 작성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="96b3f-107">The transaction support in WCF allows you write transactional services.</span></span> <span data-ttu-id="96b3f-108">또한 ws-atomictransaction (ws-at) 프로토콜에 대 한 지원을 통해 응용 프로그램은 WCF 또는 타사 기술을 사용 하 여 빌드된 웹 서비스로 트랜잭션을 이동할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="96b3f-108">In addition, with its support for the WS-AtomicTransaction (WS-AT) protocol, applications can flow transactions to Web services built using either WCF or third-party technology.</span></span>  
  
 <span data-ttu-id="96b3f-109">WCF 서비스 또는 응용 프로그램에서 WCF 트랜잭션 기능은 인프라에서 트랜잭션을 만들고, 전달 하 고, 동기화 하는 방법과 시기를 선언적으로 지정 하는 특성 및 구성을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="96b3f-109">In a WCF service or application, WCF transaction features provide attributes and configuration for declaratively specifying how and when the infrastructure should create, flow, and synchronize transactions.</span></span>  
  
## <a name="systemtransactions-transactions"></a><span data-ttu-id="96b3f-110">System.Transactions 트랜잭션</span><span class="sxs-lookup"><span data-stu-id="96b3f-110">System.Transactions Transactions</span></span>  
 <span data-ttu-id="96b3f-111"><xref:System.Transactions> 네임스페이스는 <xref:System.Transactions.Transaction> 클래스 기반의 명시적 프로그래밍 모델과 <xref:System.Transactions.TransactionScope> 클래스를 사용하는 암시적 프로그래밍 모델을 모두 제공합니다. 후자의 경우 인프라에서 자동으로 트랜잭션을 관리합니다.</span><span class="sxs-lookup"><span data-stu-id="96b3f-111">The <xref:System.Transactions> namespace provides both an explicit programming model based on the <xref:System.Transactions.Transaction> class, as well as an implicit programming model using the <xref:System.Transactions.TransactionScope> class, in which the infrastructure automatically manages transactions.</span></span>  
  
 <span data-ttu-id="96b3f-112">이러한 두 모델을 사용 하 여 트랜잭션 응용 프로그램을 만드는 방법에 대 한 자세한 내용은 [트랜잭션 응용 프로그램 작성](https://go.microsoft.com/fwlink/?LinkId=94947)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="96b3f-112">For more information about how to create a transactional application using these two models, see [Writing a Transactional Application](https://go.microsoft.com/fwlink/?LinkId=94947).</span></span>  
  
 <span data-ttu-id="96b3f-113">WCF 서비스 또는 응용 프로그램에서는 <xref:System.Transactions> 클라이언트 응용 프로그램 내에서 트랜잭션을 만들고 필요한 경우 서비스 내에서 트랜잭션과 명시적으로 상호 작용 하기 위한 프로그래밍 모델을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="96b3f-113">In a WCF service or application, <xref:System.Transactions> provides the programming model for creating transactions within a client application and for explicitly interacting with a transaction, when required, within a service.</span></span>  
  
## <a name="msdtc-transactions"></a><span data-ttu-id="96b3f-114">MSDTC 트랜잭션</span><span class="sxs-lookup"><span data-stu-id="96b3f-114">MSDTC Transactions</span></span>  
 <span data-ttu-id="96b3f-115">MSDTC(Microsoft Distributed Transaction Coordinator)는 분산 트랜잭션을 지원하는 트랜잭션 관리자입니다.</span><span class="sxs-lookup"><span data-stu-id="96b3f-115">The Microsoft Distributed Transaction Coordinator (MSDTC) is a transaction manager that provides support for distributed transactions.</span></span>  
  
 <span data-ttu-id="96b3f-116">자세한 내용은 [DTC 프로그래머 참조](/previous-versions/windows/desktop/ms686108(v=vs.85))를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="96b3f-116">For more information, see the [DTC Programmer's Reference](/previous-versions/windows/desktop/ms686108(v=vs.85)).</span></span>  
  
 <span data-ttu-id="96b3f-117">WCF 서비스 또는 응용 프로그램에서 MSDTC는 클라이언트 또는 서비스 내에서 만든 트랜잭션의 조정을 위한 인프라를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="96b3f-117">In a WCF service or application, MSDTC provides the infrastructure for the coordination of transactions created within a client or service.</span></span>
