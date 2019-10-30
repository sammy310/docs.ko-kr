---
title: LockClrVersion 함수
ms.date: 03/30/2017
api_name:
- LockClrVersion
api_location:
- mscoree.dll
- mscoreei.dll
api_type:
- DLLExport
f1_keywords:
- LockClrVersion
helpviewer_keywords:
- LockClrVersion function [.NET Framework hosting]
ms.assetid: 1318ee37-c43b-40eb-bbe8-88fc46453d74
topic_type:
- apiref
ms.openlocfilehash: 216852f8f051440b2814619b843a1f25013e4042
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73133767"
---
# <a name="lockclrversion-function"></a><span data-ttu-id="fad83-102">LockClrVersion 함수</span><span class="sxs-lookup"><span data-stu-id="fad83-102">LockClrVersion Function</span></span>
<span data-ttu-id="fad83-103">호스트에서 CLR을 명시적으로 초기화 하기 전에 프로세스 내에서 사용할 CLR (공용 언어 런타임) 버전을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fad83-103">Allows the host to determine which version of the common language runtime (CLR) will be used within the process before explicitly initializing the CLR.</span></span>  
  
 <span data-ttu-id="fad83-104">이 함수는 .NET Framework 4에서 더 이상 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="fad83-104">This function has been deprecated in the .NET Framework 4.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fad83-105">구문</span><span class="sxs-lookup"><span data-stu-id="fad83-105">Syntax</span></span>  
  
```cpp  
HRESULT LockClrVersion (  
    [in] FLockClrVersionCallback   hostCallback,  
    [in] FLockClrVersionCallback  *pBeginHostSetup,  
    [in] FLockClrVersionCallback  *pEndHostSetup  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="fad83-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="fad83-106">Parameters</span></span>  
 `hostCallback`  
 <span data-ttu-id="fad83-107">진행 초기화 될 때 CLR에 의해 호출 되는 함수입니다.</span><span class="sxs-lookup"><span data-stu-id="fad83-107">[in] The function to be called by the CLR upon initialization.</span></span>  
  
 `pBeginHostSetup`  
 <span data-ttu-id="fad83-108">진행 초기화가 시작 됨을 CLR에 알리기 위해 호스트에서 호출 하는 함수입니다.</span><span class="sxs-lookup"><span data-stu-id="fad83-108">[in] The function to be called by the host to inform the CLR that initialization is starting.</span></span>  
  
 `pEndHostSetup`  
 <span data-ttu-id="fad83-109">진행 초기화가 완료 되었음을 CLR에 알리기 위해 호스트에서 호출 하는 함수입니다.</span><span class="sxs-lookup"><span data-stu-id="fad83-109">[in] The function to be called by the host to inform the CLR that initialization is complete.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="fad83-110">반환 값</span><span class="sxs-lookup"><span data-stu-id="fad83-110">Return Value</span></span>  
 <span data-ttu-id="fad83-111">이 메서드는 Winerror.h에 정의 된 대로 다음 값 외에 표준 COM 오류 코드를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="fad83-111">This method returns standard COM error codes, as defined in WinError.h, in addition to the following values.</span></span>  
  
|<span data-ttu-id="fad83-112">반환 코드</span><span class="sxs-lookup"><span data-stu-id="fad83-112">Return code</span></span>|<span data-ttu-id="fad83-113">설명</span><span class="sxs-lookup"><span data-stu-id="fad83-113">Description</span></span>|  
|-----------------|-----------------|  
|<span data-ttu-id="fad83-114">S_OK</span><span class="sxs-lookup"><span data-stu-id="fad83-114">S_OK</span></span>|<span data-ttu-id="fad83-115">메서드가 완료되었습니다.</span><span class="sxs-lookup"><span data-stu-id="fad83-115">The method completed successfully.</span></span>|  
|<span data-ttu-id="fad83-116">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="fad83-116">E_INVALIDARG</span></span>|<span data-ttu-id="fad83-117">하나 이상의 인수가 null입니다.</span><span class="sxs-lookup"><span data-stu-id="fad83-117">One or more of the arguments is null.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="fad83-118">주의</span><span class="sxs-lookup"><span data-stu-id="fad83-118">Remarks</span></span>  
 <span data-ttu-id="fad83-119">CLR을 초기화 하기 전에 호스트에서 `LockClrVersion`를 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="fad83-119">The host calls `LockClrVersion` before initializing the CLR.</span></span> <span data-ttu-id="fad83-120">`LockClrVersion`는 세 개의 매개 변수를 사용 하며, 모두 [Flockclrversioncallback](../../../../docs/framework/unmanaged-api/hosting/flockclrversioncallback-function-pointer.md)형식의 콜백입니다.</span><span class="sxs-lookup"><span data-stu-id="fad83-120">`LockClrVersion` takes three parameters, all of which are callbacks of type [FLockClrVersionCallback](../../../../docs/framework/unmanaged-api/hosting/flockclrversioncallback-function-pointer.md).</span></span> <span data-ttu-id="fad83-121">이 형식은 다음과 같이 정의 됩니다.</span><span class="sxs-lookup"><span data-stu-id="fad83-121">This type is defined as follows.</span></span>  
  
```cpp  
typedef HRESULT ( __stdcall *FLockClrVersionCallback ) ();  
```  
  
 <span data-ttu-id="fad83-122">다음 단계는 런타임을 초기화할 때 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="fad83-122">The following steps occur upon initialization of the runtime:</span></span>  
  
1. <span data-ttu-id="fad83-123">호스트는 [CorBindToRuntimeEx](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md) 또는 다른 런타임 초기화 함수 중 하나를 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="fad83-123">The host calls [CorBindToRuntimeEx](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md) or one of the other runtime initialization functions.</span></span> <span data-ttu-id="fad83-124">또는 호스트에서 COM 개체 활성화를 사용 하 여 런타임을 초기화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fad83-124">Alternatively, the host could initialize the runtime using COM object activation.</span></span>  
  
2. <span data-ttu-id="fad83-125">런타임은 `hostCallback` 매개 변수에 지정 된 함수를 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="fad83-125">The runtime calls the function specified by the `hostCallback` parameter.</span></span>  
  
3. <span data-ttu-id="fad83-126">`hostCallback`에서 지정 하는 함수는 다음과 같은 일련의 호출을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="fad83-126">The function specified by `hostCallback` then makes the following sequence of calls:</span></span>  
  
    - <span data-ttu-id="fad83-127">`pBeginHostSetup` 매개 변수에서 지정 하는 함수입니다.</span><span class="sxs-lookup"><span data-stu-id="fad83-127">The function specified by the `pBeginHostSetup` parameter.</span></span>  
  
    - <span data-ttu-id="fad83-128">`CorBindToRuntimeEx` (또는 다른 런타임 초기화 함수).</span><span class="sxs-lookup"><span data-stu-id="fad83-128">`CorBindToRuntimeEx` (or another runtime initialization function).</span></span>  
  
    - <span data-ttu-id="fad83-129">[ICLRRuntimeHost:: SetHostControl](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-sethostcontrol-method.md).</span><span class="sxs-lookup"><span data-stu-id="fad83-129">[ICLRRuntimeHost::SetHostControl](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-sethostcontrol-method.md).</span></span>  
  
    - <span data-ttu-id="fad83-130">[ICLRRuntimeHost:: Start](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-start-method.md).</span><span class="sxs-lookup"><span data-stu-id="fad83-130">[ICLRRuntimeHost::Start](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-start-method.md).</span></span>  
  
    - <span data-ttu-id="fad83-131">`pEndHostSetup` 매개 변수에서 지정 하는 함수입니다.</span><span class="sxs-lookup"><span data-stu-id="fad83-131">The function specified by the `pEndHostSetup` parameter.</span></span>  
  
 <span data-ttu-id="fad83-132">`pBeginHostSetup` `pEndHostSetup`에서의 모든 호출은 동일한 논리 스택을 사용 하는 단일 스레드나 파이버에서 발생 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fad83-132">All the calls from `pBeginHostSetup` to `pEndHostSetup` must occur on a single thread or fiber, with the same logical stack.</span></span> <span data-ttu-id="fad83-133">이 스레드는 `hostCallback`가 호출 되는 스레드와 다를 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fad83-133">This thread can be different from the thread upon which `hostCallback` is called.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fad83-134">요구 사항</span><span class="sxs-lookup"><span data-stu-id="fad83-134">Requirements</span></span>  
 <span data-ttu-id="fad83-135">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="fad83-135">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fad83-136">**헤더:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="fad83-136">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="fad83-137">**라이브러리:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="fad83-137">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="fad83-138">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fad83-138">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fad83-139">참조</span><span class="sxs-lookup"><span data-stu-id="fad83-139">See also</span></span>

- [<span data-ttu-id="fad83-140">사용되지 않는 CLR 호스팅 함수</span><span class="sxs-lookup"><span data-stu-id="fad83-140">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
