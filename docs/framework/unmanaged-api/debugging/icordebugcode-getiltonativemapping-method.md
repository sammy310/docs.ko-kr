---
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
ms.openlocfilehash: 3de85626be6ae8e4769ac261f4de1479461417ec
ms.sourcegitcommit: 957c49696eaf048c284ef8f9f8ffeb562357ad95
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/07/2020
ms.locfileid: "82893535"
---
# <a name="icordebugcodegetiltonativemapping-method"></a><span data-ttu-id="2f82f-102">ICorDebugCode::GetILToNativeMapping 메서드</span><span class="sxs-lookup"><span data-stu-id="2f82f-102">ICorDebugCode::GetILToNativeMapping Method</span></span>
<span data-ttu-id="2f82f-103">MSIL (Microsoft 중간 언어) 오프셋에서 네이티브 오프셋으로의 매핑을 나타내는 "COR_DEBUG_IL_TO_NATIVE_MAP" 인스턴스의 배열을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="2f82f-103">Gets an array of "COR_DEBUG_IL_TO_NATIVE_MAP" instances that represent mappings from Microsoft intermediate language (MSIL) offsets to native offsets.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2f82f-104">구문</span><span class="sxs-lookup"><span data-stu-id="2f82f-104">Syntax</span></span>  
  
```cpp  
HRESULT GetILToNativeMapping (  
    [in]  ULONG32    cMap,  
    [out] ULONG32    *pcMap,  
    [out, size_is(cMap), length_is(*pcMap)]  
        COR_DEBUG_IL_TO_NATIVE_MAP map[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2f82f-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="2f82f-105">Parameters</span></span>  
 `cMap`  
 <span data-ttu-id="2f82f-106">[in] `map` 배열의 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="2f82f-106">[in] The size of the `map` array.</span></span>  
  
 `pcMap`  
 <span data-ttu-id="2f82f-107">제한이 `map` 배열에 반환 된 실제 요소 수에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="2f82f-107">[out] A pointer to the actual number of elements returned in the `map` array.</span></span>  
  
 `map`  
 <span data-ttu-id="2f82f-108">제한이 각각 MSIL 오프셋 `COR_DEBUG_IL_TO_NATIVE_MAP` 에서 네이티브 오프셋으로의 매핑을 나타내는 구조체의 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="2f82f-108">[out] An array of `COR_DEBUG_IL_TO_NATIVE_MAP` structures, each of which represents a mapping from an MSIL offset to a native offset.</span></span>  
  
 <span data-ttu-id="2f82f-109">반환 되는 요소의 배열에 대 한 순서는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="2f82f-109">There is no ordering to the array of elements returned.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2f82f-110">설명</span><span class="sxs-lookup"><span data-stu-id="2f82f-110">Remarks</span></span>  
 <span data-ttu-id="2f82f-111">메서드 `GetILToNativeMapping` 는이 "ICorDebugCode" 인스턴스가 MSIL 코드에서 JIT (just-in-time) 컴파일된 네이티브 코드를 나타내는 경우에만 의미 있는 결과를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="2f82f-111">The `GetILToNativeMapping` method returns meaningful results only if this "ICorDebugCode" instance represents native code that was just-in-time (JIT) compiled from MSIL code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2f82f-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="2f82f-112">Requirements</span></span>  
 <span data-ttu-id="2f82f-113">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="2f82f-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2f82f-114">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="2f82f-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="2f82f-115">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2f82f-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2f82f-116">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2f82f-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2f82f-117">참조</span><span class="sxs-lookup"><span data-stu-id="2f82f-117">See also</span></span>

- [<span data-ttu-id="2f82f-118">ICorDebugCode 인터페이스</span><span class="sxs-lookup"><span data-stu-id="2f82f-118">ICorDebugCode Interface</span></span>](icordebugcode-interface1.md)
