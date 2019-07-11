---
title: ICorRuntimeHost::NextDomain 메서드
ms.date: 03/30/2017
api_name:
- ICorRuntimeHost.NextDomain
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICorRuntimeHost::NextDomain
helpviewer_keywords:
- ICorRuntimeHost::NextDomain method [.NET Framework hosting]
- NextDomain method [.NET Framework hosting]
ms.assetid: fe07a05b-f6d6-44b5-ab01-b9a6eb15c350
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: bf19d322d8e4d0d05993d22b2aa7e46bda7b5a1d
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/10/2019
ms.locfileid: "67780070"
---
# <a name="icorruntimehostnextdomain-method"></a><span data-ttu-id="02c8b-102">ICorRuntimeHost::NextDomain 메서드</span><span class="sxs-lookup"><span data-stu-id="02c8b-102">ICorRuntimeHost::NextDomain Method</span></span>
<span data-ttu-id="02c8b-103">열거형에서 다음 도메인에 대 한 인터페이스 포인터를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="02c8b-103">Gets an interface pointer to the next domain in the enumeration.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="02c8b-104">구문</span><span class="sxs-lookup"><span data-stu-id="02c8b-104">Syntax</span></span>  
  
```cpp  
HRESULT NextDomain (  
    [in] HCORENUM hEnum,  
    [out] void** pAppDomain  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="02c8b-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="02c8b-105">Parameters</span></span>  
 `hEnum`  
 <span data-ttu-id="02c8b-106">[in] 호출을 통해 얻은 열거자 [EnumDomains](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-enumdomains-method.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="02c8b-106">[in] The enumerator that was obtained through a call to [EnumDomains](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-enumdomains-method.md).</span></span>  
  
 `pAppDomain`  
 <span data-ttu-id="02c8b-107">[out] 에 대 한 인터페이스 포인터를 <xref:System._AppDomain?displayProperty=nameWithType> 자세한 도메인이 없으면 null을 열거형에서 다음 도메인을 나타내는 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="02c8b-107">[out] An interface pointer to the <xref:System._AppDomain?displayProperty=nameWithType> type that represents the next domain in the enumeration, or null, if no more domains exist.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="02c8b-108">반환 값</span><span class="sxs-lookup"><span data-stu-id="02c8b-108">Return Value</span></span>  
  
|<span data-ttu-id="02c8b-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="02c8b-109">HRESULT</span></span>|<span data-ttu-id="02c8b-110">Description</span><span class="sxs-lookup"><span data-stu-id="02c8b-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="02c8b-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="02c8b-111">S_OK</span></span>|<span data-ttu-id="02c8b-112">작업에 성공 합니다.</span><span class="sxs-lookup"><span data-stu-id="02c8b-112">The operation was successful.</span></span>|  
|<span data-ttu-id="02c8b-113">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="02c8b-113">S_FALSE</span></span>|<span data-ttu-id="02c8b-114">작업을 완료 하지 못했습니다 또는 열거형에 도메인이 더 있습니다.</span><span class="sxs-lookup"><span data-stu-id="02c8b-114">The operation failed to complete, or there are no more domains in the enumeration.</span></span>|  
|<span data-ttu-id="02c8b-115">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="02c8b-115">E_FAIL</span></span>|<span data-ttu-id="02c8b-116">알 수 없는 치명적인 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="02c8b-116">An unknown, catastrophic failure occurred.</span></span> <span data-ttu-id="02c8b-117">E_FAIL을 반환 하는 메서드는 CLR (공용 언어 런타임) 더 이상 사용할 수 진행에서 합니다.</span><span class="sxs-lookup"><span data-stu-id="02c8b-117">If a method returns E_FAIL, the common language runtime (CLR) is no longer usable in the process.</span></span> <span data-ttu-id="02c8b-118">호스팅 Api에 대 한 후속 호출 HOST_E_CLRNOTAVAILABLE를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="02c8b-118">Subsequent calls to any hosting APIs return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="02c8b-119">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="02c8b-119">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="02c8b-120">CLR이 로드 된 프로세스에 또는 CLR 상태인는 관리 코드를 실행 하거나 호출을 처리할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="02c8b-120">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="02c8b-121">요구 사항</span><span class="sxs-lookup"><span data-stu-id="02c8b-121">Requirements</span></span>  
 <span data-ttu-id="02c8b-122">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="02c8b-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="02c8b-123">**헤더:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="02c8b-123">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="02c8b-124">**라이브러리:** MSCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="02c8b-124">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="02c8b-125">**.NET framework 버전:** 1.0, 1.1</span><span class="sxs-lookup"><span data-stu-id="02c8b-125">**.NET Framework Versions:** 1.0, 1.1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="02c8b-126">참고자료</span><span class="sxs-lookup"><span data-stu-id="02c8b-126">See also</span></span>

- <xref:System._AppDomain>
- <xref:System.AppDomain>
- [<span data-ttu-id="02c8b-127">ICorRuntimeHost 인터페이스</span><span class="sxs-lookup"><span data-stu-id="02c8b-127">ICorRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md)
