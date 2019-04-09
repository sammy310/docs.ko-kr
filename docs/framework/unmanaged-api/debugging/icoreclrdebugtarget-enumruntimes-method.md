---
title: ICoreClrDebugTarget::EnumRuntimes 메서드
ms.date: 03/30/2017
api_name:
- ICoreClrDebugTarget.EnumRuntimes
api_location:
- mscordbi_macx86.dll
api_type:
- COM
f1_keywords:
- ICoreClrDebugTarget::EnumRuntimes
helpviewer_keywords:
- remote debugging API [Silverlight]
- ICorClrDebugTarget::EnumRuntimes method [Silverlight debugging]
- EnumRuntimes method, ICoreClrDebugTarget interface [Silverlight debugging]
- Silverlight, remote debugging
ms.assetid: 316df866-442d-40cc-b049-45e8adcb65d1
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: afb31646d21ec7e15f79601f5fe83ea6ce44fa90
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59134682"
---
# <a name="icoreclrdebugtargetenumruntimes-method"></a><span data-ttu-id="3026e-102">ICoreClrDebugTarget::EnumRuntimes 메서드</span><span class="sxs-lookup"><span data-stu-id="3026e-102">ICoreClrDebugTarget::EnumRuntimes Method</span></span>
<span data-ttu-id="3026e-103">원격 컴퓨터에서 실행 중인 지정된 프로세스의 CLR(공용 언어 런타임)을 열거합니다.</span><span class="sxs-lookup"><span data-stu-id="3026e-103">Enumerates the common language runtimes (CLRs) in the specified process that is running on a remote computer.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3026e-104">구문</span><span class="sxs-lookup"><span data-stu-id="3026e-104">Syntax</span></span>  
  
```  
HRESULT EnumRuntimes (  
      [in] DWORD       dwInternalProcessID,  
      [out] DWORD*     pcRuntimes,  
      [out] CoreClrDebugRuntimeInfo**    ppRuntimes  
    );  
```  
  
## <a name="parameters"></a><span data-ttu-id="3026e-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="3026e-105">Parameters</span></span>  
 `dwInternalProcessID`  
 <span data-ttu-id="3026e-106">[in] 런타임을 열거하려는 프로세스의 내부 프로세스 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="3026e-106">[in] The internal process ID of the process for which you want to enumerate runtimes.</span></span> <span data-ttu-id="3026e-107">이 됩니다 `m_dwInternalID` 해당 [CoreClrDebugProcInfo](../../../../docs/framework/unmanaged-api/debugging/coreclrdebugprocinfo-structure.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="3026e-107">This will be `m_dwInternalID` from the corresponding [CoreClrDebugProcInfo](../../../../docs/framework/unmanaged-api/debugging/coreclrdebugprocinfo-structure.md).</span></span>  
  
 `pcRuntimes`  
 <span data-ttu-id="3026e-108">[out] `ppRuntimes`에 반환된 런타임 수입니다.</span><span class="sxs-lookup"><span data-stu-id="3026e-108">[out] The number of runtimes returned in `ppRuntimes`.</span></span> <span data-ttu-id="3026e-109">이 값은 0일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3026e-109">This value can be 0 (zero).</span></span>  
  
 `ppRuntimes`  
 <span data-ttu-id="3026e-110">[out] 배열을 [CoreClrDebugRuntimeInfo](../../../../docs/framework/unmanaged-api/debugging/coreclrdebugruntimeinfo-structure.md) 원격 대상 프로세스에 로드 된 런타임을 나타내는 구조입니다.</span><span class="sxs-lookup"><span data-stu-id="3026e-110">[out] An array of [CoreClrDebugRuntimeInfo](../../../../docs/framework/unmanaged-api/debugging/coreclrdebugruntimeinfo-structure.md) structures that represent the runtimes loaded in the remote target process.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="3026e-111">반환 값</span><span class="sxs-lookup"><span data-stu-id="3026e-111">Return Value</span></span>  
 <span data-ttu-id="3026e-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="3026e-112">S_OK</span></span>  
 <span data-ttu-id="3026e-113">명령 실행 성공</span><span class="sxs-lookup"><span data-stu-id="3026e-113">Success.</span></span>  
  
 <span data-ttu-id="3026e-114">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="3026e-114">S_FALSE</span></span>  
 `dwInternalProcessID` <span data-ttu-id="3026e-115">일치 하지 않습니다 컴퓨터에서 실행 되는 모든 프로세스 아마도 프로세스가 종료 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="3026e-115">does not match any process that is running on the computer, probably because the process was terminated.</span></span> `pcRuntimes` <span data-ttu-id="3026e-116">및 `ppRuntimes` null이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3026e-116">and `ppRuntimes` will be null.</span></span>  
  
 <span data-ttu-id="3026e-117">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="3026e-117">E_OUTOFMEMORY</span></span>  
 <span data-ttu-id="3026e-118">`ppRuntimes`에 대해 충분한 메모리를 할당할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="3026e-118">Unable to allocate enough memory for `ppRuntimes`.</span></span>  
  
 <span data-ttu-id="3026e-119">E_FAIL(또는 다른 E_ 반환 코드)</span><span class="sxs-lookup"><span data-stu-id="3026e-119">E_FAIL (or other E_ return codes)</span></span>  
 <span data-ttu-id="3026e-120">기타 실패</span><span class="sxs-lookup"><span data-stu-id="3026e-120">Other failures.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3026e-121">설명</span><span class="sxs-lookup"><span data-stu-id="3026e-121">Remarks</span></span>  
 <span data-ttu-id="3026e-122">이 메서드에 의해 할당 된 메모리를 확보 하기 위해 호출 된 [icoreclrdebugtarget:: Freememory](../../../../docs/framework/unmanaged-api/debugging/icoreclrdebugtarget-freememory-method.md) 메서드.</span><span class="sxs-lookup"><span data-stu-id="3026e-122">To free the memory that was allocated by this method, call the [ICoreClrDebugTarget::FreeMemory](../../../../docs/framework/unmanaged-api/debugging/icoreclrdebugtarget-freememory-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3026e-123">요구 사항</span><span class="sxs-lookup"><span data-stu-id="3026e-123">Requirements</span></span>  
 <span data-ttu-id="3026e-124">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="3026e-124">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3026e-125">**헤더:** CoreClrRemoteDebuggingInterfaces.h</span><span class="sxs-lookup"><span data-stu-id="3026e-125">**Header:** CoreClrRemoteDebuggingInterfaces.h</span></span>  
  
 <span data-ttu-id="3026e-126">**라이브러리:** mscordbi_macx86.dll</span><span class="sxs-lookup"><span data-stu-id="3026e-126">**Library:** mscordbi_macx86.dll</span></span>  
  
 <span data-ttu-id="3026e-127">**.NET framework 버전:** 3.5 SP1</span><span class="sxs-lookup"><span data-stu-id="3026e-127">**.NET Framework Versions:** 3.5 SP1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3026e-128">참고자료</span><span class="sxs-lookup"><span data-stu-id="3026e-128">See also</span></span>

- [<span data-ttu-id="3026e-129">ICoreClrDebugTarget 인터페이스</span><span class="sxs-lookup"><span data-stu-id="3026e-129">ICoreClrDebugTarget Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icoreclrdebugtarget-interface.md)
