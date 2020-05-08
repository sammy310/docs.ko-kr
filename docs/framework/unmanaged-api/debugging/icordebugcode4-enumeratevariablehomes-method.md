---
title: 'ICorDebugCode4:: EnumerateVariableHomes 메서드'
ms.date: 03/30/2017
api_name:
- ICorDebugCode4.EnumerateVariableHomes
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugCode4::EnumerateVariableHomes
helpviewer_keywords:
- EnumerateVariableHomes method [.NET Framework debugging]
- ICorDebugCode4::EnumerateVariableHomes method [.NET Framework debugging]
ms.assetid: 802c01ff-8b80-4733-b6dd-03ab6ff7fa11
topic_type:
- apiref
ms.openlocfilehash: 5f731b1459542c3f5378790b21f2ea576e89ad97
ms.sourcegitcommit: 957c49696eaf048c284ef8f9f8ffeb562357ad95
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/07/2020
ms.locfileid: "82893335"
---
# <a name="icordebugcode4enumeratevariablehomes-method"></a><span data-ttu-id="568aa-102">ICorDebugCode4:: EnumerateVariableHomes 메서드</span><span class="sxs-lookup"><span data-stu-id="568aa-102">ICorDebugCode4::EnumerateVariableHomes Method</span></span>
<span data-ttu-id="568aa-103">함수의 지역 변수 및 인수에 대 한 열거자를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="568aa-103">Gets an enumerator to the local variables and arguments in a function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="568aa-104">구문</span><span class="sxs-lookup"><span data-stu-id="568aa-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumerateVariableHomes(  
    [out] ICorDebugVariableHomeEnum **ppEnum  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="568aa-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="568aa-105">Parameters</span></span>  
 `ppEnum`  
 <span data-ttu-id="568aa-106">함수의 지역 변수 및 인수에 대 한 열거자 인 [ICorDebugVariableHomeEnum](icordebugvariablehomeenum-interface.md) interface 개체의 주소에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="568aa-106">A pointer to the address of an [ICorDebugVariableHomeEnum](icordebugvariablehomeenum-interface.md) interface object that is an enumerator for the local variables and arguments in a function.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="568aa-107">설명</span><span class="sxs-lookup"><span data-stu-id="568aa-107">Remarks</span></span>  
 <span data-ttu-id="568aa-108">[ICorDebugVariableHomeEnum](icordebugvariablehomeenum-interface.md) interface 개체는 [ICorDebugVariableHome](icordebugvariablehome-interface.md) 개체를 열거할 수 있도록 하는 "ICorDebugEnum" 인터페이스에서 파생 된 표준 열거자입니다.</span><span class="sxs-lookup"><span data-stu-id="568aa-108">The [ICorDebugVariableHomeEnum](icordebugvariablehomeenum-interface.md) interface object is a standard enumerator derived from the "ICorDebugEnum" interface that allows you to enumerate [ICorDebugVariableHome](icordebugvariablehome-interface.md) objects.</span></span> <span data-ttu-id="568aa-109">함수의 다른 지점에 다른 홈이 있는 경우 컬렉션은 동일한 슬롯 또는 인수 인덱스에 대해 여러 [ICorDebugVariableHome](icordebugvariablehome-interface.md) 개체를 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="568aa-109">The collection may include multiple [ICorDebugVariableHome](icordebugvariablehome-interface.md) objects for the same slot or      argument index if they have different homes at different points in the      function.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="568aa-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="568aa-110">Requirements</span></span>  
 <span data-ttu-id="568aa-111">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="568aa-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="568aa-112">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="568aa-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="568aa-113">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="568aa-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="568aa-114">**.NET Framework 버전:**[!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="568aa-114">**.NET Framework Versions:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="568aa-115">참조</span><span class="sxs-lookup"><span data-stu-id="568aa-115">See also</span></span>

- [<span data-ttu-id="568aa-116">ICorDebugCode4 인터페이스</span><span class="sxs-lookup"><span data-stu-id="568aa-116">ICorDebugCode4 Interface</span></span>](icordebugcode4-interface.md)
- [<span data-ttu-id="568aa-117">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="568aa-117">Debugging Interfaces</span></span>](debugging-interfaces.md)
