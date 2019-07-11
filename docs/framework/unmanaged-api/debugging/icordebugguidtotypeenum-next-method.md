---
title: ICorDebugGuidToTypeEnum::Next 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugGuidToTypeEnum.Next
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugGuidToTypeEnum::Next
helpviewer_keywords:
- ICorDebugGuidToTypeEnum::Next method [.NET Framework debugging]
- Next method, ICorDebugGuidToTypeEnum interface [.NET Framework debugging]
ms.assetid: c9937666-8e18-484d-9fe0-b9ac95199530
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 9f334b4a28b0573fa938c2fda340c0c03175ff18
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/10/2019
ms.locfileid: "67756880"
---
# <a name="icordebugguidtotypeenumnext-method"></a><span data-ttu-id="6eba9-102">ICorDebugGuidToTypeEnum::Next 메서드</span><span class="sxs-lookup"><span data-stu-id="6eba9-102">ICorDebugGuidToTypeEnum::Next Method</span></span>
<span data-ttu-id="6eba9-103">지정 된 개수를 가져옵니다 [CorDebugGuidToTypeMapping](../../../../docs/framework/unmanaged-api/debugging/cordebugguidtotypemapping-structure.md) Guid 형식 정보를 매핑하는 인스턴스.</span><span class="sxs-lookup"><span data-stu-id="6eba9-103">Gets the specified number of [CorDebugGuidToTypeMapping](../../../../docs/framework/unmanaged-api/debugging/cordebugguidtotypemapping-structure.md) instances that map GUIDs to type information.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6eba9-104">구문</span><span class="sxs-lookup"><span data-stu-id="6eba9-104">Syntax</span></span>  
  
```cpp  
HRESULT Next(  
    [in] ULONG celt,  
    [out, size_is(celt), length_is(*pceltFetched] CorDebugGuidToTypeMapping values[  ],  
    [out] ULONG *pceltFetched  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6eba9-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="6eba9-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="6eba9-106">[in] GUID-유형 매핑 개체를 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6eba9-106">[in] The number of GUID-to-type mapping objects to be retrieved.</span></span>  
  
 `values`  
 <span data-ttu-id="6eba9-107">[out] 각각 가리키는 포인터 배열을 [CorDebugGuidToTypeMapping](../../../../docs/framework/unmanaged-api/debugging/cordebugguidtotypemapping-structure.md) 해당 ICorDebugType 개체에는 Windows 런타임 GUID를 매핑하는 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="6eba9-107">[out] An array of pointers, each of which points to a [CorDebugGuidToTypeMapping](../../../../docs/framework/unmanaged-api/debugging/cordebugguidtotypemapping-structure.md) object that maps a Windows Runtime GUID to its corresponding ICorDebugType object.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="6eba9-108">[out] 개수에 대 한 포인터 [CorDebugGuidToTypeMapping](../../../../docs/framework/unmanaged-api/debugging/cordebugguidtotypemapping-structure.md) 개체에 실제로 반환 된 `values`합니다.</span><span class="sxs-lookup"><span data-stu-id="6eba9-108">[out] A pointer to the number of [CorDebugGuidToTypeMapping](../../../../docs/framework/unmanaged-api/debugging/cordebugguidtotypemapping-structure.md) objects actually returned in `values`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6eba9-109">설명</span><span class="sxs-lookup"><span data-stu-id="6eba9-109">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6eba9-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="6eba9-110">Requirements</span></span>  
 <span data-ttu-id="6eba9-111">**플랫폼:** Windows 런타임</span><span class="sxs-lookup"><span data-stu-id="6eba9-111">**Platforms:** Windows Runtime</span></span>  
  
 <span data-ttu-id="6eba9-112">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="6eba9-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="6eba9-113">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6eba9-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6eba9-114">**.NET Framework 버전:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6eba9-114">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6eba9-115">참고자료</span><span class="sxs-lookup"><span data-stu-id="6eba9-115">See also</span></span>

- [<span data-ttu-id="6eba9-116">ICorDebugGuidToTypeEnum 인터페이스</span><span class="sxs-lookup"><span data-stu-id="6eba9-116">ICorDebugGuidToTypeEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugguidtotypeenum-interface.md)
- [<span data-ttu-id="6eba9-117">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="6eba9-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
