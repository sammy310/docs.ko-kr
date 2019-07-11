---
title: ICorRuntimeHost::CloseEnum 메서드
ms.date: 03/30/2017
api_name:
- ICorRuntimeHost.CloseEnum
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICorRuntimeHost::CloseEnum
helpviewer_keywords:
- CloseEnum method, ICorRuntimeHost interface [.NET Framework hosting]
- ICorRuntimeHost::CloseEnum method [.NET Framework hosting]
ms.assetid: f7ce7e8c-0a3e-4587-a180-063e2b85940e
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: bfddd1d8f6fed105224cb2294d68f3f0bc016403
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/10/2019
ms.locfileid: "67762158"
---
# <a name="icorruntimehostcloseenum-method"></a><span data-ttu-id="d5bbe-102">ICorRuntimeHost::CloseEnum 메서드</span><span class="sxs-lookup"><span data-stu-id="d5bbe-102">ICorRuntimeHost::CloseEnum Method</span></span>
<span data-ttu-id="d5bbe-103">도메인 목록 맨 앞으로 다시 도메인 열거자를 다시 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="d5bbe-103">Resets a domain enumerator back to the beginning of the domain list.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d5bbe-104">구문</span><span class="sxs-lookup"><span data-stu-id="d5bbe-104">Syntax</span></span>  
  
```cpp  
HRESULT CloseEnum (  
    [in] HCORENUM hEnum  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d5bbe-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="d5bbe-105">Parameters</span></span>  
 `hEnum`  
 <span data-ttu-id="d5bbe-106">[in] 다시 설정 하는 열거자입니다.</span><span class="sxs-lookup"><span data-stu-id="d5bbe-106">[in] The enumerator to reset.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="d5bbe-107">반환 값</span><span class="sxs-lookup"><span data-stu-id="d5bbe-107">Return Value</span></span>  
  
|<span data-ttu-id="d5bbe-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="d5bbe-108">HRESULT</span></span>|<span data-ttu-id="d5bbe-109">Description</span><span class="sxs-lookup"><span data-stu-id="d5bbe-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="d5bbe-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="d5bbe-110">S_OK</span></span>|<span data-ttu-id="d5bbe-111">작업에 성공 합니다.</span><span class="sxs-lookup"><span data-stu-id="d5bbe-111">The operation was successful.</span></span>|  
|<span data-ttu-id="d5bbe-112">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="d5bbe-112">S_FALSE</span></span>|<span data-ttu-id="d5bbe-113">작업을 완료 하지 못했습니다.</span><span class="sxs-lookup"><span data-stu-id="d5bbe-113">The operation failed to complete.</span></span>|  
|<span data-ttu-id="d5bbe-114">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="d5bbe-114">E_FAIL</span></span>|<span data-ttu-id="d5bbe-115">알 수 없는 치명적인 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="d5bbe-115">An unknown, catastrophic failure occurred.</span></span> <span data-ttu-id="d5bbe-116">E_FAIL을 반환 하는 메서드는 CLR (공용 언어 런타임) 더 이상 사용할 수 진행에서 합니다.</span><span class="sxs-lookup"><span data-stu-id="d5bbe-116">If a method returns E_FAIL, the common language runtime (CLR) is no longer usable in the process.</span></span> <span data-ttu-id="d5bbe-117">호스팅 Api에 대 한 후속 호출 HOST_E_CLRNOTAVAILABLE를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="d5bbe-117">Subsequent calls to any hosting APIs return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="d5bbe-118">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="d5bbe-118">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="d5bbe-119">CLR이 로드 된 프로세스에 또는 CLR 상태인는 관리 코드를 실행 하거나 호출을 처리할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d5bbe-119">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="d5bbe-120">요구 사항</span><span class="sxs-lookup"><span data-stu-id="d5bbe-120">Requirements</span></span>  
 <span data-ttu-id="d5bbe-121">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="d5bbe-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d5bbe-122">**헤더:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="d5bbe-122">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="d5bbe-123">**라이브러리:** MSCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="d5bbe-123">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="d5bbe-124">**.NET framework 버전:** 1.0, 1.1</span><span class="sxs-lookup"><span data-stu-id="d5bbe-124">**.NET Framework Versions:** 1.0, 1.1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d5bbe-125">참고자료</span><span class="sxs-lookup"><span data-stu-id="d5bbe-125">See also</span></span>

- [<span data-ttu-id="d5bbe-126">CorBindToRuntimeEx 함수</span><span class="sxs-lookup"><span data-stu-id="d5bbe-126">CorBindToRuntimeEx Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md)
- [<span data-ttu-id="d5bbe-127">ICorRuntimeHost 인터페이스</span><span class="sxs-lookup"><span data-stu-id="d5bbe-127">ICorRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md)
