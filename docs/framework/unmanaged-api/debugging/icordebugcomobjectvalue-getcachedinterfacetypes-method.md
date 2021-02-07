---
description: '자세히 알아보기: ICorDebugComObjectValue:: GetCachedInterfaceTypes 메서드'
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
ms.openlocfilehash: b1c65979895dfaeacae3d171adbcfd1455b7030d
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99764621"
---
# <a name="icordebugcomobjectvaluegetcachedinterfacetypes-method"></a><span data-ttu-id="27f25-103">ICorDebugComObjectValue::GetCachedInterfaceTypes 메서드</span><span class="sxs-lookup"><span data-stu-id="27f25-103">ICorDebugComObjectValue::GetCachedInterfaceTypes Method</span></span>

<span data-ttu-id="27f25-104">현재 개체가 캐스팅 되었거나로 사용 된 인터페이스 형식에 대 한 열거자를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="27f25-104">Provides an enumerator for the interface types that the current object has been cast to or used as.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="27f25-105">구문</span><span class="sxs-lookup"><span data-stu-id="27f25-105">Syntax</span></span>  
  
```cpp  
HRESULT GetCachedInterfaceTypes(  
    [in] BOOL bIInspectableOnly,  
    [out] ICorDebugTypeEnum **ppInterfacesEnum);  
```  
  
## <a name="parameters"></a><span data-ttu-id="27f25-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="27f25-106">Parameters</span></span>  

 `bIInspectableOnly`  
 <span data-ttu-id="27f25-107">진행 메서드가 `IInspectable` RCW (런타임 호출 가능 래퍼)가 캐시 하는 Windows 런타임 인터페이스 (인터페이스) 또는 모든 COM 인터페이스만 반환 하는지 여부를 나타내는 값입니다.</span><span class="sxs-lookup"><span data-stu-id="27f25-107">[in] A value that indicates whether the method returns only Windows Runtime interfaces (`IInspectable` interfaces) or all COM interfaces cached by the runtime callable wrapper (RCW).</span></span>  
  
 `ppInterfacesEnum`  
 <span data-ttu-id="27f25-108">제한이 에 따라 필터링 된 캐시 된 인터페이스 형식을 나타내는 ICorDebugType 개체에 대 한 액세스를 제공 하는 ICorDebugTypeEnum 열거자의 주소에 대 한 포인터입니다 `bIInspectableOnly` .</span><span class="sxs-lookup"><span data-stu-id="27f25-108">[out] A pointer to the address of an ICorDebugTypeEnum enumerator that provides access to ICorDebugType objects that represent cached interface types filtered according to `bIInspectableOnly`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="27f25-109">설명</span><span class="sxs-lookup"><span data-stu-id="27f25-109">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="27f25-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="27f25-110">Requirements</span></span>  

 <span data-ttu-id="27f25-111">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="27f25-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="27f25-112">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="27f25-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="27f25-113">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="27f25-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="27f25-114">**.NET Framework 버전:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="27f25-114">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="27f25-115">참고 항목</span><span class="sxs-lookup"><span data-stu-id="27f25-115">See also</span></span>

- [<span data-ttu-id="27f25-116">ICorDebugComObjectValue 인터페이스</span><span class="sxs-lookup"><span data-stu-id="27f25-116">ICorDebugComObjectValue Interface</span></span>](icordebugcomobjectvalue-interface.md)
- [<span data-ttu-id="27f25-117">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="27f25-117">Debugging Interfaces</span></span>](debugging-interfaces.md)
