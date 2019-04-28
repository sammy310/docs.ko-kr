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
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61698293"
---
# <a name="iclrdatatargetgetcurrentthreadid-method"></a><span data-ttu-id="12e02-102">ICLRDataTarget::GetCurrentThreadID 메서드</span><span class="sxs-lookup"><span data-stu-id="12e02-102">ICLRDataTarget::GetCurrentThreadID Method</span></span>
<span data-ttu-id="12e02-103">현재 스레드에 대 한 운영 체제 식별자를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="12e02-103">Gets the operating system identifier for the current thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="12e02-104">구문</span><span class="sxs-lookup"><span data-stu-id="12e02-104">Syntax</span></span>  
  
```  
HRESULT GetCurrentThreadID (  
    [out] ULONG32    *threadID  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="12e02-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="12e02-105">Parameters</span></span>  
 `threadID`  
 <span data-ttu-id="12e02-106">[out] 대상 프로세스에 대 한 현재 스레드의 운영 체제 식별자에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="12e02-106">[out] A pointer to the operating system identifier of the current thread for the target process.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="12e02-107">설명</span><span class="sxs-lookup"><span data-stu-id="12e02-107">Remarks</span></span>  
 <span data-ttu-id="12e02-108">대상 프로세스에 대 한 현재 스레드가 없는 경우는 `GetCurrentThreadID` 메서드가 실패할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="12e02-108">If there is no current thread for the target process, the `GetCurrentThreadID` method may fail.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="12e02-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="12e02-109">Requirements</span></span>  
 <span data-ttu-id="12e02-110">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="12e02-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="12e02-111">**헤더:** ClrData.idl, ClrData.h</span><span class="sxs-lookup"><span data-stu-id="12e02-111">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="12e02-112">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="12e02-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="12e02-113">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="12e02-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="12e02-114">참고자료</span><span class="sxs-lookup"><span data-stu-id="12e02-114">See also</span></span>

- [<span data-ttu-id="12e02-115">ICLRDataTarget 인터페이스</span><span class="sxs-lookup"><span data-stu-id="12e02-115">ICLRDataTarget Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-interface.md)
