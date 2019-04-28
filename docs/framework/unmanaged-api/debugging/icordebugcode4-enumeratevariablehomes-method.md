---
title: ICorDebugCode4::EnumerateVariableHomes 메서드
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 8a6e4f6e7e3107516476b179b0ed718ca44bb114
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61749953"
---
# <a name="icordebugcode4enumeratevariablehomes-method"></a><span data-ttu-id="fb985-102">ICorDebugCode4::EnumerateVariableHomes 메서드</span><span class="sxs-lookup"><span data-stu-id="fb985-102">ICorDebugCode4::EnumerateVariableHomes Method</span></span>
<span data-ttu-id="fb985-103">함수에서 지역 변수 및 인수를 열거자를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="fb985-103">Gets an enumerator to the local variables and arguments in a function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fb985-104">구문</span><span class="sxs-lookup"><span data-stu-id="fb985-104">Syntax</span></span>  
  
```  
HRESULT EnumerateVariableHomes(  
    [out] ICorDebugVariableHomeEnum **ppEnum  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="fb985-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="fb985-105">Parameters</span></span>  
 `ppEnum`  
 <span data-ttu-id="fb985-106">주소에 대 한 포인터를 [ICorDebugVariableHomeEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehomeenum-interface.md) 인터페이스 개체는 지역 변수 및 함수에 인수에 대 한 열거자입니다.</span><span class="sxs-lookup"><span data-stu-id="fb985-106">A pointer to the address of an [ICorDebugVariableHomeEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehomeenum-interface.md) interface object that is an enumerator for the local variables and arguments in a function.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="fb985-107">설명</span><span class="sxs-lookup"><span data-stu-id="fb985-107">Remarks</span></span>  
 <span data-ttu-id="fb985-108">합니다 [ICorDebugVariableHomeEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehomeenum-interface.md) 인터페이스 개체는 열거할 수 있도록 "ICorDebugEnum" 인터페이스에서 파생 하는 표준 열거자 [ICorDebugVariableHome](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md) 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="fb985-108">The [ICorDebugVariableHomeEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehomeenum-interface.md) interface object is a standard enumerator derived from the "ICorDebugEnum" interface that allows you to enumerate [ICorDebugVariableHome](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md) objects.</span></span> <span data-ttu-id="fb985-109">컬렉션에 여러 포함 될 수 있습니다 [ICorDebugVariableHome](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md) 함수에서 다른 지점에서 다른 집에 있는 경우 동일한 인수 또는 슬롯 인덱스에 대 한 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="fb985-109">The collection may include multiple [ICorDebugVariableHome](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md) objects for the same slot or      argument index if they have different homes at different points in the      function.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fb985-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="fb985-110">Requirements</span></span>  
 <span data-ttu-id="fb985-111">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="fb985-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fb985-112">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="fb985-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="fb985-113">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="fb985-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="fb985-114">**.NET Framework 버전:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fb985-114">**.NET Framework Versions:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fb985-115">참고자료</span><span class="sxs-lookup"><span data-stu-id="fb985-115">See also</span></span>

- [<span data-ttu-id="fb985-116">ICorDebugCode4 인터페이스</span><span class="sxs-lookup"><span data-stu-id="fb985-116">ICorDebugCode4 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcode4-interface.md)
- [<span data-ttu-id="fb985-117">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="fb985-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
