---
description: '자세히 알아보기: ICorDebugFunctionBreakpoint:: GetOffset 메서드'
title: ICorDebugFunctionBreakpoint::GetOffset 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugFunctionBreakpoint.GetOffset
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugFunctionBreakpoint::GetOffset
helpviewer_keywords:
- ICorDebugFunctionBreakpoint::GetOffset method [.NET Framework debugging]
- GetOffset method, ICorDebugFunctionBreakpoint interface [.NET Framework debugging]
ms.assetid: e619eae4-3ac3-4c37-bba4-55e59989b9cb
topic_type:
- apiref
ms.openlocfilehash: 94238b761e0a42a72037f7d44d5e9609f86ac03b
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99661170"
---
# <a name="icordebugfunctionbreakpointgetoffset-method"></a><span data-ttu-id="2c68f-103">ICorDebugFunctionBreakpoint::GetOffset 메서드</span><span class="sxs-lookup"><span data-stu-id="2c68f-103">ICorDebugFunctionBreakpoint::GetOffset Method</span></span>

<span data-ttu-id="2c68f-104">함수 내에서 중단점의 오프셋을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="2c68f-104">Gets the offset of the breakpoint within the function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2c68f-105">구문</span><span class="sxs-lookup"><span data-stu-id="2c68f-105">Syntax</span></span>  
  
```cpp  
HRESULT GetOffset (  
    [out] ULONG32  *pnOffset  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2c68f-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="2c68f-106">Parameters</span></span>  

 `pnOffset`  
 <span data-ttu-id="2c68f-107">제한이 중단점의 오프셋에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="2c68f-107">[out] A pointer to the offset of the breakpoint.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2c68f-108">요구 사항</span><span class="sxs-lookup"><span data-stu-id="2c68f-108">Requirements</span></span>  

 <span data-ttu-id="2c68f-109">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="2c68f-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2c68f-110">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="2c68f-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="2c68f-111">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2c68f-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2c68f-112">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2c68f-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
