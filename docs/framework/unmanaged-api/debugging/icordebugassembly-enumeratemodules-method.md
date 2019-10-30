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
ms.openlocfilehash: b55bd41039fce84a21c5d651d93b56f5d84b7611
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73088187"
---
# <a name="icordebugassemblyenumeratemodules-method"></a><span data-ttu-id="a5fff-102">ICorDebugAssembly::EnumerateModules 메서드</span><span class="sxs-lookup"><span data-stu-id="a5fff-102">ICorDebugAssembly::EnumerateModules Method</span></span>
<span data-ttu-id="a5fff-103">`ICorDebugAssembly`에 포함 된 모듈의 열거자를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="a5fff-103">Gets an enumerator for the modules contained in the `ICorDebugAssembly`.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a5fff-104">구문</span><span class="sxs-lookup"><span data-stu-id="a5fff-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumerateModules (  
    [out] ICorDebugModuleEnum **ppModules  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a5fff-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="a5fff-105">Parameters</span></span>  
 `ppModules`  
 <span data-ttu-id="a5fff-106">제한이 열거자 인 ICorDebugModuleEnum 인터페이스의 주소에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="a5fff-106">[out] A pointer to the address of the ICorDebugModuleEnum interface that is the enumerator.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a5fff-107">요구 사항</span><span class="sxs-lookup"><span data-stu-id="a5fff-107">Requirements</span></span>  
 <span data-ttu-id="a5fff-108">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="a5fff-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a5fff-109">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="a5fff-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a5fff-110">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a5fff-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a5fff-111">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a5fff-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
