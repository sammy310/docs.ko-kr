---
description: '자세히 알아보기: ICorDebugChain:: GetNext 메서드'
title: ICorDebugChain::GetNext 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugChain.GetNext
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugChain::GetNext
helpviewer_keywords:
- GetNext method [.NET Framework debugging]
- ICorDebugChain::GetNext method [.NET Framework debugging]
ms.assetid: 8d9744a5-e08b-4ab2-9855-5c22711cc1e6
topic_type:
- apiref
ms.openlocfilehash: ced7032feffa4c14c07341242b854c08b8c897a5
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99661326"
---
# <a name="icordebugchaingetnext-method"></a><span data-ttu-id="20425-103">ICorDebugChain::GetNext 메서드</span><span class="sxs-lookup"><span data-stu-id="20425-103">ICorDebugChain::GetNext Method</span></span>

<span data-ttu-id="20425-104">스레드에 대 한 다음 프레임 체인을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="20425-104">Gets the next chain of frames for the thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="20425-105">구문</span><span class="sxs-lookup"><span data-stu-id="20425-105">Syntax</span></span>  
  
```cpp  
HRESULT GetNext (  
    [out] ICorDebugChain     **ppChain  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="20425-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="20425-106">Parameters</span></span>  

 `ppChain`  
 <span data-ttu-id="20425-107">제한이 스레드에 대 한 다음 프레임 체인을 나타내는 ICorDebugChain 개체의 주소에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="20425-107">[out] A pointer to the address of an ICorDebugChain object that represents the next chain of frames for the thread.</span></span> <span data-ttu-id="20425-108">이 체인이 마지막 체인이 면 `ppChain` 가 null입니다.</span><span class="sxs-lookup"><span data-stu-id="20425-108">If this chain is the last chain, `ppChain` is null.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="20425-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="20425-109">Requirements</span></span>  

 <span data-ttu-id="20425-110">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="20425-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="20425-111">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="20425-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="20425-112">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="20425-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="20425-113">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="20425-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
