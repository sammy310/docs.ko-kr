---
title: ICorDebugCode::GetFunction 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugCode.GetFunction
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugCode::GetFunction
helpviewer_keywords:
- GetFunction method, ICorDebugCode interface [.NET Framework debugging]
- ICorDebugCode::GetFunction method [.NET Framework debugging]
ms.assetid: c568b737-fdb2-4816-accd-051f5ab760f1
topic_type:
- apiref
ms.openlocfilehash: 9f785eafa8925324e3bd269ca08a3b1367b74c44
ms.sourcegitcommit: 957c49696eaf048c284ef8f9f8ffeb562357ad95
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/07/2020
ms.locfileid: "82893582"
---
# <a name="icordebugcodegetfunction-method"></a><span data-ttu-id="ce78b-102">ICorDebugCode::GetFunction 메서드</span><span class="sxs-lookup"><span data-stu-id="ce78b-102">ICorDebugCode::GetFunction Method</span></span>
<span data-ttu-id="ce78b-103">이 "ICorDebugCode"와 연결 된 "ICorDebugFunction"를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="ce78b-103">Gets the "ICorDebugFunction" associated with this "ICorDebugCode".</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ce78b-104">구문</span><span class="sxs-lookup"><span data-stu-id="ce78b-104">Syntax</span></span>  
  
```cpp  
HRESULT GetFunction (  
    [out] ICorDebugFunction **ppFunction  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ce78b-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="ce78b-105">Parameters</span></span>  
 `ppFunction`  
 <span data-ttu-id="ce78b-106">제한이 함수 주소에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="ce78b-106">[out] A pointer to the address of the function.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ce78b-107">설명</span><span class="sxs-lookup"><span data-stu-id="ce78b-107">Remarks</span></span>  
 <span data-ttu-id="ce78b-108">`ICorDebugCode`및 `ICorDebugFunction` 은 일 대 일 관계를 유지 합니다.</span><span class="sxs-lookup"><span data-stu-id="ce78b-108">`ICorDebugCode` and `ICorDebugFunction` maintain a one-to-one relationship.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ce78b-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="ce78b-109">Requirements</span></span>  
 <span data-ttu-id="ce78b-110">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ce78b-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ce78b-111">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="ce78b-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ce78b-112">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ce78b-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ce78b-113">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ce78b-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
