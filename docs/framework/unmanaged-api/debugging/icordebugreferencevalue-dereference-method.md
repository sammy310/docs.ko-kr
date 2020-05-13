---
title: ICorDebugReferenceValue::Dereference 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugReferenceValue.Dereference
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugReferenceValue::Dereference
helpviewer_keywords:
- ICorDebugReferenceValue::Dereference method [.NET Framework debugging]
- Dereference method [.NET Framework debugging]
ms.assetid: 5ec8cf76-3deb-4ce6-9a49-77a4c35d80b9
topic_type:
- apiref
ms.openlocfilehash: 7c64823e1a5c519eb74b508af093afeb1132e608
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/12/2020
ms.locfileid: "83210087"
---
# <a name="icordebugreferencevaluedereference-method"></a><span data-ttu-id="46b21-102">ICorDebugReferenceValue::Dereference 메서드</span><span class="sxs-lookup"><span data-stu-id="46b21-102">ICorDebugReferenceValue::Dereference Method</span></span>
<span data-ttu-id="46b21-103">참조 되는 개체를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="46b21-103">Gets the object that is referenced.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="46b21-104">구문</span><span class="sxs-lookup"><span data-stu-id="46b21-104">Syntax</span></span>  
  
```cpp  
HRESULT Dereference (  
    [out] ICorDebugValue  **ppValue  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="46b21-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="46b21-105">Parameters</span></span>  
 `ppValue`  
 <span data-ttu-id="46b21-106">제한이 이 ICorDebugReferenceValue 개체가 가리키는 개체를 나타내는 ICorDebugValue의 주소에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="46b21-106">[out] A pointer to the address of an ICorDebugValue that represents the object to which this ICorDebugReferenceValue object points.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="46b21-107">설명</span><span class="sxs-lookup"><span data-stu-id="46b21-107">Remarks</span></span>  
 <span data-ttu-id="46b21-108">`ICorDebugValue`개체는 해당 참조를 아직 사용할 수 없는 경우에만 유효 합니다.</span><span class="sxs-lookup"><span data-stu-id="46b21-108">The `ICorDebugValue` object is valid only while its reference has not yet been disabled.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="46b21-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="46b21-109">Requirements</span></span>  
 <span data-ttu-id="46b21-110">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="46b21-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="46b21-111">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="46b21-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="46b21-112">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="46b21-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="46b21-113">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="46b21-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
