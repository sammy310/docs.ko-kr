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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 571a676496683ba3251f13c41600bb017e1ced5d
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59156106"
---
# <a name="lockclrversion-function"></a><span data-ttu-id="1306e-102">LockClrVersion 함수</span><span class="sxs-lookup"><span data-stu-id="1306e-102">LockClrVersion Function</span></span>
<span data-ttu-id="1306e-103">호스트가 명시적으로 CLR을 초기화 하기 전에 프로세스 내에서 사용할는 버전의 CLR (공용 언어 런타임)을 결정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1306e-103">Allows the host to determine which version of the common language runtime (CLR) will be used within the process before explicitly initializing the CLR.</span></span>  
  
 <span data-ttu-id="1306e-104">이 함수에서 사용 중단에 [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)]합니다.</span><span class="sxs-lookup"><span data-stu-id="1306e-104">This function has been deprecated in the [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1306e-105">구문</span><span class="sxs-lookup"><span data-stu-id="1306e-105">Syntax</span></span>  
  
```  
HRESULT LockClrVersion (  
    [in] FLockClrVersionCallback   hostCallback,  
    [in] FLockClrVersionCallback  *pBeginHostSetup,  
    [in] FLockClrVersionCallback  *pEndHostSetup  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1306e-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="1306e-106">Parameters</span></span>  
 `hostCallback`  
 <span data-ttu-id="1306e-107">[in] 초기화 시 CLR에서 호출 되는 함수입니다.</span><span class="sxs-lookup"><span data-stu-id="1306e-107">[in] The function to be called by the CLR upon initialization.</span></span>  
  
 `pBeginHostSetup`  
 <span data-ttu-id="1306e-108">[in] 해당 초기화 CLR을 알리기 위해 호스트에서 호출 될 함수를 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="1306e-108">[in] The function to be called by the host to inform the CLR that initialization is starting.</span></span>  
  
 `pEndHostSetup`  
 <span data-ttu-id="1306e-109">[in] 해당 초기화 CLR을 알리기 위해 호스트에서 호출 될 함수 완료 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="1306e-109">[in] The function to be called by the host to inform the CLR that initialization is complete.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="1306e-110">반환 값</span><span class="sxs-lookup"><span data-stu-id="1306e-110">Return Value</span></span>  
 <span data-ttu-id="1306e-111">이 메서드는 다음 값 외에도 WinError.h에 정의 된 대로 표준 COM 오류 코드를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="1306e-111">This method returns standard COM error codes, as defined in WinError.h, in addition to the following values.</span></span>  
  
|<span data-ttu-id="1306e-112">반환 코드</span><span class="sxs-lookup"><span data-stu-id="1306e-112">Return code</span></span>|<span data-ttu-id="1306e-113">설명</span><span class="sxs-lookup"><span data-stu-id="1306e-113">Description</span></span>|  
|-----------------|-----------------|  
|<span data-ttu-id="1306e-114">S_OK</span><span class="sxs-lookup"><span data-stu-id="1306e-114">S_OK</span></span>|<span data-ttu-id="1306e-115">메서드가 완료되었습니다.</span><span class="sxs-lookup"><span data-stu-id="1306e-115">The method completed successfully.</span></span>|  
|<span data-ttu-id="1306e-116">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="1306e-116">E_INVALIDARG</span></span>|<span data-ttu-id="1306e-117">인수 중 하나 이상이 null입니다.</span><span class="sxs-lookup"><span data-stu-id="1306e-117">One or more of the arguments is null.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1306e-118">설명</span><span class="sxs-lookup"><span data-stu-id="1306e-118">Remarks</span></span>  
 <span data-ttu-id="1306e-119">호스트에서는 `LockClrVersion` CLR을 초기화 하기 전에 합니다.</span><span class="sxs-lookup"><span data-stu-id="1306e-119">The host calls `LockClrVersion` before initializing the CLR.</span></span> `LockClrVersion` <span data-ttu-id="1306e-120">형식의 콜백을 모두 3 개의 매개 변수를 [FLockClrVersionCallback](../../../../docs/framework/unmanaged-api/hosting/flockclrversioncallback-function-pointer.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="1306e-120">takes three parameters, all of which are callbacks of type [FLockClrVersionCallback](../../../../docs/framework/unmanaged-api/hosting/flockclrversioncallback-function-pointer.md).</span></span> <span data-ttu-id="1306e-121">이 형식은 다음과 같이 정의 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1306e-121">This type is defined as follows.</span></span>  
  
```  
typedef HRESULT ( __stdcall *FLockClrVersionCallback ) ();  
```  
  
 <span data-ttu-id="1306e-122">다음 단계는 런타임 초기화 시 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="1306e-122">The following steps occur upon initialization of the runtime:</span></span>  
  
1.  <span data-ttu-id="1306e-123">호스트 호출 [CorBindToRuntimeEx](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md) 또는 다른 런타임 초기화 함수 중 하나입니다.</span><span class="sxs-lookup"><span data-stu-id="1306e-123">The host calls [CorBindToRuntimeEx](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md) or one of the other runtime initialization functions.</span></span> <span data-ttu-id="1306e-124">또는 호스트 COM 개체 활성화를 사용 하 여 런타임을 초기화할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="1306e-124">Alternatively, the host could initialize the runtime using COM object activation.</span></span>  
  
2.  <span data-ttu-id="1306e-125">런타임에서 호출 하 여 지정 된 함수는 `hostCallback` 매개 변수입니다.</span><span class="sxs-lookup"><span data-stu-id="1306e-125">The runtime calls the function specified by the `hostCallback` parameter.</span></span>  
  
3.  <span data-ttu-id="1306e-126">지정 된 함수의 `hostCallback` 다음 호출 시퀀스를 사용 하는 합니다.</span><span class="sxs-lookup"><span data-stu-id="1306e-126">The function specified by `hostCallback` then makes the following sequence of calls:</span></span>  
  
    -   <span data-ttu-id="1306e-127">에 지정 된 함수는 `pBeginHostSetup` 매개 변수입니다.</span><span class="sxs-lookup"><span data-stu-id="1306e-127">The function specified by the `pBeginHostSetup` parameter.</span></span>  
  
    -   `CorBindToRuntimeEx` <span data-ttu-id="1306e-128">(또는 다른 런타임 초기화 함수)입니다.</span><span class="sxs-lookup"><span data-stu-id="1306e-128">(or another runtime initialization function).</span></span>  
  
    -   <span data-ttu-id="1306e-129">[ICLRRuntimeHost::SetHostControl](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-sethostcontrol-method.md).</span><span class="sxs-lookup"><span data-stu-id="1306e-129">[ICLRRuntimeHost::SetHostControl](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-sethostcontrol-method.md).</span></span>  
  
    -   <span data-ttu-id="1306e-130">[ICLRRuntimeHost::Start](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-start-method.md).</span><span class="sxs-lookup"><span data-stu-id="1306e-130">[ICLRRuntimeHost::Start](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-start-method.md).</span></span>  
  
    -   <span data-ttu-id="1306e-131">에 지정 된 함수는 `pEndHostSetup` 매개 변수입니다.</span><span class="sxs-lookup"><span data-stu-id="1306e-131">The function specified by the `pEndHostSetup` parameter.</span></span>  
  
 <span data-ttu-id="1306e-132">모든 호출은 `pBeginHostSetup` 에 `pEndHostSetup` 단일 스레드 또는 파이버를 동일한 논리 스택과 수행 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1306e-132">All the calls from `pBeginHostSetup` to `pEndHostSetup` must occur on a single thread or fiber, with the same logical stack.</span></span> <span data-ttu-id="1306e-133">이 스레드는 스레드에서 다를 수 있습니다 `hostCallback` 라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="1306e-133">This thread can be different from the thread upon which `hostCallback` is called.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1306e-134">요구 사항</span><span class="sxs-lookup"><span data-stu-id="1306e-134">Requirements</span></span>  
 <span data-ttu-id="1306e-135">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="1306e-135">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1306e-136">**헤더:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="1306e-136">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="1306e-137">**라이브러리:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="1306e-137">**Library:** MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="1306e-138">.NET Framework 버전:</span><span class="sxs-lookup"><span data-stu-id="1306e-138">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="1306e-139">참고자료</span><span class="sxs-lookup"><span data-stu-id="1306e-139">See also</span></span>

- [<span data-ttu-id="1306e-140">사용되지 않는 CLR 호스팅 함수</span><span class="sxs-lookup"><span data-stu-id="1306e-140">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
