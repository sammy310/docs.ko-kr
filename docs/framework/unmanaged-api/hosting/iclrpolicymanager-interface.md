---
description: '자세히 알아보기: ICLRPolicyManager 인터페이스'
title: ICLRPolicyManager 인터페이스
ms.date: 03/30/2017
api_name:
- ICLRPolicyManager
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRPolicyManager
helpviewer_keywords:
- ICLRPolicyManager interface [.NET Framework hosting]
ms.assetid: 5c834aa1-f2db-408a-b230-c7bec093d364
topic_type:
- apiref
ms.openlocfilehash: 8823f1db8b15b327306ff3c592b46c94537f4331
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99637380"
---
# <a name="iclrpolicymanager-interface"></a><span data-ttu-id="448db-103">ICLRPolicyManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="448db-103">ICLRPolicyManager Interface</span></span>

<span data-ttu-id="448db-104">호스트에서 오류 및 시간 제한이 발생 하는 경우 수행할 정책 작업을 지정할 수 있도록 하는 메서드를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="448db-104">Provides methods that allow the host to specify policy actions to be taken in the event of failures and timeouts.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="448db-105">메서드</span><span class="sxs-lookup"><span data-stu-id="448db-105">Methods</span></span>  
  
|<span data-ttu-id="448db-106">메서드</span><span class="sxs-lookup"><span data-stu-id="448db-106">Method</span></span>|<span data-ttu-id="448db-107">설명</span><span class="sxs-lookup"><span data-stu-id="448db-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="448db-108">SetActionOnFailure 메서드</span><span class="sxs-lookup"><span data-stu-id="448db-108">SetActionOnFailure Method</span></span>](iclrpolicymanager-setactiononfailure-method.md)|<span data-ttu-id="448db-109">지정 된 오류가 발생할 때 CLR (공용 언어 런타임)이 수행 해야 하는 정책 동작을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="448db-109">Specifies the policy action the common language runtime (CLR) should take when the specified failure occurs.</span></span>|  
|[<span data-ttu-id="448db-110">SetActionOnTimeout 메서드</span><span class="sxs-lookup"><span data-stu-id="448db-110">SetActionOnTimeout Method</span></span>](iclrpolicymanager-setactionontimeout-method.md)|<span data-ttu-id="448db-111">지정 된 작업의 제한 시간이 초과 될 때 CLR에서 수행 해야 하는 정책 동작을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="448db-111">Specifies the policy action the CLR should take when the specified operation times out.</span></span>|  
|[<span data-ttu-id="448db-112">SetDefaultAction 메서드</span><span class="sxs-lookup"><span data-stu-id="448db-112">SetDefaultAction Method</span></span>](iclrpolicymanager-setdefaultaction-method.md)|<span data-ttu-id="448db-113">지정 된 작업이 발생 했을 때 CLR에서 수행 해야 하는 정책 동작을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="448db-113">Specifies the policy action the CLR should take when the specified operation occurs.</span></span>|  
|[<span data-ttu-id="448db-114">SetTimeout 메서드</span><span class="sxs-lookup"><span data-stu-id="448db-114">SetTimeout Method</span></span>](iclrpolicymanager-settimeout-method.md)|<span data-ttu-id="448db-115">지정 된 작업에 대 한 시간 제한 값을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="448db-115">Sets a timeout value for the specified operation.</span></span>|  
|[<span data-ttu-id="448db-116">SetTimeoutAndAction 메서드</span><span class="sxs-lookup"><span data-stu-id="448db-116">SetTimeoutAndAction Method</span></span>](iclrpolicymanager-settimeoutandaction-method.md)|<span data-ttu-id="448db-117">지정 된 작업에 대 한 시간 제한 값을 설정 하 고 작업이 발생 했을 때 CLR에서 수행 해야 하는 정책 동작을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="448db-117">Sets a timeout value for the specified operation, and specifies the policy action the CLR should take when the operation occurs.</span></span>|  
|[<span data-ttu-id="448db-118">SetUnhandledExceptionPolicy 메서드</span><span class="sxs-lookup"><span data-stu-id="448db-118">SetUnhandledExceptionPolicy Method</span></span>](iclrpolicymanager-setunhandledexceptionpolicy-method.md)|<span data-ttu-id="448db-119">처리 되지 않은 예외가 발생할 때 CLR의 동작을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="448db-119">Specifies the behavior of the CLR when an unhandled exception occurs.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="448db-120">요구 사항</span><span class="sxs-lookup"><span data-stu-id="448db-120">Requirements</span></span>  

 <span data-ttu-id="448db-121">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="448db-121">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="448db-122">**헤더:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="448db-122">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="448db-123">**라이브러리:** MSCorEE.dll의 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="448db-123">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="448db-124">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="448db-124">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="448db-125">참고 항목</span><span class="sxs-lookup"><span data-stu-id="448db-125">See also</span></span>

- [<span data-ttu-id="448db-126">EClrFailure 열거형</span><span class="sxs-lookup"><span data-stu-id="448db-126">EClrFailure Enumeration</span></span>](eclrfailure-enumeration.md)
- [<span data-ttu-id="448db-127">EClrOperation 열거형</span><span class="sxs-lookup"><span data-stu-id="448db-127">EClrOperation Enumeration</span></span>](eclroperation-enumeration.md)
- [<span data-ttu-id="448db-128">EPolicyAction 열거형</span><span class="sxs-lookup"><span data-stu-id="448db-128">EPolicyAction Enumeration</span></span>](epolicyaction-enumeration.md)
- [<span data-ttu-id="448db-129">ICLRControl 인터페이스</span><span class="sxs-lookup"><span data-stu-id="448db-129">ICLRControl Interface</span></span>](iclrcontrol-interface.md)
