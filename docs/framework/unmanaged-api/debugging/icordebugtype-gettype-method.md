---
description: '자세히 알아보기: ICorDebugType:: GetType 메서드'
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
ms.openlocfilehash: 922791e51855badfb1fd548e08953a2f660f971a
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99658219"
---
# <a name="icordebugtypegettype-method"></a><span data-ttu-id="72b7c-103">ICorDebugType::GetType 메서드</span><span class="sxs-lookup"><span data-stu-id="72b7c-103">ICorDebugType::GetType Method</span></span>

<span data-ttu-id="72b7c-104">이 ICorDebugType로 표시 되는 CLR (공용 언어 런타임)의 네이티브 형식을 설명 하는 CorElementType 값을 가져옵니다 <xref:System.Type> .</span><span class="sxs-lookup"><span data-stu-id="72b7c-104">Gets a CorElementType value that describes the native type of the common language runtime (CLR) <xref:System.Type> represented by this ICorDebugType.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="72b7c-105">구문</span><span class="sxs-lookup"><span data-stu-id="72b7c-105">Syntax</span></span>  
  
```cpp  
HRESULT GetType (  
    [out] CorElementType   *ty  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="72b7c-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="72b7c-106">Parameters</span></span>  

 `ty`  
 <span data-ttu-id="72b7c-107">제한이 `CorElementType` 이가 나타내는 CLR을 나타내는 열거형의 값에 대 한 포인터입니다 <xref:System.Type> `ICorDebugType` .</span><span class="sxs-lookup"><span data-stu-id="72b7c-107">[out] A pointer to a value of the `CorElementType` enumeration that indicates the CLR <xref:System.Type> that this `ICorDebugType` represents.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="72b7c-108">설명</span><span class="sxs-lookup"><span data-stu-id="72b7c-108">Remarks</span></span>  

 <span data-ttu-id="72b7c-109">의 값 `ty` 이 ELEMENT_TYPE_CLASS 또는 ELEMENT_TYPE_VALUETYPE 인 경우 [ICorDebugType:: getclass](icordebugtype-getclass-method.md) 메서드를 호출 하 여 제네릭 형식에 대 한 인스턴스화되지 않은 형식을 가져올 수 있습니다. 그렇지 않으면를 호출 하지 않습니다 `ICorDebugType::GetClass` .</span><span class="sxs-lookup"><span data-stu-id="72b7c-109">If the value of `ty` is either ELEMENT_TYPE_CLASS or ELEMENT_TYPE_VALUETYPE, the [ICorDebugType::GetClass](icordebugtype-getclass-method.md) method may be called to get the uninstantiated type for a generic type; otherwise, do not call `ICorDebugType::GetClass`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="72b7c-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="72b7c-110">Requirements</span></span>  

 <span data-ttu-id="72b7c-111">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="72b7c-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="72b7c-112">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="72b7c-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="72b7c-113">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="72b7c-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="72b7c-114">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="72b7c-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
