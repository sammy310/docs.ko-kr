---
title: ICorDebugValue2::GetExactType 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugValue2.GetExactType
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugValue2::GetExactType
helpviewer_keywords:
- ICorDebugValue2::GetExactType method [.NET Framework debugging]
- GetExactType method [.NET Framework debugging]
ms.assetid: 8e9aae1b-d1b7-4b6e-b577-6faf36dcec85
topic_type:
- apiref
ms.openlocfilehash: 6c5e5d1c9f734e097fc9e871d7a0cffdc9bb9138
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/28/2020
ms.locfileid: "76791132"
---
# <a name="icordebugvalue2getexacttype-method"></a><span data-ttu-id="5ae5b-102">ICorDebugValue2::GetExactType 메서드</span><span class="sxs-lookup"><span data-stu-id="5ae5b-102">ICorDebugValue2::GetExactType Method</span></span>
<span data-ttu-id="5ae5b-103">이 값의 <xref:System.Type>을 나타내는 "ICorDebugType" 개체에 대 한 인터페이스 포인터를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="5ae5b-103">Gets an interface pointer to an "ICorDebugType" object that represents the <xref:System.Type> of this value.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5ae5b-104">구문</span><span class="sxs-lookup"><span data-stu-id="5ae5b-104">Syntax</span></span>  
  
```cpp  
HRESULT GetExactType (  
    [out] ICorDebugType   **ppType  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5ae5b-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="5ae5b-105">Parameters</span></span>  
 `ppType`  
 <span data-ttu-id="5ae5b-106">제한이 이 "ICorDebugValue2" 개체가 나타내는 값의 <xref:System.Type>를 나타내는 `ICorDebugType` 개체의 주소에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="5ae5b-106">[out] A pointer to the address of an `ICorDebugType` object that represents the <xref:System.Type> of the value represented by this "ICorDebugValue2" object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5ae5b-107">주의</span><span class="sxs-lookup"><span data-stu-id="5ae5b-107">Remarks</span></span>  
 <span data-ttu-id="5ae5b-108">제네릭 인식 `GetExactType` 메서드는 각각 값의 형식에 대 한 정보를 반환 하는 [ICorDebugObjectValue:: GetClass](icordebugobjectvalue-getclass-method.md) 와 [ICorDebugValue:: GetType](icordebugvalue-gettype-method.md) 메서드를 모두 대체 합니다.</span><span class="sxs-lookup"><span data-stu-id="5ae5b-108">The generics-aware `GetExactType` method supersedes both the [ICorDebugObjectValue::GetClass](icordebugobjectvalue-getclass-method.md) and the [ICorDebugValue::GetType](icordebugvalue-gettype-method.md) methods, each of which return information about the type of a value.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5ae5b-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="5ae5b-109">Requirements</span></span>  
 <span data-ttu-id="5ae5b-110">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="5ae5b-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5ae5b-111">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="5ae5b-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="5ae5b-112">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5ae5b-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5ae5b-113">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5ae5b-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5ae5b-114">참조</span><span class="sxs-lookup"><span data-stu-id="5ae5b-114">See also</span></span>
