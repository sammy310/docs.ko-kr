---
description: '자세히 알아보기: ICorDebugType:: GetRank 메서드'
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
ms.openlocfilehash: e13416856f900846d2df4b8a39303cf0b6a48ebc
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99800905"
---
# <a name="icordebugtypegetrank-method"></a><span data-ttu-id="43e5d-103">ICorDebugType::GetRank 메서드</span><span class="sxs-lookup"><span data-stu-id="43e5d-103">ICorDebugType::GetRank Method</span></span>

<span data-ttu-id="43e5d-104">배열 형식의 차원 수를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="43e5d-104">Gets the number of dimensions in an array type.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="43e5d-105">구문</span><span class="sxs-lookup"><span data-stu-id="43e5d-105">Syntax</span></span>  
  
```cpp  
HRESULT GetRank (  
    [out] ULONG32   *pnRank  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="43e5d-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="43e5d-106">Parameters</span></span>  

 `pnRank`  
 <span data-ttu-id="43e5d-107">제한이 차원 수에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="43e5d-107">[out] A pointer to the number of dimensions.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="43e5d-108">요구 사항</span><span class="sxs-lookup"><span data-stu-id="43e5d-108">Requirements</span></span>  

 <span data-ttu-id="43e5d-109">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="43e5d-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="43e5d-110">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="43e5d-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="43e5d-111">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="43e5d-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="43e5d-112">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="43e5d-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
