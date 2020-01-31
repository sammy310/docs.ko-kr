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
ms.openlocfilehash: fdfa38a4cdbbaad2fc2c987a10a122af4a1fc9a9
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/28/2020
ms.locfileid: "76791032"
---
# <a name="icordebugvariablehomegetcode-method"></a><span data-ttu-id="636dc-102">ICorDebugVariableHome:: GetCode 메서드</span><span class="sxs-lookup"><span data-stu-id="636dc-102">ICorDebugVariableHome::GetCode Method</span></span>
<span data-ttu-id="636dc-103">이 [ICorDebugVariableHome](icordebugvariablehome-interface.md) 개체를 포함 하는 "ICorDebugCode" 인스턴스를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="636dc-103">Gets the "ICorDebugCode" instance that contains this [ICorDebugVariableHome](icordebugvariablehome-interface.md) object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="636dc-104">구문</span><span class="sxs-lookup"><span data-stu-id="636dc-104">Syntax</span></span>  
  
```cpp  
HRESULT GetCode(  
    [out] ICorDebugCode **ppCode  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="636dc-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="636dc-105">Parameters</span></span>  
 `ppCode`  
 <span data-ttu-id="636dc-106">제한이 이 [ICorDebugVariableHome](icordebugvariablehome-interface.md) 개체를 포함 하는 "ICorDebugCode" 인스턴스의 주소에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="636dc-106">[out] A pointer to the address of the "ICorDebugCode" instance that contains this [ICorDebugVariableHome](icordebugvariablehome-interface.md) object.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="636dc-107">요구 사항</span><span class="sxs-lookup"><span data-stu-id="636dc-107">Requirements</span></span>  
 <span data-ttu-id="636dc-108">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="636dc-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="636dc-109">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="636dc-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="636dc-110">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="636dc-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="636dc-111">**.NET Framework 버전:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="636dc-111">**.NET Framework Versions:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="636dc-112">참조</span><span class="sxs-lookup"><span data-stu-id="636dc-112">See also</span></span>

- [<span data-ttu-id="636dc-113">ICorDebugVariableHome 인터페이스</span><span class="sxs-lookup"><span data-stu-id="636dc-113">ICorDebugVariableHome Interface</span></span>](icordebugvariablehome-interface.md)
