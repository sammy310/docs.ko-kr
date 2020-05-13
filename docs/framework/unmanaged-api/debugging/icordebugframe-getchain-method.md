---
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
ms.openlocfilehash: cab25738c9f4727fe3970cc1db15c38e68b08de6
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/12/2020
ms.locfileid: "83212921"
---
# <a name="icordebugframegetchain-method"></a><span data-ttu-id="a7b8b-102">ICorDebugFrame::GetChain 메서드</span><span class="sxs-lookup"><span data-stu-id="a7b8b-102">ICorDebugFrame::GetChain Method</span></span>
<span data-ttu-id="a7b8b-103">이 프레임이 포함 된 체인에 대 한 포인터를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="a7b8b-103">Gets a pointer to the chain this frame is a part of.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a7b8b-104">구문</span><span class="sxs-lookup"><span data-stu-id="a7b8b-104">Syntax</span></span>  
  
```cpp  
HRESULT GetChain (  
    [out] ICorDebugChain     **ppChain  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a7b8b-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="a7b8b-105">Parameters</span></span>  
 `ppChain`  
 <span data-ttu-id="a7b8b-106">제한이 이 프레임을 포함 하는 체인을 나타내는 ICorDebugChain 개체의 주소에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="a7b8b-106">[out] A pointer to the address of an ICorDebugChain object that represents the chain containing this frame.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a7b8b-107">요구 사항</span><span class="sxs-lookup"><span data-stu-id="a7b8b-107">Requirements</span></span>  
 <span data-ttu-id="a7b8b-108">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="a7b8b-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a7b8b-109">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="a7b8b-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a7b8b-110">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a7b8b-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a7b8b-111">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a7b8b-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
