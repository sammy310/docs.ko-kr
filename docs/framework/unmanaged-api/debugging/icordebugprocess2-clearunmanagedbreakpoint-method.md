---
title: ICorDebugProcess2::ClearUnmanagedBreakpoint 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugProcess2.ClearUnmanagedBreakpoint
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess2::ClearUnmanagedBreakpoint
helpviewer_keywords:
- ClearUnmanagedBreakpoint method [.NET Framework debugging]
- ICorDebugProcess2::ClearUnmanagedBreakpoint method [.NET Framework debugging]
ms.assetid: 12ed0fff-7f0e-4d7a-bb70-b3376371f36c
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 9fb566ff2e5e2b0bcb096cead243ed65a904a914
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/10/2019
ms.locfileid: "67736982"
---
# <a name="icordebugprocess2clearunmanagedbreakpoint-method"></a><span data-ttu-id="6e7e0-102">ICorDebugProcess2::ClearUnmanagedBreakpoint 메서드</span><span class="sxs-lookup"><span data-stu-id="6e7e0-102">ICorDebugProcess2::ClearUnmanagedBreakpoint Method</span></span>
<span data-ttu-id="6e7e0-103">제거 이전에 설정한 중단점이 지정된 된 주소에서 합니다.</span><span class="sxs-lookup"><span data-stu-id="6e7e0-103">Removes a previously set breakpoint at the given address.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6e7e0-104">구문</span><span class="sxs-lookup"><span data-stu-id="6e7e0-104">Syntax</span></span>  
  
```cpp  
HRESULT ClearUnmanagedBreakpoint (  
    [in] CORDB_ADDRESS   address  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6e7e0-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="6e7e0-105">Parameters</span></span>  
 `address`  
 <span data-ttu-id="6e7e0-106">[in] `CORDB_ADDRESS` 중단점을 설정한 주소를 지정 하는 값입니다.</span><span class="sxs-lookup"><span data-stu-id="6e7e0-106">[in] A `CORDB_ADDRESS` value that specifies the address at which the breakpoint was set.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6e7e0-107">설명</span><span class="sxs-lookup"><span data-stu-id="6e7e0-107">Remarks</span></span>  
 <span data-ttu-id="6e7e0-108">지정 된 중단점은 이전에 설정한 이전 호출에 의해 [ICorDebugProcess2::SetUnmanagedBreakpoint](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess2-setunmanagedbreakpoint-method.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="6e7e0-108">The specified breakpoint would have been previously set by an earlier call to [ICorDebugProcess2::SetUnmanagedBreakpoint](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess2-setunmanagedbreakpoint-method.md).</span></span>  
  
 <span data-ttu-id="6e7e0-109">`ClearUnmanagedBreakpoint` 디버깅 중인 프로세스에서 실행 되는 동안에 메서드를 호출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6e7e0-109">The `ClearUnmanagedBreakpoint` method can be called while the process being debugged is running.</span></span>  
  
 <span data-ttu-id="6e7e0-110">`ClearUnmanagedBreakpoint` 메서드가 디버거가 연결 되어 있는 관리 되는 전용 모드에서 또는 지정된 된 주소에서 중단점이 없는 경우 오류 코드를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="6e7e0-110">The `ClearUnmanagedBreakpoint` method returns a failure code if the debugger is attached in managed-only mode or if no breakpoint exists at the specified address.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6e7e0-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="6e7e0-111">Requirements</span></span>  
 <span data-ttu-id="6e7e0-112">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="6e7e0-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6e7e0-113">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="6e7e0-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="6e7e0-114">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6e7e0-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6e7e0-115">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6e7e0-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
