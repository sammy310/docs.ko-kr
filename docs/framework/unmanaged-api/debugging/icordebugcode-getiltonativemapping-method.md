---
description: '자세히 알아보기: ICorDebugCode:: GetILToNativeMapping 메서드'
title: ICorDebugCode::GetILToNativeMapping 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugCode.GetILToNativeMapping
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugCode::GetILToNativeMapping
helpviewer_keywords:
- GetILToNativeMapping method, ICorDebugCode interface [.NET Framework debugging]
- ICorDebugCode::GetILToNativeMapping method [.NET Framework debugging]
ms.assetid: a8ecd8c8-9627-4356-9c6f-bd05e24637c0
topic_type:
- apiref
ms.openlocfilehash: 808ed450fced8afecc2b637a3b990a894897b350
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99711195"
---
# <a name="icordebugcodegetiltonativemapping-method"></a><span data-ttu-id="ea7af-103">ICorDebugCode::GetILToNativeMapping 메서드</span><span class="sxs-lookup"><span data-stu-id="ea7af-103">ICorDebugCode::GetILToNativeMapping Method</span></span>

<span data-ttu-id="ea7af-104">MSIL (Microsoft 중간 언어) 오프셋에서 네이티브 오프셋으로의 매핑을 나타내는 "COR_DEBUG_IL_TO_NATIVE_MAP" 인스턴스의 배열을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="ea7af-104">Gets an array of "COR_DEBUG_IL_TO_NATIVE_MAP" instances that represent mappings from Microsoft intermediate language (MSIL) offsets to native offsets.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ea7af-105">구문</span><span class="sxs-lookup"><span data-stu-id="ea7af-105">Syntax</span></span>  
  
```cpp  
HRESULT GetILToNativeMapping (  
    [in]  ULONG32    cMap,  
    [out] ULONG32    *pcMap,  
    [out, size_is(cMap), length_is(*pcMap)]  
        COR_DEBUG_IL_TO_NATIVE_MAP map[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ea7af-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="ea7af-106">Parameters</span></span>  

 `cMap`  
 <span data-ttu-id="ea7af-107">[in] `map` 배열의 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="ea7af-107">[in] The size of the `map` array.</span></span>  
  
 `pcMap`  
 <span data-ttu-id="ea7af-108">제한이 배열에 반환 된 실제 요소 수에 대 한 포인터 `map` 입니다.</span><span class="sxs-lookup"><span data-stu-id="ea7af-108">[out] A pointer to the actual number of elements returned in the `map` array.</span></span>  
  
 `map`  
 <span data-ttu-id="ea7af-109">제한이 `COR_DEBUG_IL_TO_NATIVE_MAP` 각각 MSIL 오프셋에서 네이티브 오프셋으로의 매핑을 나타내는 구조체의 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="ea7af-109">[out] An array of `COR_DEBUG_IL_TO_NATIVE_MAP` structures, each of which represents a mapping from an MSIL offset to a native offset.</span></span>  
  
 <span data-ttu-id="ea7af-110">반환 되는 요소의 배열에 대 한 순서는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="ea7af-110">There is no ordering to the array of elements returned.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ea7af-111">설명</span><span class="sxs-lookup"><span data-stu-id="ea7af-111">Remarks</span></span>  

 <span data-ttu-id="ea7af-112">`GetILToNativeMapping`메서드는이 "ICorDebugCode" 인스턴스가 MSIL 코드에서 JIT (just-in-time) 컴파일된 네이티브 코드를 나타내는 경우에만 의미 있는 결과를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="ea7af-112">The `GetILToNativeMapping` method returns meaningful results only if this "ICorDebugCode" instance represents native code that was just-in-time (JIT) compiled from MSIL code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ea7af-113">요구 사항</span><span class="sxs-lookup"><span data-stu-id="ea7af-113">Requirements</span></span>  

 <span data-ttu-id="ea7af-114">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ea7af-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ea7af-115">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="ea7af-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ea7af-116">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ea7af-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ea7af-117">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ea7af-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ea7af-118">참고 항목</span><span class="sxs-lookup"><span data-stu-id="ea7af-118">See also</span></span>

- [<span data-ttu-id="ea7af-119">ICorDebugCode 인터페이스</span><span class="sxs-lookup"><span data-stu-id="ea7af-119">ICorDebugCode Interface</span></span>](icordebugcode-interface1.md)
