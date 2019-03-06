---
title: ICorRuntimeHost::EnumDomains 메서드
ms.date: 03/30/2017
api_name:
- ICorRuntimeHost.EnumDomains
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICorRuntimeHost::EnumDomains
helpviewer_keywords:
- ICorRuntimeHost::EnumDomains method [.NET Framework hosting]
- EnumDomains method [.NET Framework hosting]
ms.assetid: 96b74995-0cde-4876-b6df-7fc164e6a5d1
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 27587c391b1d5cf5f5edb87cf5aa81d227869315
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/06/2019
ms.locfileid: "57464674"
---
# <a name="icorruntimehostenumdomains-method"></a><span data-ttu-id="e1bcb-102">ICorRuntimeHost::EnumDomains 메서드</span><span class="sxs-lookup"><span data-stu-id="e1bcb-102">ICorRuntimeHost::EnumDomains Method</span></span>
<span data-ttu-id="e1bcb-103">현재 프로세스에서 도메인에 대 한 열거자를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="e1bcb-103">Gets an enumerator for the domains in the current process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e1bcb-104">구문</span><span class="sxs-lookup"><span data-stu-id="e1bcb-104">Syntax</span></span>  
  
```  
HRESULT EnumDomains (  
    [out] HCORENUM *hEnum  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e1bcb-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="e1bcb-105">Parameters</span></span>  
 `hEnum`  
 <span data-ttu-id="e1bcb-106">[out] 도메인에 대 한 열거자입니다.</span><span class="sxs-lookup"><span data-stu-id="e1bcb-106">[out] An enumerator for the domains.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="e1bcb-107">반환 값</span><span class="sxs-lookup"><span data-stu-id="e1bcb-107">Return Value</span></span>  
  
|<span data-ttu-id="e1bcb-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="e1bcb-108">HRESULT</span></span>|<span data-ttu-id="e1bcb-109">설명</span><span class="sxs-lookup"><span data-stu-id="e1bcb-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="e1bcb-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="e1bcb-110">S_OK</span></span>|<span data-ttu-id="e1bcb-111">작업에 성공 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1bcb-111">The operation was successful.</span></span>|  
|<span data-ttu-id="e1bcb-112">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="e1bcb-112">S_FALSE</span></span>|<span data-ttu-id="e1bcb-113">작업을 완료 하지 못했습니다.</span><span class="sxs-lookup"><span data-stu-id="e1bcb-113">The operation failed to complete.</span></span>|  
|<span data-ttu-id="e1bcb-114">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="e1bcb-114">E_FAIL</span></span>|<span data-ttu-id="e1bcb-115">알 수 없는 치명적인 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="e1bcb-115">An unknown, catastrophic failure occurred.</span></span> <span data-ttu-id="e1bcb-116">E_FAIL을 반환 하는 메서드는 CLR (공용 언어 런타임) 더 이상 사용할 수 진행에서 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1bcb-116">If a method returns E_FAIL, the common language runtime (CLR) is no longer usable in the process.</span></span> <span data-ttu-id="e1bcb-117">호스팅 Api에 대 한 후속 호출 HOST_E_CLRNOTAVAILABLE를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="e1bcb-117">Subsequent calls to any hosting APIs return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="e1bcb-118">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="e1bcb-118">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="e1bcb-119">CLR이 로드 된 프로세스에 또는 CLR 상태인는 관리 코드를 실행 하거나 호출을 처리할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="e1bcb-119">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="e1bcb-120">요구 사항</span><span class="sxs-lookup"><span data-stu-id="e1bcb-120">Requirements</span></span>  
 <span data-ttu-id="e1bcb-121">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="e1bcb-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e1bcb-122">**헤더:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="e1bcb-122">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="e1bcb-123">**라이브러리:** MSCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="e1bcb-123">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="e1bcb-124">**.NET framework 버전:** 1.0, 1.1</span><span class="sxs-lookup"><span data-stu-id="e1bcb-124">**.NET Framework Version:** 1.0, 1.1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e1bcb-125">참고자료</span><span class="sxs-lookup"><span data-stu-id="e1bcb-125">See also</span></span>
- [<span data-ttu-id="e1bcb-126">ICorRuntimeHost 인터페이스</span><span class="sxs-lookup"><span data-stu-id="e1bcb-126">ICorRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md)
