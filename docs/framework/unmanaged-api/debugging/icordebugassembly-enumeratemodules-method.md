---
title: ICorDebugAssembly::EnumerateModules 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugAssembly.EnumerateModules
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugAssembly::EnumerateModules
helpviewer_keywords:
- ICorDebugAssembly::EnumerateModules method [.NET Framework debugging]
- EnumerateModules method [.NET Framework debugging]
ms.assetid: c7ba51a1-0dd5-4452-b471-232febe0f897
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e1d8d76084bcf0b5951c6431c6f21f352406050b
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/10/2019
ms.locfileid: "67737361"
---
# <a name="icordebugassemblyenumeratemodules-method"></a><span data-ttu-id="aff58-102">ICorDebugAssembly::EnumerateModules 메서드</span><span class="sxs-lookup"><span data-stu-id="aff58-102">ICorDebugAssembly::EnumerateModules Method</span></span>
<span data-ttu-id="aff58-103">에 포함 된 모듈에 대 한 열거자를 가져옵니다는 `ICorDebugAssembly`합니다.</span><span class="sxs-lookup"><span data-stu-id="aff58-103">Gets an enumerator for the modules contained in the `ICorDebugAssembly`.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="aff58-104">구문</span><span class="sxs-lookup"><span data-stu-id="aff58-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumerateModules (  
    [out] ICorDebugModuleEnum **ppModules  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="aff58-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="aff58-105">Parameters</span></span>  
 `ppModules`  
 <span data-ttu-id="aff58-106">[out] 열거자는 ICorDebugModuleEnum 인터페이스의 주소에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="aff58-106">[out] A pointer to the address of the ICorDebugModuleEnum interface that is the enumerator.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="aff58-107">요구 사항</span><span class="sxs-lookup"><span data-stu-id="aff58-107">Requirements</span></span>  
 <span data-ttu-id="aff58-108">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="aff58-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="aff58-109">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="aff58-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="aff58-110">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="aff58-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="aff58-111">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="aff58-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
