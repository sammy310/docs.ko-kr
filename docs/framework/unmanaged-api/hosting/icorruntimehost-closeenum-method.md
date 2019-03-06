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
ms.openlocfilehash: 65da00d99fec5f2280bcd00ce97b8eddafede680
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/06/2019
ms.locfileid: "57485007"
---
# <a name="icorruntimehostcloseenum-method"></a><span data-ttu-id="7392f-102">ICorRuntimeHost::CloseEnum 메서드</span><span class="sxs-lookup"><span data-stu-id="7392f-102">ICorRuntimeHost::CloseEnum Method</span></span>
<span data-ttu-id="7392f-103">도메인 목록 맨 앞으로 다시 도메인 열거자를 다시 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="7392f-103">Resets a domain enumerator back to the beginning of the domain list.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7392f-104">구문</span><span class="sxs-lookup"><span data-stu-id="7392f-104">Syntax</span></span>  
  
```  
HRESULT CloseEnum (  
    [in] HCORENUM hEnum  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7392f-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="7392f-105">Parameters</span></span>  
 `hEnum`  
 <span data-ttu-id="7392f-106">[in] 다시 설정 하는 열거자입니다.</span><span class="sxs-lookup"><span data-stu-id="7392f-106">[in] The enumerator to reset.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="7392f-107">반환 값</span><span class="sxs-lookup"><span data-stu-id="7392f-107">Return Value</span></span>  
  
|<span data-ttu-id="7392f-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="7392f-108">HRESULT</span></span>|<span data-ttu-id="7392f-109">설명</span><span class="sxs-lookup"><span data-stu-id="7392f-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="7392f-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="7392f-110">S_OK</span></span>|<span data-ttu-id="7392f-111">작업에 성공 합니다.</span><span class="sxs-lookup"><span data-stu-id="7392f-111">The operation was successful.</span></span>|  
|<span data-ttu-id="7392f-112">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="7392f-112">S_FALSE</span></span>|<span data-ttu-id="7392f-113">작업을 완료 하지 못했습니다.</span><span class="sxs-lookup"><span data-stu-id="7392f-113">The operation failed to complete.</span></span>|  
|<span data-ttu-id="7392f-114">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="7392f-114">E_FAIL</span></span>|<span data-ttu-id="7392f-115">알 수 없는 치명적인 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="7392f-115">An unknown, catastrophic failure occurred.</span></span> <span data-ttu-id="7392f-116">E_FAIL을 반환 하는 메서드는 CLR (공용 언어 런타임) 더 이상 사용할 수 진행에서 합니다.</span><span class="sxs-lookup"><span data-stu-id="7392f-116">If a method returns E_FAIL, the common language runtime (CLR) is no longer usable in the process.</span></span> <span data-ttu-id="7392f-117">호스팅 Api에 대 한 후속 호출 HOST_E_CLRNOTAVAILABLE를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="7392f-117">Subsequent calls to any hosting APIs return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="7392f-118">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="7392f-118">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="7392f-119">CLR이 로드 된 프로세스에 또는 CLR 상태인는 관리 코드를 실행 하거나 호출을 처리할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="7392f-119">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="7392f-120">요구 사항</span><span class="sxs-lookup"><span data-stu-id="7392f-120">Requirements</span></span>  
 <span data-ttu-id="7392f-121">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="7392f-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7392f-122">**헤더:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="7392f-122">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="7392f-123">**라이브러리:** MSCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="7392f-123">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="7392f-124">**.NET framework 버전:** 1.0, 1.1</span><span class="sxs-lookup"><span data-stu-id="7392f-124">**.NET Framework Versions:** 1.0, 1.1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7392f-125">참고자료</span><span class="sxs-lookup"><span data-stu-id="7392f-125">See also</span></span>
- [<span data-ttu-id="7392f-126">CorBindToRuntimeEx 함수</span><span class="sxs-lookup"><span data-stu-id="7392f-126">CorBindToRuntimeEx Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md)
- [<span data-ttu-id="7392f-127">ICorRuntimeHost 인터페이스</span><span class="sxs-lookup"><span data-stu-id="7392f-127">ICorRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md)
