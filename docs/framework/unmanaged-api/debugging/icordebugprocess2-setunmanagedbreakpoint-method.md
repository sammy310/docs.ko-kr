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
ms.openlocfilehash: 6b9396d03892f29e3698af90856d0c0023dc628a
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/12/2020
ms.locfileid: "83213467"
---
# <a name="icordebugprocess2setunmanagedbreakpoint-method"></a><span data-ttu-id="91521-102">ICorDebugProcess2::SetUnmanagedBreakpoint 메서드</span><span class="sxs-lookup"><span data-stu-id="91521-102">ICorDebugProcess2::SetUnmanagedBreakpoint Method</span></span>
<span data-ttu-id="91521-103">지정 된 네이티브 이미지 오프셋에서 관리 되지 않는 중단점을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="91521-103">Sets an unmanaged breakpoint at the specified native image offset.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="91521-104">구문</span><span class="sxs-lookup"><span data-stu-id="91521-104">Syntax</span></span>  
  
```cpp  
HRESULT SetUnmanagedBreakpoint (  
    [in]  CORDB_ADDRESS    address,  
    [in]  ULONG32          bufsize,  
    [out, size_is(bufsize), length_is(*bufLen)]
        BYTE               buffer[],  
    [out] ULONG32          *bufLen  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="91521-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="91521-105">Parameters</span></span>  
 `address`  
 <span data-ttu-id="91521-106">진행 `CORDB_ADDRESS`네이티브 이미지 오프셋을 지정 하는 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="91521-106">[in] A `CORDB_ADDRESS` object that specifies the native image offset.</span></span>  
  
 `bufsize`  
 <span data-ttu-id="91521-107">진행 배열의 크기 (바이트) `buffer` 입니다.</span><span class="sxs-lookup"><span data-stu-id="91521-107">[in] The size, in bytes, of the `buffer` array.</span></span>  
  
 `buffer`  
 <span data-ttu-id="91521-108">제한이 중단점으로 대체 되는 opcode를 포함 하는 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="91521-108">[out] An array that contains the opcode that is replaced by the breakpoint.</span></span>  
  
 `bufLen`  
 <span data-ttu-id="91521-109">제한이 배열에서 반환 된 바이트 수에 대 한 포인터 `buffer` 입니다.</span><span class="sxs-lookup"><span data-stu-id="91521-109">[out] A pointer to the number of bytes returned in the `buffer` array.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="91521-110">설명</span><span class="sxs-lookup"><span data-stu-id="91521-110">Remarks</span></span>  
 <span data-ttu-id="91521-111">네이티브 이미지 오프셋이 CLR (공용 언어 런타임) 내에 있는 경우 중단점은 무시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="91521-111">If the native image offset is within the common language runtime (CLR), the breakpoint will be ignored.</span></span> <span data-ttu-id="91521-112">이렇게 하면 디버거에서 중단점이 설정 된 경우 CLR에서 대역 외 중단점 디스패치를 방지할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="91521-112">This allows the CLR to avoid dispatching an out-of-band breakpoint, when the breakpoint is set by the debugger.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="91521-113">요구 사항</span><span class="sxs-lookup"><span data-stu-id="91521-113">Requirements</span></span>  
 <span data-ttu-id="91521-114">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="91521-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="91521-115">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="91521-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="91521-116">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="91521-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="91521-117">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="91521-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
