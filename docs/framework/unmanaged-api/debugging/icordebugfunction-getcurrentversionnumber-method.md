---
title: ICorDebugFunction::GetCurrentVersionNumber 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugFunction.GetCurrentVersionNumber
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugFunction::GetCurrentVersionNumber
helpviewer_keywords:
- GetCurrentVersionNumber method [.NET Framework debugging]
- ICorDebugFunction::GetCurrentVersionNumber method [.NET Framework debugging]
ms.assetid: c3af1575-cbe6-457a-bc08-c53460edcbc8
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ea615eacb30fd4e7a0fd7d730094c2ab4f9dc285
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/06/2019
ms.locfileid: "57478481"
---
# <a name="icordebugfunctiongetcurrentversionnumber-method"></a><span data-ttu-id="dca2c-102">ICorDebugFunction::GetCurrentVersionNumber 메서드</span><span class="sxs-lookup"><span data-stu-id="dca2c-102">ICorDebugFunction::GetCurrentVersionNumber Method</span></span>
<span data-ttu-id="dca2c-103">ICorDebugFunction 개체가 나타내는 함수에 대 한 최신 편집의 버전 번호를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="dca2c-103">Gets the version number of the latest edit made to the function represented by this ICorDebugFunction object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dca2c-104">구문</span><span class="sxs-lookup"><span data-stu-id="dca2c-104">Syntax</span></span>  
  
```  
HRESULT GetCurrentVersionNumber (  
    [out] ULONG32 *pnCurrentVersion  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="dca2c-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="dca2c-105">Parameters</span></span>  
 `pnCurrentVersion`  
 <span data-ttu-id="dca2c-106">[out] 이 함수에 대 한 최신 편집의 버전 번호는 정수 값에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="dca2c-106">[out] A pointer to an integer value that is the version number of the latest edit made to this function.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="dca2c-107">설명</span><span class="sxs-lookup"><span data-stu-id="dca2c-107">Remarks</span></span>  
 <span data-ttu-id="dca2c-108">이 함수에 대 한 최신 편집의 버전 번호를 함수 자체의 버전 번호 보다 클 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dca2c-108">The version number of the latest edit made to this function may be greater than the version number of the function itself.</span></span> <span data-ttu-id="dca2c-109">하나를 사용 합니다 [ICorDebugFunction2::GetVersionNumber](../../../../docs/framework/unmanaged-api/debugging/icordebugfunction2-getversionnumber-method.md) 메서드 또는 [icordebugcode:: Getversionnumber](../../../../docs/framework/unmanaged-api/debugging/icordebugcode-getversionnumber-method.md) 함수 버전 번호를 검색 하는 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="dca2c-109">Use either the [ICorDebugFunction2::GetVersionNumber](../../../../docs/framework/unmanaged-api/debugging/icordebugfunction2-getversionnumber-method.md) method or the [ICorDebugCode::GetVersionNumber](../../../../docs/framework/unmanaged-api/debugging/icordebugcode-getversionnumber-method.md) method to retrieve the version number of the function.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="dca2c-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="dca2c-110">Requirements</span></span>  
 <span data-ttu-id="dca2c-111">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="dca2c-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="dca2c-112">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="dca2c-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="dca2c-113">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="dca2c-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="dca2c-114">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="dca2c-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
