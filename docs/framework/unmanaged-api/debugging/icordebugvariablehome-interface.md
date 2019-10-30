---
title: ICorDebugVariableHome 인터페이스
ms.date: 03/30/2017
dev_langs:
- cpp
api_name:
- ICorDebugVariableHome
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugVariableHome
helpviewer_keywords:
- ICorDebugVariableHome interface [.NET Framework debugging]
ms.assetid: 76f2bf3b-759f-4eed-bce7-119415b25915
topic_type:
- apiref
ms.openlocfilehash: 306a07450b8ae6d29875ca0cc4679390472e4d1d
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73121038"
---
# <a name="icordebugvariablehome-interface"></a><span data-ttu-id="fd93f-102">ICorDebugVariableHome 인터페이스</span><span class="sxs-lookup"><span data-stu-id="fd93f-102">ICorDebugVariableHome Interface</span></span>
<span data-ttu-id="fd93f-103">함수의 지역 변수 또는 인수를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="fd93f-103">Represents a local variable or argument of a function.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="fd93f-104">메서드</span><span class="sxs-lookup"><span data-stu-id="fd93f-104">Methods</span></span>  
  
|<span data-ttu-id="fd93f-105">메서드</span><span class="sxs-lookup"><span data-stu-id="fd93f-105">Method</span></span>|<span data-ttu-id="fd93f-106">설명</span><span class="sxs-lookup"><span data-stu-id="fd93f-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="fd93f-107">GetArgumentIndex 메서드</span><span class="sxs-lookup"><span data-stu-id="fd93f-107">GetArgumentIndex Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-getargumentindex-method.md)|<span data-ttu-id="fd93f-108">함수 인수의 인덱스를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="fd93f-108">Gets the index of a function argument.</span></span>|  
|[<span data-ttu-id="fd93f-109">GetCode 메서드</span><span class="sxs-lookup"><span data-stu-id="fd93f-109">GetCode Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-getcode-method.md)|<span data-ttu-id="fd93f-110">이 `ICorDebugVariableHome` 개체를 포함 하는 "ICorDebugCode" 인스턴스를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="fd93f-110">Gets the "ICorDebugCode" instance that contains this `ICorDebugVariableHome` object.</span></span>|  
|[<span data-ttu-id="fd93f-111">GetLiveRange 메서드</span><span class="sxs-lookup"><span data-stu-id="fd93f-111">GetLiveRange Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-getliverange-method.md)|<span data-ttu-id="fd93f-112">이 변수가 활성 상태인 기본 범위를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="fd93f-112">Gets the native range over which this variable is live.</span></span>|  
|[<span data-ttu-id="fd93f-113">GetLocationType 메서드</span><span class="sxs-lookup"><span data-stu-id="fd93f-113">GetLocationType Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-getlocationtype-method.md)|<span data-ttu-id="fd93f-114">변수의 네이티브 위치 유형을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="fd93f-114">Gets the type of the variable's native location.</span></span>|  
|[<span data-ttu-id="fd93f-115">GetOffset 메서드</span><span class="sxs-lookup"><span data-stu-id="fd93f-115">GetOffset Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-getoffset-method.md)|<span data-ttu-id="fd93f-116">변수에 대 한 기본 레지스터에서 오프셋을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="fd93f-116">Gets the offset from the base register for a variable.</span></span>|  
|[<span data-ttu-id="fd93f-117">GetRegister 메서드</span><span class="sxs-lookup"><span data-stu-id="fd93f-117">GetRegister Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-getregister-method.md)|<span data-ttu-id="fd93f-118">`VLT_REGISTER`위치 형식의 변수와 `VLT_REGISTER_RELATIVE`위치 형식의 변수에 대 한 기본 레지스터를 포함 하는 레지스터를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="fd93f-118">Gets the register that contains a variable with a location type of `VLT_REGISTER`, and the base register for a variable with a location type of `VLT_REGISTER_RELATIVE`.</span></span>|  
|[<span data-ttu-id="fd93f-119">GetSlotIndex 메서드</span><span class="sxs-lookup"><span data-stu-id="fd93f-119">GetSlotIndex Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-getslotindex-method.md)|<span data-ttu-id="fd93f-120">지역 변수의 관리 되는 슬롯 인덱스를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="fd93f-120">Gets the managed slot-index of a local variable.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="fd93f-121">예제</span><span class="sxs-lookup"><span data-stu-id="fd93f-121">Example</span></span>  
 <span data-ttu-id="fd93f-122">다음 코드 조각에서는 `pCode4`라는 [ICorDebugCode4](../../../../docs/framework/unmanaged-api/debugging/icordebugcode4-interface.md) 개체를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="fd93f-122">The following code fragment uses the [ICorDebugCode4](../../../../docs/framework/unmanaged-api/debugging/icordebugcode4-interface.md) object named `pCode4`.</span></span>  
  
```cpp  
ICorDebugCode4 *pCode4 = NULL;  
pCode->QueryInterface(IID_ICorDebugCode4, &pCode4);  
  
ICorDebugVariableEnum *pVarLocEnum = NULL;  
pCode4->EnumerateVariableHomes(&pVarLocEnum);  
  
// retrieve local variables and arguments  
ULONG celt = 0;  
pVarLocEnum->GetCount(&celt);  
ICorDebugVariableHome **homes = new ICorDebugVariableHome *[celt];  
ULONG celtFetched = 0;  
pVarLocEnum->Next(celt, homes, &celtFetched);  
  
for (int i = 0; i < celtFetched; i++)  
{  
    VariableLocationType locType = VLT_INVALID;  
    homes[i].GetLocationType(&locType);  
    switch (locType)  
    {  
    case VLT_REGISTER:  
        CorDebugRegister register = 0;  
        locals[i].GetRegister(&register);  
        // now we know which register it is in  
        break;  
    case VLT_REGISTER_RELATIVE:  
        CorDebugRegister baseRegister = 0;  
        LONG offset = 0;  
        locals[i].GetRegister(&register);  
        locals[i].GetOffset(&offset);  
        // now we know the register-relative offset  
        break;  
    case VLT_INVALID:  
        // handle case where we can't access the location  
        break;  
    }  
}  
```  
  
## <a name="requirements"></a><span data-ttu-id="fd93f-123">요구 사항</span><span class="sxs-lookup"><span data-stu-id="fd93f-123">Requirements</span></span>  
 <span data-ttu-id="fd93f-124">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="fd93f-124">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fd93f-125">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="fd93f-125">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="fd93f-126">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="fd93f-126">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="fd93f-127">**.NET Framework 버전:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fd93f-127">**.NET Framework Versions:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fd93f-128">참조</span><span class="sxs-lookup"><span data-stu-id="fd93f-128">See also</span></span>

- [<span data-ttu-id="fd93f-129">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="fd93f-129">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="fd93f-130">ICorDebugVariableHomeEnum 인터페이스</span><span class="sxs-lookup"><span data-stu-id="fd93f-130">ICorDebugVariableHomeEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehomeenum-interface.md)
