---
title: ICLRDataTarget::GetCurrentThreadID 메서드
ms.date: 03/30/2017
api_name:
- ICLRDataTarget.GetCurrentThreadID
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICLRDataTarget::GetCurrentThreadID
helpviewer_keywords:
- GetCurrentThreadID method, ICLRDataTarget interface [.NET Framework debugging]
- ICLRDataTarget::GetCurrentThreadID method [.NET Framework debugging]
ms.assetid: dc9a0a6c-d592-4fb7-86ed-62684da3b0e1
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 9687f6139d67a2387091367c2c72167e03be4eee
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59080659"
---
# <a name="iclrdatatargetgetcurrentthreadid-method"></a><span data-ttu-id="eaf4d-102">ICLRDataTarget::GetCurrentThreadID 메서드</span><span class="sxs-lookup"><span data-stu-id="eaf4d-102">ICLRDataTarget::GetCurrentThreadID Method</span></span>
<span data-ttu-id="eaf4d-103">현재 스레드에 대 한 운영 체제 식별자를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="eaf4d-103">Gets the operating system identifier for the current thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="eaf4d-104">구문</span><span class="sxs-lookup"><span data-stu-id="eaf4d-104">Syntax</span></span>  
  
```  
HRESULT GetCurrentThreadID (  
    [out] ULONG32    *threadID  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="eaf4d-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="eaf4d-105">Parameters</span></span>  
 `threadID`  
 <span data-ttu-id="eaf4d-106">[out] 대상 프로세스에 대 한 현재 스레드의 운영 체제 식별자에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="eaf4d-106">[out] A pointer to the operating system identifier of the current thread for the target process.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="eaf4d-107">설명</span><span class="sxs-lookup"><span data-stu-id="eaf4d-107">Remarks</span></span>  
 <span data-ttu-id="eaf4d-108">대상 프로세스에 대 한 현재 스레드가 없는 경우는 `GetCurrentThreadID` 메서드가 실패할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eaf4d-108">If there is no current thread for the target process, the `GetCurrentThreadID` method may fail.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="eaf4d-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="eaf4d-109">Requirements</span></span>  
 <span data-ttu-id="eaf4d-110">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="eaf4d-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="eaf4d-111">**헤더:** ClrData.idl, ClrData.h</span><span class="sxs-lookup"><span data-stu-id="eaf4d-111">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="eaf4d-112">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="eaf4d-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="eaf4d-113">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="eaf4d-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eaf4d-114">참고자료</span><span class="sxs-lookup"><span data-stu-id="eaf4d-114">See also</span></span>

- [<span data-ttu-id="eaf4d-115">ICLRDataTarget 인터페이스</span><span class="sxs-lookup"><span data-stu-id="eaf4d-115">ICLRDataTarget Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-interface.md)
