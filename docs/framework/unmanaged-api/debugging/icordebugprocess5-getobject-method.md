---
title: ICorDebugProcess5::GetObject 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugProcess5.GetObject
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess5::GetObject
helpviewer_keywords:
- GetObject method, ICorDebugProcess5 interface [.NET Framework debugging]
- ICorDebugProcess5::GetObject method [.NET Framework debugging]
ms.assetid: c8111502-5a20-447f-9dc2-76e8acd7ed5a
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2ec3dc37984228565b4a3fcc560d3857a1c1e46d
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/10/2019
ms.locfileid: "67767336"
---
# <a name="icordebugprocess5getobject-method"></a><span data-ttu-id="9fa17-102">ICorDebugProcess5::GetObject 메서드</span><span class="sxs-lookup"><span data-stu-id="9fa17-102">ICorDebugProcess5::GetObject Method</span></span>
<span data-ttu-id="9fa17-103">"ICorDebugObjectValue" 개체를 개체 주소를 변환합니다.</span><span class="sxs-lookup"><span data-stu-id="9fa17-103">Converts an object address to an "ICorDebugObjectValue" object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9fa17-104">구문</span><span class="sxs-lookup"><span data-stu-id="9fa17-104">Syntax</span></span>  
  
```cpp  
HRESULT GetObject(  
    [in] CORDB_ADDRESS addr,   
    [out] ICorDebugObjectValue **ppObject  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9fa17-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="9fa17-105">Parameters</span></span>  
 `addr`  
 <span data-ttu-id="9fa17-106">[in] 개체 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="9fa17-106">[in] The object address.</span></span>  
  
 `ppObject`  
 <span data-ttu-id="9fa17-107">[out] "ICorDebugObjectValue" 개체의 주소에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="9fa17-107">[out] A pointer to the address of an  "ICorDebugObjectValue" object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9fa17-108">설명</span><span class="sxs-lookup"><span data-stu-id="9fa17-108">Remarks</span></span>  
 <span data-ttu-id="9fa17-109">하는 경우 `addr` 유효한 관리 되는 개체를 가리키지 합니다 `GetObject` 메서드가 반환 되는 `E_FAIL`합니다.</span><span class="sxs-lookup"><span data-stu-id="9fa17-109">If `addr` does not point to a valid managed object, the `GetObject` method returns `E_FAIL`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9fa17-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="9fa17-110">Requirements</span></span>  
 <span data-ttu-id="9fa17-111">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="9fa17-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9fa17-112">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="9fa17-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="9fa17-113">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9fa17-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9fa17-114">**.NET Framework 버전:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9fa17-114">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9fa17-115">참고자료</span><span class="sxs-lookup"><span data-stu-id="9fa17-115">See also</span></span>

- [<span data-ttu-id="9fa17-116">ICorDebugProcess5 인터페이스</span><span class="sxs-lookup"><span data-stu-id="9fa17-116">ICorDebugProcess5 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-interface.md)
- [<span data-ttu-id="9fa17-117">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="9fa17-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
