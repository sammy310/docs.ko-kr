---
title: EClrFailure 열거형
ms.date: 03/30/2017
api_name:
- EClrFailure
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- EClrFailure
helpviewer_keywords:
- EClrFailure enumeration [.NET Framework hosting]
ms.assetid: 37b95cce-9bfb-4ecf-a00b-33dcba782c67
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: cb19f950122f7b0db66830e9ed5dff44ccd370c2
ms.sourcegitcommit: 155012a8a826ee8ab6aa49b1b3a3b532e7b7d9bd
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/04/2019
ms.locfileid: "66490429"
---
# <a name="eclrfailure-enumeration"></a><span data-ttu-id="2c87c-102">EClrFailure 열거형</span><span class="sxs-lookup"><span data-stu-id="2c87c-102">EClrFailure Enumeration</span></span>
<span data-ttu-id="2c87c-103">호스트 정책 작업 설정할 수 있는 오류를 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="2c87c-103">Describes the set of failures for which a host can set policy actions.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2c87c-104">구문</span><span class="sxs-lookup"><span data-stu-id="2c87c-104">Syntax</span></span>  
  
```  
typedef enum {  
    FAIL_NonCriticalResource,  
    FAIL_CriticalResource,  
    FAIL_FatalRuntime,  
    FAIL_OrphanedLock  
    FAIL_StackOverflow  
    FAIL_AccessViolation  
    FAIL_CodeContract  
} EClrFailure;  
```  
  
## <a name="members"></a><span data-ttu-id="2c87c-105">멤버</span><span class="sxs-lookup"><span data-stu-id="2c87c-105">Members</span></span>  
  
|<span data-ttu-id="2c87c-106">멤버</span><span class="sxs-lookup"><span data-stu-id="2c87c-106">Member</span></span>|<span data-ttu-id="2c87c-107">설명</span><span class="sxs-lookup"><span data-stu-id="2c87c-107">Description</span></span>|  
|------------|-----------------|  
|`FAIL_NonCriticalResource`|<span data-ttu-id="2c87c-108">중요 하지 않은 코드 영역 (예: 스레드, 메모리, 블록 또는 잠금을) 리소스를 할당 하는 동안 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="2c87c-108">A failure occurred during an attempt to allocate a resource (such as a thread, a block of memory, or a lock) in a non-critical region of code.</span></span>|  
|`FAIL_CriticalResource`|<span data-ttu-id="2c87c-109">코드의 중요 영역 (예: 스레드, 메모리, 블록 또는 잠금을) 리소스를 할당 하는 동안 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="2c87c-109">A failure occurred during an attempt to allocate a resource (such as a thread, a block of memory, or a lock) in a critical region of code.</span></span>|  
|`FAIL_FatalRuntime`|<span data-ttu-id="2c87c-110">CLR (공용 언어 런타임)이 더 이상 프로세스에서 관리 되는 코드를 실행 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="2c87c-110">The common language runtime (CLR) is no longer able to run managed code in the process.</span></span> <span data-ttu-id="2c87c-111">예측이 모든 호스팅 함수를 호출 하는 HOST_E_CLRNOTAVAILABLE의 HRESULT 값을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="2c87c-111">Henceforth, calls to any hosting functions return an HRESULT value of HOST_E_CLRNOTAVAILABLE.</span></span>|  
|`FAIL_OrphanedLock`|<span data-ttu-id="2c87c-112">반환 시 잠금 해제 하지 못했습니다 스레드는 <xref:System.AppDomain> 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="2c87c-112">A thread has failed to release a lock upon returning from an <xref:System.AppDomain> object.</span></span> <span data-ttu-id="2c87c-113">호스트에는이 오류는 스레드가 중단 되도록를 설정할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="2c87c-113">The host cannot set this failure to cause a thread to abort.</span></span>|  
|`FAIL_StackOverflow`|<span data-ttu-id="2c87c-114">스택 오버플로가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="2c87c-114">A stack overflow has occurred.</span></span>|  
|`FAIL_AccessViolation`|<span data-ttu-id="2c87c-115">보호 된 메모리를 쓰거나 읽을 하려고 했습니다.</span><span class="sxs-lookup"><span data-stu-id="2c87c-115">An attempt was made to read or write protected memory.</span></span> <span data-ttu-id="2c87c-116">.NET Framework 4에서 지원 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="2c87c-116">Not supported in the .NET Framework 4.</span></span>|  
|`FAIL_CodeContract`|<span data-ttu-id="2c87c-117">코드 계약 실패가 했습니다.</span><span class="sxs-lookup"><span data-stu-id="2c87c-117">A code contract failure occurred.</span></span> <span data-ttu-id="2c87c-118">참조 [계약 코드](../../../../docs/framework/debug-trace-profile/code-contracts.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="2c87c-118">See [Code Contracts](../../../../docs/framework/debug-trace-profile/code-contracts.md).</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2c87c-119">설명</span><span class="sxs-lookup"><span data-stu-id="2c87c-119">Remarks</span></span>  
 <span data-ttu-id="2c87c-120">참조를 [iclrpolicymanager:: Setactiononfailure](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-setactiononfailure-method.md) 메서드 목록은 [EPolicyAction](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md) 값 호스트 사용 오류 조건에 대 한 정책 작업을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2c87c-120">See the [ICLRPolicyManager::SetActionOnFailure](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-setactiononfailure-method.md) method for a list of [EPolicyAction](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md) values the host can use to specify the policy actions for failure conditions.</span></span> <span data-ttu-id="2c87c-121">코드의 중요 한 및 중요 하지 않은 지역에 대 한 자세한 내용은 참조 [EClrOperation](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="2c87c-121">For more information about critical and non-critical regions of code, see [EClrOperation](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2c87c-122">요구 사항</span><span class="sxs-lookup"><span data-stu-id="2c87c-122">Requirements</span></span>  
 <span data-ttu-id="2c87c-123">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="2c87c-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2c87c-124">**헤더:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="2c87c-124">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="2c87c-125">**라이브러리:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="2c87c-125">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="2c87c-126">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2c87c-126">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2c87c-127">참고자료</span><span class="sxs-lookup"><span data-stu-id="2c87c-127">See also</span></span>

- [<span data-ttu-id="2c87c-128">ICLRPolicyManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="2c87c-128">ICLRPolicyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-interface.md)
- [<span data-ttu-id="2c87c-129">SetActionOnFailure 메서드</span><span class="sxs-lookup"><span data-stu-id="2c87c-129">SetActionOnFailure Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-setactiononfailure-method.md)
- [<span data-ttu-id="2c87c-130">IHostPolicyManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="2c87c-130">IHostPolicyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostpolicymanager-interface.md)
- [<span data-ttu-id="2c87c-131">호스팅 열거형</span><span class="sxs-lookup"><span data-stu-id="2c87c-131">Hosting Enumerations</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
