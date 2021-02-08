---
description: '자세히 알아보기: OperationBehaviorAttribute'
title: OperationBehaviorAttribute
ms.date: 03/30/2017
ms.assetid: 8c9b0755-9e83-411f-bdcb-61a586022797
ms.openlocfilehash: c1f1b80134163ee65d5015e52017f5bb455aeac7
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99803063"
---
# <a name="operationbehaviorattribute"></a><span data-ttu-id="1e5c4-103">OperationBehaviorAttribute</span><span class="sxs-lookup"><span data-stu-id="1e5c4-103">OperationBehaviorAttribute</span></span>

<span data-ttu-id="1e5c4-104">OperationBehaviorAttribute</span><span class="sxs-lookup"><span data-stu-id="1e5c4-104">OperationBehaviorAttribute</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1e5c4-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="1e5c4-105">Syntax</span></span>  
  
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
  
## <a name="methods"></a><span data-ttu-id="1e5c4-106">메서드</span><span class="sxs-lookup"><span data-stu-id="1e5c4-106">Methods</span></span>  

 <span data-ttu-id="1e5c4-107">OperationBehaviorAttribute 클래스는 메서드를 정의하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="1e5c4-107">The OperationBehaviorAttribute class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="1e5c4-108">속성</span><span class="sxs-lookup"><span data-stu-id="1e5c4-108">Properties</span></span>  

 <span data-ttu-id="1e5c4-109">OperationBehaviorAttribute 클래스에는 다음과 같은 속성이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1e5c4-109">The OperationBehaviorAttribute class has the following properties:</span></span>  
  
### <a name="autodisposeparameters"></a><span data-ttu-id="1e5c4-110">AutoDisposeParameters</span><span class="sxs-lookup"><span data-stu-id="1e5c4-110">AutoDisposeParameters</span></span>  

 <span data-ttu-id="1e5c4-111">데이터 형식: boolean</span><span class="sxs-lookup"><span data-stu-id="1e5c4-111">Data type: boolean</span></span>  
  
 <span data-ttu-id="1e5c4-112">액세스 형식: 읽기 전용</span><span class="sxs-lookup"><span data-stu-id="1e5c4-112">Access type: Read-only</span></span>  
  
 <span data-ttu-id="1e5c4-113">매개 변수에 대한 자동 삭제 기능 상태입니다.</span><span class="sxs-lookup"><span data-stu-id="1e5c4-113">The state of the auto-dispose feature for parameters.</span></span>  
  
### <a name="impersonation"></a><span data-ttu-id="1e5c4-114">가장</span><span class="sxs-lookup"><span data-stu-id="1e5c4-114">Impersonation</span></span>  

 <span data-ttu-id="1e5c4-115">데이터 형식: 문자열</span><span class="sxs-lookup"><span data-stu-id="1e5c4-115">Data type: string</span></span>  
  
 <span data-ttu-id="1e5c4-116">액세스 형식: 읽기 전용</span><span class="sxs-lookup"><span data-stu-id="1e5c4-116">Access type: Read-only</span></span>  
  
 <span data-ttu-id="1e5c4-117">작업에서 지원하는 호출자의 가장 수준을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="1e5c4-117">Indicates the level of caller impersonation that the operation supports.</span></span>  
  
### <a name="releaseinstancemode"></a><span data-ttu-id="1e5c4-118">ReleaseInstanceMode</span><span class="sxs-lookup"><span data-stu-id="1e5c4-118">ReleaseInstanceMode</span></span>  

 <span data-ttu-id="1e5c4-119">데이터 형식: 문자열</span><span class="sxs-lookup"><span data-stu-id="1e5c4-119">Data type: string</span></span>  
  
 <span data-ttu-id="1e5c4-120">액세스 형식: 읽기 전용</span><span class="sxs-lookup"><span data-stu-id="1e5c4-120">Access type: Read-only</span></span>  
  
 <span data-ttu-id="1e5c4-121">작업 과정에서 개체를 재활용하기 위해 호출하는 시점을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="1e5c4-121">Indicates when in the course of an operation invocation to recycle the object.</span></span>  
  
### <a name="transactionautocomplete"></a><span data-ttu-id="1e5c4-122">TransactionAutoComplete</span><span class="sxs-lookup"><span data-stu-id="1e5c4-122">TransactionAutoComplete</span></span>  

 <span data-ttu-id="1e5c4-123">데이터 형식: boolean</span><span class="sxs-lookup"><span data-stu-id="1e5c4-123">Data type: boolean</span></span>  
  
 <span data-ttu-id="1e5c4-124">액세스 형식: 읽기 전용</span><span class="sxs-lookup"><span data-stu-id="1e5c4-124">Access type: Read-only</span></span>  
  
 <span data-ttu-id="1e5c4-125">처리되지 않은 예외가 발생하지 않을 때 현재 트랜잭션을 자동으로 커밋할지 여부를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="1e5c4-125">Indicates whether to automatically commit the current transaction if no unhandled exceptions occur.</span></span>  
  
### <a name="transactionscoperequired"></a><span data-ttu-id="1e5c4-126">TransactionScopeRequired</span><span class="sxs-lookup"><span data-stu-id="1e5c4-126">TransactionScopeRequired</span></span>  

 <span data-ttu-id="1e5c4-127">데이터 형식: boolean</span><span class="sxs-lookup"><span data-stu-id="1e5c4-127">Data type: boolean</span></span>  
  
 <span data-ttu-id="1e5c4-128">액세스 형식: 읽기 전용</span><span class="sxs-lookup"><span data-stu-id="1e5c4-128">Access type: Read-only</span></span>  
  
 <span data-ttu-id="1e5c4-129">작업에서 트랜잭션이 필요한지 여부를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="1e5c4-129">Indicates whether the operation requires a transaction.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1e5c4-130">요구 사항</span><span class="sxs-lookup"><span data-stu-id="1e5c4-130">Requirements</span></span>  
  
|<span data-ttu-id="1e5c4-131">MOF</span><span class="sxs-lookup"><span data-stu-id="1e5c4-131">MOF</span></span>|<span data-ttu-id="1e5c4-132">Servicemodel.mof에 선언되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1e5c4-132">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="1e5c4-133">네임스페이스</span><span class="sxs-lookup"><span data-stu-id="1e5c4-133">Namespace</span></span>|<span data-ttu-id="1e5c4-134">root\ServiceModel에 정의되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1e5c4-134">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="1e5c4-135">참고 항목</span><span class="sxs-lookup"><span data-stu-id="1e5c4-135">See also</span></span>

- <xref:System.ServiceModel.OperationBehaviorAttribute>
