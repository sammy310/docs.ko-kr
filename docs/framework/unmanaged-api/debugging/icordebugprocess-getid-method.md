---
description: '자세히 알아보기: ICorDebugProcess:: GetID 메서드'
title: ICorDebugProcess::GetID 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugProcess.GetID
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess::GetID
helpviewer_keywords:
- GetID method, ICorDebugProcess interface [.NET Framework debugging]
- ICorDebugProcess::GetID method [.NET Framework debugging]
ms.assetid: b0ba8453-fa7e-4c14-93e5-335409cd4a47
topic_type:
- apiref
ms.openlocfilehash: 806e73724a88d08235f4a3e751f771abace1ad56
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99746986"
---
# <a name="icordebugprocessgetid-method"></a><span data-ttu-id="78534-103">ICorDebugProcess::GetID 메서드</span><span class="sxs-lookup"><span data-stu-id="78534-103">ICorDebugProcess::GetID Method</span></span>

<span data-ttu-id="78534-104">프로세스의 OS (운영 체제) ID를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="78534-104">Gets the operating system (OS) ID of the process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="78534-105">구문</span><span class="sxs-lookup"><span data-stu-id="78534-105">Syntax</span></span>  
  
```cpp  
HRESULT GetID([out] DWORD *pdwProcessId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="78534-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="78534-106">Parameters</span></span>  

 `pdwProcessId`  
 <span data-ttu-id="78534-107">제한이 프로세스의 고유 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="78534-107">[out] The unique ID of the process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="78534-108">요구 사항</span><span class="sxs-lookup"><span data-stu-id="78534-108">Requirements</span></span>  

 <span data-ttu-id="78534-109">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="78534-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="78534-110">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="78534-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="78534-111">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="78534-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="78534-112">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="78534-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
