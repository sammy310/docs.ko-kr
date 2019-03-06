---
title: ICorDebugManagedCallback::Break 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugManagedCallback.Break
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback::Break
helpviewer_keywords:
- Break method [.NET Framework debugging]
- ICorDebugManagedCallback::Break method [.NET Framework debugging]
ms.assetid: 7d78a301-82b3-43b2-9d65-3cda3285ae97
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: bab20301c5413f8bbe95d44b87e06d3b3870c9e7
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/05/2019
ms.locfileid: "57377705"
---
# <a name="icordebugmanagedcallbackbreak-method"></a><span data-ttu-id="a7401-102">ICorDebugManagedCallback::Break 메서드</span><span class="sxs-lookup"><span data-stu-id="a7401-102">ICorDebugManagedCallback::Break Method</span></span>

<span data-ttu-id="a7401-103">디버거에 알립니다 때를 <xref:System.Reflection.Emit.OpCodes.Break> 코드 스트림의 명령이 실행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a7401-103">Notifies the debugger when a <xref:System.Reflection.Emit.OpCodes.Break> instruction in the code stream is executed.</span></span>

## <a name="syntax"></a><span data-ttu-id="a7401-104">구문</span><span class="sxs-lookup"><span data-stu-id="a7401-104">Syntax</span></span>

```cpp
HRESULT Break (
    [in] ICorDebugAppDomain *pAppDomain,
    [in] ICorDebugThread    *thread
);
```

## <a name="parameters"></a><span data-ttu-id="a7401-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="a7401-105">Parameters</span></span>

`pAppDomain`\
<span data-ttu-id="a7401-106">[in] 중단 명령이 포함 된 응용 프로그램 도메인을 나타내는 ICorDebugAppDomain 개체에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="a7401-106">[in] A pointer to an ICorDebugAppDomain object that represents the application domain that contains the break instruction.</span></span>

`thread`\
<span data-ttu-id="a7401-107">[in] 중단 명령이 포함 된 스레드를 나타내는 ICorDebugThread 개체에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="a7401-107">[in] A pointer to an ICorDebugThread object that represents the thread that contains the break instruction.</span></span>

## <a name="requirements"></a><span data-ttu-id="a7401-108">요구 사항</span><span class="sxs-lookup"><span data-stu-id="a7401-108">Requirements</span></span>

<span data-ttu-id="a7401-109">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="a7401-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>

<span data-ttu-id="a7401-110">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="a7401-110">**Header:** CorDebug.idl, CorDebug.h</span></span>

<span data-ttu-id="a7401-111">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a7401-111">**Library:** CorGuids.lib</span></span>

<span data-ttu-id="a7401-112">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a7401-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="a7401-113">참고자료</span><span class="sxs-lookup"><span data-stu-id="a7401-113">See also</span></span>

- [<span data-ttu-id="a7401-114">ICorDebugManagedCallback 인터페이스</span><span class="sxs-lookup"><span data-stu-id="a7401-114">ICorDebugManagedCallback Interface</span></span>](icordebugmanagedcallback-interface.md)