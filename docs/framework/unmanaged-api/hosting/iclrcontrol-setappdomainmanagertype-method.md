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
ms.openlocfilehash: e62f9fd6b8421ea131eff0e6b36523718589c921
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/19/2020
ms.locfileid: "83615831"
---
# <a name="iclrcontrolsetappdomainmanagertype-method"></a><span data-ttu-id="cbbfc-102">ICLRControl::SetAppDomainManagerType 메서드</span><span class="sxs-lookup"><span data-stu-id="cbbfc-102">ICLRControl::SetAppDomainManagerType Method</span></span>
<span data-ttu-id="cbbfc-103">에서 파생 된 형식을 <xref:System.AppDomainManager> 응용 프로그램 도메인 관리자의 형식으로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="cbbfc-103">Sets a type derived from <xref:System.AppDomainManager> as the type for application domain managers.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cbbfc-104">구문</span><span class="sxs-lookup"><span data-stu-id="cbbfc-104">Syntax</span></span>  
  
```cpp  
HRESULT SetAppDomainManagerType (  
    [in] LPCWSTR pwzAppDomainManagerAssembly,  
    [in] LPCWSTR pwzAppDomainManagerType  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="cbbfc-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="cbbfc-105">Parameters</span></span>  
 `pwzAppDomainManagerAssembly`  
 <span data-ttu-id="cbbfc-106">진행 에서 파생 된 요청 된 형식이 구현 되는 어셈블리의 이름입니다 <xref:System.AppDomainManager> .</span><span class="sxs-lookup"><span data-stu-id="cbbfc-106">[in] The name of the assembly in which the requested type derived from <xref:System.AppDomainManager> is implemented.</span></span>  
  
 `pwzAppDomainManagerType`  
 <span data-ttu-id="cbbfc-107">진행 `pwzAppDomainManagerAssembly`의 기능을 구현 하는 매개 변수에 구현 된 형식의 이름입니다 <xref:System.AppDomainManager> .</span><span class="sxs-lookup"><span data-stu-id="cbbfc-107">[in] The name of the type implemented in the `pwzAppDomainManagerAssembly` parameter that implements the capabilities of <xref:System.AppDomainManager>.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="cbbfc-108">Return Value</span><span class="sxs-lookup"><span data-stu-id="cbbfc-108">Return Value</span></span>  
  
|<span data-ttu-id="cbbfc-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="cbbfc-109">HRESULT</span></span>|<span data-ttu-id="cbbfc-110">설명</span><span class="sxs-lookup"><span data-stu-id="cbbfc-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="cbbfc-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="cbbfc-111">S_OK</span></span>|<span data-ttu-id="cbbfc-112">메서드가 성공적으로 반환했습니다.</span><span class="sxs-lookup"><span data-stu-id="cbbfc-112">The method returned successfully.</span></span>|  
|<span data-ttu-id="cbbfc-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="cbbfc-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="cbbfc-114">CLR (공용 언어 런타임)이 프로세스에 로드 되지 않았거나 CLR이 관리 코드를 실행할 수 없거나 호출을 성공적으로 처리할 수 없는 상태에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cbbfc-114">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="cbbfc-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="cbbfc-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="cbbfc-116">호출 시간이 초과 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="cbbfc-116">The call timed out.</span></span>|  
|<span data-ttu-id="cbbfc-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="cbbfc-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="cbbfc-118">호출자가 잠금을 소유 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="cbbfc-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="cbbfc-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="cbbfc-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="cbbfc-120">차단 된 스레드나 파이버에서 대기 하는 동안 이벤트를 취소 했습니다.</span><span class="sxs-lookup"><span data-stu-id="cbbfc-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="cbbfc-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="cbbfc-121">E_FAIL</span></span>|<span data-ttu-id="cbbfc-122">알 수 없는 치명적인 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="cbbfc-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="cbbfc-123">메서드가 E_FAIL 반환 된 후에는 프로세스 내에서 CLR을 더 이상 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="cbbfc-123">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="cbbfc-124">호스팅 메서드를 이후에 호출 하면 HOST_E_CLRNOTAVAILABLE 반환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="cbbfc-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="cbbfc-125">요구 사항</span><span class="sxs-lookup"><span data-stu-id="cbbfc-125">Requirements</span></span>  
 <span data-ttu-id="cbbfc-126">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="cbbfc-126">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cbbfc-127">**헤더:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="cbbfc-127">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="cbbfc-128">**라이브러리:** Mscoree.dll에 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="cbbfc-128">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="cbbfc-129">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cbbfc-129">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cbbfc-130">참고 항목</span><span class="sxs-lookup"><span data-stu-id="cbbfc-130">See also</span></span>

- [<span data-ttu-id="cbbfc-131">ICLRControl 인터페이스</span><span class="sxs-lookup"><span data-stu-id="cbbfc-131">ICLRControl Interface</span></span>](iclrcontrol-interface.md)
- [<span data-ttu-id="cbbfc-132">IHostControl 인터페이스</span><span class="sxs-lookup"><span data-stu-id="cbbfc-132">IHostControl Interface</span></span>](ihostcontrol-interface.md)
