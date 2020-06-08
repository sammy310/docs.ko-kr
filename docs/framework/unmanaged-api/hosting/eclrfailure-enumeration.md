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
ms.openlocfilehash: fa2b5052a1d569487f0c6c72699ff9ab571beefc
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/08/2020
ms.locfileid: "84504396"
---
# <a name="eclrfailure-enumeration"></a><span data-ttu-id="6bc0b-102">EClrFailure 열거형</span><span class="sxs-lookup"><span data-stu-id="6bc0b-102">EClrFailure Enumeration</span></span>
<span data-ttu-id="6bc0b-103">호스트에서 정책 작업을 설정할 수 있는 오류 집합을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="6bc0b-103">Describes the set of failures for which a host can set policy actions.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6bc0b-104">구문</span><span class="sxs-lookup"><span data-stu-id="6bc0b-104">Syntax</span></span>  
  
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
  
## <a name="members"></a><span data-ttu-id="6bc0b-105">멤버</span><span class="sxs-lookup"><span data-stu-id="6bc0b-105">Members</span></span>  
  
|<span data-ttu-id="6bc0b-106">멤버</span><span class="sxs-lookup"><span data-stu-id="6bc0b-106">Member</span></span>|<span data-ttu-id="6bc0b-107">설명</span><span class="sxs-lookup"><span data-stu-id="6bc0b-107">Description</span></span>|  
|------------|-----------------|  
|`FAIL_NonCriticalResource`|<span data-ttu-id="6bc0b-108">중요 하지 않은 코드 영역에서 리소스 (예: 스레드, 메모리 블록 또는 잠금)를 할당 하는 동안 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="6bc0b-108">A failure occurred during an attempt to allocate a resource (such as a thread, a block of memory, or a lock) in a non-critical region of code.</span></span>|  
|`FAIL_CriticalResource`|<span data-ttu-id="6bc0b-109">중요 한 코드 영역에서 리소스 (예: 스레드, 메모리 블록 또는 잠금)를 할당 하려고 시도 하는 동안 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="6bc0b-109">A failure occurred during an attempt to allocate a resource (such as a thread, a block of memory, or a lock) in a critical region of code.</span></span>|  
|`FAIL_FatalRuntime`|<span data-ttu-id="6bc0b-110">CLR (공용 언어 런타임)은 더 이상 프로세스에서 관리 코드를 실행할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="6bc0b-110">The common language runtime (CLR) is no longer able to run managed code in the process.</span></span> <span data-ttu-id="6bc0b-111">예측이 모든 호스팅 함수를 호출 하면 HRESULT 값 HOST_E_CLRNOTAVAILABLE 반환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6bc0b-111">Henceforth, calls to any hosting functions return an HRESULT value of HOST_E_CLRNOTAVAILABLE.</span></span>|  
|`FAIL_OrphanedLock`|<span data-ttu-id="6bc0b-112">스레드가 개체에서 반환 될 때 잠금을 해제 하지 못했습니다 <xref:System.AppDomain> .</span><span class="sxs-lookup"><span data-stu-id="6bc0b-112">A thread has failed to release a lock upon returning from an <xref:System.AppDomain> object.</span></span> <span data-ttu-id="6bc0b-113">호스트에서이 오류를 설정 하 여 스레드를 중단 시킬 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="6bc0b-113">The host cannot set this failure to cause a thread to abort.</span></span>|  
|`FAIL_StackOverflow`|<span data-ttu-id="6bc0b-114">스택 오버플로가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="6bc0b-114">A stack overflow has occurred.</span></span>|  
|`FAIL_AccessViolation`|<span data-ttu-id="6bc0b-115">보호 된 메모리를 읽거나 쓰려고 했습니다.</span><span class="sxs-lookup"><span data-stu-id="6bc0b-115">An attempt was made to read or write protected memory.</span></span> <span data-ttu-id="6bc0b-116">.NET Framework 4에서는 지원 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="6bc0b-116">Not supported in the .NET Framework 4.</span></span>|  
|`FAIL_CodeContract`|<span data-ttu-id="6bc0b-117">코드 계약 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="6bc0b-117">A code contract failure occurred.</span></span> <span data-ttu-id="6bc0b-118">[코드 계약](../../debug-trace-profile/code-contracts.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="6bc0b-118">See [Code Contracts](../../debug-trace-profile/code-contracts.md).</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6bc0b-119">설명</span><span class="sxs-lookup"><span data-stu-id="6bc0b-119">Remarks</span></span>  
 <span data-ttu-id="6bc0b-120">호스트에서 오류 조건에 대 한 정책 작업을 지정 하는 데 사용할 수 있는 [EPolicyAction](epolicyaction-enumeration.md) 값 목록은 [ICLRPolicyManager:: SetActionOnFailure](iclrpolicymanager-setactiononfailure-method.md) 메서드를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="6bc0b-120">See the [ICLRPolicyManager::SetActionOnFailure](iclrpolicymanager-setactiononfailure-method.md) method for a list of [EPolicyAction](epolicyaction-enumeration.md) values the host can use to specify the policy actions for failure conditions.</span></span> <span data-ttu-id="6bc0b-121">중요 하 고 중요 하지 않은 코드 영역에 대 한 자세한 내용은 [EClrOperation](eclroperation-enumeration.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="6bc0b-121">For more information about critical and non-critical regions of code, see [EClrOperation](eclroperation-enumeration.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6bc0b-122">요구 사항</span><span class="sxs-lookup"><span data-stu-id="6bc0b-122">Requirements</span></span>  
 <span data-ttu-id="6bc0b-123">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="6bc0b-123">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6bc0b-124">**헤더:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="6bc0b-124">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="6bc0b-125">**라이브러리:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="6bc0b-125">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="6bc0b-126">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6bc0b-126">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6bc0b-127">참고 항목</span><span class="sxs-lookup"><span data-stu-id="6bc0b-127">See also</span></span>

- [<span data-ttu-id="6bc0b-128">ICLRPolicyManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="6bc0b-128">ICLRPolicyManager Interface</span></span>](iclrpolicymanager-interface.md)
- [<span data-ttu-id="6bc0b-129">SetActionOnFailure 메서드</span><span class="sxs-lookup"><span data-stu-id="6bc0b-129">SetActionOnFailure Method</span></span>](iclrpolicymanager-setactiononfailure-method.md)
- [<span data-ttu-id="6bc0b-130">IHostPolicyManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="6bc0b-130">IHostPolicyManager Interface</span></span>](ihostpolicymanager-interface.md)
- [<span data-ttu-id="6bc0b-131">호스팅 열거형</span><span class="sxs-lookup"><span data-stu-id="6bc0b-131">Hosting Enumerations</span></span>](hosting-enumerations.md)
