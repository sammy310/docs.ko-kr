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
ms.openlocfilehash: dcec97bac2aefc8db1f9351f1dacb0f36fc0d2a0
ms.sourcegitcommit: 046a9c22487551360e20ec39fc21eef99820a254
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/14/2020
ms.locfileid: "83396806"
---
# <a name="icordebugvalue2getexacttype-method"></a><span data-ttu-id="cc3c6-102">ICorDebugValue2::GetExactType 메서드</span><span class="sxs-lookup"><span data-stu-id="cc3c6-102">ICorDebugValue2::GetExactType Method</span></span>
<span data-ttu-id="cc3c6-103">이 값의을 나타내는 "ICorDebugType" 개체에 대 한 인터페이스 포인터를 가져옵니다 <xref:System.Type> .</span><span class="sxs-lookup"><span data-stu-id="cc3c6-103">Gets an interface pointer to an "ICorDebugType" object that represents the <xref:System.Type> of this value.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cc3c6-104">구문</span><span class="sxs-lookup"><span data-stu-id="cc3c6-104">Syntax</span></span>  
  
```cpp  
HRESULT GetExactType (  
    [out] ICorDebugType   **ppType  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="cc3c6-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="cc3c6-105">Parameters</span></span>  
 `ppType`  
 <span data-ttu-id="cc3c6-106">제한이 `ICorDebugType` <xref:System.Type> 이 "ICorDebugValue2" 개체가 나타내는 값의을 나타내는 개체의 주소에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="cc3c6-106">[out] A pointer to the address of an `ICorDebugType` object that represents the <xref:System.Type> of the value represented by this "ICorDebugValue2" object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="cc3c6-107">설명</span><span class="sxs-lookup"><span data-stu-id="cc3c6-107">Remarks</span></span>  
 <span data-ttu-id="cc3c6-108">제네릭 인식 메서드는 `GetExactType` 각각 값의 형식에 대 한 정보를 반환 하는 [ICorDebugObjectValue:: getclass](icordebugobjectvalue-getclass-method.md) 와 [ICorDebugValue:: GetType](icordebugvalue-gettype-method.md) 메서드를 모두 대체 합니다.</span><span class="sxs-lookup"><span data-stu-id="cc3c6-108">The generics-aware `GetExactType` method supersedes both the [ICorDebugObjectValue::GetClass](icordebugobjectvalue-getclass-method.md) and the [ICorDebugValue::GetType](icordebugvalue-gettype-method.md) methods, each of which return information about the type of a value.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cc3c6-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="cc3c6-109">Requirements</span></span>  
 <span data-ttu-id="cc3c6-110">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="cc3c6-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cc3c6-111">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="cc3c6-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="cc3c6-112">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="cc3c6-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="cc3c6-113">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cc3c6-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cc3c6-114">참조</span><span class="sxs-lookup"><span data-stu-id="cc3c6-114">See also</span></span>
