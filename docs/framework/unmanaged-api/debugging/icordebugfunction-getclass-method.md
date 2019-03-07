---
title: ICorDebugFunction::GetClass 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugFunction.GetClass
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugFunction::GetClass
helpviewer_keywords:
- GetClass method, ICorDebugFunction interface [.NET Framework debugging]
- ICorDebugFunction::GetClass method [.NET Framework debugging]
ms.assetid: 27967230-144f-40d3-9e23-961d0241abd9
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ea71e984be42e3b1a7b4b9fa6df878aca911c412
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/06/2019
ms.locfileid: "57501190"
---
# <a name="icordebugfunctiongetclass-method"></a><span data-ttu-id="887e7-102">ICorDebugFunction::GetClass 메서드</span><span class="sxs-lookup"><span data-stu-id="887e7-102">ICorDebugFunction::GetClass Method</span></span>
<span data-ttu-id="887e7-103">이 함수는 멤버의 클래스를 나타내는 ICorDebugClass 개체를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="887e7-103">Gets an ICorDebugClass object that represents the class this function is a member of.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="887e7-104">구문</span><span class="sxs-lookup"><span data-stu-id="887e7-104">Syntax</span></span>  
  
```  
HRESULT GetClass (  
    [out] ICorDebugClass **ppClass  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="887e7-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="887e7-105">Parameters</span></span>  
 `ppClass`  
 <span data-ttu-id="887e7-106">[out] 주소에 대 한 포인터를 `ICorDebugClass` 이 함수는 클래스의 멤버가 없는 경우 클래스 또는 null을 나타내는 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="887e7-106">[out] A pointer to the address of the `ICorDebugClass` object that represents the class, or null, if this function is not a member of a class.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="887e7-107">요구 사항</span><span class="sxs-lookup"><span data-stu-id="887e7-107">Requirements</span></span>  
 <span data-ttu-id="887e7-108">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="887e7-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="887e7-109">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="887e7-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="887e7-110">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="887e7-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="887e7-111">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="887e7-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
