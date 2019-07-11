---
title: ICorDebugFrame::GetStackRange 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugFrame.GetStackRange
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugFrame::GetStackRange
helpviewer_keywords:
- GetStackRange method, ICorDebugFrame interface [.NET Framework debugging]
- ICorDebugFrame::GetStackRange method [.NET Framework debugging]
ms.assetid: fab037cb-fda6-40fb-9367-921e435dd5a0
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c9f58e66286f5e3e169507efd2f87ce10e9d323b
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/10/2019
ms.locfileid: "67754862"
---
# <a name="icordebugframegetstackrange-method"></a><span data-ttu-id="a1e76-102">ICorDebugFrame::GetStackRange 메서드</span><span class="sxs-lookup"><span data-stu-id="a1e76-102">ICorDebugFrame::GetStackRange Method</span></span>
<span data-ttu-id="a1e76-103">이 스택 프레임의 절대 주소 범위를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="a1e76-103">Gets the absolute address range of this stack frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a1e76-104">구문</span><span class="sxs-lookup"><span data-stu-id="a1e76-104">Syntax</span></span>  
  
```cpp  
HRESULT GetStackRange (  
    [out] CORDB_ADDRESS      *pStart,   
    [out] CORDB_ADDRESS      *pEnd  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a1e76-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="a1e76-105">Parameters</span></span>  
 `pStart`  
 <span data-ttu-id="a1e76-106">[out] 에 대 한 포인터를 `CORDB_ADDRESS` 이 나타내는 스택 프레임의 시작 주소를 지정 하는 `ICorDebugFrame` 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="a1e76-106">[out] A pointer to a `CORDB_ADDRESS` that specifies the starting address of the stack frame represented by this `ICorDebugFrame` object.</span></span>  
  
 `pEnd`  
 <span data-ttu-id="a1e76-107">[out] 에 대 한 포인터를 `CORDB_ADDRESS` 이 나타내는 스택 프레임의 끝 주소를 지정 하는 `ICorDebugFrame` 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="a1e76-107">[out] A pointer to a `CORDB_ADDRESS` that specifies the ending address of the stack frame represented by this `ICorDebugFrame` object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a1e76-108">설명</span><span class="sxs-lookup"><span data-stu-id="a1e76-108">Remarks</span></span>  
 <span data-ttu-id="a1e76-109">스택의 주소 범위는 여러 디버깅 엔진에서 수집 된 인터리브된 스택 추적 하나로 결합 유용 합니다.</span><span class="sxs-lookup"><span data-stu-id="a1e76-109">The address range of the stack is useful for piecing together interleaved stack traces gathered from multiple debugging engines.</span></span> <span data-ttu-id="a1e76-110">숫자 범위 스택 프레임의 내용 관련 정보를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="a1e76-110">The numeric range provides no information about the contents of the stack frame.</span></span> <span data-ttu-id="a1e76-111">것은 스택 프레임 위치 비교에 대해서만 의미가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a1e76-111">It is meaningful only for comparison of stack frame locations.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a1e76-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="a1e76-112">Requirements</span></span>  
 <span data-ttu-id="a1e76-113">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="a1e76-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a1e76-114">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="a1e76-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a1e76-115">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a1e76-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a1e76-116">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a1e76-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
