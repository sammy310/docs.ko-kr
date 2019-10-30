---
title: ICorDebugType::GetFirstTypeParameter 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugType.GetFirstTypeParameter
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugType::GetFirstTypeParameter
helpviewer_keywords:
- ICorDebugType::GetFirstTypeParameter method [.NET Framework debugging]
- GetFirstTypeParameter method [.NET Framework debugging]
ms.assetid: 35bb594f-af6a-4349-83fe-e98702674e03
topic_type:
- apiref
ms.openlocfilehash: 4dbc042143e68dc962eb21b2bf741cbaefc1977e
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73122348"
---
# <a name="icordebugtypegetfirsttypeparameter-method"></a><span data-ttu-id="8efb7-102">ICorDebugType::GetFirstTypeParameter 메서드</span><span class="sxs-lookup"><span data-stu-id="8efb7-102">ICorDebugType::GetFirstTypeParameter Method</span></span>
<span data-ttu-id="8efb7-103">이 `ICorDebugType`나타내는 형식의 첫 번째 <xref:System.Type> 매개 변수를 나타내는 ICorDebugType에 대 한 인터페이스 포인터를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="8efb7-103">Gets an interface pointer to an ICorDebugType that represents the first <xref:System.Type> parameter of the type represented by this `ICorDebugType`.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8efb7-104">구문</span><span class="sxs-lookup"><span data-stu-id="8efb7-104">Syntax</span></span>  
  
```cpp  
HRESULT GetFirstTypeParameter (  
    [out] ICorDebugType   **value  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8efb7-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="8efb7-105">Parameters</span></span>  
 `value`  
 <span data-ttu-id="8efb7-106">제한이 첫 번째 매개 변수를 나타내는 `ICorDebugType` 개체의 주소에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="8efb7-106">[out] A pointer to the address of an `ICorDebugType` object that represents the first parameter.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8efb7-107">주의</span><span class="sxs-lookup"><span data-stu-id="8efb7-107">Remarks</span></span>  
 <span data-ttu-id="8efb7-108">형식에 대 한 추가 정보에는 최대 하나의 형식 매개 변수만 포함 하는 경우에 `GetFirstTypeParameter`를 호출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8efb7-108">`GetFirstTypeParameter` can be called in cases where the additional information about the type involves, at most, one type parameter.</span></span> <span data-ttu-id="8efb7-109">특히 ELEMENT_TYPE_ARRAY, ELEMENT_TYPE_SZARRAY, ELEMENT_TYPE_BYREF 또는 ELEMENT_TYPE_PTR 인 경우 [ICorDebugType:: GetType](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-gettype-method.md) 메서드에 표시 된 것과 같은 형식으로 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8efb7-109">In particular, it can be used if the type is an ELEMENT_TYPE_ARRAY, ELEMENT_TYPE_SZARRAY, ELEMENT_TYPE_BYREF, or ELEMENT_TYPE_PTR, as indicated by the [ICorDebugType::GetType](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-gettype-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8efb7-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="8efb7-110">Requirements</span></span>  
 <span data-ttu-id="8efb7-111">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="8efb7-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8efb7-112">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="8efb7-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="8efb7-113">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8efb7-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8efb7-114">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8efb7-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
