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
ms.openlocfilehash: caf6a24207be98be9afb10be2bd027b51405fa3b
ms.sourcegitcommit: 046a9c22487551360e20ec39fc21eef99820a254
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/14/2020
ms.locfileid: "83396546"
---
# <a name="icordebugvariablehome-interface"></a><span data-ttu-id="99908-102">ICorDebugVariableHome 인터페이스</span><span class="sxs-lookup"><span data-stu-id="99908-102">ICorDebugVariableHome Interface</span></span>
<span data-ttu-id="99908-103">함수의 지역 변수 또는 인수를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="99908-103">Represents a local variable or argument of a function.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="99908-104">메서드</span><span class="sxs-lookup"><span data-stu-id="99908-104">Methods</span></span>  
  
|<span data-ttu-id="99908-105">메서드</span><span class="sxs-lookup"><span data-stu-id="99908-105">Method</span></span>|<span data-ttu-id="99908-106">Description</span><span class="sxs-lookup"><span data-stu-id="99908-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="99908-107">GetArgumentIndex 메서드</span><span class="sxs-lookup"><span data-stu-id="99908-107">GetArgumentIndex Method</span></span>](icordebugvariablehome-getargumentindex-method.md)|<span data-ttu-id="99908-108">함수 인수의 인덱스를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="99908-108">Gets the index of a function argument.</span></span>|  
|[<span data-ttu-id="99908-109">GetCode 메서드</span><span class="sxs-lookup"><span data-stu-id="99908-109">GetCode Method</span></span>](icordebugvariablehome-getcode-method.md)|<span data-ttu-id="99908-110">이 개체를 포함 하는 "ICorDebugCode" 인스턴스를 가져옵니다 `ICorDebugVariableHome` .</span><span class="sxs-lookup"><span data-stu-id="99908-110">Gets the "ICorDebugCode" instance that contains this `ICorDebugVariableHome` object.</span></span>|  
|[<span data-ttu-id="99908-111">GetLiveRange 메서드</span><span class="sxs-lookup"><span data-stu-id="99908-111">GetLiveRange Method</span></span>](icordebugvariablehome-getliverange-method.md)|<span data-ttu-id="99908-112">이 변수가 활성 상태인 기본 범위를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="99908-112">Gets the native range over which this variable is live.</span></span>|  
|[<span data-ttu-id="99908-113">GetLocationType 메서드</span><span class="sxs-lookup"><span data-stu-id="99908-113">GetLocationType Method</span></span>](icordebugvariablehome-getlocationtype-method.md)|<span data-ttu-id="99908-114">변수의 네이티브 위치 유형을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="99908-114">Gets the type of the variable's native location.</span></span>|  
|[<span data-ttu-id="99908-115">GetOffset 메서드</span><span class="sxs-lookup"><span data-stu-id="99908-115">GetOffset Method</span></span>](icordebugvariablehome-getoffset-method.md)|<span data-ttu-id="99908-116">변수에 대 한 기본 레지스터에서 오프셋을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="99908-116">Gets the offset from the base register for a variable.</span></span>|  
|[<span data-ttu-id="99908-117">GetRegister 메서드</span><span class="sxs-lookup"><span data-stu-id="99908-117">GetRegister Method</span></span>](icordebugvariablehome-getregister-method.md)|<span data-ttu-id="99908-118">위치 형식이 인 변수가 포함 된 레지스터 `VLT_REGISTER` 와 위치 형식이 인 변수에 대 한 기본 레지스터를 가져옵니다 `VLT_REGISTER_RELATIVE` .</span><span class="sxs-lookup"><span data-stu-id="99908-118">Gets the register that contains a variable with a location type of `VLT_REGISTER`, and the base register for a variable with a location type of `VLT_REGISTER_RELATIVE`.</span></span>|  
|[<span data-ttu-id="99908-119">GetSlotIndex 메서드</span><span class="sxs-lookup"><span data-stu-id="99908-119">GetSlotIndex Method</span></span>](icordebugvariablehome-getslotindex-method.md)|<span data-ttu-id="99908-120">지역 변수의 관리 되는 슬롯 인덱스를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="99908-120">Gets the managed slot-index of a local variable.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="99908-121">예제</span><span class="sxs-lookup"><span data-stu-id="99908-121">Example</span></span>  
 <span data-ttu-id="99908-122">다음 코드 조각에서는 라는 [ICorDebugCode4](icordebugcode4-interface.md) 개체를 사용 합니다 `pCode4` .</span><span class="sxs-lookup"><span data-stu-id="99908-122">The following code fragment uses the [ICorDebugCode4](icordebugcode4-interface.md) object named `pCode4`.</span></span>  
  
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
  
## <a name="requirements"></a><span data-ttu-id="99908-123">요구 사항</span><span class="sxs-lookup"><span data-stu-id="99908-123">Requirements</span></span>  
 <span data-ttu-id="99908-124">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="99908-124">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="99908-125">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="99908-125">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="99908-126">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="99908-126">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="99908-127">**.NET Framework 버전:**[!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="99908-127">**.NET Framework Versions:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="99908-128">참조</span><span class="sxs-lookup"><span data-stu-id="99908-128">See also</span></span>

- [<span data-ttu-id="99908-129">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="99908-129">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="99908-130">ICorDebugVariableHomeEnum 인터페이스</span><span class="sxs-lookup"><span data-stu-id="99908-130">ICorDebugVariableHomeEnum Interface</span></span>](icordebugvariablehomeenum-interface.md)
