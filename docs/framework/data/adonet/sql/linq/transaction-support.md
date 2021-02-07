---
description: '자세한 정보: 트랜잭션 지원'
title: 트랜잭션 지원
ms.date: 03/30/2017
ms.assetid: 8cceb26e-8d36-4365-8967-58e2e89e0187
ms.openlocfilehash: 97c076fadacde01c7d14e5d51b000839b3d014a2
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99681177"
---
# <a name="transaction-support"></a><span data-ttu-id="733d5-103">트랜잭션 지원</span><span class="sxs-lookup"><span data-stu-id="733d5-103">Transaction Support</span></span>

[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <span data-ttu-id="733d5-104">는 세 가지 고유한 트랜잭션 모델을 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="733d5-104">supports three distinct transaction models.</span></span> <span data-ttu-id="733d5-105">이러한 모델을 검사가 수행되는 순서대로 나열하면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="733d5-105">The following lists these models in the order of checks performed.</span></span>  
  
## <a name="explicit-local-transaction"></a><span data-ttu-id="733d5-106">명시적 로컬 트랜잭션</span><span class="sxs-lookup"><span data-stu-id="733d5-106">Explicit Local Transaction</span></span>  

 <span data-ttu-id="733d5-107"><xref:System.Data.Linq.DataContext.SubmitChanges%2A>가 호출될 때 <xref:System.Data.Linq.DataContext.Transaction%2A> 속성이 (`IDbTransaction`) 트랜잭션으로 설정된 경우 <xref:System.Data.Linq.DataContext.SubmitChanges%2A> 호출은 동일한 트랜잭션의 컨텍스트에서 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="733d5-107">When <xref:System.Data.Linq.DataContext.SubmitChanges%2A> is called, if the <xref:System.Data.Linq.DataContext.Transaction%2A> property is set to a (`IDbTransaction`) transaction, the <xref:System.Data.Linq.DataContext.SubmitChanges%2A> call is executed in the context of the same transaction.</span></span>  
  
 <span data-ttu-id="733d5-108">트랜잭션이 성공적으로 실행된 후 트랜잭션을 커밋하거나 롤백하는 작업은 직접 수행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="733d5-108">It is your responsibility to commit or rollback the transaction after successful execution of the transaction.</span></span> <span data-ttu-id="733d5-109">트랜잭션에 해당하는 연결은 <xref:System.Data.Linq.DataContext>를 생성하는 데 사용되는 연결과 일치해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="733d5-109">The connection corresponding to the transaction must match the connection used for constructing the <xref:System.Data.Linq.DataContext>.</span></span> <span data-ttu-id="733d5-110">다른 연결이 사용될 경우 예외가 throw됩니다.</span><span class="sxs-lookup"><span data-stu-id="733d5-110">An exception is thrown if a different connection is used.</span></span>  
  
## <a name="explicit-distributable-transaction"></a><span data-ttu-id="733d5-111">명시적 배포 가능 트랜잭션</span><span class="sxs-lookup"><span data-stu-id="733d5-111">Explicit Distributable Transaction</span></span>  

 <span data-ttu-id="733d5-112">활성 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]의 범위에서 <xref:System.Data.Linq.DataContext.SubmitChanges%2A> API(<xref:System.Transactions.Transaction>를 포함하지만 여기에 제한되지는 않음)를 호출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="733d5-112">You can call [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] APIs (including but not limited to <xref:System.Data.Linq.DataContext.SubmitChanges%2A>) in the scope of an active <xref:System.Transactions.Transaction>.</span></span> [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <span data-ttu-id="733d5-113">호출이 트랜잭션 범위에 있음을 감지 하 고 새 트랜잭션을 만들지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="733d5-113">detects that the call is in the scope of a transaction and does not create a new transaction.</span></span> [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <span data-ttu-id="733d5-114">또한이 경우 연결을 닫지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="733d5-114">also avoids closing the connection in this case.</span></span> <span data-ttu-id="733d5-115">이러한 트랜잭션의 컨텍스트에서 쿼리 및 <xref:System.Data.Linq.DataContext.SubmitChanges%2A> 실행을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="733d5-115">You can perform query and <xref:System.Data.Linq.DataContext.SubmitChanges%2A> executions in the context of such a transaction.</span></span>  
  
## <a name="implicit-transaction"></a><span data-ttu-id="733d5-116">암시적 트랜잭션</span><span class="sxs-lookup"><span data-stu-id="733d5-116">Implicit Transaction</span></span>  

 <span data-ttu-id="733d5-117"><xref:System.Data.Linq.DataContext.SubmitChanges%2A>를 호출할 경우 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]은 호출이 <xref:System.Transactions.Transaction>의 범위에 있는지 또는 `Transaction` 속성(`IDbTransaction`)이 사용자가 시작한 로컬 트랜잭션으로 설정되었는지 여부를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="733d5-117">When you call <xref:System.Data.Linq.DataContext.SubmitChanges%2A>, [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] checks to see whether the call is in the scope of a <xref:System.Transactions.Transaction> or if the `Transaction` property (`IDbTransaction`) is set to a user-started local transaction.</span></span> <span data-ttu-id="733d5-118">어떠한 트랜잭션도 찾지 못한 경우 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]은 로컬 트랜잭션(`IDbTransaction`)을 시작하고 이를 사용하여 생성된 SQL 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="733d5-118">If it finds neither transaction, [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] starts a local transaction (`IDbTransaction`) and uses it to execute the generated SQL commands.</span></span> <span data-ttu-id="733d5-119">모든 SQL 명령이 성공적으로 완료되면 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]은 로컬 트랜잭션을 커밋하고 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="733d5-119">When all SQL commands have been successfully completed, [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] commits the local transaction and returns.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="733d5-120">참고 항목</span><span class="sxs-lookup"><span data-stu-id="733d5-120">See also</span></span>

- [<span data-ttu-id="733d5-121">배경 정보</span><span class="sxs-lookup"><span data-stu-id="733d5-121">Background Information</span></span>](background-information.md)
- [<span data-ttu-id="733d5-122">방법: 트랜잭션을 사용하여 대괄호로 묶은 데이터 전송</span><span class="sxs-lookup"><span data-stu-id="733d5-122">How to: Bracket Data Submissions by Using Transactions</span></span>](how-to-bracket-data-submissions-by-using-transactions.md)
