---
title: ICorDebugChain::EnumerateFrames 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugChain.EnumerateFrames
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugChain::EnumerateFrames method
helpviewer_keywords:
- EnumerateFrames method [.NET Framework debugging]
- ICorDebugChain::EnumerateFrames method [.NET Framework debugging]
ms.assetid: 9fcefa98-750d-4168-8915-8173a43accf2
topic_type:
- apiref
ms.openlocfilehash: c8a62d8b4a4db0f36d991c32dbfc5bad68780f1b
ms.sourcegitcommit: 957c49696eaf048c284ef8f9f8ffeb562357ad95
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/07/2020
ms.locfileid: "82894689"
---
# <a name="icordebugchainenumerateframes-method"></a><span data-ttu-id="06fff-102">ICorDebugChain::EnumerateFrames 메서드</span><span class="sxs-lookup"><span data-stu-id="06fff-102">ICorDebugChain::EnumerateFrames Method</span></span>
<span data-ttu-id="06fff-103">최신 프레임에서 시작 하 여 체인의 모든 관리 되는 스택 프레임을 포함 하는 열거자를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="06fff-103">Gets an enumerator that contains all the managed stack frames in the chain, starting with the most recent frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="06fff-104">구문</span><span class="sxs-lookup"><span data-stu-id="06fff-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumerateFrames (  
    [out] ICorDebugFrameEnum **ppFrames  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="06fff-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="06fff-105">Parameters</span></span>  
 `ppFrames`  
 <span data-ttu-id="06fff-106">제한이 스택 프레임의 열거자 인 ICorDebugFrameEnum 개체의 주소에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="06fff-106">[out] A pointer to the address of an ICorDebugFrameEnum object that is the enumerator for the stack frames.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="06fff-107">설명</span><span class="sxs-lookup"><span data-stu-id="06fff-107">Remarks</span></span>  
 <span data-ttu-id="06fff-108">체인은 스레드에 대 한 물리적 호출 스택을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="06fff-108">The chain represents the physical call stack for the thread.</span></span>  
  
 <span data-ttu-id="06fff-109">메서드 `EnumerateFrames` 는 관리 되는 체인에 대해서만 호출 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="06fff-109">The `EnumerateFrames` method should be called only for managed chains.</span></span> <span data-ttu-id="06fff-110">디버깅 API는 관리 되지 않는 체인에 포함 된 프레임을 얻기 위한 메서드를 제공 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="06fff-110">The debugging API does not provide methods for obtaining frames contained in unmanaged chains.</span></span> <span data-ttu-id="06fff-111">디버거는이 정보를 얻기 위해 다른 수단을 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="06fff-111">The debugger must use other means to obtain this information.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="06fff-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="06fff-112">Requirements</span></span>  
 <span data-ttu-id="06fff-113">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="06fff-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="06fff-114">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="06fff-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="06fff-115">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="06fff-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="06fff-116">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="06fff-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
