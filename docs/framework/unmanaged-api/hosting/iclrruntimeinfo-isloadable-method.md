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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 52257b30b8172b80f968df25115956b6995c1552
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59101590"
---
# <a name="iclrruntimeinfoisloadable-method"></a><span data-ttu-id="ee12b-102">ICLRRuntimeInfo::IsLoadable 메서드</span><span class="sxs-lookup"><span data-stu-id="ee12b-102">ICLRRuntimeInfo::IsLoadable Method</span></span>
<span data-ttu-id="ee12b-103">이 인터페이스와 연결 된 런타임 고려 현재 프로세스에 로드할 수 있는지 여부를 나타내는 프로세스에 이미 로드 될 수 있는 다른 런타임과 합니다.</span><span class="sxs-lookup"><span data-stu-id="ee12b-103">Indicates whether the runtime associated with this interface can be loaded into the current process, taking into account other runtimes that might already be loaded into the process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ee12b-104">구문</span><span class="sxs-lookup"><span data-stu-id="ee12b-104">Syntax</span></span>  
  
```  
HRESULT IsLoadable(  
        [out, retval] BOOL *pbLoadable);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ee12b-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="ee12b-105">Parameters</span></span>  
 `pbLoadable`  
 <span data-ttu-id="ee12b-106">[out] `true` 이 런타임에서이 고, 그렇지 않으면 현재 프로세스에 로드 수 있으면 `false`합니다.</span><span class="sxs-lookup"><span data-stu-id="ee12b-106">[out] `true` if this runtime could be loaded into the current process; otherwise, `false`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="ee12b-107">반환 값</span><span class="sxs-lookup"><span data-stu-id="ee12b-107">Return Value</span></span>  
 <span data-ttu-id="ee12b-108">이 메서드는 다음과 같은 특정 HRESULT뿐만 아니라 메서드 오류를 나타내는 HRESULT 오류도 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="ee12b-108">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="ee12b-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="ee12b-109">HRESULT</span></span>|<span data-ttu-id="ee12b-110">설명</span><span class="sxs-lookup"><span data-stu-id="ee12b-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="ee12b-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="ee12b-111">S_OK</span></span>|<span data-ttu-id="ee12b-112">메서드가 완료되었습니다.</span><span class="sxs-lookup"><span data-stu-id="ee12b-112">The method completed successfully.</span></span>|  
|<span data-ttu-id="ee12b-113">E_POINTER</span><span class="sxs-lookup"><span data-stu-id="ee12b-113">E_POINTER</span></span>|`pbLoadable` <span data-ttu-id="ee12b-114">null입니다.</span><span class="sxs-lookup"><span data-stu-id="ee12b-114">is null.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ee12b-115">설명</span><span class="sxs-lookup"><span data-stu-id="ee12b-115">Remarks</span></span>  
 <span data-ttu-id="ee12b-116">다른 런타임 프로세스에 이미 로드 하 고이 인터페이스와 연결 된 런타임 in-process side-by-side-실행에 로드할 수 있습니다 `pbLoadable` 반환 `true`합니다.</span><span class="sxs-lookup"><span data-stu-id="ee12b-116">If another runtime is already loaded into the process and the runtime associated with this interface can be loaded for in-process side-by-side execution, `pbLoadable` returns `true`.</span></span> <span data-ttu-id="ee12b-117">두 개의 런타임 side-by-side-in-process로 실행할 수 없는 경우 `pbLoadable` 반환 `false`합니다.</span><span class="sxs-lookup"><span data-stu-id="ee12b-117">If the two runtimes cannot run side-by-side in-process, `pbLoadable` returns `false`.</span></span> <span data-ttu-id="ee12b-118">예를 들어,는 CLR (공용 언어 런타임) 버전 4-side-by-side CLR 버전 2.0 사용 하 여 동일한 프로세스에서 또는 CLR 버전 1.1 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ee12b-118">For example, the common language runtime (CLR) version 4 can run side-by-side in the same process with CLR version 2.0 or CLR version 1.1.</span></span> <span data-ttu-id="ee12b-119">그러나 CLR 버전 1.1 및 CLR 버전 2.0-병렬 처리를 실행할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="ee12b-119">However, CLR version 1.1 and CLR version 2.0 cannot run side-by-side in-process.</span></span>  
  
 <span data-ttu-id="ee12b-120">런타임 없는 프로세스에 로드 되는 경우이 메서드는 항상 반환 `true`합니다.</span><span class="sxs-lookup"><span data-stu-id="ee12b-120">If no runtimes are loaded into the process, this method always returns `true`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ee12b-121">요구 사항</span><span class="sxs-lookup"><span data-stu-id="ee12b-121">Requirements</span></span>  
 <span data-ttu-id="ee12b-122">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="ee12b-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ee12b-123">**헤더:** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="ee12b-123">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="ee12b-124">**라이브러리:** MSCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="ee12b-124">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="ee12b-125">.NET Framework 버전:</span><span class="sxs-lookup"><span data-stu-id="ee12b-125">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="ee12b-126">참고자료</span><span class="sxs-lookup"><span data-stu-id="ee12b-126">See also</span></span>

- [<span data-ttu-id="ee12b-127">ICLRRuntimeInfo 인터페이스</span><span class="sxs-lookup"><span data-stu-id="ee12b-127">ICLRRuntimeInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md)
- [<span data-ttu-id="ee12b-128">호스팅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="ee12b-128">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
- [<span data-ttu-id="ee12b-129">호스팅</span><span class="sxs-lookup"><span data-stu-id="ee12b-129">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)
