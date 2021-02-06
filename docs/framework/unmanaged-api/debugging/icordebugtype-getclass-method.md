---
description: '자세히 알아보기: ICorDebugType:: GetClass 메서드'
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
ms.openlocfilehash: 2e8d68fbc8909599ca649ba0e226cc84af820939
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99658336"
---
# <a name="icordebugtypegetclass-method"></a><span data-ttu-id="3e71d-103">ICorDebugType::GetClass 메서드</span><span class="sxs-lookup"><span data-stu-id="3e71d-103">ICorDebugType::GetClass Method</span></span>

<span data-ttu-id="3e71d-104">인스턴스화되지 않은 제네릭 형식을 나타내는 ICorDebugClass에 대 한 인터페이스 포인터를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="3e71d-104">Gets an interface pointer to an ICorDebugClass that represents the uninstantiated generic type.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3e71d-105">구문</span><span class="sxs-lookup"><span data-stu-id="3e71d-105">Syntax</span></span>  
  
```cpp  
HRESULT GetClass (  
    [out] ICorDebugClass   **ppClass  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3e71d-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="3e71d-106">Parameters</span></span>  

 `ppClass`  
 <span data-ttu-id="3e71d-107">제한이 `ICorDebugClass` 인스턴스화되지 않은 제네릭 형식을 나타내는 인터페이스의 주소에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="3e71d-107">[out] A pointer to the address of an `ICorDebugClass` interface that represents the uninstantiated generic type.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3e71d-108">설명</span><span class="sxs-lookup"><span data-stu-id="3e71d-108">Remarks</span></span>  

 <span data-ttu-id="3e71d-109">`GetClass` 특정 조건 에서만 호출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3e71d-109">`GetClass` can be called only under certain conditions.</span></span> <span data-ttu-id="3e71d-110">를 호출 하기 전에 [ICorDebugType:: GetType](icordebugtype-gettype-method.md) `GetClass` 을 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="3e71d-110">Call [ICorDebugType::GetType](icordebugtype-gettype-method.md) before calling `GetClass`.</span></span> <span data-ttu-id="3e71d-111">`ICorDebugType::GetType`가 ELEMENT_TYPE_CLASS 또는 ELEMENT_TYPE_VALUETYPE 인 CorElementType 값을 반환 하는 경우를 `GetClass` 호출 하 여 제네릭 형식에 대 한 인스턴스화되지 않은 형식을 가져올 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3e71d-111">If `ICorDebugType::GetType` returns a CorElementType value that is ELEMENT_TYPE_CLASS or ELEMENT_TYPE_VALUETYPE, `GetClass` can be called to get the uninstantiated type for a generic type.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3e71d-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="3e71d-112">Requirements</span></span>  

 <span data-ttu-id="3e71d-113">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="3e71d-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3e71d-114">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="3e71d-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="3e71d-115">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3e71d-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3e71d-116">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3e71d-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
