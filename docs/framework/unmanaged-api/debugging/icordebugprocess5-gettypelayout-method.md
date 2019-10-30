---
title: ICorDebugProcess5::GetTypeLayout 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugProcess5.GetTypeLayout
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess5::GetTypeLayout
helpviewer_keywords:
- ICorDebugProcess5::GetTypeLayout method [.NET Framework debugging]
- GetTypeLayout method, ICorDebugProcess5 interface [.NET Framework debugging]
ms.assetid: bd62f5d1-e874-41f1-81e5-a29a7572c15d
topic_type:
- apiref
ms.openlocfilehash: a348c3b2ad33a5d68b1bc46e9a284f2d2a9c7304
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73121293"
---
# <a name="icordebugprocess5gettypelayout-method"></a><span data-ttu-id="f3b5f-102">ICorDebugProcess5::GetTypeLayout 메서드</span><span class="sxs-lookup"><span data-stu-id="f3b5f-102">ICorDebugProcess5::GetTypeLayout Method</span></span>
<span data-ttu-id="f3b5f-103">형식 식별자를 기반으로 메모리에 있는 개체의 레이아웃에 대 한 정보를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="f3b5f-103">Gets information about the layout of an object in memory based on its type identifier.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f3b5f-104">구문</span><span class="sxs-lookup"><span data-stu-id="f3b5f-104">Syntax</span></span>  
  
```cpp  
HRESULT GetTypeLayout(    [in] COR_TYPEID id,     [out] COR_TYPE_LAYOUT *pLayout);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f3b5f-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="f3b5f-105">Parameters</span></span>  
 `id`  
 <span data-ttu-id="f3b5f-106">진행 레이아웃을 원하는 형식을 지정 하는 [COR_TYPEID](../../../../docs/framework/unmanaged-api/debugging/cor-typeid-structure.md) 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="f3b5f-106">[in] A [COR_TYPEID](../../../../docs/framework/unmanaged-api/debugging/cor-typeid-structure.md) token that specifies the type whose layout is desired.</span></span>  
  
 `pLayout`  
 <span data-ttu-id="f3b5f-107">제한이 메모리에 있는 개체의 레이아웃에 대 한 정보를 포함 하는 [COR_TYPE_LAYOUT](../../../../docs/framework/unmanaged-api/debugging/cor-type-layout-structure.md) 구조체에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="f3b5f-107">[out] A pointer to a [COR_TYPE_LAYOUT](../../../../docs/framework/unmanaged-api/debugging/cor-type-layout-structure.md) structure that contains information about the layout of the object in memory.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f3b5f-108">주의</span><span class="sxs-lookup"><span data-stu-id="f3b5f-108">Remarks</span></span>  
 <span data-ttu-id="f3b5f-109">`ICorDebugProcess5::GetTypeLayout` 메서드는 다양 한 [ICorDebugProcess5](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-interface.md) 메서드에 의해 반환 되는 [COR_TYPEID](../../../../docs/framework/unmanaged-api/debugging/cor-typeid-structure.md)을 기반으로 하는 개체에 대 한 정보를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="f3b5f-109">The `ICorDebugProcess5::GetTypeLayout` method provides information about an object based on its [COR_TYPEID](../../../../docs/framework/unmanaged-api/debugging/cor-typeid-structure.md), which is returned by a number of other [ICorDebugProcess5](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-interface.md) methods.</span></span> <span data-ttu-id="f3b5f-110">이 정보는 메서드에 의해 채워지는 [COR_TYPE_LAYOUT](../../../../docs/framework/unmanaged-api/debugging/cor-type-layout-structure.md) 구조체에서 제공 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f3b5f-110">The information is provided by a [COR_TYPE_LAYOUT](../../../../docs/framework/unmanaged-api/debugging/cor-type-layout-structure.md) structure that is populated by the method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f3b5f-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="f3b5f-111">Requirements</span></span>  
 <span data-ttu-id="f3b5f-112">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f3b5f-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f3b5f-113">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="f3b5f-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f3b5f-114">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f3b5f-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f3b5f-115">**.NET Framework 버전:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f3b5f-115">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f3b5f-116">참조</span><span class="sxs-lookup"><span data-stu-id="f3b5f-116">See also</span></span>

- [<span data-ttu-id="f3b5f-117">COR_TYPE_LAYOUT 구조체</span><span class="sxs-lookup"><span data-stu-id="f3b5f-117">COR_TYPE_LAYOUT Structure</span></span>](../../../../docs/framework/unmanaged-api/debugging/cor-type-layout-structure.md)
- [<span data-ttu-id="f3b5f-118">ICorDebugProcess5 인터페이스</span><span class="sxs-lookup"><span data-stu-id="f3b5f-118">ICorDebugProcess5 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-interface.md)
- [<span data-ttu-id="f3b5f-119">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="f3b5f-119">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
