---
description: ICorDebugReferenceValue::D ereference 메서드에 대해 자세히 알아보세요.
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
ms.openlocfilehash: af225f746a9c67a90a7ad73046cd03401e4ba735
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99691109"
---
# <a name="icordebugreferencevaluedereference-method"></a><span data-ttu-id="3d492-103">ICorDebugReferenceValue::Dereference 메서드</span><span class="sxs-lookup"><span data-stu-id="3d492-103">ICorDebugReferenceValue::Dereference Method</span></span>

<span data-ttu-id="3d492-104">참조 되는 개체를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="3d492-104">Gets the object that is referenced.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3d492-105">구문</span><span class="sxs-lookup"><span data-stu-id="3d492-105">Syntax</span></span>  
  
```cpp  
HRESULT Dereference (  
    [out] ICorDebugValue  **ppValue  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3d492-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="3d492-106">Parameters</span></span>  

 `ppValue`  
 <span data-ttu-id="3d492-107">제한이 이 ICorDebugReferenceValue 개체가 가리키는 개체를 나타내는 ICorDebugValue의 주소에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="3d492-107">[out] A pointer to the address of an ICorDebugValue that represents the object to which this ICorDebugReferenceValue object points.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3d492-108">설명</span><span class="sxs-lookup"><span data-stu-id="3d492-108">Remarks</span></span>  

 <span data-ttu-id="3d492-109">`ICorDebugValue`개체는 해당 참조를 아직 사용할 수 없는 경우에만 유효 합니다.</span><span class="sxs-lookup"><span data-stu-id="3d492-109">The `ICorDebugValue` object is valid only while its reference has not yet been disabled.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3d492-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="3d492-110">Requirements</span></span>  

 <span data-ttu-id="3d492-111">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="3d492-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3d492-112">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="3d492-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="3d492-113">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3d492-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3d492-114">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3d492-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
