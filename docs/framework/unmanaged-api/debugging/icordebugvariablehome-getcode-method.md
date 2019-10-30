---
title: 'ICorDebugVariableHome:: GetCode 메서드'
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
ms.openlocfilehash: 4770eb3e93104dd3862eb2163faf1dc7fe9008ba
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73125130"
---
# <a name="icordebugvariablehomegetcode-method"></a><span data-ttu-id="5ac95-102">ICorDebugVariableHome:: GetCode 메서드</span><span class="sxs-lookup"><span data-stu-id="5ac95-102">ICorDebugVariableHome::GetCode Method</span></span>
<span data-ttu-id="5ac95-103">이 [ICorDebugVariableHome](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md) 개체를 포함 하는 "ICorDebugCode" 인스턴스를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="5ac95-103">Gets the "ICorDebugCode" instance that contains this [ICorDebugVariableHome](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md) object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5ac95-104">구문</span><span class="sxs-lookup"><span data-stu-id="5ac95-104">Syntax</span></span>  
  
```cpp  
HRESULT GetCode(  
    [out] ICorDebugCode **ppCode  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5ac95-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="5ac95-105">Parameters</span></span>  
 `ppCode`  
 <span data-ttu-id="5ac95-106">제한이 이 [ICorDebugVariableHome](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md) 개체를 포함 하는 "ICorDebugCode" 인스턴스의 주소에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="5ac95-106">[out] A pointer to the address of the "ICorDebugCode" instance that contains this [ICorDebugVariableHome](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md) object.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5ac95-107">요구 사항</span><span class="sxs-lookup"><span data-stu-id="5ac95-107">Requirements</span></span>  
 <span data-ttu-id="5ac95-108">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="5ac95-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5ac95-109">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="5ac95-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="5ac95-110">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5ac95-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5ac95-111">**.NET Framework 버전:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5ac95-111">**.NET Framework Versions:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5ac95-112">참조</span><span class="sxs-lookup"><span data-stu-id="5ac95-112">See also</span></span>

- [<span data-ttu-id="5ac95-113">ICorDebugVariableHome 인터페이스</span><span class="sxs-lookup"><span data-stu-id="5ac95-113">ICorDebugVariableHome Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md)
