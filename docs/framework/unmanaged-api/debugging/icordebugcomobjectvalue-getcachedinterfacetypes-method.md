---
title: ICorDebugComObjectValue::GetCachedInterfaceTypes 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugComObjectValue::GetCachedInterfaceTypes
api_location:
- mscordbi.dll
f1_keywords:
- ICorDebugComObjectValue::GetCachedInterfaceTypes
helpviewer_keywords:
- GetCachedInterface method, ICorDebugComObjectValue interface [.NET Framework debugging]
- ICorDebugComObjectValue::GetCachedInterface method [.NET Framework debugging]
ms.assetid: d492284f-d3c5-4614-adb8-d718d5042500
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e1da347fd85e1b3856615faf49c60b607cc7f0da
ms.sourcegitcommit: 5bc85ad81d96b8dc2a90ce53bada475ee5662c44
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/12/2019
ms.locfileid: "67025833"
---
# <a name="icordebugcomobjectvaluegetcachedinterfacetypes-method"></a><span data-ttu-id="ff4ef-102">ICorDebugComObjectValue::GetCachedInterfaceTypes 메서드</span><span class="sxs-lookup"><span data-stu-id="ff4ef-102">ICorDebugComObjectValue::GetCachedInterfaceTypes Method</span></span>
<span data-ttu-id="ff4ef-103">현재 개체 캐스팅 되거나 사용 된 인터페이스 형식에 대 한 열거자를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="ff4ef-103">Provides an enumerator for the interface types that the current object has been cast to or used as.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ff4ef-104">구문</span><span class="sxs-lookup"><span data-stu-id="ff4ef-104">Syntax</span></span>  
  
```  
HRESULT GetCachedInterfaceTypes(  
    [in] BOOL bIInspectableOnly,  
    [out] ICorDebugTypeEnum **ppInterfacesEnum);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ff4ef-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="ff4ef-105">Parameters</span></span>  
 `bIInspectableOnly`  
 <span data-ttu-id="ff4ef-106">[in] 메서드를 Windows 런타임 인터페이스를 반환 하는지 여부를 나타내는 값 (`IInspectable` 인터페이스) 또는 런타임 호출 가능 래퍼 (RCW)에 의해 캐시 되는 모든 COM 인터페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="ff4ef-106">[in] A value that indicates whether the method returns only Windows Runtime interfaces (`IInspectable` interfaces) or all COM interfaces cached by the runtime callable wrapper (RCW).</span></span>  
  
 `ppInterfacesEnum`  
 <span data-ttu-id="ff4ef-107">[out] 캐시 된 인터페이스 형식을 나타내는 ICorDebugType 개체에 대 한 액세스를 제공 하는 ICorDebugTypeEnum 열거자의 주소에 대 한 포인터에 따라 필터링 `bIInspectableOnly`합니다.</span><span class="sxs-lookup"><span data-stu-id="ff4ef-107">[out] A pointer to the address of an ICorDebugTypeEnum enumerator that provides access to ICorDebugType objects that represent cached interface types filtered according to `bIInspectableOnly`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ff4ef-108">설명</span><span class="sxs-lookup"><span data-stu-id="ff4ef-108">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ff4ef-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="ff4ef-109">Requirements</span></span>  
 <span data-ttu-id="ff4ef-110">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="ff4ef-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ff4ef-111">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="ff4ef-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ff4ef-112">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ff4ef-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ff4ef-113">**.NET Framework 버전:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ff4ef-113">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ff4ef-114">참고자료</span><span class="sxs-lookup"><span data-stu-id="ff4ef-114">See also</span></span>

- [<span data-ttu-id="ff4ef-115">ICorDebugComObjectValue 인터페이스</span><span class="sxs-lookup"><span data-stu-id="ff4ef-115">ICorDebugComObjectValue Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcomobjectvalue-interface.md)
- [<span data-ttu-id="ff4ef-116">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="ff4ef-116">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
