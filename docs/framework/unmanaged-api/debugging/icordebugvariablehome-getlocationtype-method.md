---
title: ICorDebugVariableHome::GetLocationType 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugVariableHome.GetLocationType
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugVariableHome::GetLocationType
helpviewer_keywords:
- ICorDebugVariableHome::GetLocationType method [.NET Framework debugging]
- GetLocationType method, ICorDebugVariableHome interface [.NET Framework debugging]
ms.assetid: 88027c55-8ec6-4f1e-a55b-7eefdbbc3515
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: af879cbbf8edfd05e79d9b77b0c1fb71b2c835c3
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59224301"
---
# <a name="icordebugvariablehomegetlocationtype-method"></a><span data-ttu-id="1e3f4-102">ICorDebugVariableHome::GetLocationType 메서드</span><span class="sxs-lookup"><span data-stu-id="1e3f4-102">ICorDebugVariableHome::GetLocationType Method</span></span>
<span data-ttu-id="1e3f4-103">변수의 네이티브 위치 유형을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="1e3f4-103">Gets the type of the variable's native location.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1e3f4-104">구문</span><span class="sxs-lookup"><span data-stu-id="1e3f4-104">Syntax</span></span>  
  
```  
HRESULT GetLocationType(  
    [out] VariableLocationType *pLocationType  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1e3f4-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="1e3f4-105">Parameters</span></span>  
 `pLocationType`  
 <span data-ttu-id="1e3f4-106">[out] 변수의 기본 위치의 형식에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="1e3f4-106">[out] A pointer to the type of the variable's native location.</span></span>  <span data-ttu-id="1e3f4-107">참조 된 [VariableLocationType](../../../../docs/framework/unmanaged-api/debugging/variablelocationtype-enumeration.md) 자세한 정보에 대 한 열거형입니다.</span><span class="sxs-lookup"><span data-stu-id="1e3f4-107">See the [VariableLocationType](../../../../docs/framework/unmanaged-api/debugging/variablelocationtype-enumeration.md) enumeration for more information.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1e3f4-108">요구 사항</span><span class="sxs-lookup"><span data-stu-id="1e3f4-108">Requirements</span></span>  
 <span data-ttu-id="1e3f4-109">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="1e3f4-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1e3f4-110">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="1e3f4-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="1e3f4-111">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1e3f4-111">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="1e3f4-112">.NET Framework 버전:</span><span class="sxs-lookup"><span data-stu-id="1e3f4-112">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="1e3f4-113">참고자료</span><span class="sxs-lookup"><span data-stu-id="1e3f4-113">See also</span></span>

- [<span data-ttu-id="1e3f4-114">ICorDebugVariableHome 인터페이스</span><span class="sxs-lookup"><span data-stu-id="1e3f4-114">ICorDebugVariableHome Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md)
- [<span data-ttu-id="1e3f4-115">VariableLocationType 열거형</span><span class="sxs-lookup"><span data-stu-id="1e3f4-115">VariableLocationType Enumeration</span></span>](../../../../docs/framework/unmanaged-api/debugging/variablelocationtype-enumeration.md)
