---
title: ICLRRuntimeInfo::IsLoadable 메서드
ms.date: 03/30/2017
api_name:
- ICLRRuntimeInfo.IsLoadable
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRRuntimeInfo::IsLoadable
helpviewer_keywords:
- IsLoadable method [.NET Framework hosting]
- ICLRRuntimeInfo::IsLoadable method [.NET Framework hosting]
ms.assetid: 205ca53b-e78e-49b2-9a46-2a7823e96b8c
topic_type:
- apiref
ms.openlocfilehash: 9339bb974c261e62502c760dfaf45651573cbe1a
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73136370"
---
# <a name="iclrruntimeinfoisloadable-method"></a><span data-ttu-id="ca124-102">ICLRRuntimeInfo::IsLoadable 메서드</span><span class="sxs-lookup"><span data-stu-id="ca124-102">ICLRRuntimeInfo::IsLoadable Method</span></span>
<span data-ttu-id="ca124-103">프로세스에 이미 로드 되어 있을 수 있는 다른 런타임을 고려 하 여이 인터페이스와 연결 된 런타임을 현재 프로세스에 로드할 수 있는지 여부를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="ca124-103">Indicates whether the runtime associated with this interface can be loaded into the current process, taking into account other runtimes that might already be loaded into the process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ca124-104">구문</span><span class="sxs-lookup"><span data-stu-id="ca124-104">Syntax</span></span>  
  
```cpp  
HRESULT IsLoadable(  
        [out, retval] BOOL *pbLoadable);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ca124-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="ca124-105">Parameters</span></span>  
 `pbLoadable`  
 <span data-ttu-id="ca124-106">[out]이 런타임을 현재 프로세스에 로드할 수 있는 경우 `true` 합니다. 그렇지 않으면 `false`합니다.</span><span class="sxs-lookup"><span data-stu-id="ca124-106">[out] `true` if this runtime could be loaded into the current process; otherwise, `false`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="ca124-107">반환 값</span><span class="sxs-lookup"><span data-stu-id="ca124-107">Return Value</span></span>  
 <span data-ttu-id="ca124-108">이 메서드는 다음과 같은 특정 HRESULT뿐만 아니라 메서드 오류를 나타내는 HRESULT 오류도 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="ca124-108">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="ca124-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="ca124-109">HRESULT</span></span>|<span data-ttu-id="ca124-110">설명</span><span class="sxs-lookup"><span data-stu-id="ca124-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="ca124-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="ca124-111">S_OK</span></span>|<span data-ttu-id="ca124-112">메서드가 완료되었습니다.</span><span class="sxs-lookup"><span data-stu-id="ca124-112">The method completed successfully.</span></span>|  
|<span data-ttu-id="ca124-113">E_POINTER</span><span class="sxs-lookup"><span data-stu-id="ca124-113">E_POINTER</span></span>|<span data-ttu-id="ca124-114">`pbLoadable`가 null입니다.</span><span class="sxs-lookup"><span data-stu-id="ca124-114">`pbLoadable` is null.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ca124-115">주의</span><span class="sxs-lookup"><span data-stu-id="ca124-115">Remarks</span></span>  
 <span data-ttu-id="ca124-116">다른 런타임이 이미 프로세스에 로드 되어 있고이 인터페이스와 연결 된 런타임을 in-process side-by-side 실행에 대해 로드할 수 있는 경우 `pbLoadable` `true`를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="ca124-116">If another runtime is already loaded into the process and the runtime associated with this interface can be loaded for in-process side-by-side execution, `pbLoadable` returns `true`.</span></span> <span data-ttu-id="ca124-117">두 런타임이 동시에 실행 될 수 없는 경우 `pbLoadable`은 `false`을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="ca124-117">If the two runtimes cannot run side-by-side in-process, `pbLoadable` returns `false`.</span></span> <span data-ttu-id="ca124-118">예를 들어 clr (공용 언어 런타임) 버전 4는 CLR 버전 2.0 또는 CLR 버전 1.1과 동일한 프로세스에서 함께 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ca124-118">For example, the common language runtime (CLR) version 4 can run side-by-side in the same process with CLR version 2.0 or CLR version 1.1.</span></span> <span data-ttu-id="ca124-119">그러나 CLR 버전 1.1 및 CLR 버전 2.0는 side-by-side로 실행할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="ca124-119">However, CLR version 1.1 and CLR version 2.0 cannot run side-by-side in-process.</span></span>  
  
 <span data-ttu-id="ca124-120">프로세스에 로드 된 런타임이 없으면이 메서드는 항상 `true`반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="ca124-120">If no runtimes are loaded into the process, this method always returns `true`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ca124-121">요구 사항</span><span class="sxs-lookup"><span data-stu-id="ca124-121">Requirements</span></span>  
 <span data-ttu-id="ca124-122">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ca124-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ca124-123">**헤더:** MetaHost</span><span class="sxs-lookup"><span data-stu-id="ca124-123">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="ca124-124">**라이브러리:** Mscoree.dll에 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ca124-124">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="ca124-125">**.NET Framework 버전:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ca124-125">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ca124-126">참조</span><span class="sxs-lookup"><span data-stu-id="ca124-126">See also</span></span>

- [<span data-ttu-id="ca124-127">ICLRRuntimeInfo 인터페이스</span><span class="sxs-lookup"><span data-stu-id="ca124-127">ICLRRuntimeInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md)
- [<span data-ttu-id="ca124-128">호스팅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="ca124-128">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
- [<span data-ttu-id="ca124-129">호스팅</span><span class="sxs-lookup"><span data-stu-id="ca124-129">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)
