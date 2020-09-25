---
title: 트랜잭션 애플리케이션 작성
description: .NET에서 트랜잭션 응용 프로그램을 작성 합니다. 명시적 또는 암시적 프로그래밍 모델을 각각 트랜잭션 클래스 또는 TransactionScope 클래스와 함께 사용 합니다.
ms.date: 03/30/2017
ms.assetid: a4d891f2-6fc8-4395-93c6-6819492406e0
ms.openlocfilehash: b4cc33939128e61a69db319491a7d2d60ab9a819
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/24/2020
ms.locfileid: "91186668"
---
# <a name="writing-a-transactional-application"></a><span data-ttu-id="4bb74-104">트랜잭션 애플리케이션 작성</span><span class="sxs-lookup"><span data-stu-id="4bb74-104">Writing a Transactional Application</span></span>

<span data-ttu-id="4bb74-105">트랜잭션 애플리케이션 프로그래머는 <xref:System.Transactions> 네임스페이스가 제공하는 두 가지 프로그래밍 모델을 활용하여 트랜잭션을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4bb74-105">As a transactional application programmer, you can take advantage of the two programming models provided by the <xref:System.Transactions> namespace to create a transaction.</span></span> <span data-ttu-id="4bb74-106">클래스를 사용 하 여 명시적 프로그래밍 모델을 사용 <xref:System.Transactions.Transaction> 하거나, 클래스를 사용 하 여 인프라에서 트랜잭션이 자동으로 관리 되는 암시적 프로그래밍 모델을 활용할 수 있습니다 <xref:System.Transactions.TransactionScope> .</span><span class="sxs-lookup"><span data-stu-id="4bb74-106">You can utilize the explicit programming model by using the <xref:System.Transactions.Transaction> class, or the implicit programming model in which transactions are automatically managed by the infrastructure, by using the <xref:System.Transactions.TransactionScope> class.</span></span> <span data-ttu-id="4bb74-107">개발에는 암시적 트랜잭션 모델을 사용 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="4bb74-107">We recommend that you use the implicit transaction model for development.</span></span> <span data-ttu-id="4bb74-108">트랜잭션 범위를 [사용 하 여 암시적 트랜잭션 구현](implementing-an-implicit-transaction-using-transaction-scope.md) 항목에서 트랜잭션 범위를 사용 하는 방법에 대 한 자세한 내용을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4bb74-108">You can find more information on how to use a transaction scope in the [Implementing an Implicit Transaction using Transaction Scope](implementing-an-implicit-transaction-using-transaction-scope.md) topic.</span></span>  
  
 <span data-ttu-id="4bb74-109">두 모델은 모두 프로그램이 일관된 상태에 도달할 때 트랜잭션을 커밋하는 기능을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="4bb74-109">Both models support committing a transaction when the program reaches a consistent state.</span></span> <span data-ttu-id="4bb74-110">커밋이 성공하면 트랜잭션이 영구적으로 커밋됩니다.</span><span class="sxs-lookup"><span data-stu-id="4bb74-110">If the commit succeeds, the transaction is durably committed.</span></span> <span data-ttu-id="4bb74-111">커밋이 실패하면 트랜잭션이 중단됩니다.</span><span class="sxs-lookup"><span data-stu-id="4bb74-111">If the commit fails, the transaction aborts.</span></span> <span data-ttu-id="4bb74-112">애플리케이션에서 트랜잭션을 성공적으로 완료할 수 없는 경우 트랜잭션을 중단하고 그 결과를 취소합니다.</span><span class="sxs-lookup"><span data-stu-id="4bb74-112">If the application program cannot successfully complete the transaction, it attempts to abort and undo the transaction's effects.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="4bb74-113">섹션 내용</span><span class="sxs-lookup"><span data-stu-id="4bb74-113">In This Section</span></span>  
  
### <a name="creating-a-transaction"></a><span data-ttu-id="4bb74-114">트랜잭션 만들기</span><span class="sxs-lookup"><span data-stu-id="4bb74-114">Creating a Transaction</span></span>  

 <span data-ttu-id="4bb74-115"><xref:System.Transactions> 네임스페이스에서는 트랜잭션을 만드는 두 가지 모델을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="4bb74-115">The <xref:System.Transactions> namespace provides two models for creating a transaction.</span></span> <span data-ttu-id="4bb74-116">이 모델에 대해서는 다음 항목에서 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="4bb74-116">These models are covered in the following topics.</span></span>  
  
 [<span data-ttu-id="4bb74-117">트랜잭션 범위를 사용하여 암시적 트랜잭션 구현</span><span class="sxs-lookup"><span data-stu-id="4bb74-117">Implementing an Implicit Transaction using Transaction Scope</span></span>](implementing-an-implicit-transaction-using-transaction-scope.md)  
  
 <span data-ttu-id="4bb74-118"><xref:System.Transactions> 네임스페이스가 <xref:System.Transactions.TransactionScope> 클래스를 사용하여 암시적 트랜잭션을 만드는 기능을 지원하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="4bb74-118">Describes how the <xref:System.Transactions> namespace supports creating implicit transactions using the <xref:System.Transactions.TransactionScope> class.</span></span>  
  
 [<span data-ttu-id="4bb74-119">CommittableTransaction을 사용하여 명시적 트랜잭션 구현</span><span class="sxs-lookup"><span data-stu-id="4bb74-119">Implementing an Explicit Transaction using CommittableTransaction</span></span>](implementing-an-explicit-transaction-using-committabletransaction.md)  
  
 <span data-ttu-id="4bb74-120"><xref:System.Transactions> 네임스페이스가 <xref:System.Transactions.CommittableTransaction> 클래스를 사용하여 명시적 트랜잭션을 만드는 기능을 지원하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="4bb74-120">Describes how the <xref:System.Transactions> namespace supports creating explicit transactions using the <xref:System.Transactions.CommittableTransaction> class.</span></span>  
  
### <a name="escalating-transaction-management"></a><span data-ttu-id="4bb74-121">트랜잭션 관리 에스컬레이션</span><span class="sxs-lookup"><span data-stu-id="4bb74-121">Escalating Transaction Management</span></span>  

 <span data-ttu-id="4bb74-122">트랜잭션이 다른 애플리케이션 도메인의 리소스에 액세스해야 하는 경우 또는 다른 지속적인 리소스 관리자를 참여시키려는 경우 트랜잭션이 MSDTC에 의해 관리되도록 자동으로 에스컬레이션됩니다.</span><span class="sxs-lookup"><span data-stu-id="4bb74-122">When a transaction needs to access a resource in another application domain, or if you want to enlist in another durable resource manager, the transaction is automatically escalated to be managed by the MSDTC.</span></span> <span data-ttu-id="4bb74-123">트랜잭션 에스컬레이션은 [트랜잭션 관리 에스컬레이션](transaction-management-escalation.md) 항목에서 다룹니다.</span><span class="sxs-lookup"><span data-stu-id="4bb74-123">Transaction escalation is covered in the [Transaction Management Escalation](transaction-management-escalation.md) topic.</span></span>  
  
### <a name="concurrency"></a><span data-ttu-id="4bb74-124">동시성</span><span class="sxs-lookup"><span data-stu-id="4bb74-124">Concurrency</span></span>  

 <span data-ttu-id="4bb74-125">[DependentTransaction를 사용한 동시성 관리](managing-concurrency-with-dependenttransaction.md) 항목에서는 클래스를 사용 하 여 비동기 작업 간에 동시성을 구현 하는 방법을 보여 줍니다 <xref:System.Transactions.DependentTransaction> .</span><span class="sxs-lookup"><span data-stu-id="4bb74-125">The topic [Managing Concurrency with DependentTransaction](managing-concurrency-with-dependenttransaction.md) demonstrates how concurrency can be achieved between asynchronous tasks by using the <xref:System.Transactions.DependentTransaction> class.</span></span>  
  
### <a name="com-interop"></a><span data-ttu-id="4bb74-126">COM+ Interop</span><span class="sxs-lookup"><span data-stu-id="4bb74-126">COM+ Interop</span></span>  

 <span data-ttu-id="4bb74-127">[엔터프라이즈 서비스 및 COM + 트랜잭션과의 상호 운용성](interoperability-with-enterprise-services-and-com-transactions.md) 항목에서는 분산 트랜잭션이 com + 트랜잭션과 상호 작용 하도록 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="4bb74-127">The topic [Interoperability with Enterprise Services and COM+ Transactions](interoperability-with-enterprise-services-and-com-transactions.md) illustrates how you can make your distributed transactions interact with COM+ transactions.</span></span>  
  
### <a name="diagnostics"></a><span data-ttu-id="4bb74-128">진단</span><span class="sxs-lookup"><span data-stu-id="4bb74-128">Diagnostics</span></span>  

 <span data-ttu-id="4bb74-129">[진단 추적](diagnostic-traces.md) 에서는 인프라에서 생성 된 추적 코드를 사용 하 여 <xref:System.Transactions> 응용 프로그램의 오류를 해결 하는 방법을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="4bb74-129">[Diagnostic Traces](diagnostic-traces.md) describes how you can use the trace codes that are generated by the <xref:System.Transactions> infrastructure to troubleshoot errors in your applications.</span></span>  
  
### <a name="working-within-aspnet"></a><span data-ttu-id="4bb74-130">ASP.NET 작업</span><span class="sxs-lookup"><span data-stu-id="4bb74-130">Working within ASP.NET</span></span>  

 <span data-ttu-id="4bb74-131">[ASP.NET의 System.object 사용](using-system-transactions-in-aspnet.md) 항목에서는 <xref:System.Transactions> ASP.NET 응용 프로그램 내에서를 사용 하는 방법을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="4bb74-131">The [Using System.Transactions in ASP.NET](using-system-transactions-in-aspnet.md) topic describes how you can successfully use <xref:System.Transactions> inside an ASP.NET application.</span></span>
