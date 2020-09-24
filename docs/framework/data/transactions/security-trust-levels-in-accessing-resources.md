---
title: 리소스 액세스의 보안 신뢰 수준
description: .NET에서 리소스 액세스의 보안 신뢰 수준 이해 시스템 트랜잭션에는 세 가지 기본 신뢰 수준이 있습니다.
ms.date: 03/30/2017
ms.assetid: fb5be924-317d-4d69-b33a-3d18ecfb9d6e
ms.openlocfilehash: cbae3e87fc11a4230ba8f62cdbc273677e220bfb
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/24/2020
ms.locfileid: "91152912"
---
# <a name="security-trust-levels-in-accessing-resources"></a><span data-ttu-id="4cdb7-104">리소스 액세스의 보안 신뢰 수준</span><span class="sxs-lookup"><span data-stu-id="4cdb7-104">Security Trust Levels in Accessing Resources</span></span>

<span data-ttu-id="4cdb7-105">이 항목에서는 <xref:System.Transactions>에서 노출하는 리소스 형식에 따라 액세스가 제한되는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="4cdb7-105">This topic discusses how access is restricted on the types of resources that <xref:System.Transactions> exposes.</span></span>  
  
 <span data-ttu-id="4cdb7-106"><xref:System.Transactions>에 대한 세 가지 기본 신뢰 수준이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4cdb7-106">There are three main levels of trust for <xref:System.Transactions>.</span></span> <span data-ttu-id="4cdb7-107">신뢰 수준은 <xref:System.Transactions>에서 노출하는 리소스 형식과 이러한 리소스에 액세스하는 데 필요한 신뢰 수준을 기반으로 정의됩니다.</span><span class="sxs-lookup"><span data-stu-id="4cdb7-107">The trust levels are defined based on the types of resources that <xref:System.Transactions> exposes, and the level of trust that should be required to access those resources.</span></span> <span data-ttu-id="4cdb7-108"><xref:System.Transactions>에서 액세스를 제공하는 리소스는 시스템 메모리, 공유 프로세스 범위 리소스 및 시스템 범위 리소스입니다.</span><span class="sxs-lookup"><span data-stu-id="4cdb7-108">The resources that <xref:System.Transactions> provides access to are system memory, shared process wide resources, and system wide resources.</span></span> <span data-ttu-id="4cdb7-109">수준은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="4cdb7-109">The levels are:</span></span>  
  
- <span data-ttu-id="4cdb7-110">단일 응용 프로그램 도메인 내에서 트랜잭션을 사용 하는 응용 프로그램에 대 한 **AllowPartiallyTrustedCallers** (APTCA)</span><span class="sxs-lookup"><span data-stu-id="4cdb7-110">**AllowPartiallyTrustedCallers** (APTCA) for applications using transactions within a single application domain.</span></span>  
  
- <span data-ttu-id="4cdb7-111">분산 트랜잭션을 사용 하는 응용 프로그램에 대 한 **DistributedTransactionPermission** (DTP).</span><span class="sxs-lookup"><span data-stu-id="4cdb7-111">**DistributedTransactionPermission** (DTP) for applications using distributed transactions.</span></span>  
  
- <span data-ttu-id="4cdb7-112">지속적인 리소스, 구성 관리 애플리케이션 및 레거시 interop 애플리케이션에 대한 완전 신뢰</span><span class="sxs-lookup"><span data-stu-id="4cdb7-112">Full trust for durable resources, configuration management applications, and legacy interop applications.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="4cdb7-113">가장된 컨텍스트를 사용하여 인리스트먼트 인터페이스를 호출하면 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4cdb7-113">You should not call any of the enlistment interfaces with impersonated contexts.</span></span>  
  
## <a name="trust-levels"></a><span data-ttu-id="4cdb7-114">신뢰 수준</span><span class="sxs-lookup"><span data-stu-id="4cdb7-114">Trust Levels</span></span>  
  
### <a name="aptca-partial-trust"></a><span data-ttu-id="4cdb7-115">APTCA(부분 신뢰)</span><span class="sxs-lookup"><span data-stu-id="4cdb7-115">APTCA (Partial Trust)</span></span>  

 <span data-ttu-id="4cdb7-116"><xref:System.Transactions>어셈블리는 **AllowPartiallyTrustedCallers** 특성 (APTCA)으로 표시 되어 부분적으로 신뢰할 수 있는 코드에서 호출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4cdb7-116">The <xref:System.Transactions> assembly can be called by partially trusted code because it has been marked with the **AllowPartiallyTrustedCallers** attribute (APTCA).</span></span> <span data-ttu-id="4cdb7-117">이 특성은 기본적 <xref:System.Security.Permissions.SecurityAction.LinkDemand> 으로 각 형식에서 공개적으로 액세스할 수 있는 각 메서드에 자동으로 배치 되는 **FullTrust** 권한 집합에 대 한 암시적을 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="4cdb7-117">This attribute essentially removes the implicit <xref:System.Security.Permissions.SecurityAction.LinkDemand> for the **FullTrust** permission set that is otherwise automatically placed on each publicly accessible method in each type.</span></span> <span data-ttu-id="4cdb7-118">그러나 일부 형식 및 멤버에도 더 강력한 권한이 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="4cdb7-118">However, some types and members still require stronger permissions.</span></span>  
  
 <span data-ttu-id="4cdb7-119">APTCA 특성을 통해 애플리케이션은 단일 애플리케이션 도메인 내에서 부분 신뢰 트랜잭션을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4cdb7-119">The APTCA attribute enables applications to use transactions in partial trust within a single application domain.</span></span> <span data-ttu-id="4cdb7-120">이 경우 일시적인 인리스트먼트와 에스컬레이션되지 않는 트랜잭션을 오류 처리에 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4cdb7-120">This enables non-escalated transactions and volatile enlistments that can be used for error handling.</span></span> <span data-ttu-id="4cdb7-121">이러한 예로 트랜잭션된 해시 테이블과 이를 사용하는 애플리케이션이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4cdb7-121">One example of this is a transacted hash table and an application that uses it.</span></span> <span data-ttu-id="4cdb7-122">단일 트랜잭션으로 해시 테이블에 데이터를 추가하고 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4cdb7-122">Data can be added to and removed from the hash table under a single transaction.</span></span> <span data-ttu-id="4cdb7-123">나중에 트랜잭션을 롤백하는 경우 해당 트랜잭션에서 수행된 해시 테이블의 모든 변경 내용을 취소할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4cdb7-123">If the transaction is later rolled back, all of the changes made to the hash table under that transaction can be undone.</span></span>  
  
### <a name="distributedtransactionpermission-dtp"></a><span data-ttu-id="4cdb7-124">DistributedTransactionPermission(DTP)</span><span class="sxs-lookup"><span data-stu-id="4cdb7-124">DistributedTransactionPermission (DTP)</span></span>  

 <span data-ttu-id="4cdb7-125">MSDTC에서 관리하도록 <xref:System.Transactions> 트랜잭션을 에스컬레이션하는 경우 <xref:System.Transactions>에서 분산 트랜잭션을 만들려면 <xref:System.Transactions.DistributedTransactionPermission>(DTP)이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="4cdb7-125">When a <xref:System.Transactions> transaction is escalated to be managed by MSDTC, <xref:System.Transactions> demands the <xref:System.Transactions.DistributedTransactionPermission> (DTP) to create the distributed transaction.</span></span> <span data-ttu-id="4cdb7-126">따라서 serialization 또는 지속적인 추가 인리스트먼트를 통해 트랜잭션이 에스컬레이션되게 하는 코드에 DTP를 부여해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4cdb7-126">This means that the code that causes the transaction to be escalated (such as through serialization or additional durable enlistments) would need to be granted DTP.</span></span> <span data-ttu-id="4cdb7-127">원래 <xref:System.Transactions> 트랜잭션을 만든 코드에는 이 권한이 없어도 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4cdb7-127">The code that originally created the <xref:System.Transactions> transaction does not necessarily need to possess this permission.</span></span>  
  
### <a name="fulltrust-link-demands"></a><span data-ttu-id="4cdb7-128">FullTrust 링크 요청</span><span class="sxs-lookup"><span data-stu-id="4cdb7-128">FullTrust Link Demands</span></span>  

 <span data-ttu-id="4cdb7-129">이 사용 권한 수준은 지속적인 리소스에 쓰는 애플리케이션을 제한합니다.</span><span class="sxs-lookup"><span data-stu-id="4cdb7-129">This permission level is intended to restrict applications that are writing to durable resources.</span></span> <span data-ttu-id="4cdb7-130">실패 시 애플리케이션이 복구될 수 있어야 하며 트랜잭션 관리자가 영구 데이터를 업데이트할 수 있도록 트랜잭션의 최종 결과를 확인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4cdb7-130">Upon failure, the application needs to be able to recover with the transaction manager to determine the final outcome of the transaction, so that it can update permanent data.</span></span> <span data-ttu-id="4cdb7-131">이 애플리케이션 종류를 지속적인 소스 관리자라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="4cdb7-131">This type of application is known as a durable source manager.</span></span> <span data-ttu-id="4cdb7-132">이 애플리케이션 종류의 일반적인 예로 SQL이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4cdb7-132">A classic example of this type of application is SQL.</span></span>  
  
 <span data-ttu-id="4cdb7-133">복구를 사용하기 위해 이 애플리케이션 종류에는 시스템 리소스를 영구적으로 사용하는 기능이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4cdb7-133">To enable recovery, this type of application has the ability to permanently consume system resources.</span></span> <span data-ttu-id="4cdb7-134">이는 트랜잭션에 참여하는 모든 지속적인 리소스 관리자에서 결과를 받은 것을 확인할 수 있을 때까지 복구할 수 있는 트랜잭션 관리자가 커밋된 트랜잭션을 저장해야 하기 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="4cdb7-134">This is because the recoverable transaction manager must remember transactions that have committed until it can confirm that all durable resource managers that are participating in the transaction have received the outcome.</span></span> <span data-ttu-id="4cdb7-135">따라서 이 애플리케이션 종류에는 완전 신뢰가 필요하며 해당 신뢰 수준이 부여되지 않은 경우 실행하면 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4cdb7-135">Therefore, this type of application requires full trust and should not be run unless that level of trust has been granted.</span></span>  
  
 <span data-ttu-id="4cdb7-136">지속적인 인 리스트 먼 트 및 복구에 대 한 자세한 내용은 [트랜잭션에 리소스를 참가자로 참여](enlisting-resources-as-participants-in-a-transaction.md) 및 [복구 수행](performing-recovery.md) 항목을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="4cdb7-136">For more information on durable enlistments and recovery, see the [Enlisting Resources as Participants in a Transaction](enlisting-resources-as-participants-in-a-transaction.md) and [Performing Recovery](performing-recovery.md) topics.</span></span>  
  
 <span data-ttu-id="4cdb7-137">COM+와의 레거시 interop 작업을 수행하는 애플리케이션에도 완전 신뢰가 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4cdb7-137">Applications that perform legacy interop work with COM+ are also required to have full trust.</span></span>  
  
 <span data-ttu-id="4cdb7-138">다음은 **FullTrust** 선언적 보안 특성으로 데코레이팅 되어 부분적으로 신뢰할 수 있는 코드에서 호출할 수 없는 형식 및 멤버의 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="4cdb7-138">The following is a list of types and members that are not callable by partially trusted code because they are decorated with the **FullTrust** declarative security attribute:</span></span>  
  
 `PermissionSetAttribute(SecurityAction.LinkDemand, Name := "FullTrust")`  
  
- <xref:System.Transactions.Transaction.EnlistDurable%2A?displayProperty=nameWithType>  
  
- <xref:System.Transactions.Transaction.EnlistPromotableSinglePhase%2A>  
  
- <xref:System.Transactions.TransactionInterop>  
  
- <xref:System.Transactions.TransactionManager.DistributedTransactionStarted>  
  
- <xref:System.Transactions.HostCurrentTransactionCallback>  
  
- <xref:System.Transactions.TransactionManager.Reenlist%2A>  
  
- <xref:System.Transactions.TransactionManager.RecoveryComplete%2A>  
  
- <xref:System.Transactions.TransactionScope.%23ctor%28System.Transactions.TransactionScopeOption%2CSystem.Transactions.TransactionOptions%2CSystem.Transactions.EnterpriseServicesInteropOption%29>  
  
 <span data-ttu-id="4cdb7-139">위의 형식이 나 메서드를 사용 하려면 **FullTrust** 권한 집합을 소유 하는 데 직접 호출자만 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="4cdb7-139">Only the immediate caller is required to possess the **FullTrust** permission set to use the above types or methods.</span></span>
