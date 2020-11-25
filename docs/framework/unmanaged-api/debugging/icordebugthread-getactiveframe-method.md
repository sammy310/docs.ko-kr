---
title: ICorDebugThread::GetActiveFrame 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugThread.GetActiveFrame
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugThread::GetActiveFrame
helpviewer_keywords:
- ICorDebugThread::GetActiveFrame method [.NET Framework debugging]
- GetActiveFrame method, ICorDebugThread interface [.NET Framework debugging]
ms.assetid: 8d6d3a1a-fef6-4f2f-a22c-3bdd30d70e07
topic_type:
- apiref
ms.openlocfilehash: 6ca4c1ad5ef575db075a5066146bacb6d1e59ea2
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95728084"
---
# <a name="icordebugthreadgetactiveframe-method"></a><span data-ttu-id="97b90-102">ICorDebugThread::GetActiveFrame 메서드</span><span class="sxs-lookup"><span data-stu-id="97b90-102">ICorDebugThread::GetActiveFrame Method</span></span>

<span data-ttu-id="97b90-103">이 ICorDebugThread 개체의 활성 (가장 최근) 프레임에 대 한 인터페이스 포인터를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="97b90-103">Gets an interface pointer to the active (most recent) frame on this ICorDebugThread object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="97b90-104">구문</span><span class="sxs-lookup"><span data-stu-id="97b90-104">Syntax</span></span>  
  
```cpp  
HRESULT GetActiveFrame (  
    [out] ICorDebugFrame   **ppFrame  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="97b90-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="97b90-105">Parameters</span></span>  

 `ppFrame`  
 <span data-ttu-id="97b90-106">제한이 프레임을 나타내는 ICorDebugFrame interface 개체의 주소에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="97b90-106">[out] A pointer to the address of an ICorDebugFrame interface object that represents a frame.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="97b90-107">설명</span><span class="sxs-lookup"><span data-stu-id="97b90-107">Remarks</span></span>  

 <span data-ttu-id="97b90-108">`ppFrame`현재 활성화 된 프레임이 없는 경우 매개 변수는 null입니다.</span><span class="sxs-lookup"><span data-stu-id="97b90-108">The `ppFrame` parameter is null if no frame is currently active.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="97b90-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="97b90-109">Requirements</span></span>  

 <span data-ttu-id="97b90-110">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="97b90-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="97b90-111">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="97b90-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="97b90-112">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="97b90-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="97b90-113">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="97b90-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
