---
title: ICorDebugType::GetType 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugType.GetType
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugType::GetType
helpviewer_keywords:
- ICorDebugType::GetType method [.NET Framework debugging]
- GetType method, ICorDebugType interface [.NET Framework debugging]
ms.assetid: d6e64534-4d47-4ad0-a340-7590e07e2b4a
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f6b36c524921a4fecf8bc5ddcbace62af6450b6d
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61993904"
---
# <a name="icordebugtypegettype-method"></a><span data-ttu-id="cc9f9-102">ICorDebugType::GetType 메서드</span><span class="sxs-lookup"><span data-stu-id="cc9f9-102">ICorDebugType::GetType Method</span></span>
<span data-ttu-id="cc9f9-103">CLR (공용 언어 런타임)의 네이티브 형식을 설명 하는 CorElementType 값을 가져옵니다 <xref:System.Type> 이 ICorDebugType 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="cc9f9-103">Gets a CorElementType value that describes the native type of the common language runtime (CLR) <xref:System.Type> represented by this ICorDebugType.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cc9f9-104">구문</span><span class="sxs-lookup"><span data-stu-id="cc9f9-104">Syntax</span></span>  
  
```  
HRESULT GetType (  
    [out] CorElementType   *ty  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="cc9f9-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="cc9f9-105">Parameters</span></span>  
 `ty`  
 <span data-ttu-id="cc9f9-106">[out] 값에 대 한 포인터를 `CorElementType` CLR를 나타내는 열거형 <xref:System.Type> 이 `ICorDebugType` 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="cc9f9-106">[out] A pointer to a value of the `CorElementType` enumeration that indicates the CLR <xref:System.Type> that this `ICorDebugType` represents.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="cc9f9-107">설명</span><span class="sxs-lookup"><span data-stu-id="cc9f9-107">Remarks</span></span>  
 <span data-ttu-id="cc9f9-108">경우 값 `ty` ELEMENT_TYPE_CLASS 또는 ELEMENT_TYPE_VALUETYPE은 합니다 [icordebugtype:: Getclass](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-getclass-method.md) 방법으로 제네릭 형식에 대 한 인스턴스화되지 않은 형식을 가져오기 위해 호출할 수 있습니다; 그리고 그렇지 않으면 호출 하지 마세요 `ICorDebugType::GetClass`합니다.</span><span class="sxs-lookup"><span data-stu-id="cc9f9-108">If the value of `ty` is either ELEMENT_TYPE_CLASS or ELEMENT_TYPE_VALUETYPE, the [ICorDebugType::GetClass](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-getclass-method.md) method may be called to get the uninstantiated type for a generic type; otherwise, do not call `ICorDebugType::GetClass`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cc9f9-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="cc9f9-109">Requirements</span></span>  
 <span data-ttu-id="cc9f9-110">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="cc9f9-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cc9f9-111">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="cc9f9-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="cc9f9-112">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="cc9f9-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="cc9f9-113">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cc9f9-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
