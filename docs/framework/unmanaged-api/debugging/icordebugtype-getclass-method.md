---
title: ICorDebugType::GetClass 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugType.GetClass
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugType::GetClass
helpviewer_keywords:
- ICorDebugType::GetClass method [.NET Framework debugging]
- GetClass method, ICorDebugType interface [.NET Framework debugging]
ms.assetid: 2644f48b-db3c-429f-ae62-76f1c98a1af5
topic_type:
- apiref
ms.openlocfilehash: 1cb9729f175a2e82e88386b0694467c6fe05636a
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95684462"
---
# <a name="icordebugtypegetclass-method"></a><span data-ttu-id="34661-102">ICorDebugType::GetClass 메서드</span><span class="sxs-lookup"><span data-stu-id="34661-102">ICorDebugType::GetClass Method</span></span>

<span data-ttu-id="34661-103">인스턴스화되지 않은 제네릭 형식을 나타내는 ICorDebugClass에 대 한 인터페이스 포인터를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="34661-103">Gets an interface pointer to an ICorDebugClass that represents the uninstantiated generic type.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="34661-104">구문</span><span class="sxs-lookup"><span data-stu-id="34661-104">Syntax</span></span>  
  
```cpp  
HRESULT GetClass (  
    [out] ICorDebugClass   **ppClass  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="34661-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="34661-105">Parameters</span></span>  

 `ppClass`  
 <span data-ttu-id="34661-106">제한이 `ICorDebugClass` 인스턴스화되지 않은 제네릭 형식을 나타내는 인터페이스의 주소에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="34661-106">[out] A pointer to the address of an `ICorDebugClass` interface that represents the uninstantiated generic type.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="34661-107">설명</span><span class="sxs-lookup"><span data-stu-id="34661-107">Remarks</span></span>  

 <span data-ttu-id="34661-108">`GetClass` 특정 조건 에서만 호출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="34661-108">`GetClass` can be called only under certain conditions.</span></span> <span data-ttu-id="34661-109">를 호출 하기 전에 [ICorDebugType:: GetType](icordebugtype-gettype-method.md) `GetClass` 을 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="34661-109">Call [ICorDebugType::GetType](icordebugtype-gettype-method.md) before calling `GetClass`.</span></span> <span data-ttu-id="34661-110">`ICorDebugType::GetType`가 ELEMENT_TYPE_CLASS 또는 ELEMENT_TYPE_VALUETYPE 인 CorElementType 값을 반환 하는 경우를 `GetClass` 호출 하 여 제네릭 형식에 대 한 인스턴스화되지 않은 형식을 가져올 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="34661-110">If `ICorDebugType::GetType` returns a CorElementType value that is ELEMENT_TYPE_CLASS or ELEMENT_TYPE_VALUETYPE, `GetClass` can be called to get the uninstantiated type for a generic type.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="34661-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="34661-111">Requirements</span></span>  

 <span data-ttu-id="34661-112">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="34661-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="34661-113">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="34661-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="34661-114">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="34661-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="34661-115">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="34661-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
