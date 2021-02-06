---
description: '자세히 알아보기: ICorDebugThread2:: GetVolatileOSThreadID 메서드'
title: ICorDebugThread2::GetVolatileOSThreadID 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugThread2.GetVolatileOSThreadID
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugThread2::GetVolatileOSThreadID
helpviewer_keywords:
- GetVolatileOSThreadID method [.NET Framework debugging]
- ICorDebugThread2::GetVolatileOSThreadID method [.NET Framework debugging]
ms.assetid: f0922545-c2cf-40c8-9ef6-ca033563e682
topic_type:
- apiref
ms.openlocfilehash: 2c198577195c9b1e4a3a74fae686e405b22120eb
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99658596"
---
# <a name="icordebugthread2getvolatileosthreadid-method"></a><span data-ttu-id="f5ac0-103">ICorDebugThread2::GetVolatileOSThreadID 메서드</span><span class="sxs-lookup"><span data-stu-id="f5ac0-103">ICorDebugThread2::GetVolatileOSThreadID Method</span></span>

<span data-ttu-id="f5ac0-104">이 ICorDebugThread2에 대 한 운영 체제 스레드 식별자를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="f5ac0-104">Gets the operating system thread identifier for this ICorDebugThread2.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f5ac0-105">구문</span><span class="sxs-lookup"><span data-stu-id="f5ac0-105">Syntax</span></span>  
  
```cpp  
HRESULT GetVolatileOSThreadID (  
    [out] DWORD    *pdwTid  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f5ac0-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="f5ac0-106">Parameters</span></span>  

 `pdwTid`  
 <span data-ttu-id="f5ac0-107">제한이 이 스레드에 대 한 운영 체제 스레드 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="f5ac0-107">[out] The operating system thread identifier for this thread.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f5ac0-108">요구 사항</span><span class="sxs-lookup"><span data-stu-id="f5ac0-108">Requirements</span></span>  

 <span data-ttu-id="f5ac0-109">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f5ac0-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f5ac0-110">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="f5ac0-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f5ac0-111">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f5ac0-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f5ac0-112">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f5ac0-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
