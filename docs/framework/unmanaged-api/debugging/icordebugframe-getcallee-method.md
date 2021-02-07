---
description: '자세히 알아보기: ICorDebugFrame:: GetCallee 메서드'
title: ICorDebugFrame::GetCallee 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugFrame.GetCallee
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugFrame::GetCallee
helpviewer_keywords:
- ICorDebugFrame::GetCallee method [.NET Framework debugging]
- GetCallee method, ICorDebugFrame interface [.NET Framework debugging]
ms.assetid: 92d8136d-0436-4c7e-a6b2-80765f892a0d
topic_type:
- apiref
ms.openlocfilehash: 85b64933cb2f180445b88f7b19f8b78f1788252e
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99693072"
---
# <a name="icordebugframegetcallee-method"></a><span data-ttu-id="7ff76-103">ICorDebugFrame::GetCallee 메서드</span><span class="sxs-lookup"><span data-stu-id="7ff76-103">ICorDebugFrame::GetCallee Method</span></span>

<span data-ttu-id="7ff76-104">이 프레임이 호출 하는 현재 체인의 ICorDebugFrame 개체에 대 한 포인터를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="7ff76-104">Gets a pointer to the ICorDebugFrame object in the current chain that this frame called.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7ff76-105">구문</span><span class="sxs-lookup"><span data-stu-id="7ff76-105">Syntax</span></span>  
  
```cpp  
HRESULT GetCallee (  
    [out] ICorDebugFrame     **ppFrame  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7ff76-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="7ff76-106">Parameters</span></span>  

 `ppFrame`  
 <span data-ttu-id="7ff76-107">제한이 호출 된 프레임을 나타내는 개체의 주소에 대 한 포인터 `ICorDebugFrame` 입니다.</span><span class="sxs-lookup"><span data-stu-id="7ff76-107">[out] A pointer to the address of an `ICorDebugFrame` object that represents the called frame.</span></span> <span data-ttu-id="7ff76-108">호출 하는 프레임이 현재 체인에서 가장 안쪽 프레임 이면이 값은 null입니다.</span><span class="sxs-lookup"><span data-stu-id="7ff76-108">This value is null if the calling frame is the innermost frame in the current chain.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7ff76-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="7ff76-109">Requirements</span></span>  

 <span data-ttu-id="7ff76-110">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="7ff76-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7ff76-111">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="7ff76-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="7ff76-112">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7ff76-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7ff76-113">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7ff76-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
