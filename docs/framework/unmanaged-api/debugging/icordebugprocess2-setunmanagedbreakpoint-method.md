---
title: ICorDebugProcess2::SetUnmanagedBreakpoint 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugProcess2.SetUnmanagedBreakpoint
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess2::SetUnmanagedBreakpoint
helpviewer_keywords:
- ICorDebugProcess2::SetUnmanagedBreakpoint method [.NET Framework debugging]
- SetUnmanagedBreakpoint method [.NET Framework debugging]
ms.assetid: 93829d15-d942-4e2d-b7a4-dfc9d7fb96be
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f16a5d1bad80a5aad8573508aab5fbf98c8c2a03
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/10/2019
ms.locfileid: "67736830"
---
# <a name="icordebugprocess2setunmanagedbreakpoint-method"></a><span data-ttu-id="03531-102">ICorDebugProcess2::SetUnmanagedBreakpoint 메서드</span><span class="sxs-lookup"><span data-stu-id="03531-102">ICorDebugProcess2::SetUnmanagedBreakpoint Method</span></span>
<span data-ttu-id="03531-103">지정 된 네이티브 이미지 오프셋을 관리 되지 않는 중단점을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="03531-103">Sets an unmanaged breakpoint at the specified native image offset.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="03531-104">구문</span><span class="sxs-lookup"><span data-stu-id="03531-104">Syntax</span></span>  
  
```cpp  
HRESULT SetUnmanagedBreakpoint (  
    [in]  CORDB_ADDRESS    address,  
    [in]  ULONG32          bufsize,  
    [out, size_is(bufsize), length_is(*bufLen)]   
        BYTE               buffer[],  
    [out] ULONG32          *bufLen  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="03531-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="03531-105">Parameters</span></span>  
 `address`  
 <span data-ttu-id="03531-106">[in] `CORDB_ADDRESS` 네이티브 이미지 오프셋을 나타내는 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="03531-106">[in] A `CORDB_ADDRESS` object that specifies the native image offset.</span></span>  
  
 `bufsize`  
 <span data-ttu-id="03531-107">[in] 크기 (바이트)의는 `buffer` 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="03531-107">[in] The size, in bytes, of the `buffer` array.</span></span>  
  
 `buffer`  
 <span data-ttu-id="03531-108">[out] 중단점에 의해 대체 된 opcode를 포함 하는 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="03531-108">[out] An array that contains the opcode that is replaced by the breakpoint.</span></span>  
  
 `bufLen`  
 <span data-ttu-id="03531-109">[out] 반환 된 바이트 수에 대 한 포인터를 `buffer` 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="03531-109">[out] A pointer to the number of bytes returned in the `buffer` array.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="03531-110">설명</span><span class="sxs-lookup"><span data-stu-id="03531-110">Remarks</span></span>  
 <span data-ttu-id="03531-111">네이티브 이미지 오프셋은 CLR (공용 언어 런타임) 내에 있으면 중단점이 무시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="03531-111">If the native image offset is within the common language runtime (CLR), the breakpoint will be ignored.</span></span> <span data-ttu-id="03531-112">그러면 디버거에서 중단점이 설정 된 경우 대역의 중단점을 디스패치하지 CLR.</span><span class="sxs-lookup"><span data-stu-id="03531-112">This allows the CLR to avoid dispatching an out-of-band breakpoint, when the breakpoint is set by the debugger.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="03531-113">요구 사항</span><span class="sxs-lookup"><span data-stu-id="03531-113">Requirements</span></span>  
 <span data-ttu-id="03531-114">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="03531-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="03531-115">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="03531-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="03531-116">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="03531-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="03531-117">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="03531-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
