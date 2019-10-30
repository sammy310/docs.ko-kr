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
ms.openlocfilehash: 7d935bff023d806cf8cfb6d87bde0f82666b51b5
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73131119"
---
# <a name="eclrfailure-enumeration"></a><span data-ttu-id="af3ad-102">EClrFailure 열거형</span><span class="sxs-lookup"><span data-stu-id="af3ad-102">EClrFailure Enumeration</span></span>
<span data-ttu-id="af3ad-103">호스트에서 정책 작업을 설정할 수 있는 오류 집합을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="af3ad-103">Describes the set of failures for which a host can set policy actions.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="af3ad-104">구문</span><span class="sxs-lookup"><span data-stu-id="af3ad-104">Syntax</span></span>  
  
```cpp  
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
  
## <a name="members"></a><span data-ttu-id="af3ad-105">멤버</span><span class="sxs-lookup"><span data-stu-id="af3ad-105">Members</span></span>  
  
|<span data-ttu-id="af3ad-106">멤버</span><span class="sxs-lookup"><span data-stu-id="af3ad-106">Member</span></span>|<span data-ttu-id="af3ad-107">설명</span><span class="sxs-lookup"><span data-stu-id="af3ad-107">Description</span></span>|  
|------------|-----------------|  
|`FAIL_NonCriticalResource`|<span data-ttu-id="af3ad-108">중요 하지 않은 코드 영역에서 리소스 (예: 스레드, 메모리 블록 또는 잠금)를 할당 하는 동안 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="af3ad-108">A failure occurred during an attempt to allocate a resource (such as a thread, a block of memory, or a lock) in a non-critical region of code.</span></span>|  
|`FAIL_CriticalResource`|<span data-ttu-id="af3ad-109">중요 한 코드 영역에서 리소스 (예: 스레드, 메모리 블록 또는 잠금)를 할당 하려고 시도 하는 동안 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="af3ad-109">A failure occurred during an attempt to allocate a resource (such as a thread, a block of memory, or a lock) in a critical region of code.</span></span>|  
|`FAIL_FatalRuntime`|<span data-ttu-id="af3ad-110">CLR (공용 언어 런타임)은 더 이상 프로세스에서 관리 코드를 실행할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="af3ad-110">The common language runtime (CLR) is no longer able to run managed code in the process.</span></span> <span data-ttu-id="af3ad-111">예측이 모든 호스팅 함수를 호출 하면 HRESULT 값 HOST_E_CLRNOTAVAILABLE이 반환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="af3ad-111">Henceforth, calls to any hosting functions return an HRESULT value of HOST_E_CLRNOTAVAILABLE.</span></span>|  
|`FAIL_OrphanedLock`|<span data-ttu-id="af3ad-112">스레드가 <xref:System.AppDomain> 개체에서 반환 될 때 잠금을 해제 하지 못했습니다.</span><span class="sxs-lookup"><span data-stu-id="af3ad-112">A thread has failed to release a lock upon returning from an <xref:System.AppDomain> object.</span></span> <span data-ttu-id="af3ad-113">호스트에서이 오류를 설정 하 여 스레드를 중단 시킬 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="af3ad-113">The host cannot set this failure to cause a thread to abort.</span></span>|  
|`FAIL_StackOverflow`|<span data-ttu-id="af3ad-114">스택 오버플로가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="af3ad-114">A stack overflow has occurred.</span></span>|  
|`FAIL_AccessViolation`|<span data-ttu-id="af3ad-115">보호 된 메모리를 읽거나 쓰려고 했습니다.</span><span class="sxs-lookup"><span data-stu-id="af3ad-115">An attempt was made to read or write protected memory.</span></span> <span data-ttu-id="af3ad-116">.NET Framework 4에서는 지원 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="af3ad-116">Not supported in the .NET Framework 4.</span></span>|  
|`FAIL_CodeContract`|<span data-ttu-id="af3ad-117">코드 계약 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="af3ad-117">A code contract failure occurred.</span></span> <span data-ttu-id="af3ad-118">[코드 계약](../../../../docs/framework/debug-trace-profile/code-contracts.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="af3ad-118">See [Code Contracts](../../../../docs/framework/debug-trace-profile/code-contracts.md).</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="af3ad-119">주의</span><span class="sxs-lookup"><span data-stu-id="af3ad-119">Remarks</span></span>  
 <span data-ttu-id="af3ad-120">호스트에서 오류 조건에 대 한 정책 작업을 지정 하는 데 사용할 수 있는 [EPolicyAction](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md) 값 목록은 [ICLRPolicyManager:: SetActionOnFailure](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-setactiononfailure-method.md) 메서드를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="af3ad-120">See the [ICLRPolicyManager::SetActionOnFailure](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-setactiononfailure-method.md) method for a list of [EPolicyAction](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md) values the host can use to specify the policy actions for failure conditions.</span></span> <span data-ttu-id="af3ad-121">중요 하 고 중요 하지 않은 코드 영역에 대 한 자세한 내용은 [EClrOperation](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="af3ad-121">For more information about critical and non-critical regions of code, see [EClrOperation](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="af3ad-122">요구 사항</span><span class="sxs-lookup"><span data-stu-id="af3ad-122">Requirements</span></span>  
 <span data-ttu-id="af3ad-123">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="af3ad-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="af3ad-124">**헤더:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="af3ad-124">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="af3ad-125">**라이브러리:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="af3ad-125">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="af3ad-126">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="af3ad-126">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="af3ad-127">참조</span><span class="sxs-lookup"><span data-stu-id="af3ad-127">See also</span></span>

- [<span data-ttu-id="af3ad-128">ICLRPolicyManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="af3ad-128">ICLRPolicyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-interface.md)
- [<span data-ttu-id="af3ad-129">SetActionOnFailure 메서드</span><span class="sxs-lookup"><span data-stu-id="af3ad-129">SetActionOnFailure Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-setactiononfailure-method.md)
- [<span data-ttu-id="af3ad-130">IHostPolicyManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="af3ad-130">IHostPolicyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostpolicymanager-interface.md)
- [<span data-ttu-id="af3ad-131">호스팅 열거형</span><span class="sxs-lookup"><span data-stu-id="af3ad-131">Hosting Enumerations</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
