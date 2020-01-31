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
ms.openlocfilehash: 540ca78c5548d4fbdd3338671ea02314736f15cd
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/28/2020
ms.locfileid: "76792356"
---
# <a name="icordebugprocess5getobject-method"></a><span data-ttu-id="4481a-102">ICorDebugProcess5::GetObject 메서드</span><span class="sxs-lookup"><span data-stu-id="4481a-102">ICorDebugProcess5::GetObject Method</span></span>
<span data-ttu-id="4481a-103">개체 주소를 "ICorDebugObjectValue" 개체로 변환 합니다.</span><span class="sxs-lookup"><span data-stu-id="4481a-103">Converts an object address to an "ICorDebugObjectValue" object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4481a-104">구문</span><span class="sxs-lookup"><span data-stu-id="4481a-104">Syntax</span></span>  
  
```cpp  
HRESULT GetObject(  
    [in] CORDB_ADDRESS addr,   
    [out] ICorDebugObjectValue **ppObject  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4481a-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="4481a-105">Parameters</span></span>  
 `addr`  
 <span data-ttu-id="4481a-106">진행 개체 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="4481a-106">[in] The object address.</span></span>  
  
 `ppObject`  
 <span data-ttu-id="4481a-107">제한이 "ICorDebugObjectValue" 개체의 주소에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="4481a-107">[out] A pointer to the address of an  "ICorDebugObjectValue" object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4481a-108">주의</span><span class="sxs-lookup"><span data-stu-id="4481a-108">Remarks</span></span>  
 <span data-ttu-id="4481a-109">`addr`에서 유효한 관리 되는 개체를 가리키지 않는 경우 `GetObject` 메서드는 `E_FAIL`를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="4481a-109">If `addr` does not point to a valid managed object, the `GetObject` method returns `E_FAIL`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4481a-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="4481a-110">Requirements</span></span>  
 <span data-ttu-id="4481a-111">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="4481a-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4481a-112">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="4481a-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="4481a-113">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4481a-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4481a-114">**.NET Framework 버전:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4481a-114">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4481a-115">참조</span><span class="sxs-lookup"><span data-stu-id="4481a-115">See also</span></span>

- [<span data-ttu-id="4481a-116">ICorDebugProcess5 인터페이스</span><span class="sxs-lookup"><span data-stu-id="4481a-116">ICorDebugProcess5 Interface</span></span>](icordebugprocess5-interface.md)
- [<span data-ttu-id="4481a-117">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="4481a-117">Debugging Interfaces</span></span>](debugging-interfaces.md)
