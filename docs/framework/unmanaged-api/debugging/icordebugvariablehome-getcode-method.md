---
title: ICorDebugVariableHome::GetCode 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugVariableHome.GetCode
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugVariableHome::GetCode
helpviewer_keywords:
- ICorDebugVariableHome::GetCode method [.NET Framework debugging]
- GetCode method, ICorDebugVariableHome interface [.NET Framework debugging]
ms.assetid: ef002890-4a7b-4a5d-abbf-16c60083f794
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 6a4cadae7a43d0cd965e51535eae2c95e59900d0
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59130015"
---
# <a name="icordebugvariablehomegetcode-method"></a><span data-ttu-id="27ba4-102">ICorDebugVariableHome::GetCode 메서드</span><span class="sxs-lookup"><span data-stu-id="27ba4-102">ICorDebugVariableHome::GetCode Method</span></span>
<span data-ttu-id="27ba4-103">이 포함 하는 "ICorDebugCode" 인스턴스를 가져옵니다 [ICorDebugVariableHome](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md) 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="27ba4-103">Gets the "ICorDebugCode" instance that contains this [ICorDebugVariableHome](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md) object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="27ba4-104">구문</span><span class="sxs-lookup"><span data-stu-id="27ba4-104">Syntax</span></span>  
  
```  
HRESULT GetCode(  
    [out] ICorDebugCode **ppCode  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="27ba4-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="27ba4-105">Parameters</span></span>  
 `ppCode`  
 <span data-ttu-id="27ba4-106">[out] 이 포함 하는 "ICorDebugCode" 인스턴스의 주소에 대 한 포인터 [ICorDebugVariableHome](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md) 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="27ba4-106">[out] A pointer to the address of the "ICorDebugCode" instance that contains this [ICorDebugVariableHome](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md) object.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="27ba4-107">요구 사항</span><span class="sxs-lookup"><span data-stu-id="27ba4-107">Requirements</span></span>  
 <span data-ttu-id="27ba4-108">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="27ba4-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="27ba4-109">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="27ba4-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="27ba4-110">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="27ba4-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="27ba4-111">**.NET Framework 버전:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="27ba4-111">**.NET Framework Versions:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="27ba4-112">참고자료</span><span class="sxs-lookup"><span data-stu-id="27ba4-112">See also</span></span>

- [<span data-ttu-id="27ba4-113">ICorDebugVariableHome 인터페이스</span><span class="sxs-lookup"><span data-stu-id="27ba4-113">ICorDebugVariableHome Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md)
