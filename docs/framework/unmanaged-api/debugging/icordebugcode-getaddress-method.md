---
title: ICorDebugCode::GetAddress 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugCode.GetAddress
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugCode::GetAddress
helpviewer_keywords:
- GetAddress method, ICorDebugCode interface [.NET Framework debugging]
- ICorDebugCode::GetAddress method [.NET Framework debugging]
ms.assetid: cc507cb0-df2e-49c2-b32e-0c3271a8df9a
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 7df668487601e4278b56e196a43d1154b643fd29
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/01/2019
ms.locfileid: "71700741"
---
# <a name="icordebugcodegetaddress-method"></a><span data-ttu-id="ded2b-102">ICorDebugCode::GetAddress 메서드</span><span class="sxs-lookup"><span data-stu-id="ded2b-102">ICorDebugCode::GetAddress Method</span></span>
<span data-ttu-id="ded2b-103">이 "ICorDebugCode" 인터페이스가 나타내는 코드 세그먼트의 RVA (상대 가상 주소)를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="ded2b-103">Gets the relative virtual address (RVA) of the code segment that this "ICorDebugCode" interface represents.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ded2b-104">구문</span><span class="sxs-lookup"><span data-stu-id="ded2b-104">Syntax</span></span>  
  
```cpp  
HRESULT GetAddress (  
    [out] CORDB_ADDRESS *pStart  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ded2b-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="ded2b-105">Parameters</span></span>  
 `pStart`  
 <span data-ttu-id="ded2b-106">제한이 코드 세그먼트의 RVA에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="ded2b-106">[out] A pointer to the RVA of the code segment.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ded2b-107">요구 사항</span><span class="sxs-lookup"><span data-stu-id="ded2b-107">Requirements</span></span>  
 <span data-ttu-id="ded2b-108">**플랫폼** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="ded2b-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ded2b-109">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="ded2b-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ded2b-110">**라이브러리** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ded2b-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ded2b-111">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ded2b-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
