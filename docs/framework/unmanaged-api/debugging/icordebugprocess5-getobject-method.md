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
ms.openlocfilehash: ff2913399e1dbeb33bbfb697058db3caf2a8d1fb
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95713108"
---
# <a name="icordebugprocess5getobject-method"></a><span data-ttu-id="0fa19-102">ICorDebugProcess5::GetObject 메서드</span><span class="sxs-lookup"><span data-stu-id="0fa19-102">ICorDebugProcess5::GetObject Method</span></span>

<span data-ttu-id="0fa19-103">개체 주소를 "ICorDebugObjectValue" 개체로 변환 합니다.</span><span class="sxs-lookup"><span data-stu-id="0fa19-103">Converts an object address to an "ICorDebugObjectValue" object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0fa19-104">구문</span><span class="sxs-lookup"><span data-stu-id="0fa19-104">Syntax</span></span>  
  
```cpp  
HRESULT GetObject(  
    [in] CORDB_ADDRESS addr,
    [out] ICorDebugObjectValue **ppObject  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0fa19-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="0fa19-105">Parameters</span></span>  

 `addr`  
 <span data-ttu-id="0fa19-106">진행 개체 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="0fa19-106">[in] The object address.</span></span>  
  
 `ppObject`  
 <span data-ttu-id="0fa19-107">제한이 "ICorDebugObjectValue" 개체의 주소에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="0fa19-107">[out] A pointer to the address of an  "ICorDebugObjectValue" object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0fa19-108">설명</span><span class="sxs-lookup"><span data-stu-id="0fa19-108">Remarks</span></span>  

 <span data-ttu-id="0fa19-109">`addr`가 유효한 관리 되는 개체를 가리키지 않는 경우이 `GetObject` 메서드는를 반환 `E_FAIL` 합니다.</span><span class="sxs-lookup"><span data-stu-id="0fa19-109">If `addr` does not point to a valid managed object, the `GetObject` method returns `E_FAIL`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0fa19-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="0fa19-110">Requirements</span></span>  

 <span data-ttu-id="0fa19-111">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="0fa19-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0fa19-112">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="0fa19-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="0fa19-113">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0fa19-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0fa19-114">**.NET Framework 버전:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0fa19-114">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0fa19-115">참조</span><span class="sxs-lookup"><span data-stu-id="0fa19-115">See also</span></span>

- [<span data-ttu-id="0fa19-116">ICorDebugProcess5 인터페이스</span><span class="sxs-lookup"><span data-stu-id="0fa19-116">ICorDebugProcess5 Interface</span></span>](icordebugprocess5-interface.md)
- [<span data-ttu-id="0fa19-117">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="0fa19-117">Debugging Interfaces</span></span>](debugging-interfaces.md)
