---
title: ICorDebugType::GetRank 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugType.GetRank
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugType::GetRank
helpviewer_keywords:
- GetRank method, ICorDebugType interface [.NET Framework debugging]
- ICorDebugType::GetRank method [.NET Framework debugging]
ms.assetid: 72d3d927-f590-4f2d-8f60-448f3dfb96af
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e42db5d7ebc9ec9983fe9e56477808415b26968b
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/10/2019
ms.locfileid: "67751578"
---
# <a name="icordebugtypegetrank-method"></a><span data-ttu-id="47fca-102">ICorDebugType::GetRank 메서드</span><span class="sxs-lookup"><span data-stu-id="47fca-102">ICorDebugType::GetRank Method</span></span>
<span data-ttu-id="47fca-103">배열 형식의 차수를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="47fca-103">Gets the number of dimensions in an array type.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="47fca-104">구문</span><span class="sxs-lookup"><span data-stu-id="47fca-104">Syntax</span></span>  
  
```cpp  
HRESULT GetRank (  
    [out] ULONG32   *pnRank  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="47fca-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="47fca-105">Parameters</span></span>  
 `pnRank`  
 <span data-ttu-id="47fca-106">[out] 차원 수에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="47fca-106">[out] A pointer to the number of dimensions.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="47fca-107">요구 사항</span><span class="sxs-lookup"><span data-stu-id="47fca-107">Requirements</span></span>  
 <span data-ttu-id="47fca-108">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="47fca-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="47fca-109">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="47fca-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="47fca-110">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="47fca-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="47fca-111">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="47fca-111">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
