---
title: ICLRRuntimeInfo::IsStarted 메서드
ms.date: 03/30/2017
api_name:
- ICLRRuntimeInfo.IsStarted
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRRuntimeInfo::IsStarted
helpviewer_keywords:
- IsStarted method [.NET Framework hosting]
- ICLRRuntimeInfo::IsStarted method [.NET Framework hosting]
ms.assetid: ef6f2662-323b-4534-aa82-6d1afb7b9309
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 45b1ef75227932449b68366345ded33a2cd96490
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/06/2019
ms.locfileid: "57479677"
---
# <a name="iclrruntimeinfoisstarted-method"></a><span data-ttu-id="6b5a4-102">ICLRRuntimeInfo::IsStarted 메서드</span><span class="sxs-lookup"><span data-stu-id="6b5a4-102">ICLRRuntimeInfo::IsStarted Method</span></span>
<span data-ttu-id="6b5a4-103">런타임이 시작 되었는지 여부를 나타냅니다 (있는지, 즉 합니다 [iclrruntimehost:: Start 메서드](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-start-method.md) 이 호출 되었고, 했습니다).</span><span class="sxs-lookup"><span data-stu-id="6b5a4-103">Indicates whether the runtime has been started (that is, whether the [ICLRRuntimeHost::Start method](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-start-method.md) has been called and has succeeded).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6b5a4-104">구문</span><span class="sxs-lookup"><span data-stu-id="6b5a4-104">Syntax</span></span>  
  
```  
HRESULT IsStarted(  
        [out] BOOL     *pbStarted,  
        [out] DWORD    *pdwStartupFlags);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6b5a4-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="6b5a4-105">Parameters</span></span>  
 `pbStarted`  
 <span data-ttu-id="6b5a4-106">[out] `true` 이 런타임에서이 고, 그렇지 않으면 시작 경우 `false`합니다.</span><span class="sxs-lookup"><span data-stu-id="6b5a4-106">[out] `true` if this runtime is started; otherwise, `false`.</span></span>  
  
 `pdwStartupFlags`  
 <span data-ttu-id="6b5a4-107">[out] 런타임을 시작 하는 데 사용 된 플래그를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="6b5a4-107">[out] Returns the flags that were used to start the runtime.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="6b5a4-108">반환 값</span><span class="sxs-lookup"><span data-stu-id="6b5a4-108">Return Value</span></span>  
 <span data-ttu-id="6b5a4-109">이 메서드는 다음과 같은 특정 HRESULT뿐만 아니라 메서드 오류를 나타내는 HRESULT 오류도 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="6b5a4-109">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="6b5a4-110">HRESULT</span><span class="sxs-lookup"><span data-stu-id="6b5a4-110">HRESULT</span></span>|<span data-ttu-id="6b5a4-111">설명</span><span class="sxs-lookup"><span data-stu-id="6b5a4-111">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="6b5a4-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="6b5a4-112">S_OK</span></span>|<span data-ttu-id="6b5a4-113">메서드가 완료되었습니다.</span><span class="sxs-lookup"><span data-stu-id="6b5a4-113">The method completed successfully.</span></span>|  
|<span data-ttu-id="6b5a4-114">E_NOTIMPL</span><span class="sxs-lookup"><span data-stu-id="6b5a4-114">E_NOTIMPL</span></span>|<span data-ttu-id="6b5a4-115">공용 언어 런타임 (CLR) 버전에서 CLR 버전 보다 이전 인지를 [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)]입니다.</span><span class="sxs-lookup"><span data-stu-id="6b5a4-115">The common language runtime (CLR) version is earlier than the CLR version in the [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6b5a4-116">설명</span><span class="sxs-lookup"><span data-stu-id="6b5a4-116">Remarks</span></span>  
 <span data-ttu-id="6b5a4-117">이 메서드는 사용 하지 않고 CLR 버전에서 CLR 버전 보다 이전는 [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)]합니다.</span><span class="sxs-lookup"><span data-stu-id="6b5a4-117">This method does not work with CLR versions earlier than the CLR version in the [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)].</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6b5a4-118">요구 사항</span><span class="sxs-lookup"><span data-stu-id="6b5a4-118">Requirements</span></span>  
 <span data-ttu-id="6b5a4-119">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="6b5a4-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6b5a4-120">**헤더:** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="6b5a4-120">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="6b5a4-121">**라이브러리:** MSCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="6b5a4-121">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="6b5a4-122">**.NET Framework 버전:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6b5a4-122">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6b5a4-123">참고자료</span><span class="sxs-lookup"><span data-stu-id="6b5a4-123">See also</span></span>
- [<span data-ttu-id="6b5a4-124">ICLRRuntimeInfo 인터페이스</span><span class="sxs-lookup"><span data-stu-id="6b5a4-124">ICLRRuntimeInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md)
- [<span data-ttu-id="6b5a4-125">호스팅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="6b5a4-125">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
- [<span data-ttu-id="6b5a4-126">호스팅</span><span class="sxs-lookup"><span data-stu-id="6b5a4-126">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)
