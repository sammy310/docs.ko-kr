---
description: '자세히 알아보기: ICLRRuntimeInfo:: IsLoadable 때 메서드'
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
ms.openlocfilehash: cf63212350bfbd18e2a312add72818b163c32d0c
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99789790"
---
# <a name="iclrruntimeinfoisloadable-method"></a><span data-ttu-id="822d6-103">ICLRRuntimeInfo::IsLoadable 메서드</span><span class="sxs-lookup"><span data-stu-id="822d6-103">ICLRRuntimeInfo::IsLoadable Method</span></span>

<span data-ttu-id="822d6-104">프로세스에 이미 로드 되어 있을 수 있는 다른 런타임을 고려 하 여이 인터페이스와 연결 된 런타임을 현재 프로세스에 로드할 수 있는지 여부를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="822d6-104">Indicates whether the runtime associated with this interface can be loaded into the current process, taking into account other runtimes that might already be loaded into the process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="822d6-105">구문</span><span class="sxs-lookup"><span data-stu-id="822d6-105">Syntax</span></span>  
  
```cpp  
HRESULT IsLoadable(  
        [out, retval] BOOL *pbLoadable);  
```  
  
## <a name="parameters"></a><span data-ttu-id="822d6-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="822d6-106">Parameters</span></span>  

 `pbLoadable`  
 <span data-ttu-id="822d6-107">[out] `true` 이 런타임을 현재 프로세스로 로드할 수 있으면이 고, 그렇지 않으면입니다. 그렇지 않으면 `false` 입니다.</span><span class="sxs-lookup"><span data-stu-id="822d6-107">[out] `true` if this runtime could be loaded into the current process; otherwise, `false`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="822d6-108">Return Value</span><span class="sxs-lookup"><span data-stu-id="822d6-108">Return Value</span></span>  

 <span data-ttu-id="822d6-109">이 메서드는 다음과 같은 특정 HRESULT뿐만 아니라 메서드 오류를 나타내는 HRESULT 오류도 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="822d6-109">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="822d6-110">HRESULT</span><span class="sxs-lookup"><span data-stu-id="822d6-110">HRESULT</span></span>|<span data-ttu-id="822d6-111">설명</span><span class="sxs-lookup"><span data-stu-id="822d6-111">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="822d6-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="822d6-112">S_OK</span></span>|<span data-ttu-id="822d6-113">메서드가 완료되었습니다.</span><span class="sxs-lookup"><span data-stu-id="822d6-113">The method completed successfully.</span></span>|  
|<span data-ttu-id="822d6-114">E_POINTER</span><span class="sxs-lookup"><span data-stu-id="822d6-114">E_POINTER</span></span>|<span data-ttu-id="822d6-115">`pbLoadable`가 null입니다.</span><span class="sxs-lookup"><span data-stu-id="822d6-115">`pbLoadable` is null.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="822d6-116">설명</span><span class="sxs-lookup"><span data-stu-id="822d6-116">Remarks</span></span>  

 <span data-ttu-id="822d6-117">다른 런타임이 이미 프로세스에 로드 되었으며이 인터페이스와 연결 된 런타임을 in-process side-by-side 실행에 대해 로드할 수 있는 경우는을 `pbLoadable` 반환 `true` 합니다.</span><span class="sxs-lookup"><span data-stu-id="822d6-117">If another runtime is already loaded into the process, and the runtime associated with this interface can be loaded for in-process side-by-side execution, `pbLoadable` returns `true`.</span></span> <span data-ttu-id="822d6-118">두 런타임을 함께 실행할 수 없는 경우는를 `pbLoadable` 반환 `false` 합니다.</span><span class="sxs-lookup"><span data-stu-id="822d6-118">If the two runtimes cannot run side-by-side in-process, `pbLoadable` returns `false`.</span></span> <span data-ttu-id="822d6-119">예를 들어 clr (공용 언어 런타임) 버전 4는 CLR 버전 2.0 또는 CLR 버전 1.1과 동일한 프로세스에서 함께 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="822d6-119">For example, the common language runtime (CLR) version 4 can run side-by-side in the same process with CLR version 2.0 or CLR version 1.1.</span></span> <span data-ttu-id="822d6-120">그러나 CLR 버전 1.1 및 CLR 버전 2.0는 side-by-side로 실행할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="822d6-120">However, CLR version 1.1 and CLR version 2.0 cannot run side-by-side in-process.</span></span>  
  
 <span data-ttu-id="822d6-121">프로세스에 로드 된 런타임이 없으면이 메서드는 항상를 반환 `true` 합니다.</span><span class="sxs-lookup"><span data-stu-id="822d6-121">If no runtimes are loaded into the process, this method always returns `true`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="822d6-122">요구 사항</span><span class="sxs-lookup"><span data-stu-id="822d6-122">Requirements</span></span>  

 <span data-ttu-id="822d6-123">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="822d6-123">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="822d6-124">**헤더:** MetaHost</span><span class="sxs-lookup"><span data-stu-id="822d6-124">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="822d6-125">**라이브러리:** MSCorEE.dll의 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="822d6-125">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="822d6-126">**.NET Framework 버전:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="822d6-126">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="822d6-127">참고 항목</span><span class="sxs-lookup"><span data-stu-id="822d6-127">See also</span></span>

- [<span data-ttu-id="822d6-128">ICLRRuntimeInfo 인터페이스</span><span class="sxs-lookup"><span data-stu-id="822d6-128">ICLRRuntimeInfo Interface</span></span>](iclrruntimeinfo-interface.md)
- [<span data-ttu-id="822d6-129">호스팅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="822d6-129">Hosting Interfaces</span></span>](hosting-interfaces.md)
- [<span data-ttu-id="822d6-130">호스팅</span><span class="sxs-lookup"><span data-stu-id="822d6-130">Hosting</span></span>](index.md)
