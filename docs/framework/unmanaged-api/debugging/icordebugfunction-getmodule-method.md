---
description: '자세히 알아보기: ICorDebugFunction:: GetModule 메서드'
title: ICorDebugFunction::GetModule 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugFunction.GetModule
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugFunction::GetModule
helpviewer_keywords:
- ICorDebugFunction::GetModule method [.NET Framework debugging]
- GetModule method, ICorDebugFunction interface [.NET Framework debugging]
ms.assetid: 5031a5d3-2564-412a-9007-e36d4631308a
topic_type:
- apiref
ms.openlocfilehash: 62087cdf0443b2ef495461aab74cfa047b95efca
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99692474"
---
# <a name="icordebugfunctiongetmodule-method"></a><span data-ttu-id="957b3-103">ICorDebugFunction::GetModule 메서드</span><span class="sxs-lookup"><span data-stu-id="957b3-103">ICorDebugFunction::GetModule Method</span></span>

<span data-ttu-id="957b3-104">이 함수가 정의 된 모듈을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="957b3-104">Gets the module in which this function is defined.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="957b3-105">구문</span><span class="sxs-lookup"><span data-stu-id="957b3-105">Syntax</span></span>  
  
```cpp  
HRESULT GetModule (  
    [out] ICorDebugModule **ppModule  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="957b3-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="957b3-106">Parameters</span></span>  

 `ppModule`  
 <span data-ttu-id="957b3-107">제한이 이 함수가 정의 된 모듈을 나타내는 ICorDebugModule 개체의 주소에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="957b3-107">[out] A pointer to the address of an ICorDebugModule object that represents the module in which this function is defined.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="957b3-108">요구 사항</span><span class="sxs-lookup"><span data-stu-id="957b3-108">Requirements</span></span>  

 <span data-ttu-id="957b3-109">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="957b3-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="957b3-110">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="957b3-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="957b3-111">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="957b3-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="957b3-112">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="957b3-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
