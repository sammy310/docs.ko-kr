---
description: '자세히 알아보기: ICorDebugFrame:: GetChain 메서드'
title: ICorDebugFrame::GetChain 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugFrame.GetChain
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugFrame::GetChain
helpviewer_keywords:
- ICorDebugFrame::GetChain method [.NET Framework debugging]
- GetChain method [.NET Framework debugging]
ms.assetid: e28e51d3-8f73-494f-bcd4-48bac239fbe1
topic_type:
- apiref
ms.openlocfilehash: d162d484a54f107fb5937e57f60e2b82cad90ca1
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99693059"
---
# <a name="icordebugframegetchain-method"></a><span data-ttu-id="c5397-103">ICorDebugFrame::GetChain 메서드</span><span class="sxs-lookup"><span data-stu-id="c5397-103">ICorDebugFrame::GetChain Method</span></span>

<span data-ttu-id="c5397-104">이 프레임이 포함 된 체인에 대 한 포인터를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="c5397-104">Gets a pointer to the chain this frame is a part of.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c5397-105">구문</span><span class="sxs-lookup"><span data-stu-id="c5397-105">Syntax</span></span>  
  
```cpp  
HRESULT GetChain (  
    [out] ICorDebugChain     **ppChain  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c5397-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="c5397-106">Parameters</span></span>  

 `ppChain`  
 <span data-ttu-id="c5397-107">제한이 이 프레임을 포함 하는 체인을 나타내는 ICorDebugChain 개체의 주소에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="c5397-107">[out] A pointer to the address of an ICorDebugChain object that represents the chain containing this frame.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c5397-108">요구 사항</span><span class="sxs-lookup"><span data-stu-id="c5397-108">Requirements</span></span>  

 <span data-ttu-id="c5397-109">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c5397-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c5397-110">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="c5397-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c5397-111">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c5397-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c5397-112">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c5397-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
