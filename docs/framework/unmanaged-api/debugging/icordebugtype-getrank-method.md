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
ms.openlocfilehash: 5e28ccb53771be4a2b6681e2491094d15f01904e
ms.sourcegitcommit: d6bd7903d7d46698e9d89d3725f3bb4876891aa3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/13/2020
ms.locfileid: "83379973"
---
# <a name="icordebugtypegetrank-method"></a><span data-ttu-id="64f1d-102">ICorDebugType::GetRank 메서드</span><span class="sxs-lookup"><span data-stu-id="64f1d-102">ICorDebugType::GetRank Method</span></span>
<span data-ttu-id="64f1d-103">배열 형식의 차원 수를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="64f1d-103">Gets the number of dimensions in an array type.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="64f1d-104">구문</span><span class="sxs-lookup"><span data-stu-id="64f1d-104">Syntax</span></span>  
  
```cpp  
HRESULT GetRank (  
    [out] ULONG32   *pnRank  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="64f1d-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="64f1d-105">Parameters</span></span>  
 `pnRank`  
 <span data-ttu-id="64f1d-106">제한이 차원 수에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="64f1d-106">[out] A pointer to the number of dimensions.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="64f1d-107">요구 사항</span><span class="sxs-lookup"><span data-stu-id="64f1d-107">Requirements</span></span>  
 <span data-ttu-id="64f1d-108">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="64f1d-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="64f1d-109">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="64f1d-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="64f1d-110">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="64f1d-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="64f1d-111">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="64f1d-111">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
