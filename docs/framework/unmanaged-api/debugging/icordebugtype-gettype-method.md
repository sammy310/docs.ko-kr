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
ms.openlocfilehash: 25ffbf73fbefbb3c584450283c3080dfc11ee598
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/28/2020
ms.locfileid: "76791247"
---
# <a name="icordebugtypegettype-method"></a><span data-ttu-id="c3ca1-102">ICorDebugType::GetType 메서드</span><span class="sxs-lookup"><span data-stu-id="c3ca1-102">ICorDebugType::GetType Method</span></span>
<span data-ttu-id="c3ca1-103">이 ICorDebugType가 나타내는 CLR (공용 언어 런타임) <xref:System.Type>의 네이티브 형식을 설명 하는 CorElementType 값을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="c3ca1-103">Gets a CorElementType value that describes the native type of the common language runtime (CLR) <xref:System.Type> represented by this ICorDebugType.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c3ca1-104">구문</span><span class="sxs-lookup"><span data-stu-id="c3ca1-104">Syntax</span></span>  
  
```cpp  
HRESULT GetType (  
    [out] CorElementType   *ty  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c3ca1-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="c3ca1-105">Parameters</span></span>  
 `ty`  
 <span data-ttu-id="c3ca1-106">제한이 이 `ICorDebugType` 나타내는 CLR <xref:System.Type>를 나타내는 `CorElementType` 열거형의 값에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="c3ca1-106">[out] A pointer to a value of the `CorElementType` enumeration that indicates the CLR <xref:System.Type> that this `ICorDebugType` represents.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c3ca1-107">주의</span><span class="sxs-lookup"><span data-stu-id="c3ca1-107">Remarks</span></span>  
 <span data-ttu-id="c3ca1-108">`ty` 값이 ELEMENT_TYPE_CLASS 또는 ELEMENT_TYPE_VALUETYPE 인 경우 [ICorDebugType:: GetClass](icordebugtype-getclass-method.md) 메서드를 호출 하 여 제네릭 형식에 대 한 인스턴스화되지 않은 형식을 가져올 수 있습니다. 그렇지 않으면 `ICorDebugType::GetClass`를 호출 하지 마세요.</span><span class="sxs-lookup"><span data-stu-id="c3ca1-108">If the value of `ty` is either ELEMENT_TYPE_CLASS or ELEMENT_TYPE_VALUETYPE, the [ICorDebugType::GetClass](icordebugtype-getclass-method.md) method may be called to get the uninstantiated type for a generic type; otherwise, do not call `ICorDebugType::GetClass`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c3ca1-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="c3ca1-109">Requirements</span></span>  
 <span data-ttu-id="c3ca1-110">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c3ca1-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c3ca1-111">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="c3ca1-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c3ca1-112">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c3ca1-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c3ca1-113">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c3ca1-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
