---
title: OperationBehaviorAttribute
ms.date: 03/30/2017
ms.assetid: 8c9b0755-9e83-411f-bdcb-61a586022797
ms.openlocfilehash: 79601308c66abe43dd5a7f72bd2a05b9d2346c2b
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/22/2019
ms.locfileid: "59975158"
---
# <a name="operationbehaviorattribute"></a><span data-ttu-id="3f10f-102">OperationBehaviorAttribute</span><span class="sxs-lookup"><span data-stu-id="3f10f-102">OperationBehaviorAttribute</span></span>
<span data-ttu-id="3f10f-103">OperationBehaviorAttribute</span><span class="sxs-lookup"><span data-stu-id="3f10f-103">OperationBehaviorAttribute</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3f10f-104">구문</span><span class="sxs-lookup"><span data-stu-id="3f10f-104">Syntax</span></span>  
  
```csharp
class OperationBehaviorAttribute : Behavior  
{  
  boolean AutoDisposeParameters;  
  string Impersonation;  
  string ReleaseInstanceMode;  
  boolean TransactionAutoComplete;  
  boolean TransactionScopeRequired;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="3f10f-105">메서드</span><span class="sxs-lookup"><span data-stu-id="3f10f-105">Methods</span></span>  
 <span data-ttu-id="3f10f-106">OperationBehaviorAttribute 클래스는 메서드를 정의하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="3f10f-106">The OperationBehaviorAttribute class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="3f10f-107">속성</span><span class="sxs-lookup"><span data-stu-id="3f10f-107">Properties</span></span>  
 <span data-ttu-id="3f10f-108">OperationBehaviorAttribute 클래스에는 다음과 같은 속성이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3f10f-108">The OperationBehaviorAttribute class has the following properties:</span></span>  
  
### <a name="autodisposeparameters"></a><span data-ttu-id="3f10f-109">AutoDisposeParameters</span><span class="sxs-lookup"><span data-stu-id="3f10f-109">AutoDisposeParameters</span></span>  
 <span data-ttu-id="3f10f-110">데이터 형식: boolean</span><span class="sxs-lookup"><span data-stu-id="3f10f-110">Data type: boolean</span></span>  
  
 <span data-ttu-id="3f10f-111">액세스 형식: 읽기 전용</span><span class="sxs-lookup"><span data-stu-id="3f10f-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="3f10f-112">매개 변수에 대한 자동 삭제 기능 상태입니다.</span><span class="sxs-lookup"><span data-stu-id="3f10f-112">The state of the auto-dispose feature for parameters.</span></span>  
  
### <a name="impersonation"></a><span data-ttu-id="3f10f-113">가장</span><span class="sxs-lookup"><span data-stu-id="3f10f-113">Impersonation</span></span>  
 <span data-ttu-id="3f10f-114">데이터 형식: string</span><span class="sxs-lookup"><span data-stu-id="3f10f-114">Data type: string</span></span>  
  
 <span data-ttu-id="3f10f-115">액세스 형식: 읽기 전용</span><span class="sxs-lookup"><span data-stu-id="3f10f-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="3f10f-116">작업에서 지원하는 호출자의 가장 수준을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="3f10f-116">Indicates the level of caller impersonation that the operation supports.</span></span>  
  
### <a name="releaseinstancemode"></a><span data-ttu-id="3f10f-117">ReleaseInstanceMode</span><span class="sxs-lookup"><span data-stu-id="3f10f-117">ReleaseInstanceMode</span></span>  
 <span data-ttu-id="3f10f-118">데이터 형식: string</span><span class="sxs-lookup"><span data-stu-id="3f10f-118">Data type: string</span></span>  
  
 <span data-ttu-id="3f10f-119">액세스 형식: 읽기 전용</span><span class="sxs-lookup"><span data-stu-id="3f10f-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="3f10f-120">작업 과정에서 개체를 재활용하기 위해 호출하는 시점을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="3f10f-120">Indicates when in the course of an operation invocation to recycle the object.</span></span>  
  
### <a name="transactionautocomplete"></a><span data-ttu-id="3f10f-121">TransactionAutoComplete</span><span class="sxs-lookup"><span data-stu-id="3f10f-121">TransactionAutoComplete</span></span>  
 <span data-ttu-id="3f10f-122">데이터 형식: boolean</span><span class="sxs-lookup"><span data-stu-id="3f10f-122">Data type: boolean</span></span>  
  
 <span data-ttu-id="3f10f-123">액세스 형식: 읽기 전용</span><span class="sxs-lookup"><span data-stu-id="3f10f-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="3f10f-124">처리되지 않은 예외가 발생하지 않을 때 현재 트랜잭션을 자동으로 커밋할지 여부를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="3f10f-124">Indicates whether to automatically commit the current transaction if no unhandled exceptions occur.</span></span>  
  
### <a name="transactionscoperequired"></a><span data-ttu-id="3f10f-125">TransactionScopeRequired</span><span class="sxs-lookup"><span data-stu-id="3f10f-125">TransactionScopeRequired</span></span>  
 <span data-ttu-id="3f10f-126">데이터 형식: boolean</span><span class="sxs-lookup"><span data-stu-id="3f10f-126">Data type: boolean</span></span>  
  
 <span data-ttu-id="3f10f-127">액세스 형식: 읽기 전용</span><span class="sxs-lookup"><span data-stu-id="3f10f-127">Access type: Read-only</span></span>  
  
 <span data-ttu-id="3f10f-128">작업에서 트랜잭션이 필요한지 여부를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="3f10f-128">Indicates whether the operation requires a transaction.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3f10f-129">요구 사항</span><span class="sxs-lookup"><span data-stu-id="3f10f-129">Requirements</span></span>  
  
|<span data-ttu-id="3f10f-130">MOF</span><span class="sxs-lookup"><span data-stu-id="3f10f-130">MOF</span></span>|<span data-ttu-id="3f10f-131">Servicemodel.mof에 선언되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3f10f-131">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="3f10f-132">네임스페이스</span><span class="sxs-lookup"><span data-stu-id="3f10f-132">Namespace</span></span>|<span data-ttu-id="3f10f-133">root\ServiceModel에 정의되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3f10f-133">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="3f10f-134">참고자료</span><span class="sxs-lookup"><span data-stu-id="3f10f-134">See also</span></span>

- <xref:System.ServiceModel.OperationBehaviorAttribute>
