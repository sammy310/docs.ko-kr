---
title: ICorDebugMDA::GetFlags 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugMDA.GetFlags
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugMDA::GetFlags
helpviewer_keywords:
- ICorDebugMDA::GetFlags method [.NET Framework debugging]
- GetFlags method [.NET Framework debugging]
ms.assetid: 87ce7c5b-fd82-453e-bf55-c8a32150b183
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 701d578a1d3af941923d68ddc0cb7c97dd0ca8ab
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/10/2019
ms.locfileid: "67761932"
---
# <a name="icordebugmdagetflags-method"></a><span data-ttu-id="55abf-102">ICorDebugMDA::GetFlags 메서드</span><span class="sxs-lookup"><span data-stu-id="55abf-102">ICorDebugMDA::GetFlags Method</span></span>
<span data-ttu-id="55abf-103">연결 된 MDA (관리 디버깅 도우미)으로 표시 된 플래그를 가져옵니다 [ICorDebugMDA](../../../../docs/framework/unmanaged-api/debugging/icordebugmda-interface.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="55abf-103">Gets the flags associated with the managed debugging assistant (MDA) represented by [ICorDebugMDA](../../../../docs/framework/unmanaged-api/debugging/icordebugmda-interface.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="55abf-104">구문</span><span class="sxs-lookup"><span data-stu-id="55abf-104">Syntax</span></span>  
  
```cpp  
HRESULT GetFlags (  
    [in] CorDebugMDAFlags *pFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="55abf-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="55abf-105">Parameters</span></span>  
 `pFlags`  
 <span data-ttu-id="55abf-106">[in] 비트 조합 합니다 [CorDebugMDAFlags](../../../../docs/framework/unmanaged-api/debugging/cordebugmdaflags-enumeration.md) 이 MDA에 대 한 플래그의 설정을 지정 하는 열거형 값입니다.</span><span class="sxs-lookup"><span data-stu-id="55abf-106">[in] A bitwise combination of the [CorDebugMDAFlags](../../../../docs/framework/unmanaged-api/debugging/cordebugmdaflags-enumeration.md) enumeration values that specify the settings of the flags for this MDA.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="55abf-107">요구 사항</span><span class="sxs-lookup"><span data-stu-id="55abf-107">Requirements</span></span>  
 <span data-ttu-id="55abf-108">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="55abf-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="55abf-109">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="55abf-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="55abf-110">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="55abf-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="55abf-111">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="55abf-111">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="55abf-112">참고자료</span><span class="sxs-lookup"><span data-stu-id="55abf-112">See also</span></span>

- [<span data-ttu-id="55abf-113">ICorDebugMDA 인터페이스</span><span class="sxs-lookup"><span data-stu-id="55abf-113">ICorDebugMDA Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmda-interface.md)
- [<span data-ttu-id="55abf-114">관리 디버깅 도우미를 사용하여 오류 진단</span><span class="sxs-lookup"><span data-stu-id="55abf-114">Diagnosing Errors with Managed Debugging Assistants</span></span>](../../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)
