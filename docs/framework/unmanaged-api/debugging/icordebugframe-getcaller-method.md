---
description: '자세히 알아보기: ICorDebugFrame:: GetCaller 메서드'
title: ICorDebugFrame::GetCaller 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugFrame.GetCaller
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugFrame::GetCaller
helpviewer_keywords:
- GetCaller method, ICorDebugFrame interface [.NET Framework debugging]
- ICorDebugFrame::GetCaller method [.NET Framework debugging]
ms.assetid: bfdc946b-8238-4eb9-8a85-884049fb0fd4
topic_type:
- apiref
ms.openlocfilehash: a042341f6edfa0e8f6ca00f758107852f9e381cb
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99693046"
---
# <a name="icordebugframegetcaller-method"></a><span data-ttu-id="b244b-103">ICorDebugFrame::GetCaller 메서드</span><span class="sxs-lookup"><span data-stu-id="b244b-103">ICorDebugFrame::GetCaller Method</span></span>

<span data-ttu-id="b244b-104">현재 체인에서이 프레임을 호출한 ICorDebugFrame 개체에 대 한 포인터를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="b244b-104">Gets a pointer to the ICorDebugFrame object in the current chain that called this frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b244b-105">구문</span><span class="sxs-lookup"><span data-stu-id="b244b-105">Syntax</span></span>  
  
```cpp  
HRESULT GetCaller (  
    [out] ICorDebugFrame     **ppFrame  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b244b-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="b244b-106">Parameters</span></span>  

 `ppFrame`  
 <span data-ttu-id="b244b-107">제한이 호출 하는 프레임을 나타내는 개체의 주소에 대 한 포인터입니다 `ICorDebugFrame` .</span><span class="sxs-lookup"><span data-stu-id="b244b-107">[out] A pointer to the address of an `ICorDebugFrame` object that represents the calling frame.</span></span> <span data-ttu-id="b244b-108">호출 된 프레임이 현재 체인에서 가장 바깥쪽 프레임 이면이 값은 null입니다.</span><span class="sxs-lookup"><span data-stu-id="b244b-108">This value is null if the called frame is the outermost frame in the current chain.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b244b-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="b244b-109">Requirements</span></span>  

 <span data-ttu-id="b244b-110">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="b244b-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b244b-111">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="b244b-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="b244b-112">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b244b-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b244b-113">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b244b-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
