---
description: '자세히 알아보기: ICorDebugCode4:: EnumerateVariableHomes 메서드'
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
ms.openlocfilehash: 58f5f9063cd22356efd3a77ece9fb43b6b4c1062
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99710961"
---
# <a name="icordebugcode4enumeratevariablehomes-method"></a><span data-ttu-id="03bf1-103">ICorDebugCode4:: EnumerateVariableHomes 메서드</span><span class="sxs-lookup"><span data-stu-id="03bf1-103">ICorDebugCode4::EnumerateVariableHomes Method</span></span>

<span data-ttu-id="03bf1-104">함수의 지역 변수 및 인수에 대 한 열거자를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="03bf1-104">Gets an enumerator to the local variables and arguments in a function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="03bf1-105">구문</span><span class="sxs-lookup"><span data-stu-id="03bf1-105">Syntax</span></span>  
  
```cpp  
HRESULT EnumerateVariableHomes(  
    [out] ICorDebugVariableHomeEnum **ppEnum  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="03bf1-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="03bf1-106">Parameters</span></span>  

 `ppEnum`  
 <span data-ttu-id="03bf1-107">함수의 지역 변수 및 인수에 대 한 열거자 인 [ICorDebugVariableHomeEnum](icordebugvariablehomeenum-interface.md) interface 개체의 주소에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="03bf1-107">A pointer to the address of an [ICorDebugVariableHomeEnum](icordebugvariablehomeenum-interface.md) interface object that is an enumerator for the local variables and arguments in a function.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="03bf1-108">설명</span><span class="sxs-lookup"><span data-stu-id="03bf1-108">Remarks</span></span>  

 <span data-ttu-id="03bf1-109">[ICorDebugVariableHomeEnum](icordebugvariablehomeenum-interface.md) interface 개체는 [ICorDebugVariableHome](icordebugvariablehome-interface.md) 개체를 열거할 수 있도록 하는 "ICorDebugEnum" 인터페이스에서 파생 된 표준 열거자입니다.</span><span class="sxs-lookup"><span data-stu-id="03bf1-109">The [ICorDebugVariableHomeEnum](icordebugvariablehomeenum-interface.md) interface object is a standard enumerator derived from the "ICorDebugEnum" interface that allows you to enumerate [ICorDebugVariableHome](icordebugvariablehome-interface.md) objects.</span></span> <span data-ttu-id="03bf1-110">함수의 다른 지점에 다른 홈이 있는 경우 컬렉션은 동일한 슬롯 또는 인수 인덱스에 대해 여러 [ICorDebugVariableHome](icordebugvariablehome-interface.md) 개체를 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="03bf1-110">The collection may include multiple [ICorDebugVariableHome](icordebugvariablehome-interface.md) objects for the same slot or      argument index if they have different homes at different points in the      function.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="03bf1-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="03bf1-111">Requirements</span></span>  

 <span data-ttu-id="03bf1-112">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="03bf1-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="03bf1-113">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="03bf1-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="03bf1-114">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="03bf1-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="03bf1-115">**.NET Framework 버전:**[!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="03bf1-115">**.NET Framework Versions:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="03bf1-116">참고 항목</span><span class="sxs-lookup"><span data-stu-id="03bf1-116">See also</span></span>

- [<span data-ttu-id="03bf1-117">ICorDebugCode4 인터페이스</span><span class="sxs-lookup"><span data-stu-id="03bf1-117">ICorDebugCode4 Interface</span></span>](icordebugcode4-interface.md)
- [<span data-ttu-id="03bf1-118">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="03bf1-118">Debugging Interfaces</span></span>](debugging-interfaces.md)
