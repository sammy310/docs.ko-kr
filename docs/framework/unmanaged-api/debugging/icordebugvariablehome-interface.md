---
description: '자세히 알아보기: ICorDebugVariableHome 인터페이스'
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
ms.openlocfilehash: a1dcc959ba9aeffc0e511dcd2f5bb15f58445139
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99790635"
---
# <a name="icordebugvariablehome-interface"></a><span data-ttu-id="337aa-103">ICorDebugVariableHome 인터페이스</span><span class="sxs-lookup"><span data-stu-id="337aa-103">ICorDebugVariableHome Interface</span></span>

<span data-ttu-id="337aa-104">함수의 지역 변수 또는 인수를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="337aa-104">Represents a local variable or argument of a function.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="337aa-105">메서드</span><span class="sxs-lookup"><span data-stu-id="337aa-105">Methods</span></span>  
  
|<span data-ttu-id="337aa-106">메서드</span><span class="sxs-lookup"><span data-stu-id="337aa-106">Method</span></span>|<span data-ttu-id="337aa-107">설명</span><span class="sxs-lookup"><span data-stu-id="337aa-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="337aa-108">GetArgumentIndex 메서드</span><span class="sxs-lookup"><span data-stu-id="337aa-108">GetArgumentIndex Method</span></span>](icordebugvariablehome-getargumentindex-method.md)|<span data-ttu-id="337aa-109">함수 인수의 인덱스를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="337aa-109">Gets the index of a function argument.</span></span>|  
|[<span data-ttu-id="337aa-110">GetCode 메서드</span><span class="sxs-lookup"><span data-stu-id="337aa-110">GetCode Method</span></span>](icordebugvariablehome-getcode-method.md)|<span data-ttu-id="337aa-111">이 개체를 포함 하는 "ICorDebugCode" 인스턴스를 가져옵니다 `ICorDebugVariableHome` .</span><span class="sxs-lookup"><span data-stu-id="337aa-111">Gets the "ICorDebugCode" instance that contains this `ICorDebugVariableHome` object.</span></span>|  
|[<span data-ttu-id="337aa-112">GetLiveRange 메서드</span><span class="sxs-lookup"><span data-stu-id="337aa-112">GetLiveRange Method</span></span>](icordebugvariablehome-getliverange-method.md)|<span data-ttu-id="337aa-113">이 변수가 활성 상태인 기본 범위를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="337aa-113">Gets the native range over which this variable is live.</span></span>|  
|[<span data-ttu-id="337aa-114">GetLocationType 메서드</span><span class="sxs-lookup"><span data-stu-id="337aa-114">GetLocationType Method</span></span>](icordebugvariablehome-getlocationtype-method.md)|<span data-ttu-id="337aa-115">변수의 네이티브 위치 유형을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="337aa-115">Gets the type of the variable's native location.</span></span>|  
|[<span data-ttu-id="337aa-116">GetOffset 메서드</span><span class="sxs-lookup"><span data-stu-id="337aa-116">GetOffset Method</span></span>](icordebugvariablehome-getoffset-method.md)|<span data-ttu-id="337aa-117">변수에 대 한 기본 레지스터에서 오프셋을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="337aa-117">Gets the offset from the base register for a variable.</span></span>|  
|[<span data-ttu-id="337aa-118">GetRegister 메서드</span><span class="sxs-lookup"><span data-stu-id="337aa-118">GetRegister Method</span></span>](icordebugvariablehome-getregister-method.md)|<span data-ttu-id="337aa-119">위치 형식이 인 변수가 포함 된 레지스터 `VLT_REGISTER` 와 위치 형식이 인 변수에 대 한 기본 레지스터를 가져옵니다 `VLT_REGISTER_RELATIVE` .</span><span class="sxs-lookup"><span data-stu-id="337aa-119">Gets the register that contains a variable with a location type of `VLT_REGISTER`, and the base register for a variable with a location type of `VLT_REGISTER_RELATIVE`.</span></span>|  
|[<span data-ttu-id="337aa-120">GetSlotIndex 메서드</span><span class="sxs-lookup"><span data-stu-id="337aa-120">GetSlotIndex Method</span></span>](icordebugvariablehome-getslotindex-method.md)|<span data-ttu-id="337aa-121">지역 변수의 관리 되는 슬롯 인덱스를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="337aa-121">Gets the managed slot-index of a local variable.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="337aa-122">예제</span><span class="sxs-lookup"><span data-stu-id="337aa-122">Example</span></span>  

 <span data-ttu-id="337aa-123">다음 코드 조각에서는 라는 [ICorDebugCode4](icordebugcode4-interface.md) 개체를 사용 합니다 `pCode4` .</span><span class="sxs-lookup"><span data-stu-id="337aa-123">The following code fragment uses the [ICorDebugCode4](icordebugcode4-interface.md) object named `pCode4`.</span></span>  
  
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
  
## <a name="requirements"></a><span data-ttu-id="337aa-124">요구 사항</span><span class="sxs-lookup"><span data-stu-id="337aa-124">Requirements</span></span>  

 <span data-ttu-id="337aa-125">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="337aa-125">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="337aa-126">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="337aa-126">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="337aa-127">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="337aa-127">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="337aa-128">**.NET Framework 버전:**[!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="337aa-128">**.NET Framework Versions:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="337aa-129">참고 항목</span><span class="sxs-lookup"><span data-stu-id="337aa-129">See also</span></span>

- [<span data-ttu-id="337aa-130">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="337aa-130">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="337aa-131">ICorDebugVariableHomeEnum 인터페이스</span><span class="sxs-lookup"><span data-stu-id="337aa-131">ICorDebugVariableHomeEnum Interface</span></span>](icordebugvariablehomeenum-interface.md)
