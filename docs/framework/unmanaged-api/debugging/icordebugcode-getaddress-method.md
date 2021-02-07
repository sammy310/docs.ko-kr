---
description: '자세히 알아보기: ICorDebugCode:: GetAddress 메서드'
title: ICorDebugCode::GetAddress 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugCode.GetAddress
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugCode::GetAddress
helpviewer_keywords:
- GetAddress method, ICorDebugCode interface [.NET Framework debugging]
- ICorDebugCode::GetAddress method [.NET Framework debugging]
ms.assetid: cc507cb0-df2e-49c2-b32e-0c3271a8df9a
topic_type:
- apiref
ms.openlocfilehash: 4c074a407d8153703fd92aeddb53e9fa05b0ef01
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99711338"
---
# <a name="icordebugcodegetaddress-method"></a><span data-ttu-id="68b3b-103">ICorDebugCode::GetAddress 메서드</span><span class="sxs-lookup"><span data-stu-id="68b3b-103">ICorDebugCode::GetAddress Method</span></span>

<span data-ttu-id="68b3b-104">이 "ICorDebugCode" 인터페이스가 나타내는 코드 세그먼트의 RVA (상대 가상 주소)를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="68b3b-104">Gets the relative virtual address (RVA) of the code segment that this "ICorDebugCode" interface represents.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="68b3b-105">구문</span><span class="sxs-lookup"><span data-stu-id="68b3b-105">Syntax</span></span>  
  
```cpp  
HRESULT GetAddress (  
    [out] CORDB_ADDRESS *pStart  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="68b3b-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="68b3b-106">Parameters</span></span>  

 `pStart`  
 <span data-ttu-id="68b3b-107">제한이 코드 세그먼트의 RVA에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="68b3b-107">[out] A pointer to the RVA of the code segment.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="68b3b-108">요구 사항</span><span class="sxs-lookup"><span data-stu-id="68b3b-108">Requirements</span></span>  

 <span data-ttu-id="68b3b-109">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="68b3b-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="68b3b-110">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="68b3b-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="68b3b-111">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="68b3b-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="68b3b-112">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="68b3b-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
