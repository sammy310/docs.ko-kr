---
title: ICorDebugProcess5::GetArrayLayout 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugProcess5.GetArrayLayout
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess5::GetArrayLayout
helpviewer_keywords:
- ICorDebugProcess5::GetArrayLayout method [.NET Framework debugging]
- GetArrayLayout method, ICorDebugProcess5 interface [.NET Framework debugging]
ms.assetid: 9a7393b9-9735-43c6-8616-afb103c432fd
topic_type:
- apiref
ms.openlocfilehash: 5a415c8f3124c08984f8101e1f4dbcae6bf96fbf
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73129619"
---
# <a name="icordebugprocess5getarraylayout-method"></a><span data-ttu-id="fa6d5-102">ICorDebugProcess5::GetArrayLayout 메서드</span><span class="sxs-lookup"><span data-stu-id="fa6d5-102">ICorDebugProcess5::GetArrayLayout Method</span></span>
<span data-ttu-id="fa6d5-103">배열 형식의 레이아웃에 대 한 정보를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="fa6d5-103">Provides information about the layout of array types.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fa6d5-104">구문</span><span class="sxs-lookup"><span data-stu-id="fa6d5-104">Syntax</span></span>  
  
```cpp  
HRESULT GetArrayLayout(    [in] COR_TYPEID id,     [out] COR_ARRAY_LAYOUT *pLayout);  
```  
  
## <a name="parameters"></a><span data-ttu-id="fa6d5-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="fa6d5-105">Parameters</span></span>  
 `id`  
 <span data-ttu-id="fa6d5-106">진행 레이아웃이 필요한 배열을 지정 하는 [COR_TYPEID](../../../../docs/framework/unmanaged-api/debugging/cor-typeid-structure.md) 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="fa6d5-106">[in] A [COR_TYPEID](../../../../docs/framework/unmanaged-api/debugging/cor-typeid-structure.md) token that specifies the array whose layout is desired.</span></span>  
  
 `pLayout`  
 <span data-ttu-id="fa6d5-107">제한이 메모리의 배열 레이아웃에 대 한 정보를 포함 하는 [COR_ARRAY_LAYOUT](../../../../docs/framework/unmanaged-api/debugging/cor-array-layout-structure.md) 구조체에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="fa6d5-107">[out] A pointer to a [COR_ARRAY_LAYOUT](../../../../docs/framework/unmanaged-api/debugging/cor-array-layout-structure.md) structure that contains information about the layout of the array in memory.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="fa6d5-108">주의</span><span class="sxs-lookup"><span data-stu-id="fa6d5-108">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fa6d5-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="fa6d5-109">Requirements</span></span>  
 <span data-ttu-id="fa6d5-110">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="fa6d5-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fa6d5-111">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="fa6d5-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="fa6d5-112">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="fa6d5-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="fa6d5-113">**.NET Framework 버전:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fa6d5-113">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fa6d5-114">참조</span><span class="sxs-lookup"><span data-stu-id="fa6d5-114">See also</span></span>

- [<span data-ttu-id="fa6d5-115">ICorDebugProcess5 인터페이스</span><span class="sxs-lookup"><span data-stu-id="fa6d5-115">ICorDebugProcess5 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-interface.md)
- [<span data-ttu-id="fa6d5-116">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="fa6d5-116">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
