---
title: ICorDebugModule::GetSize 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugModule.GetSize
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugModule::GetSize
helpviewer_keywords:
- GetSize method, ICorDebugModule interface [.NET Framework debugging]
- ICorDebugModule::GetSize method [.NET Framework debugging]
ms.assetid: 5c68375d-145d-46ef-a7c8-2dc4257472de
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 46ee21a9fd7b9267672a14107c1706af5d5cdcc5
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/10/2019
ms.locfileid: "67763576"
---
# <a name="icordebugmodulegetsize-method"></a><span data-ttu-id="9a685-102">ICorDebugModule::GetSize 메서드</span><span class="sxs-lookup"><span data-stu-id="9a685-102">ICorDebugModule::GetSize Method</span></span>
<span data-ttu-id="9a685-103">모듈의 바이트에서 크기를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="9a685-103">Gets the size, in bytes, of the module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9a685-104">구문</span><span class="sxs-lookup"><span data-stu-id="9a685-104">Syntax</span></span>  
  
```cpp  
HRESULT GetSize(  
    [out] ULONG32 *pcBytes  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9a685-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="9a685-105">Parameters</span></span>  
 `pcBytes`  
 <span data-ttu-id="9a685-106">[out] 크기 (바이트)에서 모듈입니다.</span><span class="sxs-lookup"><span data-stu-id="9a685-106">[out] The size of the module in bytes.</span></span>  
  
 <span data-ttu-id="9a685-107">모듈 네이티브 이미지 생성기 (NGen.exe)에서 생성 된 경우 모듈의 크기는 0이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9a685-107">If the module was produced from the native image generator (NGen.exe), the size of the module will be zero.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9a685-108">요구 사항</span><span class="sxs-lookup"><span data-stu-id="9a685-108">Requirements</span></span>  
 <span data-ttu-id="9a685-109">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="9a685-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9a685-110">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="9a685-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="9a685-111">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9a685-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9a685-112">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9a685-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
