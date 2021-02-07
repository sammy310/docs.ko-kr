---
description: '자세히 알아보기: ICorDebugProcess2:: SetUnmanagedBreakpoint 메서드'
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
ms.openlocfilehash: 7989f0fc9908941513b7d099fde81c79cef82c5b
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99746544"
---
# <a name="icordebugprocess2setunmanagedbreakpoint-method"></a><span data-ttu-id="d4ac7-103">ICorDebugProcess2::SetUnmanagedBreakpoint 메서드</span><span class="sxs-lookup"><span data-stu-id="d4ac7-103">ICorDebugProcess2::SetUnmanagedBreakpoint Method</span></span>

<span data-ttu-id="d4ac7-104">지정 된 네이티브 이미지 오프셋에서 관리 되지 않는 중단점을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="d4ac7-104">Sets an unmanaged breakpoint at the specified native image offset.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d4ac7-105">구문</span><span class="sxs-lookup"><span data-stu-id="d4ac7-105">Syntax</span></span>  
  
```cpp  
HRESULT SetUnmanagedBreakpoint (  
    [in]  CORDB_ADDRESS    address,  
    [in]  ULONG32          bufsize,  
    [out, size_is(bufsize), length_is(*bufLen)]
        BYTE               buffer[],  
    [out] ULONG32          *bufLen  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d4ac7-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="d4ac7-106">Parameters</span></span>  

 `address`  
 <span data-ttu-id="d4ac7-107">진행 `CORDB_ADDRESS` 네이티브 이미지 오프셋을 지정 하는 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="d4ac7-107">[in] A `CORDB_ADDRESS` object that specifies the native image offset.</span></span>  
  
 `bufsize`  
 <span data-ttu-id="d4ac7-108">진행 배열의 크기 (바이트) `buffer` 입니다.</span><span class="sxs-lookup"><span data-stu-id="d4ac7-108">[in] The size, in bytes, of the `buffer` array.</span></span>  
  
 `buffer`  
 <span data-ttu-id="d4ac7-109">제한이 중단점으로 대체 되는 opcode를 포함 하는 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="d4ac7-109">[out] An array that contains the opcode that is replaced by the breakpoint.</span></span>  
  
 `bufLen`  
 <span data-ttu-id="d4ac7-110">제한이 배열에서 반환 된 바이트 수에 대 한 포인터 `buffer` 입니다.</span><span class="sxs-lookup"><span data-stu-id="d4ac7-110">[out] A pointer to the number of bytes returned in the `buffer` array.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d4ac7-111">설명</span><span class="sxs-lookup"><span data-stu-id="d4ac7-111">Remarks</span></span>  

 <span data-ttu-id="d4ac7-112">네이티브 이미지 오프셋이 CLR (공용 언어 런타임) 내에 있는 경우 중단점은 무시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d4ac7-112">If the native image offset is within the common language runtime (CLR), the breakpoint will be ignored.</span></span> <span data-ttu-id="d4ac7-113">이렇게 하면 디버거에서 중단점이 설정 된 경우 CLR에서 대역 외 중단점 디스패치를 방지할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d4ac7-113">This allows the CLR to avoid dispatching an out-of-band breakpoint, when the breakpoint is set by the debugger.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d4ac7-114">요구 사항</span><span class="sxs-lookup"><span data-stu-id="d4ac7-114">Requirements</span></span>  

 <span data-ttu-id="d4ac7-115">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d4ac7-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d4ac7-116">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="d4ac7-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="d4ac7-117">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d4ac7-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d4ac7-118">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d4ac7-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
