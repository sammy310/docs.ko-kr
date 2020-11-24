---
title: ICLRControl::SetAppDomainManagerType 메서드
ms.date: 03/30/2017
api_name:
- ICLRControl.SetAppDomainManagerType
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRControl::SetAppDomainManagerType
helpviewer_keywords:
- SetAppDomainManagerType method, ICLRControl interface [.NET Framework hosting]
- ICLRControl::SetAppDomainManagerType method [.NET Framework hosting]
ms.assetid: ec57828b-2aad-496d-a35a-e45d4bd7fe77
topic_type:
- apiref
ms.openlocfilehash: 28fdd5340aee0fcd9875dd983c8c7649b5491c04
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95674712"
---
# <a name="iclrcontrolsetappdomainmanagertype-method"></a><span data-ttu-id="0b2dc-102">ICLRControl::SetAppDomainManagerType 메서드</span><span class="sxs-lookup"><span data-stu-id="0b2dc-102">ICLRControl::SetAppDomainManagerType Method</span></span>

<span data-ttu-id="0b2dc-103">에서 파생 된 형식을 <xref:System.AppDomainManager> 응용 프로그램 도메인 관리자의 형식으로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="0b2dc-103">Sets a type derived from <xref:System.AppDomainManager> as the type for application domain managers.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0b2dc-104">구문</span><span class="sxs-lookup"><span data-stu-id="0b2dc-104">Syntax</span></span>  
  
```cpp  
HRESULT SetAppDomainManagerType (  
    [in] LPCWSTR pwzAppDomainManagerAssembly,  
    [in] LPCWSTR pwzAppDomainManagerType  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0b2dc-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="0b2dc-105">Parameters</span></span>  

 `pwzAppDomainManagerAssembly`  
 <span data-ttu-id="0b2dc-106">진행 에서 파생 된 요청 된 형식이 구현 되는 어셈블리의 이름입니다 <xref:System.AppDomainManager> .</span><span class="sxs-lookup"><span data-stu-id="0b2dc-106">[in] The name of the assembly in which the requested type derived from <xref:System.AppDomainManager> is implemented.</span></span>  
  
 `pwzAppDomainManagerType`  
 <span data-ttu-id="0b2dc-107">진행 `pwzAppDomainManagerAssembly` 의 기능을 구현 하는 매개 변수에 구현 된 형식의 이름입니다 <xref:System.AppDomainManager> .</span><span class="sxs-lookup"><span data-stu-id="0b2dc-107">[in] The name of the type implemented in the `pwzAppDomainManagerAssembly` parameter that implements the capabilities of <xref:System.AppDomainManager>.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="0b2dc-108">반환 값</span><span class="sxs-lookup"><span data-stu-id="0b2dc-108">Return Value</span></span>  
  
|<span data-ttu-id="0b2dc-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="0b2dc-109">HRESULT</span></span>|<span data-ttu-id="0b2dc-110">설명</span><span class="sxs-lookup"><span data-stu-id="0b2dc-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="0b2dc-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="0b2dc-111">S_OK</span></span>|<span data-ttu-id="0b2dc-112">메서드가 성공적으로 반환했습니다.</span><span class="sxs-lookup"><span data-stu-id="0b2dc-112">The method returned successfully.</span></span>|  
|<span data-ttu-id="0b2dc-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="0b2dc-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="0b2dc-114">CLR (공용 언어 런타임)이 프로세스에 로드 되지 않았거나 CLR이 관리 코드를 실행할 수 없거나 호출을 성공적으로 처리할 수 없는 상태에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0b2dc-114">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="0b2dc-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="0b2dc-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="0b2dc-116">호출 시간이 초과 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="0b2dc-116">The call timed out.</span></span>|  
|<span data-ttu-id="0b2dc-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="0b2dc-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="0b2dc-118">호출자가 잠금을 소유 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0b2dc-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="0b2dc-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="0b2dc-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="0b2dc-120">차단 된 스레드나 파이버에서 대기 하는 동안 이벤트를 취소 했습니다.</span><span class="sxs-lookup"><span data-stu-id="0b2dc-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="0b2dc-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="0b2dc-121">E_FAIL</span></span>|<span data-ttu-id="0b2dc-122">알 수 없는 치명적인 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="0b2dc-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="0b2dc-123">메서드가 E_FAIL 반환 된 후에는 프로세스 내에서 CLR을 더 이상 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="0b2dc-123">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="0b2dc-124">호스팅 메서드를 이후에 호출 하면 HOST_E_CLRNOTAVAILABLE 반환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0b2dc-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="0b2dc-125">요구 사항</span><span class="sxs-lookup"><span data-stu-id="0b2dc-125">Requirements</span></span>  

 <span data-ttu-id="0b2dc-126">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="0b2dc-126">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0b2dc-127">**헤더:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="0b2dc-127">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="0b2dc-128">**라이브러리:** MSCorEE.dll의 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0b2dc-128">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="0b2dc-129">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0b2dc-129">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0b2dc-130">참조</span><span class="sxs-lookup"><span data-stu-id="0b2dc-130">See also</span></span>

- [<span data-ttu-id="0b2dc-131">ICLRControl 인터페이스</span><span class="sxs-lookup"><span data-stu-id="0b2dc-131">ICLRControl Interface</span></span>](iclrcontrol-interface.md)
- [<span data-ttu-id="0b2dc-132">IHostControl 인터페이스</span><span class="sxs-lookup"><span data-stu-id="0b2dc-132">IHostControl Interface</span></span>](ihostcontrol-interface.md)
