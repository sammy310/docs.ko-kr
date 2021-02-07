---
description: '자세히 알아보기: ICorDebugProcess2:: ClearUnmanagedBreakpoint 메서드'
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
ms.openlocfilehash: fba31a479e9bac525109e14c02995e78918d4c17
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99746635"
---
# <a name="icordebugprocess2clearunmanagedbreakpoint-method"></a><span data-ttu-id="18c5d-103">ICorDebugProcess2::ClearUnmanagedBreakpoint 메서드</span><span class="sxs-lookup"><span data-stu-id="18c5d-103">ICorDebugProcess2::ClearUnmanagedBreakpoint Method</span></span>

<span data-ttu-id="18c5d-104">지정 된 주소에서 이전에 설정 된 중단점을 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="18c5d-104">Removes a previously set breakpoint at the given address.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="18c5d-105">구문</span><span class="sxs-lookup"><span data-stu-id="18c5d-105">Syntax</span></span>  
  
```cpp  
HRESULT ClearUnmanagedBreakpoint (  
    [in] CORDB_ADDRESS   address  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="18c5d-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="18c5d-106">Parameters</span></span>  

 `address`  
 <span data-ttu-id="18c5d-107">진행 `CORDB_ADDRESS` 중단점이 설정 된 주소를 지정 하는 값입니다.</span><span class="sxs-lookup"><span data-stu-id="18c5d-107">[in] A `CORDB_ADDRESS` value that specifies the address at which the breakpoint was set.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="18c5d-108">설명</span><span class="sxs-lookup"><span data-stu-id="18c5d-108">Remarks</span></span>  

 <span data-ttu-id="18c5d-109">지정 된 중단점은 이전에 [ICorDebugProcess2:: SetUnmanagedBreakpoint](icordebugprocess2-setunmanagedbreakpoint-method.md)에 대 한 호출에 의해 설정 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="18c5d-109">The specified breakpoint would have been previously set by an earlier call to [ICorDebugProcess2::SetUnmanagedBreakpoint](icordebugprocess2-setunmanagedbreakpoint-method.md).</span></span>  
  
 <span data-ttu-id="18c5d-110">`ClearUnmanagedBreakpoint`디버깅 중인 프로세스가 실행 되는 동안 메서드를 호출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="18c5d-110">The `ClearUnmanagedBreakpoint` method can be called while the process being debugged is running.</span></span>  
  
 <span data-ttu-id="18c5d-111">`ClearUnmanagedBreakpoint`디버거가 관리 전용 모드에서 연결 된 경우 또는 지정 된 주소에 중단점이 없는 경우 메서드는 오류 코드를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="18c5d-111">The `ClearUnmanagedBreakpoint` method returns a failure code if the debugger is attached in managed-only mode or if no breakpoint exists at the specified address.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="18c5d-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="18c5d-112">Requirements</span></span>  

 <span data-ttu-id="18c5d-113">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="18c5d-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="18c5d-114">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="18c5d-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="18c5d-115">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="18c5d-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="18c5d-116">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="18c5d-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
